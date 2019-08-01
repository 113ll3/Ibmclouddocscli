---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud billing, view account, view usage, account usage, resource groups, resources, org-usage

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Visualizando o uso para contas, organizações, grupos de recursos e recursos 
{: #ibmcloud_billing}

Use os comandos a seguir para recuperar as informações de uso de recurso e de faturamento.
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Mostre o uso mensal da conta atual (somente administrador de conta):
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

Mostrar o uso mensal de uma organização (somente administrador de conta ou gerenciador de faturamento da organização):
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

Mostre o uso mensal para um grupo de recursos (somente administrador de conta ou administrador de grupo de recursos):
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

Mostre o uso mensal de instâncias de recurso sob a conta atual:
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
  <dd>Exibir dados para o mês e a data especificados usando o formato AAAA-MM. Se não especificado, o uso do mês atual será mostrado.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

## ibmcloud billing enterprise-usage
{: #ibmcloud_billing_enterprise_usage}

Mostrar relatórios de uso corporativo:
```
ibmcloud billing enterprise-usage [--account-group ACCOUNT_GROUP_NAME | --account-group-id ACCOUNT_GROUP_ID | --account ACCOUNT_NAME | --account-id ACCOUNT_ID] [--month MONTH] [--children] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
  <dt>--account ACCOUNT_NAME (opcional)</dt>
  <dd>Nome da conta de destino.</dd>
  <dt>--account-id ACCOUNT_ID (opcional)</dt>
  <dd>ID da conta de destino.</dd>
  <dt>--account-group ACCOUNT_GROUP_NAME (opcional)</dt>
  <dd>Nome do grupo de contas de destino.</dd>
  <dt>--account-group-id ACCOUNT_GROUP_ID (opcional)</dt>
  <dd>ID do grupo de contas de destino.</dd>
  <dt>--children (opcional)</dt>
  <dd>Mostrar relatórios de uso dos filhos.</dd>
  <dt>--month MONTH (opcional)</dt>
  <dd>Mês de destino. Padrão para o mês atual.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>
