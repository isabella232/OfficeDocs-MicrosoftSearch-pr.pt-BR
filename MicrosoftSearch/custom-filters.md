---
title: Gerenciar filtros personalizados
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gerenciar filtros personalizados
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927375"
---
# <a name="create-custom-filters"></a>Criar filtros personalizados

Você pode criar filtros para personalizar a experiência de pesquisa que os usuários veem quando pesquisam no Microsoft [SharePoint](https://sharepoint.com/), no Microsoft [Office](https://office.com)e no Microsoft Search no [Bing](https://bing.com). Filtros permite que os usuários aprimorem rapidamente o conjunto de resultados de suas consultas de pesquisa.

Um filtro personalizado pode ser criado dentro de um vertical com base em uma propriedade de conexão. Por exemplo, você pode criar um filtro **publicado na** conexão do ServiceNow dentro de uma vertical personalizada.

## <a name="things-to-consider"></a>Itens a considerar

1. Para criar um filtro personalizado na fonte de conteúdo de conexão, são fornecidas algumas capacidades adicionais:
- Você também pode criar um filtro em um alias para propriedades de origem do conector
- Caso a vertical tenha várias conexões, você pode criar um filtro comum entre essas conexões. Isso pode ser feito criando o filtro em um alias comum que faz o alias de propriedades de origem entre diferentes conexões. Por exemplo, você pode criar um filtro de **autor** através de um & uma conexão do JIRA criando aliases da seguinte maneira:

| Connection | Propriedade | Alias |
| --- | --- | --- |
| Serviço agora | Proprietário | Autor |
| Jira | Publisher | Autor |

2. Há filtros no escopo da vertical. Excluí  
- Se um filtro for criado em uma vertical que está no nível organizacional, o filtro só poderá ser visto no nível organizacional
- Se um filtro for criado em uma vertical que está no nível do site, o filtro só poderá ser visto no nível do site.

## <a name="steps-to-create-custom-filter"></a>Etapas para criar um filtro personalizado

### <a name="create-filter-in-organizational-level-vertical"></a>Criar filtro no nível organizacional vertical:

Para criar um filtro na pesquisa da Microsoft, siga estas etapas:

1. No centro de administração do Microsoft 365, vá para a página [vertical](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .
2. Criar/editar a vertical na qual você deseja criar o filtro
3. Navegue até a etapa ' filtros ' no assistente
4. Clique em "Adicionar filtro" e comece após adicionar filtros, você pode revisar e salvar a vertical.

## <a name="known-limitations"></a>Limitações conhecidas

1. No momento, você pode criar filtros somente nas propriedades gerenciadas de tipo de data & de cadeia de caracteres.
2. Não é possível criar filtros hierárquicos

## <a name="resources"></a>Recursos

[Personalizar página de resultados de pesquisa](customize-search-page.md)