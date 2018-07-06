---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CLI-Befehle für Load Balancer (Lastausgleichsfunktion)

<table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 1. Load Balancer-Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Befehle von Load Balancer (loadbal)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl loadbal cancel](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_cancel)</td>
 <td>[ibmcloud sl loadbal create](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_create)</td>
 <td>[ibmcloud sl loadbal create-options](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_create_options)</td>
 <td>[ibmcloud sl loadbal detail](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_detail)</td>
 <td>[ibmcloud sl loadbal group-add](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_group_add)</td>
 <td>[ibmcloud sl loadbal group-delete](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_group_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal group-edit](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_group_edit)</td>
 <td>[ibmcloud sl loadbal group-reset](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_group_reset)</td>
 <td>[ibmcloud sl loadbal health-checks](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_health_checks)</td>
 <td>[ibmcloud sl loadbal list](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_list)</td>
 <td>[ibmcloud sl loadbal routing-methods](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_routing_methods)</td>
 <td>[ibmcloud sl loadbal routing-types](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_routing_types)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal service-add](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_service_add)</td>
 <td>[ibmcloud sl loadbal service-delete](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_service_delete)</td>
 <td>[ibmcloud sl loadbal service-edit](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_service_edit)</td>
 <td>[ibmcloud sl loadbal service-toggle](/docs/cli/reference/softlayer/sl_cli_load_balancer.html#sl_loadbal_service_toggle)</td>
 </tr>
</tbody>
 </table>
 
 ### ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

Abbruch für vorhandene Lastausgleichsfunktion.
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl loadbal create
{: #sl_loadbal_create}

Fügt eine Lastausgleichsfunktion hinzu, der die ID zugewiesen wird, die von 'create-options' zurückgegeben wurde.
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

Preisoptionen zum Erstellen einer Lastausgleichsfunktion abrufen.
```
ibmcloud sl loadbal create-options
```

### ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

Details zu Lastausgleichsfunktion abrufen.
```
ibmcloud sl loadbal detail LOADBAL_ID
```

### ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

Fügt einen neuen 'load_balancer'-Service hinzu.
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-a, --allocation</dt>
<dd>Erforderlich. Der zugeordnete Prozentsatz an Verbindungen.</dd>
<dt>-p, --port</dt>
<dd>Erforderlich. Die Portnummer.</dd>
<dt>-t, --routing-type</dt>
<dd>Erforderlich. Die ID des Routing-Typs. Führen Sie 'ibmcloud sl loadbal routing-types' aus, um eine ID zu suchen.</dd>
<dt>-m, --routing-method</dt>
<dd>Erforderlich. Die ID der Routing-Methode. Führen Sie 'ibmcloud sl loadbal routing-methods' aus, um eine ID zu suchen.</dd>
</dl>

### ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

Löscht eine vorhandene Gruppe von Services für die Lastausgleichsfunktion.
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

Bearbeitet eine vorhandene Gruppe von Services für die Lastausgleichsfunktion.
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-a, --allocation</dt>
<dd>Ändert den zugeordneten Prozentsatz an Verbindungen.</dd>
<dt>-p, --port</dt>
<dd>Ändert die Portnummer.</dd>
<dt>-t, --routing-type</dt>
<dd>Ändert die ID des Routing-Typs. Führen Sie 'ibmcloud sl loadbal routing-types' aus, um eine ID zu suchen.</dd>
<dt>-m, --routing-method</dt>
<dd>Ändert die ID der Routing-Methode. Führen Sie 'ibmcloud sl loadbal routing-methods' aus, um eine ID zu suchen.</dd>
</dl>

### ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

Verbindungen für bestimmte Servicegruppe zurücksetzen.
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

### ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

Statusprüfungstypen auflisten.
```
ibmcloud sl loadbal health-checks
```

### ibmcloud sl loadbal list
{: #sl_loadbal_list}

Aktive Lastausgleichsfunktionen auflisten.
```
ibmcloud sl loadbal list
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
<dt>-o, --order</dt>
<dd>Nach ID der Bestellung filtern, mit der die Lastausgleichsfunktion gekauft wurde.</dd>
<dt>-p, --ip-address</dt>
<dd>Nach IP-Adresse filtern.</dd>
</dl>

### ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

Routing-Methoden auflisten.
```
ibmcloud sl loadbal routing-methods
```

### ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

Routing-Typen auflisten.
```
ibmcloud sl loadbal routing-types
```

### ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

Fügt einen neuen Service für die Lastausgleichsfunktion hinzu.
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>--disabled</dt>
<dd>Optional. Erstellt den Service als 'inaktiviert'; Standardwert ist 'aktiviert', wenn nicht angegeben.</dd>
<dt>-p, --port</dt>
<dd>Erforderlich. Die Portnummer für den Service.</dd>
<dt>-w, --weight</dt>
<dd>Erforderlich. Die Gewichtung des Service.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Erforderlich. Der Statusprüfungstyp.</dd>
<dt>-i, --ip-address</dt>
<dd>Erforderlich. Die IP-Adresse des Service.</dd>
</dl>

### ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

Löscht einen vorhandenen Service für die Lastausgleichsfunktion.
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

Bearbeitet die Eigenschaften einer Servicegruppe.
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>--disabled</dt>
<dd>Inaktiviert den Service.</dd>
<dt>--enabled</dt>
<dd>Aktiviert den Service.</dd>
<dt>-p, --port</dt>
<dd>Ändert die Portnummer für den Service.</dd>
<dt>-w, --weight</dt>
<dd>Ändert die Gewichtung des Service.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Ändert den Typ der Statusprüfung.</dd>
<dt>-i, --ip-address</dt>
<dd>Ändert die IP-Adresse des Service.</dd>
</dl>

### ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

Wechselt den Status eines vorhandenen Service für die Lastausgleichsfunktion.
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>
