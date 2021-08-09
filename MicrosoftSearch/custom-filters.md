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
ms.openlocfilehash: 339c7e96a00860a044a4e1af7382932f8e440e01b8b6d12445c24c1ea9b8cad0
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533124"
---
# <a name="manage-custom-filters"></a>Gerenciar filtros personalizados

Você pode usar filtros para personalizar a Pesquisa da Microsoft experiência. Os filtros permitem que os usuários refinem rapidamente o conjunto de resultados de sua consulta de pesquisa.

Um filtro personalizado pode ser criado dentro de uma propriedade de conexão vertical. Por exemplo, você pode criar um filtro **Publicado em** para a conexão ServiceNow dentro de uma vertical.

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Criar um filtro em um nível organizacional vertical

Para criar um filtro na pesquisa da Microsoft, siga estas etapas:

1. No Centro de administração do Microsoft 365, vá para [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
1. Criar/editar a vertical na qual você deseja criar o filtro
1. Navegue até a etapa "Filtros" no assistente
1. Clique em "Adicionar Filtro" e começar
1. Depois de adicionar filtros, você pode revisar e salvar a vertical.

## <a name="things-to-consider"></a>Itens a considerar

1. Recursos adicionais de filtro existem no conteúdo da conexão.

    - Você também pode criar filtro em um alias para as propriedades de origem do conector
    - Se uma vertical tiver várias conexões, você poderá criar um filtro comum entre essas conexões. Isso pode ser feito criando o filtro em um alias comum que aliasiza as propriedades de origem entre as diferentes conexões. Por exemplo, você pode criar um filtro **Autor** em uma conexão ServiceNow e Jira criando aliases da seguinte forma:

    | Connection | Propriedade | Alias |
    | --- | --- | --- |
    | Serviço Agora | Proprietário | Autor |
    | Jira | Publisher | Autor |

1. Os filtros existem no escopo de uma vertical.

    - Se um filtro for criado em uma vertical que está no nível organizacional, o filtro só ficará visível no nível organizacional
    - Se um filtro for criado em uma vertical que está no nível do site, o filtro só ficará visível no nível do site.

## <a name="known-limitations"></a>Limitações conhecidas

1. No momento, você pode criar filtros somente em propriedades gerenciadas de tipo de & de caracteres de data.
1. Não é possível criar filtros hierárquicos.

## <a name="resources"></a>Recursos

[Gerenciar verticais e tipos de resultados](customize-search-page.md)
