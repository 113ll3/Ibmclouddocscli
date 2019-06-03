---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, classic infrastructure, load balancer service, ibmcloud sl loadbal, sl loadbal, load balancer cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Utilisation du service d'équilibrage de charge
{: #sl-load-balancer-service}

Le service d'équilibrage de charge {{site.data.keyword.cloud}} vous permet d'améliorer la disponibilité de vos applications stratégiques en distribuant le trafic entre plusieurs instances de serveur d'application et en acheminant le trafic uniquement vers des instances saines.

Utilisez les commandes suivantes pour gérer les équilibreurs de charge dans le service Load Balancer de l'infrastructure classique {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

Permet d'annuler un équilibreur de charge existant.
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl loadbal create
{: #sl_loadbal_create}

Permet d'ajouter un équilibreur de charge en fonction de l'id renvoyé par create-options.
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

Permet d'obtenir les options tarifaires afin de créer un équilibreur de charge.
```
ibmcloud sl loadbal create-options
```

## ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

Permet d'obtenir les détails relatifs à un équilibreur de charge.
```
ibmcloud sl loadbal detail LOADBAL_ID
```

## ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

Permet d'ajouter un nouveau service load_balancer.
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-a, --allocation</dt>
<dd>Obligatoire. Pourcentage de connexions alloué.</dd>
<dt>-p, --port</dt>
<dd>Obligatoire. Numéro de port.</dd>
<dt>-t, --routing-type</dt>
<dd>Obligatoire. ID du type de routage. Exécutez 'ibmcloud sl loadbal routing-types' pour rechercher un ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Obligatoire. ID de la méthode de routage. Exécutez 'ibmcloud sl loadbal routing-methods' pour rechercher un ID.</dd>
</dl>

## ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

Permet de supprimer un groupe de services d'équilibreur de charge existant.
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

Permet d'éditer un groupe de services d'équilibreur de charge existant.
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-a, --allocation</dt>
<dd>Modifiez le pourcentage de connexions alloué.</dd>
<dt>-p, --port</dt>
<dd>Modifiez le numéro de port.</dd>
<dt>-t, --routing-type</dt>
<dd>Modifiez l'ID du type de routage. Exécutez 'ibmcloud sl loadbal routing-types' pour rechercher un ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Modifiez l'ID de la méthode de routage. Exécutez 'ibmcloud sl loadbal routing-methods' pour rechercher un ID.</dd>
</dl>

## ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

Permet de réinitialiser des connexions sur un groupe de services donné.
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

## ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

Permet de répertorier les types de diagnostic d'intégrité.
```
ibmcloud sl loadbal health-checks
```

## ibmcloud sl loadbal list
{: #sl_loadbal_list}

Permet de répertorier les équilibreurs de charge actifs.
```
ibmcloud sl loadbal list
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtrer par nom abrégé de centre de données.</dd>
<dt>-o, --order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter l'équilibreur de charge.</dd>
<dt>-p, --ip-address</dt>
<dd>Filtrer par adresse IP.</dd>
</dl>

## ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

Permet de répertorier les méthodes de routage.
```
ibmcloud sl loadbal routing-methods
```

## ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

Permet de répertorier les types de routage.
```
ibmcloud sl loadbal routing-types
```

## ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

Permet d'ajouter un nouveau service d'équilibreur de charge.
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--disabled</dt>
<dd>Facultatif. Créer le service comme désactivé, il est activé par défaut si cette option n'est pas sélectionnée.</dd>
<dt>-p, --port</dt>
<dd>Obligatoire. Numéro de port du service.</dd>
<dt>-w, --weight</dt>
<dd>Obligatoire. Poids du service.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Obligatoire. Type de diagnostic d'intégrité.</dd>
<dt>-i, --ip-address</dt>
<dd>Obligatoire. Adresse IP du service.</dd>
</dl>

## ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

Permet de supprimer un service d'équilibreur de charge existant.
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

Permet d'éditer les propriétés d'un groupe de services.
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--disabled</dt>
<dd>Désactivez le service.</dd>
<dt>--enabled</dt>
<dd>Activez le service.</dd>
<dt>-p, --port</dt>
<dd>Modifiez le numéro de port du service.</dd>
<dt>-w, --weight</dt>
<dd>Modifiez le poids du service.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Modifiez le type de diagnostic d'intégrité.</dd>
<dt>-i, --ip-address</dt>
<dd>Modifiez l'adresse IP du service.</dd>
</dl>

## ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

Permet de basculer le statut d'un service d'équilibreur de charge existant.
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>
