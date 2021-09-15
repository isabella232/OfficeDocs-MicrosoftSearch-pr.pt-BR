---
title: Visão geral Graph conectores da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Visão geral dos conectores Graph microsoft para Pesquisa da Microsoft
ms.openlocfilehash: 006ab3f56eb4976b44904e5191ae8fd256c8d5de
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375633"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Visão geral dos conectores do Microsoft Graph

[Pesquisa da Microsoft](./overview-microsoft-search.md) indexa todos os dados [Microsoft 365](https://www.microsoft.com/microsoft-365) para torná-los pesquisáveis para usuários. Com os conectores Graph Microsoft, sua organização pode indexar dados de terceiros para que apareçam em Pesquisa da Microsoft resultados. Esse recurso expande os tipos de fontes de conteúdo que podem ser pesquisadas nos aplicativos de produtividade do Microsoft 365 e no ecossistema da Microsoft mais amplo. Os dados de terceiros podem ser hospedados no local ou nas nuvens públicas ou privadas.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Este artigo destina-se a ajudar Microsoft 365 os administradores localizarem os recursos disponíveis para responder às seguintes perguntas:

* [Quais fontes de dados podem ser conectadas Pesquisa da Microsoft?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Como faço para gerenciar minhas conexões?](#how-do-i-manage-my-connections)
* [Quais são os requisitos de licença e os termos de uso para conectores Graph Microsoft?](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [Quais são os recursos de visualização?](#what-are-the-preview-features)
* [Como personalizar e configurar os resultados da pesquisa?](#how-do-i-customize-and-configure-search-results)
* [Como faço para pesquisar dados do meu conector de um aplicativo personalizado?](#how-do-i-search-my-connector-data-from-a-custom-application)
* [Como personalizar os resultados da pesquisa?](#how-do-i-customize-search-results)
* [Quais são as limitações do conector](#what-are-the-connector-limitations)

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Quais fontes de dados podem ser conectadas Pesquisa da Microsoft?

A Microsoft fornece 9 conectores e nossos parceiros de ecossistema criaram mais de 100 conectores. Você também pode criar seu próprio conector.

### <a name="microsoft-graph-connectors-by-microsoft"></a>Microsoft Graph conectores da Microsoft

Você pode se conectar às seguintes fontes de dados usando conectores criados pela Microsoft:

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL e Microsoft SQL Server](MSSQL-connector.md)
* [Nuvem de Confluência (visualização)](confluence-cloud-connector.md)
* [Sites empresariais](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Compartilhamento de arquivos](fileshare-connector.md)
* [Oracle SQL](OracleSQL-connector.md)
* [Salesforce](salesforce-connector.md)
* [Conhecimento ServiceNow](servicenow-knowledge-connector.md)
* [Catálogo ServiceNow (visualização)](servicenow-catalog-connector.md)


A [galeria Graph conectores da Microsoft](https://www.microsoft.com/microsoft-search/connectors) contém uma breve descrição de cada um desses conectores. Se você estiver pronto para conectar uma dessas fontes de dados [](configure-connector.md) ao seu locatário, leia a visão geral da Instalação e quaisquer outros artigos na seção Conectores de Instalação da Microsoft que se apliquem à sua fonte de dados.

### <a name="microsoft-graph-connectors-by-our-partners"></a>Microsoft Graph conectores por nossos parceiros

A [galeria Graph](https://www.microsoft.com/microsoft-search/connectors) conectores da Microsoft inclui uma breve descrição de cada um dos conectores criados por nossos parceiros e um link para o site de cada parceiro. Para saber mais, entre em contato diretamente com cada parceiro.

### <a name="build-your-own-microsoft-graph-connector"></a>Criar seu próprio conector de Graph Microsoft

Você pode criar seu próprio conector, se preferir. Para obter mais informações sobre como criar conectores, consulte [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).

## <a name="how-do-i-manage-my-connections"></a>Como faço para gerenciar minhas conexões?

Você pode gerenciar suas conexões a partir [da guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no [Centro de administração do Microsoft 365](https://admin.microsoft.com/). Para obter mais informações sobre como gerenciar conexões, consulte: [Gerenciar suas conexões](manage-connector.md).

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a>Quais são os requisitos de licença e os termos de uso para conectores?

Você precisa de uma licença Microsoft 365 ou Office 365 e cota de conectores suficientes para que os usuários em sua organização exibirem dados de conectores em seus resultados de pesquisa.

Para saber mais, confira [Requisitos de licença e preços](licensing.md) e Termos de [uso.](terms-of-use.md)

## <a name="what-are-the-preview-features"></a>Quais são os recursos de visualização?

Embora os Graph da Microsoft e as APIs Pesquisa da Microsoft agora estão geralmente disponíveis, há vários recursos que estão na visualização.

O conjunto de conectores e recursos na visualização inclui:

* [Azure DevOps conector](azure-devops-connector.md)
* [Conector de nuvem de confluência](confluence-cloud-connector.md)
* [Conector do Catálogo ServiceNow](servicenow-catalog-connector.md)
* [Gerenciar filtros personalizados](custom-filters.md)
* [Várias conexões em um vertical](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a>Como personalizar e configurar os resultados da pesquisa?

Há muitas maneiras de personalizar e configurar os resultados da pesquisa. Confira os seguintes artigos para saber mais:

* [Gerenciar verticais e tipos de resultados](customize-search-page.md)
* [Gerenciar layouts de resultados de pesquisa](customize-results-layout.md)
* [Gerenciar tipos de cluster](result-cluster.md)
* [Gerenciar filtros personalizados](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Como faço para pesquisar dados do meu conector de um aplicativo personalizado?

Depois que os dados personalizados são indexados, os [desenvolvedores podem consultar esses dados.](/graph/search-concept-custom-types) Você pode exibir seus dados em qualquer aplicativo. Para obter mais informações, consulte [Overview of the Pesquisa da Microsoft API in Microsoft Graph](/graph/search-concept-overview).

## <a name="how-do-i-customize-search-results"></a>Como personalizar os resultados da pesquisa?

A próxima etapa é personalizar os resultados da pesquisa conforme recomendado neste artigo Como personalizar e configurar os resultados [da pesquisa?](#how-do-i-customize-and-configure-search-results). Para saber mais sobre como personalizar os resultados da pesquisa, consulte [Personalizar a página de resultados da pesquisa.](customize-search-page.md)

## <a name="what-are-the-connector-limitations"></a>Quais são as limitações do conector?

* Quando você **publica** um conector criado pela Microsoft, pode levar alguns minutos para que a conexão seja criada. Durante esse tempo, a conexão mostrará seu status como pendente.

* A produtividade de ingestão é acelerada em aproximadamente quatro itens por segundo.

* Não há suporte para atualizações de esquema. Depois de criar uma configuração de conexão, não há como atualizar o esquema. Você só pode excluir e re-criar a conexão.

* Há um limite de conexão. Cada locatário pode criar até 10 conexões.

* Não é possível editar ou alterar uma conexão depois que ela tiver sido criada. Se precisar alterar qualquer detalhe, exclua e recrie a conexão.
