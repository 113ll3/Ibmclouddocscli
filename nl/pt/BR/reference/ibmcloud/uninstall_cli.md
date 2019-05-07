---

copyright:
  years: 2019
lastupdated: "2019-04-26"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# Desinstalando a CLI do  {{site.data.keyword.cloud_notm}}  Independente
{: #uninstall-ibmcloud-cli}

Use as etapas a seguir para desinstalar a CLI do {{site.data.keyword.cloud_notm}} independente em plataformas específicas.
{: shortdesc}

## Desinstalando no Windows
{: #uninstall-cli-windows}

1. Clique no botão **Iniciar** e, em seguida, selecione **Painel de Controle**.
2. Na janela pop-up, clique em **Desinstalar um programa**.
3. Na lista de aplicativos pop-up, localize **IBM Cloud Command Line Interface**.
4. Clique com o botão direito em **IBM Cloud Command Line Interface** e selecione **Desinstalar**.
5. O desinstalador é iniciado. Siga as instruções para concluir a desinstalação.

## Desinstalando no Linux e no MacOS
{: #uninstall-cli-linux-macos}

As etapas de desinstalação são diferentes, dependendo da versão da CLI que está instalada.

Para determinar a versão da CLI do {{site.data.keyword.cloud_notm}}, execute:
```
ibmcloud -v
```
{: codeblock}

Para desinstalar versões anteriores à `0.9.0`, execute os comandos a seguir:
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

Limpe os scripts de conclusão automática, se os configurou. Para obter mais detalhes, veja [Ativando a conclusão automática de shell para a CLI do {{site.data.keyword.cloud_notm}} (somente Linux e Mac)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

Para desinstalar versões `0.9.0` e mais recentes, execute o comando a seguir:
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

Limpe qualquer script de conclusão automática customizada. Para obter mais detalhes, veja [Ativando a conclusão automática de shell para a CLI do {{site.data.keyword.cloud_notm}} (somente Linux e Mac)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).
