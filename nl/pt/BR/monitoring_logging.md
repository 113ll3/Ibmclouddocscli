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

# Monitoramento e criação de log em
{{site.data.keyword.cloud_notm}}
{: #monitoring_logging}

## Monitoramento
{: #cloud-monitoring}

O {{site.data.keyword.cloud}}, por padrão, coleta e exibe métricas para uso de CPU, utilização de memória e E/S de rede para o {{site.data.keyword.containershort_notm}}. É possível usar o serviço {{site.data.keyword.monitoringlong_notm}} no {{site.data.keyword.cloud_notm}} para coletar automaticamente e medir as métricas de chave de seu ambiente e dos aplicativos. Nenhuma instrumentação especial é necessária para coletar métricas.

Para obter mais informações, veja [Monitoramento no {{site.data.keyword.cloud_notm}}](/docs/services/cloud-monitoring?topic=cloud-monitoring-monitoring_ov#monitoring_ov).

## Registro de log
{: #cloud-logging}

O {{site.data.keyword.cloud_notm}}, por padrão, coleta e exibe os logs para seus apps, tempos de execução de apps e tempos de execução de cálculo nos quais esses apps são executados. Os recursos de criação de log do {{site.data.keyword.cloud_notm}} são integrados na plataforma e a coleção de dados é ativada automaticamente para recursos em nuvem. 

O serviço {{site.data.keyword.loganalysisfull_notm}} fornece serviços de coleção de logs e de procura de log para a plataforma {{site.data.keyword.cloud_notm}}, coletando automaticamente dados do aplicativo e dos serviços do {{site.data.keyword.cloud_notm}} de serviços selecionados. Use o serviço {{site.data.keyword.loganalysisshort}} para expandir suas capacidades de coleção de logs, retenção de log e procura de log quando você está trabalhando com logs.

Para obter mais informações, consulte [Efetuando login no {{site.data.keyword.cloud_notm}}](/docs/services/CloudLogAnalysis?topic=cloudloganalysis-log_analysis_ov#log_analysis_ov).
