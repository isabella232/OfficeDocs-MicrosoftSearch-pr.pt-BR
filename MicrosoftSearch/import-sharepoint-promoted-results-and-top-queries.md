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
description: Usar consultas de pesquisa do SharePoint para criar resultados de trabalho para o Microsoft Search
ms.openlocfilehash: ae3535e322c4d06505595018669d8bd87171b9a9
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699867"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importar resultados promovidos e principais consultas do SharePoint

> [!IMPORTANT]
> Este artigo se aplica à pesquisa da Microsoft no portal de administração do Bing. Estamos movendo o portal para o centro de administração do Microsoft 365 e, em seguida, a Pesquisa da Microsoft no portal do Bing será removida. Recomendamos que você use o centro de administração do Microsoft 365 para começar. [Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)
    
Para aproveitar as consultas dos usuários e as melhores opções criadas no SharePoint, o Microsoft Search inclui duas ferramentas para importar essas informações como indicadores sugeridos: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importar regras de consulta de resultados promovidos do SharePoint

Importe essas regras, anteriormente chamadas de melhores opções, como indicadores sugeridos. Para disponibilizá-los aos usuários, publique-os. O tempo de publicação varia com base no número de marcadores selecionados.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importar as principais consultas do SharePoint usando o PowerShell

- Baixe as principais consultas do seu SharePoint. O script do PowerShell solicitará suas credenciais de administrador do SharePoint.
    
- Execute uma pesquisa do SharePoint para cada uma das principais consultas para obter o resultado da pesquisa principal.
    
- Adicione indicadores sugeridos ao portal de administração.
    
- Suas principais consultas do SharePoint são excelentes candidatos para indicadores. Use o script do PowerShell para importá-los como indicadores sugeridos. Este script realiza o seguinte trabalho:
    - Adiciona marcadores sugeridos com base nas principais consultas do SharePoint para melhorar a cobertura do indicador de pesquisa da Microsoft. Este script baixa as principais consultas acessíveis do portal de administração do SharePoint e, em seguida, carrega-as como indicadores sugeridos para que um administrador examine no portal de administração de pesquisa da Microsoft.
    - Por padrão, o script adiciona marcadores sugeridos para o locatário fornecido para todos os meses disponíveis. Ele obtém as principais consultas de um determinado site de administrador do SharePoint e os adiciona à pesquisa da Microsoft como indicadores sugeridos. Indicadores sugeridos precisam de um administrador/editor para aprová-los no portal de administração antes de serem publicados. Ao executar esse script, você será solicitado a fornecer credenciais para acessar o portal de administração de pesquisa da Microsoft.
    - O script permite que parâmetros adicionais sejam especificados. Você pode, por exemplo, adicionar marcadores sugeridos para receber o locatário das principais consultas N em cada um dos meses disponíveis.
    - Opcionalmente, você pode adicionar marcadores sugeridos para o locatário fornecido para meses em um determinado ano. Este comando obtém as principais consultas de um determinado período de tempo do site de administração do SharePoint e os adiciona à pesquisa da Microsoft como indicadores sugeridos.
    - Além de várias outras opções e modos de comando: baixar as principais consultas do SharePoint para uma pasta especificada, executar o script no modo de segurança, executar o script no modo detalhado e um modo de depuração.
    - Baixe o script [aqui](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip). 

Para obter informações sobre requisitos, exemplos e parâmetros disponíveis, baixe o script e revise o arquivo LEIAme. Após a execução do script do PowerShell, um administrador ou editor deve revisar os indicadores sugeridos e fazer as edições necessárias antes que sejam publicados.