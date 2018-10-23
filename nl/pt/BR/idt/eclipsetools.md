---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-18"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Implementando apps com o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}
{: #deploying-apps-with-ibm-eclipse-tools-for-ibm-cloud}

O IBM® Eclipse Tools for {{site.data.keyword.Bluemix}} fornece os plug-ins que podem ser instalados em um ambiente Eclipse existente para ajudar a integrar o ambiente de desenvolvimento integrado (IDE) do desenvolvedor ao Bluemix®. As ferramentas permitem implementar os arquivos JavaScript, WAR (archive web) e EAR (archive corporativo) e os servidores de pacote do perfil Liberty no servidor Cloud direto do Eclipse IDE ou do WebSphere® Application Server Developer Tools (WDT). As ferramentas também permitem que você crie
e vincule serviços para seu aplicativo e defina variáveis de ambiente
como parte da implementação.

Se o aplicativo já estiver em execução no Eclipse usando o Websphere Application Developer Tools com o perfil Liberty, será possível instalar essas ferramentas sobre o programa em execução. É possível implementar os aplicativos por meio da inclusão do aplicativo no servidor Cloud no ambiente de trabalho.  Graças aos recursos exclusivos do buildpack do Liberty para o suporte do servidor em pacote, também há uma opção para implementar o servidor inteiro do perfil Liberty no Cloud. Também é possível implementar os aplicativos JavaScript Node.js
no Cloud.

## Instalando o Eclipse Tools

Aprenda a instalar o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. Um ambiente de execução Java™ 1.7 ou mais recente é necessário.

Há várias maneiras de instalar o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, incluindo:
* Instalando a partir do Marketplace.
* Instalando a partir do WASDev.
* Fazendo download do instalador do IBM WebSphere Application Server Developer Tools (WDT).

### Instalando a partir do Marketplace

A instalação requer o [Eclipse Oxygen for Java EE Developers (4.7)](https://www.eclipse.org/downloads/packages/release/oxygen/r/eclipse-ide-java-developers) ou o [Eclipse Neon for Java EE Developers (4.6)](http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers).

Em seguida, siga as instruções aqui:
[https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help](https://marketplace.eclipse.org/content/ibm-eclipse-tools-ibm-cloud/help).

### Instalando a partir do WASDev

1. Abra a página
[Download](https://developer.ibm.com/wasdev/downloads/)
no WASDev.
2. Arraste o ícone `Instalar` para a barra de ferramentas no Eclipse.
3. Por padrão, existem recursos selecionados. Clique em **Confirmar**.
4. Aceite o contrato de licença e clique em **Concluir**.

### Fazendo download do instalador do IBM WebSphere Application Server Developer Tools (WDT)

1. Abra **Ajuda > Instalar o software WebSphere**. Procure por Cloud
2. Selecione a entrada `IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}` e clique em
**Instalar**.
3. Por padrão, existem recursos selecionados. Clique em **Confirmar**.
4. Aceite o contrato de licença e clique em **Concluir**.

## Suporte ao servidor em pacote

Com o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, há múltiplos cenários para enviar por
push um servidor Liberty ou um servidor em pacote para o Cloud e confirmar a implementação.

* Crie o servidor Cloud.
* Crie um servidor Liberty Profile com um arquivo WAR ou EAR.
* Pare o servidor.

Usando o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} para o suporte ao servidor em pacote, há
múltiplos cenários para:

* Enviar por push um servidor Liberty para o Cloud.
* Enviar por push um servidor em pacote Liberty para o Cloud.
* Confirmar a implementação bem-sucedida do aplicativo com teste.

Além disso, é possível importar os arquivos compactados do servidor em pacote para qualquer projeto na área de
trabalho.

### Cenário 1: incluindo um servidor Liberty interrompido no Cloud e testando um aplicativo

1. Clique com o botão direito no servidor `Cloud` na visualização Servidores.
2. Selecione **Incluir e remover**.
3. Na caixa de diálogo, as instâncias do servidor Liberty são mostradas. Selecione
uma e clique em **Incluir**.
4. Clique em **Concluir**.
5. No Diálogo do aplicativo, o nome padrão é derivado
da instância do Liberty Server. É possível alterar esse nome, mas ele
não deve conter espaços ou caracteres especiais. O padrão é aceitável se ele não entrar em conflito com o nome dos
aplicativos existentes no servidor Cloud.
6. Clique em **Concluir** e, em seguida, aguarde até que o aplicativo publique no Cloud.
7. Clique com o botão direito no módulo do servidor Liberty incluído no servidor Cloud. Selecione **Abrir página inicial**. A URL raiz do servidor em pacote é aberta em seu navegador da web
padrão. Use essa URL raiz como base para construir a URL de teste dentro dos aplicativos WAR
e EAR em pacote.

### Cenário 2: arraste e solte no Cloud um servidor Liberty interrompido

O Cenário 1 descreveu como é possível incluir e remover módulos
Liberty Server. Isso pode ser simplificado com uma função arrastar e soltar.

1. Se continuar do Cenário 1, remova o módulo do servidor Liberty do servidor Cloud.
2. Selecione e arraste a instância interrompida do servidor Liberty e solte-a no servidor Cloud na
visualização Servidores. A janela Diálogo
do aplicativo aparece.
3. Siga as etapas de 5 a 10 do Cenário 1.

### Cenário 3: execute um servidor em pacote para o Cloud

O menu de contexto da instância de serviço do perfil Liberty inclui uma ação do servidor de pacote. Essa ação
empacota o servidor em um archive. No Cloud, uma nova ação foi incluída para empacotar o servidor em um arquivo
compactado e implementá-lo no IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

1. Se continuar do Cenário 1 ou 2 remova o módulo do servidor Liberty do servidor Cloud.
2. Clique com o botão direito na instância do servidor Liberty Profile na
visualização Servidores.
3. No menu Utilitários, selecione **Servidor de pacote para o {{site.data.keyword.Bluemix_notm}}**.
4. Na caixa de diálogo, escolha o servidor Cloud no qual deseja implementar o aplicativo.
5. Clique em **OK**. A janela Diálogo
do aplicativo aparece.
6. Siga as etapas de 5 a 10 do Cenário 1.
7. Se uma janela de diálogo de progresso for exibida, escolha **Executar em
segundo plano** e aguarde até que o aplicativo seja implementado.

### Cenário 4 - Trabalhando com arquivos compactados do Servidor em Pacote - Executar no servidor

Os cenários anteriores descrevem como trabalhar com as instâncias existentes do servidor Liberty na
visualização Servidores e como é possível implementá-las no Cloud. Também é possível implementar no Cloud os arquivos
compactados do servidor em pacote existentes.

1. Crie ou obtenha um arquivo compactado do servidor em pacote.
2. Importe o arquivo compactado para qualquer projeto na área de trabalho.
3. Clique com o botão direito no arquivo compactado e selecione **Executar como > Executar no servidor**. A janela de diálogo
Executar no servidor aparece.
4. Selecione um servidor Cloud.
5. Clique em **Concluir**. A janela Diálogo
do aplicativo aparece.
6. Siga as etapas de 5 a 10 do Cenário 1. O nome do módulo
é derivado do arquivo compactado.

### Cenário 5 - Trabalhando com arquivos compactados do Servidor em Pacote - Arrastar e soltar

1. Selecione e arraste o arquivo compactado do servidor em pacote e, em seguida, solte-o no servidor Cloud na
visualização Servidores. A janela de diálogo do aplicativo
aparece.
2. Siga as etapas de 5 a 10 do Cenário 1. O nome do módulo
é derivado do nome do arquivo compactado.

## Enviando por push um arquivo EAR

Use o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} para enviar por push um EAR para o Cloud.

Defina um novo servidor.

1. Para criar um novo servidor Cloud, selecione **Arquivo > Novo > Outro**.
2. Selecione **Servidor** na categoria Servidor e, em seguida, clique em **Avançar**.
3. Em IBM, localize o Cloud.
4. Clique em **Avançar**.
5. Insira as informações da conta do Cloud. Clique em
**Inscrever** se você não tiver uma conta.
6. Clique em **Avançar**.
7. Escolha suas Organizações e Espaços. O padrão é `dev`.
8. Clique em **Avançar**.
9. Clique em **Concluir**.

Importar um arquivo EAR

1. Clique com o botão direito e selecione **Importar**.
2. Procure por arquivo EAR.
3. Procure o arquivo EAR que você deseja importar.
4. Assegure-se de que o tempo de execução de destino esteja configurado como {{site.data.keyword.Bluemix_notm}} Runtime.

Implemente seu aplicativo.

1. Clique com o botão direito no servidor Cloud iniciado. Escolha **Incluir e Remover**.
2. Escolha o EAR e clique em **Incluir**.
3. Clique em **Concluir**. A
janela Detalhes do aplicativo é aberta.
4. Nomeie o aplicativo e, em seguida, clique em **Avançar**. Um nome válido pode conter de A a Z, de 0 a 9, - e _. Ele não pode conter espaços ou outros caracteres especiais. As informações de Ativar implementação são configuradas por padrão.
5. Clique em **Avançar**.
6. Se necessário, selecione serviços. Clique em **Avançar**.
7. Se necessário, inclua variáveis. Clique em **Concluir**.
8. Depois que o aplicativo for enviado por push, clique com o botão direito no projeto
e escolha **Abrir página inicial**.
9. Inclua o nome do módulo da web e o nome do aplicativo na
URL.
10. Para salvar as configurações e as  variáveis que você especificou,
marque a caixa de seleção **Salvar no arquivo manifest**
na janela Detalhes do aplicativo.

## Implementando um aplicativo Node.js
Use o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} para implementar um projeto Node.js novo ou existente no Cloud, configurar os detalhes de implementação do aplicativo e verificar os resultados em um navegador.

Se você ainda não tiver um aplicativo Node.js existente, inicie com a Etapa 1. Se você já tiver um aplicativo
Node.js existente, inicie com a Etapa 7.

1. Selecione **Arquivo > Novo > Projeto**.
2. Selecione **Projeto JavaScript** na categoria JavaScript.
3. Clique em **Avançar**.
4. Nomeie o projeto.
5. Clique em **Concluir**.

Defina um novo servidor.

1. Para criar um novo servidor Cloud, selecione **Arquivo > Novo > Outro**.
2. Selecione **Servidor** na categoria Servidor e, em seguida, clique em **Avançar**.
3. Em IBM, localize o Cloud.
4. Clique em **Avançar**.
5. Insira as informações da conta do Cloud. Clique em
**Inscrever** se você não tiver uma conta.
6. Clique em **Avançar**.
7. Escolha suas Organizações e Espaços. O padrão é `dev`.
8. Clique em **Avançar**.
9. Clique em **Concluir**.

Ative o aplicativo para publicação no Cloud

1. Clique com o botão direito no Explorador de Projetos e escolha **Propriedades > Aspecto do projeto**.
2. Clique em **Converter em formato mascarado**.
3. Em Aspectos do projeto, selecione **Aplicativo Node.js**.
4. Clique em **OK**.

Implemente seu aplicativo.

1. Clique com o botão direito no servidor Cloud iniciado. Escolha **Incluir e Remover**.
2. Escolha o projeto e clique em **Incluir**.
3. Clique em **Concluir**. A
janela Detalhes do aplicativo é aberta.
4. Para salvar a configuração de implementação para o arquivo manifest do aplicativo, marque a caixa de seleção
**Salvar para o arquivo manifest** na janela Detalhes do aplicativo.
5. Nomeie o aplicativo e, em seguida, clique em **Avançar**. Um nome válido pode conter de A a Z, de 0 a 9, - e _. Ele não pode conter espaços
ou outros caracteres especiais.
6. Aceite os padrões no painel de informações Ativar implementação.
7. Clique em **Avançar**.
8. Se necessário, selecione serviços. Clique em **Avançar**.
9. Se necessário, inclua variáveis. Clique em **Concluir**.
10. Depois que o aplicativo for enviado por push, clique com o botão direito no projeto
e escolha **Abrir página inicial**.

## Publicação incremental

É possível atualizar os arquivos de aplicativo de modo incremental sem
precisar enviar por push novamente todo o aplicativo.
Com a publicação incremental você não precisa executar uma reimplementação
completa para cada mudança, economizando tempo em todo o processo de
desenvolvimento.

Esse recurso suporta aplicativos da Web (WAR e EAR) e
servidores em pacotes.

Para usar a publicação incremental, o [Modo de desenvolvimento](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) deve ser ativado para o aplicativo ou o servidor em pacote.

1. Inclua um aplicativo ou um servidor em pacote no Cloud, a menos que exista um.
**Nota:** essa função não poderá ser ativada se o nome da implementação do aplicativo tiver um sublinhado.

2. Ative o modo de desenvolvimento clicando com o botão direito do mouse no aplicativo
ou servidor em pacote e selecionando **Ativar o modo de desenvolvimento**.

Depois que o modo de desenvolvimento for ativado, use a função de
publicação incremental:

1. Modifique o aplicativo conforme desejado.
   **Nota:** para os servidores em pacote, as modificações na configuração não são suportadas.

2. Salve as mudanças.

3. Clique com o botão direito no servidor Cloud e selecione **Publicar**.

Modos em cache: depois de reiniciar o ambiente de trabalho, se o aplicativo estava no modo de desenvolvimento ou no modo de depuração, você verá uma janela de progresso que diz, "Recuperando os estados de desenvolvimento e de depuração". Portanto, após a conclusão do progresso, o modo de desenvolvimento e o modo de depuração são atualizados.

## Depuração remota

Execute a depuração remota com relação a um aplicativo Liberty ou Node.js.

O [Modo de desenvolvimento](https://console.bluemix.net/docs/cli/plugins/dev_mode/index.html) deve ser ativado para executar a depuração. Esse modo
é executado automaticamente ao selecionar Ativar depuração do aplicativo.

### Ativar depuração do archive corporativo (EAR), do archive web (WAR) ou do servidor Liberty

Atualmente, uma porta local livre é gerada aleatoriamente, mas se o firewall de um cliente a bloquear, o cenário de depuração falhará. Para contornar isso, inicie o modo de desenvolvimento, localize o arquivo bluemixcache.xml e inclua port="#", em que o # é o número da porta da máquina local.

1. No servidor Cloud, clique com o botão direito no aplicativo que deseja depurar.

   **Nota:** essa função não poderá ser ativada se o nome da implementação do aplicativo tiver um sublinhado. Altere o nome
antes de ativar a depuração remota.

2. Clique em **Ativar depuração do aplicativo**.

   A visualização Progresso mostra o status de `Estabelecendo a sessão de depuração para <AppName>``.

   O aplicativo mostra que ele está `Desenvolvendo, Depurando <AppName>`.

   O depurador está em execução e pronto para uso.

### Desativar a depuração do EAR, do WAR ou do servidor Liberty

É possível desativar o processo de depuração e deixar o modo de desenvolvimento ativado.

1. Clique com o botão direito do mouse no aplicativo.
2. Clique em **Desativar depuração do aplicativo**.
3. Uma caixa de diálogo pergunta se você também deseja desativar o modo de desenvolvimento. Clique em
**Sim** ou em **Não**.

Se o modo de desenvolvimento permanecer em execução, o aplicativo mostrará que ele está `Desenvolvendo <AppName>``.

 Se ambos forem desativados, o aplicativo mostrará que ele é `Implementado como <AppName>`.

### Ativar a depuração dos aplicativos Node.js

**Nota:** antes de concluir as etapas a seguir, assegure-se de que você tenha um aplicativo JavaScript existente que seja implementado para o Cloud. Consulte as etapas anteriores para obter mais informações sobre
a implementação de um aplicativo JavaScript.

1. Na visualização Servidores, clique com o botão direito no aplicativo Node.js e selecione **Abrir** Depurador JavaScript. Uma caixa de diálogo é exibida perguntando se você deseja aumentar o limite de memória do aplicativo.
2. Clique em Sim. A ativação da Depuração JavaScript aumenta os requisitos de memória do aplicativo e ele reinicia mais rapidamente com a atualização do limite de memória.
3. Selecione uma instalação de navegador a ser usada para a depuração. O Google Chrome é o único navegador suportado. Se o Google Chrome não for uma opção disponível, selecione o link **Gerenciar...** e inclua um link para uma instalação local do Google Chrome.
4. Clique em **OK**. Um monitor de progresso indicando Atualizando (o seu app) para o modo de depuração é exibido. Quando a depuração for ativada, o Google Chrome abrirá o site correto.
5. Faça a autenticação no Google Chrome com o nome de login e a senha. Após uma autenticação bem-sucedida, o console
de depuração é aberto. Agora é possível depurar o aplicativo.

Modos em cache: depois de reiniciar o ambiente de trabalho, se o aplicativo estava no modo de desenvolvimento ou no modo de depuração, você verá uma janela de progresso que diz: Recuperando os estados de desenvolvimento e de depuração. Após a conclusão do progresso, o modo de desenvolvimento e o modo de depuração são atualizados.

## Conectando-se a um servidor Liberty remoto

Saiba como usar o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} para se conectar a um servidor Liberty remoto. É possível se conectar a um servidor Liberty remoto que executa o WebSphere Application Server como um serviço.

Para se conectar a um servidor Liberty remoto, o Liberty Tools deve ser instalado. Também é necessário criar um serviço do WebSphere Application Server no Cloud.

1. Clique com o botão direito no servidor Cloud e selecione **Configurar os servidores remotos...**.

   Essa opção estará disponível somente se o Liberty Tools estiver instalado.

2. Selecione um serviço do WebSphere Application Server.

   Se você não tiver um serviço do WebSphere Application Server, uma mensagem de erro poderá ser recebida. Deve-se criar um serviço do WebSphere Application Server no Cloud antes de poder concluir essa configuração.

3. Para definir um ambiente de tempo de execução, selecione **Configurar ambientes de tempo de execução...**.

   **Nota:** se você criou anteriormente um ambiente de tempo de execução, será possível ignorar essa etapa.

4. Clique em **Avançar**.

5. Insira as informações de conexão do servidor.

6. Clique em **Concluir**.

Você se conectou a um servidor Liberty remoto usando o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}.

