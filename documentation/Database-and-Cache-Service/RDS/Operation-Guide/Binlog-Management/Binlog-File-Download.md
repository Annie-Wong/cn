# Binlog 文件下载
当您想获取云数据库 MySQL/Percona/MariaDB 实例的 Binlog 文件的时候，京东云提供了内网地址，外网地址供用户自行下载。

## 注意事项
* 内网地址，外网地址是有有效期的，如果超过了有效期地址会失效，需要点击下载按钮，才能生成下载弹出框，才能获取新地址。

## Binlog 下载 
1. 登录 [云数据库 RDS 控制台](https://rds-console.jdcloud.com/database)。
2. 选择需要进行 Binlog 文件下载的目标实例，点击目标实例的名称，进入到实例详情页。
3. 选择 ***备份管理*** 标签，点击 ***Binlog*** 标签进入 Binlog 的列表页，选择你要下载的 Binlog 文件，点击 ***操作*** 这一列的 ***下载***。
4. Binlog 下载弹出框参数说明
    * 地址有效期：内网地址，外网地址支持自定义有效期时间，超过设置的有效期时间后，相应的地址就会失效无法下载，最短可以支持 1 秒，最长不超过 24 小时。
    * 内网地址：提供内网访问的域名，比如可以通过和数据库实例在同一个 VPC 或者子网内的云主机访问这个地址，从而来下载 Binlog 文件。
    * 外网地址：提供公网访问的域名，可以通过互联网下载 Binlog 文件，下载速度受限于公网的网络带宽，所以如果你的公网网络带宽太小，并且备份文件太大的话，下载时间会比较长。
    * 点击 ***本地下载*** 按钮，直接通过浏览器的方式，下载 Binlog 文件。
    * 点击 **取消**按钮，放弃 Binlog 文件的下载。

![binlog](../../../../../image/RDS/binlog_download.jpg)

## Binlog 解压
> 京东云针对 Binlog 文件进行了压缩处理，所以下载到本地之后，需要先进行解压操作，才能通过标准工具进行 Binlog 文件解析

1. 下载备份的解压工具，[点击下载](http://jddb-common-public.oss.cn-north-1.jcloudcs.com/general_mysql_backup_extract_tool.zip)，并解压，工具名 mysql_backup_extract.py，使用示例如下

```
 # 查看帮助手册
 ./mysql_backup_extract.py -h
 
 # 解压实例的 Binlog 文件
 ./mysql_backup_extract.py  -f [需要解压的 binlog 文件名] 
```
