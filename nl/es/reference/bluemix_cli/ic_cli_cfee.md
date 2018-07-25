---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Mandatos de CLI para gestionar entorno de empresa de Cloud Foundry (experimental)
{: #ibmcloud_commands_cfee}

<table summary="Gestionar entornos de empresa de Cloud Foundry (experimental)">
<caption>Tabla 1. Gestionar entornos de empresa de Cloud Foundry (experimental)</caption>
 <thead>
 <th colspan="5">Gestionar entornos de empresa de Cloud Foundry (experimental)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](ic_cli_cfee_cli.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](ic_cli_cfee_cli.html#ibmcloud_cfee_environment)</td>
 </tr>
 </tbody>
 </table>
 
 ### ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Listar entornos de CFEE.

```
ibmcloud cfee environments
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:

### ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Mostrar detalles de un entorno CFEE.

```
ibmcloud cfee environment NAME [--id]
```

<strong>Requisitos previos</strong>: Punto final, Inicio de sesión

<strong>Opciones de mandato</strong>:
  <dl>
   <dt>--id</dt>
   <dd>Mostrar solo ID.</dd>
  </dl>

<strong>Ejemplos</strong>:

Mostrar detalles de un entorno CFEE env_example:

```
ibmcloud cfee environment env_example
```

Mostrar ID de un entorno CFEE env_example:

```
ibmcloud cfee environment env_example --id
```
