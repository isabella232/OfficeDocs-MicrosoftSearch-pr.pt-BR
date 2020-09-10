---
title: Visão geral dos conectores
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Visão geral dos conectores do Microsoft Graph para o Microsoft Search
ms.openlocfilehash: e7c697505f6f84f6fef021df756091d8f4e32db1
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422897"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Visão geral dos conectores do Microsoft Graph

O Microsoft Search indexa todos os seus dados do [microsoft 365](https://www.microsoft.com/microsoft-365) para torná-los pesquisáveis para os usuários. Com os conectores do Microsoft Graph, sua organização pode indexar dados de terceiros para que eles apareçam nos resultados da pesquisa da Microsoft. Os dados de terceiros podem ser hospedados no local ou nas nuvens públicas ou privadas. Os conectores expandem os tipos de fontes de conteúdo que podem ser pesquisados em seus aplicativos de produtividade do Microsoft 365 e no ecossistema mais amplo da Microsoft.

> [!IMPORTANT]
> **Isenção de responsabilidade**: os conectores do Microsoft Graph e as APIs de pesquisa da Microsoft (consulta e índice) estão atualmente no status de visualização disponível para locatários no lançamento direcionado. Para usar conectores com o Microsoft Search ou para criar conectores, opte pelo [lançamento direcionado](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide). Para saber mais sobre a visualização, consulte [Connectors Preview Program](connectors-preview.md).

## <a name="architecture"></a>Arquitetura

O seguinte diagrama de arquitetura da plataforma do Microsoft Graph mostra como o conteúdo do conector flui através da indexação de conteúdo para os resultados do usuário nos clientes de [pesquisa da Microsoft](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) . Este artigo explica cada um dos principais blocos de construção no processo de fluxo de dados de conectores do Microsoft Graph.

![Diagrama: os dados locais e baseados em nuvem são retirados por conectores e indexados pela API do Microsoft Search e, em seguida, o serviço de pesquisa da Microsoft entrega os resultados aos usuários.](media/highlevel-connectors_FINAL.png)

A API instancia uma conexão por fonte de dados. Em seguida, a API indexa e armazena os dados. As conexões estabelecidas interagem com o Microsoft Search, para que os usuários possam obter resultados de pesquisa.

Você pode configurar todos os conectores criados pela Microsoft no centro de [Administração](https://admin.microsoft.com)do Microsoft 365. O centro de administração simplifica a configuração do seu conector com uma interface do usuário simples.

Para criar uma **conexão** com uma fonte de dados, os administradores precisam de acesso autenticado aos dados e a todo o repositório de conteúdo. Os dados são alimentados para o serviço do conector do Graph para indexação.

## <a name="available-connectors"></a>Conectores disponíveis

No momento, há 6 conectores criados pela Microsoft e mais de 100 conectores estão disponíveis em nossos parceiros de ecossistema.

Para visualizar os conectores de um de nossos parceiros de ecossistema, entre em contato diretamente com eles. Para obter mais informações, consulte a [Galeria de conectores do Microsoft Graph](connectors-gallery.md).

Você também pode [criar seu próprio conector](https://docs.microsoft.com/graph/search-concept-overview).

### <a name="connectors-by-microsoft"></a>Conectores criados pela Microsoft

A versão prévia dos conectores do Microsoft Graph inclui 6 conectores criados pela Microsoft. Você pode configurá-los no [centro de administração](https://admin.microsoft.com) e aprender como [configurar seu conector criado pela Microsoft](configure-connector.md).

As seções a seguir fornecem descrições breves para esses conectores criados pela Microsoft. Você pode obter mais informações nos artigos vinculados para cada conector.

- **[Gen2 de armazenamento do Azure data Lake](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**. Com esse conector do Microsoft Graph, os usuários em sua organização podem pesquisar arquivos e conteúdo armazenados em contêineres de blob do Azure. O conector do Gen2 de armazenamento do Azure data Lake também indexa pastas habilitadas por hierarquia nas contas do Gen2 de armazenamento do Azure data Lake que você especificar.
Saiba mais sobre o [conector do Gen2 de armazenamento do Azure data Lake](azure-data-lake-connector.md).

- **[DevOps do Azure](https://azure.microsoft.com/services/devops)**. Com esse conector do Microsoft Graph, os usuários em sua organização podem pesquisar itens de trabalho de sua instância do DevOps do Azure.
Saiba mais sobre o [conector DevOps do Azure](azure-devops-connector.md).

- **[Azure SQL](https://azure.microsoft.com/services/sql-database)**. Com esse conector do Microsoft Graph, os usuários em sua organização podem pesquisar dados de seu banco de dados SQL do Azure.
Saiba mais sobre o [Azure SQL Connector](MSSQL-connector.md).

- **Sites corporativos**. Com esse conector do Microsoft Graph, os usuários da sua organização podem Pesquisar nas páginas de qualquer site que não seja do SharePoint Enterprise.
Saiba mais sobre o [conector de sites da empresa](enterprise-web-connector.md).

- **[MediaWiki](https://www.mediawiki.org/wiki/MediaWiki)**. Com esse conector do Microsoft Graph, os usuários podem pesquisar artigos da base de conhecimento em sites wiki que sua organização cria com o MediaWiki.
Saiba mais sobre o [conector MediaWiki](mediawiki-connector.md).

- **[Microsoft SQL Server](https://www.microsoft.com/sql-server/sql-server-2017)**. Com esse conector do Microsoft Graph, os usuários em sua organização podem pesquisar dados em bancos de dados do SQL Server local.
Saiba mais sobre o [Microsoft SQL Server Connector](MSSQL-connector.md).

- **[ServiceNow](https://www.servicenow.com)**. Com esse conector do Microsoft Graph, os usuários da sua organização podem pesquisar artigos da base de conhecimento da sua instância do ServiceNow.
Saiba mais sobre o [conector do ServiceNow](servicenow-connector.md).

### <a name="connectors-from-our-partners"></a>Conectores de nossos parceiros

Há mais de 100 conectores disponíveis para visualização de nossos parceiros de ecossistema. Para visualizar os conectores de um de nossos parceiros de ecossistema, entre em contato diretamente com eles.
Saiba mais sobre conectores de nossos parceiros na [Galeria de conectores do Microsoft Graph](connectors-gallery.md).

### <a name="build-your-own-connector"></a>Criar seu próprio conector

Para indexar arquivos ou tipos de dados personalizados, os desenvolvedores podem criar conectores no [Microsoft Graph](https://developer.microsoft.com/graph/). Um conector é um aplicativo que [cria uma conexão](https://docs.microsoft.com/graph/search-index-manage-connections) e empurra itens para o índice de pesquisa da Microsoft. Para obter mais informações, consulte a [visão geral para estender a experiência de pesquisa da Microsoft para aplicativos no Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).

### <a name="search-results-with-your-custom-built-connector"></a>Resultados da pesquisa com seu conector interno personalizado

Após a indexação dos dados personalizados, os desenvolvedores podem [consultar esses dados](https://docs.microsoft.com/graph/search-concept-custom-types). Você pode exibir seus dados em qualquer aplicativo. Para obter mais informações, consulte a [visão geral para estender a experiência de pesquisa da Microsoft para aplicativos no Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).

## <a name="license-requirements"></a>Requisitos de licença

Para exibir dados de conectores nos resultados da pesquisa, os usuários devem ter uma das seguintes assinaturas do Microsoft 365 ou do Office 365:

- [Microsoft 365 ou Office 365 Enterprise E3 ou e5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

- [Microsoft 365 ou Office 365 educação a3 ou a5](https://www.microsoft.com/microsoft-365/academic/compare-office-365-education-plans?activetab=tab:primaryr1)
