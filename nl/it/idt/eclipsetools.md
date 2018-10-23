---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-18"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Distribuzione di applicazioni con IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}
{: #deploying-apps-with-ibm-eclipse-tools-for-ibm-cloud}

IBM® Eclipse Tools for {{site.data.keyword.Bluemix}} fornisce i plug-in che è possibile installare in un ambiente Eclipse esistente per assisterti nell'integrazione dell'IDE (integrated development environment) dello sviluppatore con Bluemix®. Gli strumenti ti consentono di distribuire i tuoi file JavaScript, WAR (web archive) e EAR (enterprise archive) e i server in pacchetto Liberty Profile al server Cloud direttamente dal tuo Eclipse IDE o WebSphere® Application Server Developer Tools (WDT).  Gli strumenti ti consentono anche di creare e collegare servizi alla tua applicazione e di definire delle variabili di ambiente come parte della distribuzione.

Se già hai un'applicazione in esecuzione in Eclipse con Websphere Application Developer Tools con Liberty Profile, puoi installare questi strumenti in aggiunta al programma in esecuzione. Puoi distribuire le tue applicazioni aggiungendo l'applicazione al server Cloud nel workbench. Grazie alle funzioni uniche del pacchetto di build Liberty per il supporto di server in pacchetto, puoi anche scegliere di distribuire l'intero server Liberty Profile a Cloud. Puoi anche distribuire le applicazioni JavaScript Node.js a Cloud.

## Installazione di Eclipse Tools

Impara a installare IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. È necessario un ambiente di esecuzione Java™ 1.7 o versione successiva.

Ci sono diversi modi per installare IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, inclusi i seguenti:
* Installazione dal Marketplace.
* Installazione da WASDev.
* Download dal programma di installazione di IBM WebSphere Application Server Developer Tools (WDT).

### Installazione dal Marketplace

L'installazione richiede [Eclipse Oxygen for Java EE Developers (4.7)](https://www.eclipse.org/downloads/packages/release/oxygen/r/eclipse-ide-java-developers) o [Eclipse Neon for Java EE Developers (4.6)](http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers).

Attieniti quindi alle istruzioni qui: [https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help](https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help).

### Installazione da WASDev

1. Apri la pagina [Download](https://developer.ibm.com/wasdev/downloads/) in WASDev.
2. Trascina l'icona di installazione (`Install`) nella barra degli strumenti in Eclipse.
3. Per impostazione predefinita, ci sono delle funzioni che sono selezionate per tuo conto. Fai clic su **Confirm**.
4. Accetta l'accordo di licenza e fai clic su **Finish**.

### Download dal programma di installazione di IBM WebSphere Application Server Developer Tools (WDT)

1. Apri **Help > Install WebSphere Software**. Cerca Cloud
2. Seleziona la voce `IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}` e fai clic su **Install**.
3. Per impostazione predefinita, ci sono delle funzioni che sono selezionate per tuo conto. Fai clic su **Confirm**.
4. Accetta l'accordo di licenza e fai clic su **Finish**.

## Supporto del server in pacchetto

Con IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, ci sono più scenari per eseguire il push di un server Liberty o di un server in pacchetto a Cloud e confermare la distribuzione.

* Crea il server Cloud.
* Crea un server Liberty Profile con un file WAR o EAR.
* Arresta il server.

Utilizzando IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} per il supporto di server in pacchetto, ci sono più scenari per:

* Eseguire il push di un server Liberty a Cloud.
* Eseguire il push di un server in pacchetto Liberty a Cloud.
* Confermare la corretta distribuzione dell'applicazione con l'esecuzione di un test.

Inoltre, puoi importare i file compressi di server in pacchetto in qualsiasi progetto nel tuo spazio di lavoro.

### Scenario 1 - Aggiunta di un server Liberty arrestato a Cloud ed esecuzione del test di un'applicazione

1. Fai clic con il tasto destro del mouse sul server `Cloud` nella vista Servers.
2. Seleziona **Add and Remove**.
3. Nella finestra di dialogo, vengono visualizzate le istanze del server Liberty. Selezionane una e fai clic su **Add**.
4. Fai clic su **Finish**. 
5. Nella finestra di dialogo dell'applicazione il nome predefinito è derivato dall'istanza del server Liberty. Puoi modificare questo nome, ma non deve contenere spazi o caratteri speciali. Il valore predefinito è accettabile se non è in conflitto con il nome delle applicazioni esistenti nel server Cloud.
6. Fai clic su **Finish** e attendi quindi la pubblicazione dell'applicazione su Cloud.
7. Fai clic con il tasto destro del mouse sul modulo Liberty Server aggiunto sotto il server Cloud. Seleziona **Open Home Page**. L'URL della root del server in pacchetto viene aperto nel tuo browser web predefinito. Utilizza questo URL della root come base per creare l'URL per l'esecuzione di test all'interno delle applicazioni WAR e EAR impacchettate.

### Scenario 2 - Trascina e rilascia un server Liberty arrestato su Cloud

Lo scenario 1 descrive come puoi aggiungere e rimuovere moduli di server Liberty. Ciò può essere semplificato con una funzione di trascinamento e rilascio.

1. Se continui dallo Scenario 1, rimuovi il modulo Liberty Server dal server Cloud.
2. Seleziona e trascina l'istanza server Liberty arrestata e rilasciala nel server Cloud nella vista Servers. Viene visualizzata la finestra di dialogo dell'applicazione.
3. Attieniti ai passi da 5 a 10 dallo scenario 1.

### Scenario 3 - Esegui un server in pacchetto in Cloud

Il menu di contesto dell'istanza del servizio Liberty Profile include un'azione Package Server. Questa azione impacchetta il server in un file di archivio. In Cloud, è stata aggiunta una nuova azione per impacchettare un server in un file compresso e distribuirlo a IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

1. Se continui dallo Scenario 1 o 2, rimuovi il modulo Liberty Server dal server Cloud.
2. Fai clic con il tasto destro del mouse sull'istanza del server Liberty Profile nella vista Servers.
3. Nel menu Utilities, seleziona **Package Server to {{site.data.keyword.Bluemix_notm}}**.
4. Nella finestra di dialogo, scegli il server Cloud dove vuoi distribuire l'applicazione.
5. Fai clic su **OK**. Viene visualizzata la finestra di dialogo dell'applicazione.
6. Attieniti ai passi da 5 a 10 dallo scenario 1.
7. Se viene visualizzata una finestra di dialogo di avanzamento, scegli **Run in background** a attendi che venga distribuita l'applicazione.

### Scenario 4 - Gestione dei file compressi di server in pacchetto - esecuzione sul server

Gli scenari precedenti descrivono come gestire le istanze Liberty Server esistenti nella vista Servers e come puoi distribuirle a Cloud. Puoi anche distribuire i file compressi di server in pacchetto esistenti a Cloud.

1. Crea oppure ottieni un file compresso di server in pacchetto.
2. Importa il file compresso in qualsiasi progetto nello spazio di lavoro.
3. Fai clic con il tasto destro del mouse sul file compresso e seleziona **Run As > Run on Server**. Viene visualizzata la finestra di dialogo Run On Server.
4. Seleziona un server Cloud.
5. Fai clic su **Finish**. Viene visualizzata la finestra di dialogo dell'applicazione.
6. Attieniti ai passi da 5 a 10 dallo scenario 1. Il nome del modulo è derivato dal file compresso.

### Scenario 5 - Gestione dei file compressi di server in pacchetto - trascinamento e rilascio

1. Seleziona e trascina il file compresso di server in pacchetto nel server Cloud nella vista Servers. Viene visualizzata la finestra di dialogo dell'applicazione.
2. Attieniti ai passi da 5 a 10 dallo scenario 1. Il nome del modulo è derivato dal nome del file compresso.

## Esecuzione del push di un file EAR

Utilizza IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} per eseguire il push di un EAR a Cloud.

