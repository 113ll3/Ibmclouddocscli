---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commandes générales de l'interface CLI (ibmcloud sl)
{: #softlayer_cli}

Le plug-in {{site.data.keyword.BluSoftlayer}} a été fusionné dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. Vous n'avez plus besoin d'installer le plug-in.
{: tip}

Utilisez les commandes de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}} dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} pour configurer et gérer des services SoftLayer.

A compter de mai 2018, les commandes de l'interface CLI d'{{site.data.keyword.Bluemix_notm}} ont été changées de `bluemix` et `bx` en `ibmcloud`. Vous pouvez toutefois continuer à utiliser les commandes de l'interface CLI `bluemix` et `bx` jusqu'à ce qu'elles soient retirées.
{: tip}

Pour commencer, installez l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. Voir
[Interface de ligne de commande IBM Cloud![Icône de lien externe](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window} pour plus d'informations.

Pour la liste complète des commandes de l'interface CLI {{site.data.keyword.Bluemix_notm}}, voir [Commandes {{site.data.keyword.Bluemix_notm}} (ibmcloud)](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli).

Les commandes ci-après sont prises en charge. Utilisez la commande `ibmcloud sl` pour consulter la liste des commandes disponibles :

<table summary="Commandes générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 1. Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_help)</td>
   </tbody>
 </table>
 
 Pour afficher les informations d'aide sur les commandes, exécutez `ibmcloud sl [commande] -h`
 
 ## ibmcloud sl init
{: #sl_init}

Permet d'initialiser les paramètres de configuration qui sont utilisés pour établir une connexion à l'environnement de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}. La configuration inclut un nom d'utilisateur, une clé d'API ou un mot de passe, un compte et un noeud final.
```
ibmcloud sl init [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-a, --api-endpoint</dt>
<dd>URL de noeud final d'API {{site.data.keyword.BluSoftlayer_notm}}, par défaut : https://api.softlayer.com/rest/v3.1 pour l'authentification par clé d'API, https://api.softlayer.com/mobile/v3.1 pour l'authentification par IBMid.</dd>
<dt>-u, --sl-user</dt>
<dd>Nom d'utilisateur de l'infrastructure Gen1.</dd>
<dt>-p, --sl-password</dt>
<dd>Mot de passe ou clé d'API.</dd>
<dt>-c, --account-id</dt>
<dd>ID de compte.</dd>
<dt>-q, --security-question-id</dt>
<dd>ID de question de sécurité utilisé pour l'authentification. Adressez-vous à votre propriétaire de compte si vous ne connaissez pas cet ID.</dd>
<dt>-w, --security-question-answer</dt>
<dd>Réponse à la question de sécurité utilisée pour l'authentification. Adressez-vous à votre propriétaire de compte si vous connaissez pas cette réponse.</dd>
<dt>-s, --security-code</dt>
<dd>Code de sécurité généré par le fournisseur de sécurité lorsque l'authentification à deux facteurs est activée.</dd>
<dt>-v, --security-vendor</dt>
<dd>Fournisseur de sécurité qu fournit le code de sécurité pour l'authentification. Les options possibles sont : VERISIGN,TOTP,PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>Jeton d'authentification lorsque l'authentification par téléphone est activée.</dd>
</dl>

Par exemple, connectez-vous à l'aide du nom d'utilisateur et du mot de passe ou de la clé d'API de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}.
```
$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:
1. Login with {{site.data.keyword.BluSoftlayer_notm}} infrastructure user name and password/API key
2. Use {{site.data.keyword.Bluemix_notm}} Single-Sign-On
Enter a number>1
Softlayer API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Username: []> user@example.com
API key or password: []> abcd

API endpoint:    https://api.softlayer.com/rest/v3.1   
User name:       user@example.com   
API Key:         xxxxxxxxxx
```
Par exemple, utilisez {{site.data.keyword.Bluemix_notm}} Single-Sign-On pour vous connecter à Softlayer
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account example user's Account (65ce8074c6c62b5)

API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south   
User:           user@example.com   
Account:        example user's Account (65ce8074c6c62b5)   
No org or space targeted, use 'ibmcloud target --cf or ibmcloud target -o ORG -s SPACE'


$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:

1. Login with Softlayer user name and password/API key
2. Use IBM Cloud Single-Sign-On
Enter a number> 2
{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint URL: [https://api.softlayer.com/mobile/v3.1]>
Setting account to: 123456
OK

{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint:    https://api.softlayer.com/mobile/v3.1   

Account ID:                123456   
User ID:                   user@example.com  
IMS token:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

Permet d'afficher des informations d'aide pour toutes les commandes exécutées dans un environnement d'infrastructure {{site.data.keyword.BluSoftlayer_notm}}.
```
ibmcloud sl help
```
