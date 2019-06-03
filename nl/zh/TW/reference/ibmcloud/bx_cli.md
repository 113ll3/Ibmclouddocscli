---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

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
{: shortdesc}

{{site.data.keyword.cloud_notm}} 指令行用戶端已將 Cloud Foundry 指令行用戶端搭載在其安裝中。如果您已安裝自己的 Cloud Foundry CLI，請不要在相同的環境定義中使用您專屬安裝的 {{site.data.keyword.cloud_notm}} CLI 指令及 Cloud Foundry CLI 指令。如果您要使用 Cloud Foundry CLI 以在 {{site.data.keyword.cloud_notm}} CLI 環境定義中管理 Cloud Foundry 資源，請改為使用 **`ibmcloud cf [command]`**。請注意，不容許 **`ibmcloud cf api/login/logout/target`**，必須改為使用 **`ibmcloud api/login/logout/target`**。

到 2018 年五月為止，{{site.data.keyword.cloud_notm}} CLI 指令已從 **`bluemix`** 和 **`bx`** 變更為 **`ibmcloud`**。不過，您仍然可以使用 **`bluemix`** 及 **`bx`** CLI 指令，直到未來移除它們為止。
{: tip}

以下列出 {{site.data.keyword.cloud_notm}} CLI 所支援的詳細指令，包括其名稱、引數、選項、必要條件、說明及範例。


必要條件列出使用指令之前所需的動作，而且可能包含下列一個以上的動作：

<dl>
<dt>Docker</dt>
<dd>安裝 Docker CLI。</dd>
<dt>端點</dt>
<dd>使用 **`ibmcloud api`** 指令來設定 API 端點。</dd>
<dt>登入</dt>
<dd>使用 **`ibmcloud login`** 指令來登入。如果您要使用聯合 ID 進行登入，請使用 **`--sso`** 選項以一次性密碼進行鑑別，或使用 **`--apikey`** 選項以 API 金鑰進行鑑別。</dd>
<dt>目標</dt>
<dd>使用 **`ibmcloud target`** 指令來設定組織及空間。</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

顯示 {{site.data.keyword.cloud_notm}} CLI 之第一層內建指令及所支援名稱空間的一般說明，或特定內建指令或名稱空間的說明。

```
ibmcloud help [COMMAND|NAMESPACE]
```

