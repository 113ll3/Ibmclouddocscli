---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, monitoring, logging, cloud logging, metrics, monitor cpu, monitor usage, memory utilization, runtime logging

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:pre: .pre}

# Supervisión y registro en {{site.data.keyword.cloud_notm}}
{: #monitoring_logging}

## Supervisión
{: #cloud-monitoring}

{{site.data.keyword.cloud}}, de forma predeterminada, recopila y muestra las medidas correspondientes a uso de CPU, utilización de memoria y E/S de red para {{site.data.keyword.containershort_notm}}. Puede utilizar el servicio {{site.data.keyword.monitoringlong_notm}} en {{site.data.keyword.cloud_notm}} para recopilar y calcular automáticamente medidas clave del entorno y las aplicaciones. No se requiere ninguna instrumentación especial para recopilar medidas.

Para obtener más información, consulte el apartado [Supervisión en {{site.data.keyword.cloud_notm}}](/docs/services/cloud-monitoring?topic=cloud-monitoring-monitoring_ov#monitoring_ov).

## Registro
{: #cloud-logging}

De forma predeterminada, {{site.data.keyword.cloud_notm}} recopila y muestra los registros correspondientes a sus apps, tiempos de ejecución de apps y tiempos de ejecución del sistema en el que se ejecutan dichas apps. Las funciones de registro de {{site.data.keyword.cloud_notm}} están integradas en la plataforma y la recopilación de datos se habilita automáticamente para los recursos de la nube. 

El servicio {{site.data.keyword.loganalysisfull_notm}} proporciona los servicios de recopilación y de búsqueda de registros para la plataforma de {{site.data.keyword.cloud_notm}}, recopilando automáticamente los datos de servicios de {{site.data.keyword.cloud_notm}} y de aplicaciones desde los servicios de selección. Utilice el servicio {{site.data.keyword.loganalysisshort}} para ampliar su recopilación, la retención y las capacidades de búsqueda de registros al trabajar con registros.

Para obtener más información, consulte [Inicio de sesión en {{site.data.keyword.cloud_notm}}](/docs/services/CloudLogAnalysis?topic=cloudloganalysis-log_analysis_ov#log_analysis_ov).
