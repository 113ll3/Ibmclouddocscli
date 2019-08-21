---

copyright:
  years: 2015, 2019
lastupdated: "2019-07-12"

keywords: cli, vpn cli plug-in, vpn plugin, cloud foundry vpn, vpn cli, install vpn plugin, vpn parameters

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:note: .note}

# cf CLI 的 VPN CLI 插件
{: #vpn_cli_for_cf}

您可以使用命令行界面 (CLI) 来配置和管理 {{site.data.keyword.vpn_full}} 服务。{{site.data.keyword.vpn_short}} CLI 插件提供两个版本：一个用于与 Cloud Foundry CLI 插件一起使用，另一个用于与 {{site.data.keyword.cloud}} CLI 插件一起使用。这两个版本的插件提供相同的功能。
{:shortdesc}

{{site.data.keyword.vpn_short}} 插件可用于 Windows、MAC 和 Linux 操作系统。请确保使用适合于您的插件。

## 安装 cf CLI 插件
{: #install-cf-cli-plugin}

开始之前，请先安装 cf CLI。有关详细信息，请参阅 [Cloud Foundry 命令行界面](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)。

## 安装 VPN CLI 插件
{: #install-vpn-cli-plugin}

如果已安装先前版本的 {{site.data.keyword.vpn_short}} CLI 插件，那么必须先将其卸载。请使用以下命令：
{: note}

```
cf uninstall-plugin vpn
```
{: codeblock}

### 本地安装

1. 从 [{{site.data.keyword.cloud_notm}} CLI 插件存储库](https://plugins.cloud.ibm.com/ui/repository.html#cf-plugins){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") 中，下载适用于您的平台的 {{site.data.keyword.vpn_short}} 插件。

2. 使用以下命令来安装 {{site.data.keyword.vpn_short}} 插件：

	切换到 {{site.data.keyword.vpn_short}} 插件所在位置，或指定插件位置的路径。
	{: note}

	- 对于 MS Windows 操作系统：
	```
	cf install-plugin vpn_windows64.exe
	```
	{: codeblock}

	- 对于 Apple MAC OS：
	```
	cf install-plugin vpn_mac_os_amd64
	```
	{: codeblock}

	- 对于 Linux 操作系统：
	```
	cf install-plugin vpn_linuxamd64
	```
	{: codeblock}

### 从 {{site.data.keyword.cloud_notm}} 存储库进行安装
{: #install-from-ibm-repo}

1. 将 {{site.data.keyword.cloud_notm}} 存储库添加到 Cloud Foundry CLI 存储库中。请使用以下命令：
	```
	cf add-plugin-repo "IBM Cloud" http://plugins.cloud.ibm.com
	```
	{: codeblock}

2. 运行以下命令：
	```
	cf install-plugin vpn -r IBM Cloud
	```
	{: codeblock}

##列出 VPN 服务命令
{: #list-vpn-cli-commands}

### cf vpn-create connection
{: #cli-vpn-create-connection}

创建 VPN 连接。
```
cf vpn-create connection <connection name> -g <gateway name> -k <preshared key> -subnets ["<subnet/mask>"] -cip <customer gateway IP address> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```

#### 参数
{: #p1}

**connection name：**连接的名称。

**gateway name：**网关的名称。

**-k：**预共享密钥。

**subnet/mask：**CIDR 格式的远程子网地址。

**customer gateway IP address：**VPN 隧道的远程端点 IP 地址。

##### 可选参数：
{: #op1}

**-d：**指定参数的描述。

**-peer_id：**远程同级的标识。VPN 隧道的另一个端点。

**-admin_state：**VPN 连接的状态。值：UP 或 DOWN。

**-dpd-action：**检测到同级无效时执行的操作。值：hold、clear、disabled、restart 和 restart-by-peer。缺省值：hold

**-gateway_ip：**本地 VPN 隧道端点的 IP 地址。

**-i：**发起者的状态。缺省值：bi-directional。

**-dpd-timeout：**终止会话之前的超时值（以秒为单位）。范围：6-86400 秒。缺省值：120 秒。保持活动的超时值必须大于保持活动的时间间隔值。

**-dpd-interval：**保持活动的时间间隔（以秒为单位）。按配置的时间间隔发送保持活动消息，以检查同级的活动性。范围：5-86399 秒。缺省值：15 秒

**-ike：**IKE 策略的名称。

**-ipsec：**IPSec 策略的名称。


### cf vpn-create ike
{: #cf-vpn-create}

创建 IKE 策略。
```
cf vpn-create ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### 参数
{: #p2}

**policy name：**IKE 策略的名称。

**gateway name：**网关的名称。

##### 可选参数：
{: #op2}

**-d：**指定参数的描述。

**-pfs：**Diffie-Hellman (DH) 组标识。值：Group2、Group5 和 Group14。缺省值：Group2

**-e：**加密算法。值：aes-128、aes-192、aes-256 和 3des。缺省值：aes-128

**-lv：**IKE 安全性关联的生存期值。范围：60-86400 秒。缺省值：86400 秒

**-auth：**授权算法。值：sha1 或 sha256

### cf vpn-create ipsec
{: #cf-vpn-create-ipsec}

创建 IPSec 策略。
```
cf vpn-create ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### 参数
{: #p3}

**policy name：**IPSec 策略的名称。

**gateway name：**网关的名称。

##### 可选参数：
{: #op3}

**-d：**指定参数的描述。

**-pfs：**Diffie-Hellman (DH) 组标识。值：Group2、Group5 和 Group14。缺省值：Group2

**-e：**加密算法。值：aes-128、aes-192、aes-256 和 3des。缺省值：aes-128

**-lv：**安全性关联的生存期值。范围：60-86400 秒。缺省值：3600 秒

**-auth：**授权算法。值：sha1 或 sha256

### cf vpn-create gateway

创建 VPN 网关。

```
cf vpn-create gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### 参数
{: #p4}

**gateway name：**网关的名称。

**-t：**要对其启用服务的容器。值：allSingleContainers、allContainerGroups 和 allContainers。缺省值：无缺省值，您必须指定类型。

#####可选参数：
{: #op4}

**-gateway_ip：**网关的 IP 地址。

**-subnets：**CIDR 格式的子网地址。

### cf vpn-show gateways
{: #cf-vpn-show-gateways}

显示有关当前网关的信息。
```
cf vpn-show gateways
```
{: codeblock}

### cf vpn-show ikes
{: #cf-vpn-show-ikes}

显示有关当前 IKE 连接的信息。
```
cf vpn-show ikes
```
{: codeblock}

### cf vpn-show ipsecs
{: #cf-vpn-show-ipsecs}

显示有关当前 IPSec 连接的信息。
```
cf vpn-show ipsecs
```
{: codeblock}

### cf vpn-show connections
{: #cf-vpn-show-connections}

显示有关所有当前连接的信息。
```
cf vpn-show connections
```
{: codeblock}

### cf vpn-show ike
{: #cf-vpn-show-ike}

显示有关 IKE 连接的信息。
```
cf vpn-show ike <policy name>
```
{: codeblock}

### cf vpn-show ipsec
{: #cf-vpn-show-ipsec}

显示有关 IPSec 连接的信息。
```
cf vpn-show ipsec <policy name>
```
{: codeblock}

### cf vpn-show gateway
{: #cf-vpn-show-gateway}

显示有关网关的连接信息。
```
cf vpn-show gateway <gateway name>
```
{: codeblock}

### cf vpn-show connection
{: #cf-vpn-show-connection}

显示有关特定连接的所有信息。
```
cf vpn-show connection <connection name>
```
{: codeblock}

### cf vpn-delete
{: #cf-vpn-delete}

删除现有连接、策略或网关。
```
cf vpn-delete ike <policy name>
```
{: codeblock}

```
cf vpn-delete ipsec <policy name>
```
{: codeblock}

```
cf vpn-delete connection <connection name>
```
{: codeblock}

```
cf vpn-delete gateway <gateway name>
```
{: codeblock}

### cf vpn-update connection
{: #cf-vpn-update-connection}

更新现有 VPN 连接。
```
cf vpn-update connection <connection name> -g <gateway name> -cip <customer gateway IP address> -subnets ["<subnet/mask>"] -k <preshared key> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```

#### 参数
{: #p5}

**connection name：**连接的名称。

##### 可选参数：
{: #op5}

**gateway name：**网关的名称。

**customer gateway IP address：**VPN 隧道的远程端点 IP 地址。

**subnet/mask：**CIDR 格式的子网地址。

**-k：**预共享密钥。

**-d：**指定参数的描述。

**-peer_id：**远程同级的标识。VPN 隧道的另一个端点。

**-admin_state：**VPN 连接的状态。值：UP 或 DOWN。

**-dpd-action：**检测到同级无效时执行的操作。值：hold、clear、disabled、restart 和 restart-by-peer。缺省值：hold

**-gateway_ip：**本地 VPN 隧道端点的 IP 地址。

**-i：**发起者的状态。缺省值：bi-directional。

**-dpd-timeout：**终止会话之前的超时值（以秒为单位）。范围：6-86400 秒。缺省值：120 秒

**-dpd-interval：**保持活动的时间间隔（以秒为单位）。按配置的时间间隔发送保持活动消息，以检查同级的活动性。范围：5-86399 秒。缺省值：15 秒

**-ike：**IKE 策略的名称。

**-ipsec：**IPSec 策略的名称。

### cf vpn-update ike
{: #cf-vpn-update-ike}

更新 IKE 策略。
```
cf vpn-update ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### 参数
{: #p6}

**policy name：**IKE 策略的名称。

##### 可选参数：
{: #op6}

**gateway name：**网关的名称。

**-d：**指定参数的描述。

**-pfs：**Diffie-Hellman (DH) 组标识。值：Group2、Group5 和 Group14。缺省值：Group2

**-e：**加密算法。值：aes-128、aes-192、aes-256 和 3des。缺省值：aes-128

**-lv：**IKE 安全性关联的生存期值。范围：60-86400 秒。缺省值：86400 秒

**-auth：**授权算法。值：sha1 或 sha256

### cf vpn-update ipsec
{: #cf-vpn-update-ipsec}

更新 IPSec 策略。
```
cf vpn-update ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### 参数
{: #p7}

**policy name：**IPSec 策略的名称。

##### 可选参数：
{: #op7}

**gateway name：**网关的名称。

**-d：**指定参数的描述。

**-pfs：**Diffie-Hellman (DH) 组标识。值：Group2、Group5 和 Group14。缺省值：Group2

**-e：**加密算法。值：aes-128、aes-192、aes-256 和 3des。缺省值：aes-128

**-lv：**安全性关联的生存期值。范围：60-86400 秒。缺省值：3600 秒

**-auth：**授权算法。值：sha1 或 sha256

### cf vpn-update gateway
{: #cf-vpn-update-gateway}

更新现有 VPN 网关。
```
cf vpn-update gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### 参数
{: #p8}

**gateway name：**网关的名称。

#####可选参数：
{: #op8}

**-t：**要对其启用服务的容器。值：allSingleContainers、allContainerGroups 和 allContainers。缺省值：无缺省值，您必须指定类型。

**-gateway_ip：**网关的 IP 地址。

**-subnets：**CIDR 格式的子网地址。

