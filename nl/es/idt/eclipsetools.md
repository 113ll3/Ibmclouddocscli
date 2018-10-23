---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-18"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Despliegue de apps con IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}
{: #deploying-apps-with-ibm-eclipse-tools-for-ibm-cloud}

IBM® Eclipse Tools for {{site.data.keyword.Bluemix}} proporciona plug-ins que se pueden instalar en un entorno de Eclipse existente para ayudar a integrar el entorno de desarrollo integrado (IDE) del desarrollador con Bluemix®. Las herramientas le permiten desplegar los archivos JavaScript, WAR (archivo web) y EAR (archivo empresarial), y los servidores empaquetados de Liberty Profile en el servidor de Cloud directamente desde el IDE de Eclipse, o WebSphere® Application Server Developer Tools (WDT). Las herramientas también le permiten crear y enlazar servicios a su aplicación y definir variables de entorno como parte del despliegue.

Si ya tiene la aplicación en ejecución en Eclipse utilizando Websphere Application Developer Tools con el perfil de Liberty, puede instalar estas herramientas en la parte superior del programa en ejecución. Puede desplegar las aplicaciones añadiendo la aplicación al servidor de Cloud en el entorno de trabajo. Gracias a las características exclusivas del paquete de compilación de Liberty para el soporte de servidor empaquetado, también tiene una opción para desplegar todo el servidor de perfiles Liberty en Cloud. También puede desplegar aplicaciones JavaScript de Node.js en Cloud.

## Instalación de Eclipse Tools

Aprenda a instalar las IBM Eclipse Tools para {{site.data.keyword.Bluemix_notm}}. Es necesario un entorno de ejecución Java™ 1.7 o posterior.

Existen varias formas de instalar las IBM Eclipse Tools para {{site.data.keyword.Bluemix_notm}}, entre ellas:
* Instalación desde Marketplace.
* Instalación desde WASDev.
* Descarga desde el IBM WebSphere Application Server Developer Tools (WDT) Installer.

### Instalación desde Marketplace

La instalación requiere [Eclipse Oxygen for Java EE Developers (4.7)](https://www.eclipse.org/downloads/packages/release/oxygen/r/eclipse-ide-java-developers) o [Eclipse Neon for Java EE Developers (4.6)](http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers).

A continuación, siga las instrucciones que se muestran aquí: [https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help](https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help).

### Instalación desde WASDev

1. Abra la página [Descarga](https://developer.ibm.com/wasdev/downloads/) en WASDev.
2. Arrastre el icono `Instalar` a la barra de herramientas de Eclipse.
3. De forma predeterminada, hay características que se seleccionan para usted. Pulse **Confirmar**.
4. Acepte el acuerdo de licencia y pulse **Finalizar**.

### Descarga desde el IBM WebSphere Application Server Developer Tools (WDT) Installer

1. Abra **Ayuda > Instalar software WebSphere**. Busque Cloud
2. Seleccione la entrada `IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}` y pulse **Instalar**.
3. De forma predeterminada, hay características que se seleccionan para usted. Pulse **Confirmar**.
4. Acepte el acuerdo de licencia y pulse **Finalizar**.

## Soporte de servidores empaquetados

Con IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, hay varios casos de ejemplo para enviar por push un servidor de Liberty o un servidor empaquetado a Cloud y confirmar el despliegue.

* Cree el servidor en la nube.
* Cree un servidor de perfiles de Liberty con un archivo WAR o EAR.
* Detenga el servidor.

Con IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} para el soporte del servidor empaquetado, hay varios casos de ejemplo para:

* Enviar por push un servidor de Liberty a Cloud.
* Enviar por push un servidor empaquetado de Liberty a Cloud.
* Confirmar el despliegue correcto de la aplicación con una prueba.

Además, puede importar archivos comprimidos de servidor empaquetados en cualquier proyecto del espacio de trabajo.

### Caso de ejemplo 1 - Adición de un servidor Liberty detenido a Cloud y prueba de una aplicación

1. Pulse con el botón derecho del ratón el servidor de `Cloud` en la vista Servidores.
2. Seleccione **Añadir y eliminar**.
3. En el recuadro de diálogo, se muestran las instancias del servidor de Liberty. Seleccione una y pulse **Añadir**.
4. Pulse **Finalizar**.
5. En el diálogo de la aplicación, el nombre predeterminado se deriva de la instancia de servidor Liberty. Puede cambiar este nombre, pero no debe contener espacios ni caracteres especiales. El valor predeterminado es aceptable si no entra en conflicto con el nombre de las aplicaciones existentes en el servidor de Cloud.
6. Pulse **Finalizar** y, a continuación, espere a que la aplicación publique en Cloud.
7. Pulse con el botón derecho del ratón en el módulo de servidor de Liberty añadido bajo el servidor de Cloud. Seleccione **Abrir página de inicio**. Se abre el URL raíz del servidor empaquetado en el navegador web predeterminado. Utilice este URL raíz como base para crear el URL para realizar pruebas en las aplicaciones WAR y EAR empaquetadas.

### Caso de ejemplo 2 - Arrastrar y soltar un servidor de Liberty detenido a Cloud

En el caso de ejemplo 1 se ha descrito cómo añadir y eliminar módulos del servidor Liberty. Esta tarea se puede simplificar con una función de arrastrar y soltar.

1. Si continúa con el caso de ejemplo 1, elimine el módulo del servidor de Liberty del servidor de Cloud.
2. Seleccione y arrastre la instancia de servidor de Liberty detenida y suéltela en el servidor de Cloud en la vista Servidores. Aparece la ventana de diálogo de la aplicación.
3. Siga los pasos 5 a 10 del Caso de ejemplo 1.

### Caso de ejemplo 3 - Ejecutar un servidor empaquetado en Cloud

El menú contextual de la instancia de servicio de perfil de Liberty incluye una acción de Servidor de paquete. Esta acción empaqueta el servidor en un archivo de archivado. En la Cloud, se ha añadido una nueva acción para empaquetar el servidor en un archivo comprimido y desplegarlo en IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

1. Si continúa con el Caso de ejemplo 1 o 2, elimine el módulo del servidor de Liberty del servidor de Cloud.
2. Pulse con el botón derecho en la instancia del servidor de perfiles de Liberty en la vista Servidores.
3. En el menú Programas de utilidades, seleccione **Servidor de paquete a {{site.data.keyword.Bluemix_notm}}**.
4. En el recuadro de diálogo, seleccione el servidor de Cloud en el que desea desplegar la aplicación.
5. Pulse **Aceptar**. Aparece la ventana de diálogo de la aplicación.
6. Siga los pasos 5 a 10 del Caso de ejemplo 1.
7. Si se abre una ventana de diálogo de progreso, elija **Ejecutar como programa de fondo** y espere a que la aplicación se haya desplegado.

### Caso de ejemplo 4 - Trabajar con archivos comprimidos del servidor empaquetado - Ejecutar en el servidor

En los casos de ejemplo anteriores se describe cómo trabajar con las instancias de Liberty Server existentes en la vista Servidores y cómo puede desplegarlas en Cloud. También puede desplegar archivos comprimidos del servidor empaquetado existente en Cloud.

1. Cree u obtenga un archivo comprimido de servidor empaquetado.
2. Importe el archivo comprimido en cualquier proyecto del espacio de trabajo.
3. Pulse con el botón derecho del ratón en el archivo comprimido y seleccione **Ejecutar como > Ejecutar en servidor**. Aparece la ventana de diálogo Ejecute en servidor.
4. Seleccione un servidor de Cloud.
5. Pulse **Finalizar**. Aparece la ventana de diálogo de la aplicación.
6. Siga los pasos 5-10 del caso de ejemplo 1. El nombre del módulo se deriva del archivo comprimido.

### Caso de ejemplo 5 - Trabajar con archivos comprimidos del servidor empaquetado - Arrastrar y soltar

1. Seleccione y arrastre el archivo comprimido de servidor empaquetado y, a continuación, suéltelo en el servidor de Cloud en la vista Servidores. Aparece la ventana de diálogo de la aplicación.
2. Siga los pasos 5-10 del caso de ejemplo 1. El nombre del módulo se deriva del nombre del archivo comprimido.

## Envío de un archivo EAR

Utilice las IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} para enviar por push un EAR a Cloud.

Defina un nuevo servidor.

1. Para crear un nuevo servidor de Cloud, seleccione **Archivo > Nuevo > Otros**.
2. Seleccione **Servidor** en la categoría Servidor y, a continuación, pulse **Siguiente**.
3. En IBM, busque Cloud.
4. Pulse **Siguiente**.
5. Especifique la información de su cuenta de Cloud. Pulse **Registrarse** si no tiene una cuenta.
6. Pulse **Siguiente**.
7. Seleccione sus organizaciones y espacios. El valor predeterminado es `dev`.
8. Pulse **Siguiente**.
9. Pulse **Finalizar**.

Importar un archivo EAR

1. Pulse con el botón derecho del ratón y seleccione **Importar**.
2. Busque el archivo EAR.
3. Busque el archivo EAR que desea importar.
4. Asegúrese de que el tiempo de ejecución de destino se establezca en el Tiempo de ejecución de {{site.data.keyword.Bluemix_notm}}.

Desplegar la aplicación.

1. Pulse con el botón derecho del ratón en el servidor de Cloud iniciado. Seleccione **Añadir y eliminar**.
2. Seleccione el archivo EAR y pulse **Añadir**.
3. Pulse **Finalizar**. Se abre la ventana Detalles de la aplicación.
4. Asigne un nombre a la aplicación y pulse **Siguiente**. Un nombre válido puede contener los caracteres A-Z, 0-9, - y _. No puede contener espacios ni otros caracteres especiales. La información de Inicio de despliegue se establece de forma predeterminada.
5. Pulse **Siguiente**.
6. Si es necesario, seleccione servicios. Pulse **Siguiente**.
7. Si es necesario, añada variables. Pulse **Finalizar**.
8. Una vez enviada la aplicación, pulse con el botón derecho en el proyecto y seleccione **Abrir página de inicio**.
9. Añada el nombre del módulo web y el nombre de la aplicación al URL.
10. Para guardar los valores y variables que ha especificado, marque el recuadro de selección **Guardar en el archivo de manifiesto** en la ventana Detalles de la aplicación.

## Despliegue de una aplicación Node.js
Utilice IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} para desplegar un proyecto de Node.js existente o nuevo en Cloud, establecer los detalles del despliegue de la aplicación y verificar los resultados en un navegador.