Definisci un nuovo server.

1. Per creare un nuovo server Cloud, seleziona **File > New > Other**.
2. Seleziona **Server** dalla categoria Server e fai quindi clic su **Next**.
3. Sotto IBM, trova Cloud.
4. Fai clic su **Next**. 
5. Immetti le informazioni sul tuo account Cloud. Se non hai un account, fai clic su **Sign Up**.
6. Fai clic su **Next**. 
7. Scegli le tue organizzazioni e i tuoi spazi. Il valore predefinito è `dev`.
8. Fai clic su **Next**. 
9. Fai clic su **Finish**. 

Importa un file EAR

1. Fai clic con il tasto destro del mouse e seleziona **Import**.
2. Cerca il file EAR.
3. Sfoglia per individuare il file EAR che vuoi importare.
4. Assicurati che il runtime di destinazione (Target) sia impostato su {{site.data.keyword.Bluemix_notm}} Runtime.

Distribuisci la tua applicazione.

1. Fai clic con il tasto destro del mouse sul server Cloud avviato. Scegli **Add and Remove**.
2. Scegli l'EAR e fai clic su **Add**.
3. Fai clic su **Finish**. Viene visualizzata la finestra Application Details.
4. Denomina l'applicazione e fai quindi clic su **Next**. Un nome valido può contenere A-Z, 0-9, - e _. Non può contenere spazi o altri caratteri speciali. Le informazioni Launch Deployment sono impostate come valori predefiniti.
5. Fai clic su **Next**. 
6. Se necessario, seleziona i servizi. Fai clic su **Next**. 
7. Se necessario, aggiungi le variabili. Fai clic su **Finish**. 
8. Dopo che è stato eseguito il push dell'applicazione, fai clic con il tasto destro del mouse sul progetto e scegli **Open Home Page**.
9. Aggiungi il nome del modulo web e il nome dell'applicazione all'URL.
10. Per salvare le impostazioni e le variabili che hai specificato, seleziona la casella di spunta **Save to the manifest file** nella finestra Application Details.

