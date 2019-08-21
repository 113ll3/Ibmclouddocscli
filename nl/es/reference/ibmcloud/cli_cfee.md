---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-31"

keywords: cli, cloud foundry enterprise environment, cfee, ibmcloud cfee, cfee environment, cfee instance, target user, list cfee

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Cómo trabajar con el servicio Cloud Foundry Enterprise Environment
{: #ibmcloud_commands_cfee}

Con {{site.data.keyword.cfee_full}} (CFEE), puede crear instancias de varias plataformas de Cloud Foundry aisladas y de nivel empresarial a petición. Las instancias del servicio de IBM Cloud Foundry Enterprise se ejecutan dentro de su propia cuenta en {{site.data.keyword.cloud_notm}}. El entorno se despliega en hardware aislado (clústeres de Kubernetes). Tiene un control completo sobre el entorno, que incluye el control de accesos, la capacidad, las actualizaciones de versiones, el uso de recursos y la supervisión.

Utilice los mandatos siguientes para gestionar entornos, organizaciones, espacios, usuarios y roles de CFEE.
{: shortdesc}

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Listar entornos de CFEE:
```
ibmcloud cfee environments
```
{: codeblock}

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Mostrar detalles de un entorno CFEE:
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
{: codeblock}

Mostrar ID de un entorno CFEE `env_example`:
```
ibmcloud cfee environment env_example --id
```
{: codeblock}

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

Listar todas las organizaciones:
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
{: codeblock}

Listar todas las organizaciones del entorno CFEE `env_example`:
```
ibmcloud cfee orgs --env env_example
```
{: codeblock}

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Mostrar detalles de una organización:
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
{: codeblock}

Mostrar detalles de una organización CFEE `org_example` del entorno CFEE `env_example`:
```
ibmcloud cfee org org_example --env env_example
```
{: codeblock}

Mostrar GUID de una organización CFEE `org_example`:
```
ibmcloud cfee org org_example --guid
```
{: codeblock}

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Crear una organización:
```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>ORG (obligatorio)</dt>
   <dd>Nombre de la organización que se ha de crear.</dd>
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
{: codeblock}

Crear una organización CFEE `org_example` del entorno CFEE `env_example`:
```
ibmcloud cfee org-create org_example --env env_example
```
{: codeblock}

Crear una organización CFEE `org_example` con la cuota `quote_example`:
```
ibmcloud cfee org org-create org_example --quota quota_example
```
{: codeblock}

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Suprimir una organización:
```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>ORG (obligatorio)</dt>
   <dd>El nombre de la organización que se va a suprimir.</dd>
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
{: codeblock}

Suprimir una organización CFEE `org_example` del entorno CFEE `env_example`:
```
ibmcloud cfee org-delete org_example --env env_example
```
{: codeblock}

Suprimir una organización CFEE `org_example` sin confirmación:
```
ibmcloud cfee org org-delete org_example -f
```
{: codeblock}

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Mostrar usuarios de una organización especificada por rol:
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
{: codeblock}

Mostrar usuarios de la organización CFEE `org_example` del entorno CFEE `env_example`:
```
ibmcloud cfee org-users org_example --env env_example
```
{: codeblock}

Listar todos los usuarios de la organización CFEE `org_example`:
```
ibmcloud cfee org-users org_example -a
```
{: codeblock}

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
{: codeblock}

Asignar el rol `BillingManager` al usuario `test@exmaple.com` en la organización `org_example` del entorno CFEE `env_example`:
```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Eliminar un rol de organización de un usuario (solo gestor de organización o usuario):
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
{: codeblock}

Eliminar el rol `BillingManager` del usuario `test@exmaple.com` de la organización `org_example` del entorno CFEE `env_example`:
```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

Listar todos los espacios:
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

Listar todos los espacios:
```
ibmcloud cfee spaces
```
{: codeblock}

Listar todos los espacios de la organización `org_example` y el entorno CFEE `env_example`
```
ibmcloud cfee spaces -o org_example --env env_example
```
{: codeblock}

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
   <dd>Recuperar y visualizar el guid del espacio. Se suprimirá el resto de la salida del espacio.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nombre de la organización. Si no se especifica, el valor predeterminado es la organización actual.</dd>
   <dt>--security-group-rules</dt>
   <dd>Recuperar las reglas para todos los grupos de seguridad asociados con este espacio.</dd>
  </dl>

<strong>Ejemplos</strong>:

Mostrar detalles de un espacio llamado `space_example`:
```
ibmcloud cfee space space_example
```
{: codeblock}

Recuperar y visualizar el guid del espacio `space_example`:
```
ibmcloud cfee space space_example --guid
```
{: codeblock}

Mostrar las reglas para todos los grupos de seguridad asociados con el espacio `space_example`:
```
ibmcloud cfee space space_example --security-group-rules
```
{: codeblock}

Mostrar detalles del espacio `space_example`, de la org `org_example` y del entorno de CFEE `env_example`:
```
ibmcloud cfee space space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Crear un espacio:
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

Crear un espacio llamado `space_example`:
```
ibmcloud cfee space-create space_example
```
{: codeblock}

Crear un espacio llamado `space_example`, bajo la org `org_example` y el entorno de CFEE `env_example`:
```
ibmcloud cfee space-create space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Renombrar un espacio:
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
{: codeblock}

Renombrar el espacio `space_example` a `new_pace_example` en la organización `org_example` y el entorno CFEE `env_example`:
```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Suprimir un espacio:
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
   <dd>Forzar la supresión sin confirmación.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nombre de la organización. Si no se especifica, el valor predeterminado es la organización actual.</dd>
  </dl>

<strong>Ejemplos</strong>:

Suprimir el espacio `space_example`:
```
ibmcloud cfee space-delete space_example
```
{: codeblock}

Suprimir el espacio `space_example` en la organización `org_example` y el entorno CFEE `env_example` sin confirmación:
```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```
{: codeblock}

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
   <li>SpaceManager: este rol puede invitar y gestionar usuarios, y habilitar características para un espacio.</li>
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
{: codeblock}

Asignar el usuario `test@exmaple.com` a la organización `org_example` y el espacio `space_example` con el rol `SpaceManager` en el entorno `env_example`:
```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
   <li>SpaceManager: este rol puede invitar y gestionar usuarios, y habilitar características para un espacio.</li>
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
{: codeblock}

Eliminar el usuario `test@exmaple.com` de la organización `org_example` y el espacio `space_example` con el rol `SpaceManager` en el entorno `env_example`:
```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
{: codeblock}

Obtener todos los roles de espacio del usuario actual en la organización `org_example` y el entorno `env_example`:
```
ibmcloud cfee space-roles org_example --env env_example
```
{: codeblock}

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
{: codeblock}

Mostrar todos los usuarios en el espacio `space_example`, la organización `org_example` y el entorno `env_example`:
```
ibmcloud cfee space-users org_example space_example --env env_example
```
{: codeblock}

## ibmcloud cfee create
{: #ibmcloud_cfee_create}

Realizar una solicitud para crear una instancia de Cloud Foundry Enterprise Environment:
```
ibmcloud cfee create [-n, --name NAME] [--location LOCATION] [--cells CELLS] [--virtual-dedicated-hardware] [--private-access] [--private-vlan ID, --public-vlan ID] [--plan ID] [-c PARAMETERS_AS_JSON]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>-n, --name NAME (obligatorio)</dt>
  <dd>Especifique el nombre del CFEE. El nombre no debe superar los 24 caracteres, debe comenzar por una letra y solo puede contener caracteres alfanuméricos, '-', '_' y '.'.</dd>
  <dt>--location LOCATION (obligatorio)</dt>
  <dd>Especifique el centro de datos en el que se va a suministrar este CFEE (por ejemplo, dal10). Para ver los centros de datos disponibles, ejecute "ibmcloud cfee create-locations".</dd>
  <dt>--cells CELLS</dt>
  <dd>Especifique el número de células para este CFEE. El valor predeterminado es 2 y el mínimo es 1. En un CFEE de una célula, no puede haber alta disponibilidad.</dd>
  <dt>--private-access</dt>
  <dd>Especifique el tipo de acceso de red para la base de datos PostgreSQL que se suministra como parte de CFEE. Establezca este distintivo solo si la cuenta es VRF y el punto final de servicio está habilitado. Si se establece este distintivo, se utiliza el punto final de acceso privado.</dd>
  <dt>--virtual-dedicated-hardware</dt>
  <dd>Con hardware dedicado, los nodos trabajadores están alojados en la infraestructura dedicada a su cuenta. Con hardware compartido, los recursos de la infraestructura, como el hipervisor y el hardware físico, se comparten con otros clientes de IBM, pero cada uno de los nodos trabajadores es de un único arrendatario. "Shared" es el valor predeterminado si NO se establece este distintivo. El uso de un nodo trabajador dedicado ("dedicated") tiene costes adicionales.</dd>
  <dt>--private-vlan ID</dt>
  <dd>Especifique el ID de la VLAN privada. De forma predeterminada, se utiliza un conjunto disponible de VLAN o se crea un par automáticamente.</dd>
  <dt>--public-vlan ID</dt>
  <dd>Especifique el ID de la VLAN pública. De forma predeterminada, se utiliza un conjunto disponible de VLAN o se crea un par automáticamente.</dd>
  <dt>--plan ID</dt>
  <dd>Especifique el ID del plan. De forma predeterminada, se utiliza un plan estándar.</dd>
  <dt>-c PARAMETERS_AS_JSON</dt>
  <dd>Objeto JSON válido que contiene parámetros de configuración específicos de la api, proporcionados en línea o en un archivo. Para ver una lista de los parámetros de configuración admitidos, consulte https://cloud.ibm.com/apidocs/cfaas#provision-new-cfee-environment para ver la entrada del catálogo en particular. Esto es necesario para el suministro de CFEE de varias zonas. Nota: todos los demás distintivos se pasan por alto y el mandato de CLI gestiona los campos resource_group_id, access_token y refresh_token.</dd>
</dl>

<strong>Ejemplos</strong>:

Crear una instancia denominada `test-cfee` en `dal10`:
```
ibmcloud cfee create test-cfee dal10
```

Crear una instancia `dedicated` denominada `test-cfee` en `dal10` con `4` células:
```
ibmcloud cfee create test-cfee dal10 --cells 4 --isolation dedicated
```

## ibmcloud cfee create-locations
{: #ibmcloud_cfee_create_locations}

Realizar una solicitud para obtener una lista de los centros de datos disponibles para las regiones de destino
```
ibmcloud cfee create-locations [--output FORMAT]
```
{: codeblock}

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Especificar el formato de salida; actualmente solo se admite JSON.</dd>
</dl>

## ibmcloud cfee create-permission-get
{: #ibmcloud_cfee_create_permission_get}

Comprobar si un usuario tiene todos los permisos necesarios para crear una instancia de CFEE. El mandato comprueba las siguientes políticas de acceso para el usuario de destino: editor en los servicios CFEE, rol de administrador en el servicio Kubernetes, rol de editor de la plataforma y rol de gestor de acceso al servicio Cloud Object Storage y rol de desarrollador en el espacio actual de la organización actual para el suministro de Compose for PostgreSQL

```
ibmcloud cfee create-permission-get USER_NAME [-ag, --access-group GROUP_NAME] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>El nombre del usuario.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>El nombre del grupo de acceso en el que se deben comprobar los permisos. El grupo de acceso predeterminado es "cfee-provision-access-group".</dd>
   <dt>--output FORMAT</dt>
   <dd>Especifique el formato de salida de los permisos; actualmente solo se da soporte a JSON.</dd>
  </dl>
  
<strong>Ejemplos</strong>:

Comprobar los permisos de creación de CFEE para el usuario `name@example.com`:
```
ibmcloud cfee create-permission-get name@example.com
```
{: codeblock}

Comprobar los permisos de creación de CFEE para el usuario `name@example.com` y en el grupo de acceso `test-access-group`:
```
ibmcloud cfee create-permission-get name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-permission-set
{: #ibmcloud_cfee_create_permission_set}

Otorgar al usuario todos los permisos necesarios para crear una instancia de CFEE. El mandato crea las siguientes políticas de acceso para el usuario de destino: rol de editor del servicio CFEE, rol de administrador en el servicio Kubernetes, rol de editor de la plataforma y rol de gestor de acceso al servicio Cloud Object Storage y rol de desarrollador en el espacio actual de la organización actual para el suministro de Compose for PostgreSQL

```
ibmcloud cfee create-permission-set USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>USER_NAME (necesario)</dt>
   <dd>El nombre del usuario.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>El nombre del grupo de acceso en el que se van a otorgar los permisos. El grupo de acceso predeterminado es "cfee-provision-access-group".</dd>
  </dl>
  
<strong>Ejemplos</strong>:

Otorgar permisos de creación de CFEE al usuario `name@example.com` mediante el grupo de acceso predeterminado:
```
ibmcloud cfee create-permission-set name@example.com
```
{: codeblock}

Otorgar permisos de creación de CFEE al usuario `name@example.com` mediante el grupo de acceso `test-access-group`:
```
ibmcloud cfee create-permission-set name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-status
{: #ibmcloud_cfee_create_status}

Comprobar el estado de suministro de una instancia de CFEE:
```
ibmcloud cfee create-status NAME or ID [--poll] [--output FORMAT]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>NAME o ID (obligatorio)</dt>
   <dd>El nombre o el ID de la instancia de CFEE.</dd>
   <dt>--poll</dt>
   <dd>Especifique si desea hacer que esta llamada sea recurrente, para sondear hasta alcanzar un estado estable.</dd>
   <dt>--output FORMAT</dt>
   <dd>Especifique el formato de salida del estado; actualmente solo se da soporte a JSON.</dd>
  </dl>

## ibmcloud cfee monitoring-enable
{: #ibmcloud_cfee_monitoring-enable}

Habilitar la supervisión en el entorno CFEE de destino:
```
ibmcloud cfee monitoring-enable
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
  </dl>

## ibmcloud cfee monitoring-disable
{: #ibmcloud_cfee_monitoring-disable}

Inhabilitar la supervisión en el entorno CFEE de destino:
```
ibmcloud cfee monitoring-disable
```
{: codeblock}

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
  </dl>

## ibmcloud cfee monitoring-status
{: #ibmcloud_cfee_monitoring-status}

Comprobar el estado de la operación de habilitación o inhabilitación de supervisión más reciente en el entorno CFEE de destino:
```
ibmcloud cfee monitoring-status [--poll]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>--poll</dt>
   <dd>Especifique esta opción si desea hacer que esta llamada sea recurrente, para sondear hasta alcanzar un estado estable</dd>
  </dl>
