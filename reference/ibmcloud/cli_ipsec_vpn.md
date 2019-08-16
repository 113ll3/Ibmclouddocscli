---

copyright:
  years: 2018, 2019
lastupdated: "2019-08-15"

keywords: cli, classic infrastructure, ipsec, vpn, ibmcloud sl ipsec, tunnel, vpn access, encryption, vpn tunnel cli, ipsec vpn tunnel

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing IPSec VPN tunnels
{: #sl-manage-ipsec-vpn-tunnels}

{{site.data.keyword.cloud}} VPN access allows users to manage all servers remotely and securely over the {{site.data.keyword.cloud_notm}} private network. A VPN connection from your location to the private network gives you the capability for out-of-band management and server rescue through an encrypted VPN tunnel.

Use the following commands to manage IPSec VPN tunnels in the {{site.data.keyword.cloud_notm}} classic infrastructure IPSec VPN service.
{: shortdesc}

## ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

Cancel a IPSec VPN tunnel context.
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--immediate</dt>
<dd>Cancel the IPSec immediately instead of on the billing anniversary.</dd>
<dt>--reason</dt>
<dd>An optional reason for cancellation.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl ipsec config
{: #sl_ipsec_config}

Request configuration of a tunnel context.
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

## ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

List IPSec VPN tunnel context details.
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-i, --include</dt>
<dd>Include extra resources, options are: at,is,rs,sr,ss.</dd>
</dl>

## ibmcloud sl ipsec list
{: #sl_ipsec_list}

List IPSec VPN tunnel contexts.
```
ibmcloud sl ipsec list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--order</dt>
<dd>Filter by ID of the order that purchased the IPSec.</dd>
</dl>

## ibmcloud sl ipsec order
{: #sl_ipsec_order}

Order a IPSec VPN tunnel.
```
ibmcloud sl ipsec order [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Required. Short name of the datacenter for the IPSec. For example, `dal09`.</dd>
</dl>

## ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Add a subnet to an IPSec tunnel context.
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --subnet-id</dt>
<dd>Subnet identifier to add, required.</dd>
<dt>-t, --subnet-type</dt>
<dd>Subnet type to add, required, options are: internal,remote,service.</dd>
<dt>-n, --network</dt>
<dd>Subnet network identifier to create.</dd>
</dl>

## ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Remove a subnet from an IPSEC tunnel context.
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

## ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

Add an address translation to an IPSec tunnel.
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Static IP address,required.</dd>
<dt>-r, --remote-ip</dt>
<dd>Remote IP address,required.</dd>
<dt>-n, --note</dt>
<dd>Note.</dd>
</dl>

## ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Remove a translation entry from an IPSec.
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

## ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Update an address translation for an IPSec.
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Static IP address,required.</dd>
<dt>-r, --remote-ip</dt>
<dd>Remote IP address,required.</dd>
<dt>-n, --note</dt>
<dd>Note.</dd>
</dl>

## ibmcloud sl ipsec update
{: #sl_ipsec_update}

Update tunnel context properties.
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Friendly name.</dd>
<dt>-r, --remote-peer</dt>
<dd>Remote peer IP address.</dd>
<dt>-k, --preshared-key</dt>
<dd>Preshared key.</dd>
<dt>-a, --phase1-auth</dt>
<dd>Phase 1 authentication. Options are: MD5,SHA1,SHA256.</dd>
<dt>-c, --phase1-crypto</dt>
<dd>Phase 1 encryption. Options are: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-d, --phase1-dh</dt>
<dd>Phase 1 Diffie-Hellman group. Options are: 0,1,2,5.</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>Phase 1 key life. Range is `120-172800`.</dd>
<dt>-u, --phase2-auth</dt>
<dd>Phase 2 authentication. Options are: MD5,SHA1,SHA256.</dd>
<dt>-y, --phase2-crypto</dt>
<dd>Phase 2 encryption. Options are: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-e, --phase2-dh</dt>
<dd>Phase 2 Diffie-Hellman group. Options are: 0,1,2,5.</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>Phase 2 perfect forward secrecy. Range is `0-1`.</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>Phase 2 key life. Range is `120-172800`.</dd>
</dl>
