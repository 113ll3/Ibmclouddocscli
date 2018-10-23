---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Faturamento 
{: #ibmcloud_billing}

Use os comandos a seguir para recuperar as informações de uso de recurso e de faturamento.
{: shortdesc}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar o faturamento e o uso do {{site.data.keyword.Bluemix_notm}}.">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud billing account-usage](cli_billing.html#ibmcloud_billing_account_usage)</td>
  <td>[ibmcloud billing org-usage](cli_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>
 
 
 ## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Mostrar o uso mensal da conta atual (somente administrador de conta)

```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Exibir dados para o mês e a data especificados usando o formato AAAA-MM. Se não especificado, o uso do mês atual será mostrado.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar o relatório de uso e de custo da conta atual em 06/2016:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Mostrar o uso mensal para uma organização (somente administrador da conta ou gerenciador de faturamento da
organização)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
  <dt>ORG_NAME (necessário)</dt>
  <dd>Nome da organização.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Exibir dados para o mês e a data especificados usando o formato AAAA-MM. Se não especificado, o uso do mês atual será mostrado.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Mostrar o uso mensal para um grupo de recursos (somente administrador de conta ou administrador de
grupo de recursos)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
  <dt>GROUP_NAME (obrigatório)</dt>
  <dd>Nome do grupo de recursos.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Exibir dados para o mês e a data especificados usando o formato AAAA-MM. Se não especificado, o uso do mês atual será mostrado.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Mostrar o uso mensal das instâncias de recursos sob a conta atual.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
  <dt>-o ORG_NAME (opcional)</dt>
  <dd>Filtrar instâncias por organização.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filtrar instância por grupo de recursos.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Exibir dados para mês e data especificada usando o formato AAAA-MM. Se não especificado, o uso do mês atual será mostrado.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>