Si aún no tiene una aplicación Node.js existente, empiece por el Paso 1. Si ya tiene una aplicación Node.js existente, empiece por el Paso 7.

1. Seleccione **Archivo > Nuevo > Proyecto**.
2. Seleccione **Proyecto de JavaScript** en la categoría JavaScript.
3. Pulse **Siguiente**.
4. Asigne un nombre al proyecto.
5. Pulse **Finalizar**.

Defina un nuevo servidor.

1. Para crear un nuevo servidor de Cloud, seleccione **Archivo > Nuevo > Otros**.
2. Seleccione **Servidor** en la categoría Servidor y, a continuación, pulse **Siguiente**.
3. En IBM, busque Cloud.
4. Pulse **Siguiente**.
5. Especifique la información de su cuenta de Cloud. Pulse **Registrarse** si no tiene una cuenta.
6. Pulse **Siguiente**.
7. Seleccione sus organizaciones y espacios. El valor predeterminado es `dev`.
8. Pulse **Siguiente**.
9. Pulse **Finalizar**.

Habilitar la aplicación para publicar en la Cloud

1. Pulse con el botón derecho del ratón en el proyecto en el Explorador de proyectos y seleccione **Propiedades > Faceta de proyecto**.
2. Pulse **Convertir en formato de faceta**.
3. En Facetas de proyecto, seleccione **Aplicación Node.js**.
4. Pulse **Aceptar**.

