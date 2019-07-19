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

# Überwachung und Protokollierung in {{site.data.keyword.cloud_notm}}
{: #monitoring_logging}

## Überwachung
{: #cloud-monitoring}

{{site.data.keyword.cloud}} erfasst standardmäßig Metriken zur CPU-Auslastung, Speicherauslastung und Netzein-/-ausgabe für {{site.data.keyword.containershort_notm}} und zeigt diese an. Mithilfe des {{site.data.keyword.monitoringlong_notm}}-Service in {{site.data.keyword.cloud_notm}} können Sie Schlüsselmetriken aus Ihrer Umgebung und Ihren Anwendungen automatisch erfassen und messen. Zur Erfassung der Metriken ist keine spezielle Instrumentierung erforderlich.

Weitere Informationen finden Sie unter [Überwachung in {{site.data.keyword.cloud_notm}}](/docs/services/cloud-monitoring?topic=cloud-monitoring-monitoring_ov#monitoring_ov).

## Protokollierung
{: #cloud-logging}

{{site.data.keyword.cloud_notm}} erfasst standardmäßig Protokolle für Ihre Apps, App-Laufzeiten und Verarbeitungslaufzeiten, in denen diese Apps ausgeführt werden. Die {{site.data.keyword.cloud_notm}}-Protokollierungsfunktionen sind in die Plattform integriert und die Erfassung von Daten wird für Cloudressourcen automatisch aktiviert. 

Der {{site.data.keyword.loganalysisfull_notm}}-Service umfasst Protokollerfassungs- und Protokollsuchservices für die {{site.data.keyword.cloud_notm}}-Plattform zur automatischen Erfassung von Anwendungs- und {{site.data.keyword.cloud_notm}}-Servicedaten von ausgewählten Services. Nutzen Sie den {{site.data.keyword.loganalysisshort}}-Service, um Ihre Protokollerfassungs-, Protokollspeicherungs- und Protokollsuchfunktionen zu erweitern, wenn Sie mit Protokollen arbeiten.

Weitere Informationen finden Sie in [Protokollierung in {{site.data.keyword.cloud_notm}}](/docs/services/CloudLogAnalysis?topic=cloudloganalysis-log_analysis_ov#log_analysis_ov).
