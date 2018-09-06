---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Security

Use the following commands to manage {{site.data.keyword.Bluemix_notm}} infrastructure SSH Keys and Certificates.
{: shortdesc}

<table summary="Alphabetically ordered  {{site.data.keyword.Bluemix_notm}} infrastructure Security commands that have links that bring you to more info for the command">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl security sshkey-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_add)</td>
  <td>[ibmcloud sl security sshkey-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_edit)</td>
  <td>[ibmcloud sl security sshkey-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_list)</td>
  <td>[ibmcloud sl security sshkey-print](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_print)</td>
  <td>[ibmcloud sl security sshkey-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl security cert-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_add)</td>
  <td>[ibmcloud sl security cert-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_edit)</td>
  <td>[ibmcloud sl security cert-download](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_download)</td>
  <td>[ibmcloud sl security cert-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_list)</td>
  <td>[ibmcloud sl security cert-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

Add a new SSH key.
```
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --in-file</dt>
<dd>The id_rsa.pub file to import for this key.</dd>
<dt>-k, --key</dt>
<dd>The actual SSH key.</dd>
<dt>--note</dt>
<dd>Extra note that will be associated with key.</dd>
</dl>

**Examples**:
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
This command adds a SSH key from file: ~/.ssh/id_rsa.pub with a note "mykey".

## ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

Edit an SSH key.
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--label</dt>
<dd>The new label for the key.</dd>
<dt>--note</dt>
<dd>New notes for the key.</dd>
</dl>

**Examples**:
```
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
This command updates the SSH key with ID 12345678 and sets label to "Bluemix" and note to "testing".

## ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

List SSH keys on your account.
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--sortby</dt>
<dd>Column to sort by, options are: id,label,fingerprint,notes.</dd>
</dl>

**Examples**:
```
ibmcloud sl security sshkey-list --sortby label
```
This command lists all SSH keys on current account and sorts them by label.

## ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

Prints out an SSH key to the screen.
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --out-file</dt>
<dd>The public SSH key will be written to this file.</dd>
</dl>

**Examples**:
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
This command shows the ID, label and notes of SSH key with ID 12345678 and write the public key to file: ~/mykey.pub.

## ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

Permanently removes an SSH key.
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl security sshkey-remove 12345678 -f
```
This command removes the SSH key with ID 12345678 without asking for confirmation.

## ibmcloud sl security cert-add
{: #sl_security_cert_add}

Add and upload SSL certificate details.
```
ibmcloud sl security cert-add [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--crt</dt>
<dd>Certificate file.</dd>
<dt>--csr</dt>
<dd>Certificate Signing Request file.</dd>
<dt>--icc</dt>
<dd>Intermediate Certificate file.</dd>
<dt>--key</dt>
<dd>Private Key file.</dd>
<dt>--notes</dt>
<dd>Additional notes.</dd>
</dl>

**Examples**:
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
This command adds certificate file: ~/ibm.com.cert and private key file ~/ibm.com.key for domain ibm.com.

## ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

Edit SSL certificate.
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--crt</dt>
<dd>Certificate file.</dd>
<dt>--csr</dt>
<dd>Certificate Signing Request file.</dd>
<dt>--icc</dt>
<dd>Intermediate Certificate file.</dd>
<dt>--key</dt>
<dd>Private Key file.</dd>
<dt>--notes</dt>
<dd>Additional notes.</dd>
</dl>

**Examples**:
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
This command edits certificate with ID 12345678 and updates its private key with file: ~/ibm.com.key.

## ibmcloud sl security cert-download
{: #sl_security_cert_download}

Download SSL certificate and key files.
```
ibmcloud sl security cert-download IDENTIFIER
```


**Examples**:
```
ibmcloud sl security cert-download 12345678
```
This command downloads 4 files to current directory for certificate with ID 12345678. The 4 files are: certificate file, certificate signing request file, intermediate certificate file and private key file.

## ibmcloud sl security cert-list
{: #sl_security_cert_list}

List SSL certificates on your account.
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--status</dt>
<dd>Show certificates with this status, default is: all, options are: all,valid,expired.</dd>
<dt>--sortby</dt>
<dd>Column to sort by, options are: id,common_name,days_until_expire,notes.</dd>
</dl>

**Examples**:
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
This command lists all valid certificates on current account and sort them by validity days.

## ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

Remove SSL certificate.
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl security cert-remove 12345678
```
This command removes certificate with ID 12345678.
