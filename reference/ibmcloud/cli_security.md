---

copyright:
  years: 2018, 2020
lastupdated: "2020-12-15"

keywords: cli, security cli, ssh keys cli, ssl cli, ibmcloud sl security, certificate cli, ibmcloud sl, sshkey-add, manage security cli

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Managing classic infrastructure SSH keys and SSL certificates (ibmcloud sl security)
{: #sl-manage-security-keys}

SSH keys allow access to a device without using a password from corresponding clients for each public key that is implemented on the device. By adding an SSH key to a device, the device that was provided with the SSH key accesses the device for the corresponding key without the use of a password.
{: shortdesc}

SSL certificates are enabled by websites as a security measure to protect the user. They are generally used when you are required to transmit confidential information to a website.

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage {{site.data.keyword.cloud_notm}} classic infrastructure SSH Keys and Certificates.

## ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

Add a new SSH key:
```bash
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

**Command options**:

-f, --in-file
:   The id_rsa.pub file to import for this key.

-k, --key
:   The actual SSH key.

--note
:   Extra note to be associated with the key.

**Examples**:

```bash
ibmcloud sl security sshkey-add my_sshkey -f ~/.ssh/id_rsa.pub --note mykey
```
{: codeblock}

This command adds an SSH key named `my_sshkey` from file ~/.ssh/id_rsa.pub with a note `mykey`.

## ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

Edit an SSH key:
```bash
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

**Command options**:

--label
:   The new label for the key.

--note
:   New notes for the key.

**Examples**:
```bash
ibmcloud sl security sshkey-edit 12345678 --label IBMCloud --note testing
```
{: codeblock}

This command updates the SSH key with ID `12345678` and sets label to `IBMCloud` and note to `testing`.

## ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

List SSH keys on your account:
```bash
ibmcloud sl security sshkey-list [OPTIONS]
```

**Command options**:

--sortby
:   Column to sort by. Options are: id,label,fingerprint,note.

**Examples**:
```bash
ibmcloud sl security sshkey-list --sortby label
```
{: codeblock}

This command lists all SSH keys on current account and sorts them by label.

## ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

Prints out an SSH key to the screen:
```bash
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --out-file
:   The public SSH key is written to this file.

**Examples**:
```bash
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
{: codeblock}

This command shows the ID, label and notes of SSH key with ID 12345678 and write the public key to file: ~/mykey.pub.

## ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

Permanently removes an SSH key:
```bash
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl security sshkey-remove 12345678 -f
```
{: codeblock}

This command removes the SSH key with ID `12345678` without asking for confirmation.

## ibmcloud sl security cert-add
{: #sl_security_cert_add}

Add and upload SSL certificate details:
```bash
ibmcloud sl security cert-add [OPTIONS]
```

**Command options**:

--crt
:   Certificate file.

--csr
:   Certificate Signing Request file.

--icc
:   Intermediate Certificate file.

--key
:   Private Key file.

--notes
:   Add extra notes.

**Examples**:
```bash
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
{: codeblock}

This command adds certificate file: ~/ibm.com.cert and private key file ~/ibm.com.key for domain ibm.com.

## ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

Edit SSL certificate:
```bash
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

**Command options**:

--crt
:   Certificate file.

--csr
:   Certificate Signing Request file.

--icc
:   Intermediate Certificate file.

--key
:   Private Key file.

--notes
:   Add extra notes.

**Examples**:
```bash
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
{: codeblock}

This command edits certificate with ID 12345678 and updates its private key with file: ~/ibm.com.key.

## ibmcloud sl security cert-download
{: #sl_security_cert_download}

Download SSL certificate and key files:
```bash
ibmcloud sl security cert-download IDENTIFIER 
```

**Examples**:
```bash
ibmcloud sl security cert-download 12345678
```
{: codeblock}

This command downloads four files to current directory for certificate with ID 12345678. The four files are: certificate file, certificate signing request file, intermediate certificate file, and private key file.

## ibmcloud sl security cert-list
{: #sl_security_cert_list}

List SSL certificates on your account:
```bash
ibmcloud sl security cert-list [OPTIONS]
```

**Command options**:

--status
:   Show certificates with this status, default is: all, options are: all,valid,expired.

--sortby
:   Column to sort by. Options are: id,common_name,days_until_expire,note.

**Examples**:
```bash
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
{: codeblock}

This command lists all valid certificates on current account and sort them by validity days.

## ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

Remove SSL certificate:
```bash
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl security cert-remove 12345678
```
{: codeblock}

This command removes certificate with ID 12345678.

