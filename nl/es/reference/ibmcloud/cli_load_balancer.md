---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, classic infrastructure, load balancer service, ibmcloud sl loadbal, sl loadbal, load balancer cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cómo trabajar con el servicio de equilibrador de carga
{: #sl-load-balancer-service}

El servicio de Equilibrador de carga de {{site.data.keyword.cloud}} ayuda a mejorar la disponibilidad de las aplicaciones más importantes de negocio distribuyendo el tráfico entre varias instancias del servidor de apps, y reenviando el tráfico únicamente a instancias en buen estado.

Utilice los mandatos siguientes para gestionar los equilibradores de carga en el servicio de equilibrador de carga de la infraestructura clásica de {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

Cancelar un equilibrador de carga existente.
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

## ibmcloud sl loadbal create
{: #sl_loadbal_create}

Añade un equilibrador de carga basado en el ID devuelto desde create-options.
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

## ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

Obtener opciones de precios con las que crear un equilibrador de carga.
```
ibmcloud sl loadbal create-options
```

## ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

Obtener detalles del equilibrador de carga.
```
ibmcloud sl loadbal detail LOADBAL_ID
```

## ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

Añade un nuevo servicio load_balancer.
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Obligatorio. El porcentaje de conexiones asignadas.</dd>
<dt>-p, --port</dt>
<dd>Obligatorio. El número de puerto.</dd>
<dt>-t, --routing-type</dt>
<dd>Obligatorio. El ID del tipo de direccionamiento. Ejecute 'ibmcloud sl loadbal routing-types' para buscar un ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Obligatorio. El ID del método de direccionamiento. Ejecute 'ibmcloud sl loadbal routing-methods' para buscar un ID.</dd>
</dl>

## ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

Suprime un grupo de servicios de equilibrador de carga existente.
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

## ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

Editar un grupo de servicios de equilibrador de carga existente.
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Cambie el porcentaje asignado de las conexiones.</dd>
<dt>-p, --port</dt>
<dd>Cambie el número de puerto.</dd>
<dt>-t, --routing-type</dt>
<dd>Cambie el ID del tipo de direccionamiento. Ejecute 'ibmcloud sl loadbal routing-types' para buscar un ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Cambie el ID del método de direccionamiento. Ejecute 'ibmcloud sl loadbal routing-methods' para buscar un ID.</dd>
</dl>

## ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

Restablecer conexiones en un determinado grupo de servicios.
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

## ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

Listar tipos de comprobación de estado.
```
ibmcloud sl loadbal health-checks
```

## ibmcloud sl loadbal list
{: #sl_loadbal_list}

Listar equilibradores de carga activos.
```
ibmcloud sl loadbal list
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrar por nombre abreviado de centro de datos.</dd>
<dt>-o, --order</dt>
<dd>Filtrar por ID del pedido que ha comprado el equilibrador de carga.</dd>
<dt>-p, --ip-address</dt>
<dd>Filtrar por dirección IP.</dd>
</dl>

## ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

Listar métodos de direccionamiento.
```
ibmcloud sl loadbal routing-methods
```

## ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

Listar tipos de direccionamiento.
```
ibmcloud sl loadbal routing-types
```

## ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

Añade un nuevo servicio de equilibrador de carga.
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--disabled</dt>
<dd>Opcional. Cree el servicio como inhabilitado, el valor predeterminado es habilitado si no se especifica.</dd>
<dt>-p, --port</dt>
<dd>Obligatorio. El número de puerto del servicio.</dd>
<dt>-w, --weight</dt>
<dd>Obligatorio. El peso del servicio.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Obligatorio. El tipo de comprobación de estado.</dd>
<dt>-i, --ip-address</dt>
<dd>Obligatorio. La dirección IP del servicio.</dd>
</dl>

## ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

Suprime un servicio de equilibrador de carga existente.
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

## ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

Editar las propiedades de un grupo de servicios.
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--disabled</dt>
<dd>Inhabilitar el servicio.</dd>
<dt>--enabled</dt>
<dd>Habilitar el servicio.</dd>
<dt>-p, --port</dt>
<dd>Cambie el número de puerto del servicio.</dd>
<dt>-w, --weight</dt>
<dd>Cambie el peso del servicio.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Cambie el tipo de comprobación de estado.</dd>
<dt>-i, --ip-address</dt>
<dd>Cambie la dirección IP del servicio.</dd>
</dl>

## ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

Conmutar el estado de un servicio de equilibrador de carga existente.
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>
