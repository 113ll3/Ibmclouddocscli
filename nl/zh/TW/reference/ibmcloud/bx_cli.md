---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# 一般 CLI (ibmcloud) 指令
{: #ibmcloud_cli}

{{site.data.keyword.cloud_notm}} 指令行介面 (CLI) 提供一組依名稱空間分組的指令，讓使用者與 {{site.data.keyword.cloud_notm}} 互動。

{{site.data.keyword.cloud_notm}} 指令行用戶端已將 Cloud Foundry 指令行用戶端搭載在其安裝中。如果您已安裝自己的 cf cli，請不要在相同環境定義中使用自己的安裝的 {{site.data.keyword.cloud_notm}} CLI 指令 `ibmcloud [command]` 及 Cloud Foundry CLI 指令 `cf [command]`。如果您要使用 cf cli 來管理 {{site.data.keyword.cloud_notm}} CLI 環境定義中的 Cloud Foundry 資源，請改為使用 `ibmcloud cf [command]`。請注意，不容許 `ibmcloud cf api/login/logout/target`，必須改為使用 `ibmcloud api/login/logout/target`。

到 2018 年五月為止，{{site.data.keyword.cloud_notm}} CLI 指令已從 `bluemix` 和 `bx` 變更為 `ibmcloud`。不過，您仍然可以使用 `bluemix` 及 `bx` CLI 指令，直到未來移除它們為止。
{: tip}

以下列出 {{site.data.keyword.cloud_notm}} CLI 所支援的詳細指令，包括其名稱、引數、選項、必要條件、說明及範例。
{: shortdesc}

*必要條件* 列出使用指令之前所需的動作。沒有必要動作的指令會列為**無**。否則，必要條件可能包括下列一個以上的動作：

<dl>
<dt>端點</dt>
<dd>必須透過 <code>ibmcloud api</code> 設定 API 端點後，才能使用這個指令。</dd>
<dt>登入</dt>
<dd>需要使用 <code>ibmcloud login</code> 指令進行登入後，才能使用這個指令。如果是使用聯合 ID 進行登入，請使用 '--sso' 選項以一次性密碼進行鑑別，或使用 '--apikey' 以 API 金鑰進行鑑別。</dd>
<dt>目標</dt>
<dd>必須使用 <code>ibmcloud target</code> 指令來設定組織及空間後，才能使用這個指令。</dd>
<dt>Docker</dt>
<dd>必須先安裝 Docker CLI (docker)，才能執行這個指令。</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

顯示 {{site.data.keyword.cloud_notm}} CLI 之第一層內建指令及所支援名稱空間的一般說明，或特定內建指令或名稱空間的說明。

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

顯示 {{site.data.keyword.cloud_notm}} CLI 的一般說明：
```
ibmcloud help
```
{: codeblock}

顯示 `info` 指令的說明：
```
ibmcloud help info
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

設定或檢視 {{site.data.keyword.cloud_notm}} API 端點。
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>必要條件</strong>：無

<strong>指令選項</strong>：
   <dl>
   <dt>API_ENDPOINT（選用）</dt>
   <dd>設為目標的 API 端點，例如 `https://cloud.ibm.com`。如果未同時指定 *API_ENDPOINT* 及 `--unset` 選項，則會顯示現行 API 端點。</dd>
   <dt>--unset（選用）</dt>
   <dd>移除 API 端點設定。</dd>
   <dt>--skip-ssl-validation（選用）</dt>
   <dd>略過 HTTP 要求的 SSL 驗證。</dd>
   </dl>
<strong>範例</strong>：

將 API 端點設為 cloud.ibm.com：
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

檢視現行 API 端點：
```
ibmcloud api
```
{: codeblock}

取消設定 API 端點：
```
ibmcloud api --unset
```
{: codeblock}

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
{: codeblock}

啟用 HTTP 要求的追蹤輸出：
```
ibmcloud config --trace true
```
{: codeblock}

追蹤對指定檔案 */home/usera/my_trace* 的 HTTP 要求：
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

停用彩色輸出：
```
ibmcloud config --color false
```
{: codeblock}

將語言環境設為 zh_Hans：
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

清除語言環境設定：
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

自 CLI `0.14` 版開始，無法再使用 `ibmcloud info` 指令。若要安裝最新 CLI 版本，請參閱[安裝獨立式 {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)。
{: note}

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
{: codeblock}

## ibmcloud login
{: #ibmcloud_login}

登入使用者。
```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```

<strong>必要條件</strong>：無

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>指令選項</strong>：
<dl>
  <dt> -a <i>API_ENDPOINT</i>（選用）</dt>
  <dd> API 端點（例如：cloud.ibm.com）</dd>
  <dt> --apikey <i>API_KEY 或 @API_KEY_FILE_PATH</i>
  <dd> API 金鑰內容，或透過 @ 指出的 API 金鑰檔案的路徑</dd>
  <dt> --sso（選用）</dt>
  <dd> 使用一次性密碼進行登入</dd>
  <dt> -u <i>USERNAME</i>（選用）</dt>
  <dd> 使用者名稱</dd>
  <dt> -p <i>PASSWORD</i>（選用）</dt>
  <dd> 密碼</dd>
  <dt> -c <i>ACCOUNT_ID</i>（選用）</dt>
  <dd> 目標帳戶的 ID。此選項與 --no-account 不能同時使用。</dd>
  <dt> --no-account（選用）</dt>
  <dd> 強制以不使用帳戶的方式登入。不建議使用這個選項。此選項與 -c 不能同時使用。</dd>
  <dt> -g <i>RESOURCE_GROUP</i>（選用）</dt>
  <dd> 目標資源群組的名稱</dd>
  <dt> -r REGION</dt>
  <dd> 地區的名稱，例如 'us-south' 或 'eu-gb'</dt>
  <dt> --no-region</dt>
  <dd> 強制以將地區設為目標的方式登入。</dd>
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
{: codeblock}

以使用者名稱及密碼登入，並設定目標帳戶、組織及空間：
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

以一次性密碼登入，並設定目標帳戶、組織及空間：
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

### 使用 Cloud Foundry 服務

若要使用 Cloud Foundry 服務，您必須以 Cloud Foundry 組織及空間為目標。您可以執行下列指令，以互動方式選擇組織及空間：
```
  ibmcloud target --cf
  ```
{: codeblock}

您可以選擇使用前一個指令的輸出，以下列指令手動設定您的組織及空間：
```
ibmcloud target -o <value> -s <value>
	```
{: codeblock}

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
{: codeblock}

CLI 接著會提供 URL 鏈結，並要求密碼：
```
一次性密碼（從 https://URL_Link_To_Obtain_Passcode 取得）：
```
{: screen}

在瀏覽器中開啟鏈結，以取得密碼。在主控台中鍵入給定的密碼，您就可以登入。

## ibmcloud logout
{: #ibmcloud_logout}

登出使用者。
```
ibmcloud logout
```
{: codeblock}

<strong>必要條件</strong>：無

## ibmcloud regions
{: #ibmcloud_regions}

檢視 {{site.data.keyword.Bluemix_notm}} 上所有地區的資訊。
```
ibmcloud regions
```
{: codeblock}

<strong>必要條件</strong>：端點

## ibmcloud target
{: #ibmcloud_target}


設定或檢視目標帳戶、地區、組織或空間。
```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
   <dt>-c <i>ACCOUNT_ID</i>（選用）</dt>
   <dd>要設為目標的帳戶 ID。</dd>
   <dt>-r <i>REGION_NAME</i>（選用）</dt>
   <dd>要切換至的地區名稱，例如 'us-south' 或 'eu-gb'。</dd>
   <dt>-g <i>RESOURCE_GROUP</i>（選用）</dt>
   <dd>資源群組的名稱。</dd>
   <dt>--cf</dt>
   <dd>以互動方式選取目標組織及空間</dd>
   <dt>--cf-api</dt>
   <dd>Cloud Foundry API 端點</dd>
   <dt>-o <i>ORG_NAME</i>（選用）</dt>
   <dd>要設為目標的組織名稱。</dd>
   <dt>-s <i>SPACE_NAME</i>（選用）</dt>
   <dd>要設為目標的空間名稱。</dd>
   <dt>--unset-region</dt>
   <dd>取消設定已設定目標的地區</dd>
   <dt>--unset-resource-group</dt>
   <dd>取消設定目標資源群組</dd>
   <dt>--output <i>FORMAT</i></dt>
   <dd>指定輸出格式，目前只支援 JSON。</dd>
</dl>
如果未指定選項，則會顯示現行帳戶、地區、組織及空間。

<strong>範例</strong>：

設定現行帳戶、組織及空間：
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

切換至新的地區：
```
ibmcloud target -r eu-gb
```
{: codeblock}

檢視現行帳戶、地區、組織及空間：
```
ibmcloud target
```
{: codeblock}

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


## 一般標準基礎架構服務指令
{: #softlayer_cli}

請在 {{site.data.keyword.cloud_notm}} 指令行介面 (CLI) 中使用標準基礎架構指令，以配置及管理基礎架構服務。

執行 `ibmcloud sl` 指令，以查看可用的指令清單：
```
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Gen1 infrastructure Block Storage
   cdn             Gen1 infrastructure Content Delivery Network
   file            Gen1 infrastructure File Storage
   dns             Gen1 infrastructure Domain Name System
   globalip        Gen1 infrastructure Global IP addresses
   hardware        Gen1 infrastructure hardware servers
   image           Gen1 infrastructure Compute images
   ipsec           Gen1 infrastructure IPSEC VPN
   loadbal         Gen1 infrastructure Load balancers
   security        Gen1 infrastructure SSH Keys and SSL Certificates
   securitygroup   Gen1 infrastructure network security groups
   subnet          Gen1 infrastructure Network subnets
   ticket          Gen1 infrastructure Manage Tickets
   vlan            Gen1 infrastructure Network VLANs
   vs              Gen1 infrastructure Virtual Servers
   order           Gen1 infrastructure Orders
   user            Gen1 infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

若要檢視指令的說明資訊，請執行下列指令：
```
ibmcloud sl [command] -h
```

自 CLI `0.14` 版開始，無法再使用 `ibmcloud sl init` 指令。若要安裝最新 CLI 版本，請參閱[安裝獨立式 {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)。
{: note}

## ibmcloud sl help
{: #sl_help}

檢視用來操作標準基礎架構環境之所有指令的說明資訊。
```
ibmcloud sl help
```
{: codeblock}