### 必要條件
{: #help-prereqs}

無。

### 指令選項
{: #help-options}

<dl>
<dt>COMMAND|NAMESPACE</dt>
<dd>顯示其說明的指令或名稱空間。如果未指定，則會顯示 {{site.data.keyword.Bluemix_notm}} CLI 的一般說明。選用。</dd>
</dl>

### 範例
{: #help-examples}

顯示 {{site.data.keyword.cloud_notm}} CLI 的一般說明：
```
ibmcloud help
```
{: codeblock}

顯示 **`dev`** 指令的說明：
```
ibmcloud help dev
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

設定或檢視 {{site.data.keyword.cloud_notm}} API 端點。
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

### 必要條件
{: #api-prereqs}

無。

### 指令選項
{: #api-options}

<dl>
<dt>API_ENDPOINT</dt>
<dd>設為目標的 API 端點，例如 `https://cloud.ibm.com`。如果未同時指定 **`API_ENDPOINT`** 及 **`--unset`** 選項，則會顯示現行 API 端點。選用。</dd>
<dt>--skip-ssl-validation</dt>
<dd>略過 HTTP 要求的 SSL 驗證。選用。</dd>
<dt>--unset</dt>
<dd>移除 API 端點設定。</dd>
</dl>

### 範例
{: #api-examples}

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

移除 API 端點：
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

### 必要條件
{: #config-prereqs}

無。

### 指令選項
{: #config-options}

<dl>
<dt>--check-version</dt>
<dd>啟用或停用 CLI 版本檢查。有效值為 `true` 或 `false`。</dd>
<dt>--color</dt>
<dd>啟用或停用彩色輸出。依預設會停用這個選項。有效值為 `true` 或 `false`。</dd>
<dt>--http-timeout</dt>
<dd>用於 HTTP 要求的逾時值（以秒為單位）。預設值為 60 秒。</dd>
<dt>--locale</dt>
<dd>設定預設語言環境。如果未指定任何值，則會刪除先前的語言環境。</dd>
<dt>--trace</dt>
<dd>追蹤對終端機或指定檔案的 HTTP 要求。有效值為 `true` 或 `false`。</dd>
</dl>

您一次只能指定其中一個選項。
{: tip}

### 範例
{: #config-examples}

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

追蹤對 `/home/usera/my_trace` 檔案的 HTTP 要求：
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

自 CLI 0.14 版開始，無法再使用 **`ibmcloud info`** 指令。若要安裝最新 CLI 版本，請參閱[安裝獨立式 {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)。


## ibmcloud cf
{: #ibmcloud_cf}

呼叫內嵌的 Cloud Foundry CLI。
```
ibmcloud [-q, --quiet] cf COMMAND...
```

### 必要條件
{: #info-prereqs}

無。

### 指令選項
{: #info-options}

<dl>
  <dt>-q, --quiet</dt>
  <dd>不要顯示呼叫訊息。</dd>
</dl>

### 範例
{: #info-examples}

列出 Cloud Foundry 應用程式：
```
ibmcloud cf apps
```
{: codeblock}

列出 Cloud Foundry 服務，而不顯示 `Invoking cf command...` 訊息：
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud cf install
{: #ibmcloud_cf_install}

安裝適用於 IBM Cloud CLI 的 Cloud Foundry CLI
```
ibmcloud cf install [-v, --version VERSION] [--restore] [-f, --force]
```

### 必要條件
{: #cfinstall-prereqs}

無。

### 指令選項
{: #cfinstall-options}

<dl>
  <dt>-v, --version</dt>
  <dd>指定要安裝的 Cloud Foundry CLI 版本</dd>
  <dt>--restore</dt>
  <dd>還原至 Cloud Foundry CLI 的預先組合版本</dd>
  <dt>-f, --force</dt>
  <dd>強制安裝，而不進行確認</dd>
</dl>

### 範例
{: #cfinstall-examples}

安裝 Cloud Foundry CLI `6.44.1`：

```
ibmcloud cf install -v 6.44.1
```

安裝最新版本的 Cloud Foundry CLI，而不進行確認：

```
ibmcloud cf install -f
```

回復為預設組合的 Cloud Foundry CLI：

```
ibmcloud cf install --restore
```

## ibmcloud login
{: #ibmcloud_login}

登入 {{site.data.keyword.cloud_notm}} CLI。

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```
### 必要條件
{: #login-prereqs}

無。

### 指令選項
{: #login-options}

<dl>
<dt>-a API_ENDPOINT</dt>
<dd>API 端點，例如 `cloud.ibm.com`。</dd>
<dt>--apikey API_KEY 或 @API_KEY_FILE_PATH</dt>
<dd>API 金鑰內容，或透過 @ 符號指出的 API 金鑰檔案的路徑</dd>
<dt>-u USER_NAME</dt>
<dd>使用者名稱。選用。</dd>
<dt>-p PASS_WORD</dt>
<dd>使用者密碼。選用。</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>目標帳戶的 ID。此選項不能與 **`--no account`** 選項同時使用。</dd>
<dt>--no-account</dt>
<dd>強制以不使用帳戶的方式登入。不建議使用這個選項，它與 **`-c`** 選項不能同時使用。</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>目標資源群組的名稱。選用。</dd>
<dt>-r REGION</dt>
<dd>目標地區的名稱，例如 us-south 或 eu-gb。</dd>
<dt>--no-region</dt>
<dd>強制以不將地區設為目標的方式登入。</dd>
<dt>-o ORG</dt>
<dd>目標組織的名稱。此選項已淘汰。請改用 **`ibmcloud target -o org_name`**。選用。</dd>
<dt>-s SPACE</dt>
<dd>目標空間的名稱。此選項已淘汰。請改用 **`ibmcloud target -s space_name`**。選用。</dd>
<dt>--no-iam </dt>
<dd>強制向登入伺服器進行鑑別，而非公用 IAM。</dd>
<dt>--skip-ssl-validation</dt>
<dd>略過 HTTP 要求的 SSL 驗證。不建議使用這個選項。</dd>
</dl>

### 範例
{: #login-examples}

以互動方式登入。

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

設定您的 Cloud Found 組織及空間。您可以執行下列指令，以互動方式識別組織及空間：

```
  ibmcloud target --cf
  ```
{: codeblock}

或者，如果您知道服務所屬的組織及空間，則可以使用下列指令：

```
ibmcloud target -o <value> -s <value>
	```
{: codeblock}

使用具有相關聯帳戶的 API 金鑰：

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

使用沒有相關聯帳戶的 API 金鑰：

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

如果 API 金鑰具有相關聯的帳戶，則不支援切換至另一個帳戶。
{: note}

使用一次性密碼：

```
ibmcloud login -u UserID --sso
```
{: codeblock}

然後，CLI 會提供一個 URL 鏈結，並提示您輸入密碼：

```
一次性密碼（從 https://URL_Link_To_Obtain_Passcode 取得）：
```
{: screen}

在瀏覽器中開啟鏈結以取得密碼。在主控台中輸入給定的密碼以登入。

## ibmcloud logout
{: #ibmcloud_logout}

登出 CLI。

```
ibmcloud logout
```
{: codeblock}

### 必要條件
{: #logout-prereqs}

無。

## ibmcloud regions
{: #ibmcloud_regions}

檢視 {{site.data.keyword.Bluemix_notm}} 上所有地區的資訊。

```
ibmcloud regions
```
{: codeblock}

### 必要條件
{: #regions-prereqs}

使用 **`ibmcloud api`** 指令來設定 API 端點。

## ibmcloud target
{: #ibmcloud_target}

設定或檢視目標帳戶、地區、組織或空間。

```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

### 必要條件
{: #target-prereqs}

* 使用 **`ibmcloud api`** 指令來設定 API 端點。
* 使用 **`ibmcloud login`** 指令來登入。如果您要使用聯合 ID 進行登入，請使用 **`--sso`** 選項以一次性密碼進行鑑別，或使用 **`--apikey`** 選項以 API 金鑰進行鑑別。

### 指令選項
{: #target-options}

<dl>
<dt>-c ACCOUNT_ID</dt>
<dd>目標帳戶的 ID。選用。</dd>
<dt>-r REGION</dt>
<dd>目標地區的名稱，例如 us-south 或 eu-gb。選用。</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>目標資源群組的名稱。選用。</dd>
<dt>--cf</dt>
<dd>以互動方式指定目標組織及空間。</dd>
<dt>--cf-api</dt>
<dd>Cloud Foundry API 端點。</dd>
<dt>-o ORG</dt>
<dd>目標組織的名稱。選用。</dd>
<dt>-s SPACE</dt>
<dd>目標空間的名稱。選用。</dd>
<dt>--unset-region</dt>
<dd>清除已設定目標的地區。</dd>
<dt>--unset-resource-group</dt>
<dd>清除已設定目標的資源群組。</dd>
<dt>--output FORMAT</dt>
<dd>指定的輸出格式。JSON 是目前唯一支援的格式。</dd>
</dl>

如果未指定選項，則會顯示現行帳戶、地區、組織及空間。
{: note}

### 範例
{: #target-examples}

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
### 必要條件
{: #update-prereqs}

### 指令選項
{: #update-options}

<dl>
  <dt>-f</dt>
  <dd>強制執行更新，而不進行確認。需要 root 專用權。</dd>
</dl>

## 一般標準基礎架構服務指令
{: #softlayer_cli}

請在 {{site.data.keyword.cloud_notm}} CLI 中使用標準基礎架構指令，以配置及管理基礎架構服務。

執行 **`ibmcloud sl`** 指令，以查看可用的指令清單：
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

自 CLI **`0.14`** 版開始，無法再使用 `ibmcloud sl init` 指令。若要安裝最新 CLI 版本，請參閱[安裝獨立式 {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)。
{: note}

## ibmcloud sl help
{: #sl_help}

檢視用來操作標準基礎架構環境之所有指令的說明資訊。
```
ibmcloud sl help
```
{: codeblock}

