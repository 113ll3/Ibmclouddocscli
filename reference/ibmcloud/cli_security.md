---

copyright:
  years: 2018, 2020
lastupdated: "2020-03-31"

keywords: cli, security cli, ssh keys cli, ssl cli, ibmcloud sl security, certificate cli, ibmcloud sl, sshkey-add, manage security cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Managing security SSH keys and SSL certificates
{: #sl-manage-security-keys}

SSH keys allow access to a device without using a password from corresponding clients for each public key that is implemented on the device. By adding an SSH key to a device, the device that was provided with the SSH key accesses the device for the corresponding key without the use of a password.

SSL certificates are enabled by websites as a security measure to protect the user. They are generally used when you are required to transmit confidential information to a website.

Use the following commands to manage {{site.data.keyword.cloud}} classic infrastructure SSH Keys and Certificates.
{: shortdesc}

## ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

Add a new SSH key:
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
<dd>Extra note to be associated with the key.</dd>
</dl>

**Examples**:
```
ibmcloud sl security sshkey-add my_sshkey -f ~/.ssh/id_rsa.pub --note mykey
```
{: codeblock}

This command adds an SSH key named `my_sshkey` from file ~/.ssh/id_rsa.pub with a note `mykey`.

## ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

Edit an SSH key:
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
ibmcloud sl security sshkey-edit 12345678 --label IBMCloud --note testing
```
{: codeblock}

This command updates the SSH key with ID `12345678` and sets label to `IBMCloud` and note to `testing`.

## ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

List SSH keys on your account:
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--sortby</dt>
<dd>Column to sort by. Options are: id,label,fingerprint,note.</dd>
</dl>

**Examples**:
```
ibmcloud sl security sshkey-list --sortby label
```
{: codeblock}

This command lists all SSH keys on current account and sorts them by label.

## ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

Prints out an SSH key to the screen:
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --out-file</dt>
<dd>The public SSH key is written to this file.</dd>
</dl>

**Examples**:
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
{: codeblock}

This command shows the ID, label and notes of SSH key with ID 12345678 and write the public key to file: ~/mykey.pub.

## ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

Permanently removes an SSH key:
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
{: codeblock}

This command removes the SSH key with ID `12345678` without asking for confirmation.

## ibmcloud sl security cert-add
{: #sl_security_cert_add}

Add and upload SSL certificate details:
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
<dd>Add extra notes.</dd>
</dl>

**Examples**:
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
{: codeblock}

This command adds certificate file: ~/ibm.com.cert and private key file ~/ibm.com.key for domain ibm.com.

## ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

Edit SSL certificate:
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
<dd>Add extra notes.</dd>
</dl>

**Examples**:
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
{: codeblock}

This command edits certificate with ID 12345678 and updates its private key with file: ~/ibm.com.key.

## ibmcloud sl security cert-download
{: #sl_security_cert_download}

Download SSL certificate and key files:
```
ibmcloud sl security cert-download IDENTIFIER 
```

**Examples**:
```
ibmcloud sl security cert-download 12345678
```
{: codeblock}

This command downloads four files to current directory for certificate with ID 12345678. The four files are: certificate file, certificate signing request file, intermediate certificate file, and private key file.

## ibmcloud sl security cert-list
{: #sl_security_cert_list}

List SSL certificates on your account:
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--status</dt>
<dd>Show certificates with this status, default is: all, options are: all,valid,expired.</dd>
<dt>--sortby</dt>
<dd>Column to sort by. Options are: id,common_name,days_until_expire,note.</dd>
</dl>

**Examples**:
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
{: codeblock}

This command lists all valid certificates on current account and sort them by validity days.

## ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

Remove SSL certificate:
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
{: codeblock}

This command removes certificate with ID 12345678.

