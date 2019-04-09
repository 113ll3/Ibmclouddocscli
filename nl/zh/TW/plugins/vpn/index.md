---

copyright:

  years: 2015, 2017

lastupdated: "2017-01-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}


# 適用於 cf CLI 的 VPN CLI 外掛程式
{: #vpn_cli_for_cf}


您可以使用指令行介面 (CLI) 來配置及管理 {{site.data.keyword.vpn_full}} 服務。{{site.data.keyword.vpn_short}} CLI 外掛程式有兩個版本：一個適用於 Cloud Foundry CLI 外掛程式，另一個適用於 {{site.data.keyword.Bluemix}} CLI 外掛程式。這兩個版本的外掛程式都提供相同的功能。
{:shortdesc}

{{site.data.keyword.vpn_short}} 外掛程式適用於 Windows、MAC 和 Linux 作業系統。請確定您是使用適用的版本。

下列指示適用於使用 Cloud Foundry (cf) CLI 外掛程式。若要搭配使用此外掛程式與 {{site.data.keyword.Bluemix_notm}} CLI 外掛程式，請參閱[適用於 {{site.data.keyword.Bluemix_notm}} CLI 的 {{site.data.keyword.vpn_short}} 外掛程式 ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/plugins/bx_vpn/index.html){: new_window}。

## 安裝 cf CLI 外掛程式
開始之前，請先安裝 cf CLI。如需詳細資料，請參閱 [Cloud Foundry 指令行介面 ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/downloads.html){: new_window}。

## 安裝 VPN CLI 外掛程式
**附註：**如果您已安裝舊版的 {{site.data.keyword.vpn_short}} CLI 外掛程式，則必須先將它解除安裝。使用以下指令：

```
cf uninstall-plugin vpn
```

### 在本端安裝

1. 從 [ {{site.data.keyword.Bluemix_notm}}  CLI 外掛程式儲存庫 ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/repository.html#cf-plugins){: new_window} 下載您平台的 {{site.data.keyword.vpn_short}} 外掛程式。
2. 使用下列指令，以安裝 {{site.data.keyword.vpn_short}} 外掛程式：**附註：**請切換至 {{site.data.keyword.vpn_short}} 外掛程式的位置，或指定外掛程式位置的路徑。

	- 若為 MS Windows OS：

	```
	cf install-plugin vpn_windows64.exe
	```

	- 若為 Apple MAC OS：

	```
	cf install-plugin vpn_mac_os_amd64
	```

	- 若為 Linux OS：

	```
	cf install-plugin vpn_linuxamd64
	```


### 從 {{site.data.keyword.Bluemix_notm}} 儲存庫安裝

1. 將 {{site.data.keyword.Bluemix_notm}} 儲存庫新增至 Cloud Foundry CLI 儲存庫。使用下列指令：

	```
	cf add-plugin-repo bluemix http://plugins.ng.bluemix.net
	```
2. 請執行下列指令：

	```
	cf install-plugin vpn -r bluemix
	```
##VPN 服務指令清單

### cf vpn-create connection

建立 VPN 連線。

```
cf vpn-create connection <connection name> -g <gateway name> -k <preshared key> -subnets ["<subnet/mask>"] -cip <customer gateway IP address> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```
#### 參數
{: #p1}

**connection name**：連線的名稱。

**gateway name**：閘道的名稱。

**-k**：預先共用金鑰。

**subnet/mask**：遠端子網路位址（CIDR 格式）。

**customer gateway IP address**：VPN 通道的遠端端點 IP 位址。

##### 選用性參數：
{: #op1}

**-d**：指定參數的說明。

**-peer_id**：遠端對等節點的 ID。VPN 通道的其他端點。

**-admin_state**：VPN 連線的狀態。值：UP 或 DOWN。

**-dpd-action**：偵測到對等節點已停用時所要採取的動作。值：hold、clear、disabled、restart 及 restart-by-peer。預設值：hold

**-gateway_ip**：本端 VPN 通道端點的 IP 位址。

**-i**：起始器的狀態。預設值：bi-directional。

**-dpd-timeout**：逾時值（以秒為單位），在此期間之後會終止階段作業。範圍：6 - 86400 秒。預設值：120 秒。保留作用中逾時值必須高於保留作用中間隔值。

**-dpd-interval**：保留作用中間隔（以秒為單位）。依配置的間隔傳送保留作用中訊息，以檢查對等節點是否活躍。範圍：5-86399 秒。預設值：15 秒

**-ike**：IKE 原則的名稱。

**-ipsec**：IPsec 原則的名稱。


### cf vpn-create ike

建立 IKE 原則。

```
cf vpn-create ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### 參數
{: #p2}

**policy name**：IKE 原則的名稱。

**gateway name**：閘道的名稱。

##### 選用性參數：
{: #op2}

**-d**：指定參數的說明。

**-pfs**：Diffie-Hellman (DH) 群組 ID。值：Group2、Group5 及 Group14。預設值：Group2

**-e**：加密演算法。值：aes-128、aes-192、aes-256 及 3des。預設值：aes-128

**-lv**：IKE 安全關聯的生命期限值。範圍：60 - 86400 秒。預設值：86400 秒

**-auth**：授權演算法。值：sha1 或 sha256


### cf vpn-create ipsec

建立 IPSec 原則。

```
cf vpn-create ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### 參數
{: #p3}

**policy name**：IPsec 原則的名稱。

**gateway name**：閘道的名稱。

##### 選用性參數：
{: #op3}

**-d**：指定參數的說明。

**-pfs**：Diffie-Hellman (DH) 群組 ID。值：Group2、Group5 及 Group14。預設值：Group2

**-e**：加密演算法。值：aes-128、aes-192、aes-256 及 3des。預設值：aes-128

**-lv**：安全關聯的生命期限值。範圍：60 - 86400 秒。預設值：3600 秒

**-auth**：授權演算法。值：sha1 或 sha256

### cf vpn-create gateway

建立 VPN 閘道。

```
cf vpn-create gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### 參數
{: #p4}

**gateway name**：閘道的名稱。

**-t**：您要啟用服務的容器。值：allSingleContainers、allContainerGroups、allContainers。預設值：無預設值；您必須指定類型。

#####選用性參數：
{: #op4}

**-gateway_ip**：閘道的 IP 位址。

**-subnets**：子網路位址（CIDR 格式）。

### cf vpn-show gateways

顯示現行閘道的相關資訊。

```
cf vpn-show gateways
```
### cf vpn-show ikes

顯示現行 IKE 連線的相關資訊。

```
cf vpn-show ikes
```
### cf vpn-show ipsecs

顯示現行 IPsec 連線的相關資訊。

```
cf vpn-show ipsecs
```
### cf vpn-show connections

顯示所有現行連線的相關資訊。

```
cf vpn-show connections
```
### cf vpn-show ike

顯示 IKE 連線的相關資訊。

```
cf vpn-show ike <policy name>
```
### cf vpn-show ipsec

顯示 IPsec 連線的相關資訊。

```
cf vpn-show ipsec <policy name>
```
### cf vpn-show gateway

顯示閘道的連線資訊。

```
cf vpn-show gateway <gateway name>
```
### cf vpn-show connection

顯示特定連線的所有資訊。

```
cf vpn-show connection <connection name>
```
### cf vpn-delete

刪除現有連線、原則或閘道。

```
cf vpn-delete ike <policy name>
```

```
cf vpn-delete ipsec <policy name>
```

```
cf vpn-delete connection <connection name>
```

```
cf vpn-delete gateway <gateway name>
```


### cf vpn-update connection

更新現有 VPN 連線。

```
cf vpn-update connection <connection name> -g <gateway name> -cip <customer gateway IP address> -subnets ["<subnet/mask>"] -k <preshared key> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```
#### 參數
{: #p5}

**connection name**：連線的名稱。


##### 選用性參數：
{: #op5}

**gateway name**：閘道的名稱。

**customer gateway IP address**：VPN 通道的遠端端點 IP 位址。

**subnet/mask**：子網路位址（CIDR 格式）。

**-k**：預先共用金鑰。

**-d**：指定參數的說明。

**-peer_id**：遠端對等節點的 ID。VPN 通道的其他端點。

**-admin_state**：VPN 連線的狀態。值：UP 或 DOWN。

**-dpd-action**：偵測到對等節點已停用時所要採取的動作。值：hold、clear、disabled、restart 及 restart-by-peer。預設值：hold

**-gateway_ip**：本端 VPN 通道端點的 IP 位址。

**-i**：起始器的狀態。預設值：bi-directional。

**-dpd-timeout**：逾時值（以秒為單位），在此期間之後會終止階段作業。範圍：6 - 86400 秒。預設值：120 秒

**-dpd-interval**：保留作用中間隔（以秒為單位）。依配置的間隔傳送保留作用中訊息，以檢查對等節點是否活躍。範圍：5-86399 秒。預設值：15 秒

**-ike**：IKE 原則的名稱。

**-ipsec**：IPsec 原則的名稱。


### cf vpn-update ike

更新 IKE 原則。

```
cf vpn-update ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### 參數
{: #p6}

**policy name**：IKE 原則的名稱。

##### 選用性參數：
{: #op6}

**gateway name**：閘道的名稱。

**-d**：指定參數的說明。

**-pfs**：Diffie-Hellman (DH) 群組 ID。值：Group2、Group5 及 Group14。預設值：Group2

**-e**：加密演算法。值：aes-128、aes-192、aes-256 及 3des。預設值：aes-128

**-lv**：IKE 安全關聯的生命期限值。範圍：60 - 86400 秒。預設值：86400 秒

**-auth**：授權演算法。值：sha1 或 sha256


### cf vpn-update ipsec

更新 IPSec 原則。

```
cf vpn-update ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### 參數
{: #p7}

**policy name**：IPsec 原則的名稱。


##### 選用性參數：
{: #op7}

**gateway name**：閘道的名稱。

**-d**：指定參數的說明。

**-pfs**：Diffie-Hellman (DH) 群組 ID。值：Group2、Group5 及 Group14。預設值：Group2

**-e**：加密演算法。值：aes-128、aes-192、aes-256 及 3des。預設值：aes-128

**-lv**：安全關聯的生命期限值。範圍：60 - 86400 秒。預設值：3600 秒

**-auth**：授權演算法。值：sha1 或 sha256

### cf vpn-update gateway

更新現有 VPN 閘道。

```
cf vpn-update gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### 參數
{: #p8}

**gateway name**：閘道的名稱。

#####選用性參數：
{: #op8}

**-t**：您要啟用服務的容器。值：allSingleContainers、allContainerGroups、allContainers。預設值：無預設值；您必須指定類型。

**-gateway_ip**：閘道的 IP 位址。

**-subnets**：子網路位址（CIDR 格式）。

# rellinks
## general
{: #general}
* [IBM VPN 服務](/docs/services/vpn/index.html)
* [Cloud Foundry CLI ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/downloads.html){: new_window}
