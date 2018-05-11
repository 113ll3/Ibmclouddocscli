---



copyright:

  years: 2017, 2018

lastupdated: "2018-04-17"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:new_window: target="_blank"}

# Interface de ligne de commande d'{{site.data.keyword.registrylong_notm}}
{: #containerregcli}

L'interface de ligne de commande {{site.data.keyword.registrylong}} est un plug-in qui vous permet de gérer votre registre et ses ressources pour votre compte {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

**Prérequis**
* Avant d'exécuter des commandes de registre, connectez-vous à {{site.data.keyword.Bluemix_notm}} à l'aide de la commande `bx login` pour générer un jeton d'accès et authentifier votre session.

Pour vous familiariser avec l'utilisation de l'interface de ligne de commande {{site.data.keyword.registrylong_notm}}, voir [Initiation à {{site.data.keyword.registrylong_notm}}](../../../services/Registry/index.html).

<table summary="Gérer {{site.data.keyword.registrylong_notm}}">
<caption>Tableau 1. Commandes de gestion de {{site.data.keyword.registrylong_notm}}
</caption>
 <thead>
 <th colspan="5">Commandes de gestion du registre</th>
 </thead>
 <tbody>
 <tr>
 <td>[bx cr api](#bx_cr_api)</td>
 <td>[bx cr build](#bx_cr_build)</td>
 <td>[bx cr info](#bx_cr_info)</td>
 <td>[bx cr image-inspect](#bx_cr_image_inspect)</td>
 <td>[bx cr image-list (bx cr images)](#bx_cr_image_list)</td>
 </tr>
 <tr>
 <td>[bx cr image-rm](#bx_cr_image_rm)</td>
 <td>[bx cr login](#bx_cr_login)</td>
 <td>[bx cr namespace-add](#bx_cr_namespace_add)</td>
 <td>[bx cr namespace-list (bx cr namespaces)](#bx_cr_namespace_list)</td>
 <td>[bx cr namespace-rm](#bx_cr_namespace_rm)</td>
 </tr>
 <tr>
 <td>[bx cr plan](#bx_cr_plan)</td>
 <td>[bx cr plan-upgrade](#bx_cr_plan_upgrade)</td>
 <td>[bx cr quota](#bx_cr_quota)</td>
 <td>[bx cr quota-set](#bx_cr_quota_set)</td>
 <td>[bx cr region](#bx_cr_region)</td>
 </tr>
 <tr>
 <td>[bx cr region-set](#bx_cr_region_set)</td>
 <td>[bx cr token-add](#bx_cr_token_add)</td>
 <td>[bx cr token-get](#bx_cr_token_get)</td>
 <td>[bx cr token-list (bx cr tokens)](#bx_cr_token_list)</td>
 <td>[bx cr token-rm](#bx_cr_token_rm)</td>
 </tr><tr>
 <td>[bx cr vulnerability-assessment (bx cr va)](#bx_cr_va)</td>
 </tr>
 </tbody></table>



## bx cr api
{: #bx_cr_api}

Renvoie les informations sur le noeud final de l'API de registre face auquel les commandes sont exécutées.

```
bx cr api
```
{: codeblock}


## bx cr build
{: #bx_cr_build}

Génère une image Docker dans {{site.data.keyword.registrylong_notm}}.

```
bx cr build [--no-cache] [--pull] [--quiet | -q] [--build-arg KEY=VALUE ...] [--file FILE | -f FILE] --tag TAG DIRECTORY
```
{: codeblock}

**Paramètres**
<dl>
<dt>DIRECTORY</dt>
<dd>Emplacement de votre contexte de génération, qui contient votre fichier Dockerfile et les fichiers prérequis.</dd>
<dt>--no-cache</dt>
<dd>(Facultatif) Lorsque ce paramètre est spécifié, les couches d'image mises en cache à partir de générations précédentes ne sont pas utilisées dans cette génération.</dd>
<dt>--pull</dt>
<dd>(Facultatif) Si ce paramètre est spécifié, les images de base sont extraites même si une image dotée d'une étiquette correspondante existe déjà sur l'hôte de génération.</dd>
<dt>--quiet, -q</dt>
<dd>(Facultatif) Si ce paramètre est spécifié, la sortie de génération est supprimée sauf en cas d'erreur.</dd>
<dt> --build-arg KEY=VALUE</dt>
<dd>(Facultatif) Spécifiez un argument de génération supplémentaire au format 'KEY=VALUE'. Vous avez la possibilité d'indiquer plusieurs arguments de génération en ajoutant ce paramètre plusieurs fois. La valeur de chaque argument de génération est disponible en tant que variable d'environnement quand vous spécifiez une ligne ARG qui correspond à la clé dans votre Dockerfile.</dd>
<dt>--file FILE, -f FILE</dt>
<dd>(Facultatif) Si vous utilisez les mêmes fichiers pour plusieurs générations, vous pouvez sélectionner un chemin vers un fichier Dockerfile différent. Indiquez l'emplacement du fichier Dockerfile par rapport au contexte de génération. Si vous ne l'indiquez pas, la valeur par défaut est `PATH/Dockerfile`, où PATH correspond à la racine du contexte de génération.</dd>
<dt>--tag TAG, -t TAG</dt>
<dd>Nom complet de l'image à générer, qui inclut l'URL et l'espace de nom de registre.</dd>
</dl>


## bx cr info
{: #bx_cr_info}

Affiche le nom et le compte du registre auquel vous êtes connecté.

```
bx cr info
```
{: codeblock}


## bx cr image-inspect
{: #bx_cr_image_inspect}

Affiche les détails d'une image spécifique.

```
bx cr image-inspect [--format FORMAT] IMAGE [IMAGE...]
```
{: codeblock}

**Paramètres**
<dl>
<dt>--format FORMAT</dt>
<dd>(Facultatif) Formate la sortie en utilisant un modèle Go. 

Pour plus d'informations, voir [Formatage et filtrage de la sortie de l'interface de ligne de commande pour les commandes {{site.data.keyword.registrylong_notm}}](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
<dt>IMAGE</dt>
<dd>Nom de l'image pour laquelle vous voulez obtenir un rapport. Vous pouvez inspecter plusieurs images en les répertoriant dans la commande, séparées les unes des autres par un espace.

<p>Pour trouver les noms de vos images, exécutez `bx cr image-list`. Associez le contenu des colonnes Repository et Tag pour créer le nom de l'image au format `repository:tag`. Si aucune étiquette n'est spécifiée dans le nom de l'image, l'image associée à l'étiquette `latest` est inspectée. </p> 

</dd>
</dl>


## bx cr image-list (bx cr images)
{: #bx_cr_image_list}

Affiche toutes les images de votre compte {{site.data.keyword.Bluemix_notm}}.

<p>**Remarque :** le nom de l'image est la combinaison du contenu des colonnes Repository et Tag au format `repository:tag`. </p> 

```
 bx cr image-list [--no-trunc] [--format FORMAT] [-q, --quiet] [--restrict RESTRICTION] [--include-ibm] 
```
{: codeblock}

**Paramètres**
<dl>
<dt>--no-trunc</dt>
<dd>(Facultatif) Permet de ne pas tronquer l'historique des images.</dd>
<dt>--format FORMAT</dt>
<dd>(Facultatif) Formate la sortie en utilisant un modèle Go. 

Pour plus d'informations, voir [Formatage et filtrage de la sortie de l'interface de ligne de commande pour les commandes {{site.data.keyword.registrylong_notm}}](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
<dt>-q, --quiet</dt>
<dd>(Facultatif) Chaque image est répertoriée au format `repository:tag`</dd>
<dt>--restrict RESTRICTION</dt>
<dd>(Facultatif) Limite la sortie pour n'afficher que les images dans l'espace de nom spécifié ou dans l'espace de nom et le référentiel. </dd>
<dt>--include-ibm</dt>
<dd>(Facultatif) Inclut dans la sortie les images publiques fournies par {{site.data.keyword.IBM_notm}}. Sans cette option, seules les images privées sont répertoriées par défaut.</dd>
</dl>



## bx cr image-rm
{: #bx_cr_image_rm}

Supprime une ou plusieurs images spécifiées de votre registre.

```
bx cr image-rm IMAGE [IMAGE...]
```
{: codeblock}

**Paramètres**
<dl>
<dt>IMAGE</dt>
<dd>Nom de l'image pour laquelle vous voulez obtenir un rapport. Vous pouvez supprimer plusieurs images en même temps en les répertoriant dans la commande, séparées les unes des autres par un espace.

<p>Pour trouver les noms de vos images, exécutez `bx cr image-list`. Associez le contenu des colonnes Repository et Tag pour créer le nom de l'image au format `repository:tag`. Si aucune étiquette n'est spécifiée dans le nom de l'image, l'image associée à l'étiquette `latest` est supprimée par défaut.</p> 

</dd>
</dl>


## bx cr login
{: #bx_cr_login}

Cette commande exécute la commande `docker login` sur le registre. La commande `docker login` est requise pour pouvoir exécuter les commandes `docker push` ou `docker pull` pour le registre. Cette commande n'est pas requise pour exécuter d'autres commandes `bx cr`. Si Docker n'est pas installé, cette commande renvoie un message d'erreur.

```
bx cr login
```
{: codeblock}


## bx cr namespace-add
{: #bx_cr_namespace_add}

Ajoute un espace de nom à votre compte {{site.data.keyword.Bluemix_notm}}.

```
bx cr namespace-add ESPACE DE NOM
```
{: codeblock}

**Paramètres**
<dl>
<dt>ESPACE DE NOM</dt>
<dd>Espace de nom à ajouter. Il doit être unique sur tous les comptes {{site.data.keyword.Bluemix_notm}} d'une même région.</dd>
</dl>


## bx cr namespace-list (bx cr namespaces)
{: #bx_cr_namespace_list}

Affiche tous les espaces de nom détenus par votre compte {{site.data.keyword.Bluemix_notm}}.

```
bx cr namespace-list
```
{: codeblock}


## bx cr namespace-rm
{: #bx_cr_namespace_rm}

Retire un espace de nom de votre compte {{site.data.keyword.Bluemix_notm}}. Les images dans cet espace de nom sont supprimées lorsque l'espace de nom est retiré.

```
bx cr namespace-rm ESPACE DE NOM
```
{: codeblock}

**Paramètres**
<dl>
<dt>ESPACE DE NOM</dt>
<dd>Espace de nom que vous désirez supprimer.</dd>
</dl>


## bx cr plan
{: #bx_cr_plan}

Affiche votre plan de tarification.

```
bx cr plan
```
{: codeblock}


## bx cr plan-upgrade
{: #bx_cr_plan_upgrade}

Effectue une mise à niveau vers le plan standard.

Pour plus d'information sur les plans, voir [Plans de registre](../../../services/Registry/registry_overview.html#registry_plans).

```
bx cr plan-upgrade [PLAN]
```
{: codeblock}

**Paramètres**
<dl>
<dt>PLAN</dt>
<dd>Nom du plan de tarification vers lequel que vous voulez effectuer une mise à niveau. Si PLAN n'est pas spécifié, la valeur par défaut est `standard`.</dd>
</dl>


## bx cr quota
{: #bx_cr_quota}

Affiche vos quotas actuels de trafic et de stockage, ainsi que les informations d'utilisation de ces quotas.

```
bx cr quota
```
{: codeblock}


## bx cr quota-set
{: #bx_cr_quota_set}

Modifie le quota spécifié.

```
bx cr quota-set [--traffic TRAFFIC] [--storage STORAGE]
```
{: codeblock}

**Paramètres**
<dl>
<dt>--traffic TRAFFIC</dt>
<dd>(Facultatif) Remplace votre quota de trafic par la valeur spécifiée en mégaoctets. L'opération échoue si vous n'êtes pas habilité à définir le trafic ou si vous définissez une valeur au-delà de votre plan de tarification.</dd>
<dt>--storage STORAGE</dt>
<dd>(Facultatif) Remplace votre quota de stockage par la valeur spécifiée en mégaoctets. L'opération échoue si vous n'êtes pas habilité à définir les quotas de stockage ou si vous définissez une valeur au-delà de votre plan de tarification.</dd>
</dl>


## bx cr region
{: #bx_cr_region}

Affiche les régions cible et le registre.

```
bx cr region
```
{: codeblock}

Pour plus d'informations, voir [Régions](../../../services/Registry/registry_overview.html#registry_regions).


## bx cr region-set
{: #bx_cr_region_set}

Définit une région cible pour les commandes {{site.data.keyword.registrylong_notm}}. Pour répertorier les régions disponibles, exécutez la commande sans paramètres.

```
bx cr region-set [REGION]
```
{: codeblock}

**Paramètres**
<dl>
<dt>REGION</dt>
<dd>(Facultatif) Le nom de votre région cible, par exemple, `us-south`. 

Pour plus d'informations, voir [Régions](../../../services/Registry/registry_overview.html#registry_regions).

</dd>
</dl>


## bx cr token-add
{: #bx_cr_token_add}

Ajoute un jeton que vous pouvez utiliser pour contrôler l'accès à un registre.

```
bx cr token-add [--description DESCRIPTION] [-q, --quiet] [--non-expiring] [--readwrite]
```

{: codeblock}


**Paramètres**
<dl>
<dt>--description DESCRIPTION</dt>
<dd>(Facultatif) Permet de spécifier la description du jeton qui s'affiche lorsque vous exécutez `bx cr token-list`. Si votre jeton est créé automatiquement par {{site.data.keyword.containerlong_notm}}, la description est le nom de votre cluster Kubernetes. Dans ce cas, le jeton est retiré automatiquement lorsque votre cluster est retiré.</dd>
<dt>-q, --quiet</dt>
<dd>(Facultatif) Affiche le jeton uniquement, sans aucun autre texte.</dd>
<dt>--non-expiring</dt>
<dd>(Facultatif) Crée un jeton dont l'accès n'expire jamais. Si ce paramètre n'est pas défini, l'accès à l'aide d'un jeton expire au bout de 24 heures par défaut.</dd>
<dt>--readwrite</dt>
<dd>(Facultatif) Crée un jeton qui accorde l'accès en lecture et en écriture. Sans cette option, l'accès est en lecture seule par défaut.</dd>
</dl>


## bx cr token-get
{: #bx_cr_token_get}

Extrait le jeton spécifié du registre.

```
bx cr token-get JETON
```

{: codeblock}

**Paramètres**
<dl>
<dt>JETON</dt>
<dd>(Facultatif) Identificateur unique du jeton à extraire.</dd>
</dl>


## bx cr token-list (bx cr tokens)
{: #bx_cr_token_list}

Affiche tous les jetons qui existent pour votre compte {{site.data.keyword.Bluemix_notm}}.

```
bx cr token-list --format FORMAT
```
{: codeblock}

**Paramètres**
<dl>
<dt>--format FORMAT</dt>
<dd>(Facultatif) Formate la sortie en utilisant un modèle Go. 

Pour plus d'informations, voir [Formatage et filtrage de la sortie de l'interface de ligne de commande pour les commandes {{site.data.keyword.registrylong_notm}}](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
</dl>


## bx cr token-rm
{: #bx_cr_token_rm}

Retire un ou plusieurs jetons spécifiés.

```
bx cr token-rm TOKEN [TOKEN...]
```
{: codeblock}

**Paramètres**
<dl>
<dt>JETON</dt>
<dd>(Facultatif) JETON peut correspondre au jeton lui-même ou à l'identificateur unique du jeton, comme indiqué dans `bx cr token-list`. Vous pouvez spécifier plusieurs jetons en les séparant par un espace.</dd>
</dl>


## bx cr vulnerability-assessment (bx cr va)
{: #bx_cr_va}

Affiche un rapport d'évaluation des vulnérabilités pour vos images.

```
bx cr vulnerability-assessment [--extended | -e] [--vulnerabilities | -v] [--configuration-issues | -c] [--output FORMAT | -o FORMAT] IMAGE [IMAGE...] 
```
{: codeblock}

**Paramètres**
<dl>
<dt>IMAGE</dt>
<dd>Nom de l'image pour laquelle vous voulez obtenir un rapport. Le rapport vous signale si l'image comporte des vulnérabilités de package connues. Vous pouvez demander des rapports pour plusieurs images en même temps en les répertoriant dans la commande, séparées les unes des autres par un espace.

<p>Pour trouver les noms de vos images, exécutez `bx cr image-list`. Associez le contenu des colonnes Repository et Tag pour créer le nom de l'image au format `repository:tag`. Si aucune étiquette n'est spécifiée dans le nom de l'image, le rapport évalue l'image associée à l'étiquette `latest`. </p> 

<p>Les systèmes d'exploitation suivants sont pris en charge :

<ul>

<li>Alpine</li>
<li>CentOS</li>
<li>Debian</li>
<li>Red Hat Enterprise Linux (RHEL)</li>
<li>Ubuntu</li>
</ul>

</p>

Pour plus d'informations, voir la rubrique relative à la [gestion de la sécurité des images avec l'assistant de détection des vulnérabilités](../../../services/va/va_index.html).

</dd>
<dt>--output FORMAT, -o FORMAT</dt>
<dd>(Facultatif) La sortie de la commande est retournée dans le format choisi. Le format par défaut est `text`. Les formats suivants sont pris en charge :

<ul>

<li>`text`</li>
<li>`json

`</li>
</ul>

</dd>
<dt>--vulnerabilities, -v</dt>
<dd>(Facultatif) La sortie de la commande est restreinte pour n'afficher que les vulnérabilités.</dd>
<dt>--configuration-issues, -c</dt>
<dd>(Facultatif) La sortie de la commande est restreinte pour n'afficher que les problèmes de configuration.</dd>
<dt>--extended, -e </dt>
<dd>(Facultatif) La sortie de la commande affiche des informations supplémentaires sur les correctifs pour les packages vulnérables.</dd>

</dl>

