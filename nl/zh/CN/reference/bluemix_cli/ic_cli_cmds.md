---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 常规 CLI (ibmcloud) 命令
{: #ibmcloud_cli}

版本：0.7.1

{{site.data.keyword.Bluemix_notm}} 命令行界面 (CLI) 提供了一组按名称空间分组的命令，供用户用于与 {{site.data.keyword.Bluemix_notm}} 进行交互。

从 V0.5.0 开始，{{site.data.keyword.Bluemix_notm}} 命令行客户机在其安装中捆绑了 Cloud Foundry 命令行客户机。如果您已安装 cf CLI，请勿在同一上下文中同时使用 {{site.data.keyword.Bluemix_notm}} CLI 命令 `ibmcloud [command]` 和您自己安装的 Cloud Foundry CLI 命令 `cf [command]`。如果要在 {{site.data.keyword.Bluemix_notm}} CLI 上下文中使用 cf CLI 来管理 Cloud Foundry 资源，请改为使用 `ibmcloud cf [command]`。请注意，不允许使用 `ibmcloud cf api/login/logout/target`，必须改为使用 `ibmcloud api/login/logout/target`。

从 2018 年 5 月起，{{site.data.keyword.Bluemix_notm}} CLI 命令已从 `bluemix` 和 `bx` 更改为 `ibmcloud`。但是，您仍然可以使用 `bluemix` 和 `bx` CLI 命令，直到未来某个日期这些命令被除去为止。
{: tip}

下面列出了 {{site.data.keyword.Bluemix_notm}} CLI 支持的命令的详细用法，包括命令名称、自变量、选项、先决条件、描述和示例。
{:shortdesc}

**注：***先决条件*列出使用命令前必须执行的操作。没有任何先决条件操作的命令会列出**无**。否则，先决条件可能会包含以下一个或多个操作：

<dl>
<dt>端点</dt>
<dd>使用此命令之前，必须通过 <code>bluemix api</code> 设置 API 端点。</dd>
<dt>登录</dt>
<dd>使用此命令之前，必须使用 <code>bluemix login</code> 命令登录。如果使用联合标识登录，请使用“--sso”选项通过一次性密码进行认证，或者使用“--apikey”通过 API 密钥进行认证。转至 {{site.data.keyword.Bluemix_notm}} 控制台的**管理** &gt; **安全性** &gt; **平台 API 密钥**以创建 API 密钥。
</dd>
<dt>目标</dt>
<dd>使用此命令之前，必须使用 <code>bluemix target</code> 命令来设置组织和空间。</dd>
<dt>Docker</dt>
<dd>必须安装 Docker CLI (docker) 才能运行此命令。</dd>
</dl>


使用下表中的索引可查看常用 ibmcloud 命令。

## 常规 ibmcloud 命令
{: #ibmcloud_commands_index}

<table summary="常规 ibmcloud 命令。">
<caption>表 1. 常规 ibmcloud 命令</caption>
 <thead>
 <th colspan="5">常规 ibmcloud 命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud help](ic_cli_cmds.html#ibmcloud_help)</td>
 <td>[ibmcloud api](ic_cli_cmds.html#ibmcloud_api)</td>
 <td>[ibmcloud config](ic_cli_cmds.html#ibmcloud_config)</td>
 <td>[ibmcloud info](ic_cli_cmds.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](ic_cli_cmds.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](ic_cli_cmds.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](ic_cli_cmds.html#ibmcloud_logout) </td>
 <td>[ibmcloud regions](ic_cli_cmds.html#ibmcloud_regions)</td>
 <td>[ibmcloud target](ic_cli_cmds.html#ibmcloud_target)</td>
 <td>[ibmcloud update](ic_cli_cmds.html#ibmcloud_update)</td>
 </tr>
 </tbody>
 </table>
 
 ## ibmcloud help
{: #ibmcloud_help}
显示 {{site.data.keyword.Bluemix_notm}} CLI 第一级内置命令和受支持名称空间的一般帮助，或者显示特定内置命令或名称空间的帮助。

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：

   <dl>
   <dt>COMMAND|NAMESPACE（可选）</dt>
   <dd>显示其帮助信息的命令或名称空间。如果未指定，将显示 {{site.data.keyword.Bluemix_notm}} CLI 的一般帮助。</dd>
   </dl>



<strong>示例</strong>：

显示 {{site.data.keyword.Bluemix_notm}} CLI 的一般帮助：

```
ibmcloud help
```

显示 `info` 命令的帮助：

```
ibmcloud help info
```

## ibmcloud api
{: #ibmcloud_api}
设置或查看 {{site.data.keyword.Bluemix_notm}} API 端点。

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
   <dl>
   <dt>API_ENDPOINT（可选）</dt>
   <dd>作为目标的 API 端点，例如 `https://api.chinabluemix.net`。如果未指定 *API_ENDPOINT* 和 `--unset` 选项，将显示当前 API 端点。</dd>
   <dt>--unset（可选）</dt>
   <dd>除去 API 端点设置。</dd>
   <dt>--skip-ssl-validation（可选）</dt>
   <dd>绕过 HTTP 请求的 SSL 验证。</dd>
   </dl>
<strong>示例</strong>：

将 API 端点设置为 api.chinabluemix.net：

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

查看当前 API 端点：

```
ibmcloud api
```

取消设置 API 端点：

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


将缺省值写入配置文件。

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>HTTP 请求的超时值。缺省值为 60 秒。</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>跟踪对终端或指定文件的 HTTP 请求。</dd>
   <dt>--color true|false</dt>
   <dd>启用或禁用颜色输出。缺省情况下，会启用颜色输出。</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>设置缺省语言环境。如果 LOCALE 为 <i>CLEAR</i>，将删除先前的语言环境。</dd>
   <dt>--check-version true|false</dt>
   <dd>启用或禁用 CLI 版本检查。</dd>
   </dl>

一次只能指定其中一个选项。

<strong>示例</strong>：

将 HTTP 请求超时设置为 30 秒：

```
ibmcloud config --http-timeout 30
```

启用 HTTP 请求的跟踪输出：

```
ibmcloud config --trace true
```

跟踪对指定文件 */home/usera/my_trace* 的 HTTP 请求：

```
ibmcloud config --trace /home/usera/my_trace
```

禁用颜色输出：

```
ibmcloud config --color false
```

将语言环境设置为 zh_Hans：

```
ibmcloud config --locale zh_Hans
```

清除语言环境设置：

```
ibmcloud config --locale CLEAR
```

## ibmcloud info
{: #ibmcloud_info}

查看基本 {{site.data.keyword.Bluemix_notm}} 信息，包括当前区域、云控制器版本以及一些有用的端点，例如用于登录和交换访问令牌的端点。

```
ibmcloud info
```

<strong>先决条件</strong>：端点

## ibmcloud cf
{: #ibmcloud_cf}

调用嵌入式 CF CLI

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
<dl>
  <dt>-q, --quiet</dt>
  <dd>关闭消息“正在调用 cf 命令...”</dd>
</dl>

<strong>示例</strong>：

列出 CF 应用程序：

```
ibmcloud cf apps
```

列出 CF 服务，而不显示消息“正在调用 cf 命令...”：

```
ibmcloud -q cf services
```

## ibmcloud login
{: #ibmcloud_login}

用户登录。

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>先决条件</strong>：无

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>命令选项</strong>：
<dl>
  <dt> -a <i>API_ENDPOINT</i>（可选）</dt>
  <dd> API 端点（例如：api.ng.bluemix.net）</dd>
  <dt> --apikey <i>API_KEY 或 @API_KEY_FILE_PATH</i>
  <dd> API 密钥内容或用 @ 指示的 API 密钥文件路径</dd>
  <dt> --sso（可选）</dt>
  <dd> 使用一次性密码登录</dd>
  <dt> -u <i>USERNAME</i>（可选）</dt>
  <dd> 用户名</dd>
  <dt> -p <i>PASSWORD</i>（可选）</dt>
  <dd> 密码</dd>
  <dt> -c <i>ACCOUNT_ID</i>（可选）</dt>
  <dd> 目标帐户的标识</dd>
  <dt> -g <i>RESOURCE_GROUP</i>（可选）</dt>
  <dd> 目标资源组的名称</dd>
  <dt> -o <i>ORG</i>（可选）</dt>
  <dd> 目标组织的名称（不推荐，请使用“ibmcloud target -o ORG”）</dd>
  <dt> -s <i>SPACE</i>（可选）</dt>
  <dd> 目标空间的名称（不推荐，请使用“ibmcloud target -s SPACE”）</dd>
  <dt> --no-iam</dt>
  <dd> 强制向登录服务器（而不是公共 IAM）进行认证</dd>
  <dt> --skip-ssl-validation（可选）</dt>
  <dd> 绕过 HTTP 请求的 SSL 验证。建议不要使用此选项。</dd>
</dl>

<strong>示例</strong>：

#### 交互式登录

```
ibmcloud login
```

使用用户名和密码登录，并设置目标帐户、组织和空间：

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

使用一次性密码登录，并设置目标帐户、组织和空间

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

使用 API 密钥登录并设置目标：

#### API 密钥具有关联的帐户

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### API 密钥没有关联的帐户

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>注：</strong>如果 API 密钥具有关联的帐户，那么不允许切换到其他帐户。

#### 使用一次性密码

```
ibmcloud login -u UserID --sso
```

然后，CLI 将提供一个 URL 链接并要求输入密码：
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

在浏览器中打开链接，该链接将引导您获取密码。在控制台中输入提供的密码，然后您应该能够登录。

## ibmcloud logout
{: #ibmcloud_logout}

注销用户。

```
ibmcloud logout
```

<strong>先决条件</strong>：无

## ibmcloud regions
{: #ibmcloud_regions}

查看 {{site.data.keyword.Bluemix_notm}} 上所有区域的信息。

```
ibmcloud regions
```

<strong>先决条件</strong>：端点

## ibmcloud target
{: #ibmcloud_target}


设置或查看目标帐户、区域、组织或空间。

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
   <dl>
   <dt>-r <i>REGION_NAME</i>（可选）</dt>
   <dd>要切换到的区域的名称，例如“us-south”或“eu-gb”。</dd>
   <dt>-c <i>ACCOUNT_ID</i>（可选）</dt>
   <dd>要作为目标的帐户的标识。</dd>
   <dt>-g <i>RESOURCE_GROUP</i>（可选）</dt>
   <dd>资源组的名称</dd>
   <dt>--cf</dt>
   <dd>以交互方式选择目标组织和空间</dd>
   <dt>-o <i>ORG_NAME</i>（可选）</dt>
   <dd>要作为目标的组织的名称。</dd>
   <dt>-s <i>SPACE_NAME</i>（可选）</dt>
   <dd>要作为目标的空间的名称。</dd>
   </dl>
如果未指定任何选项，那么将显示当前帐户、区域、组织和空间。


<strong>示例</strong>：

设置当前帐户、组织和空间：

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

切换到新区域：

```
ibmcloud target -r eu-gb
```

查看当前帐户、区域、组织和空间：

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

将 CLI 更新到最新版本。

```
ibmcloud update [-f]
```

<strong>先决条件</strong>：无

<strong>命令选项</strong>：
<dl>
  <dt>-f</dt>
  <dd>强制更新而不确认。需要具备 root 用户特权。</dd>
</dl>
