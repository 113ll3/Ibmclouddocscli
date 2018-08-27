---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理 Cloud Foundry Enterprise Environment（實驗性）
{: #ibmcloud_commands_cfee}

<table summary="管理 Cloud Foundry Enterprise Environment（實驗性）">
<caption>表 1. 管理 Cloud Foundry Enterprise Environment（實驗性）</caption>
 <thead>
 <th colspan="5">管理 Cloud Foundry Enterprise Environment（實驗性）</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
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
   <dt>--id</dt>
   <dd>僅顯示 ID。</dd>
  </dl>

<strong>範例</strong>：

顯示 CFEE 環境 env_example 的詳細資料：

```
ibmcloud cfee environment env_example
```

顯示 CFEE 環境 env_example 的 ID：

```
ibmcloud cfee environment env_example --id
```