Desplegar la aplicación.

1. Pulse con el botón derecho del ratón en el servidor de Cloud iniciado. Seleccione **Añadir y eliminar**.
2. Seleccione el proyecto y pulse **Añadir**.
3. Pulse **Finalizar**. Se abre la ventana Detalles de la aplicación.
4. Para guardar la configuración de despliegue en el archivo de manifiesto de la aplicación, seleccione el recuadro de selección **Guardar en el archivo de manifiesto** en la ventana Detalles de la aplicación.
5. Asigne un nombre a la aplicación y pulse **Siguiente**. Un nombre válido puede contener los caracteres A-Z, 0-9, - y _. No puede contener espacios ni otros caracteres especiales.
6. Acepte los valores predeterminados en el panel de información Iniciar despliegue.
7. Pulse **Siguiente**.
8. Si es necesario, seleccione servicios. Pulse **Siguiente**.
9. Si es necesario, añada variables. Pulse **Finalizar**.
10. Una vez enviada la aplicación, pulse con el botón derecho en el proyecto y seleccione **Abrir página de inicio**.

## Publicación incremental

Puede actualizar los archivos de la aplicación de forma incremental sin necesidad de volver a enviar por push la aplicación completa.
La publicación incremental evita la necesidad de realizar un redespliegue completo para cada cambio, lo que ahorra tiempo a lo largo del proceso de desarrollo.