## Distribuzione di un'applicazione Node.js
Utilizza IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} per distribuire un progetto Node.js nuovo o esistente in Cloud, imposta i dettagli di distribuzione dell'applicazione e verifica i risultati in un browser.

Se non disponi già di un'applicazione Node.js esistente, inizia con il passo 1. Se già disponi di un'applicazione Node.js esistente, inizia con il Passo 7.

1. Seleziona **File > New > Project**.
2. Seleziona **JavaScript project** dalla categoria JavaScript.
3. Fai clic su **Next**. 
4. Denomina il progetto.
5. Fai clic su **Finish**. 

Definisci un nuovo server.

1. Per creare un nuovo server Cloud, seleziona **File > New > Other**.
2. Seleziona **Server** dalla categoria Server e fai quindi clic su **Next**.
3. Sotto IBM, trova Cloud.
4. Fai clic su **Next**. 
5. Immetti le informazioni sul tuo account Cloud. Se non hai un account, fai clic su **Sign Up**.
6. Fai clic su **Next**. 
7. Scegli le tue organizzazioni e i tuoi spazi. Il valore predefinito è `dev`.
8. Fai clic su **Next**. 
9. Fai clic su **Finish**. 

Abilita l'applicazione per la pubblicazione in Cloud

1. Fai clic con il tasto destro del mouse sul progetto in Project Explorer e scegli **Properties > Project Facet**.
2. Fai clic su **Convert to faceted form**.
3. Sotto Project Facets, seleziona **Node.js Application**.
4. Fai clic su **OK**. 

Distribuisci la tua applicazione.

1. Fai clic con il tasto destro del mouse sul server Cloud avviato. Scegli **Add and Remove**.
2. Scegli il progetto e fai clic su **Add**.
3. Fai clic su **Finish**. Viene visualizzata la finestra Application Details.
4. Per salvare la configurazione di distribuzione nel file manifest dell'applicazione, seleziona la casella di spunta **Save to the manifest file** nella finestra Application Details.
5. Denomina l'applicazione e fai quindi clic su **Next**. Un nome valido può contenere A-Z, 0-9, - e _. Non può contenere spazi o altri caratteri speciali.
6. Accetta i valori predefiniti nel pannello di informazioni Launch Deployment.
7. Fai clic su **Next**. 
8. Se necessario, seleziona i servizi. Fai clic su **Next**. 
9. Se necessario, aggiungi le variabili. Fai clic su **Finish**. 
10. Dopo che è stato eseguito il push dell'applicazione, fai clic con il tasto destro del mouse sul progetto e scegli **Open Home Page**.

## Pubblicazione incrementale

Puoi aggiornare i file dell'applicazione in modo incrementale senza dover eseguire nuovamente il push dell'intera applicazione. Una pubblicazione incrementale ti consente di non dover eseguire una ridistribuzione completa per ogni modifica, con un conseguente risparmio di tempo nell'ambito del processo di sviluppo.

Questa funzione supporta le applicazioni web (WAR e EAR) e i server in pacchetto.

Per utilizzare la pubblicazione incrementale, la [modalità di sviluppo](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) deve essere abilitata per l'applicazione o il server in pacchetto.

1. Aggiungi un'applicazione o un server in pacchetto a Cloud, a meno che non ne esista uno/a.
**Nota:** questa funzione non può essere abilitata se il nome di distribuzione dell'applicazione ha un carattere di sottolineatura.

2. Abilita la modalità di sviluppo facendo clic con il tasto destro del mouse sull'applicazione o sul server in pacchetto e selezionando **Enable Development Mode**.

Una volta abilitata la modalità di sviluppo, utilizza la funzione di pubblicazione incrementale: 

1. Modifica l'applicazione come desideri.
   **Nota:** per i server in pacchetto, le modifiche alla configurazione non sono supportate.

2. Salva le modifiche.

3. Fai clic con il tasto destro del mouse sul server Cloud e seleziona **Publish**.

