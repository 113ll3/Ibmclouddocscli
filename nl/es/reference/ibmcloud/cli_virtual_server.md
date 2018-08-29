---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestión del servidor virtual de la infraestructura de {{site.data.keyword.Bluemix_notm}}

<table summary="Mandatos de infraestructura generales de {{site.data.keyword.Bluemix_notm}} ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">

<caption>Tabla 1. Mandatos de servidor virtual de la infraestructura de {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">Mandatos de servidor virtual de la infraestructura de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vs cancel](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_cancel)</td>
 <td>[ibmcloud sl vs capture](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_capture)</td>
 <td>[ibmcloud sl vs create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_create)</td>
 <td>[ibmcloud sl vs options](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_options)</td>
 <td>[ibmcloud sl vs credentials](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_credentials)</td>
 <td>[ibmcloud sl vs detail](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_detail)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs dns-sync](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_dns_sync)</td>
 <td>[ibmcloud sl vs edit](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_edit)</td>
 <td>[ibmcloud sl vs host-create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_create)</td>
 <td>[ibmcloud sl vs host-list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_list)</td>
 <td>[ibmcloud sl vs list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_list)</td>
 <td>[ibmcloud sl vs pause](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_pause)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs power-off](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_off)</td>
 <td>[ibmcloud sl vs power-on](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_on)
 <td>[ibmcloud sl vs ready](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_ready)</td>
 <td>[ibmcloud sl vs reboot](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reboot)</td>
 <td>[ibmcloud sl vs reload](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reload)</td>
 <td>[ibmcloud sl vs rescue](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_rescue)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs resume](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_resume)</td>
 <td>[ibmcloud sl vs upgrade](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_upgrade)</td>
