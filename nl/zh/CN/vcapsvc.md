---



copyright:

  years: 2015，2017

lastupdated: "2016-03-15"


---

{:shortdesc: .shortdesc}

# VCAP 服务
{: #vcap_services}


VCAP_SERVICES 环境变量是一个 JSON 对象，包含可用于与 {{site.data.keyword.Bluemix_notm}} 中的服务实例进行交互的信息。
{:shortdesc}


## 检索 VCAP_SERVICES 环境变量的值
{:retrieving}

VCAP_SERVICES 环境变量是一个 JSON 对象，包含可用于与 {{site.data.keyword.Bluemix_notm}} 中的服务实例进行交互的信息。这些信息包括服务实例名称、凭证以及服务实例的连接 URL。这些值会在应用程序绑定到 {{site.data.keyword.Bluemix_notm}} 中的服务实例时填充到 VCAP_SERVICES 环境变量中。

只有在将服务实例绑定到应用程序时，VCAP_SERVICES 环境变量的值才可用。您可以使用以下命令来查看应用程序环境变量：

```
cf env APP_NAME
```
