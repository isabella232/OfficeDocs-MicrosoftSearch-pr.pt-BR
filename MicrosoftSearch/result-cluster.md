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
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773023"
---
# <a name="graph-connectors-result-cluster"></a>Cluster de resultados do conectores do Graph

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Visão geral do cluster de resultados do conectores do Graph (visualização)  

Com os conectores do Graph os clusters de resultados, as empresas podem pesquisar conteúdo de fontes de dados de terceiros no modo de exibição padrão, na guia **tudo** , no SharePoint, no Office.com e no Microsoft Search no Bing.

Os clusters de resultados ajudam os usuários a descobrir todo o conteúdo de terceiros em um só lugar. Os resultados mostrados em um cluster de resultados são agrupados juntos com base na configuração vertical de pesquisa.

## <a name="how-connector-results-are-selected-and-displayed"></a>Como os resultados do conector são selecionados e exibidos

Os resultados do conector fornecidos no cluster de resultados são derivados das verticais de pesquisa individuais com o conteúdo do conector. Cada vertical de pesquisa fornece um conjunto de resultados relevantes que se torna um cluster de resultado candidato. Os resultados relevantes são escolhidos com base na propriedade "título" e na propriedade "conteúdo" de cada item. A propriedade Content está marcada como *IsContent = true* no esquema.

Para garantir a descoberta de conteúdo de verticais de pesquisa, recomendamos fornecer títulos significativos para seus itens. Isso afeta positivamente a arbitragem dos candidatos do cluster de resultados e a probabilidade de seu conteúdo aparecer em um cluster de resultados. Por exemplo, evite o uso de IDs como valores para a propriedade "title", a menos que os usuários estejam usando IDs para procurar conteúdo.

A frequência com que um cluster de resultados é mostrado varia em fatores como o número de verticais de pesquisa que você configura e o tipo de conteúdo. Por meio da interação ou ignoração de um cluster de resultados, os usuários fornecem implicitamente dicas que ajustarão o disparador ao longo do tempo.

A experiência de resultados de pesquisa para itens de conector mostrados em seu cluster de resultados usa [tipos de resultados](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) definidos por você. Se nenhum tipo de resultado é configurado, um [layout gerado pelo sistema](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) é usado. 

É recomendável usar a propriedade "title" como o título do resultado da pesquisa e a propriedade "content" como a descrição da pesquisa. Isso oferecerá a melhor experiência para os usuários por meio de um disparo preciso do cluster de resultados e dos resultados mais relevantes no cluster. 

## <a name="enable-result-clusters"></a>Habilitar clusters de resultados
  
A experiência de cluster de resultados está desativada por padrão.  

Siga estas etapas para ativar a experiência no nível da organização:

1. No [centro de administração do Microsoft 365](https://admin.microsoft.com), acesse [**verticalmente**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Selecione **todos os** verticais e, em seguida, habilitar **Mostrar resultados do conector**. 


Siga estas etapas para ativar a experiência no nível do site do SharePoint:

1. No site do SharePoint em que você deseja a experiência de cluster de resultados, vá para **configurações**.
2. Vá para **informações do site** > **Exibir todas as configurações do site**.
3. Vá para a seção de pesquisa da Microsoft e selecione **Configurar a pesquisa da Microsoft para este conjunto de sites**.
4. No painel de navegação, vá para **experiência personalizada** e, em seguida, selecione **vertical**.
5. Selecione **todos os** verticais e, em seguida, habilitar **Mostrar resultados do conector**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Exibir a experiência de cluster de resultados após a habilitação

Depois que você ativar a experiência de cluster de resultados, poderá levar alguns minutos para que você possa visualizá-lo. Se quiser a experiência imediatamente, você poderá acrescentar *cacheClear = true* à URL no SharePoint e no Office.
