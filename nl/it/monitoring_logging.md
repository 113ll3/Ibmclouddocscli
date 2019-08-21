---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-27"

keywords: cli, monitoring, logging, cloud logging, metrics, monitor cpu, monitor usage, memory utilization, runtime logging

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:pre: .pre}

# Monitoraggio e registrazione in {{site.data.keyword.cloud_notm}}
{: #monitoring_logging}

## Monitoraggio
{: #cloud-monitoring}

{{site.data.keyword.cloud}}, per impostazione predefinita, raccoglie e visualizza le metriche per l'utilizzo della CPU, l'utilizzo della memoria e l'I/O di rete per {{site.data.keyword.containershort_notm}}. Puoi utilizzare il servizio {{site.data.keyword.monitoringlong_notm}} in {{site.data.keyword.cloud_notm}} per raccogliere e misurare automaticamente le metriche chiave dal tuo ambiente e dalle tue applicazioni. Non è richiesta alcuna strumentazione speciale per raccogliere le metriche.

Per ulteriori informazioni, vedi [Monitoraggio in {{site.data.keyword.cloud_notm}}](/docs/services/cloud-monitoring?topic=cloud-monitoring-monitoring_ov#monitoring_ov).

## Registrazione
{: #cloud-logging}

Per impostazione predefinita, {{site.data.keyword.cloud_notm}} raccoglie e visualizza i log per le tue applicazioni, i runtime delle applicazioni e i runtime di calcolo in cui queste applicazioni vengono eseguite. Le funzionalità di registrazione {{site.data.keyword.cloud_notm}} sono integrate nella piattaforma e la raccolta dei dati è abilitata automaticamente per le risorse cloud. 

Il servizio {{site.data.keyword.loganalysisfull_notm}} fornisce i servizi di raccolta e ricerca dei log per la piattaforma {{site.data.keyword.cloud_notm}}, raccogliendo in automatico l'applicazione e i dati dei servizi {{site.data.keyword.cloud_notm}} dai servizi selezionati. Utilizza il servizio {{site.data.keyword.loganalysisshort}} per espandere le tue funzionalità di raccolta, conservazione e ricerca dei log quando stai utilizzando i log.

Per ulteriori informazioni, vedi [Registrazione in {{site.data.keyword.cloud_notm}}](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-getting-started#getting-started).
