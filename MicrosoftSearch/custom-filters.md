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
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790325"
---
# <a name="manage-custom-filters"></a>Gerenciar filtros personalizados

Você pode usar filtros para personalizar a experiência da Pesquisa da Microsoft. Os filtros permitem que os usuários refinem rapidamente o conjunto de resultados de sua consulta de pesquisa.

Um filtro personalizado pode ser criado dentro de uma vertical com base em uma propriedade de conexão. Por exemplo, você pode criar um filtro **Publicado em** para conexão ServiceNow dentro de uma vertical.

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Criar um filtro em um nível organizacional vertical

Para criar um filtro na pesquisa da Microsoft, siga estas etapas:

1. No centro de administração do Microsoft 365, vá para [Verticais.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
1. Criar/editar a vertical na qual você deseja criar o filtro
1. Navegue até a etapa "Filtros" no assistente
1. Clique em "Adicionar Filtro" e começar
1. Depois de adicionar filtros, você pode revisar e salvar a vertical.

## <a name="things-to-consider"></a>Itens a considerar

1. Existem recursos adicionais de filtro no conteúdo da conexão.

    - Você também pode criar filtro em um alias para propriedades de origem do conector
    - Se uma vertical tiver várias conexões, você poderá criar um filtro comum entre essas conexões. Isso pode ser feito criando o filtro em um alias comum que aliases propriedades de origem entre as diferentes conexões. Por exemplo, você pode criar um **filtro Autor** em uma conexão ServiceNow e Jira criando aliases da seguinte forma:

    | Connection | Propriedade | Alias |
    | --- | --- | --- |
    | Serviço Agora | Proprietário | Autor |
    | Jira | Publisher | Autor |

1. Existem filtros dentro do escopo de uma vertical.

    - Se um filtro for criado em uma vertical que está no nível organizacional, o filtro só ficará visível no nível organizacional
    - Se um filtro for criado em uma vertical que está no nível do site, o filtro só ficará visível no nível do site.

## <a name="known-limitations"></a>Limitações conhecidas

1. Atualmente, você só pode criar filtros em propriedades gerenciadas de tipo de & de caracteres.
1. Não é possível criar filtros hierárquicos.

## <a name="resources"></a>Recursos

[Gerenciar verticais e tipos de resultados](customize-search-page.md)
