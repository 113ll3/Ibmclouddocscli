---

copyright:
  years: 2020, 2021
lastupdated: "2021-04-02"

keywords: HA for IBM Cloud CLI, DR for IBM Cloud CLI, high availability for IBM Cloud CLI, disaster recovery for IBM Cloud CLI, failover for IBM Cloud CLI

subcollection: cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:note: .note}
{:tip: .tip}

# Understanding high availability and disaster recovery for the {{site.data.keyword.cloud_notm}} CLI
{: #ha-dr}

{{site.data.keyword.cloud}} provides a service for hosting the {{site.data.keyword.cloud}} Command Line Interface and plug-ins. The {{site.data.keyword.cloud_notm}} CLI follows the practices that are described in [How IBM Cloud ensures high availability and disaster recovery](/docs/overview?topic=overview-zero-downtime).
{: shortdesc}

This service is hosted in the Dallas (`us-south`) and Frankfurt (`eu-de`) regions, which are collectively served by a global endpoint. The CLI binary data is stored in a cross-regional {{site.data.keyword.cos_full_notm}} instance. If the service in one region fails, the {{site.data.keyword.cloud_notm}} CLI is still operational on the client's on-premise installation. At that point, region failover ensures that installation and updates can continue.

The {{site.data.keyword.cloud_notm}} CLI does not store user data.
{: note}