Esta característica da soporte a aplicaciones web (WAR y EAR) y servidores empaquetados.

Para utilizar la publicación incremental, la [Modalidad de desarrollo](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) debe estar habilitada para la aplicación o el servidor empaquetado.

1. Añada una aplicación o un servidor empaquetado a Cloud, a menos que exista una.
**Nota:** Esta función no se puede habilitar si el nombre de despliegue de la aplicación tiene un carácter de subrayado.

2. Habilite la modalidad de desarrollo pulsando con el botón derecho del ratón en la aplicación o servidor empaquetado y seleccionando **Habilitar modalidad de desarrollo**.

Una vez que la modalidad de desarrollo esté habilitada, utilice la función de publicación incremental:

1. Modifique la aplicación como desee.
   **Nota:** Para los servidores empaquetados, las modificaciones en la configuración no están soportadas.

2. Guarde los cambios.

3. Pulse con el botón derecho del ratón en el servidor de Cloud y seleccione **Publicar**.

Modalidades en memoria caché: Después de reiniciar el entorno de trabajo, si la aplicación estaba en modalidad de desarrollo o en modalidad de depuración, verá una ventana de progreso que indica "Recuperando estados de desarrollo y de depuración". En consecuencia, una vez finalizado el progreso, la modalidad de desarrollo y la modalidad de depuración se renueva.

## Depuración remota

Ejecute la depuración remota en una aplicación Liberty o Node.js.

[Modalidad de desarrollo](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) debe estar habilitada para ejecutar la depuración. Esta modalidad se ejecuta automáticamente al seleccionar Habilitar depuración de la aplicación.

### Habilitar la depuración de archivador empresarial (EAR), archivo web (WAR) o servidor de Liberty

Actualmente, se genera aleatoriamente un puerto local libre, pero si un cortafuegos de cliente lo bloquea, el caso de ejemplo de depuración falla. Para eludir esta opción, inicie la modalidad de desarrollo, localice el archivo bluemixcache.xml y añada port="#", donde # es el número de puerto de la máquina local.

1. En el servidor de Cloud, pulse con el botón derecho del ratón la aplicación que desee depurar.

   **Nota:** Esta función no se puede habilitar si el nombre de despliegue de la aplicación tiene un carácter de subrayado. Cambie el nombre antes de habilitar la depuración remota.

