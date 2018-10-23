---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Entornos de empresa de Cloud Foundry (CFEE)
{: #ibmcloud_commands_cfee}

Con {{site.data.keyword.cfee_full}} (CFEE), puede instanciar varias plataformas de Cloud Foundry aisladas y de nivel empresarial bajo demanda. Las instancias del servicio de IBM Cloud Foundry Enterprise se ejecutan dentro de su propia cuenta en IBM Cloud. El entorno se despliega en hardware aislado (clústeres de Kubernetes). Tiene un control completo sobre el entorno, que incluye el control de accesos, la capacidad, las actualizaciones de versiones, el uso de recursos y la supervisión.

Utilice los mandatos siguientes para gestionar entornos, organizaciones, espacios, usuarios y roles de CFEE.
{: shortdesc}

<table summary="Gestionar entornos de empresa de Cloud Foundry (experimental)">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 <td>[ibmcloud cfee orgs](cli_cfee.html#ibmcloud_cfee_orgs)</td>
 <td>[ibmcloud cfee org](cli_cfee.html#ibmcloud_cfee_org)</td>
 <td>[ibmcloud cfee org-create](cli_cfee.html#ibmcloud_cfee_org_create)</td>
 </tr>
 <tr>
 <td>[ibmcloud cfee org-delete](cli_cfee.html#ibmcloud_cfee_org_delete)</td>
 <td>[ibmcloud cfee org-users](cli_cfee.html#ibmcloud_cfee_org_users)</td>
 <td>[ibmcloud cfee org-role-set](cli_cfee.html#ibmcloud_cfee_org_role_set)</td>
 <td>[ibmcloud cfee org-role-unset](cli_cfee.html#ibmcloud_cfee_org_role_unset)</td>
 <td>[ibmcloud cfee spaces](cli_cfee.html#ibmcloud_cfee_spaces)</td>
 </tr>
<tr>
 <td>[ibmcloud cfee space](cli_cfee.html#ibmcloud_cfee_space)</td>
 <td>[ibmcloud cfee space-create](cli_cfee.html#ibmcloud_cfee_space_create)</td>
 <td>[ibmcloud cfee space-rename](cli_cfee.html#ibmcloud_cfee_space_rename)</td>
 <td>[ibmcloud cfee space-delete](cli_cfee.html#ibmcloud_cfee_space_delete)</td>
 <td>[ibmcloud cfee space-role-set](cli_cfee.html#ibmcloud_cfee_space_role_set)</td>
 </tr>
 <tr>

 <td>[ibmcloud cfee space-role-unset](cli_cfee.html#ibmcloud_cfee_space_role_unset)</td>
 <td>[ibmcloud cfee space-roles](cli_cfee.html#ibmcloud_cfee_space_roles)</td>
 <td>[ibmcloud cfee space-users](cli_cfee.html#ibmcloud_cfee_space_users)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Listar entornos de CFEE.

```
ibmcloud cfee environments
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Mostrar detalles de un entorno CFEE

```
ibmcloud cfee environment NAME [--id]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>NAME (necesario)</dt>
   <dd>El nombre del entorno que se va a mostrar.</dd>
   <dt>--id</dt>
   <dd>Mostrar solo ID</dd>
  </dl>

<strong>Ejemplos</strong>:

Mostrar detalles de un entorno CFEE `env_example`:

```
ibmcloud cfee environment env_example
```

Mostrar ID de un entorno CFEE `env_example`:

```
ibmcloud cfee environment env_example --id
```

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

Listar todas las organizaciones

```
ibmcloud cfee orgs [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Listar todas las organizaciones:

```
ibmcloud cfee orgs
```

Listar todas las organizaciones del entorno CFEE `env_example`:

```
ibmcloud cfee orgs --env env_example
```

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Mostrar detalles de una organización

```
ibmcloud cfee org ORG [--guid] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
   <dt>--guid</dt>
   <dd>Mostrar sólo el GUID de la organización; se suprimirá el resto de la salida de la organización</dd>
  </dl>

<strong>Ejemplos</strong>:

Mostrar detalles de una organización CFEE `org_example`:

```
ibmcloud cfee org org_example
```

Mostrar detalles de una organización CFEE `org_example` del entorno CFEE `env_example`:

```
ibmcloud cfee org org_example --env env_example
```

Mostrar GUID de una organización CFEE `org_example`:

```
ibmcloud cfee org org_example --guid
```

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Crear una organización

```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización que se está creando.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>Cuota que se debe asignar a la organización recién creada (si no se especifica, se utilizará la cuota predeterminada)</dd>
  </dl>

<strong>Ejemplos</strong>:

Crear una organización CFEE `org_example`:

```
ibmcloud cfee org-create org_example
```

Crear una organización CFEE `org_example` del entorno CFEE `env_example`:

```
ibmcloud cfee org-create org_example --env env_example
```

Crear una organización CFEE `org_example` con la cuota `quote_example`:

```
ibmcloud cfee org org-create org_example --quota quota_example
```

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Suprimir una organización

```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización que se va a suprimir.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
   <dt>-f, --force</dt>
   <dd>Forzar la supresión sin confirmación</dd>
  </dl>

<strong>Ejemplos</strong>:

Suprimir una organización CFEE `org_example`:

```
ibmcloud cfee org-delete org_example
```

Suprimir una organización CFEE `org_example` del entorno CFEE `env_example`:

```
ibmcloud cfee org-delete org_example --env env_example
```

Suprimir una organización CFEE `org_example` sin confirmación:

```
ibmcloud cfee org org-delete org_example -f
```

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Mostrar usuarios de una organización especificada por rol

```
ibmcloud cfee org-users ORG [-a, --all] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización.</dd>
   <dt>-a, --all</dt>
   <dd>Listar todos los usuarios de la organización especificada</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Mostrar usuarios de la organización CFEE `org_example`:

```
ibmcloud cfee org-users org_example
```

Mostrar usuarios de la organización CFEE `org_example` del entorno CFEE `env_example`:

```
ibmcloud cfee org-users org_example --env env_example
```

Listar todos los usuarios de la organización CFEE `org_example`:

```
ibmcloud cfee org-users org_example -a
```

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

Asignar un rol de organización a un usuario (es necesario ser gestor de organización)

```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>USER_EMAIL (necesario)</dt>
   <dd>El correo electrónico del usuario que se va a asignar.</dd>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización a la que se asigna a este usuario.</dd>
   <dt>ROLE (obligatorio)</dt>
   <dd>Nombre del rol de la organización al que se asigna a este usuario. Por ejemplo:
   <ul>
   <li>OrgManager: este rol puede invitar y gestionar usuarios, seleccionar y cambiar planes y establecer límites de gasto.</li>
   <li>BillingManager: este rol puede crear y gestionar la cuenta de facturación y la información de pago.</li>
   <li>OrgAuditor: este rol tiene acceso de sólo lectura a informes e información de organización.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Asignar el rol `BillingManager` al usuario `test@exmaple.com` en la organización `org_example`:

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```

Asignar el rol `BillingManager` al usuario `test@exmaple.com` en la organización `org_example` del entorno CFEE `env_example`:

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Eliminar un rol de organización de un usuario (gestor de organización o usuario mismo solamente)

```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>USER_EMAIL (necesario)</dt>
   <dd>El correo electrónico del usuario que se va a eliminar.</dd>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización de la que se elimina a este usuario.</dd>
   <dt>ROLE (obligatorio)</dt>
   <dd>Nombre del rol de la organización de la que se elimina a este usuario. Por ejemplo:
   <ul>
   <li>OrgManager: este rol puede invitar y gestionar usuarios, seleccionar y cambiar planes y establecer límites de gasto.</li>
   <li>BillingManager: este rol puede crear y gestionar la cuenta de facturación y la información de pago.</li>
   <li>OrgAuditor: este rol tiene acceso de sólo lectura a informes e información de organización.</li>
   </ul>
   </dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Eliminar el rol `BillingManager` del usuario `test@exmaple.com` de la organización `org_example`:

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```

Eliminar el rol `BillingManager` del usuario `test@exmaple.com` de la organización `org_example` del entorno CFEE `env_example`:

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

Listar todos los espacios

```
ibmcloud cfee spaces [-o,--org ORG] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>Nombre de la organización. Si no se especifica, el valor predeterminado es la organización actual.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Listar todos los espacios

```
ibmcloud cfee spaces
```

Listar todos los espacios de la organización `org_example` y el entorno CFEE `env_example`

```
ibmcloud cfee spaces -o org_example --env env_example
```

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

Mostrar la información del espacio especificado

```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>SPACE (obligatorio)</dt>
   <dd>Nombre del espacio que se va a mostrar.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
   <dt>--guid</dt>
   <dd>Recuperar y visualizar el guid del espacio predeterminado. Se suprimirá el resto de la salida del espacio.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nombre de la organización. Si no se especifica, el valor predeterminado es la organización actual.</dd>
   <dt>--security-group-rules</dt>
   <dd>Recuperar las reglas para todos los grupos de seguridad asociados con este espacio.</dd>
  </dl>

<strong>Ejemplos</strong>:

Mostrar la información del espacio `space_example`:

```
ibmcloud cfee space space_example
```

Recuperar y visualizar el guid del espacio `space_example`:

```
ibmcloud cfee space space_example --guid
```

Mostrar las reglas para todos los grupos de seguridad asociados con el espacio `space_example`:

```
ibmcloud cfee space space_example --security-group-rules
```

Mostrar la información del espacio `space_example` de la organización `org_example` y el entorno CFEE `env_example`:

```
ibmcloud cfee space space_example -o org_example --env env_example
```

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Crear un espacio nuevo

```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>SPACE (obligatorio)</dt>
   <dd>Nombre del espacio que se va a crear.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nombre de la organización. Si no se especifica, el valor predeterminado es la organización actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Crear un espacio nuevo `space_example`:

```
ibmcloud cfee space-create space_example
```

Crear un espacio nuevo `space_example` en la organización `org_example` y el entorno CFEE `env_example`:

```
ibmcloud cfee space-create space_example -o org_example --env env_example
```

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Renombrar un espacio

```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>OLD_NAME (obligatorio)</dt>
   <dd>Nombre antiguo del espacio que se debe renombrar.</dd>
   <dt>NEW_NAME (obligatorio)</dt>
   <dd>Nombre nuevo del espacio.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nombre de la organización. Si no se especifica, el valor predeterminado es la organización actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Renombrar el espacio `space_example` a `new_pace_example`:

```
ibmcloud cfee space-rename space_example new_pace_example
```

Renombrar el espacio `space_example` a `new_pace_example` en la organización `org_example` y el entorno CFEE `env_example`:

```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Suprimir un espacio

```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>SPACE (obligatorio)</dt>
   <dd>Nombre del espacio que se va a suprimir.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
   <dt>-f, --force</dt>
   <dd>Forzar la eliminación sin confirmación.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nombre de la organización. Si no se especifica, el valor predeterminado es la organización actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Suprimir el espacio `space_example`:

```
ibmcloud cfee space-delete space_example
```

Suprimir el espacio `space_example` en la organización `org_example` y el entorno CFEE `env_example` sin confirmación:

```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

Asignar un rol de espacio a un usuario

```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>USER_EMAIL (necesario)</dt>
   <dd>El correo electrónico del usuario que se va a asignar.</dd>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización a la que se asigna a este usuario.</dd>
   <dt>SPACE (obligatorio)</dt>
   <dd>Nombre del espacio al que se asigna a este usuario.</dd>
   <dt>ROLE (obligatorio)</dt>
   <dd>Nombre del rol de espacio al que se asigna a este usuario. Por ejemplo:
   <ul>
   <li>SpaceManager: este rol puede invitar y gestionar usuarios, y habilitar características para un espacio dado.</li>
   <li>SpaceDeveloper: este rol puede crear y gestionar apps y servicios, y ver registros e informes.</li>
   <li>SpaceAuditor: este rol puede ver los registros, informes y valores para el espacio.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Asignar el usuario `test@exmaple.com` a la organización `org_example` y el espacio `space_example` con el rol `SpaceManager`:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```

Asignar el usuario `test@exmaple.com` a la organización `org_example` y el espacio `space_example` con el rol `SpaceManager` en el entorno `env_example`:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

Eliminar un rol de espacio de un usuario

```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>USER_EMAIL (necesario)</dt>
   <dd>El correo electrónico del usuario que se va a eliminar.</dd>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización de la que se elimina a este usuario.</dd>
   <dt>SPACE (obligatorio)</dt>
   <dd>Nombre del espacio del que se elimina a este usuario.</dd>
   <dt>ROLE (obligatorio)</dt>
   <dd>Nombre del rol del espacio del que se elimina a este usuario. Por ejemplo:
   <ul>
   <li>SpaceManager: este rol puede invitar y gestionar usuarios, y habilitar características para un espacio dado.</li>
   <li>SpaceDeveloper: este rol puede crear y gestionar apps y servicios, y ver registros e informes.</li>
   <li>SpaceAuditor: este rol puede ver los registros, informes y valores para el espacio.</li>
   </ul></dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Eliminar el usuario `test@exmaple.com` de la organización `org_example` y el espacio `space_example` con el rol `SpaceManager`:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```

Eliminar el usuario `test@exmaple.com` de la organización `org_example` y el espacio `space_example` con el rol `SpaceManager` en el entorno `env_example`:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

Obtener todos los roles de espacio del usuario actual en la organización específica

```
ibmcloud cfee space-roles ORG [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Obtener todos los roles de espacio del usuario actual en la organización `org_example`:

```
ibmcloud cfee space-roles org_example
```

Obtener todos los roles de espacio del usuario actual en la organización `org_example` y el entorno `env_example`:

```
ibmcloud cfee space-roles org_example --env env_example
```

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

Mostrar usuarios de un espacio especificado por rol

```
ibmcloud cfee space-users ORG SPACE [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización.</dd>
   <dt>SPACE (obligatorio)</dt>
   <dd>El nombre del espacio.</dd>
   <dt>--env ENV</dt>
   <dd>Nombre de entorno CFEE. Si no se especifica, el valor predeterminado es el entorno CFEE actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Mostrar todos los usuarios en el espacio `space_example` y la organización `org_example`:

```
ibmcloud cfee space-users org_example space_example
```

Mostrar todos los usuarios en el espacio `space_example`, la organización `org_example` y el entorno `env_example`:

```
ibmcloud cfee space-users org_example space_example --env env_example
```
