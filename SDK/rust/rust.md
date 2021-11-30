# 京东云 Rust 签名库
## 基本说明
京东云Rust签名工具提供了Rust语言访问京东云OpenAPI时的请求签名功能。

在开始调用京东云open API之前，需提前在京东云用户中心账户管理下的[AccessKey管理页面](https://uc.jdcloud.com/accesskey/index)申请accesskey和secretKey密钥对（简称AK/SK）。AK/SK信息请妥善保管，如果遗失可能会造成非法用户使用此信息操作您在云上的资源，给你造成数据和财产损失。


## Usage: 普通方式

### Cargo.toml

添加如下一段到你的 Cargo.toml

```
[dependencies]
jdcloud_signer = "0.1"
```

### 使用范例

详细范例参见 [client.rs](https://github.com/jdcloud-api/jdcloud-sdk-rust-signer/blob/master/examples/client.rs)

```sh
$ export JDCLOUD_AK="..."
$ export JDCLOUD_SK="..."
$ cargo run --example client
    Finished dev [unoptimized + debuginfo] target(s) in 0.37s
     Running `target/debug/examples/client`
status: 200 OK
content-type: "application/json; charset=utf-8"
transfer-encoding: "chunked"
connection: "close"
date: "Mon, 22 Jul 2019 09:18:34 GMT"
x-jdcloud-request-id: "bkrovrdrv8ewru46782326noreauvdsf"
x-jdcloud-operationid: "describeInstances"
x-jdcloud-upstream-latency: "310"
x-jdcloud-proxy-latency: "30"
via: "jd-gateway/1.0.1"
requestId: "bkrovrdrv8ewru46782326noreauvdsf"
```

## Usage: 只签名方式

如果你不喜欢 `reqwest`, 准备使用自己的http库，那么可以选择只做签名。

签名时我们会添加如下几个 Header 字段

* `User-Agent`: 如果未指定，那么设为 "JdcloudSdkRust/0.1.0", 如果已指定，则不做改动。
* `X-Jdcloud-Date`: 当前时间。
* `X-Jdcloud-Nonce`: 随机数。
* `Authorization`: 签名。

### Cargo.toml

添加如下一段到你的 Cargo.toml

```
[dependencies]
jdcloud_signer = { version = "0.1", default-features = false }
```

### 使用范例

```rust
use jdcloud_signer::{Credential, Signer};
use http::Request;

fn main() {
    let ak = "...";
    let sk = "...";
    let credential = Credential::new(ak, sk);
    let signer = Signer::new(credential, "vm".to_string(), "cn-north-1".to_string());

    let mut req = Request::builder();
    let mut req = req.method("GET")
        .uri("https://vm.jdcloud-api.com/v1/regions/cn-north-1/instances")
        .body("".to_string()).unwrap();
    signer.sign_request(&mut req).unwrap();
    println!("{}", req);
}
```

更多调用示例参考  [SDK使用Demo](https://github.com/jdcloud-api/jdcloud-sdk-rust-signer/tree/master/examples)





**注意：**

- 京东云并没有提供其他下载方式，请务必使用上述官方下载方式！

- version 的版本号需要使用京东云产品提供的最新版本号。例如：示例中VM所使用的最新版本号可到官方提供的API  [更新历史](../../API/Virtual-Machines/ChangeLog.md)  中查询到。

- 每支云产品都有自己的Client，当调用该产品API时，需使用该产品的Client。例如：使用云主机的VmClient只能调用云主机（Vm）的接口；使用高可用组的AgClient只能调用高可用组（Ag）的接口。


 
