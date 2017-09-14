---



copyright:

  years: 2017

lastupdated: "2017-08-30"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# {{site.data.keyword.registrylong_notm}} CLI
{: #containerregcli}

{{site.data.keyword.registrylong}} CLI 是一種外掛程式，可管理您帳戶的登錄及其資源。
{: shortdesc}

**必要條件**
* 在執行登錄指令之前，請先使用 `bx login` 指令來登入 {{site.data.keyword.Bluemix_short}}，以產生 {{site.data.keyword.Bluemix_short}} 存取記號，並鑑別您的階段作業。

若要瞭解如何使用 {{site.data.keyword.registrylong}} CLI，請參閱[設定專用映像檔登錄](../../../services/Registry/index.html)。

<table summary="管理容器登錄">
<caption>表 1. 用來在 {{site.data.keyword.Bluemix_short}} 上管理 {{site.data.keyword.registryshort}} 的指令</caption>
 <thead>
 <th colspan="5">用來管理登錄的指令</th>
 </thead>
 <tbody>
 <tr>
 <td>[bx cr api](#bx_cr_api)</td>
 <td>[bx cr info](#bx_cr_info)</td>
 <td>[bx cr image-inspect](#bx_cr_image_inspect)</td>
 <td>[bx cr image-list (bx cr images)](#bx_cr_image_list)</td>
 <td>[bx cr image-rm](#bx_cr_image_rm)</td>
 </tr>
 <tr>
 <td>[bx cr login](#bx_cr_login)</td>
 <td>[bx cr namespace-add](#bx_cr_namespace_add)</td>
 <td>[bx cr namespace-list (bx cr namespaces)](#bx_cr_namespace_list)</td>
 <td>[bx cr namespace-rm](#bx_cr_namespace_rm)</td>
 <td>[bx cr plan](#bx_cr_plan)</td>
 </tr>
 <tr>
 <td>[bx cr plan-upgrade](#bx_cr_plan_upgrade)</td>
 <td>[bx cr pricing](#bx_cr_pricing)</td>
 <td>[bx cr quota](#bx_cr_quota)</td>
 <td>[bx cr quota-set](#bx_cr_quota_set)</td>
 <td>[bx cr token-add](#bx_cr_token_add)</td>
 </tr>
 <tr>
 <td>[bx cr token-get](#bx_cr_token_get)</td>
 <td>[bx cr token-list (bx cr tokens)](#bx_cr_token_list)</td>
 <td>[bx cr token-rm](#bx_cr_token_rm)</td>
 <td>[bx cr vulnerability-assessment (bx cr va)](#bx_cr_va)</td>
 </tr>
 </tbody></table>



## bx cr api
{: #bx_cr_api}

傳回執行指令所針對之登錄 API 端點的詳細資料。

```
bx cr api
```
{: codeblock}


## bx cr info
{: #bx_cr_info}

顯示所登入之登錄的名稱及帳戶。

```
bx cr info
```
{: codeblock}


## bx cr image-inspect
{: #bx_cr_image_inspect}

顯示特定映像檔的詳細資料。

```
bx cr image-inspect [--format FORMAT] IMAGE [IMAGE...]
```
{: codeblock}

**參數**

<dl>
<dt>--format FORMAT</dt>
<dd>（選用）使用 Go 範本將輸出元素格式化。如需相關資訊，請參閱[檢視映像檔的相關資訊](../../../services/Registry/registry_cli_reference.html#registry_cli_listing)。

</dd>
<dt>IMAGE</dt>
<dd>您要檢查之映像檔的完整 {{site.data.keyword.Bluemix_short}} 登錄路徑，格式為 `namespace/image:tag`。如果映像檔路徑中未指定標籤，則會檢查以 `latest` 標記的映像檔。若要檢查多個映像檔，您可以在指令中列出每一個專用 {{site.data.keyword.Bluemix_short}} 登錄路徑，每一個路徑之間以空格隔開。</dd>
</dl>


## bx cr image-list (bx cr images)
{: #bx_cr_image_list}

顯示 {{site.data.keyword.Bluemix_short}} 帳戶中的所有映像檔。

```
 bx cr image-list [--no-trunc] [-q, --quiet] [--include-ibm] [--format FORMAT]
```
{: codeblock}

**參數**
<dl>
<dt>--no-trunc</dt>
<dd>（選用）不要截斷映像檔摘要。</dd>
<dt>-q、--quiet</dt>
<dd>（選用）以下列格式列出每一個映像檔：`repository:tag`。</dd>
<dt>--include-ibm</dt>
<dd>（選用）將 IBM 提供的公用映像檔包含在輸出中。若不使用此選項，依預設只會列出專用映像檔。</dd>
<dt>--format FORMAT</dt>
<dd>（選用）使用 Go 範本將輸出元素格式化。如需相關資訊，請參閱[檢視映像檔的相關資訊](../../../services/Registry/registry_cli_reference.html#registry_cli_listing)。

</dd>
</dl>


## bx cr image-rm
{: #bx_cr_image_rm}

從登錄中刪除一個以上的指定映像檔。

```
bx cr image-rm IMAGE [IMAGE...]
```
{: codeblock}

**參數**
<dl>
<dt>IMAGE</dt>
<dd>您要移除之映像檔的完整 {{site.data.keyword.Bluemix_short}} 登錄路徑，格式為 `namespace/image:tag`。如果映像檔路徑中未指定標籤，則依預設會刪除以 `latest` 標記的映像檔。若要刪除多個映像檔，您可以在指令中列出每一個專用 {{site.data.keyword.Bluemix_short}} 登錄路徑，每一個路徑之間以空格隔開。</dd>
</dl>


## bx cr login
{: #bx_cr_login}

這個指令會對登錄執行 `docker login` 指令。必須執行 `docker login` 指令，才能針對登錄執行 `docker push` 或 `docker pull` 指令。若要執行其他 `bx cr` 指令，則不需要執行這個指令。如果未安裝 Docker，則這個指令會傳回錯誤訊息。

```
bx cr login
```
{: codeblock}


## bx cr namespace-add
{: #bx_cr_namespace_add}

將名稱空間新增至 {{site.data.keyword.Bluemix_short}} 帳戶。

```
bx cr namespace-add NAMESPACE
```
{: codeblock}

**參數**
<dl>
<dt>NAMESPACE</dt>
<dd>您要新增的名稱空間。此名稱空間在相同地區的所有 {{site.data.keyword.Bluemix_short}} 帳戶中必須是唯一的。</dd>
</dl>


## bx cr namespace-list (bx cr namespaces)
{: #bx_cr_namespace_list}

顯示 {{site.data.keyword.Bluemix_short}} 帳戶所擁有的所有名稱空間。

```
bx cr namespace-list
```
{: codeblock}


## bx cr namespace-rm
{: #bx_cr_namespace_rm}

從 {{site.data.keyword.Bluemix_short}} 帳戶中移除名稱空間。移除名稱空間時，也會刪除此名稱空間中的映像檔。

```
bx cr namespace-rm NAMESPACE
```
{: codeblock}

**參數**
<dl>
<dt>NAMESPACE</dt>
<dd>您要移除的名稱空間。</dd>
</dl>



## bx cr plan
{: #bx_cr_plan}

顯示定價方案。

```
bx cr plan
```
{: codeblock}


## bx cr plan-upgrade
{: #bx_cr_plan_upgrade}

讓您從免費方案升級至標準方案。

如需方案的相關資訊，請參閱[登錄方案](../../../services/Registry/registry_overview.html#registry_plans)。

```
bx cr plan-upgrade standard
```
{: codeblock}


## bx cr pricing
{: #bx_cr_pricing}

這個指令已移除。您可以使用定價計算機來計算預估成本，請參閱[預估 IBM Bluemix Container Registry 的成本](../../../services/Registry/registry_overview.html#registry_plan_billing#task_02)。


## bx cr quota
{: #bx_cr_quota}

顯示資料流量及儲存空間的現行配額，以及這些配額的用量資訊。

```
bx cr quota
```
{: codeblock}


## bx cr quota-set
{: #bx_cr_quota_set}

修改指定的配額。

```
bx cr quota-set [--traffic VALUE] [--storage VALUE]
```
{: codeblock}

**參數**
<dl>
<dt>--traffic VALUE</dt>
<dd>（選用）將資料流量配額變更為指定的值。如果您未獲授權，無法設定資料流量，或是設定了超出現行定價方案的值，則作業會失敗。</dd>
<dt>--storage VALUE</dt>
<dd>（選用）將儲存空間配額變更為指定的值。如果您未獲授權，無法設定儲存空間配額，或設定了超出現行定價方案的值，則作業會失敗。</dd>
</dl>


## bx cr token-add
{: #bx_cr_token_add}

新增可用來控制登錄存取權的記號。

```
bx cr token-add [--description VALUE] [-q, --quiet] [--non-expiring] [--readwrite]
```

{: codeblock}


**參數**
<dl>
<dt>--description VALUE</dt>
<dd>（選用）指定值作為記號說明，在您執行 `bx cr token-list` 時顯示。如果 IBM Bluemix Container Service 自動建立您的記號，則會將說明設為「Kubernetes 叢集」名稱。在此情況下，移除您的叢集時，會自動移除此記號。</dd>
<dt>-q、--quiet</dt>
<dd>（選用）僅顯示記號，不含任何周圍文字。</dd>
<dt>--non-expiring</dt>
<dd>（選用）建立具有不會到期之存取權的記號。若未設定此參數，記號的存取權依預設會在 24 個小時之後到期。</dd>
<dt>--readwrite</dt>
<dd>（選用）建立授與讀取權及寫入權的記號。若未使用此選項，則依預設為唯讀存取權。</dd>
</dl>


## bx cr token-get
{: #bx_cr_token_get}

從登錄中擷取指定的記號。

```
bx cr token-get TOKEN
```

{: codeblock}

**參數**
<dl>
<dt>TOKEN</dt>
<dd>（選用）您要擷取之記號的唯一 ID。</dd>
</dl>


## bx cr token-list (bx cr tokens)
{: #bx_cr_token_list}

顯示 {{site.data.keyword.Bluemix_short}} 帳戶的所有現有記號。

```
bx cr token-list --format FORMAT
```
{: codeblock}

**參數**
<dl>
<dt>--format FORMAT</dt>
<dd>（選用）使用 Go 範本將輸出元素格式化。如需相關資訊，請參閱[檢視映像檔的相關資訊](../../../services/Registry/registry_cli_reference.html#registry_cli_listing)。

</dd>
</dl>

## bx cr token-rm
{: #bx_cr_token_rm}

移除一個以上的指定記號。

```
bx cr token-rm TOKEN [TOKEN...]
```
{: codeblock}

**參數**
<dl>
<dt>TOKEN</dt>
<dd>（選用）TOKEN 可以是記號本身，或記號的唯一 ID（如 `bx cr token-list` 中所示）。您可以指定多個記號，而且必須以空格予以區隔。</dd>
</dl>


## bx cr vulnerability-assessment (bx cr va)
{: #bx_cr_va}

檢視映像檔的漏洞評量報告。

```
bx cr vulnerability-assessment IMAGE [IMAGE...]
```
{: codeblock}

**參數**
<dl>
<dt>IMAGE</dt>
<dd>您要取得報告之映像檔的完整 {{site.data.keyword.Bluemix_short}} 登錄路徑，格式為 `namespace/image:tag`。報告會告訴您映像檔是否有任何已知的套件漏洞。支援下列作業系統：

<ul>

<li>Alpine</li>
<li>CentOS</li>
<li>Debian</li>
<li>Red Hat Enterprise Linux (RHEL)</li>
<li>Ubuntu</li>
</ul>

如需相關資訊，請參閱[檢閱映像檔安全](../../../services/Registry/registry_images_.html#registry_security_checking)。

</dd>

</dl>

