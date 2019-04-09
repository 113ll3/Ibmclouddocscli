---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}

# 管理帳戶、使用者和 Cloud Foundry 組織
{: #ibmcloud_commands_account}

請使用下列指令來管理帳戶、帳戶中的使用者，以及公用 Cloud Foundry 環境的組織、空間及角色。
{: shortdesc}

<table summary="您可以用來管理帳戶、組織、空間及角色的 ibmcloud 指令。">
<thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud account orgs](cli_acct_org_role.html#ibmcloud_account_orgs)</td>
 <td>[ibmcloud account org](cli_acct_org_role.html#ibmcloud_account_org)</td>
 <td>[ibmcloud account org-create](cli_acct_org_role.html#ibmcloud_account_org_create)</td>
 <td>[ibmcloud account org-replicate](cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
 <td>[ibmcloud account org-rename](cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud account spaces](cli_acct_org_role.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](cli_acct_org_role.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](cli_acct_org_role.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-users](cli_acct_org_role.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-roles](cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
 <td>[ibmcloud account org-role-set](cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-role-unset](cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](cli_acct_org_role.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-roles](cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[ibmcloud account list](cli_acct_org_role.html#ibmcloud_account_list)</td>
 <td>[ibmcloud account org-account](cli_acct_org_role.html#ibmcloud_account_org_account)</td>
 <td>[ibmcloud account users](cli_acct_org_role.html#ibmcloud_account_users)</td>
 <td>[ibmcloud account user-remove](cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
 <td>[ibmcloud account user-invite](cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[ibmcloud account user-reinvite](cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud app domain-cert](cli_acct_org_role.html#ibmcloud_app_domain_cert)</td>
  <td>[ibmcloud app domain-cert-add](cli_acct_org_role.html#ibmcloud_app_domain_cert_add)</td>
  <td>[ibmcloud app domain-cert-remove](cli_acct_org_role.html#ibmcloud_app_domain_cert_remove)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud account orgs
{: #ibmcloud_account_orgs}

列出所有組織。

```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>地區名稱。列出指定地區中的組織。如果未指定，則預設為現行地區。如果設為 'all'，則列出所有地區中的組織。</dd>
   <dt>--guid</dt>
   <dd>顯示組織的 GUID。此選項與 '--output' 不能同時使用。</dd>
   <dt>--output FORMAT</dt>
   <dd>指定輸出格式，目前只支援 JSON。此選項與 '--guid' 不能同時使用。</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>帳戶 ID。列出給定帳戶下的組織。若未指定，則預設為現行帳戶。如果設為 'all'，則列出所有帳戶下的組織。此選項與 '-u' 不能同時使用。</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>帳戶擁有者名稱。列出給定使用者所擁有之帳戶下的組織。若未指定，則預設為現行帳戶。如果設為 'all'，則列出所有帳戶下的組織。此選項與 '-c' 不能同時使用。</dd>
   </dl>

<strong>範例</strong>：

列出 `us-south` 地區中的所有組織，並顯示 GUID。

```
ibmcloud account orgs -r us-south --guid
```

以 JSON 格式列出所有組織。

```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

顯示指定組織的資訊。

```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>ORG_NAME（必要）</dt>
   <dd>組織的名稱。</dd>
   <dt>-r REGION</dt>
   <dd>地區名稱。如果未指定，預設值為現行地區。如果設為 'all'，則會列出所有地區中具有給定名稱的組織。</dd>
   <dt>--guid</dt>
   <dd>擷取並顯示給定組織的 GUID。會抑制組織的所有其他輸出。此選項與 '--output' 不能同時使用。</dd>
   <dt>--output REGION</dt>
   <dd>指定輸出格式，目前只支援 JSON。此選項與 '--guid' 不能同時使用。</dd>
   </dl>

<strong>範例</strong>：

顯示 `IBM` 組織的資訊，並顯示 GUID

```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

建立新的組織。只有帳戶擁有者才能執行此作業。

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>ORG_NAME（必要）</dt>
   <dd>所要建立之組織的名稱。</dd>
   <dt>-f</dt>
   <dd>強制建立，而不進行確認。</dd>
   </dl>

<strong>範例</strong>：

建立名稱為 `IBM` 的組織。

```
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

將組織從現行地區抄寫到另一個地區。

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>ORG_NAME（必要）</dt>
   <dd>要抄寫之現有組織的名稱。</dd>
   <dt>REGION_NAME（必要）</dt>
   <dd>管理所抄寫組織的地區名稱。</dd>
   </dl>

<strong>範例</strong>：

將組織 `myorg` 抄寫到地區 `eu-gb`：

```
ibmcloud account org-replicate myorg eu-gb
```

## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

重新命名組織。只有組織管理員才能執行此作業。

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>OLD_ORG_NAME（必要）</dt>
   <dd>要重新命名之組織的舊名稱。</dd>
   <dt>NEW_ORG_NAME（必要）</dt>
   <dd>組織重新命名後的新名稱。</dd>
   </dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

列出所有空間

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>-o ORG_NAME</dt>
   <dd>組織名稱。列出所指定組織下的空間。如果未指定，則預設為現行組織。</dd>
   <dt>-r REGION-NAM</dt>
   <dd>地區名稱。列出所指定地區下的空間。如果未指定，則預設為現行地區。</dd>
   <dt>--output FORMAT</dt>
   <dd>指定輸出格式，目前只支援 JSON。</dd>
   </dl>

<strong>範例</strong>：

列出所有空間：

```
ibmcloud account spaces
```

以 JSON 格式列出組織 `org_example` 的所有空間：

```
ibmcloud account spaces -o org_example --output JSON
```

## ibmcloud account space
{: #ibmcloud_account_space}

顯示指定空間的資訊。

```
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid | --output FORMAT] [--security-group-rules]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>SPACE_NAME（必要）</dt>
   <dd>要顯示之空間的名稱。</dd>
   <dt>-o ORG_NAME</dt>
   <dd>組織名稱。如果未指定，則預設為現行組織。</dd>
   <dt>--guid</dt>
   <dd>擷取並顯示給定空間的 GUID。會抑制空間的所有其他輸出。此選項與 '--output' 不能同時使用。</dd>
   <dt>--output FORMAT</dt>
   <dd>指定輸出格式，目前只支援 JSON。會抑制空間的所有其他輸出。此選項與 '--guid' 不能同時使用。</dd>
   <dt>--security-group-rules</dt>
   <dd>擷取所有與空間相關聯的安全群組的規則。</dd>
   </dl>

<strong>範例</strong>：

顯示空間 `space_example` 的資訊：

```
ibmcloud account space space_example
```

顯示空間 `space_example` 的 GUID：

```
ibmcloud account space space_example --guid
```

以 JSON 格式顯示空間 `space_example` 的資訊：

```
ibmcloud account space space_example --output JSON
```

顯示空間 `space_example` 的安全群組規則：

```
ibmcloud account space space_example --security-group-rules
```

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

這個指令的功能及選項與 [cf create-space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} 指令相同。

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


這個指令的功能及選項與 [cf rename-space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} 指令相同。

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


這個指令的功能及選項與 [cf delete-space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} 指令相同。

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

依角色顯示指定組織中的使用者。

```
ibmcloud account org-users ORG_NAME [-a] [--output FORMAT]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>ORG_NAME（必要）</dt>
<dd>組織的名稱。</dd>
<dt>-a（選用）</dt>
<dd>列出指定組織中的所有使用者，而不依角色分組。</dd>
<dt>--output FORMAT（選用）</dt>
<dd>--output value  指定輸出格式，目前只支援 JSON。</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

將使用者新增至組織（需要組織管理員）。

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

從組織移除使用者（僅限組織管理員或使用者自己）。

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>指令選項</strong>：
<dl>
<dt>--force, -f</dt>
<dd>強制刪除，而不確認。</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

取得現行使用者的所有組織角色。

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>-u</dt>
   <dd>使用者 ID。如果未指定，則預設為現行使用者。</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

將組織角色指派給使用者。只有組織管理員才能執行此作業。

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>USER_NAME（必要）</dt>
   <dd>所指派之使用者的名稱。</dd>
   <dt>ORG_NAME（必要）</dt>
   <dd>獲指派此使用者之組織的名稱。</dd>
   <dt>ORG_ROLE（必要）</dt>
   <dd>獲指派此使用者之組織角色的名稱。例如：
   <ul>
   <li>OrgManager：此角色可以邀請和管理使用者、選取和變更方案，以及設定消費限制。</li>
   <li>BillingManager：此角色可以建立和管理計費帳戶及付款資訊。</li>
   <li>OrgAuditor：此角色具有組織資訊和報告的唯讀權。</li>
   </ul>
   </dd>
  </dl>

<strong>範例</strong>：

以 `OrgManager` 角色，將使用者 `Mary` 指派給組織 `IBM`：

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
您可以使用 CLI 來設定組織/空間角色，但如果要設定其他許可權，則必須透過使用者介面。如需進一步詳細資料，請參閱[管理對資源的存取權](/docs/iam/mngiam.html#iammanidaccser)。
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

移除使用者的組織角色。只有組織管理員才能執行此作業。

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>USER_NAME（必要）</dt>
   <dd>所要移除之使用者的名稱。</dd>
   <dt>ORG_NAME（必要）</dt>
   <dd>從中移除此使用者之組織的名稱。</dd>
   <dt>ORG_ROLE（必要）</dt>
   <dd>從中移除此使用者之組織角色的名稱。例如：
   <ul>
   <li>OrgManager：此角色可以邀請和管理使用者、選取和變更方案，以及設定消費限制。</li>
   <li>BillingManager：此角色可以建立和管理計費帳戶及付款資訊。</li>
   <li>OrgAuditor：此角色具有組織資訊和報告的唯讀權。</li>
   </ul>
   </dd>
    </dl>

<strong>範例</strong>：

以 `OrgManager` 角色，從組織 `IBM` 移除使用者 `Mary`：

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

依角色顯示指定空間中的使用者。

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>ORG_NAME（必要）</dt>
   <dd>組織的名稱。</dd>
   <dt>SPACE_NAME（必要）</dt>
   <dd>空間的名稱。</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

將空間角色指派給使用者。只有空間管理員才能執行此作業。

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

   <dl>
   <dt>USER_NAME（必要）</dt>
   <dd>所指派之使用者的名稱。</dd>
   <dt>ORG_NAME（必要）</dt>
   <dd>獲指派此使用者之組織的名稱。</dd>
   <dt>SPACE_NAME（必要）</dt>
   <dd>獲指派此使用者之空間的名稱。</dd>
   <dt>SPACE_ROLE（必要）</dt>
   <dd>獲指派此使用者之空間角色的名稱。例如：
   <ul>
   <li>SpaceManager：此角色可以邀請和管理使用者，以及啟用給定空間的特性。</li>
   <li>SpaceDeveloper：此角色可以建立和管理應用程式及服務，以及查看日誌和報告。</li>
   <li>SpaceAuditor：此角色可以檢視空間的日誌、報告和設定。</li>
   </ul></dd>
    </dl>

<strong>範例</strong>：

以 `SpaceManager` 角色，將使用者 `Mary` 指派給組織 `IBM` 及空間 `Cloud`：

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

移除使用者的空間角色。只有空間管理員才能執行此作業。

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

   <dl>
   <dt>USER_NAME（必要）</dt>
   <dd>所要移除之使用者的名稱。</dd>
   <dt>ORG_NAME（必要）</dt>
   <dd>從中移除此使用者之組織的名稱。</dd>
   <dt>SPACE_NAME（必要）</dt>
   <dd>從中移除此使用者之空間的名稱。</dd>
   <dt>SPACE_ROLE（必要）</dt>
   <dd>從中移除此使用者之空間角色的名稱。例如：
   <ul>
   <li>SpaceManager：此角色可以邀請和管理使用者，以及啟用給定空間的特性。</li>
   <li>SpaceDeveloper：此角色可以建立和管理應用程式及服務，以及查看日誌和報告。</li>
   <li>SpaceAuditor：此角色可以檢視空間的日誌、報告和設定。</li>
   </ul></dd>
    </dl>


<strong>範例</strong>：

以 `SpaceManager` 角色，從組織 `IBM` 及空間 `Cloud` 移除使用者 `Mary`：

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

列出現行使用者的所有帳戶。

```
ibmcloud account list
```

<strong>必要條件</strong>：端點、登入

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

顯示所指定組織的帳戶（需要組織使用者）

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--guid（選用）</dt>
  <dd>僅顯示帳戶 ID</dd>
</dl>

## ibmcloud account users
{: #ibmcloud_account_users}

顯示與帳戶相關聯的使用者。只有帳戶擁有者才能執行此作業。

```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

從帳戶刪除使用者（僅限帳戶擁有者）

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>USER_ID（必要）</dt>
<dd>使用者 ID</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>帳戶 ID。如果未指定，則預設為現行帳戶。</dd>
<dt>-f, --force</dt>
<dd>強制移除，而不進行確認。</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

邀請使用者加入帳戶

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
   <dt>USER_EMAIL（必要）</dt>
   <dd>所邀請之使用者的電子郵件。</dd>
   <dt>-o ORG</dt>
   <dd>邀請使用者加入的組織</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>組織角色。有效輸入為：OrgManager、BillingManager、OrgAuditor 及 OrgUser。若省略，將設定 OrgUser 角色。</dd>
   <dt>-s SPACE</dt>
   <dd>邀請使用者加入的空間</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>空間角色。有效輸入為：SpaceManager、SpaceDeveloper 及 SpaceAuditor。</dd>
</dl>

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

將邀請重新傳送給使用者（帳戶管理者）

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
   <dt>USER_EMAIL（必要）</dt>
   <dd>所重新邀請之使用者的電子郵件</dd>
</dl>

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

列出網域的憑證資訊。

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>DOMAIN_NAME（必要）</dt>
<dd>管理憑證的網域。</dd>
</dl>


<strong>範例</strong>：

檢視網域 `ibmcxo-eventconnect.com` 的憑證資訊：

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

將憑證新增到現行組織中的指定網域。

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
   <dl>
   <dt>DOMAIN（必要）</dt>
   <dd>要新增憑證的網域。</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i>（必要）</dt>
   <dd>私密金鑰檔案路徑。</dd>
   <dt>-c <i>CERT_FILE</i>（必要）</dt>
   <dd>憑證檔案路徑。</dd>
   <dt>-p <i>PASSWORD</i>（選用）</dt>
   <dd>憑證的密碼。</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i>（選用）</dt>
   <dd>中繼憑證檔案路徑。</dd>
   <dt>-t <i>TRUST_STORE_FILE</i>（選用）</dt>
   <dd>信任儲存庫檔案。</dd>
   </dl>


<strong>範例</strong>：

將憑證新增到網域 `ibmcxo-eventconnect.com`：

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

從現行組織中的指定網域移除憑證。

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：

   <dl>
   <dt>DOMAIN（必要）</dt>
   <dd>要從中移除憑證的網域。</dd>
   <dt>-f（選用）</dt>
   <dd>強制刪除，而不確認。</dd>
   </dl>