2. Pulse **Habilitar depuración de la aplicación**.

   La Vista de progreso muestra el estado de `Establecimiento de la sesión de depuración para <AppName>``.

   La aplicación muestra que se está `Desarrollando, Depurando <AppName>`.

   El depurador se está ejecutando y está listo para su uso.

### Inhabilitar la depuración de EAR, WAR o de Liberty Server

Puede inhabilitar el proceso de depuración y dejar la modalidad de desarrollo habilitada.

1. Pulse con el botón derecho del ratón en la aplicación.
2. Pulse **Inhabilitar depuración de la aplicación**.
3. Un recuadro de diálogo le solicita si también desea inhabilitar la modalidad de desarrollo. Pulse **Sí** o **No**.

Si la modalidad de desarrollo permanece en ejecución, la aplicación muestra que se está `Desarrollando <AppName>``.

 Si ambas están inhabilitadas, la aplicación muestra que se `Despliega como <AppName>`.

### Habilitar la depuración de aplicaciones Node.js

**Nota:** Antes de completar los pasos siguientes, asegúrese de que dispone de una aplicación de JavaScript existente que se ha desplegado en Cloud. Consulte los pasos anteriores para obtener más información sobre el despliegue de una aplicación JavaScript.

1. En la vista Servidores, pulse con el botón derecho del ratón en la aplicación Node.js y seleccione **Abrir** Depurador de JavaScript. Aparece un recuadro de diálogo y le pregunta si desea aumentar el límite de memoria de la aplicación.
2. Pulse Sí. La habilitación de la Depuración de JavaScript aumenta los requisitos de memoria de la aplicación, y la aplicación se reinicia más rápidamente con el límite de memoria actualizado.
3. Seleccione una instalación del navegador que desea utilizar para la depuración. Google Chrome es el único navegador soportado. Si Google Chrome no es una opción disponible, seleccione el enlace **Gestionar...** y añada un enlace a una instalación local de Google Chrome.
4. Pulse **Aceptar**. Aparece un supervisor de progreso que indica la actualización (de su app) en la modalidad de depuración. Una vez que la depuración esté habilitada, Google Chrome se abrirá en el sitio correcto.
5. Autentíquese en Google Chrome con su nombre de inicio de sesión y contraseña. Después de una autenticación correcta, se abre la consola de depuración. Ahora puede depurar la aplicación.

Modalidades en memoria caché: Después de reiniciar el entorno de trabajo, si la aplicación estaba en modalidad de desarrollo o en modalidad de depuración, verá una ventana de progreso que indica Recuperando estados de desarrollo y de depuración. Una vez finalizado el progreso, se renuevan la modalidad de desarrollo y de depuración.

## Conexión a un servidor de Liberty remoto

Aprenda a utilizar IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} para conectarse a un servidor de Liberty remoto. Puede conectarse a un servidor de Liberty remoto que ejecute WebSphere Application Server como un servicio.

Para conectarse a un servidor de Liberty remoto, Liberty Tools debe estar instalado. También debe crear un servicio de WebSphere Application Server en Cloud.

1. Pulse con el botón derecho del ratón en el servidor de Cloud y seleccione **Configurar servidores remotos...**.

   Esta opción solo está disponible si están instaladas las Liberty Tools.

2. Seleccione un servicio de WebSphere Application Server.

   Si no tiene un servicio de WebSphere Application Server, puede recibir un mensaje de error. Debe crear un servicio de WebSphere Application Server en Cloud antes de poder completar esta configuración.

3. Para definir un entorno de ejecución, seleccione **Configurar entornos de ejecución...**.

   **Nota:** Si ha creado anteriormente un entorno de ejecución, puede saltarse este paso.

4. Pulse **Siguiente**.

5. Entre la información de conexión de servidor.

6. Pulse **Finalizar**.

Ha conectado a un servidor de Liberty remoto utilizando IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

