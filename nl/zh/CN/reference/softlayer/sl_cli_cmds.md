---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 常规 CLI (ibmcloud sl) 命令
{: #softlayer_cli}

{{site.data.keyword.BluSoftlayer}} 插件已合并到 {{site.data.keyword.Bluemix_notm}} CLI 中。您不再需要安装该插件。
{: tip}

使用 {{site.data.keyword.Bluemix_notm}} 命令行界面 (CLI) 中的 {{site.data.keyword.BluSoftlayer_notm}} 基础架构命令来配置和管理 SoftLayer 服务。

从 2018 年 5 月起，{{site.data.keyword.Bluemix_notm}} CLI 命令已从 `bluemix` 和 `bx` 更改为 `ibmcloud`。但是，您仍然可以使用 `bluemix` 和 `bx` CLI 命令，直到未来某个日期这些命令被除去为止。
{: tip}

首先，请安装 {{site.data.keyword.Bluemix_notm}} CLI。有关详细信息，请参阅 [IBM Cloud CLI ![外部链接图标](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}。

要获取 {{site.data.keyword.Bluemix_notm}} CLI 命令的完整列表，请参阅：[{{site.data.keyword.Bluemix_notm}} (ibmcloud) 命令](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli)。

支持以下命令。使用 `ibmcloud sl` 命令可查看可用命令的列表：

<table summary="按字母顺序排序的常规命令（命令带有可获取命令更多信息的链接）">
<caption>表 1. 常规 {{site.data.keyword.BluSoftlayer_notm}} 基础架构命令</caption>
 <thead>
 <th colspan="6">常规 {{site.data.keyword.BluSoftlayer_notm}} 基础架构命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_help)</td>
   </tbody>
 </table>
 
 要查看命令的帮助信息，请运行：`ibmcloud sl [command] -h`。
 
 ## ibmcloud sl init
{: #sl_init}

初始化用于连接到 {{site.data.keyword.BluSoftlayer_notm}} 基础架构环境的配置设置。该配置包括用户名、API 密钥或密码、帐户和端点。
```
ibmcloud sl init [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-a, --api-endpoint</dt>
<dd>{{site.data.keyword.BluSoftlayer_notm}} 基础架构 API 端点 URL，缺省值为 https://api.softlayer.com/rest/v3.1（对于 API 密钥认证）或 https://api.softlayer.com/mobile/v3.1（对于 IBM 标识认证）。</dd>
<dt>-u, --sl-user</dt>
<dd>Gen1 基础架构用户名。</dd>
<dt>-p, --sl-password</dt>
<dd>密码或 API 密钥。</dd>
<dt>-c, --account-id</dt>
<dd>帐户标识。</dd>
<dt>-q, --security-question-id</dt>
<dd>用于认证的安全问题标识，如果您不知道，请询问您的帐户所有者。</dd>
<dt>-w, --security-question-answer</dt>
<dd>用于认证的安全问题答案，如果您不知道，请询问您的帐户所有者。</dd>
<dt>-s, --security-code</dt>
<dd>启用双重认证时安全供应商生成的安全代码。</dd>
<dt>-v, --security-vendor</dt>
<dd>提供用于认证的安全代码的安全供应商，选项为 VERISIGN、TOTP 或 PHONE_FACTOR。</dd>
<dt>-t, --auth-token</dt>
<dd>启用电话认证时的认证令牌。</dd>
</dl>

例如，使用 {{site.data.keyword.BluSoftlayer_notm}} 基础架构用户名和密码/API 密钥登录
```
$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:
1. Login with {{site.data.keyword.BluSoftlayer_notm}} infrastructure user name and password/API key
2. Use {{site.data.keyword.Bluemix_notm}} Single-Sign-On
Enter a number>1
Softlayer API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Username: []> user@example.com
API key or password: []> abcd

API endpoint:    https://api.softlayer.com/rest/v3.1   
User name:       user@example.com   
API Key:         xxxxxxxxxx
```
例如，使用 {{site.data.keyword.Bluemix_notm}} Single-Sign-On 登录 Softlayer
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account example user's Account (65ce8074c6c62b5)

API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)
Region:         us-south   
User:           user@example.com   
Account:        example user's Account (65ce8074c6c62b5)   
No org or space targeted, use 'ibmcloud target --cf or ibmcloud target -o ORG -s SPACE'

$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:

1. Login with Softlayer user name and password/API key
2. Use IBM Cloud Single-Sign-On
Enter a number> 2
{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint URL: [https://api.softlayer.com/mobile/v3.1]>
Setting account to: 123456
OK

{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint:    https://api.softlayer.com/mobile/v3.1   

Account ID:                123456   
User ID:                   user@example.com  
IMS token:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

查看所有命令的帮助信息以操作 {{site.data.keyword.BluSoftlayer_notm}} 基础架构环境。
```
ibmcloud sl help

```
