---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-18"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Apps mit IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} bereitstellen
{: #deploying-apps-with-ibm-eclipse-tools-for-ibm-cloud}

Von IBM® Eclipse Tools for {{site.data.keyword.Bluemix}} werden Plug-ins bereitgestellt, die in einer vorhandenen Eclipse-Umgebung installiert werden können und Unterstützung bei der Integration der IDE (integrierte Entwicklungsumgebung) des Entwicklers in Bluemix® bieten. Die Tools ermöglichen es Ihnen, Ihre JavaScript-Dateien, WAR-Dateien (Web Archive) und EAR-Dateien (Enterprise Archive) sowie Ihre paketierten Liberty Profile-Server direkt über die Eclipse-IDE oder über WDT (WebSphere® Application Server Developer Tools) auf dem Cloud-Server bereitzustellen. Darüber hinaus können Sie mit den Tools im Rahmen der Bereitstellung Services erstellen, diese mit Ihrer Anwendung verknüpfen und Umgebungsvariablen definieren.

Wenn Sie Ihre Anwendung bereits in Eclipse ausführen und dabei WebSphere Application Developer Tools mit Liberty Profile verwenden, können Sie diese Tools zusätzlich zum laufenden Programm installieren. Sie können Ihre Anwendungen bereitstellen, indem Sie die jeweilige Anwendung in der Workbench zum Cloud-Server hinzufügen. Die besonderen Features der Liberty-Buildpack-Unterstützung für paketierte Server ermöglichen es darüber hinaus, den gesamten Liberty Profile-Server in der Cloud bereitzustellen. JavaScript-Node.js-Anwendungen können ebenfalls in der Cloud bereitgestellt werden.

## Eclipse Tools installieren

In diesem Abschnitt wird die Installation von IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} beschrieben. Als Ausführungsumgebung ist Java™ 1.7 oder eine aktuellere Version erforderlich.

Für die Installation von IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} stehen unter anderem die folgenden Möglichkeiten zur Verfügung: 
* Installation über Marketplace.
* Installation über WASDev.
* Download über das Installationsprogramm von IBM WebSphere Application Server Developer Tools (WDT).

### Installation über Marketplace

Für die Installation ist [Eclipse Oxygen for Java EE Developers (4.7)](https://www.eclipse.org/downloads/packages/release/oxygen/r/eclipse-ide-java-developers) oder [Eclipse Neon for Java EE Developers (4.6)](http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers) erforderlich.

Gehen Sie anschließend gemäß den folgenden Anweisungen vor: [https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help](https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help).

### Installation über WASDev

1. Öffnen Sie die [Downloadseite](https://developer.ibm.com/wasdev/downloads/) in WASDev.
2. Ziehen Sie das Symbol `Installieren` in die Symbolleiste in Eclipse.
3. Standardmäßig sind vorab Features ausgewählt. Klicken Sie auf **Bestätigen**.
4. Akzeptieren Sie die Lizenzvereinbarung und klicken Sie auf **Fertigstellen**.

### Download über das Installationsprogramm von IBM WebSphere Application Server Developer Tools (WDT)

1. Öffnen Sie **Hilfe > WebSphere Software installieren**. Suchen Sie nach 'Cloud'.
2. Wählen Sie den Eintrag `IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}` aus und klicken Sie auf **Installieren**.
3. Standardmäßig sind Features vorab ausgewählt. Klicken Sie auf **Bestätigen**.
4. Akzeptieren Sie die Lizenzvereinbarung und klicken Sie auf **Fertigstellen**.

## Unterstützung für paketierte Server

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} umfasst eine Reihe von Szenarios für die Bereitstellung eines Liberty-Servers oder paketierten Servers in der Cloud mithilfe einer Push-Operation und die Bestätigung der Bereitstellung.

* Erstellen Sie den Cloud-Server.
* Erstellen Sie einen Liberty Profile-Server mit einer WAR- oder EAR-Datei.
* Stoppen Sie den Server.

Die IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}-Unterstützung für paketierte Server umfasste eine Reihe von Szenarios für Folgendes:

* Bereitstellen eines Liberty-Servers in der Cloud mithilfe einer Push-Operation.
* Bereitstellen eines paketierten Liberty-Servers in der Cloud mithilfe einer Push-Operation.
* Bestätigen der erfolgreichen Bereitstellung der Anwendung von Tests.

