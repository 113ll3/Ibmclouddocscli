---



copyright:

  years: 2015, 2017
lastupdated: "2017-07-12"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Iniciación a la CLI de {{site.data.keyword.Bluemix_notm}}
{: #getting-started}

La interfaz de línea de mandatos (CLI) de {{site.data.keyword.Bluemix_notm}} ofrece un método unificado para interactuar con aplicaciones, contenedores, infraestructuras y otros servicios mediante una interfaz de línea de mandatos. 

**Restricción**: la CLI de {{site.data.keyword.Bluemix_notm}} no se admite en Cygwin, de modo que no utilice la CLI de {{site.data.keyword.Bluemix_notm}} en la ventana de línea de mandatos de Cygwin.

**Nota**: si la red contiene un servidor proxy HTTP entre el host que ejecuta la CLI y {{site.data.keyword.Bluemix_notm}}, debe especificar el nombre de host y la dirección IP del servidor proxy en la variable HTTP_PROXY.

**Nota: la herramienta de la interfaz de línea de mandatos de ** {{site.data.keyword.Bluemix_notm}} empaqueta una interfaz de línea de mandatos de Cloud Foundry en su instalación. Sin embargo no se permite un uso mixto de mandatos de interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}} `bx xxx` y mandatos de interfaz de línea de mandatos de Cloud Foundry `cf xxx` si tiene su propia instalación de interfaz de línea de mandatos de cf. En su lugar, utilice `bluemix cf` si desea utilizar la interfaz de línea de mandatos de cf para gestionar recursos de Cloud Foundry. Se ejecutarán en un segundo plano los mandatos de la CLI de Cloud Foundry empaquetada en un contexto compartido con la interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}}.  Es más, no se permite `bluemix cf api/login/logout/target`, en su lugar, utilice `bluemix api/login/logout/target`.

