---



copyright:

  years: 2015，2016

lastupdated: "2016-10-24"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# CLI e strumenti di sviluppo
{: #cli}

Con {{site.data.keyword.Bluemix_short}}, hai accesso a potenti strumenti, quali un'interfaccia riga di comando unificata e i plug-in delle CLI. Ciascuno di questi download di CLI è disponibile a supporto della tua esperienza {{site.data.keyword.Bluemix_notm}}.
{:shortdesc}

## ![](./images/CLI.svg) Interfacce riga di comando
{: #downloads}

Scarica e installa le interfacce riga di comando a supporto della tua esperienza {{site.data.keyword.Bluemix_notm}}.

Lo strumento riga di comando cf Cloud Foundry è un prerequisito per tutti gli altri strumenti CLI {{site.data.keyword.Bluemix_notm}}. Lo strumento riga di comando {{site.data.keyword.Bluemix_notm}} fornisce un'esperienza ampliata per gestire il tuo ambiente {{site.data.keyword.Bluemix_notm}} oltre le applicazioni Cloud Foundry.

Questi strumenti CLI utilizzano entrambi la porta 443 per impostazione predefinita. Se è presente un proxy tra gli strumenti CLI e l'ambiente {{site.data.keyword.Bluemix_notm}}, devi configurare la variabile di ambiente `http-proxy` con la porta e l'url del proxy HTTP attuali se presenti. Per ulteriori dettagli, consulta [Utilizzo della CLI con un server proxy HTTP](http://docs.cloudfoundry.org/cf-cli/http-proxy.html){: new_window}.


| *{{site.data.keyword.Bluemix_notm}}: bx* | *Cloud Foundry: cf* |
|---------------------|---------------|
| [Scarica CLI](http://clis.ng.bluemix.net/) <br> [Visualizza documenti](./reference/bluemix_cli/index.html)|  [Scarica CLI](https://github.com/cloudfoundry/cli/releases){: new_window}  <br> [Visualizza documenti](./reference/cfcommands/index.html) |


## ![](./images/CLI_Plugin.svg) Plug-in di interfaccia riga di comando

Estendi facilmente la tua interfaccia riga di comando {{site.data.keyword.Bluemix_notm}} con più comandi. Per accedere ai plug-in di interfaccia
riga di comando {{site.data.keyword.Bluemix_notm}}, vedi [ CLI Plug-in Repository](https://plugins.ng.bluemix.net/).

### Estendi la tua interfaccia riga di comando {{site.data.keyword.Bluemix_notm}}: bx
{: cli_bluemix_ext}

* Per installare i plug-in CLI {{site.data.keyword.Bluemix_notm}} dal registro {{site.data.keyword.Bluemix_notm}}, imposta l'endpoint di registro di plug-in:

```
bluemix plugin repo-add bluemix-bx https://plugins.ng.bluemix.net
```
{: codeblock}

* Immetti quindi il seguente comando per installare un plug-in:

```
bluemix plugin install plugin_name -r bluemix-bx
```
{: codeblock}


| *{{site.data.keyword.activedeployshort}} CLI* | *{{site.data.keyword.autoscaling}} CLI* | *Network Security Groups* |
|-----|-----|-----|
| Nome del plug-in: active-deploy <br> [Visualizza documenti](/docs/services/ActiveDeploy/cli.html#cli) | Nome del plug-in: auto-scaling <br> [Visualizza documenti](./plugins/auto-scaling/index.html) |  Nome del plug-in: nsg <br> [Visualizza documenti](./plugins/networksecuritygroups/index.html)  |


### Estendi la tua interfaccia riga di comando Cloud Foundry: cf
{: cli_cf_ext}

* Per installare i plug-in CLI dal registro {{site.data.keyword.Bluemix_notm}}, imposta l'endpoint di registro di plug-in:

```
cf add-plugin-repo bluemix-cf https://plugins.ng.bluemix.net
```
{: codeblock}

* Immetti quindi il seguente comando per installare un plug-in:

```
cf install-plugin plugin_name -r bluemix-cf
```
{: codeblock}


| *Active Deploy* | *Console di gestione* |
|-----------------|-----------------|
| Nome del plug-in: active-deploy <br>  [Visualizza documenti](/docs/services/ActiveDeploy/cli.html#cli) |  Nome del plug-in: bluemix-admin <br> [Visualizza documenti](/docs/cli/plugins/bluemix_admin/index.html) |

| *{{site.data.keyword.IBM}} Containers for {{site.data.keyword.Bluemix_notm}}* | *VPN* |
|-----------------|-----------------|
| Nome del plug-in: ibm-containers <br> [Visualizza documenti](https://www.{DomainName}/docs/containers/container_cli_cfic.html#container_cli_cfic) | Nome del plug-in: VPN <br> [Visualizza documenti](./plugins/vpn/index.html) |


## ![](./images/Integrated_Dev_Tools.svg) Strumenti di sviluppo integrati

Scarica e installa i plug-in per integrare i tuoi servizi {{site.data.keyword.Bluemix_notm}} preferiti.

| *{{site.data.keyword.jazzhub_short}}* | *Liberty for Java* | *MobileFirst* | *{{site.data.keyword.rules_short}}* |
|-------------|----------|----------|----------|
| [Plug-in Eclipse Egit](https://hub.jazz.net/docs/reference/gitclient/#eclipse_using_egit){: new_window} <br> [Plug-in Eclipse RTC](https://hub.jazz.net/docs/reference/gitclient/#eclipse_using_rtc){: new_window} | [Plug-in Eclipse Liberty](https://developer.ibm.com/wasdev/downloads/liberty-profile-using-eclipse/){: new_window} | [Plug-in Eclipse](https://marketplace.eclipse.org/content/ibm-mobilefirst-platform-studio){: new_window} | [Plug-in Eclipse Rules Designer](/docs/services/rules/index.html#rulov002) |
