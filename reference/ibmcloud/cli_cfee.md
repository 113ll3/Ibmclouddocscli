---

copyright:

  years: 2018


lastupdated: "2018-08-20"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing Cloud Foundry Enterprise Environments (experimental)
{: #ibmcloud_commands_cfee}

<table summary="Manage Cloud Foundry Enterprise Environments (experimental)">
<caption>Table 1. Manage Cloud Foundry Enterprise Environments (experimental)</caption>
 <thead>
 <th colspan="5">Manage Cloud Foundry Enterprise Environments (experimental)</th>
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

List CFEE environments.

```
ibmcloud cfee environments
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:

### ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Show details of a CFEE environment.

```
ibmcloud cfee environment NAME [--id]
```

<strong>Prerequisites</strong>:  Endpoint, Login

<strong>Command options</strong>:
  <dl>
   <dt>--id</dt>
   <dd>Show ID only.</dd>
  </dl>

<strong>Examples</strong>:

Show details of a CFEE environment env_example:

```
ibmcloud cfee environment env_example
```

Show id of a CFEE environment env_example:

```
ibmcloud cfee environment env_example --id
```
