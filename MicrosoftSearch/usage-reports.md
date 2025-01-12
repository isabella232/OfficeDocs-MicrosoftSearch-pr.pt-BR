---
title: Relatórios de uso de pesquisa
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.topic: article
ms.service: mssearch
audience: Admin
ms.audience: Admin
ms.date: 09/24/2021
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Analisar Pesquisa da Microsoft relatórios de uso
ms.openlocfilehash: 1f2afa6e2c7691aa3284ae017913827761981529
ms.sourcegitcommit: ca6f0488b842e7fc0d98c7b84b2b8bc5817d3e7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2021
ms.locfileid: "60224863"
---
# <a name="microsoft-search-usage-reports"></a>Pesquisa da Microsoft Relatórios de uso

Os relatórios de uso da pesquisa permitem que você obtenha mais compreensão de como a pesquisa está funcionando em sua organização. As percepções geradas a partir desses relatórios ajudarão você a realizar ações que tornarão a pesquisa uma experiência mais útil e agradável para seus usuários.

> [!IMPORTANT]
> Pesquisa da Microsoft relatórios de uso estão atualmente em visualização

Os [relatórios de](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) uso do Pesquisa da Microsoft incluem gráficos e tabelas gerados a partir de pesquisas executadas SharePoint Home (o site com URL terminando em /SharePoint.aspx), Office.com e Pesquisa da Microsoft em caixas de pesquisa Bing. Você pode ver dados dos últimos 31 dias, por dia ou mensalmente do ano anterior. Esses relatórios estão apenas sendo divulgados, portanto, levará tempo para acumular os dados históricos.

> [!div class="mx-imgBorder"]
> ![Painel de relatórios de uso de pesquisa.](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Visão geral dos relatórios de pesquisa

| Relatório | Descrição |
|:-----|:-----|
|Volume da consulta|Esse relatório mostra o número de consultas de pesquisa executadas. Use este relatório para identificar tendências de volume de consulta de pesquisa e para determinar períodos de atividade de pesquisa alta e baixa.|
|Principais Consultas|Esse relatório mostra as consultas de pesquisa mais populares. Uma consulta é adicionada a esse relatório quando ela é pesquisada pelo menos três vezes com um clique em um resultado. Use este relatório para entender quais tipos de informações seus usuários estão procurando.|
|Consultas abandonadas|Este relatório mostra consultas de pesquisa populares que recebem baixo clique. Use esse relatório para identificar consultas de pesquisa que podem levar à insatisfação do usuário e para aprimorar a capacidade de descoberta de conteúdo. Em seguida, você pode determinar se criar uma resposta, como um Indicador, ou ingerir novo conteúdo por meio de um conector Graph é a ação certa.|
|Sem consultas de resultados|Esse relatório mostra consultas de pesquisa populares que retornaram sem resultado. Use-o para identificar as consultas que podem criar insatisfação do usuário e aprimorar a capacidade de descoberta do conteúdo. Em seguida, você pode determinar se criar uma resposta, como um Indicador, ou ingerir novo conteúdo por meio de um conector Graph é a ação certa.|

>[!NOTE]
>Atualmente, há um problema conhecido em que as consultas atendidas por uma resposta como um Indicador são contadas como uma consulta abandonada.

## <a name="viewing-reports"></a>Exibindo relatórios

Quando você navega até a página relatórios de uso, todos os relatórios estão disponíveis para exibição. Você pode usar o filtro de data para escolher um dia ou mês específico para exibição.

Baixar um relatório permitirá que você veja relatórios de um intervalo de tempo mais amplo. Clique na seta de download e selecione **últimos 31 dias** **ou últimos 12 meses.** O relatório é baixado como uma Excel de dados. Se você tiver selecionado os últimos 31 dias, a planilha terá uma guia individual para cada dia. O download dos últimos 12 meses terá uma guia para cada mês.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Quando eu selecionar últimos 31 dias ou últimos 12 meses, por que preciso escolher um dia específico ou um mês específico.**

A exibição do calendário, hoje, nos relatórios de uso da pesquisa da Microsoft é um processo de duas etapas. Primeiro selecione o intervalo de datas no menu suspenso (últimos 31 dias ou últimos 12 meses) e selecione o dia de início ou mês.

As tabelas de consulta superior, abandonadas e com falha mostram resultados do dia ou do mês escolhido.

**Quando vou ver os dados agregados dos últimos 7 dias, dos últimos 30 dias e assim por diante...?**

Estamos considerando esse tipo de agregação e simplificando a filtragem do intervalo de dados para versões futuras desses relatórios.

**Por que não consigo ver uma divisão de relatórios de uso por diferentes aplicativos (fontes)?**

Atualmente, a filtragem por fonte não está disponível. Os relatórios combinam pesquisas de SharePoint Home e Office.com. Nossa próxima versão incluirá filtragem de origem para que você possa ver métricas específicas para cada aplicativo.

**Que outra filtragem para relatórios de uso está chegando?**

Estamos trabalhando em mais filtros que ajudarão a entender o uso da pesquisa em um nível mais granular da sua organização. Por exemplo, você poderá ver o volume de consulta para uma geografia ou departamento específico.
