---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Desinstalar a CLI do  {{site.data.keyword.Bluemix_notm}}

Consulte as seções a seguir para obter instruções sobre como desinstalar o {{site.data.keyword.Bluemix_notm}} em plataformas específicas.

## Desinstalar no Windows

* Clique no botão `Start` e, em seguida, selecione `Control Panel`
* Na janela pop-up, clique em `Uninstall a program`
* Na lista de aplicativos pop-up, localize `IBM Cloud Command Line Interface`
* Clique com o botão direito em `IBM Cloud Command Line Interface` e selecione `Uninstall`
* O desinstalador será ativado. Siga as instruções para concluir a desinstalação.

## Desinstalar no Linux/macOS

### Antes da versão  ` 0.9.0 `

* Abra um terminal e execute os comandos a seguir
  * ` rm -rf /usr/local/ibmcloud `
  * ` rm -f /usr/local/bin/ibmcloud `
  * ` rm -f /usr/local/bin/bluemix `
  * ` rm -f /usr/local/bin/bx `
  * ` rm -f /usr/local/bin/ibmcloud-analytics `
* Limpe os scripts de conclusão automática, se os tiver configurado. Para obter mais detalhes, consulte [Ativar a conclusão automática da CLI](enable_cli_autocompletion.html).

### Versão  ` 0.9.0 `  e mais recente

* Abra um terminal e execute o comando a seguir
  * ` /usr/local/ibmcloud/uninstall `
* Limpe os scripts de conclusão automática, se os tiver configurado. Para obter mais detalhes, consulte [Ativar a conclusão automática da CLI](enable_cli_autocompletion.html).