## Ativando o Cloud Foundry Diego em aplicativos Cloud

Ative a função de arquitetura Diego por meio do IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}. Para ativar o Diego, é necessário um servidor Cloud que esteja definido na visualização Servidores.

O Diego é uma nova arquitetura do Cloud Foundry que as instâncias do Cloud Foundry usam para gerenciar os contêineres de aplicativo em execução. A arquitetura Diego substitui a arquitetura Droplet Execution Agents (DEA) que o Cloud Foundry usava anteriormente. As instalações do Cloud Foundry são movidas para o Diego e os aplicativos do usuário alternam para a nova arquitetura de forma automática e transparente.

O IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} suporta o Diego e o DEA. É possível publicar os aplicativos, ativar a publicação de aplicativo incremental e depurar os aplicativos. O Diego também permite que o IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} crie túneis de shell seguro (SSH) em aplicativos Cloud implementados, o que permite conexões mais rápidas e mais confiáveis para os aplicativos Cloud durante a depurando. Também é possível ativar o SSH para que seja possível criar os seus próprios túneis para acessar os recursos de aplicativo.

Conclua as etapas a seguir para usar a arquitetura Diego para os aplicativos antes que o Cloud alterne para implementar com o Diego por padrão:

1. Clique com o botão direito no aplicativo implementado na visualização Servidores.
2. Se o Diego for suportado no servidor Cloud e o aplicativo ainda não estiver implementado com o Diego, selecione **Ativar o Diego** no menu.
3. Se o servidor suportar o tunelamento SSH, o programa perguntará se você deseja ativar o SSH para o aplicativo. Os túneis SSH são um mecanismo mais confiável para a comunicação com o aplicativo. No entanto, se você selecionar **Não**, as funções no IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} continuarão a funcionar usando um mecanismo que não requer o tunelamento SSH.

