---
title: Importar resultados promovidos e principais consultas do SharePoint
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/8/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
ROBOTS: NOINDEX
description: Use consultas de pesquisa do SharePoint para criar resultados de trabalho para a Pesquisa da Microsoft
ms.openlocfilehash: 1538c57a7b4138b36fe62e3076feb58d746b2b3e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591598"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importar resultados promovidos e principais consultas do SharePoint

> [!IMPORTANT]
> Este artigo se aplica à Pesquisa do Microsoft no portal de administração do Bing. Estamos movendo o portal para o centro de administração do Microsoft 365 e, posteriormente, ele será removido. Recomendamos que você use o centro de administração do Microsoft 365 para começar. [Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)
    
Para aproveitar as consultas dos usuários e as Melhores Opções que você criou no SharePoint, a Pesquisa da Microsoft inclui duas ferramentas para importar essas informações como indicadores sugeridos: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importar regras de consulta de resultados promovidos do SharePoint

Importe essas regras, anteriormente chamadas Best Bets, como indicadores sugeridos. Para disponibilizá-las aos seus usuários, você pode publicá-las. O tempo de publicação varia de acordo com o número de marcadores que você selecionar.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importar as consultas do SharePoint usando o PowerShell

- Baixe as principais consultas a partir do SharePoint. O script do PowerShell solicitará suas credenciais de administrador do SharePoint.
    
- Execute uma pesquisa do SharePoint para cada uma das principais consultas para obter o maior resultado de pesquisa.
    
- Adicione indicadores sugeridos ao portal de administração.
    
- As principais consultas do SharePoint são ótimas candidatas a indicadores. Use o script do PowerShell para importá-las como indicadores sugeridos. Use este script:
    
Para saber mais sobre requisitos, exemplos e parâmetros disponíveis, baixe o script e revise o arquivo Leiame. Após a execução do script do PowerShell, um administrador ou o editor deverá revisar os indicadores sugeridos e fazer as edições necessárias antes que eles sejam publicados.

  

