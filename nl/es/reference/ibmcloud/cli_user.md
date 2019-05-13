---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-07"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestión de usuarios de la infraestructura clásica
{: #manage-sl-users}

Utilice los mandatos siguientes para gestionar los usuarios de la infraestructura clásica de {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

Para crear un usuario:
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--email</dt>
<dd>Dirección de correo electrónico de este usuario. Necesaria para la creación.</dd>
<dt>--password</dt>
<dd>Contraseña que se va a establecer para este usuario. Si no se proporciona ninguna contraseña, se envía un correo electrónico al usuario para generar una, que caduca en 24 horas. Especifique la opción '-p generate' para generar una contraseña automáticamente. Las contraseñas requieren 8 o más caracteres, letras en mayúscula y minúscula, un número y un símbolo.</dd>
<dt>--from-user</dt>
<dd>Usuario base que se utilizará como plantilla para crear este usuario. El valor predeterminado es utilizar el usuario que ejecuta este mandato. La información proporcionada en --template sustituye a esta plantilla.</dd>
<dt>--template</dt>
<dd>Una serie JSON que describe https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/.</dd>
<dt>--api-key</dt>
<dd>Crear una clave de API para este usuario.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

Establece el estado de un usuario en `CANCEL_PENDING`, que inhabilita la cuenta de manera inmediata y, finalmente, se elimina de la cuenta mediante un proceso interno automatizado.
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

Para ver los detalles de un usuario:
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--keys</dt>
<dd>Mostrar la clave de API del usuario.</dd>
<dt>--permissions</dt>
<dd>Mostrar los permisos asignados a este usuario. No aparecerá ningún permiso para los usuarios maestros.</dd>
<dt>--hardware</dt>
<dd>Mostrar el hardware al que tiene acceso este usuario.</dd>
<dt>--virtual</dt>
<dd>Mostrar los invitados virtuales a los que tiene acceso este usuario.</dd>
<dt>--logins</dt>
<dd>Mostrar el historial de inicio de sesión de este usuario durante los últimos 30 días.</dd>
<dt>--events</dt>
<dd>Mostrar el registro de auditoría de este usuario.</dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

Para editar los detalles de un usuario:
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--template</dt>
<dd>Una serie JSON que describe https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/.</dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

Para habilitar o inhabilitar permisos de usuario específicos:
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--enable</dt>
<dd>Habilitar o inhabilitar los permisos seleccionados. Los valores aceptados son 'true' y 'false'. El valor predeterminado es 'true'.</dd>
<dt>--permission</dt>
<dd>Permiso `keyName` a establecer, permitiéndose varias instancias. Utilice la palabra clave ALL para seleccionar todos los permisos.</dd>
<dt>--from-user</dt>
<dd>Establecer permisos que se ajusten a los permisos de este usuario. Añade y elimina los permisos adecuados.</dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

Para mostrar una lista de usuarios:
```
ibmcloud sl user list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--column</dt>
<dd>Columna a visualizar. [Opciones: id,username,email,displayName,status,hardwareCount,virtualGuestCount][default: id,username,email,displayName].</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

Para ver los permisos de usuario:
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

