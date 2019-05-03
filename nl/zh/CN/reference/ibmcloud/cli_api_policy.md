---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-29"

keywords: iam, iam access, api keys, service ids, access groups, authorization policy, ibmcloud iam, cli, manage keys, manage service ids, manage iam users cli, iam cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}
{:note: .note}

# 管理 IAM 访问权、API 密钥、服务标识和访问组
{: #ibmcloud_commands_iam}

使用以下命令可管理用户、服务和访问组的 API 密钥、服务标识、访问组和授权策略。
{: shortdesc}

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

列出所有服务标识：
```
ibmcloud iam service-ids [--uuid]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>--uuid</dt>
  <dd>仅显示服务标识的 UUID</dd>
</dl>

<strong>示例</strong>：

列出当前帐户下所有服务标识的 UUID：
```
ibmcloud iam service-ids --uuid
```
{: codeblock}

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

显示服务标识的详细信息：
```
ibmcloud iam service-id (NAME|UUID) [--uuid]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>--uuid</dt>
  <dd>显示服务标识的 UUID</dd>
</dl>

<strong>示例</strong>：

显示服务标识 `sample-test` 的详细信息：
```
ibmcloud iam service-id sample-test
```
{: codeblock}

显示服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的详细信息：
```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

创建服务标识：
```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称</dd>
  <dt>-d, --description</dt>
  <dd>服务标识的描述</dd>
  <dt>--lock</dt>
  <dd>锁定创建的服务标识</dd>
</dl>

<strong>示例</strong>：

创建服务名称为 `sample-test` 且描述为 `hello, world!` 的服务标识：
```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```
{: codeblock}

创建服务名称为 `sample-test` 且描述为 `hello, world!` 的锁定服务标识：
```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```
{: codeblock}

## ibmcloud iam service-id-update
{: #ibmcloud_iam_service_id_update}

更新服务标识：
```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>-n, --name</dt>
  <dd>服务的新名称</dd>
  <dt>-d, --description</dt>
  <dd>服务的新描述</dd>
  <dt>-f, --force</dt>
  <dd>更新而不确认</dd>
</dl>

<strong>示例</strong>：

将服务标识 `sample-test` 重命名为 `sample-test2` 而不确认：
```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```
{: codeblock}

更新服务 `sample-test` 的描述：
```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```
{: codeblock}

使用新描述将服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 重命名为 `sample-test3`：
```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```
{: codeblock}

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

删除服务标识：
```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除服务标识 `sample-teset` 而不确认：
```
ibmcloud iam service-id-delete sample-teset -f
```
{: codeblock}

删除服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`：
```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

锁定服务标识：
```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>-f, --force</dt>
  <dd>锁定而不确认</dd>
</dl>

<strong>示例</strong>：

锁定服务标识 `sample-teset` 而不确认：
```
ibmcloud iam service-id-lock sample-teset -f
```
{: codeblock}

锁定服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`：
```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

解锁服务标识：
```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```
{: codeblock}

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务的名称，与 UUID 互斥</dd>
  <dt>UUID（必填）</dt>
  <dd>服务的 UUID，与 NAME 互斥</dd>
  <dt>-f, --force</dt>
  <dd>解锁而不确认</dd>
</dl>

<strong>示例</strong>：

解锁服务标识 `sample-teset` 而不确认：
```
ibmcloud iam service-id-unlock sample-teset -f
```
{: codeblock}

解锁服务标识 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`：
```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

列出所有 {{site.data.keyword.Bluemix_notm}} 平台 API 密钥：
```
ibmcloud iam api-keys
```
{: codeblock}

<strong>先决条件</strong>：端点和登录

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

创建新的 {{site.data.keyword.cloud_notm}} 平台 API 密钥：
```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

将 {{site.data.keyword.cloud_notm}} CLI 登录与 API 密钥配合使用时，无法使用在 `control.softlayer.com` 上找到的旧 SL API 密钥。 需要升级基础架构通过 [cloud.ibm.com](https://cloud.ibm.com/registration){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") 管理的 {{site.data.keyword.cloud_notm}} 帐户，才能将 {{site.data.keyword.cloud_notm}} CLI 登录与 API 密钥配合使用。
{: note}

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要创建的 API 密钥的名称。</dd>
<dt>-d <i>DESCRIPTION</i>（可选）</dt>
<dd>API 密钥的描述</dd>
<dt>--file <i>FILE</i></dt>
<dd>将 API 密钥信息保存到指定的文件。</dd>
<dt>--lock</dt>
<dd>锁定创建的 API 密钥</dd>
</dl>

<strong>示例</strong>：

创建 API 密钥并将其保存到文件：
```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```
{: codeblock}

创建名称为“test-key”的锁定 API 密钥：
```
ibmcloud iam api-key-create test-key --lock
```
{: codeblock}

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

更新 {{site.data.keyword.Bluemix_notm}} 平台 API 密钥：
```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要更新的 API 密钥的旧名称，与 UUID 互斥</dd>
<dt>UUID（必填）</dt>
<dd>要更新的 API 密钥的 UUID，与 NAME 互斥</dd>
<dt>-n <i>NAME</i>（可选）</dt>
<dd>API 密钥的新名称</dd>
<dt>-d <i>DESCRIPTION</i>（可选）</dt>
<dd>API 密钥的新描述</dd>
</dl>

<strong>示例</strong>：

更新 API 密钥的描述：
```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```
{: codeblock}

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

删除 {{site.data.keyword.Bluemix_notm}} 平台 API 密钥：
```
ibmcloud iam api-key-delete (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要删除的 API 密钥的名称，与 UUID 互斥</dd>
<dt>UUID（必填）</dt>
<dd>要删除的 API 密钥的 UUID，与 NAME 互斥</dd>
<dt>-f, --force</dt>
<dd>强制删除而不确认。</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

锁定平台 API 密钥：
```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要锁定的 API 密钥的名称，与 UUID 互斥</dd>
<dt>UUID（必填）</dt>
<dd>要锁定的 API 密钥的 UUID，与 NAME 互斥</dd>
<dt>-f, --force</dt>
<dd>强制锁定而不确认。</dd>
</dl>

<strong>示例</strong>：

锁定 API 密钥 test-api-key：
```
ibmcloud iam api-key-lock test-api-key
```
{: codeblock}

锁定给定 UUID 的 API 密钥而不确认：
```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}s

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

解锁平台 API 密钥：
```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
<dt>NAME（必需）</dt>
<dd>要解锁的 API 密钥的名称，与 UUID 互斥</dd>
<dt>UUID（必填）</dt>
<dd>要解锁的 API 密钥的 UUID，与 NAME 互斥</dd>
<dt>-f, --force</dt>
<dd>强制解锁而不确认。</dd>
</dl>

<strong>示例</strong>：

解锁 API 密钥 test-api-key：
```
ibmcloud iam api-key-unlock test-api-key
```
{: codeblock}

解锁给定 UUID 的 API 密钥而不确认：
```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

列出服务的所有 API 密钥：
```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>显示服务 API 密钥而不确认</dd>
</dl>

<strong>示例</strong>：

列出服务 `sample-service` 的所有 API 密钥：
```
ibmcloud iam service-api-keys sample-service
```
{: codeblock}

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

列出服务 API 密钥的详细信息：
```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>--uuid</dt>
  <dd>显示服务 API 密钥的 UUID</dd>
  <dt>-f, --force</dt>
  <dd>显示服务 API 密钥而不确认</dd>
</dl>

<strong>示例</strong>：

显示服务 `sample-service` 的服务 API 密钥 `sample-key` 的详细信息：
```
ibmcloud iam service-api-key sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

创建服务 API 密钥：
```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>NAME（必需）</dt>
  <dd>服务标识的名称或新创建的服务 API 密钥的名称</dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-d, --description</dt>
  <dd>API 密钥的描述</dd>
  <dt>--file</dt>
  <dd>将 API 密钥信息保存到指定的文件。</dd>
  <dt>-f, --force</dt>
  <dd>强制创建而不确认</dd>
</dl>

<strong>示例</strong>：

为服务 `sample-service` 创建服务 API 密钥 `sample-key` 而不确认：
```
ibmcloud iam service-api-key-create sample-key sample-service -f
```
{: codeblock}

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

更新服务 API 密钥：
```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-n, --name</dt>
  <dd>服务 API 密钥的新名称</dd>
  <dt>-d, --description</dt>
  <dd>服务 API 密钥的新描述</dd>
  <dt>-f, --force</dt>
  <dd>更新而不确认</dd>
</dl>

<strong>示例</strong>：

将服务 API 密钥 `sample-key` 重命名为 `new-sample-key`：
```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```
{: codeblock}

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

删除服务 API 密钥：
```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除服务标识 `sample-service` 的服务 API 密钥 `sample-key`：
```
ibmcloud iam service-api-key-delete sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

锁定服务 API 密钥：
```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>锁定而不确认</dd>
</dl>

<strong>示例</strong>：

锁定服务标识 `sample-service` 的服务 API 密钥 `sample-key`：
```
ibmcloud iam service-api-key-lock sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

解锁服务 API 密钥：
```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>解锁而不确认</dd>
</dl>

<strong>示例</strong>：

解锁服务标识 `sample-service` 的服务 API 密钥 `sample-key`：
```
ibmcloud iam service-api-key-unlock sample-key sample-service
```
{: codeblock}

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

列出用户 `name@example.com` 的策略：
```
ibmcloud iam user-policies name@example.com
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dl>
<dt>USER_NAME（必需）</dt>
<dd>策略所属的用户名</dd>
</dl>

<strong>示例</strong>：

列出用户 `name@example.com` 的策略：
```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

显示用户策略的详细信息：
```
ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dl>
<dt>USER_NAME（必需）</dt>
<dd>策略所属的用户名</dd>
<dt>POLICY_ID（必需）</dt>
<dd>策略的标识</dd>
</dl>

<strong>示例</strong>：

列出用户 `name@example.com` 的策略 `0bb730daa`：
```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

创建用户策略：
```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dl>
<dt>USER_NAME（必需）</dt>
<dd>策略所属的用户名</dd>
<dt>--file <i>FILE</i>（可选）</dt>
<dd>策略定义的 JSON 文件</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i>（可选）</dt>
<dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行 `ibmcloud iam roles --service SERVICE_NAME`。此选项与 `--file` 互斥。</dd>
<dt>--service-name <i>SERVICE_NAME</i>（可选）</dt>
<dd>策略定义的服务名称，此选项与 `--file` 标志互斥。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i>（可选）</dt>
<dd>策略定义的服务实例的 GUID，此选项与 `--file` 标志互斥。</dd>
<dt>--region <i>REGION</i>（可选）</dt>
<dd>策略定义的区域，此选项与 `--file` 标志互斥。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>（可选）</dt>
<dd>策略定义的资源类型，此选项与 `--file` 标志互斥。</dd>
<dt>--resource <i>RESOURCE</i>（可选）</dt>
<dd>策略定义的资源，此选项与 `--file` 标志互斥。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>（可选）</dt>
<dd>资源组的名称。`*` 表示所有资源组。此选项与 `--file`、`--resource` 和 `--resource-group-id` 标志互斥。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>（可选）</dt>
<dd>资源组的标识。`*` 表示所有资源组。此选项与 `--file`、`--resource` 和 `--resource-group-name` 标志互斥。</dd>
</dl>

<strong>示例</strong>：

通过策略 JSON 文件 `policy.json` 为用户 `name@example.com` 创建用户策略：
```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

授予 `name@example.com` 对所有 `sample-service` 资源的 `Administrator` 角色：
```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

授予 `name@example.com` 对 `us-south` 区域中 GUID 为 `d161aeea-fd02-40f8-a487-df1998bd69a9` 的样本服务实例的资源 `key123` 的 `Editor` 角色：
```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

授予 `name@example.com` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组的 `Operator` 角色：
```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

授予 `name@example.com` 对资源组 `sample-resource-group` 的成员的 `Viewer` 角色：
```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

授予 `name@example.com` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组成员的 `Viewer` 角色：
```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

更新用户策略：
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dt>USER_NAME（必需）</dt>
<dd>策略所属的用户名</dd>
<dt>POLICY_ID（必需）</dt>
<dd>要更新的策略的标识</dd>
<dt>--file <i>FILE</i>（可选）</dt>
<dd>策略定义的 JSON 文件</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i>（可选）</dt>
<dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行 `ibmcloud iam roles --service SERVICE_NAME`。此选项与 `--file` 互斥。</dd>
<dt>--service-name <i>SERVICE_NAME</i>（可选）</dt>
<dd>策略定义的服务名称，此选项与 `--file` 标志互斥。</dd>
<dt>--serivce-instance <i>SERVICE_INSTANCE_GUID</i>（可选）</dt>
<dd>策略定义的服务实例的 GUID，此选项与 `--file` 标志互斥。</dd>
<dt>--region <i>REGION</i>（可选）</dt>
<dd>策略定义的区域，此选项与 `--file` 标志互斥。</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i>（可选）</dt>
<dd>策略定义的资源类型，此选项与 `--file` 标志互斥。</dd>
<dt>--resource <i>RESOURCE</i>（可选）</dt>
<dd>策略定义的资源，此选项与 `--file` 标志互斥。</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i>（可选）</dt>
<dd>资源组的名称。`*` 表示所有资源组。此选项与 `--file`、`--resource` 和 `--resource-group-id` 标志互斥。</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i>（可选）</dt>
<dd>资源组的标识。`*` 表示所有资源组。此选项与 `--file`、`--resource` 和 `--resource-group-name` 标志互斥。</dd>
</dl>

<strong>示例</strong>：

使用 JSON 文件中的用户策略来更新用户策略：
```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

更新用户策略以授予 `name@example.com` 对所有 `sample-service` 资源的 `Administrator` 角色：
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

更新用户策略以授予 `name@example.com` 对 `us-south` 区域中 GUID 为 `d161aeea-fd02-40f8-a487-df1998bd69a9` 的样本服务实例的资源 `key123` 的 `Editor` 角色：
```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

更新用户策略以授予 `name@example.com` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组的 `Operator` 角色：
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

更新用户策略以授予 `name@example.com` 对资源组 `sample-resource-group` 的成员的 `Viewer` 角色：
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

更新用户策略以授予 `name@example.com` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组成员的 `Viewer` 角色：
```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

删除用户策略
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标帐户

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>删除用户策略而不确认</dd>
</dl>

<strong>示例</strong>：

删除用户 `name@example.com` 的策略 `user-policy-id`：
```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

删除用户 `name@example.com` 的策略 `user-policy-id` 而不确认：
```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

列出指定服务的所有服务策略：
```
ibmcloud iam service-policies SERVICE_ID [--output FORMAT] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>指定服务策略输出格式，目前仅支持 JSON。</dd>
  <dt>-f, --force（可选）</dt>
  <dd>显示服务策略而不确认</dd>
</dl>

<strong>示例</strong>：

列出服务 `test` 的策略：
```
ibmcloud iam service-policies test
```

列出服务 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的策略：
```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

显示服务策略的详细信息：
```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--output FORMAT] [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>POLICY_ID（必需）</dt>
  <dd>服务策略的标识<dd>
  <dt>--output FORMAT（可选）</dt>
  <dd>指定服务策略输出格式，目前仅支持 JSON。</dd>
  <dt>-f, --force（可选）</dt>
  <dd>显示服务策略而不确认</dd>
</dl>

<strong>示例</strong>：

显示服务 `test` 的策略 `140798e2-8ea7db3`：
```
ibmcloud iam service-policies test 140798e2-8ea7db3
```

显示服务 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的策略 `140798e2-8ea7db3`：
```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

创建服务策略：
```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [-f, --force]",
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>--file</dt>
  <dd>策略定义的 JSON 文件。此选项与 `-r, --roles`、`--service-name`、`--service-instance`、`--region`、`--resource-type`、`--resource`、`--resource-group-name` 和 `--resource-group-id` 标志互斥。</dd>
  <dt>-r, --roles</dt>
  <dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行 `ibmcloud iam roles --service SERVICE_NAME`。此选项与 `--file` 互斥。</dd>
  <dt>--service-name</dt>
  <dd>策略定义的服务名称。此选项与 `--file` 标志互斥。</dd>
  <dt>--service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>策略定义的服务实例的 GUID。此选项与 `--file` 标志互斥。</dd>
  <dt>-region</dt>
  <dd>策略定义的区域。此选项与 `--file` 标志互斥。</dd>
  <dt>--resource-type</dt>
  <dd>策略定义的资源类型。此选项与 `--file` 标志互斥。</dd>
  <dt>--resource</dt>
  <dd>策略定义的资源。此选项与 `--file` 标志互斥。</dd>
  <dt>--resource-group-name</dt>
  <dd>资源组的名称。`*` 表示所有资源组。此选项与 `--file` 和 `--resource-group-id` 互斥。</dd>
  <dt>--resource-group-id </dt>
  <dd>资源组的标识。`*` 表示所有资源组。此选项与 `--file` 和 `--resource-group-name` 互斥。</dd>
  <dt>--account-management（可选）</dt>
  <dd>授予对所有帐户管理服务的访问权</dd>
  <dt>-f, --force</dt>
  <dd>创建服务策略而不确认</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件为服务 `test` 创建服务策略：
```
ibmcloud iam service-policy-create test --file @policy.json
```

通过 JSON 文件为服务 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 创建服务策略：
```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```

为服务 `test` 授予所有帐户管理服务的 `Administrator` 角色：
```
ibmcloud iam service-policy-create test --roles Administrator --account-management
```

为服务 `test` 授予帐户中所有资源的 `Viewer` 角色：
```
ibmcloud iam service-policy-create test --roles Viewer
```

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

更新服务策略：
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [-f, --force]",
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>POLICY_ID（必需）</dt>
  <dd>服务策略的标识<dd>
  <dt>--file</dt>
  <dd>策略定义的 JSON 文件。此选项与 `-r, --roles`、`--service-name`、`--service-instance`、`--region`、`--resource-type`、`--resource`、`resource-group-name` 和 `resource-group-id` 标志互斥。</dd>
  <dt>-r, --roles</dt>
  <dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行 `ibmcloud iam roles --service SERVICE_NAME`。此选项与 `--file` 互斥。</dd>
  <dt>-service-name</dt>
  <dd>策略定义的服务名称。此选项与 `--file` 标志互斥。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>策略定义的服务实例的 GUID。此选项与 `--file` 标志互斥。</dd>
  <dt>-region</dt>
  <dd>策略定义的区域。此选项与 `--file` 标志互斥。</dd>
  <dt>-resource-type</dt>
  <dd>策略定义的资源类型。此选项与 `--file` 标志互斥。</dd>
  <dt>-resource</dt>
  <dd>策略定义的资源。此选项与 `--file` 标志互斥。</dd>
  <dt>--resource-group-name</dt>
  <dd>资源组的名称。`*` 表示所有资源组。此选项与 `--file` 和 `--resource-group-id` 互斥。</dd>
  <dt>--resource-group-id </dt>
  <dd>资源组的标识。`*` 表示所有资源组。此选项与 `--file` 和 `--resource-group-name` 互斥。</dd>
  <dt>--account-management（可选）</dt>
  <dd>授予对所有帐户管理服务的访问权</dd>
  <dt>-f, --force</dt>
  <dd>更新服务策略而不确认</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件更新服务 `test` 的服务策略 `140798e2-8ea7db3`：
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

通过 JSON 文件更新服务 `test` 的服务策略 `140798e2-8ea7db3`：
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

更新服务策略 `140798e2-8ea7db3`，为服务 `test` 授予所有帐户管理服务的 `Administrator` 角色：
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Administrator --account-management
```

更新服务策略 `140798e2-8ea7db3`，为服务 `test` 授予帐户中所有资源的 `Viewer` 角色：
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

删除服务策略：
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SERVICE_ID（必需）</dt>
  <dd>服务标识的名称或 UUID</dd>
  <dt>POLICY_ID（必需）</dt>
  <dd>服务策略的标识<dd>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除服务 `test` 的策略 `140798e2-8ea7db3`：
```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```

删除服务 `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 的策略 `140798e2-8ea7db3`：
```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

检索并显示当前会话的 OAuth 令牌：
```
ibmcloud iam oauth-tokens
```
{: codeblock}

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

刷新并显示 OAuth 令牌：
```
ibmcloud iam oauth-tokens
```
{: codeblock}

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

断开公共 IBM 标识与专用非 IBM 标识的连接：
```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>强制断开连接而不确认</dd>
</dl>

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

创建授权策略以允许服务实例访问其他服务实例：
```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [—-source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME | --source-service-instance-id SOURCE_SERVICE_INSTANCE_ID] [--source-resource-type RESOURCE_TYPE] [—-target-service-instance-name TARGET_SERVICE_INSTANCE_NAME] [--target-resource-type RESOURCE_TYPE | --target-service-instance-id TARGET_SERVICE_INSTANCE_ID] [--output FORMAT]
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>可对其授予访问权的源服务。</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>可授权源服务访问的目标服务。</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>为源服务提供访问权的角色。</dd>  
  <dt>--source-service-instance-name SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>源服务实例名称，与 `--source-service-instance-id` 互斥。如果未指定，将对源服务的所有实例授予访问权。</dd>
  <dt>--source-service-instance-id SOURCE_SERVICE_INSTANCE_ID</dt>
  <dd>源服务实例标识，与 `--source-service-instance-name` 互斥。如果未指定，将对源服务的所有实例授予访问权。</dd>
  <dt>--source-resource-type</dt>
  <dd>源服务的资源类型</dd>
  <dt>--target-service-instance-name TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>目标服务实例名称，与 `--target-service-instance-id` 互斥。如果未指定，将对目标服务的所有实例授予访问权。</dd>
  <dt>--target-service-instance-id TARGET_SERVICE_INSTANCE_ID</dt>
  <dd>目标服务实例标识，与 `--target-service-instance-name` 互斥。如果未指定，将对目标服务的所有实例授予访问权。</dd>
  <dt>--target-resource-type</dt>
  <dd>目标服务的资源类型</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

删除授权策略：
```
ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [-f, --force]
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>要删除的授权策略的标识。</dd>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认。</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

显示授权策略的详细信息：
```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>先决条件</strong>：登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>要显示的授权策略的标识。</dd>
</dl>

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

列出当前帐户下的授权策略：
```
ibmcloud iam authorization-policies
```
{: codeblock}

<strong>先决条件</strong>：登录和目标

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

列出当前帐户下的访问组：
```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-u</dt>
  <dd>列出用户所属的访问组。此标志与“-s”互斥。</dd>
  <dt>-s</dt>
  <dd>列出服务标识所属的访问组。此标志与“-u”互斥。</dd>
</dl>

<strong>示例</strong>：

列出所有访问组：
```
ibmcloud iam access-groups
```
{: codeblock}

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

显示访问组的详细信息：
```
ibmcloud iam access-group GROUP_NAME [--id]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-id</dt>
  <dd>仅显示标识</dd>
</dl>

<strong>示例</strong>：

显示访问组 `example_group` 的详细信息：
```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

创建访问组：
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-d, --description</dt>
  <dd>访问组的描述</dd>
</dl>

<strong>示例</strong>：

创建访问组 `example_group`：
```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

更新访问组：
```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-n, --name</dt>
  <dd>新访问组名称</dd>
  <dt>-d, --description</dt>
  <dd>新描述</dd>
  <dt>-f, --force</dt>
  <dd>强制更新而不确认</dd>
</dl>

<strong>示例</strong>：

将访问组 `example_group` 重命名为 `hello_word_group`：
```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

## ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

删除访问组

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
  <dt>-r, --recursive</dt>
  <dd>删除访问组及其成员</dd>
</dl>

<strong>示例</strong>：

删除访问组 `example_group`：
```
ibmcloud iam access-group-delete example_group --force
```

## ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

列出访问组中的用户：
```
ibmcloud iam access-group-users GROUP_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

列出访问组 `example_group` 中的所有用户：
```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

将用户添加到访问组：
```
ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [USER_NAME2...]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

将用户 `name@example.com` 添加到访问组 `example_group`：
```
ibmcloud iam access group-user-add example_group name@example.com
```

## ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

从访问组中除去用户：
```
ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

从访问组 `example_group` 中除去用户 `name@example.com`：
```
ibmcloud iam access-group-user-remove example_group name@example.com
```

## ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

从所有访问组中除去用户：
```
ibmcloud iam access-group-user-purge USER_NAME [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

从所有访问组中除去用户 `name@example.com`：
```
ibmcloud iam access-group-user-purge name@example.com -f
```

## ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

列出访问组中的服务标识：
```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

列出访问组 `example_group` 中的所有服务标识：
```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

将服务标识添加到访问组：
```
ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [SERVICE_ID_NAME2...]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

将服务标识 `example-service` 添加到访问组 `example_group`：
```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

从访问组中除去服务标识：
```
ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

从访问组 `example_group` 中除去服务标识 `example-service`：
```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

从所有访问组中除去服务标识：
```
ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>删除而不确认</dd>
</dl>

<strong>示例</strong>：

从所有访问组中除去服务标识 `example-service`：

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

列出访问组的策略：
```
ibmcloud iam access-group-policies GROUP_NAME
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

列出访问组 `example_group` 中的所有策略：
```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

显示访问组策略的详细信息：
```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
</dl>

<strong>示例</strong>：

显示访问组 `example_group` 的策略 `51b9717e-76b0-4f6a-bda7-b8132431f926` 的详细信息：
```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

创建访问组策略：
```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--file</dt>
  <dd>策略定义的 JSON 文件</dd>
  <dt>-roles</dt>
  <dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行 `ibmcloud iam roles --service SERVICE_NAME`。此选项与 `--file` 互斥。</dd>
  <dt>-service-name</dt>
  <dd>策略定义的服务名称。此选项与 `--file` 互斥。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>策略定义的服务实例的 GUID。此选项与 `--file` 互斥。</dd>
  <dt>-region</dt>
  <dd>策略定义的区域。此选项与 `--file` 互斥。</dd>
  <dt>-resource-type</dt>
  <dd>策略定义的资源类型。此选项与 `--file` 互斥。</dd>
  <dt>-resource</dt>
  <dd>策略定义的资源。此选项与 `--file` 互斥。</dd>
  <dt>-resource-group-name</dt>
  <dd>资源组的名称。`*` 表示所有资源组。此选项与 `--file` 和 `--resource-group-id` 互斥。</dd>
  <dt>-resource-group-id</dt>
  <dd>资源组的标识。`*` 表示所有资源组。此选项与 `--file` 和 `--resource-group-name` 互斥。</dd>
</dl>

<strong>示例</strong>：

通过 JSON 文件创建访问组策略：
```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

授予 `example_group` 对所有 `sample-service` 资源的 `Administrator` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

授予 `example_group` 对 `us-south` 区域中 GUID 为 `d161aeea-fd02-40f8-a487-df1998bd69a9` 的 `sample-service` 实例的资源 `key123` 的 `Editor` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

授予 `example_group` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组的 `Operator` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

授予 `example_group` 对资源组 `sample-resource-group` 中成员的 `Viewer` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

授予 `example_group` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组中成员的 `Viewer` 角色：
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

更新访问组策略：
```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>--file</dt>
  <dd>策略定义的 JSON 文件</dd>
  <dt>--roles</dt>
  <dd>策略定义的角色名称。要了解特定服务所支持的角色，请运行 `ibmcloud iam roles --service SERVICE_NAME`。此选项与 `--file` 互斥。</dd>
  <dt>-service-name</dt>
  <dd>策略定义的服务名称。此选项与 `--file` 互斥。</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>策略定义的服务实例的 GUID。此选项与 `--file` 互斥。</dd>
  <dt>-region</dt>
  <dd>策略定义的区域。此选项与 `--file` 互斥。</dd>
  <dt>-resource-type</dt>
  <dd>策略定义的资源类型。此选项与 `--file` 互斥。</dd>
  <dt>-resource</dt>
  <dd>策略定义的资源。此选项与 `--file` 互斥。</dd>
  <dt>-resource-group-name</dt>
  <dd>资源组的名称。`*` 表示所有资源组。此选项与 `--file` 和 `--resource-group-id` 互斥。</dd>
  <dt>-resource-group-id</dt>
  <dd>资源组的标识。`*` 表示所有资源组。此选项与 `--file` 和 `--resource-group-name` 互斥。</dd>
</dl>

<strong>示例</strong>：

使用策略 JSON 文件中的访问组策略来更新访问组策略：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

更新访问组策略，以授予 `example_group` 对所有 `sample-service` 资源的 `Administrator` 角色：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

更新访问组策略，以授予 `example_group` 对 `us-south` 区域中 GUID 为 `d161aeea-fd02-40f8-a487-df1998bd69a9` 的 `sample-service` 实例的资源 `key123` 的 `Editor` 角色：
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

更新访问组策略，以授予 `example_group` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组的 `Operator` 角色：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

更新访问组策略，以授予 `example_group` 对资源组 `sample-resource-group` 中成员的 `Viewer` 角色：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

更新访问组策略，以授予 `example_group` 对标识为 `dda27e49d2a1efca58083a01dfde18f6` 的资源组中成员的 `Viewer` 角色：
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

删除访问组策略：
```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
<dl>
  <dt>-f, --force</dt>
  <dd>强制删除而不确认</dd>
</dl>

<strong>示例</strong>：

删除访问组 `example_group` 的策略 `51b9717e-76b0-4f6a-bda7-b8132431f926`：
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
