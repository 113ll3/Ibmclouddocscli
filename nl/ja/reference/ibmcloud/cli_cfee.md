---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cloud Foundry エンタープライズ環境の管理 (試験的)
{: #ibmcloud_commands_cfee}

<table summary="Cloud Foundry エンタープライズ環境の管理 (試験的)">
<caption>表 1. Cloud Foundry エンタープライズ環境の管理 (試験的)</caption>
 <thead>
 <th colspan="5">Cloud Foundry エンタープライズ環境の管理 (試験的)</th>
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

CFEE 環境をリストします。

```
ibmcloud cfee environments
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

CFEE 環境の詳細を表示します。

```
ibmcloud cfee environment NAME [--id]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
  <dl>
   <dt>--id</dt>
   <dd>ID のみを表示します。</dd>
  </dl>

<strong>例</strong>:

CFEE 環境 env_example の詳細を表示します。

```
ibmcloud cfee environment env_example
```

CFEE 環境 env_example の ID を表示します。

```
ibmcloud cfee environment env_example --id
```