Zusätzlich können Sie komprimierte Dateien für gepackte Server in ein Projekt im Arbeitsbereich importieren.

### Szenario 1 - Hinzufügen eines gestoppten Liberty-Servers zur Cloud und Testen einer Anwendung

1. Klicken Sie mit der rechten Maustaste auf den `Cloud`-Server in der Serveransicht.
2. Wählen Sie **Hinzufügen und Entfernen** aus.
3. Im Dialogfenster werden die Instanzen des Liberty-Servers angezeigt. Wählen Sie eine aus und klicken Sie auf **Hinzufügen**.
4. Klicken Sie auf **Fertigstellen**.
5. Im Anwendungsdialog wird der Standardname von der Instanz des Liberty-Servers abgeleitet. Sie können diesen Namen ändern; beachten Sie, dass der Name keine Leerzeichen oder Sonderzeichen enthalten darf. Der Standardname ist zulässig, wenn er keinen Konflikt mit Namen vorhandener Anwendungen im Bluemix-Server verursacht.
6. Klicken Sie auf **Fertigstellen** und warten Sie anschließend, bis die Anwendung in der Cloud veröffentlicht ist.
7. Klicken Sie mit der rechten Maustaste auf das hinzugefügte Liberty-Server-Modul unter dem Cloud-Server. Wählen Sie **Homepage öffnen** aus. Die Stamm-URL des paketierten Servers wird im Standard-Web-Browser geöffnet. Verwenden Sie diese Stamm-URL als Basis für die Generierung der URL für Tests in den paketierten WAR- und EAR-Anwendungen.

### Szenario 2 - Ziehen und Ablegen eines gestoppten Liberty-Servers in der Cloud

In Szenario 1 wird beschrieben, wie Liberty-Servermodule hinzugefügt und entfernt werden können. Mithilfe einer Funktion zum Ziehen und Ablegen kann dieser Vorgang vereinfacht werden.

1. Falls Sie bereits Szenario 1 ausgeführt haben, entfernen Sie das Liberty-Servermodul vom Cloud-Server.
2. Wählen Sie die Instanz des gestoppten Liberty-Servers aus, ziehen Sie sie zum Cloud-Server in der Serveransicht und legen Sie sie ab. Das Fenster mit dem Anwendungsdialog wird angezeigt.
3. Führen Sie die Schritte 5 bis 10 von Szenario 1 aus.

### Szenario 3 - Ausführen eines paketierten Servers in der Cloud

Das Kontextmenü der Liberty Profile-Serviceinstanz enthält die Aktion 'Server paketieren'. Mit dieser Aktion wird der Server in eine Archivdatei gepackt. In der Cloud wurde eine neue Aktion hinzugefügt, mit der der Server in eine komprimierte Datei gepackt und in IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} bereitgestellt wird.

1. Falls Sie bereits Szenario 1 oder 2 ausgeführt haben, entfernen Sie das Liberty-Servermodul vom Cloud-Server.
2. Klicken Sie mit der rechten Maustaste auf die Instanz des Liberty Profile-Servers in der Serveransicht.
3. Wählen Sie im Dienstprogrammmenü **Server für {{site.data.keyword.Bluemix_notm}} packen** aus.
4. Wählen Sie im Dialogfenster den Cloud-Server aus, auf dem Sie die Anwendung bereitstellen möchten.
5. Klicken Sie auf **OK**. Das Fenster mit dem Anwendungsdialog wird angezeigt.
6. Führen Sie die Schritte 5 bis 10 von Szenario 1 aus.
7. Wenn ein Fortschrittsdialogfenster angezeigt wird, wählen Sie **Im Hintergrund ausführen** aus und warten Sie, bis die Anwendung bereitgestellt wird.

### Szenario 4 - Arbeiten mit komprimierten Dateien für paketierte Server - Ausführung auf dem Server

In den vorhergehenden Szenarios wurde beschrieben, wie mit vorhandenen Liberty Server-Instanzen in der Serveransicht gearbeitet wird und wie diese in der Cloud bereitgestellt werden können. Es ist ebenfalls möglich, vorhandene komprimierte Dateien für paketierte Server in der Cloud bereitzustellen.

