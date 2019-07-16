---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-06"

keywords: cli, ibmcloud account cli, managing accounts cli, managing users cli, managing orgs, cloud foundry user cli, account space cli, account, account orgs, account update command, add certificate cli, remove certificate command, manage cf users cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}

# Gestión de cuentas, usuarios y organizaciones de Cloud Foundry
{: #ibmcloud_commands_account}

Utilice los mandatos siguientes para gestionar cuentas, usuarios de una cuenta y la organización, el espacio y los roles de los entornos de Cloud Foundry públicos.
{: shortdesc}

## ibmcloud account orgs
{: #ibmcloud_account_orgs}

Listar todas las organizaciones.
```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>Nombre de región. Lista las organizaciones en la región especificada. Si no se especifica, el valor predeterminado es la región actual. Si se establece en 'all', se listan las organizaciones de todas las regiones.</dd>
   <dt>--guid</dt>
   <dd>Mostrar el GUID de las organizaciones. Esta opción es exclusiva con '--output'.</dd>
   <dt>--output FORMAT</dt>
   <dd>Especificar el formato de salida; actualmente solo se admite JSON. Esta opción es exclusiva con '--guid'.</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>ID de cuenta. Lista las organizaciones bajo la cuenta. Si no se especifica, el valor predeterminado es la cuenta actual. Si se establece en 'all', se listan las organizaciones de todas las cuentas. Esta opción es exclusiva con '-u'.</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>Nombre del propietario de la cuenta. Lista las organizaciones bajo las cuentas propiedad del usuario. Si no se especifica, el valor predeterminado es la cuenta actual. Si se establece en 'all', se listan las organizaciones de todas las cuentas. Esta opción es exclusiva con '-c'.</dd>
   </dl>

<strong>Ejemplos</strong>:

Listar todas las organizaciones de la región: `us-south` con GUID visualizado

```
ibmcloud account orgs -r us-south --guid
```

Listar todas las organizaciones en formato JSON

```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

Mostrar la información de la organización especificada.
```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización.</dd>
   <dt>-r REGION</dt>
   <dd>Nombre de región. Si no se especifica, el valor predeterminado es la región actual. Si se establece en 'all', se listarán las organizaciones con el nombre proporcionado de todas las regiones.</dd>
   <dt>--guid</dt>
   <dd>Recuperar y visualizar el guid de la organización determinada. Se suprimirá el resto de la salida de la organización. Esta opción es exclusiva con '--output'.</dd>
   <dt>--output REGION</dt>
   <dd>Especificar el formato de salida; actualmente solo se admite JSON. Esta opción es exclusiva con '--guid'.</dd>
   </dl>

<strong>Ejemplos</strong>:

Mostrar la información de la organización `IBM` con GUID visualizado.
```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Crear una nueva organización. Esta operación solamente la puede ejecutar el propietario de la cuenta.
```
ibmcloud account org-create ORG_NAME [-f]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización que se está creando.</dd>
   <dt>-f</dt>
   <dd>Forzar la creación sin confirmación.</dd>
   </dl>

<strong>Ejemplos</strong>:

Cree una organización denominada `IBM`.
```
ibmcloud account org-create IBM
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replicar una organización desde la región actual a otra región.
```
ibmcloud account org-replicate ORG_NAME REGION_NAME
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización existente que se debe replicar.</dd>
   <dt>REGION_NAME (necesario)</dt>
   <dd>Nombre de la región que aloja la organización replicada.</dd>
   </dl>

<strong>Ejemplos</strong>:

Replicar la organización `myorg` en la región `eu-gb`:
```
ibmcloud account org-replicate myorg eu-gb
```

## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Cambiar el nombre de una organización. Esta operación solamente la puede llevar a cabo un gestor de la organización.
```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>OLD_ORG_NAME (necesario)</dt>
   <dd>Nombre antiguo de la organización que se debe renombrar.</dd>
   <dt>NEW_ORG_NAME (necesario)</dt>
   <dd>Nuevo nombre de la organización.</dd>
   </dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Listar todos los espacios de cuenta.
```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>-o ORG_NAME</dt>
   <dd>Nombre de la organización. Lista los espacios en la organización especificada. Si no se especifica, el valor predeterminado es la organización actual.</dd>
   <dt>-r REGION-NAM</dt>
   <dd>Nombre de región. Lista los espacios en la región especificada. Si no se especifica, el valor predeterminado es la región actual.</dd>
   <dt>--output FORMAT</dt>
   <dd>Especificar el formato de salida; actualmente solo se admite JSON.</dd>
   </dl>

<strong>Ejemplos</strong>:

Listar todos los espacios:
```
ibmcloud account spaces
```

Listar todos los espacios de la organización `org_example` en formato JSON:
```
ibmcloud account spaces -o org_example --output JSON
```

## ibmcloud account space
{: #ibmcloud_account_space}

Mostrar la información de un espacio específico.
```
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid | --output FORMAT] [--security-group-rules]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>SPACE_NAME (necesario)</dt>
   <dd>Nombre del espacio que se va a mostrar.</dd>
   <dt>-o ORG_NAME</dt>
   <dd>Nombre de la organización. Si no se especifica, el valor predeterminado es la organización actual.</dd>
   <dt>--guid</dt>
   <dd>Recuperar y visualizar el guid del espacio predeterminado. Se suprimirá el resto de la salida del espacio. Esta opción es exclusiva con '--output'.</dd>
   <dt>--output FORMAT</dt>
   <dd>Especificar el formato de salida; actualmente solo se admite JSON. Se suprimirá el resto de la salida del espacio. Esta opción es exclusiva con '--guid'.</dd>
   <dt>--security-group-rules</dt>
   <dd>Recuperar las reglas para todos los grupos de seguridad asociados con este espacio.</dd>
   </dl>

<strong>Ejemplos</strong>:

Mostrar la información del espacio `space_example`:
```
ibmcloud account space space_example
```

Mostrar la GUID del espacio `space_example`:
```
ibmcloud account space space_example --guid
```

Mostrar la información del espacio `space_example` en formato JSON:
```
ibmcloud account space space_example --output JSON
```

Mostrar las reglas de grupo de seguridad del espacio `space_example`:
```
ibmcloud account space space_example --security-group-rules
```

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

Este mandato tiene la misma función y opciones que el mandato [`cf create-space`](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo").

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}

Este mandato tiene la misma función y opciones que el mandato [`cf rename-space`](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo").

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}

Este mandato tiene la misma función y opciones que el mandato [`cf delete-space`](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo").

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Visualice usuarios en el archivo de organización según el rol.
```
ibmcloud account org-users ORG_NAME [-r, --region REGION] [-a, --all]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>ORG_NAME (necesario)</dt>
<dd>Nombre de la organización.</dd>
<dt>-a, -all (opcional)</dt>
<dd>Lista todos los usuarios de la organización especificada, no agrupada por rol.</dd>
<dt>-r, --region REGION (opcional)</dt>
<dd>Nombre de región. Si no se especifica, el valor predeterminado es la región actual.</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Añadir un usuario a la organización (es necesario ser gestor de organización).
```
 ibmcloud account org-user-add USER_NAME ORG
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Eliminar un usuario de la organización (gestor de organización o usuario solamente).
```
ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Forzar la supresión sin confirmación.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Obtener todos los roles de la organización del usuario actual.
```
ibmcloud account org-roles [-u USER_ID]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ID de usuario. Si no se especifica, el valor predeterminado es el usuario actual.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Asignar un rol de organización a un usuario. Esta operación solamente la puede ejecutar un gestor de la organización.
```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>El nombre del usuario que se va a asignar.</dd>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización a la que se asigna a este usuario.</dd>
   <dt>ORG_ROLE (necesario)</dt>
   <dd>Nombre del rol de la organización al que se asigna a este usuario. Por ejemplo:
   <ul>
   <li>OrgManager: este rol puede invitar y gestionar usuarios, seleccionar y cambiar planes y establecer límites de gasto.</li>
   <li>BillingManager: este rol puede crear y gestionar la cuenta de facturación y la información de pago.</li>
   <li>OrgAuditor: este rol tiene acceso de sólo lectura a informes e información de organización.</li>
   </ul>
   </dd>
  </dl>

<strong>Ejemplos</strong>:

Asigne el usuario `Mary` a la organización `IBM` como el rol de `OrgManager`:
```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
Establezca roles de espacios/organizaciones utilizando la CLI, sin embargo, si desea establecer otros permisos, debe utilizar la interfaz de usuario. Para obtener más información, consulte [Gestión del acceso a recursos](/docs/iam?topic=iam-iammanidaccser).
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Elimine un rol de organización de un usuario. Esta operación solamente la puede llevar a cabo un gestor de la organización.
```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>Nombre del usuario al que se elimina.</dd>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización de la que se elimina a este usuario.</dd>
   <dt>ORG_ROLE (necesario)</dt>
   <dd>Nombre del rol de la organización de la que se elimina a este usuario. Por ejemplo:
   <ul>
   <li>OrgManager: este rol puede invitar y gestionar usuarios, seleccionar y cambiar planes y establecer límites de gasto.</li>
   <li>BillingManager: este rol puede crear y gestionar la cuenta de facturación y la información de pago.</li>
   <li>OrgAuditor: este rol tiene acceso de sólo lectura a informes e información de organización.</li>
   </ul>
   </dd>
    </dl>

<strong>Ejemplos</strong>:

Elimine el usuario `Mary` de la organización `IBM` como el rol de `OrgManager`:
```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

Visualice usuarios en el espacio especificado según el rol.
```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización.</dd>
   <dt>SPACE_NAME (necesario)</dt>
   <dd>El nombre del espacio.</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Asignar un rol de espacio a un usuario. Esta operación solamente la puede ejecutar un gestor de espacios.
```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>El nombre del usuario que se va a asignar.</dd>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización a la que se asigna a este usuario.</dd>
   <dt>SPACE_NAME (necesario)</dt>
   <dd>Nombre del espacio al que se asigna a este usuario.</dd>
   <dt>SPACE_ROLE (necesario)</dt>
   <dd>Nombre del rol de espacio al que se asigna a este usuario. Por ejemplo:
   <ul>
   <li>SpaceManager: este rol puede invitar y gestionar usuarios, y habilitar características.</li>
   <li>SpaceDeveloper: este rol puede crear y gestionar apps y servicios, y ver registros e informes.</li>
   <li>SpaceAuditor: este rol puede ver los registros, informes y valores para el espacio.</li>
   </ul></dd>
    </dl>

<strong>Ejemplos</strong>:

Asigne el usuario `Mary` a la organización `IBM` y al espacio `Cloud` como rol `SpaceManager`:
```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Elimine un rol de espacio de un usuario. Esta operación solamente la puede ejecutar un gestor de espacios.
```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>El nombre del usuario que se va a eliminar.</dd>
   <dt>ORG_NAME (necesario)</dt>
   <dd>Nombre de la organización de la que se elimina a este usuario.</dd>
   <dt>SPACE_NAME (necesario)</dt>
   <dd>Nombre del espacio del que se elimina a este usuario.</dd>
   <dt>SPACE_ROLE (necesario)</dt>
   <dd>Nombre del rol del espacio del que se elimina a este usuario. Por ejemplo:
   <ul>
   <li>SpaceManager: este rol puede invitar y gestionar usuarios, y habilitar características.</li>
   <li>SpaceDeveloper: este rol puede crear y gestionar apps y servicios, y ver registros e informes.</li>
   <li>SpaceAuditor: este rol puede ver los registros, informes y valores para el espacio.</li>
   </ul></dd>
    </dl>


<strong>Ejemplos</strong>:

Elimine el usuario `Mary` de la organización `IBM` y del espacio `Cloud` como rol `SpaceManager`:
```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

Lista todas las cuentas del usuario actual:
```
ibmcloud account list
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Visualiza la cuenta de la organización especificada (se necesita un usuario de la organización).
```
ibmcloud account org-account ORG_NAME [--guid]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--guid (opcional)</dt>
  <dd>Visualiza únicamente el ID de la cuenta</dd>
</dl>

## ibmcloud account show
{: #ibmcloud_account_show}

Mostrar detalles de la cuenta.
```
ibmcloud account show
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
</dl>

<strong>Ejemplos</strong>:

Mostrar detalles de la cuenta de destino actual:
```
ibmcloud account show
```

## ibmcloud account update
{: #ibmcloud_account_update}

Actualizar una cuenta específica:
```
ibmcloud account update (--service-endpoint-enable true | false)
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--service-endpoint-enable true | false</dt>
  <dd>Habilitar o inhabilitar la conectividad de puntos finales de servicio para una cuenta de SoftLayer.</dd>
</dl>

<strong>Ejemplos</strong>:

Habilitar la conectividad de punto final de servicio para la cuenta actual:
```
ibmcloud account update --service-endpoint-enable true
```

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

Mostrar una lista de registros de auditoría de cuentas de SoftLayer:
```
account audit-logs [-u, --user-name USER_NAME] [-t, --object-type OBJECT_TYPE] [-o, --object OBJECT] [-a, --action ACTION] [-s, --start-date START_DATE] [-e, --end-date END_DATE]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-a, --action <i>ACTION</i></dt>
  <dd>Acción. Obtener una lista de registros de auditoría con la acción.</dd>
  <dt>-e, --end-date <i>END_DATE</i></dt>
  <dd>Fecha de finalización. Obtener una lista de registros de auditoría anteriores a la fecha de finalización. Los formatos admitidos son aaaa-MM-ddTHH:mm:ss.</dd>
  <dt>-o, --object <i>OBJECT</i></dt>
  <dd>Objeto. Obtener una lista de registros de auditoría con el objeto.</dd>
  <dt>-t, --object-type <i>OBJECT_TYPE</i></dt>
  <dd>Tipo de objeto. Obtener una lista de registros de auditoría con el tipo de objeto.</dd>
  <dt>-s, --start-date <i>START_DATE</i></dt>
  <dd>Fecha de inicio. Obtener una lista de registros de auditoría posteriores a la fecha de inicio. Los formatos admitidos son aaaa-MM-ddTHH:mm:ss.</dd>
  <dt>-u, --user-name <i>USER_NAME</i></dt>
  <dd>Nombre de usuario. Obtener una lista de registros de auditoría con el nombre de usuario.</dd>
</dl>

<strong>Ejemplos</strong>:

Listar registros de auditoría:
```
ibmcloud account audit-logs
```

## ibmcloud account users
{: #ibmcloud_account_users}

Muestra los usuarios asociados a la cuenta. Esta operación solamente la puede ejecutar el propietario de la cuenta.
```
ibmcloud account users
```

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Eliminar un usuario de una cuenta (solo propietario de cuenta).
```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>USER_ID (necesario)</dt>
<dd>ID de usuario</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID de cuenta. Si no se especifica, el valor predeterminado es la cuenta actual.</dd>
<dt>-f, --force</dt>
<dd>Forzar la eliminación sin confirmación.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Invitar a un usuario a la cuenta:
```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
   <dt>USER_EMAIL (necesario)</dt>
   <dd>El correo electrónico del usuario al que se invita.</dd>
   <dt>-o ORG</dt>
   <dd>Organización a la que invitar a un usuario</dd>
   <dt>--org-role ORG_ROLE</dt>
   <dd>Rol de organización. Las entradas válidas son: OrgManager, BillingManager, OrgAuditor y OrgUser. Si se omite, se establecerá el rol OrgUser.</dd>
   <dt>-s SPACE</dt>
   <dd>Espacio al que invitar al usuario</dd>
   <dt>--space-role SPACE_ROLE</dt>
   <dd>Rol de espacio. Las entradas válidas son: SpaceManager, SpaceDeveloper y SpaceAuditor.</dd>
</dl>

Si no está preparado para asignar acceso o desea asignar una política IAM en lugar de Acceso de Cloud Foundry, puede invitar a un usuario sin acceso y asignarlo más tarde. Para obtener más información sobre la asignación de acceso a los usuarios, consulte [Gestión del acceso a los recursos](/docs/iam?topic=iam-iammanidaccser#assign_new_access).
{: tip}

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Reenviar la invitación a un usuario (administrador de cuenta).
```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
   <dt>USER_EMAIL (necesario)</dt>
   <dd>El correo electrónico del usuario al que se invita de nuevo.</dd>
</dl>

## ibmcloud app domain-cert
{: #accounts-list-domain-cert}

Liste la información de certificado de un dominio.
```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
<dt>DOMAIN_NAME (necesario)</dt>
<dd>Nombre del dominio que aloja el certificado.</dd>
</dl>


<strong>Ejemplos</strong>:

Ver la información de certificado del dominio `ibmcxo-eventconnect.com`:
```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #accounts-add-domain-cert}

Añadir un certificado para el dominio especificado en la organización actual.
```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
   <dl>
   <dt>DOMAIN (necesario)</dt>
   <dd>Dominio al que se añade el certificado.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (necesario)</dt>
   <dd>Vía de acceso del archivo de claves privado.</dd>
   <dt>-c <i>CERT_FILE</i> (necesario)</dt>
   <dd>Vía de acceso del archivo de certificado.</dd>
   <dt>-p <i>PASSWORD</i> (opcional)</dt>
   <dd>Contraseña del certificado.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (opcional)</dt>
   <dd>Vía de acceso del archivo de certificado intermedio.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (opcional)</dt>
   <dd>El archivo del almacén de confianza.</dd>
   </dl>


<strong>Ejemplos</strong>:

Añadir un certificado al dominio `ibmcxo-eventconnect.com`:
```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #accounts-remove-domain-cert}

Eliminar un certificado del dominio especificado en la organización actual.
```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:

   <dl>
   <dt>DOMAIN (necesario)</dt>
   <dd>Dominio a eliminar del certificado.</dd>
   <dt>-f  (opcional)</dt>
   <dd>Forzar la supresión sin confirmación.</dd>
   </dl>
