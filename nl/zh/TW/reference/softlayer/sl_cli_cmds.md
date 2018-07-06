---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 一般 CLI (ibmcloud sl) 指令
{: #softlayer_cli}

{{site.data.keyword.BluSoftlayer}} 外掛程式已合併至 {{site.data.keyword.Bluemix_notm}} CLI。您不再需要安裝外掛程式。
{: tip}

在 {{site.data.keyword.Bluemix_notm}} 指令行介面 (CLI) 中使用 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構指令，以配置及管理 SoftLayer 服務。

到 2018 年五月為止，{{site.data.keyword.Bluemix_notm}} CLI 指令已從 `bluemix` 和 `bx` 變更為 `ibmcloud`。不過，您仍然可以使用 `bluemix` 和 `bx` CLI 指令，直到未來移除它們為止。
{: tip}

若要開始使用，請安裝 {{site.data.keyword.Bluemix_notm}} CLI。如需詳細資料，請參閱 [IBM Cloud CLI ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}。

如需完整 {{site.data.keyword.Bluemix_notm}} CLI 指令清單，請參閱：[{{site.data.keyword.Bluemix_notm}} (ibmcloud) 指令](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli)。

支援下列指令。使用 `ibmcloud sl` 指令，以查看可用的指令清單：

<table summary="按字母順序排序的一般指令，其鏈結提供指令的相關資訊">
<caption>表 1. 一般 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構指令</caption>
 <thead>
 <th colspan="6">一般 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構指令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_help)</td>
   </tbody>
 </table>
 
 若要檢視指令的說明資訊，請執行：`ibmcloud sl [command] -h`
 
 ## ibmcloud sl init
{: #sl_init}

起始設定用來連接至 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構環境的配置設定。配置包括使用者名稱、API 金鑰或密碼、帳戶及端點。
```
ibmcloud sl init [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-a, --api-endpoint</dt>
<dd>{{site.data.keyword.BluSoftlayer_notm}} 基礎架構 API 端點 URL，預設值為：https://api.softlayer.com/rest/v3.1（適用於 API 金鑰鑑別）、https://api.softlayer.com/mobile/v3.1（適用於 IBM ID 鑑別）。</dd>
<dt>-u, --sl-user</dt>
<dd>Gen1 基礎架構使用者名稱。</dd>
<dt>-p, --sl-password</dt>
<dd>密碼或 API 金鑰。</dd>
<dt>-c, --account-id</dt>
<dd>帳戶 ID。</dd>
<dt>-q, --security-question-id</dt>
<dd>用來鑑別的安全問題 ID，如果您不知道，請詢問帳戶擁有者。</dd>
<dt>-w, --security-question-answer</dt>
<dd>用來鑑別的安全問題回答，如果您不知道，請詢問帳戶擁有者。</dd>
<dt>-s, --security-code</dt>
<dd>啟用雙因子鑑別時，安全供應商所產生的安全程式碼。</dd>
<dt>-v, --security-vendor</dt>
<dd>提供安全程式碼以進行鑑別的安全供應商，選項包含：VERISIGN、TOTP、PHONE_FACTOR。</dd>
<dt>-t, --auth-token</dt>
<dd>啟用電話鑑別時的鑑別記號。</dd>
</dl>

例如，使用 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構使用者名稱及密碼/API 金鑰登入
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
例如，使用 {{site.data.keyword.Bluemix_notm}} Single-Sign-On 登入 Softlayer
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

檢視運作 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構環境的所有指令說明資訊。
```
ibmcloud sl help

```