1. Erstellen Sie eine komprimierte Datei für einen paketierten Server oder fordern Sie eine solche Datei an.
2. Importieren Sie die komprimierte Datei in ein beliebiges Projekt im Arbeitsbereich.
3. Klicken Sie mit der rechten Maustaste auf die komprimierte Datei und wählen Sie **Ausführen als > Auf dem Server ausführen** aus. Das Dialogfenster für die Ausführung auf dem Server wird angezeigt.
4. Wählen Sie einen Cloud-Server aus.
5. Klicken Sie auf **Fertigstellen**. Das Fenster mit dem Anwendungsdialog wird angezeigt.
6. Führen Sie die Schritte 5 bis 10 von Szenario 1 aus. Der Name des Moduls wird von der komprimierten Datei abgeleitet.

### Szenario 5 - Arbeiten mit komprimierten Dateien für paketierte Server - Ziehen und ablegen

1. Wählen Sie die komprimierte Datei für den paketierten Server aus, ziehen Sie sie zum Cloud-Server in der Serveransicht und legen Sie sie dort ab. Das Fenster mit dem Anwendungsdialog wird angezeigt.
2. Führen Sie die Schritte 5 bis 10 von Szenario 1 aus. Der Name des Moduls wird vom Namen der komprimierten Datei abgeleitet.

## Push-Operation für eine EAR-Datei durchführen

Mit IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} können Sie eine EAR-Datei mithilfe einer Push-Operation in der Cloud bereitstellen.

Definieren Sie einen neuen Server.

1. Wählen Sie zum Erstellen eines neuen Cloud-Servers **Datei > Neu > Andere** aus.
2. Wählen Sie **Server** aus der Serverkategorie aus und klicken Sie anschließend auf **Weiter**.
3. Suchen Sie unter IBM nach 'Cloud'.
4. Klicken Sie auf **Weiter**.
5. Geben Sie die Kontoinformationen für die Cloud ein. Klicken Sie auf **Registrierung**, falls Sie noch nicht über ein Konto verfügen.
6. Klicken Sie auf **Weiter**.
7. Wählen Sie Ihre Organisationen und Bereiche aus. Der Standardwert ist `dev`.
8. Klicken Sie auf **Weiter**.
9. Klicken Sie auf **Fertigstellen**.

Importieren Sie eine EAR-Datei. 

1. Drücken Sie die rechte Maustaste und wählen Sie **Importieren** aus.
2. Suchen Sie nach einer EAR-Datei.
3. Suchen Sie nach der zu importierenden EAR-Datei.
4. Stellen Sie sicher, dass für die Ziellaufzeit {{site.data.keyword.Bluemix_notm}} Runtime festgelegt ist.

Stellen Sie die Anwendung bereit.

1. Klicken Sie mit der rechten Maustaste auf den gestarteten Cloud-Server. Wählen Sie **Hinzufügen und Entfernen** aus.
2. Wählen Sie die EAR-Datei aus und klicken Sie auf **Hinzufügen**.
3. Klicken Sie auf **Fertigstellen**. Das Fenster mit den Anwendungsdetails wird geöffnet.
4. Geben Sie einen Namen für die Anwendung ein und klicken Sie dann auf **Weiter**. Ein gültiger Name darf die Zeichen A - Z, 0 - 9, - und _ enthalten. Er darf keine Leerzeichen oder andere Sonderzeichen enthalten. Die Informationen zum Starten der Bereitstellung werden standardmäßig festgelegt.
5. Klicken Sie auf **Weiter**.
6. Wählen Sie bei Bedarf Services aus. Klicken Sie auf **Weiter**.
7. Fügen Sie bei Bedarf Variablen hinzu. Klicken Sie auf **Fertigstellen**.
8. Nach dem Bereitstellen der Anwendung klicken Sie mit der rechten Maustaste auf das Projekt und wählen Sie **Homepage öffnen** aus.
9. Fügen Sie den Webmodulnamen und den Anwendungsnamen zur URL hinzu.
10. Wählen Sie zum Speichern der angegebenen Einstellungen und Variablen das Kontrollkästchen **In Manifestdatei speichern** im Fenster mit den Anwendungsdetails aus.

