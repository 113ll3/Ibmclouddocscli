---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 汎用 CLI (ibmcloud sl) コマンド
{: #softlayer_cli}

{{site.data.keyword.BluSoftlayer}} プラグインは、{{site.data.keyword.Bluemix_notm}} CLI にマージされました。 このプラグインのインストールは必要なくなりました。
{: tip}

{{site.data.keyword.Bluemix_notm}} コマンド・ライン・インターフェース (CLI) で {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンドを使用して、SoftLayer のサービスを管理および構成します。

2018 年 5 月、{{site.data.keyword.Bluemix_notm}} CLI コマンドは `bluemix` および `bx` から `ibmcloud` に変更されました。 ただし、後日削除されるまで、`bluemix` および `bx` CLI CLI コマンドを引き続き使用できます。
{: tip}

まず、{{site.data.keyword.Bluemix_notm}} CLI をインストールします。 詳しくは、『[IBM Cloud CLI ![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}』を参照してください。

{{site.data.keyword.Bluemix_notm}} CLI コマンドの完全リストについては、[{{site.data.keyword.Bluemix_notm}} (ibmcloud) コマンド](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli)を参照してください。

以下のコマンドがサポートされます。 使用可能なコマンドのリストを表示するには、`ibmcloud sl` コマンドを使用します。

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用コマンド">
<caption>表 1. 汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド</caption>
 <thead>
 <th colspan="6">汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_help)</td>
   </tbody>
 </table>
 
 コマンドのヘルプ情報を表示するには、`ibmcloud sl [command] -h` を実行します。
 
 ## ibmcloud sl init
{: #sl_init}

{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー環境への接続に使用される構成設定を初期化します。 この構成には、ユーザー名、API キーまたはパスワード、アカウント、およびエンドポイントが含まれます。
```
ibmcloud sl init [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー API エンドポイント URL。デフォルトは、API キー認証の場合は https://api.softlayer.com/rest/v3.1、IBMid 認証の場合は https://api.softlayer.com/mobile/v3.1。</dd>
<dt>-u, --sl-user</dt>
<dd>Gen1 インフラストラクチャー・ユーザー名。</dd>
<dt>-p, --sl-password</dt>
<dd>パスワードまたは API キー。</dd>
<dt>-c, --account-id</dt>
<dd>アカウント ID。</dd>
<dt>-q, --security-question-id</dt>
<dd>認証に使用されるセキュリティー質問 ID。不明な場合はアカウント所有者に確認してください。</dd>
<dt>-w, --security-question-answer</dt>
<dd>認証に使用されるセキュリティー質問の回答。不明な場合はアカウント所有者に確認してください。</dd>
<dt>-s, --security-code</dt>
<dd>二要素認証が有効になっている場合にセキュリティー・ベンダーによって生成されるセキュリティー・コード。</dd>
<dt>-v, --security-vendor</dt>
<dd>認証用のセキュリティー・コードを提供するセキュリティー・ベンダー。オプション: VERISIGN、TOTP、PHONE_FACTOR。</dd>
<dt>-t, --auth-token</dt>
<dd>電話認証が有効な場合の認証トークン。</dd>
</dl>

例えば、{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャーのユーザー名とパスワード/API キーを使用してログインします
```
$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:
1. Login with {{site.data.keyword.BluSoftlayer_notm}} infrastructure user name and password/API key
2. Use {{site.data.keyword.Bluemix_notm}} Single-Sign-On
Enter a number>1
Softlayer API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Username: []> user@example.com
API key or password: []> abcd

API endpoint:    https://api.softlayer.com/rest/v3.1   
User name:       user@example.com   
API Key:         xxxxxxxxxx
```
例えば、{{site.data.keyword.Bluemix_notm}} の Single-Sign-On を使用して Softlayer にログインします
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account example user's Account (65ce8074c6c62b5)

API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south   
User:           user@example.com   
Account:        example user's Account (65ce8074c6c62b5)   
No org or space targeted, use 'ibmcloud target --cf or ibmcloud target -o ORG -s SPACE'


$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:

1. Login with Softlayer user name and password/API key
2. Use IBM Cloud Single-Sign-On
Enter a number> 2
{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint URL: [https://api.softlayer.com/mobile/v3.1]>
Setting account to: 123456
OK

{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint:    https://api.softlayer.com/mobile/v3.1   

Account ID:                123456   
User ID:                   user@example.com  
IMS token:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー環境で作動するすべてのコマンドのヘルプ情報を表示します。
```
ibmcloud sl help
```
