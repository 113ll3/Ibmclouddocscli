---

copyright:
  years: 2017, 2019
lastupdated: "2019-04-03"

keywords: cli, contribute plug-in, sdk plug-in, cloud foundry cli, go environment, internationalization, ginkgo, govendor

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Contribution au plug-in SDK
{: #contribute}

Suivez les instructions décrites ci-après pour contribuer au plug-in SDK d'interface de ligne de commande {{site.data.keyword.cloud}}.

## Configuration de votre environnement de développement
{: #dev-env}

* [Interface de ligne de commande Cloud Foundry ](https://github.com/cloudfoundry/cli/releases){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe").

   L'interface de ligne de commande Cloud Foundry n'est pas requise, mais elle facilite l'accès à {{site.data.keyword.cloud_notm}} à partir du terminal.

   Pour plus d'informations sur l'interface de ligne de commande Cloud Foundry, voir la [documentation](/docs/cli?topic=cloud-cli-cf#cf).

* [Interface de ligne de commande](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) {{site.data.keyword.cloud_notm}}.

   Ce plug-in s'installe dans l'interface de ligne de commande {{site.data.keyword.cloud_notm}}. L'interface de ligne de commande {{site.data.keyword.cloud_notm}} fournit également des ressources utiles pour accéder à {{site.data.keyword.cloud_notm}} à partir du terminal.

* [Environnement de développement de Go ](https://golang.org/doc/code.html){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

   Go est strict en ce qui concerne les emplacements des packages, par conséquent, votre source doit être définie dans la structure de répertoire `$GOPATH`. Prenez soin de définir vos variables `$GOPATH` et `$GOROOT` et d'inclure `$GOPATH/bin` dans votre variable d'environnement `$PATH` en éditant votre fichier de configuration `~/.bash_profile` (sur Mac OS).

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Gestionnaire de dépendances : [govendor ](https://github.com/kardianos/govendor){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

   L'outil `govendor` crée et gère les dépendances Go. Vous n'en avez pas besoin sauf si vous prévoyez de mettre à jour le répertoire vendor.

   * Installez-le à l'aide de la commande suivante :

      ```
      go get -u github.com/kardianos/govendor
      ```
      {: codeblock}

   * Initialisez `govendor` sur votre répertoire de projet à l'aide de la commande suivante :

      ```
      govendor init
      ```
      {: codeblock}

   * Ajoutez des dépendances au répertoire vendor à partir de `$GOPATH` en exécutant la commande suivante :

      ```
      govendor add +local
      ```
      {: codeblock}

* Structure de test de BDD : [Ginkgo ](http://onsi.github.io/ginkgo/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

La structure de test repose sur Ginkgo, une structure de test BDD pour Go. Elle est utilisée avec [Gomega](http://onsi.github.io/gomega/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe"), qui est une bibliothèque d'assertion et de comparateur pour Ginkgo.

   * Installez `ginkgo` à l'aide de la commande suivante :

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * Installez `gomega` à l'aide de la commande suivante :

      ```
      go get -u github.com/onsi/gomega
      ```
      {: codeblock}

   * Exécutez des tests d'unité à l'aide de la commande suivante :

      ```
      ginkgo -r
      ```
      {: codeblock}

      * Pour ajouter une couverture de code, ajoutez `-cover` à la commande.

   * Procurez-vous une forme HTML conviviale de la couverture de code ; pour cela, exécutez la commande suivante :

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * Vous accédez au répertoire dans lequel se trouve le fichier `.coverprofile`.

* Internationalisation : [go-i18n ](https://github.com/nicksnyder/go-i18n){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") et [go-bindata ](https://github.com/jteeuwen/go-bindata){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

L'internationalisation est basée sur `go-i18n`. Il s'agit d'un outil de ligne de commande et de package qui fournit le support nécessaire pour traduire une application Go en plusieurs langues. Les groupements de traduction sont prétraités par `go-bindata`. Il s'agit d'une commande qui convertit un fichier d'entrée en code source Go gérable.

   * Installez `go-i18n` à l'aide de la commande suivante :

      ```
      go get -u github.com/nicksnyder/go-i18n/goi18n
      ```
      {: codeblock}

   * Installez `go-bindata` à l'aide de la commande suivante :

      ```
      go get -u github/com/jteeuwen/go-bindata/go-bindata
      ```
      {: codeblock}

* Débogage : [delve ](https://github.com/go-delve/delve){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

Delve est un débogueur pour le langage de programmation Go et il est utilisé par [Visual Studio Code ](https://code.visualstudio.com/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe").

   * Installez `delve` à l'aide de la commande suivante :

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Pour Mac OS, suivez les [instructions ](http://blog.ralch.com/tutorial/golang-debug-with-delve/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") pour créer le certificat autosigné requis.


## Bibliothèques d'exécution requises
{: #runtime-libs}

Les bibliothèques d'exécution requises sont gérées sous le répertoire `vendor` et sont validées dans le référentiel Git pour garantir la stabilité, dans la mesure où  Go ne fournit pas un gestionnaire de dépendances robuste.

### Dépendances d'exécution
{: #runtime-dependencies}

Les dépendances imbriquées ne sont pas répertoriées.

* [github.ibm.com/Bluemix/bluemix-cli-sdk ](https://github.ibm.com/Bluemix/bluemix-cli-sdk){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

   SDK de plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}} qui fournit l'infrastructure pour développer les plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}}.

* [github.com/urfave/cli ](https://github.com/urfave/cli){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

   Ce package fournit l'infrastructure permettant de générer des applications de ligne de commande dans Go. Le plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}} repose sur une ancienne version de cette bibliothèque (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ](https://github.com/asaskevich/govalidator){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

   Ce package fournit un certain nombre de valideurs et de nettoyeurs pour des chaînes, des structs et des collections. Utilisez ce package au lieu d'implémenter vos propres valideurs.

* [github.com/parnurzeal/gorequest ](https://github.com/parnurzeal/gorequest){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

   Ce package implémente un client HTTP simplifié pour vous aider à gérer les demandes et les réponses HTTP.

* [github.com/briandowns/spinner ](https://github.com/briandowns/spinner){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

   Ce package implémente une bouton fléché d'interface de ligne de commande permettant de fournir des commentaires en retour d'utilisateur durant le traitement d'opérations de longue durée, par exemple, une génération de SDK.

* [github.com/cloudfoundry-attic/jibber_jabber ](https://github.com/cloudfoundry-attic/jibber_jabber){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

   Ce package est utilisé pour détecter la langue en cours du système d'exploitation.

## Clonage du référentiel
{: #clone-repo}

Le référentiel doit être cloné dans la [structure de répertoire ](https://golang.org/doc/code.html){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") de Go en raison de la façon dont `govendor` fonctionne (application des meilleures pratiques de Go).

* Importez les dépendances internes via un nom de package qualifié complet.

   ```
   import (
      ...
      "github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/plugin"
   )
   ```
   {: codeblock}

* Clonez le référentiel.

   ```
   mkdir -p $GOPATH/src/github.ibm.com/bluemix-mobile-services
   cd $GOPATH/src/github.ibm.com/bluemix-mobile-services
   git clone https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## Génération, test et installation du plug-in
{: #build-plug-in}

Générez le plug-in en choisissant l'une des commandes suivantes :
```
cd $GOPATH/src/github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin
go build main.go
```
{: codeblock}

```
cd $GOPATH/src/github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin
sh bin/build.sh
```
{: codeblock}

Le script de génération installe également le plug-in dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.
{: note}

Testez le plug-in en choisissant l'une des commandes suivantes :
```
ginkgo -r
```
{: codeblock}

```
go test ./plugin/...
```
{: codeblock}

Exécutez des tests d'intégration avec des unités de test et une couverture.
```
sh bin/testAll.sh
```
{: codeblock}

Exécutez le plug-in en tant qu'interface de ligne de commande autonome.
```
./main
```
{: codeblock}

Installez et appelez le plug-in en tant qu'interface de ligne de commande {{site.data.keyword.cloud_notm}} en choisissant l'une des commandes suivantes :
```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