## Node.js-Anwendung bereitstellen
Mit IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} können Sie ein vorhandenes oder neues Node.js-Projekt in der Cloud bereitstellen, Anwendungsbereitstellungsdetails festlegen und die Ergebnisse in einem Browser überprüfen.

Wenn Sie nicht bereits über eine vorhandene Node.js-Anwendung verfügen, beginnen Sie mit Schritt 1. Verfügen Sie bereits über eine vorhandene Node.js-Anwendung, beginnen Sie mit Schritt 7.

1. Wählen Sie **Datei > Neu > Projekt** aus.
2. Wählen Sie in der JavaScript-Kategorie **JavaScript-Projekt** aus.
3. Klicken Sie auf **Weiter**.
4. Geben Sie einen Namen für das Projekt ein.
5. Klicken Sie auf **Fertigstellen**.

Definieren Sie einen neuen Server.

1. Wählen Sie zum Erstellen eines neuen Cloud-Servers **Datei > Neu > Andere** aus.
2. Wählen Sie **Server** aus der Serverkategorie aus und klicken Sie anschließend auf **Weiter**.
3. Suchen Sie unter IBM nach 'Cloud'.
4. Klicken Sie auf **Weiter**.
5. Geben Sie die Kontoinformationen für die Cloud ein. Klicken Sie auf **Registrierung**, falls Sie noch nicht über ein Konto verfügen.
6. Klicken Sie auf **Weiter**.
7. Wählen Sie Ihre Organisationen und Bereiche aus. Der Standardwert ist `dev`.
8. Klicken Sie auf **Weiter**.
9. Klicken Sie auf **Fertigstellen**.

Aktivieren Sie die Anwendung für die Veröffentlichung in der Cloud.

1. Klicken Sie im Projektexplorer mit der rechten Maustaste und wählen Sie **Eigenschaften > Projektfacette** aus.
2. Klicken Sie auf **In Facettenformat umwandeln**.
3. Wählen Sie unter 'Projektfacetten' die Option **Node.js-Anwendung** aus.
4. Klicken Sie auf **OK**.

Stellen Sie die Anwendung bereit.

1. Klicken Sie mit der rechten Maustaste auf den gestarteten Cloud-Server. Wählen Sie **Hinzufügen und Entfernen** aus.
2. Wählen Sie das Projekt aus und klicken Sie auf **Hinzufügen**.
3. Klicken Sie auf **Fertigstellen**. Das Fenster mit den Anwendungsdetails wird geöffnet.
4. Wählen Sie zum Speichern der Bereitstellungskonfiguration in der Anwendungsmanifestdatei das Kontrollkästchen **In Manifestdatei speichern** im Fenster mit den Anwendungsdetails aus.
5. Geben Sie einen Namen für die Anwendung ein und klicken Sie dann auf **Weiter**. Ein gültiger Name darf die Zeichen A - Z, 0 - 9, - und _ enthalten. Er darf keine Leerzeichen oder andere Sonderzeichen enthalten.
6. Bestätigen Sie die Standardwerte in der Anzeige mit den Informationen zum Starten der Bereitstellung.
7. Klicken Sie auf **Weiter**.
8. Wählen Sie bei Bedarf Services aus. Klicken Sie auf **Weiter**.
9. Fügen Sie bei Bedarf Variablen hinzu. Klicken Sie auf **Fertigstellen**.
10. Nach dem Bereitstellen der Anwendung klicken Sie mit der rechten Maustaste auf das Projekt und wählen Sie **Homepage öffnen** aus.

## Inkrementelle Veröffentlichung

Sie können Anwendungsdateien inkrementell aktualisieren, ohne für die gesamte Anwendung eine erneute Push-Operation ausführen zu müssen. Durch das inkrementelle Veröffentlichen ersparen Sie sich die Durchführung einer kompletten erneuten Bereitstellung bei jeder Änderung und sparen dadurch im Entwicklungsprozess Zeit.

Dieses Feature unterstützt Webanwendungen (WAR und EAR) sowie paketierte Server.

Für eine inkrementelle Veröffentlichung muss der [Entwicklungsmodus](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) für die Anwendung oder den paketierten Server aktiviert sein.

1. Fügen Sie eine Anwendung oder einen paketierten Server zur Cloud hinzu, sofern vorhanden.
**Anmerkung:** Diese Funktion kann nicht aktiviert werden, wenn der Anwendungsbereitstellungsname ein Unterstreichungszeichen aufweist.

