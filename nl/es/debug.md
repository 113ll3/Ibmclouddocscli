---

copyright:
  years: 2015, 2017
lastupdated: "2018-03-27"

---



{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}


# Depuración
{: #debugging}

Si tiene problemas con {{site.data.keyword.Bluemix}}, consulte los archivos de registro para investigar los problemas y depurar los errores.
{:shortdesc}

Los registros dan información si un trabajo se ejecuta correctamente o si falla. También proporcionan información importante que se puede utilizar para la depuración y determinar la causa de un problema.

Los registros tienen un formato fijo. En registros detallados, puede filtrar registros o utilizar hosts de registros externos para almacenar y procesar los registros. Para obtener más información sobre los formatos de registro, los registros de visualización y de filtrado y la configuración de registro externo, consulte [Registro de apps que se ejecutan en Cloud Foundry ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](/docs/monitor_log/logging.html#logging){: new_window}.


## Depuración de errores de transferencia
{: #debugging-staging-errors}
Es posible que tenga algún problema al transferir sus apps en {{site.data.keyword.Bluemix_notm}}. Si la app no se puede transferir, puede buscar y revisar los registros de transferencia (STG) para determinar qué ha ocurrido durante el despliegue de la app y solucionar el problema. Para obtener más información sobre los métodos de visualización de registros para las apps de {{site.data.keyword.Bluemix}}, consulte [visualización de registros ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana){: new_window}.  

Para obtener información explicativa sobre el motivo por el cual su app podría fallar en {{site.data.keyword.Bluemix_notm}}, debe saber cómo se despliega una app en {{site.data.keyword.Bluemix_notm}} y cómo se ejecuta. Para obtener información detallada, consulte [Despliegue de aplicaciones ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](/docs/cfapps/depapps.html#appdeploy){: new_window}.


El procedimiento siguiente muestra cómo puede utilizar el mandato `cf logs` para depurar errores de transferencia. Antes de seguir estos pasos, asegúrese de haber instalado la interfaz de línea de mandatos cf. Para obtener más información sobre la instalación de la interfaz de línea de mandatos cf, consulte [Instalación de la interfaz de línea de mandatos de cf ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](/docs/starters/install_cli.html){: new_window}.

  1. Conecte con {{site.data.keyword.Bluemix_notm}} escribiendo el siguiente código en la interfaz de línea de mandatos cf:
     ```
	 cf api https://api.stage1.ng.bluemix.net
	 ```

  2. Inicie la sesión en {{site.data.keyword.Bluemix_notm}} especificando `cf login`.

  3. Recupere los registros recientes con el mandato `cf logs appname --recent`. Si desea filtrar un registro detallado, utilice la opción `grep`. Por ejemplo, puede introducir el siguiente código para mostrar solo los registros [STG]:
    ```
	cf logs nombre_app --recent | grep '\[STG\]'
	```
  4. Examine el primer error que se visualiza en el registro.

Si utiliza el plug-in de herramientas IBM Eclipse para {{site.data.keyword.Bluemix_notm}} para desplegar apps, en el separador **Consola** de la herramienta Eclipse, verá registros parecidos a los que muestra el mandato cf logs. También puede abrir otra ventana Eclipse para realizar un seguimiento de `los registros` al desplegar la app.

Además del mandato `cf logs`, en {{site.data.keyword.Bluemix_notm}} también puede utilizar el servicio {{site.data.keyword.loganalysisshort}} para recopilar detalles del registro.

### Depuración de errores de transferencia para una app Node.js

El ejemplo siguiente muestra el registro que se muestra después de escribir `cf logs appname --recent`. En el ejemplo se da por supuesto que los errores de transferencia se han producido para una app Node.js:
```
2014-08-11T14:19:36.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({name"=>"SampleExpressApp"}
2014-08-11T14:20:44.17+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STOPPED"})
2014-08-11T14:20:44.19+0100 [App/0]   ERR
2014-08-11T14:20:44.43+0100 [DEA]     OUT Stopping app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:44.44+0100 [DEA]     OUT Stopped app instance (index 0) with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:48.97+0100 [DEA]     OUT Got staging request for app with id 6d80051d-eb56-4fc5-b499-e43d6fb87bc2
2014-08-11T14:20:50.94+0100 [API]     OUT Updated app with guid 6d80051d-eb56-4fc5-b499-e43d6fb87bc2 ({"state"=>"STARTED"})
2014-08-11T14:20:51.66+0100 [STG]     OUT -----> Download app package (4.1M)
2014-08-11T14:20:51.90+0100 [STG]     OUT -----> Download app buildpack cache (1.1M)
2014-08-11T14:20:52.78+0100 [STG]     OUT -----> Buildpack Version: v1.1-20140717-1447
2014-08-11T14:20:52.78+0100 [STG]     ERR parse error: Expected another key-value pair at line 18, column 3
2014-08-11T14:20:52.79+0100 [STG]     OUT 0 info it worked if it ends with ok
```
{: screen}


El primer error del registro muestra la causa de que falle la transferencia. En el ejemplo, el primer error es una salida procedente del componente DEA durante la fase de transferencia.
```
2014-08-11T14:20:52.78+0100 [STG]   ERR parse error: expected another key-value pair at line 18, column 3
```
{: screen}


Para una app Node.js, el DEA utiliza la información del archivo `package.json` para descargar los módulos. A partir de este error, puede ver que se han producido errores para el módulo. Por lo tanto, es posible que tenga que revisar la línea 18 del archivo `package.json`.

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*",
18   }
```
{: screen}


Como puede ver, se ha colocado una coma al final de la línea 17, por lo que se esperaba un par clave-valor en la línea 18. Para solucionar el problema, elimine la coma:

```
15   "jade": "~1.3.0",
16   "mongodb": "*",
17   "monk":"*"
18   }
```
{: screen}


## Debugging runtime errors
{: #debugging-runtime-errors}
Si tiene problemas con la app en tiempo de ejecución, los registros de la app pueden ayudar a identificar la causa del error y a solucionar el problema.

En concreto, se puede habilitar el registro en stdout y stderr. Para obtener más información sobre cómo configurar los archivos de registro para las apps que se despliegan mediante los paquetes de compilación integrados de {{site.data.keyword.Bluemix_notm}}, consulte la lista siguiente:

  * Para las apps Liberty for Java™, consulte [Liberty: registro y rastreo ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/support/knowledgecenter/en/SSEQTP_liberty/com.ibm.websphere.wlp.doc/ae/rwlp_logging.html){: new_window}.
  * Para las apps Node.js, consulte [La depuración de Node.js se inicia con un registro mejor ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/blogs/bluemix/2015/03/node-js-better-logging/){: new_window}.
  * Para las apps PHP, consulte [error_log ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](http://php.net/manual/en/function.error-log.php){: new_window}.
  * Para las apps Python, consulte [Logging HOWTO ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](https://docs.python.org/2/howto/logging.html){: new_window}.
  * Para las apps Ruby on Rails, consulte [The Logger ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](http://guides.rubyonrails.org/debugging_rails_applications.html#the-logger){: new_window}.
  * Para las apps Ruby Sinatra, consulte [Registro ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo")](http://www.sinatrarb.com/intro.html#Logging){: new_window}.

Cuando especifica `cf logs nombre_app --recent` en la interfaz de línea de mandatos cf, solo se muestran los registros más recientes. Para ver los registros en busca de errores producidos anteriormente, debe recuperar todos los registros y buscar los errores. Para recuperar todos los registros correspondientes a la app, siga uno de los siguientes métodos:
<dl>
<dt><strong>{{site.data.keyword.loganalysisshort}}</strong></dt>
<dd>Las funciones integradas de búsqueda y análisis de archivos de registro del servicio {{site.data.keyword.loganalysisshort}} le pueden ayudar a identificar errores rápidamente. Para obtener más información, consulte <a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">{{site.data.keyword.loganalysisfull}}</a>.</dd>
<dt><strong>Herramientas de terceros </strong></dt>
<dd>Puede recopilar y exportar los registros de la app en un host de registro externo. Para obtener más información, consulte <a href="/docs/services/CloudLogAnalysis/log_analysis_ov.html#log_analysis_ov" target="_blank">Configuración de registro externo</a>.</dd>
<dt><strong>Scripts para recopilar y exportar los registros</strong></dt>
<dd>Para utilizar un script a fin de recopilar y exportar automáticamente los registros a un archivo externo, debe conectar con la consola de {{site.data.keyword.Bluemix_notm}} desde el sistema y debe tener suficiente espacio para descargar los registros. Para obtener más información, consulte <a href="/docs/get-support/quicktickresp.html#collecting-diagnostic-information" target="_blank">Recopilación de información de diagnóstico</a>. </dd>
</dl>

Antes se accedía a los archivos `stdout.log` y `stderr.log` de forma predeterminada a través de la vista de app de la consola de {{site.data.keyword.Bluemix_notm}} bajo **Archivos** > **registros**. Sin embargo, este registro de apps ya no está disponible con la versión actual de Cloud Foundry en la que se aloja {{site.data.keyword.Bluemix_notm}}. Para que se pueda acceder al registro de app stdout y stderr a través de la consola de {{site.data.keyword.Bluemix_notm}} bajo **Archivos** > **registros**, puede redirigir el registro a otros archivos del sistema de archivos de {{site.data.keyword.Bluemix_notm}}, en función del tiempo de ejecución que utilice.

  * Para las apps Liberty for Java, la información de salida que se dirige a stdout y stderr ya está contenida en el archivo `messages.log` del directorio logs. Busque las entradas con el prefijo SystemOut y SystemErr respectivamente.
  * Para apps Node.js, puede modificar la función console.log para que escriba específicamente en un archivo del directorio logs.
  * Para las apps PHP, puede utilizar la función error_log para escribir en un archivo del directorio de logs.
  * Para las aplicaciones Python, puede hacer que el registrador escriba en un archivo del directorio logs: `logging.basicConfig(filename='/docs/logs/example.log',level=logging.DEBUG)`
  * Para apps Ruby, puede hacer que el registrador escriba en un archivo del directorio logs.


### Depuración de cambios de código
{: #debug_code_changes}

Si realiza cambios de código en una app que ya está desplegada y en funcionamiento, los cambios no se reflejarán todavía en {{site.data.keyword.Bluemix_notm}} y puede depurar mediante los registros. Independientemente de que su app se esté ejecutando, puede comprobar los registros que se generan durante el despliegue o la ejecución de la app para determinar por qué no se ejecuta el código nuevo.

En función de la forma de desplegar el nuevo código, elija uno de los métodos siguientes para depurar los cambios de código:

  * Para el nuevo código desplegado desde la línea de mandatos, compruebe la salida del mandato *cf push*. Además, puede utilizar el mandato *cf logs* para encontrar más pistas para resolver el problema. Para obtener más información sobre cómo utilizar el mandato *cf logs*, consulte [visualización de registros desde la interfaz de línea de mandatos](/docs/services/CloudLogAnalysis/manage_logs.html#manage_logs).

  * Para el nuevo código que se despliega desde una interfaz gráfica de usuario, como la consola de {{site.data.keyword.Bluemix_notm}}, DevOps Delivery Pipeline o Travis-CI, puede comprobar los registros de la interfaz. Por ejemplo, si despliega el nuevo código desde la consola de {{site.data.keyword.Bluemix_notm}}, puede ir a Panel de control, localizar la app y ver los registros para buscar claves sobre el problema.   Para obtener más información sobre cómo visualizar registros desde la consola de {{site.data.keyword.Bluemix_notm}}, consulte [Visualización de registros desde el panel de control de {{site.data.keyword.Bluemix}}] (/docs/services/CloudLogAnalysis/kibana/analyzing_logs_Kibana.html#analyzing_logs_Kibana).  

