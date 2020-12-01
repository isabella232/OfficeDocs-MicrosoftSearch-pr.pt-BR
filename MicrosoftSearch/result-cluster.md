---
title: Cluster de resultados de conectores
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Detalhes sobre a experiência de cluster do resultado dos conectores
ms.openlocfilehash: fa6ac2dc720ed43e40454b952526734accd45ea4
ms.sourcegitcommit: a328b9764abf5cd0c1c0a8c7def0c6e334da9a1d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477109"
---
# <a name="graph-connectors-result-cluster"></a>Cluster de resultados do conectores do Graph

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Visão geral do cluster de resultados do conectores do Graph (visualização)  

Com os grupos de resultados de conectores do Graph, as empresas podem pesquisar conteúdo de fontes de dados de terceiros em seu modo de exibição padrão (a guia tudo) no SharePoint e no Office.com.

Os clusters de resultados ajudam os usuários a descobrir todo o conteúdo de terceiros (previoulsy vinculado a um único conector e vertical) em um só lugar. Os resultados mostrados em um cluster de resultados são agrupados juntos com base em como o administrador de locatários os configura em uma vertical de pesquisa.  

## <a name="how-connector-results-are-selected-and-displayed"></a>Como os resultados do conector são selecionados e exibidos

Os resultados do conector fornecidos no cluster de resultados são derivados das verticais de pesquisa individuais com o conteúdo do conector. Cada vertical de pesquisa fornece um conjunto de resultados relevantes que se torna um cluster de resultado candidato. Os resultados relevantes são escolhidos com base na propriedade "título", no trecho de resultados e no componente de conteúdo de cada item.

Para garantir a descoberta de conteúdo de verticais de pesquisa, recomendamos fornecer títulos significativos para seus itens. Isso afeta positivamente a arbitragem dos candidatos do cluster de resultados e a probabilidade de seu conteúdo aparecer em um cluster de resultados. Por exemplo, evite o uso de IDs como valores para a propriedade "title", a menos que os usuários estejam usando IDs para procurar conteúdo.

A frequência com que um cluster de resultados é mostrado varia em fatores como o número de verticais de pesquisa que você configura e o tipo de conteúdo. Ao selecionar ou ignorar resultados de cluster de resultados, você fornecerá implicitamente dicas que ajustarão o disparo dos clusters de resultados ao longo do tempo.

A experiência de resultados de pesquisa para itens de conector mostrados em seu cluster de resultados é gerada pelo sistema e não usa layouts de resultados personalizados. Você deve declarar a propriedade "título" e o conteúdo do item durante o registro da conexão, se quiser que os resultados apareçam no seu cluster de resultados.

## <a name="enable-result-clusters"></a>Habilitar clusters de resultados
  
A experiência de cluster de resultados está desativada por padrão.  

Siga estas etapas para ativar a experiência no nível da organização:

1. No [centro de administração do Microsoft 365](https://admin.microsoft.com/), vá para **configurações**  >  **&** de personalização de inteligência de pesquisa  >  **Customization**  >  **Verticals**.  
2. Selecione **todos os** verticais e, em seguida, habilitar **Mostrar resultados do conector**. 


Siga estas etapas para ativar a experiência no nível do site:

1. No site do SharePoint em que você deseja a experiência de cluster de resultados, vá para **configurações**.
2. Vá para **informações do site** > **Exibir todas as configurações do site**.
3. Vá para a seção de pesquisa da Microsoft e selecione **Configurar a pesquisa da Microsoft para este conjunto de sites**.
4. No painel de navegação, vá para **experiência personalizada** e, em seguida, selecione **vertical**.
5. Selecione **todos os** verticais e, em seguida, habilitar **Mostrar resultados do conector**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Exibir a experiência de cluster de resultados após a habilitação

Depois que você ativar a experiência de cluster de resultados, poderá levar alguns minutos para que você possa visualizá-lo. Se quiser a experiência imediatamente, você poderá acrescentar *cacheClear = true* à URL no SharePoint e no Office.
