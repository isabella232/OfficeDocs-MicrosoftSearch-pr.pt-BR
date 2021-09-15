---
title: Gerenciar filtros
ms.author: v-revathib
author: revathi-b
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Gerenciar filtros para uso na SERP
ms.openlocfilehash: c614d4b60c746f2e18fdb3352281891ea5134373
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375623"
---
# <a name="manage-filters"></a>Gerenciar filtros

Os filtros permitem aos usuários refinar os resultados de suas consultas e exibir os resultados refinados. Você pode personalizar os filtros disponíveis para seus usuários Pesquisa da Microsoft experiência.

Há dois tipos de filtros disponíveis na página de pesquisa.

- Filtros fora da caixa
- Filtros personalizados

> [!NOTE]
> Os Filtros Personalizados estão atualmente em visualização para administradores e usuários finais em Versão Direcionada. Para obter mais informações sobre visualização, consulte [Conectores recursos de visualização](connectors-overview.md#what-are-the-preview-features).

## <a name="out-of-the-box-filters"></a>Filtros fora da caixa

Por padrão, os filtros de caixa estão disponíveis em verticais de pesquisa, como Todos, Arquivos, Imagens e Notícias. Nas verticais 'Tudo' e 'Arquivo', você pode ver o filtro "Tipo de arquivo" na propriedade FileType e o filtro "Última modificação" na propriedade LastModifiedTime. Esses filtros estão disponíveis em SharePoint Home, Office.com, SharePoint Sites e Trabalhar verticalmente Bing.

## <a name="custom-filters"></a>Filtros personalizados

Os filtros podem ser adicionados às verticais de pesquisa personalizadas no nível da organização e do site. As propriedades gerenciadas refináveis são usadas para configurar filtros no assistente de administração vertical.  Em seguida, um filtro personalizado pode ser criado dentro de uma propriedade de conexão vertical. Por exemplo, você pode criar um filtro Publicado em para uma conexão ServiceNow dentro de uma vertical.

Os filtros configurados para verticais no escopo da organização estarão disponíveis no escopo da organização. Os filtros também podem ser configurados no escopo do site.  

## <a name="create-organization-level-filters"></a>Criar filtros no nível da organização

1. Em  [Centro de administração do Microsoft 365](https://admin.microsoft.com/), vá para  [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Selecione sua vertical preferida onde você deseja criar um filtro e clique em **Editar**.  
3. Navegue até a etapa Filtros no assistente vertical.
4. Clique **em Adicionar um Filtro para** configurar filtros em propriedades gerenciadas refináveis.
5. Depois de adicionar filtros, você pode revisar e salvar a vertical.

## <a name="create-sharepoint-site-level-filters"></a>Criar SharePoint de nível de site

1. No [SharePoint de administração,](https://sharepoint.com/)vá para Configurações.
2. Procure a seção Pesquisa da Microsoft e selecione Configurar Pesquisa da Microsoft **para este conjunto de sites.**
3. No painel de navegação, vá para Experiência personalizada e selecione  **Verticals**.
4. Selecione sua vertical preferida para criar o filtro e clique em **Editar**.
5. Navegue até a etapa Filtros no assistente vertical.
6. Clique **em Adicionar um Filtro para** configurar filtros em propriedades gerenciadas refináveis.
7. Depois de adicionar filtros, você pode revisar e salvar a vertical.

## <a name="filter-across-multiple-properties"></a>Filtrar entre várias propriedades

As verticais podem ser criadas com uma ou mais fontes de conteúdo. Quando uma vertical é configurada com várias fontes de conteúdo, a lista de propriedades do refinador mostra a qual fonte de conteúdo cada propriedade refinável pertence. As propriedades gerenciadas comuns serão mescladas com base no nome (ou alias) e no tipo de dados. Os filtros também podem ser configurados nessas propriedades comuns. Isso é feito criando o filtro em um alias comum que aliasiza as propriedades de origem entre as diferentes conexões. Por exemplo, você pode criar um filtro **Autor** entre conexões ServiceNow e Jira criando aliases da seguinte forma:

 | Connection | Propriedade | Alias |
 | --- | --- | --- |
 | Serviço Agora | Proprietário | Autor |
 | Jira | Publisher | Autor |

## <a name="important-details"></a>Detalhes importantes

- Os filtros só podem ser adicionados a verticais personalizadas. Novos filtros não podem ser adicionados a verticais fora da caixa, como Todos, Arquivos, Pessoas, Sites, Notícias.
- Os filtros são configuráveis nas propriedades Text e DateTime.
- Você está limitado a um total de 50 filtros.
- Não é possível ajustar a ordem dos filtros de saída da caixa.
- Não há suporte para filtros para OneDrive conteúdo. Os valores de filtro correspondentes aos resultados da pesquisa OneDrive conteúdo não serão exibidos em filtros.
- Os valores de filtro personalizados mostrarão opções SharePoint conteúdo e não do conteúdo do One Drive.Por exemplo, se você criar um filtro personalizado para 'Autor' e SharePoint conteúdo contiver resultados apenas de um autor, "Amy", e OneDrive conteúdo contém resultados apenas de um autor chamado 'John', o filtro personalizado Autor mostrará 'Amy' como a única opção.
- Um valor de filtro mostrado para SharePoint conteúdo será aplicado OneDrive conteúdo quando usado.
