---

copyright:
  years: 2020
lastupdated: "2020-09-23"

keywords: HA for IBM Cloud CLI, DR for IBM Cloud CLI, high availability for IBM Cloud CLI, disaster recovery for IBM Cloud CLI, failover for IBM Cloud CLI

subcollection: cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}

# Understanding high availability and disaster recovery for the {{site.data.keyword.cloud_notm}} CLI
{: #ha-dr}

{{site.data.keyword.cloud}} provides a service for hosting the {{site.data.keyword.cloud}} Command Line Interface and plug-ins. The {{site.data.keyword.cloud_notm}} CLI follows the practices that are described in [How IBM Cloud ensures high availability and disaster recovery](/docs/overview?topic=overview-zero-downtime).
{: shortdesc}

This service is hosted in the Dallas (`us-south`) and Frankfurt (`eu-de`) regions, which are collectively served by a global endpoint. Each location has three different data centers for redundancy. The data for each location is kept in the data centers near that location. If all the data centers in a location fail, the {{site.data.keyword.cloud_notm}} CLI is still operational on the client's on-premise installation. At that point, region failover ensures that installation and updates can continue.
