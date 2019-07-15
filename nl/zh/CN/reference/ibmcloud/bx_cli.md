---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-10"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# 常规 CLI (ibmcloud) 命令
{: #ibmcloud_cli}

{{site.data.keyword.cloud_notm}} 命令行界面 (CLI) 提供了一组按名称空间分组的命令，供用户用于与 {{site.data.keyword.cloud_notm}} 进行交互。
{: shortdesc}

{{site.data.keyword.cloud_notm}} 命令行客户机在其安装中捆绑了 Cloud Foundry 命令行客户机。如果您已安装 Cloud Foundry CLI，请勿在同一上下文中同时使用 {{site.data.keyword.cloud_notm}} CLI 命令和您自己安装的 Cloud Foundry CLI 命令。如果要在 {{site.data.keyword.cloud_notm}} CLI 上下文中使用 Cloud Foundry CLI 来管理 Cloud Foundry 资源，请改为使用 **`ibmcloud cf [command]`**。请注意，不允许使用 **`ibmcloud cf api/login/logout/target`**，必须改为使用 **`ibmcloud api/login/logout/target`**。

从 2018 年 5 月起，{{site.data.keyword.cloud_notm}} CLI 命令已从 **`bluemix`** 和 **`bx`** 更改为 **`ibmcloud`**。但是，您仍然可以使用 **`bluemix`** 和 **`bx`** CLI 命令，直到稍后这些命令被除去为止。
{: tip}

下面列出了 {{site.data.keyword.cloud_notm}} CLI 支持的命令的详细用法，包括命令名称、自变量、选项、先决条件、描述和示例。

先决条件列出使用命令前必须执行的操作，并且可能包含以下一个或多个操作：

<dl>
<dt>Docker</dt>
<dd>安装 Docker CLI。</dd>
<dt>端点</dt>
<dd>使用 **`ibmcloud api`** 命令来设置 API 端点。</dd>
<dt>登录</dt>
<dd>使用 **`ibmcloud login`** 命令登录。如果使用联合标识登录，请使用 **`--sso`** 选项通过一次性密码进行认证，或者使用 **`--apikey`** 选项通过 API 密钥进行认证。</dd>
<dt>目标</dt>
<dd>使用 **`ibmcloud target`** 命令来设置组织和空间。</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

显示 {{site.data.keyword.cloud_notm}} CLI 第一级内置命令和受支持名称空间的一般帮助，或者显示特定内置命令或名称空间的帮助。

```
ibmcloud help [COMMAND|NAMESPACE]
```

### 先决条件
{: #help-prereqs}

无。

### 命令选项
{: #help-options}

<dl>
<dt>COMMAND|NAMESPACE</dt>
<dd>显示其帮助信息的命令或名称空间。如果未指定，将显示 {{site.data.keyword.cloud_notm}} CLI 的一般帮助。可选。</dd>
</dl>

### 示例
{: #help-examples}

显示 {{site.data.keyword.cloud_notm}} CLI 的一般帮助：
```
ibmcloud help
```
{: codeblock}

显示 **`dev`** 命令的帮助：
```
ibmcloud help dev
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

设置或查看 {{site.data.keyword.cloud_notm}} API 端点。
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

### 先决条件
{: #api-prereqs}

无。

### 命令选项
{: #api-options}

<dl>
<dt>API_ENDPOINT</dt>
<dd>作为目标的 API 端点，例如 `https://cloud.ibm.com`。如果未指定 **`API_ENDPOINT`** 和 **`--unset`** 选项，将显示当前 API 端点。可选。</dd>
<dt>--skip-ssl-validation</dt>
<dd>绕过 HTTP 请求的 SSL 验证。可选。</dd>
<dt>--unset</dt>
<dd>除去 API 端点设置。</dd>
</dl>

### 示例
{: #api-examples}

将 API 端点设置为 cloud.ibm.com：
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

查看当前 API 端点：
```
ibmcloud api
```
{: codeblock}

除去 API 端点：
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

将缺省值写入配置文件。

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

### 先决条件
{: #config-prereqs}

无。

### 命令选项
{: #config-options}

<dl>
<dt>--check-version</dt>
<dd>启用或禁用 CLI 版本检查。有效值为 `true` 或 `false`。</dd>
<dt>--color</dt>
<dd>启用或禁用颜色输出。缺省情况下，此选项处于禁用状态。有效值为 `true` 或 `false`。</dd>
<dt>--http-timeout</dt>
<dd>HTTP 请求的超时值（以秒为单位）。缺省值为 60 秒。</dd>
<dt>--locale</dt>
<dd>设置缺省语言环境。如果未指定值，将删除先前的语言环境。</dd>
<dt>--trace </dt>
<dd>跟踪对终端或指定文件的 HTTP 请求。有效值为 `true` 或 `false`。</dd>
</dl>

一次只能指定其中一个选项。
{: tip}

### 示例
{: #config-examples}

将 HTTP 请求超时设置为 30 秒：
```
ibmcloud config --http-timeout 30
```
{: codeblock}

启用 HTTP 请求的跟踪输出：
```
ibmcloud config --trace true
```
{: codeblock}

跟踪对 `/home/usera/my_trace` 文件的 HTTP 请求：
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

禁用颜色输出：
```
ibmcloud config --color false
```
{: codeblock}

将语言环境设置为 zh_Hans：
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

清除语言环境设置：
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

从 CLI V0.14 开始，**`ibmcloud info`** 命令不再可用。要安装最新的 CLI 版本，请参阅[安装独立 {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)。


## ibmcloud cf
{: #ibmcloud_cf}

调用嵌入式 Cloud Foundry CLI。
```
ibmcloud [-q, --quiet] cf COMMAND...
```

### 先决条件
{: #info-prereqs}

无。

### 命令选项
{: #info-options}

<dl>
  <dt>-q, --quiet</dt>
  <dd>不显示调用消息。</dd>
</dl>

### 示例
{: #info-examples}

列出 Cloud Foundry 应用程序：

```
ibmcloud cf apps
```

列出 Cloud Foundry 服务，而不显示 `Invoking cf command...` 消息：
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud cf install
{: #ibmcloud_cf_install}

为 IBM Cloud CLI 安装 Cloud Foundry CLI
```
ibmcloud cf install [-v, --version VERSION] [--restore] [-f, --force]
```

### 先决条件
{: #cfinstall-prereqs}

无。

### 命令选项
{: #cfinstall-options}

<dl>
  <dt>-v, --version</dt>
  <dd>指定要安装的 Cloud Foundry CLI 版本</dd>
  <dt>--restore</dt>
  <dd>复原到 Cloud Foundry CLI 的预捆绑版本</dd>
  <dt>-f, --force</dt>
  <dd>强制安装而不确认</dd>
</dl>

### 示例
{: #cfinstall-examples}

安装 Cloud Foundry CLI `6.44.1`：

```
ibmcloud cf install -v 6.44.1
```

安装最新版本的 Cloud Foundry CLI 而不确认：

```
ibmcloud cf install -f
```

恢复到缺省捆绑 Cloud Foundry CLI：

```
ibmcloud cf install --restore
```

## ibmcloud login

{: #ibmcloud_login}

登录到 {{site.data.keyword.cloud_notm}} CLI。

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```
### 先决条件
{: #login-prereqs}

无。

### 命令选项
{: #login-options}

<dl>
<dt>-a API_ENDPOINT</dt>
<dd>API 端点，例如 `cloud.ibm.com`。</dd>
<dt>--apikey API_KEY 或 @API_KEY_FILE_PATH</dt>
<dd>API 密钥内容或用 @ 符号指示的 API 密钥文件的路径。</dd>
<dt>-u USER_NAME</dt>
<dd>用户名。可选。</dd>
<dt>-p PASS_WORD</dt>
<dd>用户密码。可选。</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>目标帐户的标识。此选项与 **`--no account`** 选项互斥。</dd>
<dt>--no-account</dt>
<dd>强制在没有帐户的情况下登录。建议不要使用此选项，此选项与 **`-c`** 选项互斥。</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>目标资源组的名称。可选。</dd>
<dt>-r REGION</dt>
<dd>目标区域的名称，例如，us-south 或 eu-gb。</dd>
<dt>--no-region</dt>
<dd>强制在不设置目标区域的情况下登录。</dd>
<dt>-o ORG</dt>
<dd>目标组织的名称。不推荐使用该选项。请改为使用 **`ibmcloud target -o org_name`**。可选。</dd>
<dt>-s SPACE</dt>
<dd>目标空间的名称。不推荐使用此选项。请改为使用 **`ibmcloud target -s space_name`**。可选。</dd>
<dt>--no-iam</dt>
<dd>强制向登录服务器（而不是公共 IAM）进行认证。</dd>
<dt>--skip-ssl-validation</dt>
<dd>绕过 HTTP 请求的 SSL 验证。不建议使用此选项。</dd>
</dl>

### 示例
{: #login-examples}

以交互方式登录。

```
ibmcloud login
```
{: codeblock}

使用用户名和密码登录，并设置目标帐户、组织和空间：
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

使用一次性密码登录，并设置目标帐户、组织和空间：
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

设置 Cloud Found 组织和空间。您可以运行以下命令，通过交互方式确定组织和空间：

```
  ibmcloud target --cf
  ```
{: codeblock}

或者，如果您知道服务所属的组织和空间，可以使用以下命令：

```
ibmcloud target -o <value> -s <value>
	```
{: codeblock}

使用具有关联帐户的 API 密钥：

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

使用没有关联帐户的 API 密钥：

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

如果 API 密钥具有关联的帐户，那么不支持切换到其他帐户。
{: note}

使用一次性密码：

```
ibmcloud login -u UserID --sso
```
{: codeblock}

然后，CLI 会提供一个 URL 链接并要求输入密码：

```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

在浏览器中打开链接，以获取密码。在控制台中输入给定的密码进行登录。

## ibmcloud logout
{: #ibmcloud_logout}

从 CLI 注销。

```
ibmcloud logout
```
{: codeblock}

### 先决条件
{: #logout-prereqs}

无。

## ibmcloud regions
{: #ibmcloud_regions}

查看 {{site.data.keyword.cloud_notm}} 上所有区域的信息。

```
ibmcloud regions
```
{: codeblock}

### 先决条件
{: #regions-prereqs}

使用 **`ibmcloud api`** 命令来设置 API 端点。

## ibmcloud target
{: #ibmcloud_target}

设置或查看目标帐户、区域、组织或空间。

```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

### 先决条件
{: #target-prereqs}

* 使用 **`ibmcloud api`** 命令来设置 API 端点。
* 使用 **`ibmcloud login`** 命令登录。如果使用联合标识登录，请使用 **`--sso`** 选项通过一次性密码进行认证，或者使用 **`--apikey`** 选项通过 API 密钥进行认证。

### 命令选项
{: #target-options}

<dl>
<dt>-c ACCOUNT_ID</dt>
<dd>目标帐户的标识。可选。</dd>
<dt>-r REGION</dt>
<dd>目标区域的名称，例如，us-south 或 eu-gb。可选。</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>目标资源组的名称。可选。</dd>
<dt>--cf</dt>
<dd>交互指定目标组织和空间。</dd>
<dt>--cf-api</dt>
<dd>Cloud Foundry API 端点。</dd>
<dt>-o ORG</dt>
<dd>目标组织的名称。可选。</dd>
<dt>-s SPACE</dt>
<dd>目标空间的名称。可选。</dd>
<dt>--unset-region</dt>
<dd>清除目标区域。</dd>
<dt>--unset-resource-group</dt>
<dd>清除目标资源组。</dd>
<dt>--output FORMAT</dt>
<dd>指定的输出格式。JSON 是目前唯一受支持的格式。</dd>
</dl>

如果未指定任何选项，那么将显示当前帐户、区域、组织和空间。
{: note}

### 示例
{: #target-examples}

设置当前帐户、组织和空间：
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

切换到新区域：
```
ibmcloud target -r eu-gb
```
{: codeblock}

查看当前帐户、区域、组织和空间：
```
ibmcloud target
```
{: codeblock}

## ibmcloud update
{: #ibmcloud_update}

将 CLI 更新到最新版本。

```
ibmcloud update [-f]
```
### 先决条件
{: #update-prereqs}

### 命令选项
{: #update-options}

<dl>
  <dt>-f</dt>
  <dd>强制更新而不确认。需要具备 root 用户特权。</dd>
</dl>

## 常规经典基础架构服务命令
{: #classic-service-commands}

使用 {{site.data.keyword.cloud_notm}} CLI 中的经典基础架构命令可配置和管理基础架构服务。

运行 **`ibmcloud sl`** 命令可查看可用命令的列表：
```
用法：
   ibmcloud sl command [arguments...] [options...]

命令：
   block           经典基础架构块存储器
   cdn             经典基础架构内容交付网络
   file            经典基础架构文件存储器
   dns             经典基础架构域名系统
   globalip        经典基础架构全局 IP 地址
   hardware        经典基础架构硬件服务器
   image           经典基础架构计算映像
   ipsec           经典基础架构 IPSEC VPN
   loadbal         经典基础架构负载均衡器
   security        经典基础架构 SSH 密钥和 SSL 证书
   securitygroup   经典基础架构网络安全组
   subnet          经典基础架构网络子网
   ticket          经典基础架构管理凭单
   vlan            经典基础架构网络 VLAN
   vs              经典基础架构虚拟服务器
   order           经典基础架构订单
   user            经典基础架构管理用户
   call-api        调用任意 API 端点。
   help            显示命令用法消息
```
{: screen}

要查看有关命令的帮助信息，请运行以下命令：
```
ibmcloud sl [command] -h
```

从 CLI V**`0.14`** 开始，`ibmcloud sl init` 命令不再可用。要安装最新的 CLI 版本，请参阅[安装独立 {{site.data.keyword.cloud_notm}} CLI](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)。
{: note}

## ibmcloud sl help
{: #sl_help}

查看所有命令的帮助信息以操作经典基础架构环境。
```
ibmcloud sl help

```
{: codeblock}

