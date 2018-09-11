---

copyright:

  years: 2018


lastupdated: "2018-08-28"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 一般 CLI (ibmcloud) 指令
{: #ibmcloud_cli}


{{site.data.keyword.Bluemix_notm}} 指令行介面 (CLI) 提供一組依名稱空間分組的指令，讓使用者與 {{site.data.keyword.Bluemix_notm}} 互動。

{{site.data.keyword.Bluemix_notm}} 指令行用戶端已將 Cloud Foundry 指令行用戶端搭載在其安裝中。如果您已安裝自己的 cf cli，請不要在相同環境定義中使用自己的安裝的 {{site.data.keyword.Bluemix_notm}} CLI 指令 `ibmcloud [command]` 及 Cloud Foundry CLI 指令 `cf [command]`。如果您要使用 cf cli 來管理 {{site.data.keyword.Bluemix_notm}} CLI 環境定義中的 Cloud Foundry 資源，請改為使用 `ibmcloud cf [command]`。請注意，不容許 `ibmcloud cf api/login/logout/target`，必須改為使用 `ibmcloud api/login/logout/target`。

到 2018 年五月為止，{{site.data.keyword.Bluemix_notm}} CLI 指令已從 `bluemix` 和 `bx` 變更為 `ibmcloud`。不過，您仍然可以使用 `bluemix` 和 `bx` CLI 指令，直到未來移除它們為止。
{: tip}

以下列出 {{site.data.keyword.Bluemix_notm}} CLI 所支援的詳細指令，包括其名稱、引數、選項、必要條件、說明及範例。
{:shortdesc}

**附註：***必要條件* 列出使用指令之前需要哪些動作。沒有必要動作的指令會列為**無**。否則，必要條件可能包括下列一個以上的動作：

<dl>
<dt>端點</dt>
<dd>必須透過 <code>bluemix api</code> 設定 API 端點後，才能使用這個指令。</dd>
<dt>登入</dt>
<dd>需要使用 <code>bluemix login</code> 指令進行登入後，才能使用這個指令。如果是使用聯合 ID 進行登入，請使用 '--sso' 選項以一次性密碼進行鑑別，或使用 '--apikey' 以 API 金鑰進行鑑別。移至 {{site.data.keyword.Bluemix_notm}} 主控台**管理** &gt; **安全** &gt; **平台 API 金鑰**，以建立 API 金鑰。
</dd>
<dt>目標</dt>
<dd>必須使用 <code>bluemix target</code> 指令來設定組織及空間後，才能使用這個指令。</dd>
<dt>Docker</dt>
<dd>必須先安裝 Docker CLI (docker)，才能執行這個指令。</dd>
</dl>


請使用下表中的索引來參照常用的 ibmcloud 指令。

## 一般 ibmcloud 指令
{: #ibmcloud_commands_index}

<table summary="一般 ibmcloud 指令。">
<caption>表 1. 一般 ibmcloud 指令</caption>
 <thead>
 <th colspan="5">一般 ibmcloud 指令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud help](bx_cli.html#ibmcloud_help)</td>
 <td>[ibmcloud api](bx_cli.html#ibmcloud_api)</td>
 <td>[ibmcloud config](bx_cli.html#ibmcloud_config)</td>
 <td>[ibmcloud info](bx_cli.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](bx_cli.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](bx_cli.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](bx_cli.html#ibmcloud_logout) </td>
 <td>[ibmcloud regions](bx_cli.html#ibmcloud_regions)</td>
 <td>[ibmcloud target](bx_cli.html#ibmcloud_target)</td>
 <td>[ibmcloud update](bx_cli.html#ibmcloud_update)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud help
{: #ibmcloud_help}
顯示 {{site.data.keyword.Bluemix_notm}} CLI 之第一層內建指令及所支援名稱空間的一般說明，或特定內建指令或名稱空間的說明。

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：

   <dl>
   <dt>COMMAND|NAMESPACE（選用）</dt>
   <dd>顯示其說明的指令或名稱空間。如果未指定，則會顯示 {{site.data.keyword.Bluemix_notm}} CLI 的一般說明。</dd>
   </dl>



<strong>範例</strong>：

顯示 {{site.data.keyword.Bluemix_notm}} CLI 的一般說明：

```
ibmcloud help
```

顯示 `info` 指令的說明：

```
ibmcloud help info
```

## ibmcloud api
{: #ibmcloud_api}
設定或檢視 {{site.data.keyword.Bluemix_notm}} API 端點。

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
   <dl>
   <dt>API_ENDPOINT（選用）</dt>
   <dd>設為目標的 API 端點，例如 `https://api.chinabluemix.net`。 如果未同時指定 *API_ENDPOINT* 及 `--unset` 選項，則會顯示現行 API 端點。</dd>
   <dt>--unset（選用）</dt>
   <dd>移除 API 端點設定。</dd>
   <dt>--skip-ssl-validation（選用）</dt>
   <dd>略過 HTTP 要求的 SSL 驗證。</dd>
   </dl>
<strong>範例</strong>：

將 API 端點設為 api.chinabluemix.net：

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

檢視現行 API 端點：

```
ibmcloud api
```

取消設定 API 端點：

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


將預設值寫入配置檔。

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>用於 HTTP 要求的逾時值。預設值為 60 秒。</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>追蹤對終端機或指定檔案的 HTTP 要求。</dd>
   <dt>--color true|false</dt>
   <dd>啟用或停用彩色輸出。依預設，會啟用彩色輸出。</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>設定預設語言環境。如果 LOCALE 為 <i>CLEAR</i>，則會刪除先前的語言環境。</dd>
   <dt>--check-version true|false</dt>
   <dd>啟用或停用 CLI 版本檢查。</dd>
   </dl>

一次只能指定其中一個選項。

<strong>範例</strong>：

將 HTTP 要求逾時值設為 30 秒：

```
ibmcloud config --http-timeout 30
```

啟用 HTTP 要求的追蹤輸出：

```
ibmcloud config --trace true
```

追蹤對指定檔案 */home/usera/my_trace* 的 HTTP 要求：

```
ibmcloud config --trace /home/usera/my_trace
```

停用彩色輸出：

```
ibmcloud config --color false
```

將語言環境設為 zh_Hans：

```
ibmcloud config --locale zh_Hans
```

清除語言環境設定：

```
ibmcloud config --locale CLEAR
```

## ibmcloud info
{: #ibmcloud_info}

檢視基本 {{site.data.keyword.Bluemix_notm}} 資訊，包括現行地區、雲端控制器版本以及部分有用端點（例如用於登入及交換存取記號的端點）。

```
ibmcloud info
```

<strong>必要條件</strong>：端點

## ibmcloud cf
{: #ibmcloud_cf}

呼叫內嵌的 CF CLI

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
<dl>
  <dt>-q, --quiet</dt>
  <dd>關閉「呼叫 cf 指令...」訊息</dd>
</dl>

<strong>範例</strong>：

列出 cf 應用程式：

```
ibmcloud cf apps
```

列出 cf 服務，但沒有「呼叫 cf 指令...」訊息：

```
ibmcloud -q cf services
```

## ibmcloud login
{: #ibmcloud_login}

登入使用者。

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>必要條件</strong>：無

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>指令選項</strong>：
<dl>
  <dt> -a <i>API_ENDPOINT</i>（選用）</dt>
  <dd> API 端點（例如：api.ng.bluemix.net）</dd>
  <dt> --apikey <i>API_KEY 或 @API_KEY_FILE_PATH</i>
  <dd> API 金鑰內容，或透過 @ 指出的 API 金鑰檔案的路徑</dd>
  <dt> --sso（選用）</dt>
  <dd> 使用一次性密碼進行登入</dd>
  <dt> -u <i>USERNAME</i>（選用）</dt>
  <dd> 使用者名稱</dd>
  <dt> -p <i>PASSWORD</i>（選用）</dt>
  <dd> 密碼</dd>
  <dt> -c <i>ACCOUNT_ID</i>（選用）</dt>
  <dd> 目標帳戶的 ID。此選項與 '--no-account' 不能同時使用。</dd>
  <dt> --no-account（選用）</dt>
  <dd> 強制以不使用帳戶的方式登入。不建議使用這個選項。此選項與 '-c' 不能同時使用。</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (optional)</dt>
  <dd> 目標資源群組的名稱</dd>
  <dt> -o <i>ORG</i>（選用）</dt>
  <dd> 目標組織的名稱（已淘汰，請使用 'ibmcloud target -o ORG'）</dd>
  <dt> -s <i>SPACE</i>（選用）</dt>
  <dd> 目標空間的名稱（已淘汰，請使用 'ibmcloud target -s SPACE'）</dd>
  <dt> --no-iam </dt>
  <dd> 強制向登入伺服器進行鑑別，而非公用 IAM</dd>
  <dt> --skip-ssl-validation（選用）</dt>
  <dd> 略過 HTTP 要求的 SSL 驗證。不建議使用這個選項。</dd>
</dl>

<strong>範例</strong>：

### 互動式登入

```
ibmcloud login
```

以使用者名稱及密碼登入，並設定目標帳戶、組織及空間：

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

以一次性密碼登入，並設定目標帳戶、組織及空間：

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

以 API 金鑰登入，並設定目標：

### API 金鑰具有關聯的帳戶

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### API 金鑰沒有關聯的帳戶

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>附註：</strong>如果 API 金鑰具有關聯的帳戶，則不容許切換至另一個帳戶。

### 使用一次性密碼

```
ibmcloud login -u UserID --sso
```

CLI 接著會提供 URL 鏈結，並要求密碼：
```
一次性密碼（從 https://URL_Link_To_Obtain_Passcode 取得）：
```

在瀏覽器中開啟鏈結，這會引導您取得密碼。在主控台中鍵入給定的密碼，您應該就可以登入。

## ibmcloud logout
{: #ibmcloud_logout}

登出使用者。

```
ibmcloud logout
```

<strong>必要條件</strong>：無

## ibmcloud regions
{: #ibmcloud_regions}

檢視 {{site.data.keyword.Bluemix_notm}} 上所有地區的資訊。

```
ibmcloud regions
```

<strong>必要條件</strong>：端點

## ibmcloud target
{: #ibmcloud_target}


設定或檢視目標帳戶、地區、組織或空間。

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>-r <i>REGION_NAME</i>（選用）</dt>
   <dd>要切換至的地區名稱，例如 'us-south' 或 'eu-gb'。</dd>
   <dt>-c <i>ACCOUNT_ID</i>（選用）</dt>
   <dd>要設為目標的帳戶 ID。</dd>
   <dt>-g <i>RESOURCE_GROUP</i>（選用）</dt>
   <dd>資源群組的名稱。</dd>
   <dt>--cf</dt>
   <dd>以互動方式選取目標組織及空間</dd>
   <dt>-o <i>ORG_NAME</i>（選用）</dt>
   <dd>要設為目標的組織名稱。</dd>
   <dt>-s <i>SPACE_NAME</i>（選用）</dt>
   <dd>要設為目標的空間名稱。</dd>
   </dl>
如果未指定選項，則會顯示現行帳戶、地區、組織及空間。



<strong>範例</strong>：

設定現行帳戶、組織及空間：

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

切換至新的地區：

```
ibmcloud target -r eu-gb
```

檢視現行帳戶、地區、組織及空間：

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

將 CLI 更新為最新版本。

```
ibmcloud update [-f]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
<dl>
  <dt>-f</dt>
  <dd>強制更新，而不進行確認。需要 root 專用權。</dd>
</dl>


## 一般 CLI (ibmcloud sl) 指令
{: #softlayer_cli}


請在 {{site.data.keyword.Bluemix_notm}} 指令行介面 (CLI) 中使用基礎架構服務指令，以配置及管理基礎架構服務。

支援下列指令。使用 `ibmcloud sl` 指令，以查看可用的指令清單：

<table summary="按字母順序排序的一般指令，其鏈結提供指令的相關資訊">
<caption>表 1. 一般基礎架構服務指令</caption>
 <thead>
 <th colspan="6">一般基礎架構服務指令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/ibmcloud/bx_cli.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/ibmcloud/bx_cli.html#sl_help)</td>
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
