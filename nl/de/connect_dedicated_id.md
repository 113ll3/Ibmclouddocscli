---



copyright:

  years: 2015，2017

lastupdated: "2017-12-08"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Dedizierte ID mit öffentlicher IBMid verbinden
{: #connect_dedicated_id}

Bei der Anmeldung bei einer dedizierten Cloud, bei der der öffentliche IAM-Service verfügbar ist, werden Sie von der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle dazu aufgefordert, sich nicht mit der dedizierten ID, sondern mit Ihrer öffentlichen IBMid anzumelden. 


```
  $ bluemix login -a https://api.{dedicated_env}.bluemix.net
  API-Endpunkt: https://api.{dedicated_env}.bluemix.net

  Der öffentliche IAM-Token-Service ist in der dedizierten Umgebung verfügbar.
  Melden Sie sich mit Ihrer öffentlichen IBMid an oder verwenden Sie '--no-iam', wenn die Anmeldung nur als dedizierter Benutzer erfolgen soll.

  Email>
```

Ist Ihre dedizierte ID bereits mit der öffentlichen IBMid verbunden, werden Authentifizierung und Anmeldung durchgeführt: 

```
  Authentifizieren...
  OK

  Verbunden mit dediziertem Benutzer eigene_dedizierte_ID
```

Ist Ihre dedizierte ID jedoch noch nicht mit der öffentlichen IBMid verbunden, werden Sie dazu aufgefordert, manuell eine Verbindung zu der öffentlichen IBMid herzustellen: 

```
  Sie melden sich unter einer IBMid an, die keinem dedizierten Benutzer zugeordnet ist. Um die Verbindung herzustellen, müssen Sie die Berechtigungsnachweise des dedizierten Benutzers eingeben. Wählen Sie einen Berechtigungsnachweistyp aus:
  1. Benutzername und Kennwort
  2. Einmaliger Code (Abruf unter https://login.{dedicated_env}.bluemix.net.com/passcode)
  Geben Sie eine Zahl ein.>
```

Wählen Sie eine Option aus, um die Berechtigungsnachweise für die dedizierte ID einzugeben. Nach der erfolgreichen Authentifizierung ist Ihre dedizierte ID nun mit Ihrer öffentlichen IBMid verbunden. 

## Anmeldung bei einem lokalen UAA-Server erzwingen

Erzwingen Sie eine Anmeldung bei dem UAA-Server unter einer dedizierten ID, indem Sie die Option `--no-iam` beim Befehl `bluemix login` angeben: 

```
  $ bluemix login --no-iam
```

## Verbindung zwischen dedizierter ID und öffentlicher IBMid aufheben 

Mit dem Befehl `bluemix iam dedicated-id-disconnect` können Sie die Verbindung zwischen der öffentlichen IBMid und der dedizierten ID aufheben. 

```
  $ bluemix iam dedicated-id-disconnect
  Soll eigene_dedizierte_ID wirklich von der öffentlichen IBMid getrennt werden? (J/N)> j
  Dedizierter Benutzer 'eigene_dedizierte_ID' wird von öffentlicher IBMid getrennt...
  OK

  Abmelden...
  OK
```

