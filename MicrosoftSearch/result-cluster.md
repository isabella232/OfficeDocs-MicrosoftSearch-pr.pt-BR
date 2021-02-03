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
description: Detalhes da experiência do Cluster de Resultados de Conectores
ms.openlocfilehash: fb29fb9c14811698fb7c5d043853b57231c76a0b
ms.sourcegitcommit: d1bc6c41ecf47584373ce57543502bed55753d0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080833"
---
# <a name="graph-connectors-result-cluster"></a>Cluster de resultados de conectores do Graph

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Visão geral do cluster de resultados dos conectores do Graph (Visualização)  

Com os clusters de resultados de conectores do Graph, as empresas  podem pesquisar conteúdo de fontes de dados de terceiros em sua exibição padrão, a guia Todos, no SharePoint, no Office.com e na Pesquisa da Microsoft no Bing.

Os clusters de resultados ajudam os usuários a descobrir todo o conteúdo de terceiros em um só lugar. Os resultados mostrados em um cluster de resultados são agrupados com base na configuração vertical de pesquisa.

## <a name="how-connector-results-are-selected-and-displayed"></a>Como os resultados do conector são selecionados e exibidos

Os resultados do conector fornecidos no cluster de resultados são derivados de pesquisas verticais individuais com conteúdo do conector. Cada pesquisa vertical fornece um conjunto de resultados relevantes que se torna um cluster de resultados candidatos. Os resultados relevantes são escolhidos com base na propriedade "title" e na propriedade "content" de cada item. A propriedade de conteúdo é marcada *como isContent=true* no esquema.

Para garantir a descoberta de conteúdo dos verticais de pesquisa, recomendamos fornecer títulos significativos para seus itens. Isso positivamente afeta a arbitragem de candidatos a cluster de resultados e a probabilidade de seu conteúdo aparecer em um cluster de resultados. Por exemplo, evite o uso de IDs como valores para a propriedade "title", a menos que os usuários usem IDs para procurar conteúdo.

A frequência com que um cluster de resultados é exibido varia em fatores como o número de pesquisas verticais que você configura e o tipo de conteúdo. Ao interagir ou ignorar um cluster de resultados, os usuários fornecerão implicitamente dicas que ajustarão seu gatilho ao longo do tempo.

A experiência de resultado de pesquisa para itens de conector mostrados em seu cluster de resultados usa [tipos de](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) resultados definidos por você. Se nenhum tipo de resultado for configurado, um [layout gerado pelo](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) sistema será usado. 

Recomendamos usar a propriedade "title" como o título do resultado da pesquisa e a propriedade "content" como a descrição da pesquisa. Isso fornecerá a melhor experiência para seus usuários por meio do disparo preciso do cluster de resultados e dos resultados mais relevantes no cluster. 

## <a name="enable-result-clusters"></a>Habilitar clusters de resultados
  
A experiência do cluster de resultados está desligada por padrão.  

Siga estas etapas para ativar a experiência no nível da organização:

1. No centro [de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Verticais.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Selecione Todos **os verticais** e habilitar **Mostrar resultados do conector.** 


Siga estas etapas para ativar a experiência no nível do site do SharePoint:

1. No site do SharePoint onde você deseja a experiência de cluster de resultados, vá para **Configurações**.
2. Vá para Informações **do Site** Exibir todas > **as configurações do site.**
3. Vá para a seção Pesquisa da Microsoft e selecione **Configurar a Pesquisa da Microsoft para este conjunto de sites.**
4. No painel de navegação, vá para **Experiência personalizada** e selecione **Verticals.**
5. Selecione Todos **os verticais** e habilitar **Mostrar resultados do conector.**

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Exibir a experiência do cluster de resultados depois que ela for habilitada

Depois de ativar a experiência do cluster de resultados, pode levar até 12 horas para que você possa exibi-la. Se quiser a experiência imediatamente, você pode anexar *cacheClear=true* à URL no SharePoint e no Office.
