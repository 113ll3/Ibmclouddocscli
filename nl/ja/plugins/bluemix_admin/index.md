---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-21"

keywords: cli, ibmcloud admin cli, admin cli plugin, admin plugin, cloud foundry admin cli plugin, adding users, buildpack, security groups, cf ba

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:note: .note}
{:important: .important}
{:tip: .tip}

# {{site.data.keyword.cloud_notm}} 管理 CLI
{: #bluemixadmincli}

Cloud Foundry コマンド・ライン・インターフェース (CLI) を {{site.data.keyword.cloud_notm}} 管理 CLI プラグインと共に使用することにより、{{site.data.keyword.cloud_notm}} Local 環境または {{site.data.keyword.cloud_notm}} Dedicated 環境を管理できます。例えば、LDAP レジストリーからユーザーを追加できます。

始めに、Cloud Foundry CLI をインストールします。 {{site.data.keyword.cloud_notm}} 管理 CLI プラグインを使用する場合、`CF` バージョン 6.11.2 以降が必要です。 [Cloud Foundry コマンド・ライン・インターフェースのダウンロード ](https://github.com/cloudfoundry/cli/releases){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") を行ってください。

Cloud Foundry CLI は、Cygwin ではサポートされていません。Cloud Foundry CLI は、Cygwin コマンド・ライン・ウィンドウ以外のコマンド・ライン・ウィンドウで使用してください。

{{site.data.keyword.cloud_notm}} 管理 CLI は、{{site.data.keyword.cloud_notm}} Local および {{site.data.keyword.cloud_notm}} Dedicated 環境でのみ使用されます。 {{site.data.keyword.cloud_notm}} Public ではサポートされません。
{: note}

## {{site.data.keyword.cloud_notm}} 管理 CLI プラグインの追加
{: #add-admin-cli}

Cloud Foundry CLI のインストール後に、{{site.data.keyword.cloud_notm}} 管理 CLI プラグインを追加できます。

既に {{site.data.keyword.cloud_notm}} 管理プラグインがインストールされていると、プラグインをアンインストールし、リポジトリーを削除してから、再びインストールして最新の更新を取得することが必要になる場合があります。
{: tip}

以下のステップを実行して、リポジトリーを追加し、プラグインをインストールします。

1. {{site.data.keyword.cloud_notm}} 管理プラグイン・リポジトリーを追加するには、以下のコマンドを実行します。
  ```
  cf add-plugin-repo IBMCloudAdmin https://<customer_console_endpoint>.bluemix.net/cli
  ```
  {: codeblock}

  管理コンソール CLI ページ (`https://<customer_console_endpoint>.bluemix.net/cli`) 内の実際のエンドポイントを使用して、同じコマンドを見つけることができます。
  {: note}

2. {{site.data.keyword.cloud_notm}} 管理 CLI プラグインをインストールするには、以下のコマンドを実行します。
  ```
  cf install-plugin IBMCloudAdminCLI -r IBMCloudAdmin
```
  {: codeblock}

## {{site.data.keyword.cloud_notm}} 管理 CLI プラグインのアンインストール
{: #remove-admin-cli}

プラグインをアンインストールするには、以下の手順を実行します。 

1. プラグインをアンインストールするには、次のようにします。
  ```
  cf uninstall-plugin IBMCloudAdminCLI
  ```
  {: codeblock}

2. プラグイン・リポジトリーを削除するには、次のようにします。
  ```
  cf remove-plugin-repo IBMCloudAdmin
  ```
  {: codeblock}

その後、更新されたリポジトリーを追加して、最新のプラグインをインストールできます。

## {{site.data.keyword.cloud_notm}} 管理 CLI プラグインの使用
{: #using-admin-cli}

{{site.data.keyword.cloud_notm}} 管理 CLI プラグインを使用すると、ユーザーの追加と削除、組織へのユーザーの割り当てと割り当て解除、といった管理タスクを実行できます。

コマンドのリストを表示するには、次のコマンドを実行します。
```
cf plugins
```
{: codeblock}

追加でコマンドのヘルプを表示するには、`-help` オプションを使用します。

### {{site.data.keyword.cloud_notm}} への接続とログイン
{: #connecting-ibm-cloud}

1. {{site.data.keyword.cloud_notm}} API エンドポイントに接続するには、次のコマンドを実行します。
  ```
  cf api api.us-south.cf.cloud.ibm.com
  ```
  {: codeblock}
  
  従来の `api.*.bluemix.net` Cloud Foundry API エンドポイントも引き続き使用できますが、スクリプトとインフラストラクチャーの自動化を更新して、地域に応じた以下の更新済みの Cloud Foundry API エンドポイントを使用できます。

  * api.us-south.cf.cloud.ibm.com (以前の api.ng.bluemix.net)
  * api.eu-gb.cf.cloud.ibm.com (以前の api.eu-gb.bluemix.net)
  * api.us-east.cf.cloud.ibm.com (以前の api.us-east.bluemix.net)
  * api.eu-de.cf.cloud.ibm.com (以前の api.eu-de.bluemix.net)
  * api.au-syd.cf.cloud.ibm.com (以前の api.au-syd.bluemix.net)

  正しい URL は、管理コンソールの「リソースおよび情報 (Resources and Information)」ページで確認できます。 URL は**「API URL」**フィールドの「API 情報」セクションに表示されます。

2. 次のコマンドを実行して、{{site.data.keyword.cloud_notm}} にログインします。
  ```
  cf login
  ```
  {: codeblock}

## ユーザーの管理
{: #admin_users}

### ユーザーの追加
{: #admin_add_user}

ご使用環境のユーザー・レジストリーから {{site.data.keyword.cloud_notm}} 環境にユーザーを追加するには、以下のコマンドを使用します。
```
cf ba add-user <user_name> <organization> <first_name> <last_name>
```
{: codeblock}

ユーザーを特定の組織に追加するには、users.write (または Superuser) 権限を持った管理者でなければなりません。組織管理者の場合、**`enable-managers-add-users`** コマンドを実行する Superuser から、組織にユーザーを追加する権限を付与してもらうこともできます。 詳しくは、[管理者へのユーザー追加権限の付与](#clius_emau)を参照してください。

| オプション | 説明 | 
| -------| ------------|
| _userName_ | LDAP レジストリー内のユーザーの名前。 |
| _organization_ | ユーザーの追加先となる {{site.data.keyword.cloud_notm}} 組織の名前または GUID。 |
| _firstName_ | 組織に追加するユーザーの名。 | 
| _lastName_ | 組織に追加するユーザーの姓。 | 
{: caption="表 1. cf ba add-user コマンド・オプション" caption-side="top"}

**`ba add-user`** という長いコマンド名の別名として **`ba au`** を使用することもできます。
{: tip}

### {{site.data.keyword.Bluemix_dedicated_notm}} からのユーザーの招待
{: #admin_dedicated_invite_public}

それぞれの {{site.data.keyword.Bluemix_dedicated_notm}} 環境には、{{site.data.keyword.cloud_notm}} にパブリックの、クライアント所有の、企業アカウントがあります。 Dedicated 環境のユーザーが {{site.data.keyword.containershort}} を使用してクラスターを作成するためには、管理者はユーザーをこのパブリック企業アカウントに追加する必要があります。 ユーザーがパブリック企業アカウントに追加されると、ユーザーの Dedicated アカウントとパブリック・アカウントがリンクされます。 そしてユーザーは IBMid を使用して Dedicated とパブリックの両方に同時にログインでき、Dedicated のインターフェースからパブリック・アカウントにリソースを作成できます。 詳しくは、『[Dedicated での IBM Cloud Container Service のセットアップ](/docs/containers?topic=containers-dedicated#dedicated_setup)』を参照してください。 Dedicated のユーザーをパブリック・アカウントに招待するには以下のようにします。
```
cf ba invite-users-to-public -userid=<user_email> -organization=<dedicated_org_id> -apikey=<public_api_key> -public_org_id=<public_org_id>
```
{: pre}

Dedicated 環境のユーザーを {{site.data.keyword.cloud_notm}} パブリック・アカウントに追加するには、Dedicated アカウントの管理者であることが必要です。

| オプション | 説明 | 
| -------| ------------|
| -userid | 単一のユーザーを招待する場合、ユーザーの E メール。 |
| -organization | Dedicated アカウント組織に現在いるすべてのユーザーを招待する場合、Dedicated アカウント組織 ID。 |
| -apikey | ユーザーをパブリック・アカウントに招待するための API キー。 これはパブリック・アカウントの管理者が生成する必要があります。 | 
| -public_org_id | ユーザーを招待するパブリック・アカウント組織の ID。 | 
{: caption="表 2. cf ba invite-users-to-public コマンド・オプション" caption-side="top"}

### {{site.data.keyword.Bluemix_dedicated_notm}} から招待したユーザーのリスト表示
{: #admin_dedicated_list}

Dedicated 環境のユーザーを {{site.data.keyword.Bluemix_notm}} アカウントに [**`invite-users-to-public`** コマンド](#admin_dedicated_invite_public)を使用して招待した場合、招待の状況を確認するためにアカウントのユーザーをリスト表示することができます。 既存の IBMid を持つ招待されたユーザーは、ACTIVE の状況になります。 既存の IBMid を持たない招待されたユーザーは、アカウントへの招待を受け入れたかどうかによって、PENDING または ACTIVE のいずれかの状況になります。 {{site.data.keyword.Bluemix_notm}} アカウントのユーザーをリストするには、以下のようにします。

```
cf ba invite-users-status -apikey=<public_api_key>
```
{: pre}

Dedicated 環境のユーザーを {{site.data.keyword.Bluemix_notm}} パブリック・アカウントに追加するには、Dedicated アカウントの管理者であることが必要です。

<dl class="parml">
<dt class="pt dlterm">&lt;public_api_key&gt;</dt>
<dd class="pd">ユーザーをアカウントに招待するのに使用された API キー。 これはパブリック・アカウントの管理者が生成する必要があります。</dd>
</dl>

<!-- staging-only commands start. Live for interconnect -->

### ユーザーの検索
{: #admin_search_user}

ユーザーを検索するには、オプションの検索フィルター・パラメーター (name、permission、organization、および role) を指定して、以下のコマンドを使用します。

```
cf ba search-users -name=<user_name_value> -permission=<permission_value> -organization=<organization_value> -role=<role_value>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| -name | ユーザーの名前。 |
| -permission | ユーザーに割り当てられた許可。 使用可能な許可は、admin (または superuser)、login (または basic)、catalog.read、catalog.write、reports.read 、reports.write、users.read、または users.write です。同じ照会内でこのパラメーターを organization パラメーターと一緒に使用することはできません。 |
| -organization | ユーザーが所属する組織の名前。 同じ照会内でこのパラメーターを permission パラメーターと一緒に使用することはできません。 | 
| -role | ユーザーに割り当てられた組織の役割。 有効な役割は、auditors、managers、billing_managers です。このパラメーターと一緒に組織を指定する必要があります。 | 
{: caption="表 3. cf ba search-users コマンド・オプション" caption-side="top"}

**`ba search-users`** という長いコマンド名の別名として **`ba su`** を使用することもできます。
{: tip}

### ユーザーの許可の設定
{: #admin_setperm_user}

指定されたユーザーの許可を設定するには、以下のコマンドを使用します。
```
cf ba set-permissions <user_name> <permission> <access>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _userName_ | ユーザーの名前。 |
| _permission_ | ユーザーに割り当てる権限を設定します。使用可能な許可は、admin (または superuser)、login (または basic)、catalog.read、catalog.write、reports.read 、reports.write、users.read、または users.write です。同じ照会内でこのパラメーターを organization パラメーターと一緒に使用することはできません。 |
| _access_ | catalog、reports、user の権限の場合は、アクセス・レベルも `read` または `write` に設定する必要があります。|  
{: caption="表 4. cf ba set-permissions コマンド・オプション" caption-side="top"}

一度に 1 つの許可を設定できます。

**`ba set-permissions`** という長いコマンド名の別名として **`ba sp`** を使用することもできます。
{: tip}

<!-- staging-only commands end -->

### ユーザーの削除
{: #admin_remov_user}

{{site.data.keyword.Bluemix_notm}} 環境からユーザーを削除するには、以下のコマンドを使用します。

```
cf ba remove-user <user_name>
```
{: codeblock}

<dl class="parml">

<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">{{site.data.keyword.Bluemix_notm}} 内のユーザーの名前。</dd>

</dl>

**`ba remove-user`** という長いコマンド名の別名として **`ba ru`** を使用することもできます。
{: tip}

### 管理者へのユーザー追加権限の付与
{: #clius_emau}

{{site.data.keyword.Bluemix_notm}} 環境で Superuser 許可がある場合、組織管理者が、自分が管理している組織にユーザーを追加できるようにすることが可能です。 管理者がユーザーを追加できるようにするには、以下のコマンドを使用します。

```
cf ba enable-managers-add-users
```
{: codeblock}

**`ba enable-managers-add-users`** という長いコマンド名の別名として **`ba emau`** を使用することもできます。
{: tip}

### 管理者のユーザー追加権限の無効化
{: #clius_dmau}

**`enable-managers-add-users`** コマンドによって、組織管理者が {{site.data.keyword.Bluemix_notm}} 環境で管理している組織にユーザーを追加できるようになっている場合、Superuser 権限があれば、この設定を削除できます。管理者によるユーザーの追加を不可にするには、以下のコマンドを使用します。

```
cf ba disable-managers-add-users
```
{: codeblock}

**`ba disable-managers-add-users`** という長いコマンド名の別名として **`ba dmau`** コマンドを使用することもできます。
{: tip}

## 組織の管理
{: #admin_orgs}

### 組織の追加
{: #admin_add_org}

組織を追加するには、以下のコマンドを使用します。

```
cf ba create-org <organization> <manager>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _organization_ | 追加する {{site.data.keyword.Bluemix_notm}} 組織の名前または GUID。|
| _manager_ | 組織のマネージャーのユーザー名。 |
{: caption="表 5. cf ba create-org コマンド・オプション" caption-side="top"}

**`ba create-org`** という長いコマンド名の別名として **`ba co`** を使用することもできます。
{: tip}

### 組織の削除
{: #admin_delete_org}

組織を削除するには、以下のコマンドを使用します。

```
cf ba delete-org <organization>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">削除する {{site.data.keyword.cloud_notm}} 組織の名前または GUID。</dd>
</dl>

**`ba delete-org`** という長いコマンド名の別名として **`ba do`** を使用することもできます。
{: tip}

### 組織へのユーザーの割り当て
{: #admin_ass_user_org}

{{site.data.keyword.cloud_notm}} 環境内のユーザーを特定の組織に割り当てるには、以下のコマンドを使用します。

```
cf ba set-org <user_name> <organization> [<role>]
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _userName_ | ユーザーの名前。 |
| _organization_ | ユーザーの割り当て先の {{site.data.keyword.cloud_notm}} 組織の名前または GUID。|
| _role_ | ユーザーの役割。有効な値は、`OrgManager`、`BillingManager`、`OrgAuditor` です。役割の説明については、[役割](/docs/iam?topic=iam-userroles#userroles)も参照してください。|  
{: caption="表 6. cf ba set-org コマンド・オプション" caption-side="top"}

**`ba set-org`** という長いコマンド名の別名として **`ba so`** を使用することもできます。
{: tip}

### 組織からのユーザーの割り当て解除
{: #admin_unass_user_org}

{{site.data.keyword.cloud_notm}} 環境内のユーザーを特定の組織から割り当て解除するには、以下のコマンドを使用します。

```
cf ba unset-org <user_name> <organization> [<role>]
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _userName_ | ユーザーの名前。 |
| _organization_ | {{site.data.keyword.cloud_notm}} 組織の名前または GUID。 |
| _role_ | ユーザーの役割。有効な値は、`OrgManager`、`BillingManager`、`OrgAuditor` です。役割の説明については、[役割](/docs/iam?topic=iam-userroles#userroles)も参照してください。|  
{: caption="表 7. cf ba unset-org コマンド・オプション" caption-side="top"}

**`ba unset-org`** という長いコマンド名の別名として **`ba uo`** を使用することもできます。
{: tip}

### 組織の割り当て量の設定
{: #admin_set_org_quota}

特定組織の使用量の割り当て量を設定するには、以下のコマンドを使用します。

```
cf ba set-quota <organization> <plan>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _organization_ | 割り当て量を設定する {{site.data.keyword.cloud_notm}} 組織の名前または GUID。 |
| _plan_ | 組織の割り当て量プラン。 |  
{: caption="表 8. cf ba set-quota コマンド・オプション" caption-side="top"}

**`ba set-quota`** という長いコマンド名の別名として **`ba sq`** を使用することもできます。
{: tip}


### 組織のコンテナー割り当て量の判別
{: #admin_find_containquotas}

組織のコンテナーの割り当て量を判別するには、以下のコマンドを使用します。

```
cf ibmcloud-admin containers-quota <organization>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">IBM Cloud 内の組織の名前または ID。 このパラメーターは必須です。</dd>
</dl>

**`ibmcloud-admin containers-quota`** という長いコマンド名の別名として **`ba cq`** を使用することもできます。
{: tip}

### 組織のコンテナー割り当て量の設定
{: #admin_set_containquotas}

組織のコンテナーの割り当て量を設定するには、少なくとも 1 つのオプションを含めて以下のコマンドを使用します。

```
cf ibmcloud-admin set-containers-quota <organization> <options>
```
{: codeblock}

複数のオプションを含められますが、少なくとも 1 つは含める必要があります。
{: note}

| オプション | 説明 | 
| -------| ------------|
| _organization_ | 割り当て量を設定する {{site.data.keyword.cloud_notm}} 組織の名前または ID。|
| _options_ | 選択肢は、**`floating-ips-max value`** (短縮名 **`fim`**)、**`floating-ips-space-default value`** (短縮名 **`fisd`**)、**`memory-max value`** (短縮名 **`mm`**)、**`memory-space-default value`** (短縮名 **`msd`**)、**`image-limit value`** (短縮名 **`il`**) です。値は整数でなければなりません。|  
{: caption="表 9. cf ibmcloud-admin set-containers-quota コマンド・オプション" caption-side="top"}

オプションで、有効な JSON オブジェクトに固有の構成パラメーターを含むファイルを指定できます。 **`-file`** オプションを使用すると、それが優先され、他のオプションは無視されます。 オプションを設定する代わりにファイルを指定する場合は、以下のコマンドを使用します。

```
cf ibmcloud-admin set-containers-quota <organization> <-file path_to_JSON_file>
```
{: codeblock}

JSON ファイルには、以下の例に示したフォーマットが含まれる必要があります。

```
{
  "floating_ips_max": 10,
  "floating_ips_space_default": 0,
  "ram_max": 4096,
  "ram_space_default": 0,
  "image_limit": 10
}
```
{: codeblock}

**`ibmcloud-admin set-containers-quota`** という長いコマンド名の別名として **`ba scq`** を使用することもできます。
{: tip}

## スペースの管理
{: #admin_spaces}

### 組織へのスペースの追加

組織でスペースを追加するには、以下のコマンドを使用します。

```
cf ibmcloud-admin create-space <organization> <space_name>
```

{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _organization_ | スペースの追加先の組織の名前または GUID。|
| _spaceName_ | 組織に追加するスペースの名前。|  
{: caption="表 10. cf ibmcloud-admin create-space コマンド・オプション" caption-side="top"}

**`ba create-space`** という長いコマンド名の別名として **`ba cs`** を使用することもできます。
{: tip}

### 組織からスペースを削除

組織からスペースを削除するには、以下のコマンドを使用します。

```
cf ibmcloud-admin delete-space <organization> <space_name>
```

{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _organization_ | スペースを削除する組織の名前または GUID。|
| _spaceName_ | 組織から削除するスペースの名前。|  
{: caption="表 11. cf ibmcloud-admin delete-space コマンド・オプション" caption-side="top"}

**`ba delete-space`** という長いコマンド名の別名として **`ba cs`** を使用することもできます。
{: tip}

### 指定した役割のユーザーをスペースに追加

指定した役割を持つユーザーをスペースに作成するには、以下のコマンドを使用します。

```
cf ibmcloud-admin set-space <organization> <space_name> <user_name> <role>
```

{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _organization_ | ユーザーの追加先の組織の名前または GUID。|
| _spaceName_ | ユーザーの追加先のスペースの名前。|
| _userName_ | ユーザーの名前。 |
| _role_ | ユーザーの役割。有効な値は、`Manager`、`Developer`、`Auditor`です。|  
{: caption="表 12. cf ibmcloud-admin set-space コマンド・オプション" caption-side="top"}

**`ba set-space`** という長いコマンド名の別名として **`ba ss`** を使用することもできます。
{: tip}


### スペース内のユーザーの役割の削除

スペース内のユーザーの役割を削除するには、以下のコマンドを使用します。

```
cf ibmcloud-admin unset-space <organization> <space_name> <user_name> <role>
```

{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _organization_ | ユーザーが所属する組織の名前または GUID。|
| _spaceName_ | ユーザーが所属するスペースの名前。|
| _userName_ | ユーザーの名前。 |
| _role_ | ユーザーの役割。有効な値は、`Manager`、`Developer`、`Auditor`です。|  
{: caption="表 13. cf ibmcloud-admin unset-space コマンド・オプション" caption-side="top"}

**`ba unset-space`** という長いコマンド名の別名として **`ba us`** を使用することもできます。
{: tip}

## カタログの管理
{: #admin_catalog}

### すべての組織のサービスの有効化
{: #admin_ena_service_org}

すべての組織に対して {{site.data.keyword.cloud_notm}} カタログでのサービスの表示を有効化するには、以下のコマンドを使用します。

```
cf ba enable-service-plan <plan_identifier>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">有効化するサービス・プランの名前または GUID。 非固有のサービス・プラン名 (例えば、「標準」または「Basic」) を入力すると、サービス・プランを選択するように求めるプロンプトが出されます。 サービス・プラン名を識別するには、ホーム・ページのサービス・カテゴリーを選択してから、**「追加」**を選択してそのカテゴリーのサービスを表示します。 サービス名をクリックして詳細ビューを開くと、そのサービスで使用可能なサービス・プランの名前を表示できます。 </dd>
</dl>

**`ba enable-service-plan`** という長いコマンド名の別名として **`ba esp`** を使用することもできます。
{: tip}

### すべての組織のサービスの無効化
{: #admin_dis_service_org}

すべての組織に対して {{site.data.keyword.Bluemix_notm}} カタログでのサービスの表示を無効化するには、以下のコマンドを使用します。

```
cf ba disable-service-plan <plan_identifier>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">有効化するサービス・プランの名前または GUID。 非固有のサービス・プラン名 (例えば、「標準」または「Basic」) を入力すると、サービス・プランを選択するように求めるプロンプトが出されます。 サービス・プラン名を識別するには、ホーム・ページのサービス・カテゴリーを選択してから、**「追加」**を選択してそのカテゴリーのサービスを表示します。 サービス名をクリックして詳細ビューを開くと、そのサービスで使用可能なサービス・プランの名前を表示できます。</dd>
</dl>

**`ba disable-service-plan`** という長いコマンド名の別名として **`ba dsp`** を使用することもできます。
{: tip}

### 組織に対するサービスの表示可能性の追加
{: #admin_addvis_service_org}

{{site.data.keyword.Bluemix_notm}} カタログで特定のサービスを表示できる組織のリストで、組織を追加できます。 組織がカタログで特定のサービスを表示できるようにするには、以下のコマンドを使用します。

```
cf ba add-service-plan-visibility <plan_identifier> <organization>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _planIdentifier_ | 有効化するサービス・プランの名前または GUID。 非固有のサービス・プラン名 (例えば、「標準」または「Basic」) を入力すると、サービス・プランを選択するように求めるプロンプトが出されます。 サービス・プラン名を識別するには、ホーム・ページのサービス・カテゴリーを選択してから、**「追加」**を選択してそのカテゴリーのサービスを表示します。 サービス名をクリックして詳細ビューを開くと、そのサービスで使用可能なサービス・プランの名前を表示できます。 |
| _organization_ | サービスの表示可能性リストに追加する組織の名前または GUID。|  
{: caption="表 14. cf ba add-service-plan-visibility コマンド・オプション" caption-side="top"}

**`ba add-service-plan-visibility`** という長いコマンド名の別名として **`ba aspv`** を使用することもできます。
{: tip}

### 組織に対するサービスの表示可能性の削除
{: #admin_remvis_service_org}

{{site.data.keyword.Bluemix_notm}} カタログで特定のサービスを表示できる組織のリストで、組織を削除できます。 組織に対してカタログでのサービスの表示可能性を削除するには、以下のコマンドを使用します。

```
cf ba remove-service-plan-visibility <plan_identifier> <organization>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _planIdentifier_ | 有効化するサービス・プランの名前または GUID。 非固有のサービス・プラン名 (例えば、「標準」または「Basic」) を入力すると、サービス・プランを選択するように求めるプロンプトが出されます。 サービス・プラン名を識別するには、ホーム・ページのサービス・カテゴリーを選択してから、**「追加」**を選択してそのカテゴリーのサービスを表示します。 サービス名をクリックして詳細ビューを開くと、そのサービスで使用可能なサービス・プランの名前を表示できます。 |
| _organization_ | サービスの表示可能性リストから削除する組織の名前または GUID。|  
{: caption="表 15. cf ba remove-service-plan-visibility コマンド・オプション" caption-side="top"}

**`ba remove-service-plan-visibility`** という長いコマンド名の別名として **`ba rspv`** を使用することもできます。
{: tip}

### 組織に対するサービスの表示可能性の編集
{: #admin_editvis_service_org}

特定の組織が {{site.data.keyword.Bluemix_notm}} カタログで表示できるサービスのリストを編集および置換することができます。 単一または複数の組織に対して既存のすべての表示されるサービスを置換するには、以下のコマンドを使用します。

```
cf ba edit-service-plan-visibilities <plan_identifier> <organization_1> <optional_organization_2>
```
{: codeblock}

このコマンドにより、指定した組織で表示される既存のサービスが、コマンドで指定したサービスに置換されます。

| オプション | 説明 | 
| -------| ------------|
| _planIdentifier_ | 有効化するサービス・プランの名前または GUID。 非固有のサービス・プラン名 (例えば、「標準」または「Basic」) を入力すると、サービス・プランを選択するように求めるプロンプトが出されます。 サービス・プラン名を識別するには、ホーム・ページのサービス・カテゴリーを選択してから、**「追加」**を選択してそのカテゴリーのサービスを表示します。 サービス名をクリックして詳細ビューを開くと、そのサービスで使用可能なサービス・プランの名前を表示できます。 |
| _organization_ | 表示可能性を追加する組織の名前または GUID。 コマンドに追加の組織名または GUID を入力することで、複数の組織に対してサービスの表示可能性を有効化できます。 |  
{: caption="表 16. cf ba edit-service-plan-visibilities コマンド・オプション" caption-side="top"}

**`ba edit-service-plan-visibility`** という長いコマンド名の別名として **`ba espv`** を使用することもできます。
{: tip}

## レポートの管理
{: #admin_add_report}

### レポートの追加
{: #admin_adding_report}

セキュリティー・レポートを追加するには、以下のコマンドを使用します。

```
cf ba add-report <category> <date> <PDF|TXT|LOG> <RTF>
```
{: codeblock}

レポートの書き込みアクセス許可がある場合は、新規カテゴリーを作成し、ユーザー用に受け入れられるフォーマットのいずれかでレポートを追加できます。 **`category`** パラメーターに新規カテゴリー名を入力するか、既存のカテゴリーに新規レポートを追加します。

| オプション | 説明 | 
| -------| ------------|
| _category_ | レポートのカテゴリー。 名前にスペースが含まれている場合は、引用符を使用してください。|
| _date_ | YYYYMMDD という形式のレポート日付。|  
| _filePath_ | アップロードするレポート PDF、テキスト・ファイル、またはログ・ファイルのパス。 |
| _RTF_ | PDF の RTF (リッチ・テキスト・フォーマット) バージョンを含めるためのオプション。 このオプションが適用されるのは、レポート PDF のパスを含めた場合に限られます。RTF バージョンは、索引付けおよび検索に使用されます。 |
{: caption="表 17. cf ba add-report コマンド・オプション" caption-side="top"}

**`ba add-report`** という長いコマンド名の別名として **`ba ar`** を使用することもできます。
{: tip}

### レポートの削除
{: #admin_del_report}

セキュリティー・レポートを削除するには、以下のコマンドを使用します。

```
cf ba delete-report <category> <date> <name>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _category_ | レポートのカテゴリー。 名前にスペースが含まれている場合は、引用符を使用してください。|
| _date_ | YYYYMMDD という形式のレポート日付。|  
| _name_ | レポートの名前。 |
{: caption="表 18. cf ba delete-report コマンド・オプション" caption-side="top"}

**`ba delete-report`** という長いコマンド名の別名として **`ba dr`** を使用することもできます。
{: tip}

### レポートの取得
{: #admin_retr_report}

セキュリティー・レポートを取得するには、以下のコマンドを使用します。

```
cf ba retrieve-report <search>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;search&gt;</dt>
<dd class="pd">レポートのファイル名。 名前にスペースが含まれている場合は、引用符を使用して名前を囲んでください。</dd>
</dl>

**`ba retrieve-report`** という長いコマンド名の別名として **`ba rr`** を使用することもできます。
{: tip}

## リソース・メトリック情報の表示
{: #cliresourceusage}

メモリー、ディスク、CPU 使用量など、リソース・メトリック情報を表示できます。 使用可能な物理リソースと予約済みリソース、および物理リソースと予約済みリソースの使用量の要約を確認できます。 Droplet Execution Agent (DEA) およびセル (Diego アーキテクチャー) の使用データも確認できます。 リソース・メトリック情報を表示するには、以下のコマンドを使用します。

```
cf ba resource-metrics
```

**`ba resource-metrics`** という長いコマンド名の別名として **`ba rsm`** を使用することもできます。
{: tip}

## リソース・メトリック履歴の表示
{: #cliresourceusagehistory}

メモリーおよびディスクの使用量に関するリソース・メトリック履歴を取得できます。 返されるメトリックは、物理リソースと予約済みリソースの両方について、使用可能な合計量のうちの使用済みリソースの量を示します。 メモリーおよびディスクの使用量の履歴データは、毎時、日次、または月次で表示できます。 特定の日付範囲内のデータを取得するには、開始日と終了日を指定します。 日付が指定されていない場合、デフォルトの履歴データは、過去 48 時間の毎時のメモリー・データです。 データは、最新の日付を先頭にして、降順に表示されます。 リソース・メトリック履歴情報を表示するには、以下のコマンドを使用します。

```
cf ba resource-metrics-history <hourly|daily|monthly>  <memory|disk >  <start|end>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| --hourly | View the historical data for the last 48 hours. This is the default value. |
| --daily | View the historical data daily average for the last 30 days. |  
| --monthly | View the historical data monthly average for the last 6 months. |
| --memory | View the used and total reserved and physical memory. |
| --disk | View the used and total reserved and physical disk. | 
| --start | Specify a start date for daily or monthly in the format of mm-dd-yyyy, or start date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone. |
| --end | Specify an end date for daily or monthly in the format of mm-dd-yyyy, or end date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone. |
{: caption="表 19. cf ba resource-metrics-history コマンド・オプション" caption-side="top"}

**例**

```
cf ibmcloud-admin resource-metrics-history
cf ibmcloud-admin resource-metrics-history --daily --disk --start=07-04-2017
cf ibmcloud-admin resource-metrics-history --monthly --memory
cf ibmcloud-admin resource-metrics-history --hourly --start="06-01-2017 00:00:00 EDT" --end="06-30-2017 23:59:00 EDT
```
{: codeblock}

以下のコマンドを使用して、前述のコマンド・パラメーターおよび例のリストを表示できます。

```
cf ba resource-metrics-history -help
```

**`ba resource-metrics-history`** という長いコマンド名の別名として **`ba rsmh`** を使用することもできます。
{: tip}

## サービス・ブローカーの管理
{: #admin_servbro}

### サービス・ブローカーのリスト
{: #clilistservbro}

サービス・ブローカーをリストするには、以下のコマンドを使用します。

```
cf ba service-brokers <broker_name>
```
{: codeblock}

すべてのサービス・ブローカーをリストするには、**`broker_name`** パラメーターを指定せずにコマンドを入力します。

<dl class="parml">
<dt class="pt dlterm">&lt;broker_name&gt;</dt>
<dd class="pd">カスタム・サービス・ブローカーの名前。 特定のサービス・ブローカーの情報を入手したい場合は、このパラメーターを使用します。 オプション。</dd>
</dl>

**`ba service-brokers`** という長いコマンド名の別名として **`ba sb`** を使用することもできます。
{: tip}

### サービス・ブローカーの追加
{: #cliaddservbro}

サービス・ブローカーを追加して、{{site.data.keyword.Bluemix_notm}} カタログにカスタム・サービスを追加できるようにするには、以下のコマンドを使用します。

```
cf ba add-service-broker <broker_name> <user_name> <password> <broker_url>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _brokerName_ | カスタム・サービス・ブローカーの名前。 |
| _userName_ | サービス・ブローカーに対するアクセス権限を持つアカウントのユーザー名。 |  
| _password_ | サービス・ブローカーに対するアクセス権限を持つアカウントのパスワード。 |
| _brokerURL_ | サービス・ブローカーの URL。 |
{: caption="表 20. cf ba add-service-broker コマンド・オプション" caption-side="top"}

**`ba add-service-broker`** という長いコマンド名の別名として **`ba asb`** を使用することもできます。
{: tip}

### サービス・ブローカーの削除
{: #clidelservbro}

{{site.data.keyword.Bluemix_notm}} カタログからカスタム・サービスを削除するサービス・ブローカーを削除するには、以下のコマンドを使用します。

```
cf ba delete-service-broker <service_broker>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;service_broker&gt;</dt>
<dd class="pd">カスタム・サービス・ブローカーの名前または GUID。</dd>
</dl>

**`ba delete-service-broker`** という長いコマンド名の別名として **`ba dsb`** を使用することもできます。
{: tip}

### サービス・ブローカーの更新
{: #cliupdservbro}

サービス・ブローカーを更新するには、以下のコマンドを使用します。

```
cf ba update-service-broker <broker_name> <user_name> <password> <broker_url>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _brokerName_ | カスタム・サービス・ブローカーの名前。 |
| _userName_ | サービス・ブローカーに対するアクセス権限を持つアカウントのユーザー名。 |  
| _password_ | サービス・ブローカーに対するアクセス権限を持つアカウントのパスワード。 |
| _brokerURL_ | サービス・ブローカーの URL。 |
{: caption="表 21. cf ba update-service-broker コマンド・オプション" caption-side="top"}

**`ba update-service-broker`** という長いコマンド名の別名として **`ba usb`** を使用することもできます。
{: tip}

## アプリケーション・セキュリティー・グループの管理
{: #admin_secgro}

アプリケーション・セキュリティー・グループ (ASG) に関して作業するには、ローカル環境または専用環境の全アクセス権限を持つ管理者でなければなりません。 コマンドでターゲットとする組織に有効な ASG のリスト表示は、環境のすべてのユーザーが行えます。 それに対し、ASG の作成、更新、バインドを行うには、{{site.data.keyword.Bluemix_notm}} 環境の管理者である必要があります。

ASG は、{{site.data.keyword.cloud_notm}} 環境内のアプリからのアウトバウンド・トラフィックを制御する仮想ファイアウォールとして機能します。各 ASG は、外部ネットワークに対する特定のトラフィックおよび通信を許可するルールのリストから構成されます。 1 つ以上の ASG を特定のセキュリティー・グループ・セット (例えば、グローバル・アクセスの適用に使用されるグループ・セットなど) にバインドすることや、{{site.data.keyword.Bluemix_notm}} 環境の組織内のスペースにバインドすることができます。

{{site.data.keyword.Bluemix_notm}} は最初、制限された外部ネットワークへのすべてのアクセス権限でセットアップされます。 IBM が作成した 2 つのセキュリティー・グループ `public_networks` と `dns` をデフォルトの Cloud Foundry セキュリティー・グループ・セットにバインドした場合、これらのグループにより、外部ネットワークへのグローバル・アクセスが可能になります。 グローバル・アクセスの適用に使用される Cloud Foundry 内の 2 つのセキュリティー・グループ・セットは、**デフォルト・ステージング**と**デフォルト実行**のグループ・セットです。 これらのグループ・セットは、すべての実行アプリ、またはすべてのステージング・アプリに対するトラフィックを許可するためのルールを適用します。 これらの 2 つのセキュリティー・グループ・セットにバインドしたくない場合は、Cloud Foundry グループ・セットからアンバインドし、セキュリティー・グループを特定スペースにバインドしてください。 詳しくは、[アプリケーション・セキュリティー・グループのバインド ](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") を参照してください。

IBM が作成した 2 つのセキュリティー・グループ `public_networks` と `dns` から**デフォルト・ステージング**または**デフォルト実行**のグループ・セットをアンバインドすると、外部ネットワークへのグローバル・アクセスが無効になります。 アンバインドは、環境内で実行中およびステージング中のアプリへの影響の可能性を認識して、十分注意して使用してください。
{: important}

セキュリティー・グループに関する作業を可能にする以下のコマンドは、Cloud Foundry 1.6 バージョンをベースとしています。 必須フィールドやオプション・フィールドなどの詳細については、[アプリケーション・セキュリティー・グループの作成 ](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") に関する Cloud Foundry 資料を参照してください。

### セキュリティー・グループのリスト
{: #clilissecgro}

すべてのセキュリティー・グループをリストするには、以下のコマンドを使用します。

```
cf ba security-groups
```
{: codeblock}

特定セキュリティー・グループの詳細を表示するには、以下のコマンドを使用します。

```
cf ba security-groups <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">セキュリティー・グループの名前</dd>
</dl>

**`ba security-groups`** という長いコマンド名の別名として **`ba sg`** を使用することもできます。
{: tip}

### セキュリティー・グループの作成
{: #clicreasecgro}

セキュリティー・グループを作成するには、以下のコマンドを使用します。
```
cf ba create-security-group <security-group> <path-to-rules-file>
```
{: codeblock}

IBM が作成したセキュリティー・グループと区別するため、ユーザーが作成した各セキュリティー・グループの名前には、接頭部 `adminconsole_` が追加されます。

| オプション | 説明 | 
| -------| ------------|
| _groupName_ | セキュリティー・グループの名前。 |
| _filePath_ | ルール・ファイルの絶対パスまたは相対パス。|  
{: caption="表 22. cf ba create-security-group コマンド・オプション" caption-side="top"}

**`ba create-security-group`** という長いコマンド名の別名として **`ba csg`** を使用することもできます。
{: tip}

セキュリティー・グループの作成と、発信トラフィックを定義するルールについて詳しくは、[アプリケーション・セキュリティー・グループの作成 ](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") を参照してください。

### セキュリティー・グループの更新
{: #cliupdsecgro}

セキュリティー・グループを更新するには、以下のコマンドを使用します。

```
cf ba update-security-group <security-group> <path-to-rules-file>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _groupName_ | セキュリティー・グループの名前。 |
| _filePath_ | ルール・ファイルの絶対パスまたは相対パス。|  
{: caption="表 23. cf ba update-security-group コマンド・オプション" caption-side="top"}

**`ba update-security-group`** という長いコマンド名の別名として **`ba usg`** を使用することもできます。
{: tip}

### セキュリティー・グループの削除
{: #clidelsecgro}

セキュリティー・グループを削除するには、以下のコマンドを使用します。
```
cf ba delete-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">セキュリティー・グループの名前</dd>
</dl>

**`ba delete-security-group`** という長いコマンド名の別名として **`ba dsg`** を使用することもできます。
{: tip}

### セキュリティー・グループのバインド
{: #clibindsecgro}

デフォルト・ステージングのセキュリティー・グループ・セットにバインドするには、以下のコマンドを使用します。

```
cf ba bind-staging-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">セキュリティー・グループの名前</dd>
</dl>

**`ba bind-staging-security-group`** という長いコマンド名の別名として **`ba bssg`** を使用することもできます。
{: tip}

デフォルト実行のセキュリティー・グループ・セットにバインドするには、以下のコマンドを使用します。

```
cf ba bind-running-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">セキュリティー・グループの名前</dd>
</dl>

**`ba bind-running-security-group`** という長いコマンド名の別名として **`ba brsg`** を使用することもできます。
{: tip}

セキュリティー・グループをスペースにバインドするには、以下のコマンドを使用します。

```
cf ba bind-security-group <security-group> <org> <space>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _groupName_ | セキュリティー・グループの名前。 |
| _org_ | セキュリティー・グループをバインドする組織の名前。 |
| _space_ | セキュリティー・グループをバインドする組織内のスペースの名前。 |
{: caption="表 24. cf ba bind-security-group コマンド・オプション" caption-side="top"}

**`ba bind-security-group`** という長いコマンド名の別名として **`ba bsg`** を使用することもできます。
{: tip}

セキュリティー・グループのバインドについて詳しくは、[アプリケーション・セキュリティー・グループのバインド ](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") を参照してください。

### セキュリティー・グループのアンバインド
{: #cliunbindsecgro}

IBM が作成した 2 つのセキュリティー・グループ `public_networks` と `dns` からデフォルト・ステージングのグループ・セットをアンバインドすると、外部ネットワークへのグローバル・アクセスが無効になります。アンバインドは、環境内でステージング中のすべてのアプリに与える悪影響を理解し、十分注意して使用する必要があります。デフォルト・ステージングのセキュリティー・グループ・セットからアンバインドするには、以下のコマンドを使用します。

```
cf ba unbind-staging-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">セキュリティー・グループの名前</dd>
</dl>

**`ba unbind-staging-security-group`** という長いコマンド名の別名として **`ba ussg`** を使用することもできます。
{: tip}

IBM が作成した 2 つのセキュリティー・グループ `public_networks` と `dns` からデフォルト実行のグループ・セットをアンバインドすると、外部ネットワークへのグローバル・アクセスが無効になります。アンバインドは、環境内で実行中のすべてのアプリに与える悪影響を理解し、十分注意して使用する必要があります。デフォルト実行のセキュリティー・グループ・セットからアンバインドするには、以下のコマンドを使用します。

```
cf ba unbind-running-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">セキュリティー・グループの名前</dd>
</dl>

**`ba unbind-running-security-group`** という長いコマンド名の別名として **`ba brsg`** を使用することもできます。
{: tip}

スペースに対してセキュリティー・グループをアンバインドするには、以下のコマンドを使用します。

```
cf ba unbind-security-group <security-group> <org> <space>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _groupName_ | セキュリティー・グループの名前。 |
| _org_ | セキュリティー・グループをアンバインドする組織の名前。|
| _space_ | セキュリティー・グループをアンバインドする組織内のスペースの名前。 |
{: caption="表 25. cf ba unbind-security-group コマンド・オプション" caption-side="top"}

**`ba unbind-security-group`** という長いコマンド名の別名として **`ba usg`** を使用することもできます。
{: tip}

セキュリティー・グループのアンバインドについて詳しくは、[アプリケーション・セキュリティー・グループのアンバインド ](https://docs.cloudfoundry.org/concepts/asg.html#unbinding-groups){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") を参照してください。

## ビルドパックの管理
{: #admin_buildpack}

### ビルドパックのリスト
{: #clilistbuildpack}

アプリ・カタログ書き込み許可がある場合、ビルドパックをリストできます。 すべてのビルドパックをリストするか、または特定のビルドパックを表示するには、以下のコマンドを使用します。

```
cf ba buildpacks <buildpack_name>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">表示する特定のビルドパックを指定するオプション・パラメーター。</dd>
</dl>

**`ba buildpacks`** という長いコマンド名の別名として **`ba lb`** を使用することもできます。
{: tip}

### ビルドパックの作成およびアップロード
{: #clicreupbuildpack}

アプリ・カタログ書き込み許可がある場合、ビルドパックを作成およびアップロードできます。 `.zip` ファイル・タイプの任意の圧縮ファイルをアップロードできます。 ビルドパックをアップロードするには、以下のコマンドを使用します。

```
cf ba create-buildpack <buildpack_name> <file_path> <position>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _name_ | アップロードするビルドパックの名前。 |
| _filePath_ | ビルドパック圧縮ファイルのパス。 |
| _position_ | ビルドパックの自動検出時にビルドパックを検査する順序。 |
{: caption="表 26. cf ba create-buildpack コマンド・オプション" caption-side="top"}

**`ba create-buildpack`** という長いコマンド名の別名として **`ba cb`** を使用することもできます。
{: tip}

### ビルドパックの更新
{: #cliupdabuildpack}

アプリ・カタログ書き込み許可がある場合、既存のビルドパックを更新できます。 ビルドパックを更新するには、以下のコマンドを使用します。
```
cf ba update-buildpack <buildpack_name> <position> <enabled> <locked>
```
{: codeblock}

| オプション | 説明 | 
| -------| ------------|
| _name_ | 更新するビルドパックの名前。 |
| _position_ | ビルドパックの自動検出時にビルドパックを検査する順序。 |
| _enabled_ | ビルドパックをステージング用に使用するのかどうかを示します。 |
| _locked_ | 更新されないようにビルドパックをロックするのかどうかを示します。 | 
{: caption="表 27. cf ba update-buildpack コマンド・オプション" caption-side="top"}

**`ba update-buildpack`** という長いコマンド名の別名として **`ba ub`** を使用することもできます。
{: tip}

### ビルドパックの削除
{: #clidelbuildpack}

アプリ・カタログ書き込み許可がある場合、既存のビルドパックを削除できます。 ビルドパックを削除するには、以下のコマンドを使用します。
```
cf ba delete-buildpack <buildpack_name>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">削除するビルドパックの名前。</dd>
</dl>

**`ba delete-buildpack`** という長いコマンド名の別名として **`ba db`** を使用することもできます。
{: tip}
