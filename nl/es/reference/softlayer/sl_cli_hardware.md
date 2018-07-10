---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Mandatos de CLI de hardware

<table summary="Mandatos de infraestructura generales de {{site.data.keyword.BluSoftlayer_notm}} ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">
<caption>Tabla 1. Mandatos de hardware de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Mandato de hardware de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl hardware cancel](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_cancel)</td>
 <td>[ibmcloud sl hardware cancel-reasons](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_cancel_reasons)</td>
 <td>[ibmcloud sl hardware create](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_create)</td>
 <td>[ibmcloud sl hardware create-options](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_create_options)</td>
 <td>[ibmcloud sl hardware credentials](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_credentials)</td>
 <td>[ibmcloud sl hardware detail](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_detail)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware edit](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_edit)</td>
 <td>[ibmcloud sl hardware list](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_list)</td>
 <td>[ibmcloud sl hardware power-cycle](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_cycle)</td>
 <td>[ibmcloud sl hardware power-off](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_off)</td>
 <td>[ibmcloud sl hardware power-on](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_on)</td>
 <td>[ibmcloud sl hardware reboot](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_reboot)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware reload](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_reload)</td>
 <td>[ibmcloud sl hardware rescue](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_rescue)</td>
 <td>[ibmcloud sl hardware update-firmware](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_update_firmware)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl hardware cancel
{: #sl_hardware_cancel}

Cancelar un servidor de hardware.
```
ibmcloud sl hardware cancel IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-i, --immediate</dt>
<dd>Cancela el servidor inmediatamente (en lugar de en el aniversario de facturación).</dd>
<dt>-r, --reason</dt>
<dd>Un motivo de cancelación opcional. Consulte 'ibmcloud sl hardware cancel-reasons' para obtener una lista de opciones disponibles.</dd>
<dt>-c, --comment</dt>
<dd>Un comentario opcional para añadir al tíquet de cancelación.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

Visualizar una lista de razones de cancelación.
```
ibmcloud sl hardware cancel-reasons
```

### ibmcloud sl hardware create
{: #sl_hardware_create}

Solicitar/crear un servidor hardware.
```
ibmcloud sl hardware create [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Parte de host del FQDN, obligatorio.</dd>
<dt>-D, --domain</dt>
<dd>Parte de dominio de FQDN, obligatorio.</dd>
<dt>-s, --size</dt>
<dd>Tamaño de hardware, obligatorio.</dd>
<dt>-o, --os</dt>
<dd>Código de instalación del sistema operativo, obligatorio.</dd>
<dt>-d, --datacenter</dt>
<dd>Nombre abreviado del centro de datos, obligatorio.</dd>
<dt>-p, --port-speed</dt>
<dd>Velocidad de puerto, obligatorio.</dd>
<dt>-b, --billing</dt>
<dd>Tasa de facturación, por hora o mensual. El valor predeterminado es por hora si no se especifica.</dd>
<dt>-i, --post-install</dt>
<dd>Publicar-instalar script para descargar.</dd>
<dt>-k, --key</dt>
<dd>Las claves SSH para añadir al usuario root, se permiten varias apariciones.</dd>
<dt>-n, --no-public</dt>
<dd>Solo red privada.</dd>
<dt>-e, --extra</dt>
<dd>Opciones adicionales, aparición múltiple permitida.</dd>
<dt>-t, --test</dt>
<dd>No crear realmente el servidor virtual.</dd>
<dt>-m, --template</dt>
<dd>Un archivo de plantilla que establece valores predeterminados en las opciones de línea de mandatos.</dd>
<dt>-x, --export</dt>
<dd>Exporta opciones a un archivo de plantilla.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

Opciones de pedido de servidor para un determinado chasis.
```
ibmcloud sl hardware create-options
```

### ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

Listar credenciales de servidor de hardware.
```
ibmcloud sl hardware credentials IDENTIFIER
```

### ibmcloud sl hardware detail
{: #sl_hardware_detail}

Obtener detalles para un servidor de hardware.
```
ibmcloud sl hardware detail IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-p, --passwords</dt>
<dd>Mostrar contraseñas (revise por encima).</dd>
<dt>-c, --price</dt>
<dd>Mostrar precios asociados.</dd>
</dl>

### ibmcloud sl hardware edit
{: #sl_hardware_edit}

Editar detalles del servidor de hardware.
```
ibmcloud sl hardware edit IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Parte de host del FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Parte de dominio del FQDN.</dd>
<dt>-g, --tag</dt>
<dd>Etiquetas para establecer o cadena vacía para eliminar todas.</dd>
<dt>-F, --userfile</dt>
<dd>Leer datos de usuario del archivo.</dd>
<dt>-u, --userdata</dt>
<dd>Cadena de metadatos definida por el usuario.</dd>
<dt>-p, --public-speed</dt>
<dd>Velocidad de puerto público, las opciones son: 0,10,100,1000,10000.</dd>
<dt>-v, --private-speed</dt>
<dd>Velocidad de puerto privado, las opciones son: 0,10,100,1000,10000.</dd>
</dl>

### ibmcloud sl hardware list
{: #sl_hardware_list}

Listar servidores de hardware.
```
ibmcloud sl hardware list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Filtrar por número de núcleos de CPU.</dd>
<dt>-D, --domain</dt>
<dd>Filtrar por dominio.</dd>
<dt>-H, --hostname</dt>
<dd>Filtrar por nombre de host.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar por centro de datos.</dd>
<dt>-m, --memory</dt>
<dd>Filtrar por memoria en gigabytes.</dd>
<dt>-n, --network</dt>
<dd>Filtrar por velocidad de puerto de red en Mbps.</dd>
<dt>-g, --tag</dt>
<dd>Filtrar por etiquetas, se permiten varias.</dd>
<dt>-p, --public-ip</dt>
<dd>Filtrar por dirección IP pública.</dd>
<dt>-v, --private-ip</dt>
<dd>Filtrar por dirección IP privada.</dd>
<dt>-o, --order</dt>
<dd>Filtrar por ID del pedido que ha comprado el servidor hardware.</dd>
<dt>--owner</dt>
<dd>Filtrar por ID del propietario.</dd>
<dt>--sortby</dt>
<dd>Columna por la que se debe ordenar. Valor predeterminado:hostname, Opciones: id,guid,hostname,domain,public_ip,private_ip,datacenter,status,ipmi_ip,created,created_by.</dd>
<dt>--columns</dt>
<dd>Columnas que se deben visualizar. Valor predeterminado: id,hostname,domain,public_ip,private_ip,datacenter,status, Opciones: guid,cpu,memory,os,ipmi_ip,created,created_by,tags.</dd>
</dl>

### ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

Encender y apagar un servidor.
```
ibmcloud sl hardware power-cycle IDENTIFIER
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

Apagar un servidor activo.
```
ibmcloud sl hardware power-off IDENTIFIER
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

Encender un servidor.
```
ibmcloud sl hardware power-on IDENTIFIER
```

### ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

Rearrancar un servidor activo.
```
ibmcloud sl hardware reboot IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--hard</dt>
<dd>Realizar un rearranque (hard reboot).</dd>
<dt>--soft</dt>
<dd>Realice un rearranque (soft reboot).</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl hardware reload
{: #sl_hardware_reload}

Volver a cargar el sistema operativo en un servidor.
```
ibmcloud sl hardware reload IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Script de instalación posterior para descargar, sólo se ejecuta HTTPS, HTTP deja el archivo en /root.</dd>
<dt>-k, --key</dt>
<dd>ID de la clave SSH para añadir al usuario root, se permiten varias apariciones.</dd>
<dt>-b, --upgrade-bios</dt>
<dd>Actualizar BIOS.</dd>
<dt>-w, --upgrade-firmware</dt>
<dd>Actualizar el firmware de todos los discos duros.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

Rearrancar el servidor en una imagen de rescate.
```
ibmcloud sl hardware rescue IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

Actualizar firmware del servidor.
```
ibmcloud sl hardware update-firmware IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>
