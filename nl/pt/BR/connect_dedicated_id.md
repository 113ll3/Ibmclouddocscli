---



copyright:

  years: 2015，2018

lastupdated: "2018-04-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Conectando um ID dedicado ao seu IBMid público
{: #connect_dedicated_id}

Para efetuar login em uma nuvem dedicada na qual o serviço IAM público está disponível,
a CLI do {{site.data.keyword.Bluemix_notm}} requer que você efetue login com seu IBMid público em
vez com seu ID dedicado.


```
  $ bluemix login -a https://api.{dedicated_env}.bluemix.net
  Terminal da API: https://api.{dedicated_env}.bluemix.net

  O serviço de token público do IAM está disponível no ambiente dedicado.
  Efetue login com seu IBMid público ou use '--no-iam' para efetuar login somente como um usuário dedicado.
  E-mail>
```

Se seu ID dedicado já estiver conectado ao IBMid público, ele se autenticará e efetuará login:

```
  Authenticating...
  OK

  Conectado ao usuário dedicado my_dedicated_id
```

No entanto, se seu ID dedicado não estiver conectado ao IBMid público, será solicitado a conectar-se
manualmente com o IBMid público:

```
  Você está efetuando login com um IBMid que não está associado a nenhum usuário dedicado.
  Para configurar a conexão, insira as credenciais do usuário dedicado.

  Escolha um tipo de credencial:
  1. Nome do usuário e senha
  2. Um código de tempo (obtenha um em https://login.{dedicated_env}.bluemix.net.com/passcode)
  Insira um número>
```

Selecione uma opção para inserir as credenciais para o ID dedicado. Após a autenticação bem-sucedida, seu ID dedicado será conectado a seu IBMid público.

## Forçar o login no servidor UAA local

Para forçar o login no servidor UAA com um ID dedicado, especifique a opção `--no-iam` no comando `bluemix login`:

```
  $ bluemix login --no-iam
```

## Desconectar seu ID dedicado do IBMid público 

É possível usar `bluemix iam dedicated-id-disconnect` para desconectar o IBMid público com o ID dedicado conectado.

```
  $ bluemix iam dedicated-id-disconnect
  Do you really want to disconnect my_dedicated_id from public IBMid? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```

