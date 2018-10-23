---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Load Balancer

O serviço {{site.data.keyword.Bluemix}} Load Balancer ajuda a melhorar a disponibilidade dos aplicativos críticos para os negócios, distribuindo o tráfego entre as múltiplas instâncias do servidor de aplicativos e encaminhando-o somente para as instâncias funcionais.

Use os comandos a seguir para gerenciar os balanceadores de carga no serviço Load Balancer da infraestrutura do {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Comandos do Load Balancer do {{site.data.keyword.Bluemix_notm}} ordenados alfabeticamente com os links para as informações adicionais do comando">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[Sl loadbal cancel ibmcloud](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_cancel)</td>
 <td>[ibmcloud sl loadbal create](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create)</td>
 <td>[ibmcloud sl loadbal create-options
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create_options)</td>
 <td>[Sl loadbal detail ibmcloud](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_detail)</td>
 <td>[Ibmcloud sl loadbal group-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_add)</td>
 <td>[Ibmcloud sl loadbal group-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_delete)</td>
 </tr>
 <tr>
 <td>[Ibmcloud sl loadbal group-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_edit)</td>
 <td>[Ibmcloud sl loadbal group-reset](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_reset)</td>
 <td>[ibmcloud sl loadbal health-checks
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_health_checks)</td>
 <td>[ibmcloud sl loadbal list
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_list)</td>
 <td>[ibmcloud sl loadbal routing-methods
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_methods)</td>
 <td>[ibmcloud sl loadbal routing-types
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_types)</td>
 </tr>
 <tr>
 <td>[Ibmcloud sl loadbal service-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_add)</td>
 <td>[Ibmcloud sl loadbal service-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_delete)</td>
 <td>[Ibmcloud sl loadbal service-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_edit)</td>
 <td>[Ibmcloud sl loadbal service-toggle](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_toggle)</td>
 </tr>
</tbody>
 </table>

 ## Sl loadbal cancel ibmcloud
{: #sl_loadbal_cancel}

Cancelar um balanceador de carga existente.
```
Ibmcloud sl loadbal cancel LOADBAL_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl loadbal create
{: #sl_loadbal_create}

Inclui um balanceador de carga devido ao ID retornado de opções de criação.
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

Obter opções de preço para criar um balanceador de carga.
```
ibmcloud sl loadbal create-options
```

## Sl loadbal detail ibmcloud
{: #sl_loadbal_detail}

Obter detalhes do balanceador de carga.
```
Sl loadbal detail LOADBAL_ID ibmcloud
```

## Ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

Inclui um novo serviço de balanceador de carga.
```
Ibmcloud sl loadbal group-add LOADBAL_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Requerido. O percentual de conexões alocado.</dd>
<dt>-p, --port</dt>
<dd>Requerido. O número da porta.</dd>
<dt>-t, --routing-type</dt>
<dd>Requerido. O ID do tipo de roteamento. Execute 'ibmcloud sl loadbal routing-types' para localizar um ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Requerido. O ID do método de roteamento. Execute 'ibmcloud sl loadbal routing-methods' para localizar um ID.</dd>
</dl>

## Ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

Exclui um grupo de serviços do balanceador de carga existente.
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## Ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

Editar um grupo de serviços do balanceador de carga existente.
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Mudar o percentual de conexões alocado.</dd>
<dt>-p, --port</dt>
<dd>Mudar o número da porta.</dd>
<dt>-t, --routing-type</dt>
<dd>Mude o ID do tipo de roteamento. Execute 'ibmcloud sl loadbal routing-types' para localizar um ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Mude o ID do método de roteamento. Execute 'ibmcloud sl loadbal routing-methods' para localizar um ID.</dd>
</dl>

## Ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

Reconfigurar conexões em um determinado grupo de serviços.
```
Ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

## ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

Listar tipos de verificação de funcionamento.
```
ibmcloud sl loadbal health-checks
```

## ibmcloud sl loadbal list
{: #sl_loadbal_list}

Listar balanceadores de carga ativos.
```
ibmcloud sl loadbal list
```

<strong>Opções de comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>-o, --order</dt>
<dd>Filtrar pelo ID da ordem que comprou o balanceador de carga.</dd>
<dt>-p, --ip-address</dt>
<dd>Filtrar pelo endereço IP.</dd>
</dl>

## ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

Listar métodos de roteamento.
```
ibmcloud sl loadbal routing-methods
```

## ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

Listar tipos de roteamento.
```
ibmcloud sl loadbal routing-types
```

## Ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

Inclui um novo serviço do balanceador de carga.
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--disabled</dt>
<dd>Opcional. Crie o serviço como desativado, o padrão será ativado, se não especificado.</dd>
<dt>-p, --port</dt>
<dd>Requerido. O número da porta para o serviço.</dd>
<dt>-w, --weight</dt>
<dd>Requerido. O peso do serviço.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Requerido. O tipo de verificação de funcionamento.</dd>
<dt>-i, --ip-address</dt>
<dd>Requerido. O endereço IP do serviço.</dd>
</dl>

## Ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

Exclui um serviço do balanceador de carga existente.
```
Ibmcloud sl loadbal service-delete SERVICE_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

## Ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

Editar as propriedades de um grupo de serviços.
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--disabled</dt>
<dd>Desativar o serviço.</dd>
<dt>--enabled</dt>
<dd>Ativar o serviço.</dd>
<dt>-p, --port</dt>
<dd>Mudar o número da porta do serviço.</dd>
<dt>-w, --weight</dt>
<dd>Mudar o peso do serviço.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Mudar o tipo de verificação de funcionamento.</dd>
<dt>-i, --ip-address</dt>
<dd>Mudar o endereço IP do serviço.</dd>
</dl>

## Ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

Alternar o status de um serviço do balanceador de carga existente.
```
Ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>
