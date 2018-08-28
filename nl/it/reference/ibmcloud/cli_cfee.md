---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione dei Cloud Foundry Enterprise Environment (sperimentale)
{: #ibmcloud_commands_cfee}

<table summary="Gestisci i Cloud Foundry Enterprise Environment (sperimentale)">
<caption>Tabella 1. Gestisci i Cloud Foundry Enterprise Environment (sperimentale)</caption>
 <thead>
 <th colspan="5">Gestisci i Cloud Foundry Enterprise Environment (sperimentale)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments
](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Elenca gli ambienti CFEE.

```
ibmcloud cfee environments
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Mostra i dettagli di un ambiente CFEE.

```
ibmcloud cfee environment NOME [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>--id</dt>
   <dd>Mostra solo l'ID.</dd>
  </dl>

<strong>Esempi</strong>:

Mostra i dettagli di un ambiente CFEE env_example:

```
ibmcloud cfee environment env_example
```

Mostra l'ID di un ambiente CFEE env_example:

```
ibmcloud cfee environment env_example --id
```
