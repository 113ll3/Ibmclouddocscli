---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, monitoring, logging, cloud logging, metrics, monitor cpu, monitor usage, memory utilization, runtime logging

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:pre: .pre}

# {{site.data.keyword.cloud_notm}} でのモニタリングとロギング
{: #monitoring_logging}

## モニタリング
{: #cloud-monitoring}

{{site.data.keyword.cloud}} は、デフォルトで、{{site.data.keyword.containershort_notm}} の CPU 使用量、メモリー使用量、およびネットワーク入出力のメトリックを収集して表示します。 {{site.data.keyword.cloud_notm}} で {{site.data.keyword.monitoringlong_notm}} サービスを使用すると、ご使用の環境およびアプリケーションから主要メトリックを自動的に収集し、測定することができます。 メトリックの収集には、特別な計測装置は必要ありません。

詳しくは、[{{site.data.keyword.cloud_notm}} でのモニタリング](/docs/services/cloud-monitoring?topic=cloud-monitoring-monitoring_ov#monitoring_ov)を参照してください。

## ロギング
{: #cloud-logging}

{{site.data.keyword.cloud_notm}} は、デフォルトで、アプリ、アプリ・ランタイム、およびそれらのアプリの実行場所であるコンピュート・ランタイムについて、ログの収集と表示を行います。 {{site.data.keyword.cloud_notm}} ロギング機能はプラットフォームに統合されており、クラウド・リソースに関するデータ収集は自動的に有効になります。 

{{site.data.keyword.loganalysisfull_notm}} サービスは、{{site.data.keyword.cloud_notm}} プラットフォーム用のログ収集サービスとログ検索サービスを提供し、アプリおよび {{site.data.keyword.cloud_notm}} サービスのデータを、選択したサービスから自動的に収集します。 {{site.data.keyword.loganalysisshort}} サービスを使用して、ログを処理する際のログ収集、ログ保存、およびログ検索の機能を拡張します。

詳しくは、[{{site.data.keyword.cloud_notm}} でのロギング](/docs/services/CloudLogAnalysis?topic=cloudloganalysis-log_analysis_ov#log_analysis_ov)を参照してください。
