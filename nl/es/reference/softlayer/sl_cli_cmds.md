---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Mandatos de CLI generales (ibmcloud sl)
{: #softlayer_cli}

El plugin de {{site.data.keyword.BluSoftlayer}} se ha fusionado en la CLI de {{site.data.keyword.Bluemix_notm}}. Ya no necesita instalar el plugin.
{: tip}

Utilice los mandatos de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}} en la interfaz de línea de mandatos (CLI) de {{site.data.keyword.Bluemix_notm}} para configurar y gestionar los servicios de SoftLayer.

A partir de mayo de 2018, los mandatos de CLI de {{site.data.keyword.Bluemix_notm}} han cambiado de `bluemix` y `bx` a `ibmcloud`. Sin embargo, todavía puede utilizar los mandatos de CLI `bluemix` y `bx` hasta que se dejen de utilizar en una fecha posterior.
{: tip}

Para empezar, instale la CLI de {{site.data.keyword.Bluemix_notm}}. Consulte
[CLI de IBM Cloud ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window} para obtener más detalles.

Para obtener una lista completa de los mandatos de CLI de {{site.data.keyword.Bluemix_notm}}, consulte: [Mandatos de {{site.data.keyword.Bluemix_notm}} (ibmcloud)](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli).

Se da soporte a los mandatos siguientes. Utilice el mandato `ibmcloud sl` para ver la lista de mandatos disponibles:

<table summary="Mandatos ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">
<caption>Tabla 1. Mandatos de infraestructura generales de {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Mandatos de infraestructura generales de {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_help)</td>
   </tbody>
 </table>
 
 Para ver la información de ayuda de los mandatos, ejecute: `ibmcloud sl [command] -h`
 
 ## ibmcloud sl init
{: #sl_init}

Inicialice los valores de configuración que se utilizan para conectarse al entorno de infraestructura de {{site.data.keyword.BluSoftlayer_notm}}. La configuración incluye nombre de usuario, contraseña o una clave de API, cuenta y punto final.
```
ibmcloud sl init [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>URL de punto final de API de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}, el valor predeterminado es: https://api.softlayer.com/rest/v3.1 para la autenticación de claves de API, https://api.softlayer.com/mobile/v3.1 para la autenticación de IBMid.</dd>
<dt>-u, --sl-user</dt>
<dd>Nombre de usuario de infraestructura Gen1.</dd>
<dt>-p, --sl-password</dt>
<dd>contraseña o clave de API.</dd>
<dt>-c, --account-id</dt>
<dd>ID de cuenta.</dd>
<dt>-q, --security-question-id</dt>
<dd>ID de pregunta de seguridad utilizado para autenticar. Pregunte al propietario de la cuenta si no lo conoce.</dd>
<dt>-w, --security-question-answer</dt>
<dd>Respuesta a la pregunta de seguridad utilizada para autenticar. Pregunte al propietario de la cuenta si no la conoce.</dd>
<dt>-s, --security-code</dt>
<dd>Código de seguridad generado por el proveedor de seguridad cuando está habilitada la autenticación de 2 factores.</dd>
<dt>-v, --security-vendor</dt>
<dd>Proveedor de seguridad que proporciona código de seguridad para la autenticación. Las opciones son: VERISIGN,TOTP,PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>Señal de autenticación cuando se habilita la autenticación telefónica.</dd>
</dl>

Por ejemplo, inicie la sesión con nombre de usuario y contraseña/clave de API de {{site.data.keyword.BluSoftlayer_notm}}
```
$ ibmcloud sl init
Elija cómo configurar la autenticación de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}:
1. Iniciar sesión con nombre de usuario y contraseña/clave de API de {{site.data.keyword.BluSoftlayer_notm}}
2. Utilizar inicio de sesión único de {{site.data.keyword.Bluemix_notm}}
Escriba un número>1
URL de punto final de API de Softlayer: [https://api.softlayer.com/rest/v3.1]>
Nombre de usuario: []> user@example.com
Clave de API o contraseña: []> abcd

Punto final de API:    https://api.softlayer.com/rest/v3.1
Nombre de usuario:       user@example.com
Clave de API:         xxxxxxxxxx
```
Por ejemplo, utilice el inicio de sesión único de {{site.data.keyword.Bluemix_notm}} para iniciar la sesión en Softlayer
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
Punto final de API: api.ng.bluemix.net
Autenticando...
OK

Cuenta de usuario de ejemplo de cuenta de destino (65ce8074c6c62b5)

Punto final de la API:   https://api.ng.bluemix.net (Versión de la API: 2.54.0)   
Región:         us-south
Usuario:           user@example.com
Cuenta:        Cuenta de usuario example (65ce8074c6c62b5)   
Ninguna organización ni espacio de destino. Utilice 'ibmcloud target --cf o ibmcloud target -o ORG -s SPACE'


$ ibmcloud sl init
Elija cómo configurar la autenticación de infraestructura de {{site.data.keyword.BluSoftlayer_notm}}:

1. Iniciar sesión con nombre de usuario y contraseña/clave de API de Softlayer
2. Utilice inicio de sesión único de IBM Cloud
Especifique un número> 2
URL de punto final de API de la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}: [https://api.softlayer.com/mobile/v3.1]>
Estableciendo la cuenta en: 123456
OK

Punto final de API de {{site.data.keyword.BluSoftlayer_notm}}:    https://api.softlayer.com/mobile/v3.1   

ID de cuenta:                123456
ID de usuario:                   user@example.com
Señal de IMS:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

Ver la información de ayuda para que todos los mandatos operen en el entorno de {{site.data.keyword.BluSoftlayer_notm}}.
```
ibmcloud sl help
```
