---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cloud Foundry Enterprise Environment (CFEE)（測試版）
{: #ibmcloud_commands_cfee}

請使用下列指令管理 CFEE 組織、空間、使用者和角色。
{: shortdesc}

<table summary="管理 Cloud Foundry Enterprise Environment（實驗性）">
<thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 <td>[ibmcloud cfee orgs](cli_cfee.html#ibmcloud_cfee_orgs)</td>
 <td>[ibmcloud cfee org](cli_cfee.html#ibmcloud_cfee_org)</td>
 <td>[ibmcloud cfee org-create](cli_cfee.html#ibmcloud_cfee_org_create)</td>
 </tr>
 <tr>
 <td>[ibmcloud cfee org-delete](cli_cfee.html#ibmcloud_cfee_org_delete)</td>
 <td>[ibmcloud cfee org-users](cli_cfee.html#ibmcloud_cfee_org_users)</td>
 <td>[ibmcloud cfee org-role-set](cli_cfee.html#ibmcloud_cfee_org_role_set)</td>
 <td>[ibmcloud cfee org-role-unset](cli_cfee.html#ibmcloud_cfee_org_role_unset)</td>
 <td>[ibmcloud cfee spaces](cli_cfee.html#ibmcloud_cfee_spaces)</td>
 </tr>
<tr>
 <td>[ibmcloud cfee space](cli_cfee.html#ibmcloud_cfee_space)</td>
 <td>[ibmcloud cfee space-create](cli_cfee.html#ibmcloud_cfee_space_create)</td>
 <td>[ibmcloud cfee space-rename](cli_cfee.html#ibmcloud_cfee_space_rename)</td>
 <td>[ibmcloud cfee space-delete](cli_cfee.html#ibmcloud_cfee_space_delete)</td>
 <td>[ibmcloud cfee space-role-set](cli_cfee.html#ibmcloud_cfee_space_role_set)</td>
 </tr>
 <tr>

 <td>[ibmcloud cfee space-role-unset](cli_cfee.html#ibmcloud_cfee_space_role_unset)</td>
 <td>[ibmcloud cfee space-roles](cli_cfee.html#ibmcloud_cfee_space_roles)</td>
 <td>[ibmcloud cfee space-users](cli_cfee.html#ibmcloud_cfee_space_users)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

列出 CFEE 環境。

```
ibmcloud cfee environments
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

顯示 CFEE 環境的詳細資料。

```
ibmcloud cfee environment NAME [--id]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>NAME（必要）</dt>
   <dd>要顯示之環境的名稱。</dd>
   <dt>--id</dt>
   <dd>僅顯示 ID</dd>
  </dl>

<strong>範例</strong>：

顯示 CFEE 環境 `env_example` 的詳細資料：

```
ibmcloud cfee environment env_example
```

顯示 CFEE 環境 `env_example` 的 ID：

```
ibmcloud cfee environment env_example --id
```

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

列出所有組織

```
ibmcloud cfee orgs [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
  </dl>

<strong>範例</strong>：

列出所有組織：

```
ibmcloud cfee orgs
```

列出 CFEE 環境 `env_example` 的所有組織：

```
ibmcloud cfee orgs --env env_example
```

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

顯示組織的詳細資料

```
ibmcloud cfee org ORG [--guid] [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>ORG（必要）</dt>
   <dd>組織的名稱。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
   <dt>--guid</dt>
   <dd>只顯示組織 GUID，會抑制組織的所有其他輸出。</dd>
  </dl>

<strong>範例</strong>：

顯示 CFEE 組織 `org_example` 的詳細資料：

```
ibmcloud cfee org org_example
```

顯示 CFEE 環境 `env_example` 的 CFEE 組織 `org_example` 的詳細資料：

```
ibmcloud cfee org org_example --env env_example
```

顯示 CFEE 組織 `org_example` 的 GUID：

```
ibmcloud cfee org org_example --guid
```

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

建立組織

```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>ORG（必要）</dt>
   <dd>所要建立之組織的名稱。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>要指派給新建立組織的配額（如果未指定，則使用預設配額）。</dd>
  </dl>

<strong>範例</strong>：

建立 CFEE 組織 `org_example`：

```
ibmcloud cfee org-create org_example
```

建立 CFEE 環境 `env_example` 的 CFEE 組織 `org_example`：

```
ibmcloud cfee org-create org_example --env env_example
```

建立具有配額 `quota_example` 的 CFEE 組織 `org_example`：

```
ibmcloud cfee org org-create org_example --quota quota_example
```

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

刪除組織

```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>ORG（必要）</dt>
   <dd>所要刪除之組織的名稱。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
   <dt>-f, --force</dt>
   <dd>強制刪除，而不進行確認</dd>
  </dl>

<strong>範例</strong>：

刪除 CFEE 組織 `org_example`：

```
ibmcloud cfee org-delete org_example
```

刪除 CFEE 環境 `env_example` 的 CFEE 組織 `org_example`：

```
ibmcloud cfee org-delete org_example --env env_example
```

刪除 CFEE 組織 `org_example` 而不進行確認：

```
ibmcloud cfee org org-delete org_example -f
```

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

依角色顯示指定組織中的使用者。

```
ibmcloud cfee org-users ORG [-a, --all] [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>ORG（必要）</dt>
   <dd>組織的名稱。</dd>
   <dt>-a, --all</dt>
   <dd>列出指定組織中的所有使用者。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
  </dl>

<strong>範例</strong>：

顯示 CFEE 組織 `org_example` 中的使用者：

```
ibmcloud cfee org-users org_example
```

顯示 CFEE 環境 `env_example` 的 CFEE 組織 `org_example` 中的使用者：

```
ibmcloud cfee org-users org_example --env env_example
```

列出 CFEE 組織 `org_example` 中的所有使用者：

```
ibmcloud cfee org-users org_example -a
```

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

將組織角色指派給使用者（需要組織管理員）。

```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>USER_EMAIL（必要）</dt>
   <dd>所指派之使用者的電子郵件。</dd>
   <dt>ORG（必要）</dt>
   <dd>獲指派此使用者之組織的名稱。</dd>
   <dt>ROLE（必要）</dt>
   <dd>獲指派此使用者之組織角色的名稱。例如：
   <ul>
   <li>OrgManager：此角色可以邀請和管理使用者、選取和變更方案，以及設定消費限制。</li>
   <li>BillingManager：此角色可以建立和管理計費帳戶及付款資訊。</li>
   <li>OrgAuditor：此角色具有組織資訊和報告的唯讀權。</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
  </dl>

<strong>範例</strong>：

在組織 `org_example` 中，將角色 `BillingManager` 指派給使用者 `test@exmaple.com`：

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```

在 CFEE 環境 `env_example` 的組織 `org_example` 中，將角色 `BillingManager` 指派給使用者 `test@exmaple.com`：

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

從使用者移除組織角色（僅限組織管理員或使用者自己）。

```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>USER_EMAIL（必要）</dt>
   <dd>所移除之使用者的電子郵件。</dd>
   <dt>ORG（必要）</dt>
   <dd>從中移除此使用者之組織的名稱。</dd>
   <dt>ROLE（必要）</dt>
   <dd>從中移除此使用者之組織角色的名稱。例如：
   <ul>
   <li>OrgManager：此角色可以邀請和管理使用者、選取和變更方案，以及設定消費限制。</li>
   <li>BillingManager：此角色可以建立和管理計費帳戶及付款資訊。</li>
   <li>OrgAuditor：此角色具有組織資訊和報告的唯讀權。</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
  </dl>

<strong>範例</strong>：

從組織 `org_example`，移除使用者 `test@exmaple.com` 的角色 `BillingManager`：

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```

從 CFEE 環境 `env_example` 的組織 `org_example`，移除使用者 `test@exmaple.com` 的角色 `BillingManager`：

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

列出所有空間

```
ibmcloud cfee spaces [-o,--org ORG] [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>組織名稱。如果未指定，則預設為現行組織。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
  </dl>

<strong>範例</strong>：

列出所有空間

```
ibmcloud cfee spaces
```

列出組織 `org_example` 和 CFEE 環境 `env_example` 的所有空間。

```
ibmcloud cfee spaces -o org_example --env env_example
```

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

顯示指定空間的資訊。

```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>SPACE（必要）</dt>
   <dd>要顯示之空間的名稱。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
   <dt>--guid</dt>
   <dd>擷取並顯示給定空間的 GUID。會抑制空間的所有其他輸出。</dd>
   <dt>-o, --org ORG</dt>
   <dd>組織名稱。如果未指定，則預設為現行組織。</dd>
   <dt>--security-group-rules</dt>
   <dd>擷取所有與空間相關聯的安全群組的規則。</dd>
  </dl>

<strong>範例</strong>：

顯示空間 `space_example` 的資訊：

```
ibmcloud cfee space space_example
```

擷取並顯示空間 `space_example` 的 GUID：

```
ibmcloud cfee space space_example --guid
```

顯示與空間 `space_example` 相關聯的所有安全群組的規則：

```
ibmcloud cfee space space_example --security-group-rules
```

顯示組織 `org_example` 和 CFEE 環境 `env_example` 的空間 `space_example` 資訊：

```
ibmcloud cfee space space_example -o org_example --env env_example
```

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

建立新的空間

```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>SPACE（必要）</dt>
   <dd>正在建立的空間名稱。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
   <dt>-o, --org ORG</dt>
   <dd>組織名稱。如果未指定，則預設為現行組織。</dd>
  </dl>

<strong>範例</strong>：

建立新的空間 `space_example`：

```
ibmcloud cfee space-create space_example
```

在組織 `org_example` 和 CFEE 環境 `env_example` 下，建立新的空間 `space_example`：

```
ibmcloud cfee space-create space_example -o org_example --env env_example
```

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

重新命名空間

```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>OLD_NAME（必要）</dt>
   <dd>要重新命名之空間的舊名稱。</dd>
   <dt>NEW_NAME（必要）</dt>
   <dd>空間重新命名後的新名稱。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
   <dt>-o, --org ORG</dt>
   <dd>組織名稱。如果未指定，則預設為現行組織。</dd>
  </dl>

<strong>範例</strong>：

將空間 `space_example` 重新命名為 `new_pace_example`：

```
ibmcloud cfee space-rename space_example new_pace_example
```

在組織 `org_example` 和 CFEE 環境 `env_example` 下，將空間 `space_example` 重新命名為 `new_pace_example`：

```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

刪除空間

```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>SPACE（必要）</dt>
   <dd>要刪除之空間的名稱。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
   <dt>-f, --force</dt>
   <dd>強制刪除，而不確認。</dd>
   <dt>-o, --org ORG</dt>
   <dd>組織名稱。如果未指定，則預設為現行組織。</dd>
  </dl>

<strong>範例</strong>：

刪除空間 `space_example`：

```
ibmcloud cfee space-delete space_example
```

在組織 `org_example` 和 CFEE 環境 `env_example` 下，刪除空間 `space_example`，而不進行確認：

```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

將空間角色指派給使用者。

```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>USER_EMAIL（必要）</dt>
   <dd>所指派之使用者的電子郵件。</dd>
   <dt>ORG（必要）</dt>
   <dd>獲指派此使用者之組織的名稱。</dd>
   <dt>SPACE（必要）</dt>
   <dd>獲指派此使用者之空間的名稱。</dd>
   <dt>ROLE（必要）</dt>
   <dd>獲指派此使用者之空間角色的名稱。例如：
   <ul>
   <li>SpaceManager：此角色可以邀請和管理使用者，以及啟用給定空間的特性。</li>
   <li>SpaceDeveloper：此角色可以建立和管理應用程式及服務，以及查看日誌和報告。</li>
   <li>SpaceAuditor：此角色可以檢視空間的日誌、報告和設定。</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
  </dl>

<strong>範例</strong>：

將使用者 `test@exmaple.com` 指派到組織 `org_example` 和空間 `space_example`，作為 `SpaceManager` 角色：

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```

將使用者 `test@exmaple.com` 指派到組織 `org_example` 和空間 `space_example`，在環境 `env_example` 下作為 `SpaceManager` 角色：

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

移除使用者的空間角色。

```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>USER_EMAIL（必要）</dt>
   <dd>所移除之使用者的電子郵件。</dd>
   <dt>ORG（必要）</dt>
   <dd>從中移除此使用者之組織的名稱。</dd>
   <dt>SPACE（必要）</dt>
   <dd>從中移除此使用者之空間的名稱。</dd>
   <dt>ROLE（必要）</dt>
   <dd>從中移除此使用者之空間角色的名稱。例如：
   <ul>
   <li>SpaceManager：此角色可以邀請和管理使用者，以及啟用給定空間的特性。</li>
   <li>SpaceDeveloper：此角色可以建立和管理應用程式及服務，以及查看日誌和報告。</li>
   <li>SpaceAuditor：此角色可以檢視空間的日誌、報告和設定。</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
  </dl>

<strong>範例</strong>：

從組織 `org_example` 和空間 `space_example`，移除使用者 `test@exmaple.com` 的 `SpaceManager` 角色：

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```

從組織 `org_example` 和空間 `space_example`，移除使用者 `test@exmaple.com` 在環境 `env_example` 下的 `SpaceManager` 角色：

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

取得現行使用者在特定組織下的所有空間角色。

```
ibmcloud cfee space-roles ORG [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>ORG（必要）</dt>
   <dd>組織的名稱。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
  </dl>

<strong>範例</strong>：

取得現行使用者在組織 `org_example` 下的所有空間角色：

```
ibmcloud cfee space-roles org_example
```

取得現行使用者在組織 `org_example` 和環境 `env_example` 下的所有空間角色：

```
ibmcloud cfee space-roles org_example --env env_example
```

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

依角色顯示指定空間中的使用者。

```
ibmcloud cfee space-users ORG SPACE [--env ENV]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
  <dl>
   <dt>ORG（必要）</dt>
   <dd>組織的名稱。</dd>
   <dt>SPACE（必要）</dt>
   <dd>空間的名稱。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 環境名稱。如果未指定，則預設為現行 CFEE 環境。</dd>
  </dl>

<strong>範例</strong>：

顯示空間 `space_example` 及組織 `org_example` 中的所有使用者：

```
ibmcloud cfee space-users org_example space_example
```

顯示空間 `space_example`、組織 `org_example` 和環境 `env_example` 中的所有使用者：

```
ibmcloud cfee space-users org_example space_example --env env_example
```
