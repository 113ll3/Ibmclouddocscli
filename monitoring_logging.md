---

copyright:
  years: 2018, 2020
lastupdated: "2020-06-05"

keywords: cli, monitoring, logging, cloud logging, metrics, monitor cpu, monitor usage, memory utilization, runtime logging

subcollection: cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:pre: .pre}

# Monitoring and logging in {{site.data.keyword.cloud_notm}}
{: #monitoring_logging}

By default, {{site.data.keyword.cloud}} collects metrics and logs that you can use to monitor your cloud environment and applications.
{: shortdesc}

## Monitoring
{: #cloud-monitoring}

{{site.data.keyword.cloud_notm}}, by default, collects and displays metrics for CPU usage, memory utilization, and network I/O for the {{site.data.keyword.containershort_notm}}. You can use the {{site.data.keyword.monitoringlong_notm}} service in {{site.data.keyword.cloud_notm}} to automatically collect and measure key metrics from your environment and applications. No special instrumentation is required to collect metrics.

For more information, see [Monitoring in {{site.data.keyword.cloud_notm}}](/docs/Monitoring-with-Sysdig?topic=Monitoring-with-Sysdig-getting-started).

## Logging
{: #cloud-logging}

{{site.data.keyword.cloud_notm}}, by default, collects and displays logs for your apps, apps runtimes, and compute runtimes where those apps run. {{site.data.keyword.cloud_notm}} logging capabilities are integrated in the platform and collection of data is automatically enabled for cloud resources. 

The {{site.data.keyword.loganalysisfull_notm}} service provides log collection and log search services for the {{site.data.keyword.cloud_notm}} platform, automatically collecting app and {{site.data.keyword.cloud_notm}} services’ data from select services. Use the {{site.data.keyword.loganalysisshort}} service to expand your log collection, log retention, and log search abilities when you're working with logs.

For more information, see [Logging in {{site.data.keyword.cloud_notm}}](/docs/Log-Analysis-with-LogDNA?topic=Log-Analysis-with-LogDNA-getting-started).
