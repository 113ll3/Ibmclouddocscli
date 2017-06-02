---



copyright:

  years: 2015, 2017

lastupdated: "2017-01-16"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# VPN plug-in for Bluemix CLI
{: #vpn_plugin}

*Version:* 1.5.1

You can use the command line interface (CLI) to configure and manage your {{site.data.keyword.vpn_full}} service. The {{site.data.keyword.vpn_short}} CLI plug-in is available in two versions: one for use with the {{site.data.keyword.Bluemix}} CLI plug-in and the other for use with the Cloud Foundry CLI plug-in. Both versions of the plug-in provide the same functionality. The following instructions are for working with the {{site.data.keyword.Bluemix_notm}} CLI plug-in. To use the plug-in with the Cloud Foundry (cf) CLI plug-in, see [{{site.data.keyword.vpn_short}} CLI plug-in for cf CLI](/docs/cli/plugins/vpn/index.html).
{:shortdesc}

The {{site.data.keyword.vpn_short}} plug-in is available for Windows, MAC, and Linux operating systems. Ensure that you use the one that is applicable to you.

To get started, install the IBM Bluemix CLI. See
[Bluemix CLI](/docs/cli/reference/bluemix_cli/index.html) for details.

## Install the VPN plug-in

You can install the {{site.data.keyword.vpn_short}} plug-in locally or from the {{site.data.keyword.Bluemix_notm}} plugin repository.

**Note:** If you have a previous version of the plug-in installed, you need to uninstall it by running the following command:

```
bluemix plugin uninstall vpn
```

### Install locally

Download the {{site.data.keyword.vpn_short}} plug-in for your platform from the [IBM Bluemix CLI plug-in repository ![External link icon](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/repository.html#bluemix-plugins){: new_window}.

Install the {{site.data.keyword.vpn_short}} plug-in by using the following command:

**Note**: Either switch to the location of the plug-in or specify the path to the plug-in location.

* For Microsoft Windows OS:

```
bluemix plugin install bx_vpn_win_v1.5.1.exe
```

* For Apple MAC OS:

```
bluemix plugin install bx_vpn_mac_v1.5.1
```

* For Linux OS:

```
bluemix plugin install bx_vpn_linux_v1.5.1
```

**Note**: While you are installing the plug-in for Linux OS, if you see an error message that shows permission is denied, then run the following command and change the permissions:

```
chmod a+x ./bx_vpn_linux_v1.5.1
```

### Install from Bluemix repository

Take the following steps to install the plug-in from the {{site.data.keyword.Bluemix_notm}} repository:

1. Add the {{site.data.keyword.Bluemix_notm}} plug-in registry endpoint:
	```
	bluemix plugin repo-add bluemix-bx http://plugins.stage1.ng.bluemix.net
	```

2. Run the following command:

	```
	bluemix plugin install vpn -r bluemix-bx
	```

## IBM VPN commands

The following commands are supported by the {{site.data.keyword.vpn_short}} plug-in for Bluemix CLI. Use the `bluemix vpn` command to see the list of available commands. Use the `bluemix vpn help [command]` to see more information of a specific command.

**Note:** *Prerequisites* list the actions that are required before using the command. Prerequisites might include one or more of the following actions:
<dl>
<dt>**Endpoint**</dt>
<dd>An API endpoint must be set through the `bluemix api` before using the command.</dd>
<dt>**Login**</dt>
<dd>Login by using the `bluemix login` command is required before using this command.</dd>
<dt>**Target**</dt>
<dd>The `bluemix target` command must be used to set an org and space before using this command.</dd>
</dl>

<table summary="Alphabetically ordered VPN connection commands that have links that bring you to more info for the command">
<caption>Table 1. VPN connection commands</caption>
 <thead>
 <th colspan="5">VPN connection commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix vpn connection](/docs/cli/plugins/bx_vpn/index.html#vpn_connection)</td>
 <td>[bluemix vpn connections](/docs/cli/plugins/bx_vpn/index.html#vpn_connections)</td>
 <td>[bluemix vpn connection-create](/docs/cli/plugins/bx_vpn/index.html#vpn_connection_create)</td>
 <td>[bluemix vpn connection-delete](/docs/cli/plugins/bx_vpn/index.html#vpn_connection_delete)</td>
 <td>[bluemix vpn connection-update](/docs/cli/plugins/bx_vpn/index.html#vpn_connection_update)</td>
 </tr>
   </tbody>
 </table>

<table summary="Alphabetically ordered VPN gateway commands that have links that bring you to more info for the command">
 <caption>Table 2. VPN gateway commands</caption>
  <thead>
  <th colspan="5">VPN gateway commands</th>
  </thead>
  <tbody>
  <tr>
  <td>[bluemix vpn gateway](/docs/cli/plugins/bx_vpn/index.html#vpn_gateway)</td>
  <td>[bluemix vpn gateways](/docs/cli/plugins/bx_vpn/index.html#vpn_gateways)</td>
  <td>[bluemix vpn gateway-create](/docs/cli/plugins/bx_vpn/index.html#vpn_gateway_create)</td>
  <td>[bluemix vpn gateway-delete](/docs/cli/plugins/bx_vpn/index.html#vpn_gateway_delete)</td>
  <td>[bluemix vpn gateway-update](/docs/cli/plugins/bx_vpn/index.html#vpn_gateway_update)</td>
  </tr>
    </tbody>
  </table>

<table summary="Alphabetically ordered VPN ike commands that have links that bring you to more info for the command">
    <caption>Table 3. VPN ike commands</caption>
     <thead>
     <th colspan="5">VPN ike commands</th>
     </thead>
     <tbody>
     <tr>
     <td>[bluemix vpn ike](/docs/cli/plugins/bx_vpn/index.html#vpn_ike)</td>
     <td>[bluemix vpn ikes](/docs/cli/plugins/bx_vpn/index.html#vpn_ikes)</td>
     <td>[bluemix vpn ike-create](/docs/cli/plugins/bx_vpn/index.html#vpn_ike_create)</td>
     <td>[bluemix vpn ike-delete](/docs/cli/plugins/bx_vpn/index.html#vpn_ike_delete)</td>
     <td>[bluemix vpn ike-update](/docs/cli/plugins/bx_vpn/index.html#vpn_ike_update)</td>
     </tr>
       </tbody>
  </table>

<table summary="Alphabetically ordered VPN ipsec commands that have links that bring you to more info for the command">
  <caption>Table 4. VPN ipsec commands</caption>
   <thead>
   <th colspan="5">VPN ipsec commands</th>
   </thead>
   <tbody>
   <tr>
   <td>[bluemix vpn ipsec](/docs/cli/plugins/bx_vpn/index.html#vpn_ipsec)</td>
   <td>[bluemix vpn ipsecs](/docs/cli/plugins/bx_vpn/index.html#vpn_ipsecs)</td>
   <td>[bluemix vpn ipsec-create](/docs/cli/plugins/bx_vpn/index.html#vpn_ipsec_create)</td>
   <td>[bluemix vpn ipsec-delete](/docs/cli/plugins/bx_vpn/index.html#vpn_ipsec_delete)</td>
   <td>[bluemix vpn ipsec-update](/docs/cli/plugins/bx_vpn/index.html#vpn_ipsec_update)</td>
   </tr>
     </tbody>
</table>


### bluemix vpn connection
{: #vpn_connection}

Display all information about a particular connection.

```
bluemix vpn connection NAME
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the connection to be displayed.</dd>
    </dl>

### bluemix vpn connections
{: #vpn_connections}

Display all the current connections.

```
bluemix vpn connections
```

**Prerequisites**:  Endpoint, Login, Target

### bluemix vpn connection-create
{: #vpn_connection_create}

Creates a VPN connection.

```
bluemix vpn connection-create NAME -g GATEWAY -k PRESHARED_KEY -subnets ["192.168.10.0/24","1.1.1.0/24"] -cip CUSTOMER_GATEWAY_IP [-d DESCRIPTION] [-peer_id PEER_ID] [-admin_state UP_DOWN] [-dpd-action TIMEOUT_ACTION] [-gateway_ip GATEWAY_IP] [-i INITIATOR] [-dpd-timeout TIMEOUT] [-dpd-interval TIME_INTERVAL] [-ike IKE_POLICY] [-ipsec IPSEC_POLICY]
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the connection.</dd>
   <dt>-g GATEWAY</dt>
   <dd>Required. Name of the gateway.</dd>
   <dt>-k PRESHARED_KEY</dt>
   <dd>Required. Preshared key.</dd>
   <dt>-subnets ["192.168.10.0/24","1.1.1.0/24"]</dt>
   <dd>Required. Remote subnet address in CIDR format.</dd>
   <dt>-cip CUSTOMER_GATEWAY_IP</dt>
   <dd>Required. Remote endpoint IP address of the VPN tunnel.</dd>
   <dt>-d DESCRIPTION</dt>
   <dd>Optional. Description of the parameters specified.</dd>
   <dt>-peer_id PEER_ID</dt>
   <dd>Optional. ID of the remote peer. Another endpoint of the VPN tunnel.</dd>
   <dt>-admin_state UP_DOWN</dt>
   <dd>Optional. Status of the VPN connection. Valid value is <code>UP</code> or <code>DOWN</code>.</dd>
   <dt>-dpd-action TIMEOUT_ACTION</dt>
   <dd>Optional. Action to be taken when the peer is detected as dead. Valid value is <code>hold</code>, <code>clear</code>, <code>disabled</code>, <code>restart</code> or <code>restart-by-peer</code>. Default value is <code>hold</code>.</dd>
   <dt>-gateway_ip GATEWAY_IP</dt>
   <dd>Optional. IP address of the local VPN tunnel endpoint.</dd>
   <dt>-i INITIATOR</dt>
   <dd>Optional. State of the initiator. Default value is <code>bi-directional</code>.</dd>
   <dt>-dpd-timeout TIMEOUT</dt>
   <dd>Optional. Timeout value in seconds after which the session is terminated. Range: 6 - 86400 seconds. Default value is <code>120</code> seconds.</dd>
   <dt>-dpd-interval TIME_INTERVAL</dt>
   <dd>Optional. Keepalive interval in seconds. Send keepalive messages at the configured interval to check liveliness of the peer. Range: 5-86399 seconds. Default value is <code>15</code> seconds.</dd>
   <dt>-ike IKE_POLICY</dt>
   <dd>Optional. Name of the IKE policy.</dd>
   <dt>-ipsec IPSEC_POLICY</dt>
   <dd>Optional. Name of the IPSec policy.</dd>
    </dl>

**Examples**:

Create a new vpn connection with name `my_connection`:

```
bluemix vpn connection-create my_connection -g my_gateway -k 123456 -subnets "192.168.10.0/24" -cip 162.135.1.1
```

### bluemix vpn connection-delete
{: #vpn_connection_delete}

Deletes an existing connection.

```
bluemix vpn connection-delete CONNECTION_NAME
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>CONNECTION_NAME</dt>
   <dd>Required. Name of the connection to be deleted.</dd>
    </dl>

### bluemix vpn connection-update
{: #vpn_connection_update}

Updates an existing VPN connection.

```
bluemix vpn connection-update NAME [-n NAME] [-g GATEWAY] [-k PRESHARED_KEY] [-cip CUSTOMER_GATEWAY_IP] -subnets ["192.168.10.0/24","1.1.1.0/24"] [-i INITIATOR] [-d DESCRIPTION] [-peer_id PEER_ID] [-admin_state UP_DOWN] [-dpd-action TIMEOUT_ACTION] [-gateway_ip GATEWAY_IP] [-dpd-timeout TIMEOUT] [-dpd-interval TIME_INTERVAL] [-ike IKE_POLICY] [-ipsec IPSEC_POLICY]
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the connection.</dd>
   <dt>-n NAME</dt>
   <dd>Optional. New name of the connection.</dd>
   <dt>-g GATEWAY</dt>
   <dd>Optional. Name of the gateway.</dd>
   <dt>-k PRESHARED_KEY</dt>
   <dd>Optional. Preshared key.</dd>
   <dt>-cip CUSTOMER_GATEWAY_IP</dt>
   <dd>Optional. Remote endpoint IP address of the VPN tunnel.</dd>
   <dt>-subnets ["192.168.10.0/24","1.1.1.0/24"]</dt>
   <dd>Optional. Subnet address in CIDR format.</dd>
   <dt>-i INITIATOR</dt>
   <dd>Optional. State of the initiator.</dd>
   <dt>-d DESCRIPTION</dt>
   <dd>Optional. Description of the parameters specified.</dd>
   <dt>-peer_id PEER_ID</dt>
   <dd>Optional. ID of the remote peer. Another endpoint of the VPN tunnel.</dd>
   <dt>-admin_state UP_DOWN</dt>
   <dd>Optional. Status of the VPN connection. Valid value is <code>UP</code> or <code>DOWN</code>.</dd>
   <dt>-dpd-action TIMEOUT_ACTION</dt>
   <dd>Optional. Action to be taken when the peer is detected as dead. Valid value is <code>hold</code>, <code>clear</code>, <code>disabled</code>, <code>restart</code> or <code>restart-by-peer</code>.</dd>
   <dt>-gateway_ip GATEWAY_IP</dt>
   <dd>Optional. IP address of the local VPN tunnel endpoint.</dd>
   <dt>-dpd-timeout TIMEOUT</dt>
   <dd>Optional. Timeout value in seconds after which the session is terminated. Range: 6 - 86400 seconds.</dd>
   <dt>-dpd-interval TIME_INTERVAL</dt>
   <dd>Optional. Keepalive interval in seconds. Send keepalive messages at the configured interval to check liveliness of the peer. Range: 5-86399 seconds.</dd>
   <dt>-ike IKE_POLICY</dt>
   <dd>Optional. Name of the IKE policy.</dd>
   <dt>-ipsec IPSEC_POLICY</dt>
   <dd>Optional. Name of the IPSec policy.</dd>
</dl>

### bluemix vpn gateway
{: #vpn_gateway}

Display connection information about a gateway.

```
bluemix vpn gateway NAME
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the connection to be displayed.</dd>
    </dl>

### bluemix vpn gateways
{: #vpn_gateways}

List all the current gateways.

```
bluemix vpn gateways
```

**Prerequisites**:  Endpoint, Login, Target

### bluemix vpn gateway-create
{: #vpn_gateway_create}

Creates a VPN gateway.

```
bluemix vpn gateway-create NAME -t TYPE [-gateway_ip GATEWAY_IP] [-subnets SUBNETS]
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the gateway.</dd>
   <dt>-t TYPE</dt>
   <dd>Required. Containers for which you want to enable the service. Valid value is <code>allSingleContainers</code>, <code>allContainerGroups</code>, or <code>allContainers</code>. No default value; you must specify a type.</dd>
   <dt>-gateway_ip GATEWAY_IP</dt>
   <dd>Optional. IP address of the gateway.</dd>
   <dt>-subnets SUBNETS</dt>
   <dd>Optional. Subnet address in CIDR format.</dd>
</dl>

**Examples**:

Create a gateway with name `my_gateway` and type `allContainerGroups`:

```
bluemix vpn gateway-create my_gateway -t allContainerGroups
```

### bluemix vpn gateway-delete
{: #vpn_gateway_delete}

Deletes an existing gateway.

```
bluemix vpn gateway-delete NAME
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
<dl>
   <dt>NAME</dt>
   <dd>Required. Name of the gateway to be deleted.</dd>
</dl>

### bluemix vpn gateway-update
{: #vpn_gateway_update}

Updates an existing VPN gateway.

```
bluemix vpn gateway-update [-n NAME] [-t TYPE] [-gateway_ip GATEWAY_IP] [-subnets SUBNETS]
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the gateway.</dd>
   <dt>-n NAME</dt>
   <dd>Required. New name of the gateway.</dd>
   <dt>-t TYPE</dt>
   <dd>Optional. Containers for which you want to enable the service. Valid value is <code>allSingleContainers</code>, <code>allContainerGroups</code>, or <code>allContainers</code>.</dd>
   <dt>-gateway_ip GATEWAY_IP</dt>
   <dd>Optional. IP address of the gateway.</dd>
   <dt>-subnets SUBNETS</dt>
   <dd>Optional. Subnet address in CIDR format.</dd>
</dl>

### bluemix vpn ike
{: #vpn_ike}

Display information about a IKE policy.

```
bluemix vpn ike NAME
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the IKE policy to be displayed.</dd>
</dl>

### bluemix vpn ikes
{: #vpn_ikes}

List all the current IKE policies.

```
bluemix vpn ikes
```

### bluemix vpn ike-create
{: #vpn_ike_create}

Create an IKE policy.

```
bluemix vpn ike-create NAME -g GATEWAY [-d DESCRIPTION] [-pfs PFS] [-e ENCRYPTION] [-lv LIFETIME(SECONDS)]
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the IKE policy.</dd>
   <dt>-g GATEWAY</dt>
   <dd>Required. Name of the gateway.</dd>
   <dt>-d DESCRIPTION</dt>
   <dd>Optional. Description of the parameters specified.</dd>
   <dt>-pfs PFS</dt>
   <dd>Optional. Diffie-Hellman (DH) group identifier. Valid value is <code>Group2</code>, <code>Group5</code> or <code>Group14</code>. Default value is <code>Group2</code>.</dd>
   <dt>-e ENCRYPTION</dt>
   <dd>Optional. Encryption algorithm. Valid value is <code>aes-128</code>, <code>aes-192</code>, <code>aes-256</code> or <code>3des</code>. Default value is <code>aes-128</code>.</dd>
   <dt>-lv LIFETIME(SECONDS)</dt>
   <dd>Optional. Lifetime value of the IKE security association. Range: 60 - 86400 seconds. Default value is <code>86400</code> seconds.</dd>
</dl>

**Examples**:

Create a new IKE policy with name `my_ike`:
```
bluemix vpn ike-create my_ike -g my_gateway
```

**Prerequisites**:  Endpoint, Login, Target

### bluemix vpn ike-delete
{: #vpn_ike_delete}

Delete an existing IKE policy.

```
bluemix vpn ike-delete NAME
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the IKE policy to be deleted.</dd>
</dl>

### bluemix vpn ike-update
{: #vpn_ike_update}

Updates an IKE policy.

```
bluemix vpn ike-update NAME [-n NAME] [-g GATEWAY] [-d DESCRIPTION] [-pfs PFS] [-e ENCRYPTION] [-lv LIFETIME(SECONDS)]
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the IKE policy.</dd>
   <dt>-n NAME</dt>
   <dd>Required. New name of the IKE policy.</dd>
   <dt>-g GATEWAY</dt>
   <dd>Optional. Name of the gateway.</dd>
   <dt>-d DESCRIPTION</dt>
   <dd>Optional. Description of the parameters specified.</dd>
   <dt>-pfs PFS</dt>
   <dd>Optional. Diffie-Hellman (DH) group identifier. Valid value is <code>Group2</code>, <code>Group5</code> or <code>Group14</code>.</dd>
   <dt>-e ENCRYPTION</dt>
   <dd>Optional. Encryption algorithm. Valid value is <code>aes-128</code>, <code>aes-192</code>, <code>aes-256</code> or <code>3des</code>.</dd>
   <dt>-lv LIFETIME(SECONDS)</dt>
   <dd>Optional. Lifetime value of the IKE security association. Range: 60 - 86400 seconds.</dd>
</dl>

### bluemix vpn ipsec
{: #vpn_ipsec}

Display information about an IPSec policy.

```
bluemix vpn ipsec NAME
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the IPSec policy to be displayed.</dd>
</dl>

### bluemix vpn ipsecs
{: #vpn_ipsecs}

List all the current IPSec connections.

```
bluemix vpn ipsecs
```

**Prerequisites**:  Endpoint, Login, Target

### bluemix vpn ipsec-create
{: #vpn_ipsec_create}

Create an IPSec policy.

```
bluemix vpn ipsec-create NAME -g GATEWAY [-d DESCRIPTION] [-pfs PFS] [-e ENCRYPTION] [-lv LIFETIME(SECONDS)]
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the IPSec policy.</dd>
   <dt>-g GATEWAY</dt>
   <dd>Required. Name of the gateway.</dd>
   <dt>-d DESCRIPTION</dt>
   <dd>Optional. Description of the parameters specified.</dd>
   <dt>-pfs PFS</dt>
   <dd>Optional. Diffie-Hellman (DH) group identifier. Valid value is <code>Group2</code>, <code>Group5</code> or <code>Group14</code>. Default value is <code>Group2</code>.</dd>
   <dt>-e ENCRYPTION</dt>
   <dd>Optional. Encryption algorithm. Valid value is <code>aes-128</code>, <code>aes-192</code>, <code>aes-256</code> or <code>3des</code>. Default value is <code>aes-128</code>.</dd>
   <dt>-lv LIFETIME(SECONDS)</dt>
   <dd>Optional. Lifetime value of the security association.. Range: 60 - 86400 seconds. Default value is <code>3600</code> seconds.</dd>
</dl>

**Examples**:

Create an IPSec policy with name `my_policy`:
```
bluemix vpn ipsec-create my_policy -g my_gateway
```

### bluemix vpn ipsec-delete
{: #vpn_ipsec_delete}

Delete an existing IPSec policy.

```
bluemix vpn ipsec-delete NAME
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the IPSec policy to be deleted.</dd>
</dl>

### bluemix vpn ipsec-update
{: #vpn_ipsec_update}

Updates an IPSec policy.

```
bluemix vpn ipsec-update NAME [-n NAME] [-g GATEWAY] [-d DESCRIPTION] [-pfs PFS] [-e ENCRYPTION] [-lv LIFETIME(SECONDS)]
```

**Prerequisites**:  Endpoint, Login, Target

<strong>Command options</strong>:
   <dl>
   <dt>NAME</dt>
   <dd>Required. Name of the IPSec policy.</dd>
   <dt>-n NAME</dt>
   <dd>Optional. New name of the IPSec policy.</dd>
   <dt>-g GATEWAY</dt>
   <dd>Optional. Name of the gateway.</dd>
   <dt>-d DESCRIPTION</dt>
   <dd>Optional. Description of the parameters specified.</dd>
   <dt>-pfs PFS</dt>
   <dd>Optional. Diffie-Hellman (DH) group identifier. Valid value is <code>Group2</code>, <code>Group5</code> or <code>Group14</code>.</dd>
   <dt>-e ENCRYPTION</dt>
   <dd>Optional. Encryption algorithm. Valid value is <code>aes-128</code>, <code>aes-192</code>, <code>aes-256</code> or <code>3des</code>.</dd>
   <dt>-lv LIFETIME(SECONDS)</dt>
   <dd>Optional. Lifetime value of the IKE security association. Range: 60 - 86400 seconds.</dd>
</dl>
