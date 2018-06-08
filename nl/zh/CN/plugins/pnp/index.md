---

copyright:

  years: 2016, 2018

lastupdated: "2018-05-23"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# {{site.data.keyword.Bluemix_notm}} CLI 的专用网络对等连接插件
{: #private_network_cli}

使用专用网络对等连接命令行界面 (CLI) 可配置和管理两个 {{site.data.keyword.Bluemix}} 空间之间的专用网络对等连接。IBM Containers（Docker 容器）支持专用网络对等连接。{{site.data.keyword.Bluemix_notm}} 空间可以位于同一区域中的不同可用性区域中，也可以位于不同区域中。专用网络对等连接 CLI 插件可与 {{site.data.keyword.Bluemix_notm}} CLI 插件一起使用。

专用网络对等连接 CLI 插件可用于 Windows、MAC 和 Linux 操作系统。请确保使用适合于您的插件。

开始之前，请先创建 {{site.data.keyword.Bluemix_notm}} 空间。确保空间中的每个容器都具有来自不同网络的 IP 地址。

**注：**将专用网络对等连接用于 {{site.data.keyword.Bluemix_notm}} 空间后，如果需要删除该空间，请首先删除该空间内的专用网络对等连接。

首先，请安装 {{site.data.keyword.Bluemix_notm}} CLI。有关详细信息，请参阅 [IBM Cloud CLI](http://clis.ng.bluemix.net/ui/home.html)。

## 安装专用网络对等连接 CLI 插件

**注**：如果已安装先前版本的该插件，您需要将其卸载。使用以下命令来卸载插件：

```
ibmcloud plugin uninstall private-network-peering
```
### 本地安装
从 [{{site.data.keyword.ibmcloud_notm}} CLI Plugin Repository ![外部链接图标](../../../icons/launch-glyph.svg)](http://plugins.ng.ibmcloud.net/ui/repository.html#ibmcloud-plugins){: new_window} 下载适用于您的平台的专用网络对等连接插件。

使用以下命令来安装专用网络对等连接插件：

**注**：切换到插件所在位置，或指定插件位置的路径。

* 对于 Microsoft Windows 操作系统：

```
ibmcloud plugin install private-network-peering-windows-amd64.exe
```

* 对于 Apple MAC OS：

```
ibmcloud plugin install private-network-peering-darwin-amd64
```

* 对于 Linux 操作系统：

```
ibmcloud plugin install private-network-peering-linux-amd64
```

**注**：在为 Linux 操作系统安装插件时，如果看到错误消息指示许可权被拒绝，请运行以下命令并更改许可权：

```
chmod a+x ./private-network-peering-linux-amd64
```

### 从 {{site.data.keyword.ibmcloud_notm}} 存储库进行安装

执行以下步骤以从 {{site.data.keyword.ibmcloud_notm}} 存储库安装插件：

1. 添加 {{site.data.keyword.ibmcloud_notm}} 插件注册表端点：
	```
	ibmcloud plugin repo-add bluemix-bx http://plugins.ng.bluemix.net
	```

2. 运行以下命令：

	```
	ibmcloud plugin install private-network-peering -r bluemix-bx
	```

## 列出专用网络对等连接命令
支持以下命令。使用 `ibmcloud network` 命令可查看可用命令的列表：

|命令|描述
|
|-------------|------------------------------------------------|
|pnp-routers|列出用于对等连接的所有可用路由器|
|pnp-create|创建专用网络对等连接|
|pnp-delete|删除专用网络对等连接|
|pnp-show|列出所有专用网络对等连接|
{: caption="表 1. 专用网络对等连接命令" caption-side="top"}


### 命令用法
要查看命令的帮助信息，请运行：`ibmcloud network [command] -h`。

#### 列出用于对等连接的所有可用路由器
```
ibmcloud network pnp-routers [--verbose (or -v)]
```

#####可选参数
{: #op1}

* **--verbose（或 -v）**（标志）：查看有关每个路由器的详细网络信息。

######命令示例
{: #ex1}

查看有关所有路由器的网络信息：

	$ ibmcloud network pnp-routers
	Listing available routers ...
	OK

	IP              NAME            COMPUTE    REGION          ORGANIZATION    SPACE
	129.41.234.246  default-router  Container  US-South        ywu@us.ibm.com  demo1
	129.41.237.172  default-router  Container  US-South        ywu@us.ibm.com  demo2
	129.41.238.212  default-router  Container  United-Kingdom  ywu@us.ibm.com  demo3


查看有关所有路由器的详细网络信息：


	$ ibmcloud network pnp-routers -v
	Listing available routers ...
	OK

	Router 'bce1aa25-bad0-4cf1-a831-d53c16463d06':
	FIELD          VALUE
	IP             129.41.234.246
	Name           default-router
	Compute        Container
	Region         US-South
	Organization   ywu@us.ibm.com
	Space          demo1
	Networks       172.31.0.0/16

	Router '9ea160f2-1a30-44cd-bd25-794d441b274b':
	FIELD          VALUE
	IP             129.41.237.172
	Name           default-router
	Compute        Container
	Region         US-South
	Organization   ywu@us.ibm.com
	Space          demo2
	Networks       172.25.0.0/16

	...


#### 使用 IP 地址来创建专用网络对等连接
```
ibmcloud network pnp-create <router_ip> <router_ip> <name>
```

#####参数
{: #p1}

* **router_ip**：要连接的两个路由器的 IP 地址。可以使用 `ibmcloud network pnp-routers` 命令来查找 IP 地址
* **name**：专用网络对等连接的名称。

######命令示例
{: #ex2}

	$ ibmcloud network pnp-create 129.41.234.246 129.41.237.172 demo
	Creating private network peering connection 'demo' ...
	Connecting 'default-router(129.41.234.246)' and 'default-router(129.41.237.172)' ...
	OK

	Private network peering connection 'demo' created.


####使用连接名称来创建专用网络对等连接

```
ibmcloud network pnp-create -i <name>
```

#####参数
{: #p2}

* **--interactive (-i)**（标志）：以交互方式选择路由器。
* **name**：专用网络对等连接的名称。

######命令示例
{: #ex3}

	$ ibmcloud network pnp-create -i demo
	Creating private network peering connection 'demo' ...
	List of available routers (select TWO for peering):

	#  ROUTER                          COMPUTE    REGION          ORGANIZATION    SPACE
	1  default-router(129.41.234.246)  Container  US-South        ywu@us.ibm.com  demo1
	2  default-router(129.41.237.172)  Container  US-South        ywu@us.ibm.com  demo2
	3  default-router(129.41.238.212)  Container  United-Kingdom  ywu@us.ibm.com  demo3

	Select first router for peering> 1
	Select second router for peering> 2

	Connecting 'default-router(129.41.234.246)' and 'default-router(129.41.237.172)' ...
	OK

	Private network peering connection 'demo' created.


#### 列出所有专用网络对等连接
```
ibmcloud network pnp-show [--verbose (or -v)]
```

#####可选参数
{: #op2}

* **--verbose（或 -v）**（标志）：查看有关每个路由器的详细网络信息。

######命令示例
{: #ex4}

查看基本信息：

	$ ibmcloud network pnp-show
	Listing private network peering connections ...
	OK

	ID                                    NAME  STATUS  ROUTER1                         ROUTER2
	17b1c3c7-d614-4fc5-9afe-961e38ee79f8  demo  Active  default-router(129.41.234.246)  default-router(129.41.237.172)

查看详细信息：

	$ ibmcloud network pnp-show -v
	Listing private network peering connections ...
	OK

	Connection 'bedbc077-8040-41cc-a4aa-d9ce09a2e8ec':
	FIELD              VALUE
	Name               demo
	Status             Active
	Router1 Name       default-router
	Router1 IP         129.41.234.246
	Router1 Networks   172.31.0.0/16
	Router2 Name       default-router
	Router2 IP         129.41.237.172
	Router2 Networks   172.25.0.0/16


#### 删除专用网络对等连接
```
ibmcloud network pnp-delete [--force (or -f)] <connection_id>
```
#####参数
{: #p3}
* **connection_id**：一个或多个连接标识，用逗号分隔。

#####可选参数
{: #op3}

* **--force（或 -f）**（标志）：删除连接，而不提示确认。

######命令示例：
{: #ex5}

删除连接：

	$ ibmcloud network pnp-delete 17b1c3c7-d614-4fc5-9afe-961e38ee79f8
	Warning: deleted connections cannot be restored.
	Are you sure you want to delete the connection? (yes/no)> yes

	Deleting private network peering connection '17b1c3c7-d614-4fc5-9afe-961e38ee79f8' ...
	OK

	Private network peering connection '17b1c3c7-d614-4fc5-9afe-961e38ee79f8' deleted.


删除多个连接：

```
ibmcloud network pnp-delete [-f] <connection_id>,<connection_id>,<connection_id>
```
