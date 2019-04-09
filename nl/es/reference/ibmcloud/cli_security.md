---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: manage security, ssh keys, ssl certificates, ibmcloud sl security, certificate, ibmcloud sl, sshkey-add

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestión de claves SSH de seguridad y de certificados SSL
{: #sl-manage-security-keys}

Las claves SSH permiten el acceso a un dispositivo sin utilizar una contraseña de los clientes correspondientes para cada clave pública que se implementa en el dispositivo. Al añadir una clave SSH a un dispositivo, el dispositivo que se proporciona con la clave SSH accede al dispositivo para la clave correspondiente sin el uso de una contraseña.

Los certificados de SSL están habilitados por los sitios web como medida de seguridad para proteger al usuario. Generalmente se utilizan cuando se le pide que transmita información confidencial a un sitio web.

Utilice los mandatos siguientes para gestionar certificados y claves SSH de la infraestructura clásica de {{site.data.keyword.cloud}}.
{: shortdesc}

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
{: codeblock}

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
ibmcloud sl security sshkey-edit 12345678 --label ibmcloud --note testing
```
{: codeblock}

Este mandato actualiza la clave SSH con el ID `12345678` y establece la etiqueta en `ibmcloud` y la nota en `testing`.

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
{: codeblock}

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
{: codeblock}

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
{: codeblock}

Este mandato elimina la clave SSH con el ID `12345678` sin solicitar confirmación.

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
