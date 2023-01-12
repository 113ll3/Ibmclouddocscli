---

copyright:
  years: 2020, 2021
lastupdated: "2021-12-15"

keywords: HA for IBM Cloud CLI, DR for IBM Cloud CLI, high availability for IBM Cloud CLI, disaster recovery for IBM Cloud CLI, failover for IBM Cloud CLI

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Understanding high availability and disaster recovery for the {{site.data.keyword.cloud_notm}} CLI
{: #ha-dr}

{{site.data.keyword.cloud}} provides storage of {{site.data.keyword.cloud_notm}} CLI binary files, plug-ins, and metadata that is used by the {{site.data.keyword.cloud_notm}} CLI and the IBM-provided CLI installers. The {{site.data.keyword.cloud_notm}} CLI follows the practices that are described in [How IBM Cloud ensures high availability and disaster recovery](/docs/overview?topic=overview-zero-downtime).
{: shortdesc}

The CLI binary data and metadata are stored in a US cross-regional {{site.data.keyword.cos_full_notm}} instance. If the cross-regional {{site.data.keyword.cos_short}} instance is unavailable at any time, the {{site.data.keyword.cloud_notm}} CLI is still operational on the client's on-premises installation. 

The {{site.data.keyword.cloud_notm}} CLI does not store user data.
{: note}
