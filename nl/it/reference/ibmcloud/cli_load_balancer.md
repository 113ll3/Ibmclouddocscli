---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Load Balancer dell'infrastruttura {{site.data.keyword.Bluemix_notm}}

Utilizza i seguenti comandi per gestire un programma di bilanciamento del carico che utilizza il servizio Load Balancer dell'infrastruttura {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Comandi Load Balancer {{site.data.keyword.Bluemix_notm}} riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl loadbal cancel](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_cancel)</td>
 <td>[ibmcloud sl loadbal create](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create)</td>
 <td>[ibmcloud sl loadbal create-options
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create_options)</td>
 <td>[ibmcloud sl loadbal detail](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_detail)</td>
 <td>[ibmcloud sl loadbal group-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_add)</td>
 <td>[ibmcloud sl loadbal group-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal group-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_edit)</td>
 <td>[ibmcloud sl loadbal group-reset](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_reset)</td>
 <td>[ibmcloud sl loadbal health-checks
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_health_checks)</td>
 <td>[ibmcloud sl loadbal list](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_list)</td>
 <td>[ibmcloud sl loadbal routing-methods
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_methods)</td>
 <td>[ibmcloud sl loadbal routing-types
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_types)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal service-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_add)</td>
 <td>[ibmcloud sl loadbal service-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_delete)</td>
 <td>[ibmcloud sl loadbal service-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_edit)</td>
 <td>[ibmcloud sl loadbal service-toggle](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_toggle)</td>
 </tr>
</tbody>
 </table>

 ## ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

Annulla un programma di bilanciamento del carico esistente.
```
ibmcloud sl loadbal cancel ID_PROGRAMMA_DI_BILANCIAMENTO_DEL_CARICO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl loadbal create
{: #sl_loadbal_create}

Aggiunge un programma di bilanciamento del carico fornendo l'id restituito dalle opzioni di creazione.
```
ibmcloud sl loadbal create ID_PREZZO UBICAZIONE [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

Ottieni le opzioni dei prezzi con cui creare un programma di bilanciamento del carico.
```
ibmcloud sl loadbal create-options
```

## ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

Ottieni i dettagli del programma di bilanciamento del carico.
```
ibmcloud sl loadbal detail ID_PROGRAMMA_DI_BILANCIAMENTO_DEL_CARICO
```

## ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

Aggiunge un nuovo servizio del programma di bilanciamento del carico.
```
ibmcloud sl loadbal group-add ID_PROGRAMMA_DI_BILANCIAMENTO_DEL_CARICO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Obbligatorio. La percentuale allocata di connessioni.</dd>
<dt>-p, --port</dt>
<dd>Obbligatorio. Il numero di porta.</dd>
<dt>-t, --routing-type</dt>
<dd>Obbligatorio. L'ID del tipo di instradamento. Esegui 'ibmcloud sl loadbal routing-types' per trovare un ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Obbligatorio. L'ID del metodo di instradamento. Esegui 'ibmcloud sl loadbal routing-methods' per trovare un ID.</dd>
</dl>

## ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

Elimina un gruppo di servizi del programma di bilanciamento del carico esistente.
```
ibmcloud sl loadbal group-delete ID_GRUPPO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

Modifica un gruppo di servizi del programma di bilanciamento del carico esistente.
```
ibmcloud sl loadbal group-edit ID_PROGRAMMA_DI_BILANCIAMENTO_DEL_CARICO ID_GRUPPO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Modifica la percentuale allocata di connessioni.</dd>
<dt>-p, --port</dt>
<dd>Modifica il numero di porta.</dd>
<dt>-t, --routing-type</dt>
<dd>Modifica l'ID del tipo di instradamento. Esegui 'ibmcloud sl loadbal routing-types' per trovare un ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Modifica l'ID del metodo di instradamento. Esegui 'ibmcloud sl loadbal routing-methods' per trovare un ID.</dd>
</dl>

## ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

Reimposta i collegamenti a un determinato gruppo di servizi.
```
ibmcloud sl loadbal group-reset ID_PROGRAMMA_DI_BILANCIAMENTO_DEL_CARICO ID_GRUPPO
```

## ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

Elenca i tipi di controllo di integrità.
```
ibmcloud sl loadbal health-checks
```

## ibmcloud sl loadbal list
{: #sl_loadbal_list}

Elenca i programmi di bilanciamento del carico attivi.
```
ibmcloud sl loadbal list
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtra per nome breve del datacenter.</dd>
<dt>-o, --order</dt>
<dd>Filtra in base all'ID dell'ordine che ha acquistato il programma di bilanciamento del carico.</dd>
<dt>-p, --ip-address</dt>
<dd>Filtra in base all'indirizzo IP.</dd>
</dl>

## ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

Elenca i metodi di instradamento.
```
ibmcloud sl loadbal routing-methods
```

## ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

Elenca i tipi di instradamento.
```
ibmcloud sl loadbal routing-types
```

## ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

Aggiunge un nuovo servizio del programma di bilanciamento del carico.
```
ibmcloud sl loadbal service-add ID_PROGRAMMA_DI_BILANCIAMENTO_DEL_CARICO ID_GRUPPO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--disabled</dt>
<dd>Facoltativo. Crea il servizio come disabilitato; se non viene specificato, il valore predefinito è abilitato.</dd>
<dt>-p, --port</dt>
<dd>Obbligatorio. Il numero di porta per il servizio.</dd>
<dt>-w, --weight</dt>
<dd>Obbligatorio. Il peso del servizio.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Obbligatorio. Il tipo di controllo di integrità.</dd>
<dt>-i, --ip-address</dt>
<dd>Obbligatorio. L'indirizzo IP del servizio.</dd>
</dl>

## ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

Elimina un servizio del programma di bilanciamento del carico esistente.
```
ibmcloud sl loadbal service-delete ID_SERVIZIO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

Modifica le proprietà di un gruppo di servizi.
```
ibmcloud sl loadbal service-edit ID_PROGRAMMA_DI_BILANCIAMENTO_DEL_CARICO ID_SERVIZIO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--disabled</dt>
<dd>Disabilita il servizio.</dd>
<dt>--enabled</dt>
<dd>Abilita il servizio.</dd>
<dt>-p, --port</dt>
<dd>Modifica il numero di porta per il servizio.</dd>
<dt>-w, --weight</dt>
<dd>Modifica il peso del servizio.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Modifica il tipo di controllo di integrità.</dd>
<dt>-i, --ip-address</dt>
<dd>Modifica l'indirizzo IP del servizio.</dd>
</dl>

## ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

Attiva lo stato di un servizio del programma di bilanciamento del carico esistente.
```
ibmcloud sl loadbal service-toggle ID_SERVIZIO
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>