</tr>
   </tbody>
 </table>

 ## ibmcloud sl vs cancel
{: #sl_vs_cancel}

Cancelar la instancia de servidor virtual.
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs cancel 12345678
```
Este mandato cancela la instancia de servidor virtual con el ID 12345678.

## ibmcloud sl vs capture
{: #sl_vs_capture}

Capturar la instancia de servidor virtual en una imagen.
```
ibmcloud sl vs capture IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Obligatorio. Nombre de la imagen.</dd>
<dt>--all</dt>
<dd>Capturar todos los discos que pertenecen al VS.</dd>
<dt>--note</dt>
<dd>Añadir una nota para asociar a la imagen.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
Este mandato captura la instancia de servidor virtual con el ID de 12345678 con todos los discos en una imagen denominada "mycloud" con la nota "testing".

## ibmcloud sl vs create
{: #sl_vs_create}

Crear una instancia de servidor virtual.
```
ibmcloud sl vs create [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Obligatorio. Parte de host del FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Obligatorio. Parte de dominio del FQDN.</dd>
<dt>-c, --cpu</dt>
<dd>Obligatorio. Número de núcleos de CPU.</dd>
<dt>-m, --memory</dt>
<dd>Obligatorio. Memoria en megabytes.</dd>
<dt>--flavor</dt>
<dd>Nombre de clave de la versión de servidor virtual público.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatorio. Nombre abreviado del centro de datos.</dd>
<dt>-o, --os</dt>
<dd>Código de instalación de sistema operativo. Consejo: puede especificar <OS>_LATEST.</dd>
<dt>--image</dt>
<dd>ID de imagen. Consulte: 'ibmcloud sl image list' como referencia.</dd>
<dt>--billing</dt>
<dd>Tasa de facturación. El valor predeterminado es: por hora. Las opciones son: por hora, mensual.</dd>
<dt>--dedicated</dt>
<dd>Crear un servidor virtual dedicado (nodo privado).</dd>
<dt>--host-id</dt>
<dd>ID de host en el que suministrar un servidor virtual dedicado.</dd>
<dt>--san</dt>
<dd>Utilizar un almacenamiento SAN en lugar de un disco local.</dd>
<dt>--test</dt>
<dd>No crear realmente el servidor virtual.</dd>
<dt>--export</dt>
<dd>Exporta opciones a un archivo de plantilla.</dd>
<dt>-i, --postinstall</dt>
<dd>Publicar-instalar script para descargar.</dd>
<dt>-k, --key</dt>
<dd>ID de las claves SSH para añadir al usuario root (se permiten varios).</dd>
<dt>--disk</dt>
<dd>Tamaños de disco (se permiten varios).</dd>
<dt>--private</dt>
<dd>Fuerza el servidor virtual para que sólo tenga acceso a la red privada.</dd>
<dt>--like</dt>
<dd>Utilizar la configuración de un servidor virtual existente.</dd>
<dt>-n, --network</dt>
<dd>Velocidad de puerto de red en Mbps.</dd>
<dt>-g, --tag</dt>
<dd>Etiquetas para añadir a la instancia (se permiten varias).</dd>
<dt>-t, --template</dt>
<dd>Un archivo de plantilla que establece valores predeterminados en las opciones de línea de mandatos.</dd>
<dt>-u, --userdata</dt>
<dd>Cadena de metadatos definida por el usuario.</dd>
<dt>-F, --userfile</dt>
<dd>Leer datos de usuario del archivo.</dd>
<dt>--vlan-public</dt>
<dd>ID de la VLAN pública donde quiere colocar el servidor virtual.</dd>
<dt>--vlan-private</dt>
<dd>ID de la VLAN privada donde quiere colocar el servidor virtual.</dd>
<dt>-S, --public-security-group</dt>
<dd>ID de grupo de seguridad para asociar con la interfaz pública (se permiten varias ocurrencias).</dd>
<dt>-s, --private-security-group</dt>
<dd>ID de grupo de seguridad para asociar con la interfaz privada (se permiten varias ocurrencias).</dd>
<dt>--wait</dt>
<dd>Espere hasta que el servidor virtual finalice el suministro durante x segundos antes de volver.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Este mandato solicita una instancia de servidor virtual cuyo nombre de host es myvsi, el dominio es ibm.com, 4 núcleos de cpu, 4096M de memoria, ubicada en el centro de datos: dal10,

## ibmcloud sl vs options
{: #sl_vs_options}

Listar las opciones para crear una instancia de servidor virtual.
```
ibmcloud sl vs options [OPTIONS]
```


**Ejemplos**:
```
ibmcloud sl vs options
```
Este mandato lista todas las opciones para crear una instancia de servidor virtual, por ejemplo centros de datos, cpu, memoria, sistema operativo, disco, velocidad de red, etc.

## ibmcloud sl vs credentials
{: #sl_vs_credentials}

Listar las credenciales de instancia de servidor virtual.
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONS]
```


**Ejemplos**:
```
ibmcloud sl vs credentials 12345678
```
Este mandato lista todos los pares de nombres de usuario y contraseñas de la instancia de servidor virtual con el ID 12345678.

## ibmcloud sl vs detail
{: #sl_vs_detail}

Obtener detalles para una instancia de servidor virtual.
```
ibmcloud sl vs detail IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--passwords</dt>
<dd>Mostrar contraseñas (revise por encima).</dd>
<dt>--price</dt>
<dd>Mostrar precios asociados.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs details 12345678
```
Este mandato lista información detallada sobre la instancia de servidor virtual con el ID 12345678.

## ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

Sincronizar los registros de DNS para una instancia de servidor virtual.
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>Sincronizar el registro A para el host.</dd>
<dt>--aaaa-record</dt>
<dd>Sincronizar el registro AAAA para el host.</dd>
<dt>--ptr</dt>
<dd>Sincronizar el registro PTR para el host.</dd>
<dt>--ttl</dt>
<dd>Establece el TTL para los registros A y/o PTR, el valor predeterminado es: 7200.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
Este mandato sincroniza un registro A (dirección IP V4) de la instancia de servidor virtual con el ID 12345678 con el servidor DNS y establece el ttl de este registro A en 3600.

## ibmcloud sl vs edit
{: #sl_vs_edit}

Editar detalles de una instancia de servidor virtual.
```
ibmcloud sl vs edit IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>Parte de dominio del FQDN.</dd>
<dt>-H, --hostname</dt>
<dd>Parte de host del FQDN. Ejemplo: servidor.</dd>
<dt>-g, --tag</dt>
<dd>Etiquetas para establecer o cadena vacía para eliminar todas.</dd>
<dt>-u, --userdata</dt>
<dd>Cadena de metadatos definida por el usuario.</dd>
<dt>-F, --userfile</dt>
<dd>Leer datos de usuario del archivo.</dd>
<dt>--public-speed</dt>
<dd>Velocidad de puerto público, las opciones son: 0,10,100,1000,10000.</dd>
<dt>--private-speed</dt>
<dd>Velocidad de puerto privado, las opciones son: 0,10,100,1000,10000.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
Este mandato actualiza la instancia de servidor virtual con el ID 12345678 y establece su dominio en "ibm.com", el nombre de host en "myapp", la etiqueta en "testcli",

## ibmcloud sl vs host-create
{: #sl_vs_host_create}

Crear un host para servidores virtuales dedicados.
```
ibmcloud sl vs host-create [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Obligatorio. Parte de host del FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Obligatorio. Parte de dominio del FQDN.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatorio. Nombre abreviado del centro de datos.</dd>
<dt>-s, --size</dt>
<dd>Tamaño del host dedicado, actualmente solo hay un tamaño disponible: 56_CORES_X_242_RAM_X_1_4_TB.</dd>
<dt>-b, --billing</dt>
<dd>Tasa de facturación. El valor predeterminado es: por hora. Las opciones son: por hora, mensual.</dd>
<dt>-v, --vlan-private</dt>
<dd>El ID de la VLAN privada donde quiere colocar el host dedicado. Consulte: 'ibmcloud sl vlan list' como referencia.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

## ibmcloud sl vs host-list
{: #sl_vs_host_list}

Listar los hosts dedicados de su cuenta.
```
ibmcloud sl vs host-list [OPTIONS]
```


<strong>Opciones de mandato</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Filtrar por nombre del host dedicado.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar por centro de datos del host dedicado.</dd>
<dt>--owner</dt>
<dd>Filtrar por propietario del host dedicado.</dd>
<dt>--order</dt>
<dd>Filtrar por ID del pedido que ha comprado este host dedicado.</dd>
</dl>

## ibmcloud sl vs list
{: #sl_vs_list}

Listar las instancias de servidor virtual de su cuenta.
```
ibmcloud sl vs list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Filtrar por número de núcleos de CPU.</dd>
<dt>-D, --domain</dt>
<dd>Filtrar por parte de dominio del FQDN.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar por nombre abreviado de centro de datos.</dd>
<dt>-H, --hostname</dt>
<dd>Filtrar por parte de host del FQDN.</dd>
<dt>-m, --memory</dt>
<dd>Filtrar por memoria en megabytes.</dd>
<dt>-n, --network</dt>
<dd>Filtrar por velocidad de puerto de red en Mbps.</dd>
<dt>-P, --public-ip</dt>
<dd>Filtrar por dirección IP pública.</dd>
<dt>-p, --private-ip</dt>
<dd>Filtrar por dirección IP privada.</dd>
<dt>--hourly</dt>
<dd>Mostrar solo las instancias por hora.</dd>
<dt>--monthly</dt>
<dd>Mostrar solo las instancias mensuales.</dd>
<dt>-g, --tag</dt>
<dd>Filtrar por etiquetas (se permiten varias).</dd>
<dt>-o, --order</dt>
<dd>Filtrar por ID del pedido que ha comprado esta instancia.</dd>
<dt>--owner</dt>
<dd>Filtrado por ID de usuario propietario de las instancias.</dd>
<dt>--sortby</dt>
<dd>Columna por la que ordenar, el valor predeterminado es:hostname; las opciones son:id,hostname,domain,datacenter,cpu,memory,public_ip,private_ip.</dd>
<dt>--columns</dt>
<dd>Columnas que se deben visualizar, el valor predeterminado es:id,hostname,public_ip,private_ip,datacenter,action; las opciones son: guid,power_state,created_by,tags.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
Este mandato lista todas las instancias de servidor virtual de facturación por hora de la cuenta actual, filtrando el dominio igual a "ibm.com" y ordenándolas por memoria.

## ibmcloud sl vs pause
{: #sl_vs_pause}

Detener una instancia de servidor virtual activa.
```
ibmcloud sl vs pause IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs pause 12345678 -f
```
Este mandato detiene la instancia de servidor virtual con el ID 12345678 sin solicitar confirmación.

## ibmcloud sl vs power-off
{: #sl_vs_power_off}

Apagar una instancia de servidor virtual activa.
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--hard</dt>
<dd>Realizar un cierre (hard shutdown).</dd>
<dt>--soft</dt>
<dd>Realizar un cierre (soft shutdown).</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs power-off 12345678 --soft
```
Este mandato realiza un apagado (soft power off) para la instancia de servidor virtual con el ID 12345678.

## ibmcloud sl vs power-on
{: #sl_vs_power_on}

Encender una instancia de servidor virtual.
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs power-on 12345678
```
Este mandato realiza un encendido para la instancia de servidor virtual con el ID 12345678.

## ibmcloud sl vs ready
{: #sl_vs_ready}

Comprobar si hay una instancia de servidor virtual lista para su uso.
```
ibmcloud sl vs ready IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--wait</dt>
<dd>Espere hasta que el servidor virtual finalice el suministro durante x segundos antes de volver.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
Este mandato comprueba la instancia de servidor virtual con el estado del ID 12345678 para ver si está lista para su uso continuado y espera hasta 30 segundos.

## ibmcloud sl vs reboot
{: #sl_vs_reboot}

Rearrancar una instancia de servidor virtual activa.
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONS]
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

**Ejemplos**:
```
ibmcloud sl vs reboot 12345678 --hard
```
Este mandato realiza un rearranque (hard reboot) para la instancia de servidor virtual con el ID 12345678.

## ibmcloud sl vs reload
{: #sl_vs_reload}

Volver a cargar el sistema operativo en una instancia de servidor virtual.
```
ibmcloud sl vs reload IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Publicar-instalar script para descargar.</dd>
<dt>--image</dt>
<dd>ID de imagen. El valor predeterminado es utilizar el sistema operativo actual.</dd>
<dt>Consulte:</dt>
<dd>'ibmcloud sl image list' como referencia.</dd>
<dt>-k, --key</dt>
<dd>ID de las claves SSH para añadir al usuario root (se permiten varios).</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs reload 12345678
```
Este mandato vuelve a cargar el sistema operativo actual para la instancia de servidor virtual con el ID 12345678.

## ibmcloud sl vs rescue
{: #sl_vs_rescue}

Rearrancar una instancia de servidor virtual en una imagen de rescate.
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs rescue 12345678
```
Este mandato rearranca la instancia de servidor virtual con el ID 12345678 en una imagen de rescate.

## ibmcloud sl vs resume
{: #sl_vs_resume}

Reanudar una instancia de servidor virtual detenida.
```
ibmcloud sl vs resume IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs resume 12345678
```
Este mandato reanuda la instancia de servidor virtual con el ID 12345678.

## ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

Actualizar una instancia de servidor virtual.
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Número de núcleos de CPU.</dd>
<dt>--private</dt>
<dd>El núcleo de CPU estará en un servidor de host dedicado.</dd>
<dt>-m, --memory</dt>
<dd>Memoria en megabytes.</dd>
<dt>--network</dt>
<dd>Velocidad de puerto de red en Mbps.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
Este mandato actualiza la instancia de servidor virtual con el ID 12345678 y establece el número de núcleos de CPU en 8, la memoria en 8192M, la velocidad de puerto de red en 1000 Mbps.
