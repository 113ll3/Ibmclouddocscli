---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-31"

keywords: cli, cloud foundry enterprise environment, cfee, ibmcloud cfee, cfee environment, cfee instance, target user, list cfee

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 使用 Cloud Foundry Enterprise Environment 服务
{: #ibmcloud_commands_cfee}

通过 {{site.data.keyword.cfee_full}} (CFEE)，您可以按需实例化多个隔离的企业级 Cloud Foundry 平台。IBM Cloud Foundry Enterprise 服务实例在 {{site.data.keyword.cloud_notm}} 中您自己的帐户下运行。环境部署在隔离的硬件（Kubernetes 集群）上。您拥有对环境的完全控制权，包括访问控制、容量、版本更新、资源使用和监视。

使用以下命令可管理 CFEE 环境、组织、空间、用户和角色。
{: shortdesc}

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

列出 CFEE 环境：
```
ibmcloud cfee environments
```
{: codeblock}

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

显示 CFEE 环境的详细信息：
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
{: codeblock}

显示 CFEE 环境 `env_example` 的标识：
```
ibmcloud cfee environment env_example --id
```
{: codeblock}

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

列出所有组织：
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
{: codeblock}

列出 CFEE 环境 `env_example` 的所有组织：
```
ibmcloud cfee orgs --env env_example
```
{: codeblock}

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

显示组织的详细信息：
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
{: codeblock}

显示 CFEE 环境 `env_example` 的 CFEE 组织 `org_example` 的详细信息：
```
ibmcloud cfee org org_example --env env_example
```
{: codeblock}

显示 CFEE 组织 `org_example` 的 GUID：
```
ibmcloud cfee org org_example --guid
```
{: codeblock}

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

创建组织：
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
{: codeblock}

创建 CFEE 环境 `env_example` 的 CFEE 组织 `org_example`：
```
ibmcloud cfee org-create org_example --env env_example
```
{: codeblock}

创建配额为 `quote_example` 的 CFEE 组织 `org_example`：
```
ibmcloud cfee org org-create org_example --quota quota_example
```
{: codeblock}

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

删除组织：
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
{: codeblock}

删除 CFEE 环境 `env_example` 的 CFEE 组织 `org_example`：
```
ibmcloud cfee org-delete org_example --env env_example
```
{: codeblock}

删除 CFEE 组织 `org_example` 而不确认：
```
ibmcloud cfee org org-delete org_example -f
```
{: codeblock}

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

按角色显示指定组织中的用户：
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
{: codeblock}

显示 CFEE 环境 `env_example` 的 CFEE 组织 `org_example` 中的用户：
```
ibmcloud cfee org-users org_example --env env_example
```
{: codeblock}

列出 CFEE 组织 `org_example` 中的所有用户：
```
ibmcloud cfee org-users org_example -a
```
{: codeblock}

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

向用户分配组织角色（必须是组织管理者）
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
   <dd>要将此用户分配到的组织角色的名称。例如：
<ul>
   <li>OrgManager：此角色可以邀请和管理用户，选择并更改套餐，以及设置花费限制。</li>
   <li>BillingManager：此角色可以创建和管理计费帐户和付款信息。</li>
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
{: codeblock}

将角色 `BillingManager` 分配给 CFEE 环境 `env_example` 的组织 `org_example` 中的用户 `test@example.com`：
```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

除去用户的组织角色（仅限组织管理者或用户自己）
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
   <dd>要将此用户从中除去的组织角色的名称。例如：
<ul>
   <li>OrgManager：此角色可以邀请和管理用户，选择并更改套餐，以及设置花费限制。</li>
   <li>BillingManager：此角色可以创建和管理计费帐户和付款信息。</li>
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
{: codeblock}

从 CFEE 环境 `env_example` 的组织 `org_example` 中除去用户 `test@example.com` 的角色 `BillingManager`：
```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

列出所有空间：
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

列出所有空间：
```
ibmcloud cfee spaces
```
{: codeblock}

列出组织 `org_example` 和 CFEE 环境 `env_example` 的所有空间
```
ibmcloud cfee spaces -o org_example --env env_example
```
{: codeblock}

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
   <dd>检索并显示空间的 GUID。将禁止空间的所有其他输出。</dd>
   <dt>-o, --org ORG</dt>
   <dd>组织名称。如果未指定，将缺省为当前组织。</dd>
   <dt>--security-group-rules</dt>
   <dd>检索与空间关联的所有安全组的规则。</dd>
  </dl>

<strong>示例</strong>：

显示名为 `space_example` 的空间的详细信息：
```
ibmcloud cfee space space_example
```
{: codeblock}

检索并显示空间 `space_example` 的 GUID：
```
ibmcloud cfee space space_example --guid
```
{: codeblock}

显示与空间 `space_example` 关联的所有安全组的规则：
```
ibmcloud cfee space space_example --security-group-rules
```
{: codeblock}

显示空间 `space_example`、组织 `org_example` 和 CFEE 环境 `env_example` 的详细信息：
```
ibmcloud cfee space space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

创建空间：
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

创建名为 `space_example` 的空间：
```
ibmcloud cfee space-create space_example
```
{: codeblock}

在 CFEE 环境 `env_example` 中的组织 `org_example` 下，创建名为 `space_example` 的空间：
```
ibmcloud cfee space-create space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

重命名空间：
```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>OLD_NAME（必需）</dt>
   <dd>要重命名的空间的旧名称。</dd>
   <dt>NEW_NAME（必需）</dt>
   <dd>要重命名的空间的新名称。</dd>
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
{: codeblock}

将组织 `org_example` 和 CFEE 环境 `env_example` 下的空间 `space_example` 重命名为 `new_pace_example`：
```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

删除空间：
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
{: codeblock}

删除组织 `org_example` 和 CFEE 环境 `env_example` 下的空间 `space_example` 而不确认：
```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```
{: codeblock}

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
   <dd>要将此用户分配到的空间角色的名称。例如：
<ul>
   <li>SpaceManager：此角色可以邀请和管理用户，以及启用空间的功能。</li>
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
{: codeblock}

为环境 `env_example` 下的组织 `org_example` 和空间 `space_example` 的用户 `test@example.com` 分配 `SpaceManager` 角色：
```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
   <dd>要将此用户从中除去的空间角色的名称。例如：
<ul>
   <li>SpaceManager：此角色可以邀请和管理用户，以及启用空间的功能。</li>
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
{: codeblock}

除去环境 `env_example` 下组织 `org_example` 和空间 `space_example` 的用户 `test@example.com` 的 `SpaceManager` 角色：
```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
{: codeblock}

获取组织 `org_example` 和环境 `env_example` 下当前用户的所有空间角色：
```
ibmcloud cfee space-roles org_example --env env_example
```
{: codeblock}

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
{: codeblock}

显示空间 `space_example`、组织 `org_example` 和环境 `env_example` 中的所有用户：
```
ibmcloud cfee space-users org_example space_example --env env_example
```
{: codeblock}

## ibmcloud cfee create
{: #ibmcloud_cfee_create}

请求创建 Cloud Foundry Enterprise Environment 实例：
```
ibmcloud cfee create [-n, --name NAME] [--location LOCATION] [--cells CELLS] [--virtual-dedicated-hardware] [--private-access] [--private-vlan ID, --public-vlan ID] [--plan ID] [-c PARAMETERS_AS_JSON]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-n, --name NAME（必需）</dt>
  <dd>指定 CFEE 的名称。名称必须不超过 24 个字符，以字母开头，并且仅包含字母数字字符、“-”、“_”和“.”。</dd>
  <dt>--location LOCATION（必需）</dt>
  <dd>指定要将此 CFEE 供应到的数据中心（例如，dal10）。要查找可用的数据中心，请运行“ibmcloud cfee create-locations”。</dd>
  <dt>--cells CELLS</dt>
  <dd>指定此 CFEE 的单元数。缺省值为 2，最小值为 1。在一个单元的 CFEE 中，无法获得高可用性。</dd>
  <dt>--private-access</dt>
  <dd>作为 CFEE 的一部分供应的 PostgreSQL 数据库的特定网络访问类型。仅当帐户为 VRF 且启用了服务端点时，才可设置此标志。如果设置了此标志，那么将使用专用访问端点。</dd>
  <dt>--virtual-dedicated-hardware</dt>
  <dd>工作程序节点通过专用硬件在帐户专用的基础架构上进行托管。基础架构资源（例如，系统管理程序和物理硬件）通过共享硬件与其他 IBM 客户共享，但每个工作程序节点对您来说都是单租户。如果未设置此标志，那么“Shared”是缺省值。使用“dedicated”工作程序会产生额外的成本。</dd>
  <dt>--private-vlan ID</dt>
  <dd>指定专用 VLAN 的标识。缺省情况下，将使用一组可用 VLAN 或为您创建一对 VLAN。</dd>
  <dt>--public-vlan ID</dt>
  <dd>指定公用 VLAN 的标识。缺省情况下，将使用一组可用 VLAN 或为您创建一对 VLAN。</dd>
  <dt>--plan ID</dt>
  <dd>指定套餐的标识。缺省情况下，会使用标准套餐。</dd>
  <dt>-c PARAMETERS_AS_JSON</dt>
  <dd>包含特定于 API 的配置参数的有效 JSON 对象，以内联方式或文件形式提供。有关受支持的配置参数的列表，请参阅 https://cloud.ibm.com/apidocs/cfaas#provision-new-cfee-environment 以获取特定目录条目。此标志对于供应多专区 CFEE 是必需的。注：这将忽略其他所有标志，并且 CLI 命令会处理 resource_group_id、access_token 和 refresh_token 字段。</dd>
</dl>

<strong>示例</strong>：

在 `dal10` 中创建名为 `test-cfee` 的实例：
```
ibmcloud cfee create test-cfee dal10
```

在 `dal10` 中创建具有 `4` 个单元且名为 `test-cfee` 的 `dedicated` 实例：
```
ibmcloud cfee create test-cfee dal10 --cells 4 --isolation dedicated
```

## ibmcloud cfee create-locations
{: #ibmcloud_cfee_create_locations}

请求获取目标区域的可用数据中心列表
```
ibmcloud cfee create-locations [--output FORMAT]
```
{: codeblock}

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--output FORMAT</dt>
  <dd>指定输出格式，目前仅支持 JSON。</dd>
</dl>

## ibmcloud cfee create-permission-get
{: #ibmcloud_cfee_create_permission_get}

检查用户是否具有创建 CFEE 实例所需的所有许可权。该命令会检查目标用户的以下访问策略：CFEE 服务的编辑者角色、Kubernetes Service 的管理员角色、Cloud Object Storage 服务的平台编辑者角色和服务访问管理者角色，以及当前组织中用于供应 Compose for PostgreSQL 的当前空间的开发者角色

```
ibmcloud cfee create-permission-get USER_NAME [-ag, --access-group GROUP_NAME] [--output FORMAT]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
  <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>用户的名称。</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>要在其中检查许可权的访问组的名称。缺省访问组为“cfee-provision-access-group”。</dd>
   <dt>--output FORMAT</dt>
   <dd>指定许可权输出格式，现在仅支持 JSON。</dd>
  </dl>
  
<strong>示例</strong>：

检查用户 `name@example.com` 的 CFEE 创建许可权：
```
ibmcloud cfee create-permission-get name@example.com
```
{: codeblock}

在访问组 `test-access-group` 中检查用户 `name@example.com` 的 CFEE 创建许可权：
```
ibmcloud cfee create-permission-get name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-permission-set
{: #ibmcloud_cfee_create_permission_set}

授予用户创建 CFEE 实例所需的所有许可权。该命令会为目标用户创建以下访问策略：CFEE 服务的编辑者角色、Kubernetes Service 的管理员角色、Cloud Object Storage 服务的平台编辑者角色和服务访问管理者角色，以及当前组织中用于供应 Compose for PostgreSQL 的当前空间的开发者角色

```
ibmcloud cfee create-permission-set USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
  <dl>
   <dt>USER_NAME（必需）</dt>
   <dd>用户的名称。</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>要在其中授予许可权的访问组的名称。缺省访问组为“cfee-provision-access-group”。</dd>
  </dl>
  
<strong>示例</strong>：

通过缺省访问组向用户 `name@example.com` 授予 CFEE 创建许可权：
```
ibmcloud cfee create-permission-set name@example.com
```
{: codeblock}

通过访问组 `test-access-group` 向用户 `name@example.com` 授予 CFEE 创建许可权：
```
ibmcloud cfee create-permission-set name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-status
{: #ibmcloud_cfee_create_status}

检查 CFEE 实例的供应状态：
```
ibmcloud cfee create-status NAME or ID [--poll] [--output FORMAT]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>NAME or ID（必需）</dt>
   <dd>CFEE 实例的名称或标识。</dd>
   <dt>--poll</dt>
   <dd>指定是否要重复此调用来进行轮询，直到处于稳定状态。</dd>
   <dt>--output FORMAT</dt>
   <dd>指定状态输出格式，现在仅支持 JSON。</dd>
  </dl>

## ibmcloud cfee monitoring-enable
{: #ibmcloud_cfee_monitoring-enable}

启用对目标 CFEE 环境的监视：
```
ibmcloud cfee monitoring-enable
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
  </dl>

## ibmcloud cfee monitoring-disable
{: #ibmcloud_cfee_monitoring-disable}

禁用对目标 CFEE 环境的监视：
```
ibmcloud cfee monitoring-disable
```
{: codeblock}

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
  </dl>

## ibmcloud cfee monitoring-status
{: #ibmcloud_cfee_monitoring-status}

检查目标 CFEE 环境中最近的监视启用/禁用操作的状态：
```
ibmcloud cfee monitoring-status [--poll]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>--poll</dt>
   <dd>指定是否要重复此调用来进行轮询，直到处于稳定状态</dd>
  </dl>
