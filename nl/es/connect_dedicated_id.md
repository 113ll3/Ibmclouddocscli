---



copyright:

  years: 2015，2018

lastupdated: "2018-05-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Conexión de un ID dedicado a su IBMid público
{: #connect_dedicated_id}

Para iniciar sesión en una nube dedicada en la que el servicio IAM público está disponible, la CLI de {{site.data.keyword.Bluemix_notm}} le solicita iniciar sesión con el IBMid público en lugar del ID dedicado.


```
  $ ibmcloud login -a https://api.{dedicated_env}.bluemix.net
  Punto final de la API: https://api.{dedicated_env}.bluemix.net

  El servicio de señal de IAM público está disponible en el entorno dedicado.
  Inicie sesión con su IBMid público, o utilice '--no-iam' para iniciar sesión sólo como un usuario dedicado.

  Correo electrónico>
```

Si el ID dedicado ya se ha conectado al IBMid público, se autentica y se inicia sesión:

```
  Autenticando...
  Correcto

  Conectado con el usuario dedicado my_dedicated_id
```

Sin embargo, si el ID dedicado no se ha conectado con el IBMid público, se le solicita que se conecte manualmente al IBMid público:

```
  Está registrándose con IBMid no asociado con ningún usuario dedicado.
  Para configurar la conexión, especifique las credenciales del usuario dedicado.

  Elija un tipo de credencial:
  1. Nombre de usuario y contraseña
  2. Código de un solo uso (obtenga uno en https://login.{dedicated_env}.bluemix.net.com/passcode)
  Escriba un número>
```

Seleccione una opción para la entrada de credenciales para el ID dedicado. Después de una autenticación satisfactoria, el ID dedicado se conecta a su IBMid público.

## Forzar el inicio de sesión en el servidor local UAA

Para forzar el inicio de sesión en el servidor UAA con un ID dedicado, especifique la opción `--no-iam` en el mandato `ibmcloud login`:

```
  $ ibmcloud login --no-iam
```

## Desconectar el ID dedicado del IBMid público

Puede utilizar `ibmcloud iam dedicated-id-disconnect` para desconectar el IBMid público y el ID dedicado conectado.

```
  $ ibmcloud iam dedicated-id-disconnect
  ¿Realmente desea desconectar a my_dedicated_id del IBMid público? (S/N)> s
  Desconectando el usuario dedicado my_dedicated_id del IBMid público...
  Correcto

  Cerrando sesión...
  Correcto
```
