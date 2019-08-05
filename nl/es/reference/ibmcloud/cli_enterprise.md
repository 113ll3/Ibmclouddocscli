---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud enterprise, view enterprise, view enterprise account, view enterprise account group., enterprise, account-group, account-group-create, account-group-update, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestión de la empresa, cuentas y grupos de cuentas
{: #ibmcloud_enterprise}

Utilice los mandatos siguientes para gestionar la empresa, cuentas y grupos de cuentas.
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

Creación de una empresa.
```
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre de la empresa.</dd>
<dt>-d, --domain DOMAIN_NAME (opcional)</dt>
<dd>Nombre del dominio.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (opcional)</dt>
<dd>ID de usuario de contacto principal de la empresa.</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

Actualización de la información de la empresa.
```
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>-f, --force (opcional)</dt>
<dd>Actualización sin confirmación.</dd>
<dt>-n, --name NEW_NAME (obligatorio)</dt>
<dd>Nombre nuevo de la empresa.</dd>
<dt>--output FORMAT (opcional)</dt>
<dd>Especificar el formato de salida; solo se admite 'JSON'.</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

Visualización de los detalles de la empresa.
```
ibmcloud enterprise show [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>--output FORMAT (opcional)</dt>
<dd>Especificar el formato de salida; solo se admite 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

Creación de un grupo de cuentas.
```
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre del grupo de cuentas.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (opcional)</dt>
<dd>Nombre del grupo de cuentas padre. Si se omite, el padre podría ser la empresa actual.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (opcional)</dt>
<dd>ID de usuario de contacto principal del grupo de cuentas.</dd>
<dt>--output FORMAT (opcional)</dt>
<dd>Especificar el formato de salida; solo se admite 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

Actualización de un grupo de cuentas.
```
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME) [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>--id ID (obligatorio)</dt>
<dd>ID del grupo de cuentas de destino. Esta opción es excluyente con `-n, --name`.</dd>
<dt>-n, --name NAME (obligatorio)</dt>
<dd>Nombre del grupo de cuentas de destino. Esta opción es excluyente con `--id`.</dd>
<dt>--new-name NEW_NAME (obligatorio)</dt>
<dd>Nombre nuevo del grupo de cuentas de destino.</dd>
<dt>--output FORMAT (opcional)</dt>
<dd>Especificar el formato de salida; solo se admite 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

Visualización de los detalles del grupo de cuentas.
```
ibmcloud enterprise account-group (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>--id ID (obligatorio)</dt>
<dd>ID del grupo de cuentas. Esta opción es excluyente con `-n, --name`.</dd>
<dt>-n, --name NAME (obligatorio)</dt>
<dd>Nombre del grupo de cuentas. Esta opción es excluyente con `--id`.</dd>
<dt>--output FORMAT (opcional)</dt>
<dd>Especificar el formato de salida; solo se admite 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

Lista de los grupos de cuentas.
```
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (opcional)</dt>
<dd>Nombre del grupo de cuentas padre. Esta opción es excluyente con `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (opcional)</dt>
<dd>ID del grupo de cuentas padre. Esta opción es excluyente con `--parent-account-group`.</dd>
<dt>--recursive (opcional)</dt>
<dd>Mostrar los grupos de cuentas.</dd>
<dt>--output FORMAT (opcional)</dt>
<dd>Especificar el formato de salida; solo se admite 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

Creación de una cuenta.
```
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>NAME (necesario)</dt>
<dd>Nombre del grupo de cuentas.</dd>
<dt>--owner USER_ID (opcional)</dt>
<dd>ID de usuario del grupo de cuentas.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (opcional).</dt>
<dd>Nombre del grupo de cuentas padre. Si se omite, el padre podría ser la empresa actual.</dd>
<dt>--output FORMAT (opcional)</dt>
<dd>Especificar el formato de salida; solo se admite 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

Mover una cuenta bajo un padre distinto.
```
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>--id ID (obligatorio)</dt>
<dd>ID de la cuenta de destino. Esta opción es excluyente con `-n, --name`.</dd>
<dt>-n, --name NAME (obligatorio)</dt>
<dd>Nombre de la cuenta de destino. Esta opción es excluyente con `--id`.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (obligatorio)</dt>
<dd>Nombre del grupo de cuentas padre. Esta opción es excluyente con `--parent-account-group-id` y `--parent-enterprise`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (obligatorio)</dt>
<dd>ID del grupo de cuentas padre. Esta opción es excluyente con `--parent-account-group` y `--parent-enterprise`.</dd>
<dt>--parent-enterprise (obligatorio)</dt>
<dd>Definir la empresa como padre. Esta opción es excluyente con `--parent-account-group` y `--parent-account-group-id`.</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

Visualización de los detalles de una cuenta.
```
ibmcloud enterprise account-show (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>--id ID (obligatorio)</dt>
<dd>ID de la cuenta. Esta opción es excluyente con `-n, --name`.</dd>
<dt>-n, --name NAME (obligatorio)</dt>
<dd>Nombre de la cuenta. Esta opción es excluyente con `--id`.</dd>
<dt>--output FORMAT (opcional)</dt>
<dd>Especificar el formato de salida; solo se admite 'JSON'.</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

Listar cuentas.
```
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (opcional)</dt>
<dd>Nombre del grupo de cuentas padre. Esta opción es excluyente con `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (opcional)</dt>
<dd>ID del grupo de cuentas padre. Esta opción es excluyente con `--parent-account-group`.</dd>
<dt>--recursive (opcional)</dt>
<dd>Mostrar las cuentas descendientes.</dd>
<dt>--output FORMAT (opcional)</dt>
<dd>Especificar el formato de salida; solo se admite 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

Importación de una cuenta autónoma.
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
<dt>--account-id</dt>
<dd>ID de la cuenta de origen.</dd>
<dt>--parent-account-group PARENT_ACCOUNT_GROUP (opcional)</dt>
<dd>Nombre del grupo de cuentas padre. Esta opción es excluyente con `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id PARENT_ACCOUNT_GROUP_ID (opcional)</dt>
<dd>ID del grupo de cuentas padre. Esta opción es excluyente con `--parent-account-group`.</dd>
</dl>
