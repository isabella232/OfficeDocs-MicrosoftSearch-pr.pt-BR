---
title: Visão geral dos conectores
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Visão geral dos conectores do Microsoft Graph para o Microsoft Search
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367519"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Visão geral dos conectores do Microsoft Graph

O [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexa todos os seus dados do [Microsoft 365](https://www.microsoft.com/microsoft-365) para torná-los pesquisáveis para os usuários. Com os conectores do Microsoft Graph, sua organização pode indexar dados de terceiros para que apareçam nos resultados da pesquisa da Microsoft. Isso expande os tipos de fontes de conteúdo que podem ser pesquisadas nos seus aplicativos de produtividade do Microsoft 365 e no ecossistema mais amplo da Microsoft. Os dados de terceiros podem ser hospedados no local ou nas nuvens públicas ou privadas.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

O restante deste artigo destina-se a ajudar os administradores da Microsoft 365 a localizar os recursos que estão disponível para responder às seguintes perguntas:

* [Quais fontes de dados podem ser conectadas à pesquisa da Microsoft?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Como gerenciar minhas conexões?](#how-do-i-manage-my-connections)
* [Quais são os requisitos de licença e os termos de uso para conectores do Graph?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [Como personalizar e configurar os resultados da pesquisa?](#how-do-i-customize-and-configure-search-results)
* [Como pesquisar dados do meu conector de um aplicativo personalizado?](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> Agora, os conectores do Microsoft Graph e as APIs de pesquisa da Microsoft estão disponíveis. As primeiras distribuições serão para os clientes configurados para lançamento direcionado. Se você quiser usar um conector de gráfico em seu locatário, os usuários e os administradores deverão optar pelo [lançamento direcionado](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Quais fontes de dados podem ser conectadas à pesquisa da Microsoft?

A Microsoft fornece dez conectores de gráfico e nossos parceiros de ecossistema criaram mais de 100 conectores de gráficos adicionais. Você também pode criar seu próprio conector de Graph. 

### <a name="graph-connectors-by-microsoft"></a>Conectores do Graph pela Microsoft

Você pode se conectar às fontes de dados a seguir usando os conectores do Graph criados pela Microsoft:

<!---Need to add a few links below when docs exist--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* Azure SQL
* [Sites empresariais](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [Compartilhamento de arquivos](fileshare-connector.md)
* Oracle (versão prévia)
* [Salesforce (visualização)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

A [Galeria de conectores do Graph](connectors-gallery.md) contém uma breve descrição de cada um desses conectores gráficos. Se você estiver pronto para conectar uma dessas fontes de dados ao seu locatário, leia a [visão geral da instalação](configure-connector.md) e outros artigos na seção conectores de instalação pela Microsoft que se aplicam à sua fonte de dados.

### <a name="graph-connectors-by-our-partners"></a>Conectores do Graph por nossos parceiros

A [Galeria de conectores do Microsoft Graph](connectors-gallery.md) inclui uma breve descrição de cada um dos conectores de gráficos criados por nossos parceiros e um link para o site de cada parceiro. Entre em contato diretamente com cada parceiro para saber mais.

### <a name="build-your-own-graph-connector"></a>Criar seu próprio conector de gráfico

Se você planeja Compilar seu próprio conector de gráfico, confira a [visão geral da API de pesquisa da Microsoft no Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) para obter mais informações.

## <a name="how-do-i-manage-my-connections"></a>Como gerenciar minhas conexões?

Você pode gerenciar suas conexões na [guia conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) do [centro de administração do Microsoft 365](https://admin.microsoft.com/). Confira [gerenciar suas conexões](manage-connector.md) para obter mais informações.

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Quais são os requisitos de licença e os termos de uso para conectores do Graph?

Você precisa de uma licença válida do Microsoft 365 ou do Office 365 e uma cota de conectores de gráfico suficiente para que os usuários em sua organização exibam dados de conectores em seus resultados de pesquisa.

Para saber mais, veja [requisitos de licença e preços](licensing.md) e [termos de uso](terms-of-use.md).

## <a name="how-do-i-customize-and-configure-search-results"></a>Como personalizar e configurar os resultados da pesquisa?

Há várias maneiras de personalizar e configurar os resultados da pesquisa. Consulte os seguintes artigos para saber mais:

* [Gerenciar verticais e tipos de resultados](customize-search-page.md)
* [Gerenciar layouts de resultados de pesquisa](customize-results-layout.md)
* [Gerenciar o cluster de resultados](result-cluster.md)
* [Gerenciar filtros personalizados](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Como pesquisar dados do meu conector de um aplicativo personalizado?

Após a indexação dos dados personalizados, os desenvolvedores podem [consultar esses dados](https://docs.microsoft.com/graph/search-concept-custom-types). Você pode exibir seus dados em qualquer aplicativo. Para obter mais informações, consulte a [visão geral da API de pesquisa da Microsoft no Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).
