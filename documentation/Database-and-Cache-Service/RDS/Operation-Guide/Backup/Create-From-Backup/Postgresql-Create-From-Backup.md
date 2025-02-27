# PostgreSQL根据备份创建
云数据库 PostgreSQL 实例可以根据实例的备份，在同一个地域创建一个新实例。

## 注意事项 
* 新实例的规格不能小于备份所在源实例的规格
* *如果创建计费方式为按配置的资源，请确保您的账户余额（或代金券金额）不少于 50 元。

## 操作步骤
1. 登录 [云数据库 RDS 控制台]。
2. 选择需要进行根据备份新建实例的目标实例，点击目标实例的名称，进入到实例详情页。
3. 点击 **备份管理** 标签，选择目标备份文件，点击操作列 **根据备份创建** 按钮点击，进入创建页面：

      ![根据备份创建](../../../../image/RDS/create-backup.png)
4. 实例配置的参数说明如下：  

- 存储类型：不同的存储类性能和支持的大小不同。本地存储具有更好的性能，云盘的空间大小更为灵活，可按需创建。
- 规格：实例的CPU核数和内存大小。
- 存储空间：该存储空间包括数据空间、系统文件空间以及日志文件空间。
- 私有网络：只支持在私有网络中创建。如果用户没有私有网络及子网，可以通过【新建私有网络】和【新建子网】的链接创建私有网络和子网。创建完成后，点击【刷新】，就可以看到新创建的私有网络和子网了。
   - 在选择私有网络的时候，请确保需要连接数据库实例的云主机和数据库实例在同一个私有网络内。
   - 由于管理的需要，选择的子网保留若干剩余IP才允许创建实例。
      - PostgreSQL：需要10个以上的剩余IP
- 部署方式：目前支持单可用区部署，多可用区部署两种部署方式。
   - 多可用区部署：数据库主备分别位于不同的可用区，可用性更高，一个可用区发生故障，整个实例仍然可提供服务。
   - 单可用区部署：主从位于同一可用区，如果该可用区发生故障，整个实例无法对外提供服务。
- 基本信息
   - 实例名称：允许重复，名称的长度和字符有一定限制，具体以控制台为准。

5. 点击 **立即购买** 进入订单确认页。
6. 勾选完云数据库 RDS 服务条款，按照提示完成后续操作
