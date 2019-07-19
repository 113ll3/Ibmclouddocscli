---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-21"

keywords: monitoring, logging, cloud logging, metrics

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:pre: .pre}

# Surveillance et journalisation dans {{site.data.keyword.cloud_notm}}
{: #monitoring_logging}

## Surveillance
{: #cloud-monitoring}

Par défaut, {{site.data.keyword.cloud}} collecte et affiche des métriques de performance relatives à l'utilisation de l'unité centrale, à l'utilisation de la mémoire et aux entrées-sorties de réseau pour le service {{site.data.keyword.containershort_notm}}. Vous pouvez utiliser le service {{site.data.keyword.monitoringlong_notm}} dans {{site.data.keyword.cloud_notm}} pour collecter et mesurer automatiquement des métriques clés à partir de votre environnement et de vos applications. Aucune instrumentation spéciale n'est requise pour collecter les métriques.

Pour plus d'informations, voir [Surveillance dans {{site.data.keyword.cloud_notm}}](/docs/services/cloud-monitoring?topic=cloud-monitoring-monitoring_ov#monitoring_ov).

## Journalisation
{: #cloud-logging}

Par défaut, {{site.data.keyword.cloud_notm}} collecte et affiche des journaux pour vos applications, vos contextes d'exécution d'application et vos contexte d'exécution de calcul dans lesquels ces applications s'exécutent. Les capacités de journalisation d'{{site.data.keyword.cloud_notm}} sont intégrées dans la plateforme et la collecte de données est automatiquement activée pour les ressources de cloud. 

{{site.data.keyword.loganalysisfull_notm}} fournit des services de collecte de journaux et de recherche dans ceux-ci pour la plateforme {{site.data.keyword.cloud_notm}}, en collectant automatiquement des données d'application et de services {{site.data.keyword.cloud_notm}} depuis divers services. Vous pouvez utiliser le service {{site.data.keyword.loganalysisshort}} pour étendre vos fonctions de collecte de journaux, de conservation de journaux et de recherche de journaux lorsque vous utilisez des journaux.

Pour plus d'informations, voir [Journalisation dans {{site.data.keyword.cloud_notm}}](/docs/services/CloudLogAnalysis?topic=cloudloganalysis-log_analysis_ov#log_analysis_ov).
