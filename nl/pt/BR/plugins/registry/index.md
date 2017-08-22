---



copyright:

  years: 2017

lastupdated: "2017-07-27"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# {{site.data.keyword.registrylong_notm}} CLI
{: #containerregcli}

O {{site.data.keyword.registrylong}} CLI é um plug-in para gerenciar seu registro e seus recursos para sua conta.
{: shortdesc}

**Pré-requisitos**
* Antes de executar os comandos de registro, efetue login no {{site.data.keyword.Bluemix_short}}
 com o comando `bx login` para gerar um token de acesso do {{site.data.keyword.Bluemix_short}}
 e autenticar sua sessão.

Para descobrir sobre como usar a CLI do {{site.data.keyword.registrylong}}, veja [Configurando um registro de imagens privado](../../../services/Registry/index.html).

<table summary="Gerenciar seu registro de contêineres">
<caption>Tabela 1. Comandos para gerenciar o {{site.data.keyword.registryshort}} no {{site.data.keyword.Bluemix_short}}
</caption>
 <thead>
 <th colspan="5">Comandos para gerenciar o registro</th>
 </thead>
 <tbody>
 <tr>
 <td>[bx cr api](#bx_cr_api)</td>
 <td>[bx cr info](#bx_cr_info)</td>
 <td>[bx cr image-inspect](#bx_cr_image_inspect)</td>
 <td>[bx cr image-list (imagens bx cr)](#bx_cr_image_list)</td>
 <td>[bx cr image-rm](#bx_cr_image_rm)</td>
 </tr>
 <tr>
 <td>[bx cr login
](#bx_cr_login)</td>
 <td>[bx cr namespace-add](#bx_cr_namespace_add)</td>
 <td>[bx cr namespace-list (namespaces bx cr)](#bx_cr_namespace_list)</td>
 <td>[bx cr namespace-rm](#bx_cr_namespace_rm)</td>
 <td>[bx cr plano](#bx_cr_plan)</td>
 </tr>
 <tr>
 <td>[bx cr plano de upgrade](#bx_cr_plan_upgrade)</td>
 <td>[bx cr pricing](#bx_cr_pricing)</td>
 <td>[bx cr cota](#bx_cr_quota)</td>
 <td>[bx cr de cota configurado](#bx_cr_quota_set)</td>
 <td>[bx cr token-add](#bx_cr_token_add)</td>
 </tr>
 <tr>
 <td>[bx cr token-get](#bx_cr_token_get)</td>
 <td>[bx cr token-list (tokens bx cr)](#bx_cr_token_list)</td>
 <td>[bx cr token-rm](#bx_cr_token_rm)</td>
 <td>[Bx cr vulnerabilidade de avaliação (que va bx)](#bx_cr_va)</td>
 </tr>
 </tbody></table>



## bx cr api
{: #bx_cr_api}

Retorna os detalhes sobre o terminal de API de registro com relação ao qual os comandos são executados.

```
bx cr api
```
{: codeblock}


## bx cr info
{: #bx_cr_info}

Exibe o nome e a conta do registro ao qual você está conectado.

```
bx cr info
```
{: codeblock}


## bx cr image-inspect
{: #bx_cr_image_inspect}

Exibe detalhes sobre uma imagem específica.

```
bx cr image-inspect [--format FORMAT] IMAGE [IMAGE...]
```
{: codeblock}

**Parâmetros**

<dl>
<dt>--format FORMAT</dt>
<dd>(Opcional) Formata os elementos de saída usando um modelo Go. 

Para obter mais informações, veja [Visualizando informações sobre as imagens](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
<dt>IMAGE</dt>
<dd>O caminho de registro completo do {{site.data.keyword.Bluemix_short}} para a imagem que você deseja inspecionar, que está no formato `namespace/image:tag`. Se uma tag não for especificada no caminho da imagem, a imagem identificada como `latest` será inspecionada. É possível inspecionar múltiplas imagens listando cada caminho de registro privado do {{site.data.keyword.Bluemix_short}} no comando com um espaço entre cada caminho.</dd>
</dl>


## bx cr image-list (imagens bx cr)
{: #bx_cr_image_list}

Exibe todas as imagens na conta do {{site.data.keyword.Bluemix_short}}.

```
 bx cr image-list [--no-trunc] [-q, --quiet] [--include-ibm] [--format FORMAT]
```
{: codeblock}

**Parâmetros**
<dl>
<dt>--no-trunc</dt>
<dd>(Opcional) Não truncar as compilações de imagem.</dd>
<dt>-q, --quiet</dt>
<dd>(Opcional) Cada imagem é listada no formato: `repository:tag`.</dd>
<dt>--include-ibm</dt>
<dd>(Opcional) Inclui imagens públicas fornecidas pela IBM na saída. Sem essa opção, somente imagens privadas serão listadas, por padrão.</dd>
<dt>--format FORMAT</dt>
<dd>(Opcional) Formata os elementos de saída usando um modelo Go. 

Para obter mais informações, veja [Visualizando informações sobre as imagens](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
</dl>


## bx cr image-rm
{: #bx_cr_image_rm}

Exclui uma ou mais imagens especificadas do seu registro.

```
bx cr image-rm IMAGE [IMAGE...]
```
{: codeblock}

**Parâmetros**
<dl>
<dt>IMAGE</dt>
<dd>O caminho de registro completo do {{site.data.keyword.Bluemix_short}} para a imagem que você deseja remover, no formato `namespace/image:tag`. Se uma tag não for especificada no caminho da imagem, a imagem identificada como `latest` será excluída por padrão. É possível excluir múltiplas imagens listando cada caminho de registro privado do {{site.data.keyword.Bluemix_short}} no comando com um espaço entre cada caminho.</dd>
</dl>


## bx cr login
{: #bx_cr_login}

Esse comando executa o comando `docker login` no registro. O comando `docker login` é necessário para poder executar os comandos `docker push` ou `docker pull` para o registro. Esse comando não é necessário para executar outros comandos `bx cr`. Se o Docker não estiver instalado, esse comando retornará uma mensagem de erro.

```
bx cr login
```
{: codeblock}


## bx cr namespace-add
{: #bx_cr_namespace_add}

Inclui um namespace em sua conta do {{site.data.keyword.Bluemix_short}}.

```
bx cr namespace-add NAMESPACE
```
{: codeblock}

**Parâmetros**
<dl>
<dt>NAMESPACE</dt>
<dd>O namespace que deseja incluir. O namespace deve ser exclusivo em todas as contas do {{site.data.keyword.Bluemix_short}} na mesma região.</dd>
</dl>


## bx cr namespace-list (namespaces bx cr)
{: #bx_cr_namespace_list}

Exibe todos os namespaces pertencentes à sua conta do {{site.data.keyword.Bluemix_short}}.

```
bx cr namespace-list
```
{: codeblock}


## bx cr namespace-rm
{: #bx_cr_namespace_rm}

Remove um namespace de sua conta do {{site.data.keyword.Bluemix_short}}. As imagens nesse namespace são excluídas quando o namespace é removido.

```
bx cr namespace-rm NAMESPACE
```
{: codeblock}

**Parâmetros**
<dl>
<dt>NAMESPACE</dt>
<dd>O namespace que deseja remover.</dd>
</dl>



## Cr bx plano
{: #bx_cr_plan}

Exibe seu plano de precificação.

```
Cr bx plano
```
{: codeblock}


## bx cr plan-upgrade
{: #bx_cr_plan_upgrade}

Faz seu upgrade do plano grátis para o padrão.

Para obter informações sobre planos, veja [Planos de registro](../../../services/Registry/registry_overview.html#registry_plans).

```
bx cr plan-upgrade standard
```
{: codeblock}


## bx cr pricing
{: #bx_cr_pricing}

Calcula o custo estimado de seu uso em dólares americanos considerando seu armazenamento livre e abonos de tráfego pull.

```
bx cr pricing --traffic VALUE --storage VALUE
```
{: codeblock}

**Parâmetros**
<dl>
<dt>-- tráfego VALUE</dt>
<dd>Especifique seu tráfego pull mensal previsto em megabytes. O tráfego deve ser especificado como um número inteiro.</dd>
<dt>-- armazenamento VALUE</dt>
<dd>Especifique seu armazenamento total médio previsto em megabytes. O armazenamento deve ser especificado como um número inteiro.</dd>
</dl>


## Cota cr bx
{: #bx_cr_quota}

Exibe suas cotas atuais para tráfego e armazenamento e informações de uso com relação a essas cotas.

```
Cota cr bx
```
{: codeblock}


## -cr bx conjunto de cota
{: #bx_cr_quota_set}

Modifique a cota especificada.

```
bx cr quota-set [--traffic VALUE] [--storage VALUE]
```
{: codeblock}

**Parâmetros**
<dl>
<dt>-- tráfego VALUE</dt>
<dd>(Opcional) Muda sua cota de tráfego para o valor especificado. A operação falhará se você não estiver autorizado a configurar o tráfego ou se configurar um valor que exceda o seu plano de precificação atual.</dd>
<dt>-- armazenamento VALUE</dt>
<dd>(Opcional) Muda sua cota de armazenamento para o valor especificado. A operação falhará se você não estiver autorizado a configurar cotas de armazenamento ou se configurar um valor que exceda o seu plano de precificação atual.</dd>
</dl>


## bx cr token-add
{: #bx_cr_token_add}

Inclui um token que pode ser usado para controlar o acesso a um registro.

```
bx cr token-add [--description VALUE] [-q, --quiet] [--non-expiring] [--readwrite]
```

{: codeblock}


**Parâmetros**
<dl>
<dt>--description VALUE</dt>
<dd>(Opcional) Especifica o valor como uma descrição para o token, que é exibida quando você executa `bx cr token-list`. Se o seu token for criado automaticamente pelo IBM Bluemix Container Service, a descrição será configurada para seu nome do Cluster do Kubernetes. Nesse caso, o token é removido automaticamente quando o cluster é removido.</dd>
<dt>-q, --quiet</dt>
<dd>(Opcional) Exibe o token somente, sem nenhum texto circundante.</dd>
<dt>--non-expiring</dt>
<dd>(Opcional) Cria um token com acesso que não expira. Sem esse conjunto de parâmetros, o acesso por meio de um token expirará após 24 horas, por padrão.</dd>
<dt>--readwrite</dt>
<dd>(Opcional) Cria um token que concede acesso de leitura e gravação. Sem essa opção, o acesso será somente leitura, por padrão.</dd>
</dl>


## bx cr token-get
{: #bx_cr_token_get}

Recuperar o token especificado do registro.

```
bx cr token-get TOKEN
```

{: codeblock}

**Parâmetros**
<dl>
<dt>TOKEN</dt>
<dd>(Opcional) O identificador exclusivo do token que você deseja recuperar.</dd>
</dl>


## bx cr token-list (tokens bx cr)
{: #bx_cr_token_list}

Exibe todos os tokens que existem para sua conta do {{site.data.keyword.Bluemix_short}}.

```
bx cr token-list --format FORMAT
```
{: codeblock}

**Parâmetros**
<dl>
<dt>--format FORMAT</dt>
<dd>(Opcional) Formata os elementos de saída usando um modelo Go. 

Para obter mais informações, veja [Visualizando informações sobre as imagens](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
</dl>

## bx cr token-rm
{: #bx_cr_token_rm}

Remover um ou mais tokens especificados.

```
bx cr token-rm TOKEN [TOKEN...]
```
{: codeblock}

**Parâmetros**
<dl>
<dt>TOKEN</dt>
<dd>(Opcional) TOKEN pode ser o próprio token ou o identificador exclusivo do token, conforme mostrado em `bx cr token-list`. É possível especificar múltiplos tokens e devem ser separados por um espaço.</dd>
</dl>


## Bx cr vulnerabilidade de avaliação (que va bx)
{: #bx_cr_va}

Visualize um relatório de avaliação de vulnerabilidade para uma imagem.

```
Bx cr vulnerabilidade de avaliação IMAGEM [ IMAGEM ... ]
```
{: codeblock}

**Parâmetros**
<dl>
<dt>IMAGE</dt>
<dd>O caminho de registro integral do {{site.data.keyword.Bluemix_short}}, no formato `namespace/image:tag`, para a imagem para a qual você deseja obter um relatório. O relatório indica se a imagem em quaisquer vulnerabilidades de pacote conhecidas. Os seguintes sistemas operacionais são suportados:

<ul>

<li>Alpine</li>
<li>CentOS</li>
<li>Debian</li>
<li>Red Hat Enterprise Linux (RHEL)</li>
<li>Ubuntu</li>
</ul>

Para obter mais informações, veja [Revisando a segurança da imagem](../../../services/Registry/registry_images_.html#registry_security_checking).

</dd>

</dl>

