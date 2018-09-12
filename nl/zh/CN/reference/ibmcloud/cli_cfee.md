---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cloud Foundry Enterprise Environments (CFEE) (beta)
{: #ibmcloud_commands_cfee}

使用以下命令可管理 CFEE 组织、空间、用户和角色。
{: shortdesc}

<table summary="管理 Cloud Foundry Enterprise Environments（试验性）">
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

列出 CFEE 环境。

```
ibmcloud cfee environments
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

显示 CFEE 环境的详细信息

```
ibmcloud cfee environment NAME [--id]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>NAME（必需）</dt>
   <dd>要显示的环境的名称。</dd>
   <dt>--id</dt>
   <dd>仅显示标识</dd>
  </dl>

<strong>示例</strong>：

显示 CFEE 环境 `env_example` 的详细信息：

```
ibmcloud cfee environment env_example
```

显示 CFEE 环境 `env_example` 的标识：

```
ibmcloud cfee environment env_example --id
```

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

列出所有组织

```
ibmcloud cfee orgs [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
  </dl>

<strong>示例</strong>：

列出所有组织：

```
ibmcloud cfee orgs
```

列出 CFEE 环境 `env_example` 的所有组织：

```
ibmcloud cfee orgs --env env_example
```

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

显示组织的详细信息

```
ibmcloud cfee org ORG [--guid] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>ORG（必需）</dt>
   <dd>组织的名称。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
   <dt>--guid</dt>
   <dd>仅显示组织 GUID，禁止组织的所有其他输出。</dd>
  </dl>

<strong>示例</strong>：

显示 CFEE 组织 `org_example` 的详细信息：

```
ibmcloud cfee org org_example
```

显示 CFEE 环境 `env_example` 的 CFEE 组织 `org_example` 的详细信息：

```
ibmcloud cfee org org_example --env env_example
```

显示 CFEE 组织 `org_example` 的 GUID：

```
ibmcloud cfee org org_example --guid
```

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

创建组织

```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>ORG（必需）</dt>
   <dd>要创建的组织的名称。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>要分配给新创建的组织的配额（如果未指定，将使用缺省配额）</dd>
  </dl>

<strong>示例</strong>：

创建 CFEE 组织 `org_example`：

```
ibmcloud cfee org-create org_example
```

创建 CFEE 环境 `env_example` 的 CFEE 组织 `org_example`：

```
ibmcloud cfee org-create org_example --env env_example
```

创建配额为 `quote_example` 的 CFEE 组织 `org_example`：

```
ibmcloud cfee org org-create org_example --quota quota_example
```

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

删除组织

```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>ORG（必需）</dt>
   <dd>要删除的组织的名称。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
   <dt>-f, --force</dt>
   <dd>强制删除而不确认</dd>
  </dl>

<strong>示例</strong>：

删除 CFEE 组织 `org_example`：

```
ibmcloud cfee org-delete org_example
```

删除 CFEE 环境 `env_example` 的 CFEE 组织 `org_example`：

```
ibmcloud cfee org-delete org_example --env env_example
```

删除 CFEE 组织 `org_example` 而不确认：

```
ibmcloud cfee org org-delete org_example -f
```

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

按角色显示指定组织中的用户

```
ibmcloud cfee org-users ORG [-a, --all] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>ORG（必需）</dt>
   <dd>组织的名称。</dd>
   <dt>-a, --all</dt>
   <dd>列出指定组织中的所有用户。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
  </dl>

<strong>示例</strong>：

显示 CFEE 组织 `org_example` 中的用户：

```
ibmcloud cfee org-users org_example
```

显示 CFEE 环境 `env_example` 的 CFEE 组织 `org_example` 中的用户：

```
ibmcloud cfee org-users org_example --env env_example
```

列出 CFEE 组织 `org_example` 中的所有用户：

```
ibmcloud cfee org-users org_example -a
```

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

向用户分配组织角色（必须是组织管理员）

```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>USER_EMAIL（必需）</dt>
   <dd>要分配的用户的电子邮件。</dd>
   <dt>ORG（必需）</dt>
   <dd>要将此用户分配到的组织的名称。</dd>
   <dt>ROLE（必需）</dt>
   <dd>要将此用户分配到的组织角色的名称。例如：<ul>
   <li>OrgManager：此角色可以邀请和管理用户，选择并更改套餐，以及设置花费限制。</li>
   <li>BillingManager：此角色可以创建和管理缴费帐户和付款信息。</li>
   <li>OrgAuditor：此角色具有对组织信息和报告的只读访问权。</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
  </dl>

<strong>示例</strong>：

将角色 `BillingManager` 分配给组织 `org_example` 中的用户 `test@example.com`：

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```

将角色 `BillingManager` 分配给 CFEE 环境 `env_example` 的组织 `org_example` 中的用户 `test@example.com`：

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

除去用户的组织角色（仅限组织管理员或用户自己）

```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>USER_EMAIL（必需）</dt>
   <dd>要除去的用户的电子邮件。</dd>
   <dt>ORG（必需）</dt>
   <dd>要将此用户从中除去的组织的名称。</dd>
   <dt>ROLE（必需）</dt>
   <dd>要将此用户从中除去的组织角色的名称。例如：<ul>
   <li>OrgManager：此角色可以邀请和管理用户，选择并更改套餐，以及设置花费限制。</li>
   <li>BillingManager：此角色可以创建和管理缴费帐户和付款信息。</li>
   <li>OrgAuditor：此角色具有对组织信息和报告的只读访问权。</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
  </dl>

<strong>示例</strong>：

从组织 `org_example` 中除去用户 `test@example.com` 的角色 `BillingManager`：

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```

从 CFEE 环境 `env_example` 的组织 `org_example` 中除去用户 `test@example.com` 的角色 `BillingManager`：

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

列出所有空间

```
ibmcloud cfee spaces [-o,--org ORG] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>组织名称。如果未指定，将缺省为当前组织。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
  </dl>

<strong>示例</strong>：

列出所有空间

```
ibmcloud cfee spaces
```

列出组织 `org_example` 和 CFEE 环境 `env_example` 的所有空间

```
ibmcloud cfee spaces -o org_example --env env_example
```

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

显示指定空间的信息

```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>SPACE（必需）</dt>
   <dd>要显示的空间的名称。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
   <dt>--guid</dt>
   <dd>检索并显示给定空间的 GUID。将禁止空间的所有其他输出。</dd>
   <dt>-o, --org ORG</dt>
   <dd>组织名称。如果未指定，将缺省为当前组织。</dd>
   <dt>--security-group-rules</dt>
   <dd>检索与空间关联的所有安全组的规则。</dd>
  </dl>

<strong>示例</strong>：

显示空间 `space_example` 的信息：

```
ibmcloud cfee space space_example
```

检索并显示空间 `space_example` 的 GUID：

```
ibmcloud cfee space space_example --guid
```

显示与空间 `space_example` 关联的所有安全组的规则：

```
ibmcloud cfee space space_example --security-group-rules
```

显示组织 `org_example` 和 CFEE 环境 `env_example` 的空间 `space_example` 的信息：

```
ibmcloud cfee space space_example -o org_example --env env_example
```

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

创建新空间

```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>SPACE（必需）</dt>
   <dd>要创建的空间的名称。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
   <dt>-o, --org ORG</dt>
   <dd>组织名称。如果未指定，将缺省为当前组织。</dd>
  </dl>

<strong>示例</strong>：

创建新空间 `space_example`：

```
ibmcloud cfee space-create space_example
```

在组织 `org_example` 和 CFEE 环境 `env_example` 下创建新空间 `space_example`：

```
ibmcloud cfee space-create space_example -o org_example --env env_example
```

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

重命名空间

```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>OLD_NAME（必需）</dt>
   <dd>要重命名的空间的旧名称。</dd>
   <dt>NEW_NAME（必需）</dt>
   <dd>空间要重命名为的新名称。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
   <dt>-o, --org ORG</dt>
   <dd>组织名称。如果未指定，将缺省为当前组织。</dd>
  </dl>

<strong>示例</strong>：

将空间 `space_example` 重命名为 `new_pace_example`：

```
ibmcloud cfee space-rename space_example new_pace_example
```

将组织 `org_example` 和 CFEE 环境 `env_example` 下的空间 `space_example` 重命名为 `new_pace_example`：

```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

删除空间

```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>SPACE（必需）</dt>
   <dd>要删除的空间的名称。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
   <dt>-f, --force</dt>
   <dd>强制删除而不确认。</dd>
   <dt>-o, --org ORG</dt>
   <dd>组织名称。如果未指定，将缺省为当前组织。</dd>
  </dl>

<strong>示例</strong>：

删除空间 `space_example`：

```
ibmcloud cfee space-delete space_example
```

删除组织 `org_example` 和 CFEE 环境 `env_example` 下的空间 `space_example` 而不确认：

```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

向用户分配空间角色

```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>USER_EMAIL（必需）</dt>
   <dd>要分配的用户的电子邮件。</dd>
   <dt>ORG（必需）</dt>
   <dd>要将此用户分配到的组织的名称。</dd>
   <dt>SPACE（必需）</dt>
   <dd>要将此用户分配到的空间的名称。</dd>
   <dt>ROLE（必需）</dt>
   <dd>要将此用户分配到的空间角色的名称。例如：<ul>
   <li>SpaceManager：此角色可以邀请和管理用户，以及启用给定空间的功能。</li>
   <li>SpaceDeveloper：此角色可以创建和管理应用程序与服务，以及查看日志和报告。</li>
   <li>SpaceAuditor：此角色可以查看空间的日志、报告和设置。</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
  </dl>

<strong>示例</strong>：

为组织 `org_example` 和空间 `space_example` 的用户 `test@example.com` 分配 `SpaceManager` 角色：

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```

为环境 `env_example` 下的组织 `org_example` 和空间 `space_example` 的用户 `test@example.com` 分配 `SpaceManager` 角色：

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

除去用户的空间角色

```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>USER_EMAIL（必需）</dt>
   <dd>要除去的用户的电子邮件。</dd>
   <dt>ORG（必需）</dt>
   <dd>要将此用户从中除去的组织的名称。</dd>
   <dt>SPACE（必需）</dt>
   <dd>要将此用户从中除去的空间的名称。</dd>
   <dt>ROLE（必需）</dt>
   <dd>要将此用户从中除去的空间角色的名称。例如：<ul>
   <li>SpaceManager：此角色可以邀请和管理用户，以及启用给定空间的功能。</li>
   <li>SpaceDeveloper：此角色可以创建和管理应用程序与服务，以及查看日志和报告。</li>
   <li>SpaceAuditor：此角色可以查看空间的日志、报告和设置。</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
  </dl>

<strong>示例</strong>：

除去组织 `org_example` 和空间 `space_example` 的用户 `test@example.com` 的 `SpaceManager` 角色：

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```

除去环境 `env_example` 下组织 `org_example` 和空间 `space_example` 的用户 `test@example.com` 的 `SpaceManager` 角色：

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

获取当前用户在特定组织下的所有空间角色

```
ibmcloud cfee space-roles ORG [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>ORG（必需）</dt>
   <dd>组织的名称。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
  </dl>

<strong>示例</strong>：

获取组织 `org_example` 下当前用户的所有空间角色：

```
ibmcloud cfee space-roles org_example
```

获取组织 `org_example` 和环境 `env_example` 下当前用户的所有空间角色：

```
ibmcloud cfee space-roles org_example --env env_example
```

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

按角色显示指定空间中的用户

```
ibmcloud cfee space-users ORG SPACE [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>ORG（必需）</dt>
   <dd>组织的名称。</dd>
   <dt>SPACE（必需）</dt>
   <dd>空间的名称。</dd>
   <dt>--env ENV</dt>
   <dd>CFEE 环境名称。如果未指定，将缺省为当前的 CFEE 环境。</dd>
  </dl>

<strong>示例</strong>：

显示空间 `space_example` 和组织 `org_example` 中的所有用户：

```
ibmcloud cfee space-users org_example space_example
```

显示空间 `space_example`、组织 `org_example` 和环境 `env_example` 中的所有用户：

```
ibmcloud cfee space-users org_example space_example --env env_example
```
