---
title: Importar resultados promovidos e principais consultas do SharePoint
ms.author: dawholl
author: dawholl
manager: kellis
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
description: Use consultas de pesquisa SharePoint para criar resultados de trabalho para Pesquisa da Microsoft
ms.openlocfilehash: cfd5fafd0529f537a55e436ef078800a4b9714177e04c63e65e968f16fcf322e
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533820"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importar resultados promovidos e principais consultas do SharePoint

> [!IMPORTANT]
> Este artigo se aplica ao Pesquisa da Microsoft no portal Bing administrador. Estamos movendo o portal para o centro de administração do Microsoft 365 e, em seguida, a Pesquisa da Microsoft no portal do Bing será removida. Recomendamos que você use o centro de administração do Microsoft 365 para começar. [Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)
    
Para aproveitar as consultas dos usuários e as Melhores Opções que você criou no SharePoint, o Pesquisa da Microsoft inclui duas ferramentas para importar essas informações como indicadores sugeridos: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importar SharePoint regras de consulta de resultados promovidos

Importe essas regras, anteriormente chamadas de Melhores Apostas, como indicadores sugeridos. Para torná-los disponíveis para seus usuários, publique-os. O tempo de publicação varia com base no número de indicadores selecionados.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importar as principais SharePoint usando o PowerShell

- Baixe as principais consultas do seu SharePoint. O script do PowerShell solicitará que você SharePoint credenciais de administrador.
    
- Execute uma SharePoint pesquisa de cada uma das principais consultas para obter o resultado principal da pesquisa.
    
- Adicione indicadores sugeridos ao portal de administração.
    
- Suas principais SharePoint são excelentes candidatos para indicadores. Use o script do PowerShell para importá-los como indicadores sugeridos. Este script faz o seguinte trabalho:
    - Adiciona indicadores sugeridos com base SharePoint principais consultas para melhorar Pesquisa da Microsoft de indicador. Esse script baixa as principais consultas acessíveis SharePoint portal de administração e as carrega como indicadores sugeridos para um administrador analisar no portal de administração Pesquisa da Microsoft.
    - Por padrão, o script adiciona indicadores sugeridos a determinado locatário para todos os meses disponíveis. Ele obtém as principais consultas de um determinado SharePoint site de administração e as adiciona Pesquisa da Microsoft como indicadores sugeridos. Indicadores sugeridos precisam de um administrador/editor para aprove-los no portal de administração antes de serem publicados. Ao executar esse script, você será solicitado a solicitar credenciais para acessar o portal Pesquisa da Microsoft administrador.
    - O script permite que parâmetros adicionais sejam especificados. Você pode, por exemplo, adicionar indicadores sugeridos a determinado locatário para as principais consultas N em cada um dos meses disponíveis.
    - Opcionalmente, você pode adicionar indicadores sugeridos a determinado locatário por meses no ano determinado. Este comando obtém as principais consultas para o determinado período de tempo SharePoint site do administrador e as adiciona Pesquisa da Microsoft como indicadores sugeridos.
    - Além disso, há várias outras opções e modos de comando: baixar as principais consultas do SharePoint para uma pasta especificada, executar o script no modo Cofre, executar o script no modo Verbose e um modo de depuração.
    - Baixe o script [aqui](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip). 

Para obter informações sobre requisitos, exemplos e parâmetros disponíveis, baixe o script e revise o arquivo README. Depois que o script do PowerShell for executado, um administrador ou editor deve revisar os indicadores sugeridos e fazer todas as edições necessárias antes de ser publicado.