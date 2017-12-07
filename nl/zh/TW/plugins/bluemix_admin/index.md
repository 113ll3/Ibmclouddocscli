---

copyright:

  years: 2015, 2017

lastupdated: "2017-09-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} 管理 CLI
{: #bluemixadmincli}


您可以搭配使用 Cloud Foundry 指令行介面與 {{site.data.keyword.Bluemix_notm}} 管理 CLI 外掛程式，來管理「{{site.data.keyword.Bluemix_notm}} 本端」或「{{site.data.keyword.Bluemix_notm}} 專用」環境。例如，您可以從 LDAP 登錄新增使用者。如果您要尋找管理「{{site.data.keyword.Bluemix_notm}} 公用」帳戶的相關資訊，請參閱[管理](/docs/admin/adminpublic.html#administer)。

在開始之前，請先安裝 cf 指令行介面。{{site.data.keyword.Bluemix_notm}} 管理 CLI 外掛程式需要 cf 6.11.2 版或更新版本。[下載 Cloud Foundry 指令行介面 ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://github.com/cloudfoundry/cli/releases){: new_window}

**限制：**Cygwin 不支援 Cloud Foundry 指令行介面。請在非 Cygwin 指令行視窗的指令行視窗中使用 Cloud Foundry 指令行介面。

**附註**：{{site.data.keyword.Bluemix_notm}} 管理 CLI 僅適用於「{{site.data.keyword.Bluemix_notm}} 本端」及「{{site.data.keyword.Bluemix_notm}} 專用」環境。「{{site.data.keyword.Bluemix_notm}} 公用」則不予支援。

## 新增 {{site.data.keyword.Bluemix_notm}} 管理 CLI 外掛程式

安裝 cf 指令行介面之後，您可以新增 {{site.data.keyword.Bluemix_notm}} 管理 CLI 外掛程式。

**附註**：如果您先前已安裝 {{site.data.keyword.Bluemix_notm}} 管理外掛程式，則可能需要解除安裝外掛程式、刪除儲存庫，然後重新安裝以取得最新更新。

完成下列步驟以新增儲存庫並安裝外掛程式：

<ol>
<li>若要新增 {{site.data.keyword.Bluemix_notm}} 管理外掛程式儲存庫，請執行下列指令：<br/><br/>
<code>
cf add-plugin-repo BluemixAdmin https://console.&lt;subdomain&gt;.bluemix.net/cli
</code><br/><br/>
</li>
<li>若要安裝 {{site.data.keyword.Bluemix_notm}} 管理 CLI 外掛程式，請執行下列指令：<br/><br/>
<code>
cf install-plugin BluemixAdminCLI -r BluemixAdmin
</code>
</li>
</ol>

如果您需要解除安裝外掛程式，則可以使用下列指令，然後新增已更新的儲存庫以及安裝最新外掛程式：

* 解除安裝外掛程式：`cf uninstall-plugin BluemixAdminCLI`
* 移除外掛程式儲存庫：`cf remove-plugin-repo BluemixAdmin`


## 使用 {{site.data.keyword.Bluemix_notm}} 管理 CLI 外掛程式

您可以使用 {{site.data.keyword.Bluemix_notm}} 管理 CLI 外掛程式來新增或移除使用者、對組織指派或取消指派使用者，以及執行其他管理作業。

若要查看指令清單，請執行下列指令：


```
cf plugins
```
{: codeblock}

如需指令的其他說明，請使用 `-help` 選項。

### 連接並登入 {{site.data.keyword.Bluemix_notm}}

如果尚未連接並登入，您必須先完成此作業，才能使用管理 CLI 外掛程式。

<ol>
<li>若要連接至 {{site.data.keyword.Bluemix_notm}} API 端點，請執行下列指令：<br/><br/>
<code>
cf ba api https://console.&lt;subdomain&gt;.bluemix.net
</code>
<dl class="parml">
<dt class="pt dlterm">&lt;subdomain&gt;</dt>
<dd class="pd">您的 {{site.data.keyword.Bluemix_notm}} 實例 URL 的子網域。<br />
</dd>
</dl>
<p>您可以查看「管理主控台」的「資源及資訊」頁面，以取得正確的 URL。URL 顯示在「API 資訊」區段的 **API URL** 欄位中。</p>
</li>
<li>使用下列指令登入 {{site.data.keyword.Bluemix_notm}}：<br/><br/>
<code>
cf login
</code>
</li>
</ol>

## 管理使用者
{: #admin_users}

### 新增使用者
{: #admin_add_user}

若要從環境的使用者登錄中，將使用者新增至 {{site.data.keyword.Bluemix_notm}} 環境，請使用下列指令：

```
cf ba add-user <user_name> <organization> <first_name> <last_name>
```
{: codeblock}

**附註**：若要將使用者新增至特定組織，您必須是具有 **users.write**（或**超級使用者**）許可權的**管理者**。如果您是組織管理員，則透過「超級使用者」執行 **enable-managers-add-users** 指令，您也可以具有將使用者新增至組織的功能。如需相關資訊，請參閱[允許管理員新增使用者](index.html#clius_emau)。

<dl class="parml">
<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">LDAP 登錄中的使用者名稱。</dd>
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要新增使用者之 {{site.data.keyword.Bluemix_notm}} 組織的名稱或 GUID。</dd>
<dt class="pt dlterm">&lt;first_name&gt;</dt>
<dd class="pd">要新增至組織之使用者的名字。</dd>
<dt class="pt dlterm">&lt;last_name&gt;</dt>
<dd class="pd">要新增至組織之使用者的姓氏。</dd>
</dl>

**提示：**您也可以使用 **ba au** 作為 **ba add-user** 這個較長指令名稱的別名。

<!-- staging-only commands start. Live for interconnect -->

### 搜尋使用者
{: #admin_search_user}

若要搜尋使用者，請搭配使用下列指令與選用性的搜尋過濾器參數（name、permission、organization 及 role）：

```
cf ba search-users -name=<user_name_value> -permission=<permission_value> -organization=<organization_value> -role=<role_value>
```
{: codeblock}

<dl class="parml">

<dt class="pt dlterm">&lt;user_name_value&gt;</dt>
<dd class="pd">{{site.data.keyword.Bluemix_notm}} 中的使用者名稱。</dd>
<dt class="pt dlterm">&lt;permission_value&gt;</dt>
<dd class="pd">指派給使用者的許可權。例如，admin（或 superuser）、login（或 basic）、catalog.read、catalog.write、reports.read、reports.write、users.read 或 users.write。如需所指派使用者許可權的相關資訊，請參閱[許可權](/docs/admin/index.html#permissions)。您不能在相同的查詢中搭配使用此參數與 organization 參數。</dd>
<dt class="pt dlterm">&lt;organization_value&gt;</dt>
<dd class="pd">使用者所屬的組織名稱。您不能在相同的查詢中搭配使用此參數與 permission 參數。</dd>
<dt class="pt dlterm">&lt;role_value&gt;</dt>
<dd class="pd">指派給使用者的組織角色。例如，auditor、manager 或 billing_manager。您必須使用此參數來指定組織。如需角色的相關資訊，請參閱[使用者角色](/docs/admin/users_roles.html#userrolesinfo)。</dd>

</dl>

**提示：**您也可以使用 **ba su** 作為 **ba search-users** 這個較長指令名稱的別名。

### 設定使用者的許可權
{: #admin_setperm_user}

若要設定所指定使用者的許可權，請使用下列指令：

```
cf ba set-permissions <user_name> <permission> <access>
```
{: codeblock}

**附註**：一次可以設定一個許可權。

<dl class="parml">
<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">{{site.data.keyword.Bluemix_notm}} 中的使用者名稱。</dd>
<dt class="pt dlterm">&lt;permission&gt;</dt>
<dd class="pd">設定使用者的許可權：管理（可用的替代項目是「超級使用者」）、登入（可用的替代項目是「基本」）、型錄（「讀取」或「寫入」存取權）、報告（「讀取」或「寫入」存取權）或使用者（「讀取」或「寫入」存取權）。</dd>
<dt class="pt dlterm">&lt;access&gt;</dt>
<dd class="pd">對於「型錄」、「報告」或「使用者」許可權，您還必須將存取層次設定為 <code>read</code> 或 <code>write</code>。</dd>
</dl>

**提示：**您也可以使用 **ba sp** 作為 **ba set-permissions** 這個較長指令名稱的別名。

<!-- staging-only commands end -->

### 移除使用者
{: #admin_remov_user}

若要從 {{site.data.keyword.Bluemix_notm}} 環境移除使用者，請使用下列指令：

```
cf ba remove-user <user_name>
```
{: codeblock}

<dl class="parml">

<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">{{site.data.keyword.Bluemix_notm}} 中的使用者名稱。</dd>

</dl>

**提示：**您也可以使用 **ba ru** 作為 **ba remove-user** 這個較長指令名稱的別名。

### 允許管理員新增使用者
{: #clius_emau}

如果您在 {{site.data.keyword.Bluemix_notm}} 環境中具有**超級使用者**許可權，則可以允許組織管理員將使用者新增至他們所管理的組織。若要讓管理員新增使用者，請使用下列指令：

```
cf ba enable-managers-add-users
```
{: codeblock}

**提示：**您也可以使用 **ba emau** 作為 **ba enable-managers-add-users** 這個較長指令名稱的別名。

### 禁止管理員新增使用者
{: #clius_dmau}

如果已在您的 {{site.data.keyword.Bluemix_notm}} 環境中使用 **enable-managers-add-users** 指令，讓組織管理員能將使用者新增至他們所管理的組織，而且您具有**超級使用者**許可權，則可以移除此設定。若要停止讓管理員新增使用者，請使用下列指令：

```
cf ba disable-managers-add-users
```
{: codeblock}

**提示：**您也可以使用 **ba dmau** 作為 **ba disable-managers-add-users** 這個較長指令名稱的別名。

## 管理組織
{: #admin_orgs}

### 新增組織
{: #admin_add_org}

若要新增組織，請使用下列指令：

```
cf ba create-org <organization> <manager>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要新增之 {{site.data.keyword.Bluemix_notm}} 組織的名稱或 GUID。</dd>
<dt class="pt dlterm">&lt;manager&gt;</dt>
<dd class="pd">組織管理員的使用者名稱。</dd>
</dl>

**提示：**您也可以使用 **ba co** 作為 **ba create-org** 這個較長指令名稱的別名。

{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要刪除之 {{site.data.keyword.Bluemix_notm}} 組織的名稱或 GUID。</dd>
</dl>

**提示：**您也可以使用 **ba do** 作為 **ba delete-org** 這個較長指令名稱的別名。

### 將使用者指派至組織
{: #admin_ass_user_org}

若要將 {{site.data.keyword.Bluemix_notm}} 環境中的使用者指派給特定組織，請使用下列指令：

```
cf ba set-org <user_name> <organization> [<role>]
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">{{site.data.keyword.Bluemix_notm}} 中的使用者名稱。</dd>
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要指派使用者之 {{site.data.keyword.Bluemix_notm}} 組織的名稱或 GUID。</dd>
<dt class="pt dlterm">&lt;role&gt;</dt>
<dd class="pd">請參閱[角色](/docs/admin/users_roles.html)，以取得 {{site.data.keyword.Bluemix_notm}} 使用者的角色及說明。</dd>
</dl>

**提示：**您也可以使用 **ba so** 作為 **ba set-org** 這個較長指令名稱的別名。

### 從組織取消指派使用者
{: #admin_unass_user_org}

若要從特定組織取消指派 {{site.data.keyword.Bluemix_notm}} 環境中的使用者，請使用下列指令：

```
cf ba unset-org <user_name> <organization> [<role>]
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">{{site.data.keyword.Bluemix_notm}} 中的使用者名稱。</dd>
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要指派使用者之 {{site.data.keyword.Bluemix_notm}} 組織的名稱或 GUID。</dd>
<dt class="pt dlterm">&lt;role&gt;</dt>
<dd class="pd">請參閱[指派角色](/docs/admin/users_roles.html)，以取得 {{site.data.keyword.Bluemix_notm}} 使用者角色及說明。</dd>
</dl>

**提示：**您也可以使用 **ba uo** 作為 **ba unset-org** 這個較長指令名稱的別名。

#### 指派角色

<dl class="parml">
<dt class="pt dlterm">OrgManager</dt>
<dd class="pd">組織管理員。組織管理員具有執行下列動作的權限：<ul>
<li>在組織內建立或刪除空間。</li>
<li>邀請使用者加入組織及管理使用者。</li>
<li>管理組織的網域。</li>
</ul>
</dd>
<dt class="pt dlterm">BillingManager</dt>
<dd class="pd">帳單管理員。帳單管理員可以檢視組織的運行環境及服務用量資訊。</dd>
<dt class="pt dlterm">OrgAuditor</dt>
<dd class="pd">組織審核員。組織審核員可以檢視空間中的應用程式及服務內容。</dd>
</dl>

### 設定組織的配額
{: #admin_set_org_quota}

若要設定特定組織的用量配額，請使用下列指令：

```
cf ba set-quota <organization> <plan>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要設定其配額之 {{site.data.keyword.Bluemix_notm}} 組織的名稱或 GUID。</dd>
<dt class="pt dlterm">&lt;plan&gt;</dt>
<dd class="pd">組織的配額方案。</dd>
</dl>

**提示：**您也可以使用 **ba sq** 作為 **ba set-quota** 這個較長指令名稱的別名。


### 尋找組織的容器配額
{: #admin_find_containquotas}

若要尋找組織的容器配額，請使用下列指令：

```
cf bluemix-admin containers-quota <organization>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">Bluemix 中組織的名稱或 ID。這是必要參數。</dd>
</dl>

**提示：**您也可以使用 **ba cq** 作為 **bluemix-admin containers-quota** 這個較長指令名稱的別名。

### 設定組織的容器配額
{: #admin_set_containquotas}

若要設定組織中容器的配額，請使用下列指令，並至少包括其中一個選項：

```
cf bluemix-admin set-containers-quota <organization> <options>
```
{: codeblock}

**附註**：您可以包括多個選項，但必須至少包括一個。

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">Bluemix 中組織的名稱或 ID。這是必要參數。</dd>
<dt class="pt dlterm">&lt;options&gt;</dt>
<dd class="pd">包括下列一個以上的選項，其中的值必須是整數：
<ul>
<li>floating-ips-max &lt;value&gt;</li>
<li>floating-ips-space-default &lt;value&gt;</li>
<li>memory-max &lt;value&gt;</li>
<li>memory-space-default &lt;value&gt;</li>
<li>image-limit &lt;value&gt;</li>
</ul>
</dd>
</dl>

**提示：**您也可以使用下列簡稱作為較長選項名稱的別名：
<dl class="parml">
<dt class="pt dlterm">floating-ips-max &lt;value&gt;</dt>
<dd class="pd"><strong>fim</strong></dd>
<dt class="pt dlterm">floating-ips-space-default &lt;value&gt;</dt>
<dd class="pd"><strong>fisd</strong></dd>
<dt class="pt dlterm">memory-max &lt;value&gt;</dt>
<dd class="pd"><strong>mm</strong></dd>
<dt class="pt dlterm">memory-space-default &lt;value&gt;</dt>
<dd class="pd"><strong>msd</strong></dd>
<dt class="pt dlterm">image-limit &lt;value&gt;</dt>
<dd class="pd"><strong>il</strong></dd>
</dl>

您可以選擇提供一個檔案，其中包含有效 JSON 物件中的特定配置參數。如果使用 **-file** 選項，則會優先處理此選項，並忽略其他選項。若要提供檔案而非設定選項，請使用下列指令：

```
cf bluemix-admin set-containers-quota <organization> <-file path_to_JSON_file>
```
{: codeblock}

JSON 檔案應該具有下列範例中所顯示的格式：

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

**提示：**您也可以使用 **ba scq** 作為 **bluemix-admin set-containers-quota** 這個較長指令名稱的別名。

## 管理空間
{: #admin_spaces}

### 將空間新增至組織

若要在組織中新增空間，請使用下列指令：

```
cf bluemix-admin create-space <organization> <space_name>
```

{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要在其中新增空間之組織的名稱或 GUID。</dd>
<dt class="pt dlterm">&lt;space_name&gt;</dt>
<dd class="pd">要在組織中建立之空間的名稱。</dd>
</dl>

**提示：**您也可以使用 **ba cs** 作為 **ba create-space** 這個較長指令名稱的別名。

### 刪除組織中的空間

若要移除組織中的空間，請使用下列指令：

```
cf bluemix-admin delete-space <organization> <space_name>
```

{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要從中移除空間之組織的名稱或 GUID。</dd>
<dt class="pt dlterm">&lt;space_name&gt;</dt>
<dd class="pd">要從組織移除之空間的名稱。</dd>
</dl>

**提示：**您也可以使用 **ba cs** 作為 **ba delete-space** 這個較長指令名稱的別名。

### 在空間中新增具有某角色的使用者

若要在空間中建立具有指定角色的使用者，請使用下列指令：

```
cf bluemix-admin set-space <organization> <space_name> <user_name> <role>
```

{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要在其中新增使用者之組織的名稱或 GUID。</dd>
<dt class="pt dlterm">&lt;space_name&gt;</dt>
<dd class="pd">要在其中新增使用者之空間的名稱。</dd>
<dt class="pt dlterm">&lt;user_anme&gt;</dt>
<dd class="pd">要新增之使用者的名稱。</dd>
<dt class="pt dlterm">&lt;role&gt;</dt>
<dd class="pd">要指派之使用者的角色。此值可以是 Manager、Developer 或 Auditor。請參閱[指派角色](/docs/admin/users_roles.html)，以取得空間中的 {{site.data.keyword.Bluemix_notm}} 使用者角色及說明。</dd>
</dl>

**提示：**您也可以使用 **ba ss** 作為 **ba set-space** 這個較長指令名稱的別名。


### 移除空間中的使用者角色 

若要移除空間中的使用者角色，請使用下列指令：

```
cf bluemix-admin unset-space <organization> <space_name> <user_name> <role>
```

{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要在其中新增使用者之組織的名稱或 GUID。</dd>
<dt class="pt dlterm">&lt;space_name&gt;</dt>
<dd class="pd">要在其中新增使用者之空間的名稱。</dd>
<dt class="pt dlterm">&lt;user_anme&gt;</dt>
<dd class="pd">要新增之使用者的名稱。</dd>
<dt class="pt dlterm">&lt;role&gt;</dt>
<dd class="pd">要指派之使用者的角色。此值可以是 Manager、Developer 或 Auditor。請參閱[指派角色](/docs/admin/users_roles.html)，以取得空間中的 {{site.data.keyword.Bluemix_notm}} 使用者角色及說明。</dd>
</dl>

**提示：**您也可以使用 **ba us** 作為 **ba unset-space** 這個較長指令名稱的別名。

## 管理型錄
{: #admin_catalog}

### 針對所有組織啟用服務
{: #admin_ena_service_org}

若要啟用服務，以便針對所有組織顯示在 {{site.data.keyword.Bluemix_notm}}「型錄」中，請使用下列指令：

```
cf ba enable-service-plan <plan_identifier>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">您要停用之服務方案的名稱或 GUID。如果輸入非唯一的服務方案名稱（例如 "Standard" 或 "Basic"），系統會提示您可從中選擇的服務方案。若要識別服務方案名稱，請從首頁選取服務種類，然後選取**新增**，以檢視該種類的服務。請按一下服務名稱，以開啟詳細資料視圖，然後您可以檢視該服務可用的服務方案名稱。</dd>
</dl>

**提示：**您也可以使用 **ba esp** 作為 **ba enable-service-plan** 這個較長指令名稱的別名。

### 針對所有組織停用服務
{: #admin_dis_service_org}

若要讓所有組織在 {{site.data.keyword.Bluemix_notm}}「型錄」中看不見服務，請使用下列指令：

```
cf ba disable-service-plan <plan_identifier>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">您要停用之服務方案的名稱或 GUID。如果輸入非唯一的服務方案名稱（例如 "Standard" 或 "Basic"），系統會提示您可從中選擇的服務方案。若要識別服務方案名稱，請從首頁選取服務種類，然後選取**新增**，以檢視該種類的服務。請按一下服務名稱，以開啟詳細資料視圖，然後您可以檢視該服務可用的服務方案名稱。</dd>
</dl>

**提示：**您也可以使用 **ba dsp** 作為 **ba disable-service-plan** 這個較長指令名稱的別名。

### 新增組織的服務可見性
{: #admin_addvis_service_org}

您可以從組織清單中新增可在 {{site.data.keyword.Bluemix_notm}}「型錄」中看見特定服務的組織。若要容許組織在 {{site.data.keyword.Bluemix_notm}}「型錄」中檢視特定服務，請使用下列指令：

```
cf ba add-service-plan-visibility <plan_identifier> <organization>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">您要停用之服務方案的名稱或 GUID。如果輸入非唯一的服務方案名稱（例如 "Standard" 或 "Basic"），系統會提示您可從中選擇的服務方案。若要識別服務方案名稱，請從首頁選取服務種類，然後選取**新增**，以檢視該種類的服務。請按一下服務名稱，以開啟詳細資料視圖，然後您可以檢視該服務可用的服務方案名稱。</dd>
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要新增至服務可見性清單之 {{site.data.keyword.Bluemix_notm}} 組織的名稱或 GUID。</dd>
</dl>

**提示：**您也可以使用 **ba aspv** 作為 **ba add-service-plan-visibility** 這個較長指令名稱的別名。

### 移除組織的服務可見性
{: #admin_remvis_service_org}

您可以從可在 {{site.data.keyword.Bluemix_notm}}「型錄」看見特定服務的組織清單，移除某個組織。若要針對組織移除 {{site.data.keyword.Bluemix_notm}}「型錄」中的服務可見性，請使用下列指令：

```
cf ba remove-service-plan-visibility <plan_identifier> <organization>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">您要停用之服務方案的名稱或 GUID。如果輸入非唯一的服務方案名稱（例如 "Standard" 或 "Basic"），系統會提示您可從中選擇的服務方案。若要識別服務方案名稱，請從首頁選取服務種類，然後選取**新增**，以檢視該種類的服務。請按一下服務名稱，以開啟詳細資料視圖，然後您可以檢視該服務可用的服務方案名稱。</dd>
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要從服務的可見性清單移除之 {{site.data.keyword.Bluemix_notm}} 組織的名稱或 GUID。</dd>
</dl>

**提示：**您也可以使用 **ba rspv** 作為 **ba remove-service-plan-visibility** 這個較長指令名稱的別名。

### 編輯組織的服務可見性
{: #admin_editvis_service_org}

您可以編輯及取代特定組織可在 {{site.data.keyword.Bluemix_notm}}「型錄」中看到的服務清單。若要取代一個組織或多個組織的所有現有可見服務，請使用下列指令：

```
cf ba edit-service-plan-visibilities <plan_identifier> <organization_1> <optional_organization_2>
```
{: codeblock}

**附註：**這個指令會將所指定組織的現有可見服務取代為您在指令中指定的服務。

<dl class="parml">
<dt class="pt dlterm">&lt;plan_identifier&gt;</dt>
<dd class="pd">您要停用之服務方案的名稱或 GUID。如果輸入非唯一的服務方案名稱（例如 "Standard" 或 "Basic"），系統會提示您可從中選擇的服務方案。若要識別服務方案名稱，請從首頁選取服務種類，然後選取**新增**，以檢視該種類的服務。請按一下服務名稱，以開啟詳細資料視圖，然後您可以檢視該服務可用的服務方案名稱。</dd>
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">要新增可見性之 {{site.data.keyword.Bluemix_notm}} 組織的名稱或 GUID。您可以在指令中輸入其他組織名稱或 GUID，針對多個組織啟用服務的可見性。</dd>
</dl>

**提示：**您也可以使用 **ba espv** 作為 **ba edit-service-plan-visibility** 這個較長指令名稱的別名。

## 管理報告
{: #admin_add_report}

### 新增報告
{: #admin_add_report}

若要新增安全報告，請使用下列指令：

```
cf ba add-report <category> <date> <PDF|TXT|LOG> <RTF>
```
{: codeblock}

**附註**：如果您有報告許可權的寫入權，則可以建立新的種類，並以使用者可以接受的任何格式來新增報告。請在 `category` 參數中輸入新的種類名稱，或是將您的新報告新增至現有種類。

<dl class="parml">
<dt class="pt dlterm">&lt;category&gt;</dt>
<dd class="pd">報告的種類。如果名稱中有空格，請使用引號括住該名稱。</dd>
<dt class="pt dlterm">&lt;date&gt;</dt>
<dd class="pd">報告日期，格式為 <samp class="ph codeph">YYYYMMDD</samp>。</dd>
<dt class="pt dlterm">&lt;PDF|TXT|LOG&gt;</dt>
<dd class="pd">要上傳之報告 PDF、文字檔或日誌檔的路徑。</dd>
<dt class="pt dlterm">&lt;RTF&gt;</dt>
<dd class="pd">用來包含 PDF 之「Rich Text 格式 (RTF)」版本的選項。只有在您包含報告 PDF 的路徑時，此選項才適用。RTF 版本用於編製索引及進行搜尋。</dd>
</dl>

**提示：**您也可以使用 **ba ar** 作為 **ba add-report** 這個較長指令名稱的別名。

### 刪除報告
{: #admin_del_report}

若要刪除安全報告，請使用下列指令：

```
cf ba delete-report <category> <date> <name>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;category&gt;</dt>
<dd class="pd">報告的種類。如果名稱中有空格，請使用引號括住該名稱。</dd>
<dt class="pt dlterm">&lt;date&gt;</dt>
<dd class="pd">報告日期，格式為 <samp class="ph codeph">YYYYMMDD</samp>。</dd>
<dt class="pt dlterm">&lt;name&gt;</dt>
<dd class="pd">報告的名稱。</dd>
</dl>

**提示：**您也可以使用 **ba dr** 作為 **ba delete-report** 這個較長指令名稱的別名。

### 擷取報告
{: #admin_retr_report}

若要擷取安全報告，請使用下列指令：

```
cf ba retrieve-report <search>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;search&gt;</dt>
<dd class="pd">報告的檔名。如果名稱中有空格，請使用引號括住該名稱。</dd>
</dl>

**提示：**您也可以使用 **ba rr** 作為 **ba retrieve-report** 這個較長指令名稱的別名。

## 檢視資源度量值資訊
{: #cliresourceusage}

您可以檢視資源度量值資訊（包括記憶體用量、磁碟用量及 CPU 用量）。您可以查看可用的實體資源與保留資源的摘要，以及實體資源與保留資源用量的摘要。您也可以查看 Droplet Execution Agent (DEA) 及 Cell（Diego 架構）用量資料。若要檢視資源度量值資訊，請使用下列指令：

```
cf ba resource-metrics
```

**提示：**您也可以使用 **ba rsm** 作為 **ba resource-metrics** 這個較長指令名稱的別名。

## 檢視資源度量值歷程 
{: #cliresourceusagehistory}

您可以擷取記憶體及磁碟用量的資源度量值歷程。傳回的度量值包括已使用的資源量佔可用總計的比例（針對實體以及保留資源）。記憶體及磁碟用量歷程資料可以每小時、每日或每月顯示。您可以指定開始及結束日期，以在特定日期範圍內擷取資料。未指定任何日期時，預設歷程資料是最新 48 小時的每小時記憶體資料。資料以遞減順序顯示，最近的日期最先顯示。若要檢視資源度量值歷程資訊，請使用下列指令：

```
cf ba resource-metrics-history <hourly|daily|monthly>  <memory|disk >  <start|end>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;--hourly&gt;</dt>
<dd class="pd">檢視過去 48 小時的歷程資料。這是預設值。</dd>
<dt class="pt dlterm">&lt;--daily&gt;</dt>
<dd class="pd">檢視過去 30 天的歷程資料每日平均值。</dd>
<dt class="pt dlterm">&lt;--monthly&gt;</dt>
<dd class="pd">檢視過去 6 個月的歷程資料每月平均值。</dd>
<dt class="pt dlterm">&lt;--memory&gt;</dt>
<dd class="pd">檢視已使用及總計的保留和實體記憶體。</dd>
<dt class="pt dlterm">&lt;--disk&gt;</dt>
<dd class="pd">檢視已使用及總計的保留和實體磁碟。</dd>
<dt class="pt dlterm">&lt;--start&gt;</dt>
<dd class="pd">指定每日或每月的開始日期（格式必須為 mm-dd-yyyy），或是每小時的開始日期及時間（格式必須為 mm-dd-yyyy hh:mm:ss timezone）</dd>
<dt class="pt dlterm">&lt;--end&gt;</dt>
<dd class="pd">指定每日或每月的結束日期（格式必須為 mm-dd-yyyy），或是每小時的結束日期及時間（格式必須為 mm-dd-yyyy hh:mm:ss timezone）</dd>
</dl>

{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Examples&gt;</dt>
<dd class="pd">cf bluemix-admin resource-metrics-history</dd>
<dd class="pd">cf bluemix-admin resource-metrics-history --daily --disk --start=07-04-2017</dd>
<dd class="pd">cf bluemix-admin resource-metrics-history --monthly --memory</dd>
<dd class="pd">cf bluemix-admin resource-metrics-history --hourly --start="06-01-2017 00:00:00 EDT" --end="06-30-2017 23:59:00 EDT</dd>
</dl>

您可以使用下列指令來檢視應用程式環境變數： 

```
cf ba resource-metrics-history -help
```

**提示：**您也可以使用 **ba rsmh** 作為 **ba resource-metrics-history** 這個較長指令名稱的別名。

## 管理服務分配管理系統
{: #admin_servbro}

### 列出服務分配管理系統
{: #clilistservbro}

若要列出所有服務分配管理系統，請使用下列指令：

```
cf ba service-brokers <broker_name>
```
{: codeblock}

**附註**：若要列出所有服務分配管理系統，請輸入不含 `broker_name` 參數的指令。

<dl class="parml">
<dt class="pt dlterm">&lt;broker_name&gt;</dt>
<dd class="pd">選用項目：自訂服務分配管理系統的名稱。如果您要取得特定服務分配管理系統的資訊，請使用此參數。</dd>
</dl>

**提示：**您也可以使用 **ba sb** 作為 **ba service-brokers** 這個較長指令名稱的別名。

### 新增服務分配管理系統
{: #cliaddservbro}

若要新增服務分配管理系統，以將自訂服務新增至 {{site.data.keyword.Bluemix_notm}}「型錄」，請使用下列指令：

```
cf ba add-service-broker <broker_name> <user_name> <password> <broker_url>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;broker_name&gt;</dt>
<dd class="pd">自訂服務分配管理系統的名稱。</dd>
<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">可存取服務分配管理系統之帳戶的使用者名稱。</dd>
<dt class="pt dlterm">&lt;password&gt;</dt>
<dd class="pd">可存取服務分配管理系統之帳戶的密碼。</dd>
<dt class="pt dlterm">&lt;broker_url&gt;</dt>
<dd class="pd">服務分配管理系統的 URL。</dd>
</dl>

**提示：**您也可以使用 **ba asb** 作為 **ba add-service-broker** 這個較長指令名稱的別名。

### 刪除服務分配管理系統
{: #clidelservbro}

若要刪除服務分配管理系統，以從 {{site.data.keyword.Bluemix_notm}}「型錄」移除自訂服務，請使用下列指令：

```
cf ba delete-service-broker <service_broker>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;service_broker&gt;</dt>
<dd class="pd">自訂服務分配管理系統的名稱或 GUID。</dd>
</dl>

**提示：**您也可以使用 **ba dsb** 作為 **ba delete-service-broker** 這個較長指令名稱的別名。

### 更新服務分配管理系統
{: #cliupdservbro}

若要更新服務分配管理系統，請使用下列指令：

```
cf ba update-service-broker <broker_name> <user_name> <password> <broker_url>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;broker_name&gt;</dt>
<dd class="pd">自訂服務分配管理系統的名稱。</dd>
<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">可存取服務分配管理系統之帳戶的使用者名稱。</dd>
<dt class="pt dlterm">&lt;password&gt;</dt>
<dd class="pd">可存取服務分配管理系統之帳戶的密碼。</dd>
<dt class="pt dlterm">&lt;broker_url&gt;</dt>
<dd class="pd">服務分配管理系統的 URL。</dd>
</dl>

**提示：**您也可以使用 **ba usb** 作為 **ba update-service-broker** 這個較長指令名稱的別名。


## 管理應用程式安全群組
{: #admin_secgro}

若要使用應用程式安全群組 (ASG)，您必須是本端或專用環境中具有完整存取權的管理者。環境的所有使用者都可以列出可供指令設為目標之組織使用的 ASG。不過，若要建立、更新或連結 ASG，您必須是 {{site.data.keyword.Bluemix_notm}} 環境的管理者。

ASG 是當作虛擬防火牆使用，可控制 {{site.data.keyword.Bluemix_notm}} 環境中應用程式的出埠資料流量。每一個 ASG 都包含一份規則清單，可容許與外部網路之間的特定資料流量和通訊。您可以將一個以上的 ASG 連結至特定安全群組集（例如，用於套用廣域存取權的群組集），也可以連結至 {{site.data.keyword.Bluemix_notm}} 環境中組織內的空間。

{{site.data.keyword.Bluemix_notm}} 一開始是設定成限制外部網路的所有存取權。將 IBM 所建立的兩個安全群組（`public_networks` 及 `dns`）連結至預設 Cloud Foundry 安全群組集時，這些群組就會啟用外部網路的廣域存取權。Cloud Foundry 中用來套用廣域存取權的兩個安全群組集是 **Default Staging** 及 **Default Running** 群組集。這些群組集會套用規則，以容許對所有執行中應用程式或所有編譯打包中應用程式的資料流量。如果您不想要連結至這兩個安全群組集，則可以取消與 Cloud Foundry 群組集的連結，然後將安全群組連結至特定空間。如需相關資訊，請參閱 [Binding Application Security Groups ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://docs.cloudfoundry.org/adminguide/app-sec-groups.html#binding-groups){: new_window}。

**警告**：取消連結 **Default Staging** 或 **Default Running** 群組集與兩個 IBM 建立的安全群組
`public_networks` 及 `dns`，將會停用對外部網路的廣域存取。請小心使用取消連結，並了解它對您環境中所有執行中與編譯打包中的應用程式造成的結果。

**附註**：下列可讓您使用安全群組的指令是根據 Cloud Foundry 1.6 版。如需相關資訊（包括必要及選用性欄位），請參閱有關 [Creating Application Security Groups ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://docs.cloudfoundry.org/adminguide/app-sec-groups.html#creating-groups){: new_window} 的 Cloud Foundry 資訊。

### 列出安全群組
{: #clilissecgro}

* 若要列出所有安全群組，請使用下列指令：

```
cf ba security-groups
```
{: codeblock}

**提示：**您也可以使用 **ba sgs** 作為 **ba security-groups** 這個較長指令名稱的別名。

* 若要顯示特定安全群組的詳細資料，請使用下列指令：

```
cf ba security-groups <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">安全群組的名稱</dd>
</dl>

**提示：**您也可以使用 **ba sg** 作為 **ba security-groups** 這個較長指令名稱（含 `security-group` 參數）的別名。


### 建立安全群組
{: #clicreasecgro}

如需建立安全群組以及定義送出資料流量的規則相關資訊，請參閱 [Creating Application Security Groups ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://docs.cloudfoundry.org/adminguide/app-sec-groups.html#creating-groups){: new_window}。

若要建立安全群組，請使用下列指令：

```
cf ba create-security-group <security-group> <path-to-rules-file>
```
{: codeblock}

您建立的每一個安全群組的名稱前面都會加上 `adminconsole_` 字首，以與 IBM 所建立的安全群組進行區別。

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">您的安全群組名稱</dd>
<dt class="pt dlterm">&lt;Path to rules file&gt;</dt>
<dd class="pd">rules 檔的絕對或相對路徑</dd>
</dl>

**提示：**您也可以使用 **ba csg** 作為 **ba create-security-group** 這個較長指令名稱的別名。

### 更新安全群組
{: #cliupdsecgro}

若要更新安全群組，請使用下列指令：

```
cf ba update-security-group <security-group> <path-to-rules-file>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">您的安全群組名稱</dd>
<dt class="pt dlterm">&lt;Path to rules file&gt;</dt>
<dd class="pd">rules 檔的絕對或相對路徑</dd>
</dl>

**提示：**您也可以使用 **ba usg** 作為 **ba update-security-group** 這個較長指令名稱的別名。

### 刪除安全群組
{: #clidelsecgro}

若要刪除安全群組，請使用下列指令：

```
cf ba delete-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">您的安全群組名稱</dd>
</dl>

**提示：**您也可以使用 **ba dsg** 作為 **ba delete-security-group** 這個較長指令名稱的別名。


### 連結安全群組
{: #clibindsecgro}

如需連結安全群組的相關資訊，請參閱 [Binding Application Security Groups ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://docs.cloudfoundry.org/adminguide/app-sec-groups.html#binding-groups){: new_window}。

* 若要連結至 Default Staging 安全群組集，請使用下列指令：

```
cf ba bind-staging-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">您的安全群組名稱</dd>
</dl>

**提示：**您也可以使用 **ba bssg** 作為 **ba bind-staging-security-group** 這個較長指令名稱的別名。

* 若要連結至 Default Running 安全群組集，請使用下列指令：

```
cf ba bind-running-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">您的安全群組名稱</dd>
</dl>

**提示：**您也可以使用 **ba brsg** 作為 **ba bind-running-security-group** 這個較長指令名稱的別名。

* 若要將安全群組連結至空間，請使用下列指令：

```
cf ba bind-security-group <security-group> <org> <space>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">您的安全群組名稱</dd>
<dt class="pt dlterm">&lt;Org&gt;</dt>
<dd class="pd">要與安全群組取消連結的組織名稱</dd>
<dt class="pt dlterm">&lt;Space&gt;</dt>
<dd class="pd">組織內要與安全群組取消連結的空間名稱</dd>
</dl>

**提示：**您也可以使用 **ba bsg** 作為 **ba bind-security-group** 這個較長指令名稱的別名。

### 取消連結安全群組
{: #cliunbindsecgro}

如需取消連結安全群組的相關資訊，請參閱 [Unbinding Application Security Groups ![外部鏈結圖示](../../../icons/launch-glyph.svg)](https://docs.cloudfoundry.org/adminguide/app-sec-groups.html#unbinding-groups){: new_window}。

* 若要從 Default Staging 安全群組集取消連結，請使用下列指令：

```
cf ba unbind-staging-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">您的安全群組名稱</dd>
</dl>

**警告**：取消連結 **Default Staging** 群組集與兩個 IBM 建立的安全群組
`public_networks` 及 `dns`，將會停用對外部網路的廣域存取，必須小心使用取消連結，並了解它對您環境中所有編譯打包中的應用程式造成的結果。

**提示：**您也可以使用 **ba ussg** 作為 **ba unbind-staging-security-group** 這個較長指令名稱的別名。

* 若要從 Default Running 安全群組集取消連結，請使用下列指令：

```
cf ba unbind-running-security-group <security-group>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">您的安全群組名稱</dd>
</dl>

**警告**：取消連結 **Default Running** 群組集與兩個 IBM 建立的安全群組
`public_networks` 及 `dns`，將會停用對外部網路的廣域存取，必須小心使用取消連結，並了解它對您環境中所有執行中的應用程式造成的結果。

**提示：**您也可以使用 **ba brsg** 作為 **ba unbind-running-security-group** 這個較長指令名稱的別名。

* 若要取消安全群組與空間的連結，請使用下列指令：

```
cf ba unbind-security-group <security-group> <org> <space>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Security group&gt;</dt>
<dd class="pd">您的安全群組名稱</dd>
<dt class="pt dlterm">&lt;Org&gt;</dt>
<dd class="pd">要與安全群組取消連結的組織名稱</dd>
<dt class="pt dlterm">&lt;Space&gt;</dt>
<dd class="pd">組織內要與安全群組取消連結的空間名稱</dd>
</dl>

**提示：**您也可以使用 **ba usg** 作為 **ba unbind-staging-security-group** 這個較長指令名稱的別名。

## 管理建置套件
{: #admin_buildpack}

### 列出建置套件
{: #clilistbuildpack}

如果您具有應用程式型錄寫入權，則可以列出建置套件。若要列出所有建置套件，或檢視特定建置套件，請使用下列指令：

```
cf ba buildpacks <buildpack_name>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">選用性參數，可指定要檢視的特定建置套件。</dd>
</dl>

**提示：**您也可以使用 **ba lb** 作為 **ba buildpacks** 這個較長指令名稱的別名。

### 建立及上傳建置套件
{: #clicreupbuildpack}

如果您具有應用程式型錄寫入權，則可以建立及上傳建置套件。您可以上傳任何檔案類型為 .zip 的壓縮檔。若要上傳建置套件，請使用下列指令：

```
cf ba create-buildpack <buildpack_name> <file_path> <position>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">要上傳之建置套件的名稱。</dd>
<dt class="pt dlterm">&lt;file_path&gt;</dt>
<dd class="pd">建置套件壓縮檔的路徑。</dd>
<dt class="pt dlterm">&lt;position&gt;</dt>
<dd class="pd">在建置套件自動偵測期間檢查建置套件的順序。</dd>
</dl>

**提示：**您也可以使用 **ba cb** 作為 **ba create-buildpack** 這個較長指令名稱的別名。

### 更新建置套件
{: #cliupdabuildpack}

如果您具有應用程式型錄寫入權，則可以更新現有建置套件。若要更新建置套件，請使用下列指令：

```
cf ba update-buildpack <buildpack_name> <position> <enabled> <locked>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">要更新之建置套件的名稱。</dd>
<dt class="pt dlterm">&lt;position&gt;</dt>
<dd class="pd">在建置套件自動偵測期間檢查建置套件的順序。</dd>
<dt class="pt dlterm">&lt;enabled&gt;</dt>
<dd class="pd">指出是否將建置套件用於編譯打包。</dd>
<dt class="pt dlterm">&lt;locked&gt;</dt>
<dd class="pd">指出是否鎖定建置套件，以防止更新。</dd>
</dl>

**提示：**您也可以使用 **ba ub** 作為 **ba update-buildpack** 這個較長指令名稱的別名。

### 刪除建置套件
{: #clidelbuildpack}

如果您具有應用程式型錄寫入權，則可以刪除現有建置套件。若要刪除建置套件，請使用下列指令：

```
cf ba delete-buildpack <buildpack_name>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;buildpack_name&gt;</dt>
<dd class="pd">要刪除之建置套件的名稱。</dd>
</dl>

**提示：**您也可以使用 **ba db** 作為 **ba delete-buildpack** 這個較長指令名稱的別名。
