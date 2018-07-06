---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CLI-Befehle für Cloud Foundry-Unternehmensumgebungen verwalten (experimentell)
{: #ibmcloud_commands_cfee}

<table summary="Cloud Foundry-Unternehmensumgebungen verwalten (experimentell)">
<caption>Tabelle 1. Cloud Foundry-Unternehmensumgebungen verwalten (experimentell)</caption>
 <thead>
 <th colspan="5">Cloud Foundry-Unternehmensumgebungen verwalten (experimentell)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](ic_cli_cfee_cli.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](ic_cli_cfee_cli.html#ibmcloud_cfee_environment)</td>
 </tr>
 </tbody>
 </table>
 
 ### ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

CFEE-Umgebungen auflisten

```
ibmcloud cfee environments
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>

### ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Details einer CFEE-Umgebung anzeigen

```
ibmcloud cfee environment NAME [--id]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen:</strong>
  <dl>
   <dt>--id</dt>
   <dd>Nur ID anzeigen</dd>
  </dl>

<strong>Beispiele</strong>:

Details der CFEE-Umgebung "env_example" anzeigen

```
ibmcloud cfee environment env_example
```

ID der CFEE-Umgebung "env_example" anzeigen

```
ibmcloud cfee environment env_example --id
```
