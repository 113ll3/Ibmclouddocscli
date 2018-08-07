---

copyright:

  years: 2018


lastupdated: "2018-07-27"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 用于管理 Cloud Foundry Enterprise Environments 的命令（试验性）
{: #ibmcloud_commands_cfee}

<table summary="管理 Cloud Foundry Enterprise Environments（试验性）">
<caption>表 1. 管理 Cloud Foundry Enterprise Environments（试验性）</caption>
 <thead>
 <th colspan="5">管理 Cloud Foundry Enterprise Environments（试验性）</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 </tr>
 </tbody>
 </table>

 ### ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

列出 CFEE 环境。

```
ibmcloud cfee environments
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：

### ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

显示 CFEE 环境的详细信息。

```
ibmcloud cfee environment NAME [--id]
```

<strong>先决条件</strong>：端点和登录

<strong>命令选项</strong>：
  <dl>
   <dt>--id</dt>
   <dd>仅显示标识。</dd>
  </dl>

<strong>示例</strong>：

显示 CFEE 环境 env_example 的详细信息：

```
ibmcloud cfee environment env_example
```

显示 CFEE 环境 env_example 的标识：

```
ibmcloud cfee environment env_example --id
```