Modalità memorizzate in cache: dopo il riavvio del workbench, se l'applicazione era in modalità di sviluppo o in modalità di debug, vedi una finestra di avanzamento che indica che è in corso il richiamo degli stati di sviluppo e debug (Retrieving development and debug states). Di conseguenza, una volta terminato l'avanzamento, la modalità di sviluppo e quella di debug vengono aggiornate.

## Debug remoto

Esegui il debug remoto su un'applicazione Liberty o Node.js.

Per eseguire il debug, deve essere abilitata una [modalità di sviluppo](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html). Questa modalità viene eseguita automaticamente quando selezioni Enable Application Debug.

### Abilita il debug di EAR (enterprise archive), WAR (web archive) oppure Liberty Server

Attualmente, una porta locale libera viene generata casualmente ma, se il firewall del client la blocca, lo scenario di debug non riesce. Per evitare ciò, avvia la modalità di sviluppo, individua il file bluemixcache.xml e aggiungi port="#", dove # è il numero porta della macchina locale.

1. Nel server Cloud, fai clic con il tasto destro del mouse sull'applicazione di cui vuoi eseguire il debug.

   **Nota:** questa funzione non può essere abilitata se il nome di distribuzione dell'applicazione ha un carattere di sottolineatura. Modifica il nome prima di abilitare il debug remoto.

2. Fai clic su **Enable Application Debug**.

   La vista Progress mostra lo stato di `Establishing debug session for <AppName>``.

   L'applicazione mostra come sua condizione `Developing, Debugging <AppName>`.

   Il debugger è in esecuzione e pronto all'uso.

### Disabilita il debug di EAR, WAR o Liberty Server

Puoi disabilitare il processo di debug e lasciare la modalità di sviluppo abilitata.

1. Fai clic con il tasto destro del mouse sull'applicazione.
2. Fai clic su **Disable Application Debug**.
3. Una finestra di dialogo ti chiede se desideri disabilitare anche la modalità di sviluppo. Fai clic su **Yes** o su **No**.

Se la modalità di sviluppo rimane in esecuzione, l'applicazione mostra come sua condizione `Developing <AppName>``.

 Se entrambe sono disabilitate, l'applicazione mostra come sua condizione `Deployed as <AppName>`.

### Abilita il debug delle applicazioni Node.js

**Nota:** prima di completare la seguente procedura, assicurati di disporre di un'applicazione JavaScript esistente distribuita a Cloud. Vedi i passi precedenti per ulteriori informazioni sulla distribuzione di un'applicazione JavaScript.

1. Nella vista Servers, fai clic con il tasto destro del mouse sull'applicazione Node,js e seleziona **Open** JavaScript Debugger. Viene visualizzata una finestra di dialogo che ti chiede se vuoi aumentare il limite di memoria dell'applicazione. 
2. Fai clic su Yes. L'abilitazione di JavaScript Debugging aumenta i requisiti di memoria dell'applicazione e l'applicazione viene riavviata più velocemente con il limite di memoria aggiornato.
3. Seleziona un'installazione del browser da utilizzare per il debug. Google Chrome è il solo browser supportato. Se Google Chrome non è disponibile, seleziona il link **Manage...** e aggiungi un link a un'istallazione di Google Chrome locale.
4. Fai clic su **OK**. Viene visualizzato un monitoraggio dell'avanzamento che indica che è in corso l'aggiornamento della tua applicazione alla modalità di debug. Una volta abilitato il debug, Google Chrome viene aperto al sito corretto.
5. Esegui l'autenticazione in Google Chrome con il tuo nome e la tua password di accesso. Dopo una corretta autenticazione, viene aperta la console di debug. Puoi ora eseguire il debug dell'applicazione.

Modalità memorizzate in cache: dopo il riavvio del workbench, se l'applicazione era in modalità di sviluppo o in modalità di debug, vedi una finestra di avanzamento che indica che è in corso il richiamo degli stati di sviluppo e debug (Retrieving development and debug states). Una volta terminato l'avanzamento, la modalità di sviluppo e quella di debug vengono aggiornate.

## Connessione a un server Liberty remoto

Impara a utilizzare IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} per stabilire una connessione a un server Liberty remoto. Puoi stabilire una connessione a un server Liberty remoto che esegue WebSphere Application Server come un servizio.

Per stabilire una connessione a un server Liberty remoto, deve essere installato Liberty Tools. Devi anche creare un servizio WebSphere Application Server su Cloud.

1. Fai clic con il tasto destro del mouse sul tuo server Cloud e seleziona **Configure remote servers...**.

   Questa opzione è disponibile solo se è installato Liberty Tools.

