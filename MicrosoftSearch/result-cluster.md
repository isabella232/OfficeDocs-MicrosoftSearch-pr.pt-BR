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
description: Detalhes da experiência do Cluster de Resultados dos Conectores
ms.openlocfilehash: 912e27942e9ae3bfef874ae66227880af676b7a1a28449cc82ae8fc02f4446c0
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533973"
---
# <a name="graph-connectors-result-cluster"></a>Graph de resultados de conectores

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Visão geral do cluster de resultados Graph conectores (Visualização)  

Com clusters de resultados de conectores Graph, as empresas podem pesquisar conteúdo de fontes de dados de terceiros em seu modo de exibição padrão, a guia **Todos,** em SharePoint, Office.com e Pesquisa da Microsoft em Bing.

Os clusters de resultados ajudam os usuários a descobrir todo o conteúdo de terceiros em um só lugar. Os resultados mostrados em um cluster de resultados são agrupados com base na configuração vertical da pesquisa.

## <a name="how-connector-results-are-selected-and-displayed"></a>Como os resultados do conector são selecionados e exibidos

Os resultados do conector fornecidos no cluster de resultados são derivados de verticais de pesquisa individuais com conteúdo de conector. Cada pesquisa vertical fornece um conjunto de resultados relevantes que se torna um cluster de resultados de candidato. Os resultados relevantes são escolhidos com base na propriedade "title" e na propriedade "content" de cada item. A propriedade content é marcada como *isContent=true* no esquema.

Para garantir a descoberta de conteúdo das verticais de pesquisa, recomendamos fornecer títulos significativos para seus itens. Isso afeta positivamente a arbitragem de candidatos a cluster de resultados e a probabilidade de seu conteúdo aparecer em um cluster de resultados. Por exemplo, evite o uso de IDs como valores para a propriedade "title" a menos que seus usuários usem IDs para procurar conteúdo.

A frequência com que um cluster de resultados é mostrado varia em fatores como o número de verticais de pesquisa que você configura e o tipo de conteúdo. Ao interagir ou ignorar um cluster de resultados, os usuários fornecerão implicitamente dicas que ajustarão seu gatilho ao longo do tempo.

A experiência de resultado da pesquisa para itens de conector mostrados em seu cluster de resultados usa [tipos de resultados](./customize-search-page.md#create-your-own-result-type) definidos por você. Se nenhum tipo de resultado for configurado, um [layout gerado pelo sistema](./customize-search-page.md#default-search-result-layout) será usado. 

Recomendamos usar a propriedade "title" como o título do resultado da pesquisa e a propriedade "content" como a descrição da pesquisa. Isso fornecerá a melhor experiência para seus usuários por meio do acionamento preciso do cluster de resultados e dos resultados mais relevantes no cluster. 

## <a name="enable-result-clusters"></a>Habilitar clusters de resultados
  
A experiência de cluster de resultados é desligada por padrão.  

Siga estas etapas para ativar a experiência no nível da organização:

1. No [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Selecione Todos **os verticais** e, em seguida, **habilitar Mostrar resultados do conector**. 


Siga estas etapas para ativar a experiência no nível SharePoint site:

1. No site SharePoint onde você deseja a experiência de cluster de resultados, vá para **Configurações**.
2. Acesse Informações **do site** Exibir todas > **as configurações do site.**
3. Vá para a seção Pesquisa da Microsoft, em seguida, selecione **Configurar Pesquisa da Microsoft para este conjunto de sites**.
4. No painel de navegação, vá para **Experiência personalizada** e selecione **Verticals**.
5. Selecione Todos **os verticais** e, em seguida, **habilitar Mostrar resultados do conector**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Exibir a experiência de cluster de resultados depois de habilitada

Depois de ativar a experiência de cluster de resultados, pode levar até 12 horas para poder exibi-la. Se quiser a experiência imediatamente, você pode anexar *cacheClear=true* à URL em SharePoint e Office.