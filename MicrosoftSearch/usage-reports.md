---
title: Relatórios de uso de pesquisa
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Analisar relatórios de uso da Pesquisa da Microsoft
ms.openlocfilehash: ad349e60794f219fa757861081b12a33c6806091
ms.sourcegitcommit: 25b82bce1eaec5803111161b04ee9fd9e82a0bd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50072235"
---
# <a name="microsoft-search-usage-reports"></a>Relatórios de Uso da Pesquisa da Microsoft

Os relatórios de uso de pesquisa permitem que você entenda melhor como a pesquisa está funcionando em sua organização. As informações geradas a [](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find) partir desses relatórios o ajudarão a facilitar a descoberta e a tomada de ações que tornarão a pesquisa uma experiência mais útil e agradável para seus usuários.

Os [relatórios de uso da](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) Pesquisa da Microsoft incluem gráficos e tabelas gerados a partir de pesquisas executadas na Página Office.com SharePoint Home. Você pode ver dados dos últimos 31 dias, por dia ou mensalmente do ano anterior. Esses relatórios estão apenas sendo implantando, portanto, levará algum tempo para acumular os dados históricos.

Uma versão anterior desta página incluía dados de pesquisas executadas para a Pesquisa da Microsoft no Bing Bing.com. Esses dados serão integrados a esses relatórios em breve, mas, por enquanto, você ainda poderá ver esses relatórios clicando no link na parte inferior da página para exibir as principais consultas e distribuição de impressões do **Bing.**

> [!div class="mx-imgBorder"]
> ![Painel de relatórios de uso de pesquisa](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Visão geral dos relatórios de pesquisa

| Relatório | Descrição |
|:-----|:-----|
|Volume da consulta|Esse relatório mostra o número de consultas de pesquisa executadas. Use esse relatório para identificar tendências de volume de consulta de pesquisa e para determinar períodos de atividade de pesquisa alta e baixa.|
|Principais Consultas|Esse relatório mostra as consultas de pesquisa mais populares. Use esse relatório para entender quais tipos de informações os usuários estão procurando.|
|Consultas Abandonadas|Este relatório mostra consultas de pesquisa populares que recebem baixo clique. Use esse relatório para identificar consultas de pesquisa que podem levar à insatisfação do usuário e para aprimorar a capacidade de descoberta de conteúdo. Em seguida, você pode determinar se criar uma resposta, como um Indicador, ou ingerir novo conteúdo por meio de um conector do Graph é a ação certa.|
|Nenhuma consulta de resultados|Esse relatório mostra consultas de pesquisa populares que retornaram sem resultado. Use-o para identificar as consultas que podem criar insatisfação do usuário e aprimorar a capacidade de descoberta do conteúdo. Em seguida, você pode determinar se criar uma resposta, como um Indicador, ou ingerir novo conteúdo por meio de um conector do Graph é a ação certa.|

## <a name="viewing-reports"></a>Exibindo relatórios

Quando você navega até a página de relatórios de uso, todos os relatórios ficam disponíveis para exibição. Você pode usar o filtro de data para escolher um dia ou mês específico para exibição.

Baixar um relatório permitirá que você veja relatórios de um intervalo de tempo maior. Clique na seta de download e selecione **nos últimos 31 dias** ou nos últimos **12 meses.** O relatório é baixado como uma planilha do Excel. Se você selecionou nos últimos 31 dias, a planilha terá uma guia individual para cada dia. O download dos últimos 12 meses terá uma guia para cada mês.

Para exibir as principais consultas e relatórios de distribuição de impressões do Bing, clique no link na página.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Quando eu selecionar últimos 31 dias ou últimos 12 meses, por que eu tenho que escolher um dia específico ou um mês específico.**

A exibição de calendário, hoje, nos relatórios de uso da pesquisa da Microsoft é um processo de duas etapas. Primeiro selecione o intervalo de datas no menu suspenso (últimos 31 dias ou últimos 12 meses) e, em seguida, selecione o dia de início ou mês.

As tabelas de consulta principais, abandonadas e com falha mostram os resultados do dia ou do mês escolhido.

**Quando verei os dados agregados dos últimos 7 dias, dos últimos 30 dias, etc... Como os principais relatórios de consultas do Bing?**

Estamos considerando esse tipo de agregação e simplificando a filtragem de intervalo de dados para versões futuras desses relatórios.

**Por que não consigo ver um detalhamento dos relatórios de uso por diferentes aplicativos (fontes)?**

Atualmente, a filtragem por fonte não está disponível. Os relatórios combinam pesquisas do SharePoint Home e Office.com. Nossa próxima versão incluirá filtragem de origem para que você possa ver métricas específicas para cada aplicativo.

**Quais outros relatórios de uso de filtragem estão chegando?**

Estamos trabalhando em filtros adicionais que ajudarão a fazer sentido no uso da pesquisa em um nível mais granular da sua organização. Por exemplo, você poderá ver o volume de consulta de um departamento ou região geográfica específica.

**Por que a Pesquisa da Microsoft nos relatórios do Bing está em uma página separada?**

Modernizar a pesquisa em aplicativos do Office 365 para a Pesquisa da Microsoft exigiu que insinuá-lo em sistemas diferentes anteriormente, incluindo a geração de relatórios. Isso leva tempo e achamos que era mais importante obter esses relatórios agora em vez de aguardar até concluirmos a integração dos dados do Bing. Depois que concluirmos a integração, os dados de todos os pontos de extremidade de pesquisa serão incluídos nos mesmos relatórios.
