---

copyright:

  years: 2018


lastupdated: "2018-11-29"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Visualización del uso de cuentas, organizaciones, grupos de recursos y recursos 
{: #ibmcloud_billing}

Utilice los mandatos siguientes para recuperar el uso de recursos y la información de facturación.
{: shortdesc}

<table summary="mandatos ibmcloud que puede utilizar para gestionar el uso y la facturación de {{site.data.keyword.Bluemix_notm}}.">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud billing account-usage](cli_billing.html#ibmcloud_billing_account_usage)</td>
  <td>[ibmcloud billing org-usage](cli_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>
 
 
 ## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Mostrar el uso mensual de la cuenta actual (solo el administrador de la cuenta)

```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Mostrar datos para el mes y la fecha especificados utilizando el formato AAAA-MM. Si no se especifica, se muestra el uso en el mes actual.</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>Especificar el formato de salida; actualmente solo se admite JSON.</dd>
</dl>

<strong>Ejemplos</strong>:

Mostrar el informe de uso y de coste de la cuenta actual en 2016-06:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Mostrar el uso mensual de una organización (solo el administrador de la cuenta o el gestor de facturación de la organización)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
  <dt>ORG_NAME (necesario)</dt>
  <dd>Nombre de la organización.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Mostrar datos para el mes y la fecha especificados utilizando el formato AAAA-MM. Si no se especifica, se muestra el uso en el mes actual.</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>Especificar el formato de salida; actualmente solo se admite JSON.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Mostrar el uso mensual de un grupo de recursos (solo el administrador de la cuenta o el administrado del grupo de recursos)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
  <dt>GROUP_NAME (necesario)</dt>
  <dd>Nombre del grupo de recursos.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Mostrar datos para el mes y la fecha especificados utilizando el formato AAAA-MM. Si no se especifica, se muestra el uso en el mes actual.</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>Especificar el formato de salida; actualmente solo se admite JSON.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Mostrar el uso mensual de las instancias de recurso de la cuenta actual.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

<dl>
  <dt>-o ORG_NAME (opcional)</dt>
  <dd>Filtrar instancias por organización.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filtrar instancia por grupo de recursos.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Mostrar datos para el mes y la fecha especificados utilizando el formato AAAA-MM. Si no se especifica, se muestra el uso en el mes actual.</dd>
  <dt>--output FORMAT (opcional)</dt>
  <dd>Especificar el formato de salida; actualmente solo se admite JSON.</dd>
</dl>