## Habilitación de Cloud Foundry Diego on Cloud Applications

Habilite la función de arquitectura de Diego desde dentro de IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. Para habilitar Diego, necesita un servidor de Cloud que esté definido en la vista Servidores.

Diego es una nueva arquitectura de Cloud Foundry que las instancias de Cloud Foundry utilizan para gestionar contenedores de aplicaciones en ejecución. La arquitectura de Diego sustituye a la arquitectura de Droplet Execution Agents (DEA) que Cloud Foundry utilizaba anteriormente. Las instalaciones de Cloud Foundry se van a trasladar a Diego, y las aplicaciones de usuario cambian de forma automática y transparente a la nueva arquitectura.

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} da soporte a Diego y DEA. Puede publicar aplicaciones, habilitar la publicación de aplicaciones incrementales y las aplicaciones de depuración. Diego también permite a IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} crear túneles Secure Shell (SSH) en aplicaciones Cloud desplegadas, lo que permite conexiones más rápidas y fiables a aplicaciones Cloud durante la depuración. También puede habilitar SSH de modo que pueda crear sus propios túneles para acceder a los recursos de la aplicación.

Complete los pasos siguientes para utilizar la arquitectura de Diego para las aplicaciones antes de que los conmutadores Cloud se desplieguen con Diego de forma predeterminada:

1. Pulse con el botón derecho del ratón en la aplicación desplegada en la vista Servidores.
2. Si Diego está soportado en el servidor de Cloud, y la aplicación aún no se ha desplegado con Diego, seleccione **Habilitar Diego** en el menú.
3. Si el servidor da soporte al tunelado de SSH, el programa le solicita si desea habilitar SSH para la aplicación. Los túneles SSH son un mecanismo más fiable para comunicarse con la aplicación. Sin embargo, si selecciona **No**, las funciones de IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} siguen funcionando utilizando un mecanismo que no requiere tunelado de SSH.

La aplicación se redesplegará utilizando la arquitectura de Diego.

## Creación de un servidor con Cloud Enterprise Federation

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} da soporte a Cloud Enterprise Federation, un servicio de inicio de sesión único que permite a los usuarios acceder de forma segura a los servicios de la nube. Con Cloud Enterprise Federation, puede habilitar una autenticación de terceros personalizada que proporcione su propia organización, sin la autenticación de inicio de sesión estándar, para que otros usuarios accedan de forma segura a las aplicaciones.

Cloud Enterprise Federation autentica un conjunto de usuarios para acceder a los servicios de nube. Después de habilitar Cloud Enterprise Federation, los usuarios reciben autenticación para las aplicaciones habilitadas para la nube a través de la opción de inicio de sesión único. Los usuarios deben seleccionar la opción de inicio de sesión único para crear un servidor en el entorno de trabajo de Eclipse y el inicio de sesión con el inicio de sesión y la contraseña de la organización. Después de habilitar Cloud Enterprise Federation, el ID de usuario y la contraseña de Cloud tradicionales en Eclipse Tools ya no se utilizan para autenticar usuarios.

1. En IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, seleccione **Archivo > Nuevo > Otros...**.
2. Seleccione **Servidor > Servidor > Siguiente**.
3. En el árbol, seleccione **IBM > {{site.data.keyword.Bluemix_notm}} > Siguiente**.
4. Seleccione el recuadro de selección **Utilizar una contraseña única para iniciar sesión (SSO)**.
5. Aparece un hiperenlace en el diálogo de inicio de sesión. Pulse el hiperenlace para abrir la página de autenticación de Cloud.
6. Especifique su dirección de correo electrónico y la contraseña que desee.
7. Después de un inicio de sesión correcto, se le proporcionará un código de acceso de un solo uso. Copie este código de acceso en el campo Código de paso: del diálogo Eclipse Tools for Cloud New Server.
8. Pulse **Finalizar**.

Una entrada de servidor Cloud se lista en la vista Servidores con el estado Conectado como Servidor.