2. Aktivieren Sie den Entwicklungsmodus, indem Sie mit der rechten Maustaste auf die Anwendung oder den paketierten Server klicken und die Option **Entwicklungsmodus aktivieren** auswählen.

Sobald der Entwicklungsmodus aktiviert ist, verwenden Sie die Funktion für eine inkrementelle Veröffentlichung:

1. Ändern Sie die Anwendung wie gewünscht.
   **Anmerkung:** Änderungen an der Konfiguration werden für paketierte Server nicht unterstützt.

2. Speichern Sie die Änderungen.

3. Klicken Sie mit der rechten Maustaste auf den Cloud-Server und wählen Sie die Option **Veröffentlichen** aus.

Zwischengespeicherte Modi: Wenn die Anwendung den Entwicklungsmodus oder Debugmodus aufwies, wird nach dem Neustart der Workbench ein Fortschrittsfenster mit einer Nachricht angezeigt, die besagt, dass die Statusarten für Entwicklungsmodus und Debugmodus abgerufen werden. Nach dem Abschluss des Verarbeitungsfortschritts werden der Entwicklungsmodus und der Debugmodus entsprechend aktualisiert.

## Debugger remote ausführen

Sie können ein fernes Debugging für eine Liberty- oder Node.js-Anwendung ausführen.

Der [Entwicklungsmodus](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) muss für die Ausführung des Debuggers aktiviert sein. Dieser Modus wird bei der Auswahl der Option zur Aktivierung des Anwendungsdebugging automatisch ausgeführt.

### Debugging für EAR-Datei (Enterprise Archive), WAR-Datei (Web Archive) oder Liberty-Server aktivieren

Derzeit wird ein freier lokaler Port nach dem Zufallsprinzip generiert, wenn er jedoch von der Firewall eines Kunden blockiert wird, schlägt das Debugging-Szenario fehl. Starten Sie zur Vermeidung dieses Problems den Entwicklungsmodus, suchen Sie die Datei 'bluemixcache.xml' und fügen Sie 'port="#"' hinzu, wobei das Zeichen # für den Portnamen des lokalen Computers steht.

1. Klicken Sie auf dem Cloud-Server mit der rechten Maustaste auf die Anwendung, für die Sie den Debugger ausführen möchten.

   **Anmerkung:** Diese Funktion kann nicht aktiviert werden, wenn der Anwendungsbereitstellungsname ein Unterstreichungszeichen aufweist. Ändern Sie den Namen, bevor Sie die remote Ausführung des Debuggers aktivieren.

2. Klicken Sie auf die Option **Anwendungsdebugging aktivieren**.

   In der Fortschrittsansicht wird der Status von `Einrichtung einer Debugsitzung für <AppName>` angezeigt.

   Für die Anwendung `<AppName>` wird angezeigt, dass sie sich im Status 'Wird entwickelt' bzw. 'Debugging wird ausgeführt' befindet.

   An dieser Stelle wird der Debugger ausgeführt und kann verwendet werden.

### Ausführung des Debuggers inaktivieren

Sie können den Debugprozess inaktivieren und den Entwicklungsmodus aktiviert lassen.

1. Klicken Sie mit der rechten Maustaste auf die Anwendung.
2. Klicken Sie auf die Option **Anwendungsdebugging inaktivieren**.
3. Es wird ein Dialogfenster geöffnet und Sie werden gefragt, ob Sie auch den Entwicklungsmodus inaktivieren möchten. Klicken Sie auf **Ja** oder **Nein**.

Wenn der Entwicklungsmodus weiter aktiv bleibt, wird für die Anwendung `<AppName> wird entwickelt` angezeigt.

 Sind beide Optionen inaktiviert, wird für die Anwendung `<AppName> wird bereitgestellt als` angezeigt.

### Debugging für Node.js-Anwendung aktivieren

**Anmerkung:** Stellen Sie vor der Ausführung der folgenden Schritte sicher, dass Sie über eine vorhandene JavaScript-Anwendung verfügen, die in der Cloud bereitgestellt wird. Weitere Informationen zum Bereitstellen einer JavaScript-Anwendung finden Sie in den vorherigen Schritten.

