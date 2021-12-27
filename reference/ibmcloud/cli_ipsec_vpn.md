---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-15"

keywords: cli, classic infrastructure, ipsec, vpn, ibmcloud sl ipsec, tunnel, vpn access, encryption, vpn tunnel cli, ipsec vpn tunnel

subcollection: cli

---


{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing IPSec VPN tunnels (ibmcloud sl ipsec)
{: #sl-manage-ipsec-vpn-tunnels}

{{site.data.keyword.cloud}} VPN access allows users to manage all servers remotely and securely over the {{site.data.keyword.cloud_notm}} private network. A VPN connection from your location to the private network gives you the capability for out-of-band management and server rescue through an encrypted VPN tunnel.

Use the following commands from the {{site.data.keyword.cloud_notm}} Command Line Interface to manage IPSec VPN tunnels in the {{site.data.keyword.cloud_notm}} classic infrastructure IPSec VPN service.
{: shortdesc}

## ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

Cancel an IPSec VPN tunnel context:
```bash
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONS]
```

**Command options**:

--immediate
:   Cancel the IPSec immediately instead of on the billing anniversary.

--reason
:   An optional reason for cancellation.

-f, --force
:   Force operation without confirmation.

## ibmcloud sl ipsec config
{: #sl_ipsec_config}

Request configuration of a tunnel context:
```bash
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

## ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

List IPSec VPN tunnel context details:
```bash
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONS]
```

**Command options**:

-i, --include
:   Include extra resources. Options are: at,is,rs,sr,ss.

## ibmcloud sl ipsec list
{: #sl_ipsec_list}

List IPSec VPN tunnel contexts:
```bash
ibmcloud sl ipsec list [OPTIONS]
```

**Command options**:

--order
:   Filter by ID of the order that purchased the IPSec.


## ibmcloud sl ipsec order
{: #sl_ipsec_order}

Order an IPSec VPN tunnel:
```bash
ibmcloud sl ipsec order [OPTIONS]
```

**Command options**:

-d, --datacenter
:   Required. Short name of the datacenter for the IPSec. For example, `dal09`.

## ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Add a subnet to an IPSec tunnel context:
```bash
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONS]
```

**Command options**:

-s, --subnet-id
:   Subnet identifier to add, required.

-t, --subnet-type
:   Required. Subnet type to add. Options are: internal,remote,service.

-n, --network
:   Subnet network identifier to create.

## ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Remove a subnet from an IPSEC tunnel context:
```bash
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE
```

## ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

Add an address translation to an IPSec tunnel:
```bash
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

**Command options**:

-s, --static-ip
:   Required. Static IP address.

-r, --remote-ip
:   Required. Remote IP address.

-n, --note
:   Note.

## ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Remove a translation entry from an IPSec:
```bash
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID
```

## ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Update an address translation for an IPSec:
```bash
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

**Command options**:

-s, --static-ip
:   Required. Static IP address.

-r, --remote-ip
:   Required. Remote IP address.

-n, --note
:   Note.

## ibmcloud sl ipsec update
{: #sl_ipsec_update}

Update tunnel context properties:
```bash
ibmcloud sl ipsec update CONTEXT_ID [OPTIONS]
```

**Command options**:

-n, --name
:   Friendly name.

-r, --remote-peer
:   Remote peer IP address.

-k, --preshared-key
:   Preshared key.

-a, --phase1-auth
:   Phase 1 authentication. Options are: MD5, SHA1, SHA256.

-c, --phase1-crypto
:   Phase 1 encryption. Options are: DES, 3DES, AES128, AES192, AES256.

-d, --phase1-dh
:   Phase 1 Diffie-Hellman group. Options are: 0, 1, 2, 5.

-t, --phase1-key-ttl
:   Phase 1 key life. Range is `120-172800`.

-u, --phase2-auth
:   Phase 2 authentication. Options are: MD5, SHA1, SHA256.

-y, --phase2-crypto
:   Phase 2 encryption. Options are: DES, 3DES, AES128, AES192, AES256.

-e, --phase2-dh
:   Phase 2 Diffie-Hellman group. Options are: 0, 1, 2, 5.

-f, --phase2-forward-secrecy
:   Phase 2 perfect forward secrecy. Range is `0-1`.

-l, --phase2-key-ttl
:   Phase 2 key life. Range is `120-172800`.