O aplicativo, então, é reimplementado usando a arquitetura Diego.

## Criando um servidor com o Cloud Enterprise Federation

O IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}} suporta o Cloud Enterprise Federation, um serviço de conexão única que permite que os usuários acessem os serviços de nuvem com segurança. Com o Cloud Enterprise Federation, é possível ativar uma autenticação de terceiro customizada que é fornecida por sua própria organização, sem a autenticação de login padrão, para que os outros usuários acessem os aplicativos com segurança.

O Cloud Enterprise Federation autentica um conjunto de usuários para acessar os serviços de nuvem. Depois de ativar o Cloud Enterprise Federation, os usuários recebem a autenticação para os aplicativos ativados para nuvem por meio da opção de conexão única. Os usuários devem selecionar a opção de conexão única para criar um servidor no ambiente de trabalho do Eclipse e efetuar login com o login e a senha da organização. Depois de ativar o Cloud Enterprise Federation, o ID do usuário e a senha tradicionais do Cloud no Eclipse Tools não são mais usados para autenticar os usuários.

1. No IBM Eclipse Tools for {{site.data.keyword.Bluemix_notm}}, selecione **Arquivo > Novo > Outro...**.
2. Selecione **Servidor > Servidor > Avançar**.
3. Na árvore, selecione ** IBM > {{site.data.keyword.Bluemix_notm}} > Avançar**.
4. Marque a caixa de seleção **Usar uma senha descartável para efetuar login (SSO)**.
5. Um hyperlink aparece no diálogo de login. Clique no hyperlink para abrir a página de autenticação do Cloud.
6. Insira o endereço de e-mail e a senha desejados.
7. Após um login bem-sucedido, uma senha descartável é fornecida. Copie essa senha no campo Senha: do diálogo Novo servidor do Eclipse Tools for Cloud.
8. Clique em **Concluir**.

Uma entrada do servidor Cloud é listada na visualização Servidores com o status do servidor Conectado.
