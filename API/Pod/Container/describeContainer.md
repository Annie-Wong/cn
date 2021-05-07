# describeContainer


## 描述
获取 pod 中某个容器的详情

## 请求方式
GET

## 请求地址
https://pod.jdcloud-api.com/v1/regions/{regionId}/pods/{podId}/containers/{containerName}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |Region ID|
|**podId**|String|True| |Pod ID|
|**containerName**|String|True| |container name|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describecontainer#result)| |
|**requestId**|String| |

### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**container**|[Container](describecontainer#container)| |
### <div id="container">Container</div>
|名称|类型|描述|
|---|---|---|
|**name**|String|容器名称|
|**command**|String[]|容器执行的命令。|
|**args**|String[]|容器执行命令的参数。|
|**env**|[Env[]](describecontainer#env)|容器执行的环境变量。|
|**image**|String|容器镜像名称。|
|**secret**|String|容器镜像仓库认证信息。|
|**tty**|Boolean|容器是否分配tty。|
|**workingDir**|String|容器的工作目录。|
|**livenessProbe**|[Probe](describecontainer#probe)|容器存活探针配置|
|**readinessProbe**|[Probe](describecontainer#probe)|容器服务就绪探针配置|
|**resources**|[ResourceRequests](describecontainer#resourcerequests)|容器计算资源配置|
|**systemDisk**|[CloudDisk](describecontainer#clouddisk)|容器计算资源配置|
|**volumeMounts**|[VolumeMount[]](describecontainer#volumemount)|容器计算资源配置|
|**containerStatus**|[ContainerStatus](describecontainer#containerstatus)|容器状态信息|
### <div id="containerstatus">ContainerStatus</div>
|名称|类型|描述|
|---|---|---|
|**name**|String|容器名称|
|**restartCount**|Integer|容器被重新启动的次数|
|**ready**|Boolean|容器是否通过了就绪探针探测|
|**state**|[ContainerState](describecontainer#containerstate)|关于容器当前状态详细信息|
|**lastState**|[ContainerState](describecontainer#containerstate)|关于容器最后一次termination详细信息|
### <div id="containerstate">ContainerState</div>
|名称|类型|描述|
|---|---|---|
|**running**|[ContainerStateRunning](describecontainer#containerstaterunning)|容器运行的详细信息|
|**terminated**|[ContainerStateTerminated](describecontainer#containerstateterminated)|容器终止的详细信息|
|**waiting**|[ContainerStateWaiting](describecontainer#containerstatewaiting)|容器等待的详细信息|
### <div id="containerstatewaiting">ContainerStateWaiting</div>
|名称|类型|描述|
|---|---|---|
|**reason**|String|（简要）容器还没有运行原因。<br><br>eg ContainerCreating     <br>|
|**message**|String|容器还没有运行的详细信息。|
### <div id="containerstateterminated">ContainerStateTerminated</div>
|名称|类型|描述|
|---|---|---|
|**signal**|Integer|容器被终止的信号。|
|**exitCode**|Integer|容器被终止的退出码。|
|**reason**|String|（简要）容器被终止的原因。|
|**message**|String|容器被终止的详细信息。|
|**finishedAt**|String|容器被终止的时间。|
|**startedAt**|String|容器开始执行的时间。|
### <div id="containerstaterunning">ContainerStateRunning</div>
|名称|类型|描述|
|---|---|---|
|**startedAt**|String|容器最后一次重启或启动的时间。|
### <div id="volumemount">VolumeMount</div>
|名称|类型|描述|
|---|---|---|
|**name**|String|挂载的云盘在pod中的名称。|
|**mountPath**|String|容器内挂载点。|
|**readOnly**|Boolean|是否以只读方式挂载。|
### <div id="clouddisk">CloudDisk</div>
|名称|类型|描述|
|---|---|---|
|**category**|String| 磁盘类型|
|**volumeId**|String|云盘ID。|
|**snapshotId**|String|云盘快照ID。|
|**diskType**|String|云盘类型：hdd.std1,ssd.gp1,ssd.io1。|
|**sizeGB**|Integer|云盘size,单位 GB。|
|**fsType**|String|指定volume文件系统类型，目前支持[xfs, ext4]。|
|**iops**|Integer|云盘的 iops 值，目前只有 ssd.io1 类型有效。|
|**autoDelete**|Boolean|是否随pod删除。|
### <div id="resourcerequests">ResourceRequests</div>
|名称|类型|描述|
|---|---|---|
|**requests**|[Request](describecontainer#request)|容器必需的计算资源|
|**limits**|[Request](describecontainer#request)|容器使用计算资源上限|
### <div id="request">Request</div>
|名称|类型|描述|
|---|---|---|
|**cpu**|String|容器必需的计算资源|
|**memoryMB**|String|容器使用计算资源上限|
### <div id="probe">Probe</div>
|名称|类型|描述|
|---|---|---|
|**initialDelaySeconds**|Integer|容器启动多久后触发探针。|
|**periodSeconds**|Integer|探测的时间间隔。|
|**timeoutSeconds**|Integer|探测的超时时间。|
|**failureThreshold**|Integer|在成功状态后，连续探活失败的次数，认为探活失败。|
|**successThreshold**|Integer|在失败状态后，连续探活成功的次数，认为探活成功。|
|**exec**|[Exec](describecontainer#exec)|在容器内执行指定命令；如果命令退出时返回码为 0 则认为诊断成功。|
|**httpGet**|[Hg](describecontainer#hg)|对指定的端口和路径上的容器的 IP 地址执行 HTTP Get 请求。如果响应的状态码大于等于 200 且小于 400，则认为诊断成功。|
|**tcpSocket**|[TcpSocket](describecontainer#tcpsocket)|对指定端口上的容器的 IP 地址进行 TCP 检查；如果端口打开，则认为诊断成功。|
### <div id="tcpsocket">TcpSocket</div>
|名称|类型|描述|
|---|---|---|
|**port**|Integer|端口号，范围：[1-65535]|
### <div id="hg">Hg</div>
|名称|类型|描述|
|---|---|---|
|**scheme**|String|默认值：http。|
|**host**|String|连接到pod的host信息。|
|**port**|Integer|端口号。|
|**path**|String|HTTP的路径。|
|**httpHeader**|[Hh[]](describecontainer#hh)|自定义Http headers|
### <div id="hh">Hh</div>
|名称|类型|描述|
|---|---|---|
|**name**|String|http header 键|
|**value**|String|http header 值|
### <div id="exec">Exec</div>
|名称|类型|描述|
|---|---|---|
|**command**|String[]|执行的命令。|
### <div id="env">Env</div>
|名称|类型|描述|
|---|---|---|
|**name**|String|环境变量名称（ASCII）。|
|**value**|String|环境变量取值。|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|
