---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandos da CLI para gerenciamento de ambientes corporativos do Cloud Foundry (experimental)
{: #ibmcloud_commands_cfee}

<table summary="Manage Cloud Foundry Enterprise Environments (experimental)">
<caption>Tabela 1. Gerenciar ambientes corporativos do Cloud Foundry (experimental)</caption>
 <thead>
 <th colspan="5">Gerenciar Cloud Foundry Enterprise Environments (experimental)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee ambientes](ic_cli_cfee_cli.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee ambiente](ic_cli_cfee_cli.html#ibmcloud_cfee_environment)</td>
 </tr>
 </tbody>
 </table>
 
 ### Ambientes cfee ibmcloud
{: #ibmcloud_cfee_environments}

Lista de ambientes CFEE.

```
Ambientes cfee ibmcloud
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

### Ambiente cfee ibmcloud
{: #ibmcloud_cfee_environment}

Mostrar detalhes de um ambiente CFEE.

```
ibmcloud cfee environment NAME [--id]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>--id</dt>
   <dd>Mostrar somente o ID.</dd>
  </dl>

<strong>Exemplos</strong>:

Mostrar detalhes de um ambiente CFEE env_example:

```
ibmcloud cfee environment env_example
```

Mostrar ID de um ambiente CFEE env_example:

```
ibmcloud cfee environment env_example --id
```
