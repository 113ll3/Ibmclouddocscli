---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 用來管理帳戶、組織及角色的 CLI 指令
 {: #ibmcloud_commands_account}

<table summary="您可以用來管理帳戶、組織、空間及角色的 ibmcloud 指令。">
<caption>表 1. 用來管理帳戶、組織、空間及角色的指令</caption>
 <thead>
 <th colspan="5">用來管理帳戶、組織、空間及角色的指令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud account orgs](ic_cli_acct_org_role.html#ibmcloud_account_orgs)</td>
 <td>[ibmcloud account org](ic_cli_acct_org_role.html#ibmcloud_account_org)</td>
 <td>[ibmcloud account org-create](ic_cli_acct_org_role.html#ibmcloud_account_org_create)</td>
 <td>[ibmcloud account org-replicate](ic_cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
 <td>[ibmcloud account org-rename](ic_cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud account spaces](ic_cli_acct_org_role.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](ic_cli_acct_org_role.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](ic_cli_acct_org_role.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](ic_cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](ic_cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-users](ic_cli_acct_org_role.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](ic_cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](ic_cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-roles](ic_cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
 <td>[ibmcloud account org-role-set](ic_cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](ic_cli_acct_org_role.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-roles](ic_cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](ic_cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[ibmcloud account list](ic_cli_acct_org_role.html#ibmcloud_account_list)</td>
 <td>[ibmcloud account org-account](ic_cli_acct_org_role.html#ibmcloud_account_org_account)</td>
 <td>[ibmcloud account users](ic_cli_acct_org_role.html#ibmcloud_account_users)</td>
 <td>[ibmcloud account user-remove](ic_cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
 <td>[ibmcloud account user-invite](ic_cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[ibmcloud account user-reinvite](ic_cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud iam access-groups](ic_cli_acct_org_role.html#ibmcloud_iam_access-groups)</td>
  <td>[ibmcloud iam access-group](ic_cli_acct_org_role.html#ibmcloud_iam_access-group)</td>
  <td>[ibmcloud iam access-group-create](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-create)</td>
  <td>[ibmcloud iam access-group-update](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-delete)</td>
  <td>[ibmcloud iam access-group-users](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-users)</td>
  <td>[ibmcloud iam access-group-user-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-add)</td>
  <td>[ibmcloud iam access-group-user-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-remove)</td>
  <td>[ibmcloud iam access-group-user-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-service-ids](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-ids)</td>
  <td>[ibmcloud iam access-group-service-id-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-add)</td>
  <td>[ibmcloud iam access-group-service-id-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-remove)</td>
  <td>[ibmcloud iam access-group-service-id-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-purge)</td>
  <td>[ibmcloud iam access-group-policies](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-policy](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policy)</td>
  <td>[ibmcloud iam access-group-policy-create](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_create)</td>
  <td>[ibmcloud iam access-group-policy-update](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_update)</td>
  <td>[ibmcloud iam access-group-policy-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_delete)</td>
 </tr>
 </tbody>
 </table>
 
 ### ibmcloud account orgs
{: #ibmcloud_account_orgs}

列出所有組織

```
ibmcloud account orgs [-r REGION] [--guid]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>-r <i>REGION</i>（選用）</dt>
   <dd>顯示其組織資訊的地區。如果設為 'all'，則會列出所有地區中的所有組織。</dd>
   <dt>--guid（選用）</dt>
   <dd>顯示組織的 GUID。</dd>
   </dl>

<strong>範例</strong>：

列出 `us-south` 地區中的所有組織，並顯示 GUID

```
ibmcloud account orgs -r us-south --guid
```

### ibmcloud account org
{: #ibmcloud_account_org}

顯示所指定組織的資訊。

```
ibmcloud account org ORG_NAME [--guid]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
   <dl>
   <dt>ORG_NAME（必要）</dt>
   <dd>組織的名稱。</dd>
   <dt>--guid（選用）</dt>
   <dd>顯示組織的 GUID。</dd>
   </dl>

<strong>範例</strong>：

顯示 `IBM` 組織的資訊，並顯示 GUID

```
ibmcloud account org IBM --guid
```

### ibmcloud account org-create
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

### ibmcloud account org-replicate
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

### ibmcloud account org-rename
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

### ibmcloud account spaces
{: #ibmcloud_account_spaces}

列出所有空間

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>指令選項</strong>：
   <dl>
   <dt>-o</dt>
   <dd>組織名稱。列出所指定組織下的空間。如果未指定，則預設為現行組織。</dd>
   <dt>-r</dt>
   <dd>地區名稱。列出所指定地區下的空間。如果未指定，則預設為現行地區。</dd>
   </dl>

### ibmcloud account space
{: #ibmcloud_account_space}

這個指令的功能及選項與 [cf space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window} 指令相同。

### ibmcloud account space-create
{: #ibmcloud_account_space_create}

這個指令的功能及選項與 [cf create-space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} 指令相同。

### ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


這個指令的功能及選項與 [cf rename-space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} 指令相同。

### ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


這個指令的功能及選項與 [cf delete-space ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} 指令相同。

### ibmcloud account org-users
{: #ibmcloud_account_org_users}

依角色顯示指定組織中的使用者。

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>ORG_NAME（必要）</dt>
<dd>組織的名稱。</dd>
<dt>-a（選用）</dt>
<dd>列出指定組織中的所有使用者，而不依角色分組。</dd>
</dl>

### ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

將使用者新增至組織（需要組織管理員）。

```
 ibmcloud account org-user-add USER_NAME ORG
```

### ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

從組織移除使用者（僅限組織管理員或使用者自己）

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>指令選項</strong>：
<dl>
<dt>--force, -f</dt>
<dd>強制刪除，而不確認。</dd>
</dl>

### ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

取得現行使用者的所有組織角色

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>-u</dt>
   <dd>使用者 ID。如果未指定，則預設為現行使用者。</dd>
  </dl>

### ibmcloud account org-role-set
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
**附註**：您可以使用 CLI 設定組織/空間角色，但如果您要設定其他許可權，則必須利用使用者介面。如需進一步詳細資料，請參閱[指派使用者存取權](/docs/iam/assignaccess.html#assignaccess)。<!-- Begin Staging URL vs Prod URL -->

### ibmcloud account org-role-unset
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

### ibmcloud account space-users
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

### ibmcloud account space-role-set
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

### ibmcloud account space-role-unset
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

### ibmcloud account list
{: #ibmcloud_account_list}

列出現行使用者的所有帳戶

```
ibmcloud account list
```

<strong>必要條件</strong>：端點、登入

### ibmcloud account org-account
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

### ibmcloud account users
{: #ibmcloud_account_users}

顯示與帳戶相關聯的使用者。只有帳戶擁有者才能執行此作業。

```
ibmcloud account users
```

### ibmcloud account user-remove
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

### ibmcloud account user-invite
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

### ibmcloud account user-reinvite
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

### ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

列出現行帳戶下的存取群組

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-u</dt>
  <dd>列出使用者所屬的存取群組。此旗標與 '-s' 互斥。</dd>
  <dt>-s</dt>
  <dd>列出服務 ID 所屬的存取群組。此旗標與 '-u' 互斥。</dd>
</dl>

<strong>範例</strong>：

列出所有存取群組：

```
ibmcloud iam access-groups
```

### ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

顯示存取群組的詳細資料

```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-id</dt>
  <dd>僅顯示 ID</dd>
</dl>

<strong>範例</strong>：

顯示存取群組 `example_group` 的詳細資料：

```
ibmcloud iam access-group example_group
```

### ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

建立存取群組

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-d, --description</dt>
  <dd>存取群組的說明</dd>
</dl>

<strong>範例</strong>：

建立存取群組 `example_group`：

```
ibmcloud iam access-group-create example_group -d "example access group"
```

### ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

更新存取群組

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-n, --name</dt>
  <dd>新的存取群組名稱</dd>
  <dt>-d, --description</dt>
  <dd>新的說明</dd>
  <dt>-f, --force</dt>
  <dd>強制更新，而不進行確認</dd>
</dl>

<strong>範例</strong>：

將存取群組 `example_group` 重新命名為 `hello_world_group`：

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

### ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

刪除存取群組

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
  <dt>-r, --recursive</dt>
  <dd>刪除存取群組及其成員</dd>
</dl>

<strong>範例</strong>：

刪除存取群組 `example_group`：

```
ibmcloud iam access-group-delete example_group --force
```

### ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

列出存取群組中的使用者

```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出存取群組 `example_group` 中的所有使用者：

```
ibmcloud iam access-group-users example_group
```

### ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

將使用者新增至存取群組

```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將使用者 `name@example.com` 新增至存取群組 `example_group`：

```
ibmcloud iam access group-user-add example_group name@example.com
```

### ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

從存取群組移除使用者

```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將使用者 `name@example.com` 從存取群組 `example_group` 移除：

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

### ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

從所有存取群組移除使用者

```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

從所有存取群組移除使用者 `name@example.com`：

```
ibmcloud iam access-group-user-purge name@example.com -f
```

### ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

列出存取群組中的服務 ID

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出存取群組 `example_group` 中的所有服務 ID：

```
ibmcloud iam access-group-service-ids example_group
```

### ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

將服務 ID 新增至存取群組

```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將服務 ID `example-service` 新增至存取群組 `example_group`：

```
ibmcloud iam access-group-service-id-add example_group example-service
```

### ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

從存取群組移除服務 ID

```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

將服務 ID `example-service` 從存取群組 `example_group` 移除：

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

### ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

從所有存取群組移除服務 ID

```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>刪除而不進行確認</dd>
</dl>

<strong>範例</strong>：

從所有存取群組移除服務 ID `example-service`：

```
ibmcloud iam access-group-service-id-purge example --force
```

### ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

列出存取群組的原則

```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

列出存取群組 `example_group` 的所有原則：

```
ibmcloud iam access-group-policies example_group
```

### ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

顯示存取群組原則的詳細資料

```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
</dl>

<strong>範例</strong>：

顯示存取群組 `example_group` 之原則 `51b9717e-76b0-4f6a-bda7-b8132431f926` 的詳細資料：

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

### ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

建立存取群組原則

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--file</dt>
  <dd>原則定義的 JSON 檔案</dd>
  <dt>-roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-name</dt>
  <dd>原則定義的服務名稱。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>原則定義之服務實例的 GUID。此選項與 '--file' 不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource-type</dt>
  <dd>原則定義的資源類型。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource</dt>
  <dd>原則定義的資源。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>-resource-group-id</dt>
  <dd>資源群組的 ID。此選項與 '--file' 及 '--resource-group-name' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

從 JSON 檔建立存取群組原則：

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

針對 `us-south` 地區中 GUID 為 `d161aeea-fd02-40f8-a487-df1998bd69a9` 之 `sample-service` 實例的資源 `key123`，將 `Editor` 角色授與給 `name@example.com`：
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 之資源群組的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

更新存取群組原則

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>--file</dt>
  <dd>原則定義的 JSON 檔案</dd>
  <dt>--roles</dt>
  <dd>原則定義的角色名稱。針對特定服務所支援的角色，執行 'ibmcloud iam roles --service SERVICE_NAME'。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-name</dt>
  <dd>原則定義的服務名稱。此選項與 '--file' 不能同時使用。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>原則定義之服務實例的 GUID。此選項與 '--file' 不能同時使用。</dd>
  <dt>-region</dt>
  <dd>原則定義的地區。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource-type</dt>
  <dd>原則定義的資源類型。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource</dt>
  <dd>原則定義的資源。此選項與 '--file' 不能同時使用。</dd>
  <dt>-resource-group-name</dt>
  <dd>資源群組的名稱。此選項與 '--file' 及 '--resource-group-id' 不能同時使用。</dd>
  <dt>-resource-group-id</dt>
  <dd>資源群組的 ID。此選項與 '--file' 及 '--resource-group-name' 不能同時使用。</dd>
</dl>

<strong>範例</strong>：

以原則 JSON 檔案中的原則來更新存取群組原則：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

更新存取群組原則，以針對所有 `sample-service` 資源，將 `Administrator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

更新存取群組原則，以針對 `us-south` 地區中 GUID 為 `d161aeea-fd02-40f8-a487-df1998bd69a9` 之 `sample-service` 實例的資源 `key123`，將 `Editor` 角色授與給 `name@example.com`：
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

更新存取群組原則，以針對 ID 為 `dda27e49d2a1efca58083a01dfde18f6` 的資源群組，將 `Operator` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

更新存取群組原則，以針對資源群組 `sample-resource-group` 的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

更新存取群組原則，以針對具有 ID `dda27e49d2a1efca58083a01dfde18f6` 的資源群組的成員，將 `Viewer` 角色授與給 `example_group`：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

刪除存取群組原則

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>強制刪除，而不進行確認</dd>
</dl>

<strong>範例</strong>：

刪除存取群組 `example_group` 的原則 `51b9717e-76b0-4f6a-bda7-b8132431f926`：
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
