---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 帐户、用户和组织
 {: #ibmcloud_commands_account}

 使用以下命令可管理帐户、帐户中的用户以及 Cloud Foundry 服务的组织、空间、角色和域证书。
  {: shortdesc}

  <table summary="可用于管理帐户、组织、空间和角色的 ibmcloud 命令。">
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
   </tr>
   </tbody>
   </table>

 ## ibmcloud account orgs
{: #ibmcloud_account_orgs}

列出所有组织

```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>区域名称。列出指定区域中的组织。如果未指定，将缺省为当前区域。如果设置为“all”，将列出所有区域中的组织。</dd>
   <dt>--guid</dt>
   <dd>显示组织的 GUID。此选项与“--output”互斥。</dd>
   <dt>--output FORMAT</dt>
   <dd>指定输出格式，目前仅支持 JSON。此选项与“--guid”互斥。</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>帐户标识。列出给定帐户下的组织。如果未指定，将缺省为当前帐户。如果设置为“all”，将列出所有帐户下的组织。此选项与“--u”互斥。</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>帐户所有者名称。列出给定用户所拥有的帐户下的组织。如果未指定，将缺省为当前帐户。如果设置为“all”，将列出所有帐户下的组织。此选项与“-c”互斥。</dd>
   </dl>

<strong>示例</strong>：

列出区域 `us-south` 中的所有组织并显示 GUID

```
ibmcloud account orgs -r us-south --guid
```

以 JSON 格式列出所有组织

```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

显示指定组织的信息。

```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>ORG_NAME（必需）</dt>
   <dd>组织的名称。</dd>
   <dt>-r REGION</dt>
   <dd>区域名称。如果未指定，将缺省为当前区域。如果设置为“all”，将列出所有区域中给定名称的组织。</dd>
   <dt>--guid</dt>
   <dd>检索并显示给定组织的 GUID。将禁止组织的所有其他输出。此选项与“--output”互斥。</dd>
   <dt>--output REGION</dt>
   <dd>指定输出格式，目前仅支持 JSON。此选项与“--guid”互斥。</dd>
   </dl>

<strong>示例</strong>：

显示组织 `IBM` 的信息并显示 GUID

```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

创建新组织。此操作只能由帐户所有者执行。

```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>ORG_NAME（必需）</dt>
   <dd>要创建的组织的名称。</dd>
   <dt>-f</dt>
   <dd>强制创建而不确认。</dd>
   </dl>

<strong>示例</strong>：

创建名为 `IBM` 的组织。

```
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

将组织从当前区域复制到其他区域。

```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>ORG_NAME（必需）</dt>
   <dd>要复制的现有组织的名称。</dd>
   <dt>REGION_NAME（必需）</dt>
   <dd>托管所复制组织的区域的名称。</dd>
   </dl>

<strong>示例</strong>：

将组织 `myorg` 复制到区域 `eu-gb`：

```
ibmcloud account org-replicate myorg eu-gb
```

## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

重命名组织。此操作只能由组织管理员执行。

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>OLD_ORG_NAME（必需）</dt>
   <dd>要重命名的组织的旧名称。</dd>
   <dt>NEW_ORG_NAME（必需）</dt>
   <dd>组织要重命名为的新名称。</dd>
   </dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

列出所有空间

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>-o ORG_NAME</dt>
   <dd>组织名称。列出指定组织下的空间。如果未指定，将缺省为当前组织。</dd>
   <dt>-r REGION-NAM</dt>
   <dd>区域名称。列出指定区域下的空间。如果未指定，将缺省为当前区域。</dd>
   <dt>--output FORMAT</dt>
   <dd>指定输出格式，目前仅支持 JSON。</dd>
   </dl>

<strong>示例</strong>：

列出所有空间：

```
ibmcloud account spaces
```

以 JSON 格式列出组织 `org_example` 的所有空间：

```
ibmcloud account spaces -o org_example --output JSON
```

## ibmcloud account space
{: #ibmcloud_account_space}

显示指定空间的信息

```
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid | --output FORMAT] [--security-group-rules]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>SPACE_NAME（必需）</dt>
   <dd>要显示的空间的名称。</dd>
   <dt>-o ORG_NAME</dt>
   <dd>组织名称。如果未指定，将缺省为当前组织。</dd>
   <dt>--guid</dt>
   <dd>检索并显示给定空间的 GUID。将禁止空间的所有其他输出。此选项与“--output”互斥。</dd>
   <dt>--output FORMAT</dt>
   <dd>指定输出格式，目前仅支持 JSON。将禁止空间的所有其他输出。此选项与“--guid”互斥。</dd>
   <dt>--security-group-rules</dt>
   <dd>检索与空间关联的所有安全组的规则。</dd>
   </dl>

<strong>示例</strong>：

显示空间 `space_example` 的信息：

```
ibmcloud account space space_example
```

显示空间 `space_example` 的 GUID：

```
ibmcloud account space space_example --guid
```

以 JSON 格式显示空间 `space_example` 的信息：

```
ibmcloud account space space_example --output JSON
```

显示空间 `space_example` 的安全组规则：

```
ibmcloud account space space_example --security-group-rules
```

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

此命令的功能和选项与 [cf create-space ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} 命令的相同。

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


此命令的功能和选项与 [cf rename-space ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} 命令的相同。

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


此命令的功能和选项与 [cf delete-space ![外部链接图标](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} 命令的相同。

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

按角色显示指定组织中的用户。

```
ibmcloud account org-users ORG_NAME [-a]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>ORG_NAME（必需）</dt>
<dd>组织的名称。</dd>
<dt>-a（可选）</dt>
<dd>列出指定组织中的所有用户，但不按角色分组。</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

将用户添加到组织（需要组织管理员）。

```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

从组织除去用户（仅限组织管理员或用户自己）

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>命令选项</strong>：
<dl>
<dt>--force, -f</dt>
<dd>强制删除而不确认。</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

获取当前用户的所有组织角色

```
ibmcloud account org-roles [-u USER_ID]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>-u</dt>
   <dd>用户标识。如果未指定，将缺省为当前用户。</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

向用户分配组织角色。此操作只能由组织管理员执行。

```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>要分配的用户的名称。</dd>
   <dt>ORG_NAME（必需）</dt>
   <dd>要将此用户分配到的组织的名称。</dd>
   <dt>ORG_ROLE（必需）</dt>
   <dd>要将此用户分配到的组织角色的名称。例如：<ul>
   <li>OrgManager：此角色可以邀请和管理用户，选择并更改套餐，以及设置花费限制。</li>
   <li>BillingManager：此角色可以创建和管理缴费帐户和付款信息。</li>
   <li>OrgAuditor：此角色具有对组织信息和报告的只读访问权。</li>
   </ul>
   </dd>
  </dl>

<strong>示例</strong>：

将用户 `Mary` 以 `OrgManager` 角色分配给组织 `IBM`：

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**注**：您可以使用 CLI 设置组织/空间角色，但是如果您想要设置其他许可权，那么必须使用 UI。有关进一步的详细信息，请参阅[分配用户访问权](/docs/iam/assignaccess.html#assignaccess)。<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

除去用户的组织角色。此操作只能由组织管理员执行。

```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>要除去的用户的名称。</dd>
   <dt>ORG_NAME（必需）</dt>
   <dd>要将此用户从中除去的组织的名称。</dd>
   <dt>ORG_ROLE（必需）</dt>
   <dd>要将此用户从中除去的组织角色的名称。例如：<ul>
   <li>OrgManager：此角色可以邀请和管理用户，选择并更改套餐，以及设置花费限制。</li>
   <li>BillingManager：此角色可以创建和管理缴费帐户和付款信息。</li>
   <li>OrgAuditor：此角色具有对组织信息和报告的只读访问权。</li>
   </ul>
   </dd>
    </dl>

<strong>示例</strong>：

从组织 `IBM` 中除去用户 `Mary` 的 `OrgManager` 角色：

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

按角色显示指定空间中的用户。

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>ORG_NAME（必需）</dt>
   <dd>组织的名称。</dd>
   <dt>SPACE_NAME（必需）</dt>
   <dd>空间的名称。</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

向用户分配空间角色。此操作只能由空间管理员执行。

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

   <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>要分配的用户的名称。</dd>
   <dt>ORG_NAME（必需）</dt>
   <dd>要将此用户分配到的组织的名称。</dd>
   <dt>SPACE_NAME（必需）</dt>
   <dd>要将此用户分配到的空间的名称。</dd>
   <dt>SPACE_ROLE（必需）</dt>
   <dd>要将此用户分配到的空间角色的名称。例如：<ul>
   <li>SpaceManager：此角色可以邀请和管理用户，以及启用给定空间的功能。</li>
   <li>SpaceDeveloper：此角色可以创建和管理应用程序与服务，以及查看日志和报告。</li>
   <li>SpaceAuditor：此角色可以查看空间的日志、报告和设置。</li>
   </ul></dd>
    </dl>

<strong>示例</strong>：

将用户 `Mary` 以 `SpaceManager` 角色分配给组织 `IBM` 和空间 `Cloud`：

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

除去用户的空间角色。此操作只能由空间管理员执行。

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

   <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>要除去的用户的名称。</dd>
   <dt>ORG_NAME（必需）</dt>
   <dd>要将此用户从中除去的组织的名称。</dd>
   <dt>SPACE_NAME（必需）</dt>
   <dd>要将此用户从中除去的空间的名称。</dd>
   <dt>SPACE_ROLE（必需）</dt>
   <dd>要将此用户从中除去的空间角色的名称。例如：<ul>
   <li>SpaceManager：此角色可以邀请和管理用户，以及启用给定空间的功能。</li>
   <li>SpaceDeveloper：此角色可以创建和管理应用程序与服务，以及查看日志和报告。</li>
   <li>SpaceAuditor：此角色可以查看空间的日志、报告和设置。</li>
   </ul></dd>
    </dl>


<strong>示例</strong>：

从组织 `IBM` 和空间 `Cloud` 中除去用户 `Mary` 的 `SpaceManager` 角色：

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

列出当前用户的所有帐户

```
ibmcloud account list
```

<strong>先决条件</strong>：端点和登录

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

显示指定组织的帐户（需要组织用户）

```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--guid（可选）</dt>
  <dd>仅显示帐户标识</dd>
</dl>

## ibmcloud account users
{: #ibmcloud_account_users}

显示与帐户关联的用户。此操作只能由帐户所有者执行。

```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

从帐户中除去用户（仅帐户所有者）

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>USER_ID（必填）</dt>
<dd>用户标识</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>帐户标识。如果未指定，缺省值为当前帐户。</dd>
<dt>-f, --force</dt>
<dd>强制删除而不确认。</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

邀请用户加入帐户

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
   <dt>USER_EMAIL（必需）</dt>
   <dd>要邀请的用户的电子邮件。</dd>
   <dt>-o ORG</dt>
   <dd>邀请用户加入的组织</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>组织角色。有效输入为：OrgManager、BillingManager、OrgAuditor 和 OrgUser。如果省略，将设置 OrgUser 角色。</dd>
   <dt>-s SPACE</dt>
   <dd>邀请用户加入的空间</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>空间角色。有效输入为：SpaceManager、SpaceDeveloper 和 SpaceAuditor。</dd>
</dl>

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

向用户重新发送邀请（帐户管理员）

```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
   <dt>USER_EMAIL（必需）</dt>
   <dd>要重新邀请的用户的电子邮件。</dd>
</dl>
