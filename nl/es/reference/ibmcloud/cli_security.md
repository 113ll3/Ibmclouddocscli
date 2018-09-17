---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Certificados y claves SSH de la infraestructura de {{site.data.keyword.Bluemix_notm}}

Utilice los mandatos siguientes para gestionar certificados y claves SSH de la infraestructura de {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Mandatos security de la infraestructura de {{site.data.keyword.Bluemix_notm}} ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">
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

Añadir una nueva clave SSH.
```
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --in-file</dt>
<dd>El archivo id_rsa.pub a importar para esta clave.</dd>
<dt>-k, --key</dt>
<dd>La clave SSH real.</dd>
<dt>--note</dt>
<dd>Nota adicional que se asociará a la clave.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
Este mandato añade una clave SSH desde el archivo: ~/.ssh/id_rsa.pub con la nota "mykey".

## ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

Editar una clave SSH.
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--label</dt>
<dd>La nueva etiqueta para la clave.</dd>
<dt>--note</dt>
<dd>Nuevas notas para la clave.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
Este mandato actualiza la clave SSH con el ID 12345678 y establece la etiqueta en "Bluemix" y la nota en "testing".

## ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

Listar claves SSH de su cuenta.
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--sortby</dt>
<dd>Columna por la que se debe ordenar. Las opciones son: id,label,fingerprint,notes.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl security sshkey-list --sortby label
```
Este mandato lista todas las claves SSH de la cuenta actual y las ordena por etiqueta.

## ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

Imprime una clave SSH para la pantalla.
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --out-file</dt>
<dd>La clave SSH pública se escribirá en este archivo.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
Este mandato muestra el ID, la etiqueta y las notas de la clave SSH con el ID 12345678 y escribe la clave pública en el archivo: ~/mykey.pub.

## ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

Elimina una clave SSH de forma permanente.
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl security sshkey-remove 12345678 -f
```
Este mandato elimina la clave SSH con el ID 12345678 sin solicitar confirmación.

## ibmcloud sl security cert-add
{: #sl_security_cert_add}

Añadir y cargar detalles del certificado SSL.
```
ibmcloud sl security cert-add [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--crt</dt>
<dd>Archivo de certificado.</dd>
<dt>--csr</dt>
<dd>Archivo de solicitud de solicitud de firma de certificado.</dd>
<dt>--icc</dt>
<dd>Archivo de certificado intermedio.</dd>
<dt>--key</dt>
<dd>Archivo de claves privado.</dd>
<dt>--notes</dt>
<dd>Notas adicionales.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
Este mandato añade un archivo de certificado: ~/ibm.com.cert and private key file ~/ibm.com.key for domain ibm.com.

## ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

Editar certificado SSL.
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--crt</dt>
<dd>Archivo de certificado.</dd>
<dt>--csr</dt>
<dd>Archivo de solicitud de solicitud de firma de certificado.</dd>
<dt>--icc</dt>
<dd>Archivo de certificado intermedio.</dd>
<dt>--key</dt>
<dd>Archivo de claves privado.</dd>
<dt>--notes</dt>
<dd>Notas adicionales.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
Este mandato edita el certificado con el ID 12345678 y actualiza su clave privada con el archivo: ~/ibm.com.key.

## ibmcloud sl security cert-download
{: #sl_security_cert_download}

Descargar el certificado SSL y los archivos de claves.
```
ibmcloud sl security cert-download IDENTIFIER
```


**Ejemplos**:
```
ibmcloud sl security cert-download 12345678
```
Este mandato descarga 4 archivos al directorio actual para el certificado con el ID 12345678. Los 4 archivos son: archivo de certificado, archivo de solicitud de firma de certificado, archivo de certificado intermedio y archivo de claves privado.

## ibmcloud sl security cert-list
{: #sl_security_cert_list}

Listar certificados SSL de su cuenta.
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--status</dt>
<dd>Mostrar certificados con este estado, el valor predeterminado es: all, las opciones son: all,valid,expired.</dd>
<dt>--sortby</dt>
<dd>Columna por la que se debe ordenar. Las opciones son: id,common_name,days_until_expire,notes.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
Este mandato lista todos los certificados válidos de la cuenta actual y los ordena por días de validez.

## ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

Eliminar certificado SSL.
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl security cert-remove 12345678
```
Este mandato elimina el certificado con el ID 12345678.