1. Klicken Sie in der Serveransicht mit der rechten Maustaste auf die Node.js-Anwendung und wählen Sie für den JavaScript-Debugger **Öffnen** aus. Es wird ein Dialogfenster angezeigt und Sie werden gefragt, ob Sie die Speicherbegrenzung für die Anwendung erhöhen möchten.
2. Klicken Sie auf 'Ja'. Durch das Aktivieren des JavaScript-Debuggings erhöht sich der Anwendungsspeicherbedarf; die Anwendung wird mit der aktualisierten Speicherbegrenzung schneller erneut gestartet.
3. Wählen Sie eine Browserinstallation aus, die für das Debugging verwendet werden soll. Google Chrome ist der einzige Browser, der unterstützt wird. Wenn Google Chrome keine verfügbare Option ist, wählen Sie den Link **Verwalten...** aus und fügen Sie einen Link zu einer lokalen Google Chrome-Installation hinzu.
4. Klicken Sie auf **OK**. Es wird ein Fortschrittsmonitor angezeigt, der die Aktualisierung (der App) für den Debugmodus angibt. Sobald das Debugging aktiviert ist, wird Google Chrome für die richtige Site geöffnet.
5. Authentifizieren Sie sich in Google Chrome mit Ihrem Anmeldenamen und Kennwort. Nach einer erfolgreichen Authentifizierung wird die Debugkonsole geöffnet. Sie können jetzt das Debugging für die Anwendung ausführen.

Zwischengespeicherte Modi: Wenn die Anwendung den Entwicklungsmodus oder Debugmodus aufwies, wird nach dem Neustart der Workbench ein Fortschrittsfenster mit einer Nachricht angezeigt, die besagt, dass die Statusarten für Entwicklungsmodus und Debugmodus abgerufen werden. Nach dem Abschluss des Verarbeitungsfortschritts werden der Entwicklungsmodus und der Debugmodus aktualisiert.

## Verbindung zu einem fernen Liberty-Server herstellen

In diesem Abschnitt wird beschrieben, wie mit IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} eine Verbindung zu einem fernen Liberty-Server hergestellt wird. Sie können eine Verbindung zu einem fernen Liberty-Server herstellen, auf dem WebSphere Application Server als Service ausgeführt wird.

Damit eine Verbindung zu einem fernen Liberty-Server hergestellt werden kann, müssen Liberty-Tools installiert sein. Außerdem müssen Sie einen WebSphere Application Server-Service in der Cloud erstellen.

1. Klicken Sie mit der rechten Maustaste auf den Cloud-Server und wählen Sie die Option **Fernen Server konfigurieren...** aus.

   Diese Option ist nur verfügbar, wenn Liberty-Tools installiert sind.

2. Wählen Sie einen WebSphere Application Server-Service aus.

   Falls kein WebSphere Application Server-Service vorhanden ist, kann es vorkommen, dass eine Fehlernachricht angezeigt wird. Damit Sie diese Konfiguration durchführen können, müssen Sie vorher einen WebSphere Application Server-Service in der Cloud erstellen.

3. Wählen Sie zum Definieren einer Laufzeitumgebung die Option **Laufzeitumgebungen konfigurieren...** aus.

   **Anmerkung:** Falls Sie vorher eine Laufzeitumgebung erstellt haben, können Sie diesen Schritt überspringen.

4. Klicken Sie auf **Weiter**.

5. Geben Sie die Verbindungsinformationen für den Server ein.

6. Klicken Sie auf **Fertigstellen**.

Sie haben unter Verwendung von IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} ein Verbindung zu einem fernen Liberty-Server hergestellt.

## Cloud Foundry Diego für Cloud-Anwendungen aktivieren

Aktivieren Sie die Funktion für die Diego-Architektur in IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. Zum Aktivieren von Diego benötigen Sie einen Cloud-Server, der in der Serveransicht definiert ist.

