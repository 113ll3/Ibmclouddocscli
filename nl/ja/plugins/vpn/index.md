---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-03"

keywords: cli, vpn cli plug-in, vpn plugin, cloud foundry vpn, vpn cli, install vpn plugin, vpn parameters

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:note: .note}

# cf CLI 用の VPN CLI プラグイン
{: #vpn_cli_for_cf}

コマンド・ライン・インターフェース (CLI) を使用して、{{site.data.keyword.vpn_full}} サービスの構成と管理を行うことができます。 {{site.data.keyword.vpn_short}} CLI プラグインには、2 つのバージョンがあります。1 つは Cloud Foundry CLI プラグインで使用するためのものであり、もう 1 つは {{site.data.keyword.cloud}} CLI プラグインで使用するためのものです。 どちらのバージョンのプラグインも同じ機能を提供します。
{:shortdesc}

{{site.data.keyword.vpn_short}} プラグインには、Windows、MAC、および Linux オペレーティング・システム用があります。 環境に適したものを使用してください。

## cf CLI プラグインのインストール
{: #install-cf-cli-plugin}

始めに、cf CLI をインストールします。 詳しくは、 [『Cloud Foundry command line interface』](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)を参照してください。

## VPN CLI プラグインのインストール
{: #install-vpn-cli-plugin}

{{site.data.keyword.vpn_short}} CLI プラグインの以前のバージョンがインストールされている場合は、最初にそれをアンインストールする必要があります。 以下のコマンドを使用します。
{: note}

```
cf uninstall-plugin vpn
```
{: codeblock}

### ローカル・インストール

1. ご使用のプラットフォーム用の {{site.data.keyword.vpn_short}} プラグインを [{{site.data.keyword.cloud_notm}} CLI プラグイン・リポジトリー ](https://plugins.cloud.ibm.com/ui/repository.html#cf-plugins){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") からダウンロードします。

2. 以下のコマンドを使用して、{{site.data.keyword.vpn_short}} プラグインをインストールします。

	{{site.data.keyword.vpn_short}} プラグインの場所に移動するか、このプラグインの場所のパスを指定します。
	{: note}

	- MS Windows OS の場合:
	```
	cf install-plugin vpn_windows64.exe
	```
	{: codeblock}

	- Apple MAC OS の場合:
	```
	cf install-plugin vpn_mac_os_amd64
	```
	{: codeblock}

	- Linux OS の場合:
	```
	cf install-plugin vpn_linuxamd64
	```
	{: codeblock}

### {{site.data.keyword.cloud_notm}} リポジトリーからのインストール
{: #install-from-ibm-repo}

1. {{site.data.keyword.cloud_notm}} リポジトリーを Cloud Foundry CLI のリポジトリーに追加します。 次のコマンドを使用します。
	```
	cf add-plugin-repo "IBM Cloud" http://plugins.cloud.ibm.com
	```
	{: codeblock}

2. 次のコマンドを実行します。
	```
	cf install-plugin vpn -r IBM Cloud
	```
	{: codeblock}

##VPN サービス・コマンドのリスト
{: #list-vpn-cli-commands}

### cf vpn-create connection
{: #cli-vpn-create-connection}

VPN 接続を作成します。
```
cf vpn-create connection <connection name> -g <gateway name> -k <preshared key> -subnets ["<subnet/mask>"] -cip <customer gateway IP address> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```

#### パラメーター
{: #p1}

**connection name:** 接続の名前。

**gateway name:** ゲートウェイの名前。

**-k:**
事前共有鍵。

**subnet/mask:** CIDR フォーマットでのリモート・サブネット・アドレス。

**customer gateway IP address:** VPN トンネルのリモート・エンドポイント IP アドレス。

##### オプションのパラメーター:
{: #op1}

**-d:** 指定されたパラメーターの説明。

**-peer_id:** リモート・ピアの ID。 VPN トンネルの相手側のエンドポイント。

**-admin_state:** VPN 接続の状況。 値: UP または DOWN。

**-dpd-action:** ピアが非活動として検出された場合に取るアクション。 値: hold、clear、disabled、restart、restart-by-peer。 デフォルト値: hold

**-gateway_ip:** ローカル VPN トンネル・エンドポイントの IP アドレス。

**-i:** イニシエーターの状態。 デフォルト値: bi-directional。

**-dpd-timeout:** セッションが終了するまでのタイムアウト値 (秒)。 範囲: 6 秒から 86400 秒。 デフォルト値: 120 秒。 キープアライブ・タイムアウトの値は、キープアライブ間隔の値よりも高くなければなりません。

**-dpd-interval:** キープアライブ間隔 (秒)。 ピアの活動状態を確認するために、構成された間隔でキープアライブ・メッセージを送信します。 範囲: 5 秒から 86399 秒。 デフォルト値: 15 秒

**-ike:** IKE ポリシーの名前。

**-ipsec:** IPSec ポリシーの名前。


### cf vpn-create ike
{: #cf-vpn-create}

IKE ポリシーを作成します。
```
cf vpn-create ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### パラメーター
{: #p2}

**policy name:** IKE ポリシーの名前。

**gateway name:** ゲートウェイの名前。

##### オプションのパラメーター:
{: #op2}

**-d:** 指定されたパラメーターの説明。

**-pfs:** Diffie-Hellman (DH) グループ ID。 値: Group2、Group5、Group14。 デフォルト値: Group2

**-e:** 暗号化アルゴリズム。 値: aes-128、aes-192、aes-256、3des。 デフォルト値: aes-128

**-lv:** IKE セキュリティー・アソシエーションの存続時間値。 範囲: 60 秒から 86400 秒。 デフォルト値: 86400 秒

**-auth:** 許可アルゴリズム。 値: sha1 または sha256

### cf vpn-create ipsec
{: #cf-vpn-create-ipsec}

IPSec ポリシーを作成します。
```
cf vpn-create ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### パラメーター
{: #p3}

**policy name:** IPSec ポリシーの名前。

**gateway name:** ゲートウェイの名前。

##### オプションのパラメーター:
{: #op3}

**-d:** 指定されたパラメーターの説明。

**-pfs:** Diffie-Hellman (DH) グループ ID。 値: Group2、Group5、Group14。 デフォルト値: Group2

**-e:** 暗号化アルゴリズム。 値: aes-128、aes-192、aes-256、3des。 デフォルト値: aes-128

**-lv:** セキュリティー・アソシエーションの存続時間の値。 範囲: 60 秒から 86400 秒。 デフォルト値: 3600 秒

**-auth:** 許可アルゴリズム。 値: sha1 または sha256

### cf vpn-create gateway

VPN ゲートウェイを作成します。

```
cf vpn-create gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### パラメーター
{: #p4}

**gateway name:** ゲートウェイの名前。

**-t:** サービスを有効にするコンテナー。 値: allSingleContainers、allContainerGroups、allContainers。 デフォルト値: デフォルト値はありません。タイプを指定する必要があります。

#####オプションのパラメーター:
{: #op4}

**-gateway_ip:**
ゲートウェイの IP アドレス。

**-subnets:**
CIDR 形式のサブネット・アドレス。

### cf vpn-show gateways
{: #cf-vpn-show-gateways}

現在のゲートウェイについての情報が表示されます。
```
cf vpn-show gateways
```
{: codeblock}

### cf vpn-show ikes
{: #cf-vpn-show-ikes}

現在の IKE 接続についての情報が表示されます。
```
cf vpn-show ikes
```
{: codeblock}

### cf vpn-show ipsecs
{: #cf-vpn-show-ipsecs}

現在の IPSec 接続についての情報が表示されます。
```
cf vpn-show ipsecs
```
{: codeblock}

### cf vpn-show connections
{: #cf-vpn-show-connections}

現在の接続すべてについての情報が表示されます。
```
cf vpn-show connections
```
{: codeblock}

### cf vpn-show ike
{: #cf-vpn-show-ike}

IKE 接続についての情報が表示されます。
```
cf vpn-show ike <policy name>
```
{: codeblock}

### cf vpn-show ipsec
{: #cf-vpn-show-ipsec}

IPSec 接続についての情報が表示されます。
```
cf vpn-show ipsec <policy name>
```
{: codeblock}

### cf vpn-show gateway
{: #cf-vpn-show-gateway}

ゲートウェイについての接続情報が表示されます。
```
cf vpn-show gateway <gateway name>
```
{: codeblock}

### cf vpn-show connection
{: #cf-vpn-show-connection}

特定の接続についてのすべての情報が表示されます。
```
cf vpn-show connection <connection name>
```
{: codeblock}

### cf vpn-delete
{: #cf-vpn-delete}

既存の接続、ポリシー、またはゲートウェイを削除します。
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

既存の VPN 接続を更新します。
```
cf vpn-update connection <connection name> -g <gateway name> -cip <customer gateway IP address> -subnets ["<subnet/mask>"] -k <preshared key> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```

#### パラメーター
{: #p5}

**connection name:** 接続の名前。

##### オプションのパラメーター:
{: #op5}

**gateway name:** ゲートウェイの名前。

**customer gateway IP address:** VPN トンネルのリモート・エンドポイント IP アドレス。

**subnet/mask:** CIDR フォーマットでのサブネット・アドレス。

**-k:**
事前共有鍵。

**-d:** 指定されたパラメーターの説明。

**-peer_id:** リモート・ピアの ID。 VPN トンネルの相手側のエンドポイント。

**-admin_state:** VPN 接続の状況。 値: UP または DOWN。

**-dpd-action:** ピアが非活動として検出された場合に取るアクション。 値: hold、clear、disabled、restart、restart-by-peer。 デフォルト値: hold

**-gateway_ip:** ローカル VPN トンネル・エンドポイントの IP アドレス。

**-i:** イニシエーターの状態。 デフォルト値: bi-directional。

**-dpd-timeout:** セッションが終了するまでのタイムアウト値 (秒)。 範囲: 6 秒から 86400 秒。 デフォルト値: 120 秒

**-dpd-interval:** キープアライブ間隔 (秒)。 ピアの活動状態を確認するために、構成された間隔でキープアライブ・メッセージを送信します。 範囲: 5 秒から 86399 秒。 デフォルト値: 15 秒

**-ike:** IKE ポリシーの名前。

**-ipsec:** IPSec ポリシーの名前。

### cf vpn-update ike
{: #cf-vpn-update-ike}

IKE ポリシーを更新します。
```
cf vpn-update ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### パラメーター
{: #p6}

**policy name:** IKE ポリシーの名前。

##### オプションのパラメーター:
{: #op6}

**gateway name:** ゲートウェイの名前。

**-d:** 指定されたパラメーターの説明。

**-pfs:** Diffie-Hellman (DH) グループ ID。 値: Group2、Group5、Group14。 デフォルト値: Group2

**-e:** 暗号化アルゴリズム。 値: aes-128、aes-192、aes-256、3des。 デフォルト値: aes-128

**-lv:** IKE セキュリティー・アソシエーションの存続時間値。 範囲: 60 秒から 86400 秒。 デフォルト値: 86400 秒

**-auth:** 許可アルゴリズム。 値: sha1 または sha256

### cf vpn-update ipsec
{: #cf-vpn-update-ipsec}

IPSec ポリシーを更新します。
```
cf vpn-update ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```

#### パラメーター
{: #p7}

**policy name:** IPSec ポリシーの名前。

##### オプションのパラメーター:
{: #op7}

**gateway name:** ゲートウェイの名前。

**-d:** 指定されたパラメーターの説明。

**-pfs:** Diffie-Hellman (DH) グループ ID。 値: Group2、Group5、Group14。 デフォルト値: Group2

**-e:** 暗号化アルゴリズム。 値: aes-128、aes-192、aes-256、3des。 デフォルト値: aes-128

**-lv:** セキュリティー・アソシエーションの存続時間の値。 範囲: 60 秒から 86400 秒。 デフォルト値: 3600 秒

**-auth:** 許可アルゴリズム。 値: sha1 または sha256

### cf vpn-update gateway
{: #cf-vpn-update-gateway}

既存の VPN ゲートウェイを更新します。
```
cf vpn-update gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### パラメーター
{: #p8}

**gateway name:** ゲートウェイの名前。

#####オプションのパラメーター:
{: #op8}

**-t:** サービスを有効にするコンテナー。 値: allSingleContainers、allContainerGroups、allContainers。 デフォルト値: デフォルト値はありません。タイプを指定する必要があります。

**-gateway_ip:**
ゲートウェイの IP アドレス。

**-subnets:**
CIDR 形式のサブネット・アドレス。

