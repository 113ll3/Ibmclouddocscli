---

copyright:
  years: 2017
lastupdated: "2018-03-16"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Contribution au plug-in SDK
{: #contribute}

Suivez les instructions décrites ci-après pour contribuer au plug-in SDK d'interface de ligne de commande {{site.data.keyword.Bluemix}}. 

## Configuration de votre environnement de développement
{: #dev-env}

* [Interface de ligne de commande Cloud Foundry ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/cloudfoundry/cli/releases)

   L'interface de ligne de commande Cloud Foundry n'est pas requise, mais elle facilite l'accès à {{site.data.keyword.Bluemix_notm}} à partir du terminal.

   Pour plus d'informations sur l'interface de ligne de commande Cloud Foundry, voir la [documentation ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](/docs/cli/reference/cfcommands/index.html){: new_window}.

* [Interface de ligne de commande {{site.data.keyword.Bluemix_notm}}![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://clis.{DomainName}/ui/home.html)

   Ce plug-in s'installe dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. L'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} fournit également des ressources utiles pour accéder à {{site.data.keyword.Bluemix_notm}} à partir du terminal. 

   Pour plus d'informations sur l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, voir la[documentation ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](/docs/cli/reference/bluemix_cli/index.html){: new_window}.

* [Environnement de développement de Go ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://golang.org/doc/code.html)

   Go est strict en ce qui concerne les emplacements des packages, par conséquent, votre source doit être définie dans la structure de répertoire `$GOPATH`. Prenez soin de définir vos variables `$GOPATH` et `$GOROOT` et d'inclure `$GOPATH/bin` dans votre variable d'environnement `$PATH` en éditant votre fichier de configuration `~/.bash_profile` (sur Mac OS).

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* Gestionnaire de dépendances : [govendor ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/kardianos/govendor)

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

* Structure de test de BDD : [Ginkgo ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://onsi.github.io/ginkgo/)

La structure de test repose sur Ginkgo, une structure de test BDD pour Go. Elle est utilisée avec [Gomega ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://onsi.github.io/gomega/), qui est une bibliothèque d'assertion et de comparateur pour Ginkgo.

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

* Internationalisation : [go-i18n ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/nicksnyder/go-i18n) and [go-bindata ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/jteeuwen/go-bindata)

L'internationalisation est basée sur go-i18n. Il s'agit d'un outil de ligne de commande et de package qui fournit le support nécessaire pour traduire une application Go en plusieurs langues. Les groupements de traduction sont prétraités par go-bindata. Il s'agit d'une commande qui convertit un fichier d'entrée en code source Go gérable. 

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

* Débogage : [delve ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/derekparker/delve)

Delve est un débogueur pour le langage de programmation Go et il est utilisé par [Visual Studio Code ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://code.visualstudio.com/).

   * Installez `delve` à l'aide de la commande suivante :

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Pour Mac OS, suivez les [instructions ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://blog.ralch.com/tutorial/golang-debug-with-delve/) pour créer le certificat autosigné requis. 


## Bibliothèques d'exécution requises
{: #runtime-libs}

Les bibliothèques d'exécution requises sont gérées sous le répertoire `vendor` et sont validées dans le référentiel Git pour garantir la stabilité, dans la mesure où  Go ne fournit pas un gestionnaire de dépendances robuste. 

### Dépendances d'exécution
{: #runtime-dependencies}

Les dépendances imbriquées ne sont pas répertoriées.

* [github.ibm.com/Bluemix/bluemix-cli-sdk ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.ibm.com/Bluemix/bluemix-cli-sdk)

   SDK de plug-in d'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} qui fournit l'infrastructure pour développer les plug-in d'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. 

* [github.com/urfave/cli ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/urfave/cli)

   Ce package fournit l'infrastructure permettant de générer des applications de ligne de commande dans Go. Le plug-in d'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} repose sur une ancienne version de cette bibliothèque (github.com/codegangsta/cli).

* [github.com/asaskevich/govalidator ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/asaskevich/govalidator)

   Ce package fournit un certain nombre de valideurs et de nettoyeurs pour des chaînes, des structs et des collections. Utilisez ce package au lieu d'implémenter vos propres valideurs. 

* [github.com/parnurzeal/gorequest ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/parnurzeal/gorequest)

   Ce package implémente un client HTTP simplifié pour vous aider à gérer les demandes et les réponses HTTP. 

* [github.com/briandowns/spinner ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/briandowns/spinner)

   Ce package implémente une bouton fléché d'interface de ligne de commande permettant de fournir des commentaires en retour d'utilisateur durant le traitement d'opérations de longue durée, par exemple, une génération de SDK. 

* [github.com/cloudfoundry-attic/jibber_jabber ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/cloudfoundry-attic/jibber_jabber)

   Ce package est utilisé pour détecter la langue en cours du système d'exploitation. 


## Clonage du référentiel
{: #clone-repo}

Ce [référentiel ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/tree/compute) doit être cloné dans la [structure de répertoire de Go ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://golang.org/doc/code.html) en raison de la façon dont `govendor` fonctionne, qui suit également les meilleures pratiques de Go. 

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

**Remarque** : le script de génération installé également le plug-in dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}. 

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

Installez et appelez le plug-in en tant qu'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} en choisissant l'une des commandes suivantes :

```
bluemix plugin install main
bluemix help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