2. Seleziona un servizio WebSphere Application Server.

   Se non hai un servizio WebSphere Application Server, potresti ricevere un messaggio di errore. Devi creare un servizio WebSphere Application Server su Cloud prima di poter completare questa impostazione.

3. Per definire un ambiente di runtime, seleziona **Configure runtime environments...**.

   **Nota:** se hai precedentemente creato un ambiente di runtime, puoi tralasciare questo passo.

4. Fai clic su **Next**. 

5. Immetti le informazioni relative alla connessione al server.

6. Fai clic su **Finish**. 

Hai stabilito una connessione a un server Liberty remoto utilizzando IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

## Abilitazione di Cloud Foundry Diego su applicazioni Cloud

Abilita la funzione di architettura Diego dall'interno di IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. Per abilitare Diego, hai bisogno di un server Cloud che sia definito nella vista Servers.

Diego è una nuova architettura Cloud Foundry utilizzata dalle istanze Cloud Foundry per gestire i contenitori applicazioni in esecuzione. L'architettura Diego sostituisce l'architettura DEA (Droplet Execution Agents) che veniva precedentemente utilizzata da Cloud Foundry. Le installazioni Cloud Foundry verranno trasferite a Diego e le applicazioni utente passeranno in modo automatico e trasparente alla nuova architettura.

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} supporta Diego e DEA. Puoi pubblicare le applicazioni, abilitare la pubblicazione delle applicazioni incrementale ed eseguire il debug di applicazioni. Diego permette anche a IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} di creare tunnel SSH (Secure Shell) in applicazioni Cloud distribuite, consentendo così connessioni più rapide e affidabili ad applicazioni Cloud durante il debug. Puoi anche abilitare SSH in modo da poter creare i tuoi tunnel per accedere alle risorse dell'applicazione.

Completa la seguente procedura per utilizzare l'architettura Diego per le tue applicazioni prima che Cloud passi alla distribuzione con Diego per impostazione predefinita:

1. Fai clic con il tasto destro del mouse sull'applicazione distribuita nella vista Servers.
2. Se Diego è supportato sul tuo server Cloud, e la tua applicazione non è già stata distribuita con Diego, seleziona **Enable Diego** dal menu.
3. Se il server supporta il tunneling SSH, il programma ti chiede se vuoi abilitare SSH per la tua applicazione. I tunnel SSH sono un meccanismo più affidabile per comunicare con la tua applicazione. Tuttavia, se selezioni **No**, le funzioni in IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} continuano a funzionare utilizzando un meccanismo che non richiede il tunneling SSH.

Viene quindi eseguita una ridistribuzione dell'applicazione utilizzando l'architettura Diego.

## Creazione di un server con Cloud Enterprise Federation

IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} supporta Cloud Enterprise Federation, un servizio SSO (single sign-on) che consente agli utenti di accedere in modo protetto ai servizi cloud. Con Cloud Enterprise Federation, puoi abilitare un'autenticazione di terze parti personalizzata fornita dalla tua organizzazione, senza l'autenticazione di accesso standard, per consentire ad altri utenti di accedere in modo protetto alle applicazioni.

Cloud Enterprise Federation autentica un insieme di utenti ad accedere ai servizi cloud. Dopo che hai abilitato Cloud Enterprise Federation, i tuoi utenti ricevono l'autenticazione per le applicazioni abilitate al cloud tramite l'opzione SSO (single sign-on). Gli utenti devono selezionare l'opzione SSO (single sign-on) per creare un server nel workbench Eclipse e accedere con l'accesso e la password dell'organizzazione. Dopo che hai abilitato Cloud Enterprise Federation, l'ID utente e la password cloud tradizionali non sono più utilizzati per autenticare gli utenti.

1. In IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, seleziona **File > New > Other...**.
2. Seleziona **Server > Server > Next**.
3. Dalla struttura ad albero, seleziona **IBM > {{site.data.keyword.Bluemix_notm}} > Next**.
4. Seleziona la casella di spunta **Use a one-time password to log in (SSO)**.
5. Nella finestra di dialogo di accesso viene visualizzato un collegamento ipertestuale. Fai clic sul collegamento ipertestuale per aprire la pagina di autenticazione Cloud.
6. Immetti il tuo indirizzo email e la tua password prevista.
7. Dopo un accesso eseguito correttamente, ti viene fornito un passcode monouso. Copia questo passcode nel campo Passcode della finestra di dialogo New Server di Eclipse Tools for Cloud.
8. Fai clic su **Finish**. 

Una voce di server Cloud è elencata nella vista Servers con Connected come stato del server (Server Status).