Diego ist eine neue Cloud Foundry-Architektur, die Cloud Foundry-Instanzen zum Verwalten von aktiven Anwendungscontainern verwenden. Die Diego-Architektur ersetzt die DEA-Architektur (DEA - Droplet Execution Agents), die zuvor von Cloud Foundry verwendet wurde. Cloud Foundry-Installationen werden automatisch nach Diego verschoben und Benutzeranwendungen werden automatisch und transparent auf die neue Architektur umgestellt.

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} unterstützt Diego und DEA. Sie können Anwendungen veröffentlichen, inkrementelle Anwendungsveröffentlichungen aktivieren und den Debugger für Anwendungen ausführen. Diego ermöglicht IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} außerdem, SSH-Tunnel (SSH - Secure Shell) in bereitgestellten Cloud-Anwendungen zu erstellen, wodurch eine schnellere und zuverlässigere Verbindung zu Cloud-Anwendungen während des Debuggings möglich ist. Sie können SSH auch aktivieren, damit Sie eigene Tunnel für den Zugriff auf Anwendungsressourcen erstellen können.

Führen Sie die folgenden Schritte aus, um die Diego-Architektur für Ihre Anwendungen zu verwenden, bevor in der Cloud standardmäßig zur Bereitstellung mit Diego gewechselt wird:

1. Klicken Sie mit der rechten Maustaste auf die bereitgestellte Anwendung in der Serveransicht.
2. Wenn Diego auf dem Cloud-Server unterstützt wird und die Anwendung noch nicht mit Diego bereitgestellt wird, wählen Sie im Menü die Option **Diego aktivieren** aus.
3. Wenn der Server die SSH-Tunnelung unterstützt, wird vom Programm gefragt, ob Sie SSH für die Anwendung aktivieren möchten. SSH-Tunnel stellen einen zuverlässigeren Mechanismus für die Kommunikation mit der Anwendung dar. Wenn Sie jedoch **Nein** auswählen, arbeiten die Funktionen in IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} weiterhin mit einem Mechanismus, der keine SSH-Tunnelung erfordert.

Anschließend wird die Anwendung mithilfe der Diego-Architektur erneut bereitgestellt.

## Server mit Cloud Enterprise Federation erstellen

Von IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} wird Cloud Enterprise Federation unterstützt, ein Single Sign-on-Service, mit dem Benutzer sicher auf Cloud-Services zugreifen können. Mit Cloud Enterprise Federation können Sie ohne Verwendung der standardmäßigen Anmeldeauthentifizierung eine angepasste Authentifizierung eines Drittanbieters aktivieren, die von Ihrer eigenen Organisation bereitgestellt wird, damit andere Benutzer sicher auf Anwendungen zugreifen können.

Von Cloud Enterprise Federation werden Benutzer für den Zugriff auf Cloud-Services authentifiziert. Nachdem Sie Cloud Enterprise Federation aktiviert haben, erhalten die Benutzer die Authentifizierung für Cloud-fähige Anwendungen über die Single Sign-on-Option. Die Benutzer müssen die Single Sign-on-Option auswählen, um einen Server in der Eclipse-Workbench zu erstellen und sich mit der Anmeldung und dem Kennwort der Organisation anzumelden. Nach der Aktivierung von Cloud Enterprise Federation werden die herkömmliche Cloud-Benutzer-ID und das herkömmliche Cloud-Kennwort in Eclipse Tools nicht mehr für die Authentifizierung von Benutzern verwendet.

1. Wählen Sie in IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} die Optionen **Datei > Neu > Andere...** aus.
2. Wählen Sie **Server > Server > Weiter** aus.
3. Wählen Sie in der Baumstruktur **IBM > {{site.data.keyword.Bluemix_notm}} > Weiter** aus.
4. Wählen Sie das Kontrollkästchen **Ein Einmalkennwort für die Anmeldung verwenden (SSO)** aus.
5. Im Anmeldedialog wird eine Hyperlink angezeigt. Klicken Sie auf den Hyperlink, um die Authentifizierungsseite für die Cloud zu öffnen.
6. Geben Sie Ihre E-Mail-Adresse und Ihr gewünschtes Kennwort ein.
7. Nach einer erfolgreichen Anmeldung wird ein einmaliger Kenncode bereitgestellt. Kopieren Sie diesen Kenncode in das Kenncodefeld des Dialogs für den neuen Server von Eclipse Tools for Cloud.
8. Klicken Sie auf **Fertigstellen**.

In der Serveransicht wird ein Eintrag für den Cloud-Server mit dem Serverstatus 'Verbunden' (Connected) aufgelistet.