## Instalación de la CLI de {{site.data.keyword.Bluemix_notm}}
{: #install_bluemix_cli}

<!-- Online installation Currently Production Only! Please don't forget to replace the domain name-->

### Instalación en línea

Con acceso a una conexión a internet, copie y pegue el siguiente mandato en un terminal consola y ejecútelo.

**macOS**
```
sh <(curl -fsSL https://clis.ng.bluemix.net/install/osx)
```

**Linux**
```
sh <(curl -fsSL https://clis.ng.bluemix.net/install/linux)
```

**Windows PowerShell**

Copie y pegue el mandato siguiente en una consola de terminal de [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell) y ejecútelo.
```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```

### Instalación fuera de línea

<!-- End of online installation -->

Para Mac OS y Windows, descargue el [paquete de CLI de {{site.data.keyword.Bluemix_notm}}](/docs/cli/index.html#downloads) y ejecute el instalador.

Para Linux, siga estos pasos:

  1. Descargue el paquete y extráigalo. Por ejemplo:

  ```
  ~$ tar -xvf Bluemix_CLI.tar.gz
  Bluemix_CLI/
  Bluemix_CLI/update_global_config
  Bluemix_CLI/install_bluemix_cli
  Bluemix_CLI/bx/
  Bluemix_CLI/bx/bash_autocomplete
  Bluemix_CLI/bx/zsh_autocomplete
  Bluemix_CLI/bin/
  Bluemix_CLI/bin/bluemix
  ~$
  ```

  2. Vaya al directorio `Bluemix_CLI` y ejecute el mandato `./install_bluemix_cli` con el permiso root. Puede ejecutar el mandato como usuario root o puede utilizar el mandato `sudo` para obtener el permiso root. Por ejemplo:

  ```
  ~# cd Bluemix_CLI
  ~/Bluemix_CLI# sudo ./install_bluemix_cli
  Superuser privileges are required to run this script.
  The Cloud Foundry CLI version 6.15 is already installed.
  Copying files...
  The Bluemix CLI installed successfully. To get started, open a new Linux terminal and enter "bluemix help", or enter "bx help" as short name.
  ~/Bluemix_CLI#
  ```

Ahora puede empezar a utilizar {{site.data.keyword.Bluemix_notm}} CLI o instalar plug-ins adicionales.

## Primeros pasos con la CLI de {{site.data.keyword.Bluemix_notm}}

Para configurar la herramienta CLI de {{site.data.keyword.Bluemix_notm}}, tendrá que especificar la API a utilizar.  Esto depende de la región con la que estará trabajando. Para obtener una lista, utilice:

```
 ~ $ bluemix regions
Listing Bluemix regions...

Name       Geolocation      Customer   Deployment   Domain               CF API Endpoint                  Type
eu-de      Germany          IBM        Production   eu-de.bluemix.net    https://api.eu-de.bluemix.net    public
au-syd     Sydney           IBM        Production   au-syd.bluemix.net   https://api.au-syd.bluemix.net   public
us-south   US South         IBM        Production   ng.bluemix.net       https://api.ng.bluemix.net       public
eu-gb      United Kingdom   IBM        Production   eu-gb.bluemix.net    https://api.eu-gb.bluemix.net    public
```

Para la región a la que desea acceder, tome el `Punto final de la API de CF` y utilícelo para especificar el punto final de la API, como se indica a continuación:

```
~ $ bluemix api https://api.eu-gb.bluemix.net
Setting api endpoint to https://api.eu-gb.bluemix.net...
OK

API endpoint: https://api.eu-gb.bluemix.net (CF API version: 2.75.0)
Not logged in. Use 'bx login' to log in.
```

Luego siga la solicitud para iniciar sesión:

```
 ~ $ bluemix login
API endpoint: https://api.eu-gb.bluemix.net

Email> user@example.com

Contraseña>
    Autenticando...
    Correcto

```

Se puede especificar la organización y el espacio que se utilizarán con las conmutaciones `-o` y `-s`. De lo contrario, el mandato de inicio de sesión le solicitará que seleccione desde donde tiene más de una.

La CLI de {{site.data.keyword.Bluemix_notm}} ahora está configurada y lista para utilizar.

## Instalación de un plugin
{: #install_plug-in}

La interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}} admite una infraestructura de ampliación de plug-in para integrar otros mandatos además de los que vienen integrados.


Puede instalar un plugin desde el repositorio, de forma local o desde un servidor remoto. {{site.data.keyword.Bluemix_notm}} tiene repositorios que contienen plugins de la CLI de {{site.data.keyword.Bluemix_notm}} y plugins de la CLI de Cloud Foundry:

   * [Repositorio de plugins de la CLI de {{site.data.keyword.Bluemix_notm}}](http://clis.ng.bluemix.net/ui/repository.html#bluemix-plugins){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg), que contiene plugins de la interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}}.

Para instalar desde el repositorio, siga estos pasos:

  1. Busque el plugin en el repositorio. Después de instalar la CLI de {{site.data.keyword.Bluemix_notm}}, el repositorio oficial `Bluemix` se añade de forma predeterminada. Puede ver los plugins del repositorio de `Bluemix` con el mandato `bluemix plugin repo-plugins`. Por ejemplo:

  ```
  ~$ bluemix plugin repo-plugins -r Bluemix
  Getting plug-ins from repository 'Bluemix'...

  Repository: Bluemix
  Name           Description                                    Versions
  auto-scaling   Bluemix CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            Bluemix Network Security Group plugin          0.1.1

  ~$
  ```

  2. Instale el plug-in desde el repositorio de `Bluemix` con el mandato `bluemix plugin install`. Por ejemplo:

  ```
  ~$ bluemix plugin install auto-scaling -r Bluemix
  Looking up 'auto-scaling' from repository 'Bluemix'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```


Para instalar un plugin desde el entorno local, siga estos pasos:

  1. Descargue el plugin. Por ejemplo:

  ```
  ~$ wget http://public.dhe.ibm.com/cloud/bluemix/cli/bluemix-plugins/auto-scaling-darwin-amd64.0.2.2--2016-02-18 14:02:12-- http://public.dhe.ibm.com/cloud/bluemix/cli/bluemix-plugins/auto-scaling-darwin-amd64.0.2.2
  Resolving public.dhe.ibm.com... 9.17.248.112
  Connection to public.dhe.ibm.com|9.17.248.112|:80... connected.
  HTTP request sent, awaiting response... 200 OK
  Length: 9857792 (9.4M) [text/plain]
  Saving to: 'auto-scaling-darwin-amd64-0.2.2'

  auto-scaling-darwin-0.2.2 100%[===================>] 9.40M 518KB/s in 22s

  2016-02-18 14:02:34 (443 KB/s) - `auto-scaling-darwin-amd64-0.2.2' saved [9857792/9857792]
  ```

  2. Para sistemas de tipo UNIX, debe convertir el archivo descargado en ejecutable mediante el mandato `chmod`. Por ejemplo:

  ```
  ~$ sudo chmod 755 auto-scaling-darwin-amd64-0.2.2
  Password:
  ~$
  ```

  3. Instale el plugin con el mandato `bluemix plugin install`. Por ejemplo:

  ```
  ~$ bluemix plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing pluign './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```

Para instalar desde un servidor remoto, siga estos pasos:

  1. Instale el plugin desde un URL remoto directamente con el mandato `bluemix plugin install`. Por ejemplo:

  ```
  ~$ bluemix plugin install http://public.dhe.ibm.com/cloud/bluemix/cli/bluemix-plugins/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```


Ahora estará listo para utilizar las líneas de mandatos de {{site.data.keyword.Bluemix_notm}}. Ejecute `bluemix help` para ver una lista de mandatos y sus descripciones. 

## Póngase en contacto

Utilice las opciones siguientes para encontrar información de la versión, proporcionar comentarios y formular preguntas:
 * Para obtener detalles sobre los releases más recientes y que nos notifiquen los problemas: [{{site.data.keyword.Bluemix_notm}} CLI SDK](https://github.com/IBM-Bluemix/bluemix-cli-sdk){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg)
 * Para formular preguntas y compartir conocimientos con la comunidad: [Canal Slack de la CLI de Bluemix](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg)
