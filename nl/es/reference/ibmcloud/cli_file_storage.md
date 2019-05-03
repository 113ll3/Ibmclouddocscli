---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, file storage service, ibmcloud sl file, snapshot, file storage, storage, nfs, nas, iops, volume, datacenter

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cómo trabajar con el servicio de almacenamiento de archivos
{: #sl-file-storage-service}

{{site.data.keyword.filestorage_full}} es una {{site.data.keyword.filestorage_short}} basada en NFS persistente, rápida y flexible conectada a la red. En este entorno de almacenamiento adjunto de red (NAS), tiene un control total sobre la función y el rendimiento de las comparticiones de archivos.

Utilice los mandatos siguientes para gestionar un volumen determinado en el servicio de almacenamiento de archivos de la infraestructura clásica de {{site.data.keyword.cloud_notm}}.
{: shortdesc}
 
## ibmcloud sl file access-authorize
{: #sl_file_access_authorize}

Autorizar que los hosts accedan a un volumen determinado.
```
ibmcloud sl file access-authorize VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>El ID de un servidor hardware para autorizar.</dd>
<dt>-v, --virtual-id</dt>
<dd>El ID de un servidor virtual para autorizar.</dd>
<dt>-i, --ip-address-id</dt>
<dd>El ID de una dirección IP para autorizar.</dd>
<dt>-p, --ip-address</dt>
<dd>Una dirección IP para autorizar.</dd>
<dt>-s, --subnet-id</dt>
<dd>ID de una subred que se va a autorizar.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```

Este mandato autoriza al servidor virtual con el ID `87654321` a acceder al volumen con el ID `12345678`.

## ibmcloud sl file access-list
{: #sl_file_access_list}

Listar ACL.
```
ibmcloud sl file access-list VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--sortby</dt>
<dd>Columna por la que ordenar. Las opciones son: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Columnas a visualizar. Las opciones son: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file access-list 12345678 --sortby id
```

Este mandato lista todos los hosts que están autorizados para acceder al volumen con el ID `12345678` y los ordena por ID.

## ibmcloud sl file access-revoke
{: #sl_file_access_revoke}

Revocar autorización para hosts que acceden a un volumen determinado.
```
ibmcloud sl file access-revoke VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>El ID de un servidor hardware a revocar.</dd>
<dt>-v, --virtual-id</dt>
<dd>El ID de un servidor virtual a revocar.</dd>
<dt>-i, --ip-address-id</dt>
<dd>El ID de una dirección IP a revocar.</dd>
<dt>-p, --ip-address</dt>
<dd>Una dirección IP a revocar.</dd>
<dt>-s, --subnet-id</dt>
<dd>ID de una subred que se va a revocar.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```

Este mandato revoca el acceso del servidor virtual con el ID `87654321` al volumen con el ID `12345678`.

## ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

Restablecimiento de un volumen de archivo a partir de una réplica.
```
ibmcloud sl file replica-failback VOLUME_ID
```

**Ejemplos**:
```
ibmcloud sl file replica-failback 12345678
```
Este mandato realiza la operación de restablecimiento para el volumen con el ID `12345678`.

## ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

Migración tras error de un volumen de archivo a un volumen de réplica determinado.
```
ibmcloud sl file replica-failover VOLUME_ID REPLICA_ID
```


**Ejemplos**:
```
ibmcloud sl file replica-failover 12345678 87654321
```
Este mandato realiza la operación de migración tras error para el volumen con el ID `12345678` al volumen de réplica con el ID `87654321`.

## ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

Listar centros de datos de réplicas adecuados para el volumen indicado.
```
ibmcloud sl file replica-locations VOLUME_ID
```


**Ejemplos**:
```
ibmcloud sl file replica-locations 12345678
```
Este mandato lista centros de datos de réplicas adecuados para el volumen de archivo con el ID `12345678`.

## ibmcloud sl file replica-order
{: #sl_file_replica_order}

Solicitar un volumen de réplica de almacenamiento en archivo.
```
ibmcloud sl file replica-order VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Obligatorio. Planificación de instantáneas para utilizar para la réplica. Las opciones son: HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatorio. Nombre abreviado del centro de datos para la réplica, p. ej. dal09.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Nivel de almacenamiento resistente (IOPS por GB) del volumen primario para el cual se solicita una réplica. Las opciones son: 0,25, 2, 4, 10. Si no se especifica el nivel, se utilizará el nivel del volumen original.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de almacenamiento de rendimiento, entre 100 y 6000 en múltiplos de 100. Si no se especifica IOPS, se utilizará el IOPS del volumen original.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```

Este mandato solicita una réplica para el volumen con el ID `12345678`, que realiza una réplica DIARIA, está ubicado en `dal09`, nivel de grados 4.

## ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

Listar volúmenes replicantes existentes de un volumen de archivo.
```
ibmcloud sl file replica-partners VOLUME_ID [OPTIONS]
```


**Ejemplos**:
```
ibmcloud sl file replica-partners 12345678
```

Este mandato lista volúmenes replicantes existentes de un volumen de archivo con el ID `12345678`.

## ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

Cancelar el espacio de instantáneas existente para un volumen determinado.
```
ibmcloud sl file snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--reason</dt>
<dd>Una razón opcional para la cancelación.</dd>
<dt>--immediate</dt>
<dd>Cancelar el espacio de instantáneas inmediatamente, en lugar de en el aniversario de facturación.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```

Este mandato cancela la instantánea con el ID `12345678` inmediatamente sin pedir confirmación.

## ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

Crear una instantánea en un volumen determinado.
```
ibmcloud sl file snapshot-create VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Notas para establecer en la nueva instantánea.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file snapshot-create 12345678 --note snapshotforibmcloud
```
Este mandato crea una instantánea para el volumen con el ID `12345678` y con una nota de adición como `snapshotforibmcloud`.

## ibmcloud sl file snapshot-disable
{: #sl_file_snapshot_disable}

Inhabilitar instantáneas en la planificación especificada para un volumen determinado.
```
ibmcloud sl file snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Obligatorio. Planificación de instantáneas. Las opciones son: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```

Este mandato inhabilita la instantánea diaria para el volumen con el ID `12345678`.

## ibmcloud sl file snapshot-enable
{: #sl_file_snapshot_enable}

Habilitar instantáneas para un volumen determinado en la planificación especificada.
```
ibmcloud sl file snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Obligatorio. Planificación de instantáneas. Las opciones son: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Obligatorio. Número de instantáneas que se deben retener.</dd>
<dt>-m, --minute</dt>
<dd>Minuto de la hora en el que deben tomarse las instantáneas, entero entre 0 y 59.</dd>
<dt>-r, --hour</dt>
<dd>Hora del día en la que deben tomarse las instantáneas, número entero entre 0 y 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Día de la semana en que deben tomarse las instantáneas, número entero entre 0 y 6. 0 significa domingo, 1 significa lunes, 2 significa martes, 3 significa miércoles, 4 significa jueves, 5 significa viernes, 6 significa sábado.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```

Este mandato habilita la instantánea para el volumen con el ID `12345678`. La instantánea se toma semanalmente cada domingo a las 2:00, y se retienen hasta 5 instantáneas.

## ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

Suprimir una instantánea en un volumen determinado.
```
ibmcloud sl file snapshot-delete SNAPSHOT_ID
```

**Ejemplos**:
```
ibmcloud sl file snapshot-delete 12345678
```

Este mandato suprime la instantánea con el ID `12345678`.

## ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

Listar las instantáneas de almacenamiento en archivo.
```
ibmcloud sl file snapshot-list VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--sortby</dt>
<dd>Columna por la que se debe ordenar. Las opciones son: id,name,created,size_bytes.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file snapshot-list 12345678 --sortby id
```

Este mandato lista todas las instantáneas de volumen con el ID `12345678` y las ordena por ID.

## ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

Solicitar espacio de instantáneas para un volumen de almacenamiento en archivos.
```
ibmcloud sl file snapshot-order VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Obligatorio. Tamaño del espacio de instantáneas para crear en GB.</dd>
<dt>-t, --tier</dt>
<dd>Opcional. Nivel de almacenamiento resistente (IOPS por GB) del volumen de archivo para el cual se solicita el espacio. Las opciones son: 0,25, 2, 4, 10.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de almacenamiento de rendimiento, entre 100 y 6000 en múltiplos de 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Distintivo para indicar que el pedido es una actualización.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
Este mandato solicita espacio de instantáneas para el volumen con el ID `12345678`, el tamaño es 1000 GB, el nivel de grados es 4 IOPS por GB.

## ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

Restaurar volumen de archivo mediante una instantánea determinada.
```
ibmcloud sl file snapshot-restore VOLUME_ID SNAPSHOT_ID
```

**Ejemplos**:
```
ibmcloud sl file snapshot-restore 12345678 87654321
```

Este mandato restaura el volumen con el ID `12345678` a partir de la instantánea con el ID `87654321`.

## ibmcloud sl snapshot-schedule-list
{: #sl_snapshot_schedule_list}

Obtener una lista de planificaciones de instantáneas para un volumen determinado
```
ibmcloud sl snapshot-schedule-list VOLUME_ID
```

**Ejemplos**:
```
ibmcloud sl file snapshot-schedule-list 12345678
```

Este mandato muestra una lista de las planificaciones de instantáneas para el volumen con el ID `12345678`.

## ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

Cancelar un volumen de almacenamiento de archivos existente.
```
ibmcloud sl file volume-cancel VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--reason</dt>
<dd>Una razón opcional para la cancelación.</dd>
<dt>--immediate</dt>
<dd>Cancelar el volumen de almacenamiento de archivos inmediatamente, en lugar de en el aniversario de facturación.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file volume-cancel 12345678 --immediate -f
```

Este mandato cancela el volumen con el ID `12345678` inmediatamente y sin solicitar confirmación.

## ibmcloud sl file volume-count
{: #sl_file_volume_count}

Listar el número de volúmenes de almacenamiento de archivos por centro de datos.
```
ibmcloud sl file volume-count [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrar por nombre abreviado de centro de datos.</dd>
</dl>

## ibmcloud sl file volume-list
{: #sl_file_volume_list}

Listar el almacenamiento en archivo.
```
ibmcloud sl file volume-list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-u, --username</dt>
<dd>Filtrar por nombre de usuario del volumen.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar por nombre abreviado de centro de datos.</dd>
<dt>-t, --storage-type</dt>
<dd>Filtrar por tipo de volumen de almacenamiento. Las opciones son: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>Filtrar por ID del pedido que ha comprado el almacenamiento en archivo.</dd>
<dt>--sortby</dt>
<dd>Columna por la que se debe ordenar. Las opciones son: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,active_transactions,mount_addr.</dd>
<dt>--columns</dt>
<dd>Columnas que se deben visualizar. Las opciones son: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,mount_addr,notes.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```

Este mandato lista todos los volúmenes de resistencia en la cuenta actual que están ubicados en `dal09`, y los ordena por capacidad.

## ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

Mostrar detalles de un volumen especificado.
```
ibmcloud sl file volume-detail VOLUME_ID
```


**Ejemplos**:
```
ibmcloud sl file volume-detail 12345678
```

Este mandato muestra detalles de volumen con el ID `12345678`.

## ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

Solicitar un volumen de archivo duplicando un volumen existente.
```
ibmcloud sl file volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID de la instantánea de volumen original a utilizar para la duplicación.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Tamaño del volumen de archivo duplicado en GB, si no se especifica el tamaño se utilizará el del volumen original.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>IOPS de almacenamiento de rendimiento, entre 100 y 6000 en múltiplos de 100. Si no se especifica IOPS, se utilizará el IOPS del volumen original.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Nivel de almacenamiento resistente. Si no se especifica ningún tamaño, se utilizará el nivel del volumen original.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>El tamaño del espacio de instantáneas para la duplicación, si no se especifica espacio de instantáneas, se utilizará el espacio de instantáneas del volumen original.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file volume-duplicate 12345678
```

Este mandato muestra la solicitud de un volumen nuevo duplicando el volumen con el ID `12345678`.

## ibmcloud sl file volume-order
{: #sl_file_volume_order}

Solicitar un volumen de almacenamiento en archivo.
```
ibmcloud sl file volume-order [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>Obligatorio. Tipo de volumen de almacenamiento. Las opciones son: performance, endurance.</dd>
<dt>-s, --size</dt>
<dd>Obligatorio. Tamaño de volumen de almacenamiento en GB.</dd>
<dt>-i, --iops</dt>
<dd>IOPS de almacenamiento de rendimiento, entre 100 y 6000 en múltiplos de 100 [obligatorio para el rendimiento de tipo de almacenamiento].</dd>
<dt>-e, --tier</dt>
<dd>Nivel de almacenamiento resistente (IOP por GB) [obligatorio para la resistencia de tipo de almacenamiento]. Las opciones son: 0,25, 2, 4, 10.</dd>
<dt>-d, --datacenter</dt>
<dd>Obligatorio. Nombre abreviado del centro de datos.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Parámetro opcional para solicitar espacio de instantáneas junto con el volumen.</dd>
<dt>-b, --billing</dt>
<dd>Parámetro opcional para tasa de facturación (el valor predeterminado es monthly). Las opciones son hourly, monthly.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```

Este mandato solicita un volumen de rendimiento cuyo tamaño es 1000 GB, IOPS es 4000, ubicado en `dal09`.

## ibmcloud sl file volume-modify
{: #sl_file_volume_modify}

Modificar un volumen de almacenamiento de archivos existente
```
ibmcloud sl file volume-modify VOLUME_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-c, --new-size</dt>
<dd>Nuevo tamaño de volumen de archivos en GB. ***Si no se proporciona ningún tamaño, se utiliza el tamaño original del volumen.*** Tamaños posibles: [20, 40, 80, 100, 250, 500, 1000, 2000, 4000, 8000, 12000] Mínimo: [el tamaño original del volumen]</dd>
<dt>-i, --new-iops</dt>
<dd>IOPS de almacenamiento de rendimiento, entre 100 y 6000 en múltiplos de 100 [solo para volúmenes de rendimiento] ***Si no se especifica ningún valor de IOPS, se utiliza el valor de IOPS original del volumen.*** Requisitos: [Si el valor de IOPS/GB original del volumen es menor que 0,3, el nuevo valor de IOPS/GB del volumen también debe ser menor que 0,3. Si el valor de IOPS/GB original del volumen es mayor o igual que 0,3, el nuevo valor de IOPS/GB del volumen también debe ser mayor o igual que 0,3].</dd>
<dt>-t, --new-tier</dt>
<dd>Nivel de almacenamiento resistente (IOPS por GB) [solo para volúmenes de resistencia] ***Si no se especifica ningún nivel, se utiliza el nivel original del volumen.***
Requisitos: [Si el valor de IOPS/GB original del volumen es 0,25, el nuevo valor de IOPS/GB del volumen también debe ser 0,25]. Si el valor de IOPS/GB original del volumen es mayor que 0,25, el nuevo valor de IOPS/GB del volumen también debe ser mayor que 0,25].</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:

```
ibmcloud sl file volume-modify 12345678 --new-size 1000 --new-iops 4000
```

Este mandato modifica un volumen `12345678` con un tamaño de 1000 GB, IOPS es 4000.

```
ibmcloud sl file volume-modify 12345678 --new-size 500 --new-tier 4
```

Este mandato modifica un volumen `12345678` con un tamaño de 500 GB, el nivel es 4 IOPS por GB.


## ibmcloud sl file volume-options
{: #sl_file_volume_options}

Listar todas las opciones para solicitar un almacenamiento en archivo.
```
ibmcloud sl file volume-options
```

**Ejemplos**:
```
ibmcloud sl file volume-options
```
Este mandato lista todas las opciones para crear un volumen de almacenamiento en archivos, incluyendo el tipo de almacenamiento, el tamaño de volumen, IOPS, nivel de grados, centro de datos y tamaño de instantánea.
