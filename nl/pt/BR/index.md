---



copyright:

  years: 2015, 2017

lastupdated: "2017-06-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Instalação manual da CLI
{: #cli}

A CLI do {{site.data.keyword.Bluemix}} fornece uma experiência de linha de comandos para gerenciar seu ambiente {{site.data.keyword.Bluemix_notm}}. Ela também inclui uma interface da linha de comandos do Cloud Foundry, cf, em sua instalação, para gerenciar aplicativos e serviços do Cloud Foundry.
{:shortdesc}

Ambas as ferramentas da CLI usam a porta 443 por padrão. Se você tiver o proxy HTTP entre as ferramentas da CLI e o ambiente do {{site.data.keyword.Bluemix_notm}}, deverá configurar a variável de ambiente `HTTP_PROXY` com a URL real do proxy HTTP e a porta, se houver uma. Veja [Usando a CLI com um Servidor proxy HTTP ![Ícone de link externo](../icons/launch-glyph.svg)](http://docs.cloudfoundry.org/cf-cli/http-proxy.html){: new_window} para obter mais detalhes.

[Fazer download da CLI do {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/bluemix_cli/all_versions.html){: new_window} 

Se você estiver no macOS, a maneira mais fácil de iniciar a utilização das ferramentas do IBM Cloud será usando o [IBM Cloud Application Tools 2](/docs/cli/icat.html).
{: tip}

## ![](./images/CLI_Plugin.svg) Plug-ins da interface de linha de comandos
{: #cliplugins notoc}

Estenda facilmente sua interface de linha de comandos do {{site.data.keyword.Bluemix_notm}} com mais comandos. Para acessar os plug-ins da interface da linha de comandos do {{site.data.keyword.Bluemix_notm}}, veja o [Repositório de plug-in da CLI ![Ícone de link externo](../icons/launch-glyph.svg)](https://plugins.ng.bluemix.net/){: new_window}.

### Ampliar sua interface da linha de comandos do {{site.data.keyword.Bluemix_notm}}: bx
{: #cli_bluemix_ext notoc}


Depois de instalar a ferramenta cli do {{site.data.keyword.Bluemix_notm}}, o [Repositório de plug-in da CLI ![Ícone de link externo](../icons/launch-glyph.svg)](https://plugins.ng.bluemix.net/){: new_window} é pré-configurado com um alias de repositório `Bluemix` por padrão. É possível instalar plug-ins disponíveis diretamente.

```
bluemix plugin install plugin_name -r Bluemix
```

| *CLI do {{site.data.keyword.autoscaling}}* |  *IBM Bluemix Container Service*  |
|-----|-----|-----|
| Plug-in name: auto-scaling <br> [Visualizar docs](/docs/cli/plugins/auto-scaling/index.html) |  Plug-in name: container-service  <br> [Visualizar docs](/docs/containers/cs_cli_devtools.html) |
{: caption="Tabela 2. Plug-ins" caption-side="top"}

|  *Peer de rede privada* | *Esquemático* | *VPN*  |
|-----|-----|-----|
| Nome do plug-in:
private-network-peering  <br> [Visualizar docs](/docs/cli/plugins/pnp/index.html) | Nome do Plug-in: Esquema  <br> [Visualizar docs](/docs/services/schematics/schematics_reference.html) | Plug-in name: VPN  <br> [Visualizar docs](/docs/cli/plugins/bx_vpn/index.html) |
{: caption="Tabela 3. Plug-ins" caption-side="top"}

Também é possível incluir plug-ins de outros repositórios que obedeçam à arquitetura de cli do {{site.data.keyword.Bluemix_notm}}.
1. Para instalar plug-ins da CLI do {{site.data.keyword.Bluemix_notm}} de outro repositório, configure o terminal de registro de plug-in:
```
bluemix plugin repo-add bluemix-other-repo [repo_url]
```
em que `repo_url` é a URL de HTTPS do repositório de plug-in.

2. Execute o comando a seguir para instalar um
plug-in:
```
bluemix plugin install plugin_name -r bluemix-other-repo
```

### Ampliar a interface da linha de comandos do Cloud Foundry: bx cf
{: #cli_cf_ext notoc}

Depois de instalar a interface da linha de comandos do {{site.data.keyword.Bluemix_notm}}, uma interface da linha de comandos do Cloud Foundry também será instalada dentro do diretório da CLI do {{site.data.keyword.Bluemix_notm}}. Execute os comandos da CLI do Cloud Foundry usando `bluemix cf`.

* Para instalar plug-ins da CLI cf a partir do registro do {{site.data.keyword.Bluemix_notm}}, configure o terminal de registro de plug-in:

```
bluemix cf add-plugin-repo bluemix-cf-repo https://plugins.ng.bluemix.net
```
{: codeblock}

* Em seguida, execute o comando a seguir para instalar um plug-in:

```
bluemix cf install-plugin plugin_name -r bluemix-cf-repo
```
{: codeblock}

| *Console do administrador* |
-----------------|
|  Plug-in name: bluemix-admin <br> [Visualizar docs](/docs/cli/plugins/bluemix_admin/index.html) |
{: caption="Tabela 4. Plug-ins" caption-side="top"}

| *{{site.data.keyword.IBM}} Containers for {{site.data.keyword.Bluemix_notm}}* | *VPN* |
|-----------------|-----------------|
| Plug-in name: ibm-containers <br> [Visualizar docs ![Ícone de link externo](../icons/launch-glyph.svg)](https://www.{DomainName}/docs/containers/container_cli_cfic.html#container_cli_cfic){: new_window} | Plug-in name: VPN <br> [Visualizar docs](/docs/cli/plugins/vpn/index.html) |
{: caption="Tabela 5. Plug-ins" caption-side="top"}

## ![](./images/Integrated_Dev_Tools.svg) Ferramentas de desenvolvimento integradas
{: #ide notoc}

Faça download e instale os plug-ins para integrar seus serviços do {{site.data.keyword.Bluemix_notm}} favoritos.

| *Liberty for Java* | *MobileFirst* | *{{site.data.keyword.rules_short}}* | *API Connect* | *Eclipse Tools for Bluemix* |
|----------|----------|----------|----------|----------|
| [Plug-in do Eclipse do Liberty ![Ícone de link externo](../icons/launch-glyph.svg)](https://developer.ibm.com/wasdev/downloads/liberty-profile-using-eclipse/){: new_window} | [Plug-in do Eclipse ![Ícone de link externo](../icons/launch-glyph.svg)](https://marketplace.eclipse.org/content/ibm-mobilefirst-platform-studio){: new_window} | [Plug-in do Eclipse do Rules Designer](../services/rules/index.html#rulov002) | [Developer Toolkit](/docs/services/apiconnect/apic_003.html#apic_001 ) | [Plug-in do Eclipse do Bluemix](/docs/manageapps/eclipsetools/eclipsetools.html) |
{: caption="Tabela 6. Plug-ins" caption-side="top"}
