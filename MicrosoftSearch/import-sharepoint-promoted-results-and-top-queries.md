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
description: Usar consultas de pesquisa do SharePoint para criar resultados de trabalho para o Microsoft Search
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508750"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importar resultados promovidos e principais consultas do SharePoint

Para aproveitar as consultas dos usuários e as melhores opções criadas no SharePoint, o Microsoft Search inclui duas ferramentas para importar essas informações como indicadores sugeridos: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importar regras de consulta de resultados promovidos do SharePoint

Importe essas regras, anteriormente chamadas de melhores opções, como indicadores sugeridos. Para disponibilizá-los aos usuários, publique-os. O tempo de publicação varia com base no número de marcadores selecionados.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importar as principais consultas do SharePoint usando o PowerShell

- Baixe as principais consultas do seu SharePoint. O script do PowerShell solicitará suas credenciais de administrador do SharePoint.
    
- Execute uma pesquisa do SharePoint para cada uma das principais consultas para obter o resultado da pesquisa principal.
    
- Adicione indicadores sugeridos ao portal de administração.
    
- Suas principais consultas do SharePoint são excelentes candidatos para indicadores. Use o script do PowerShell para importá-los como indicadores sugeridos. Este script irá:
    
Para obter informações sobre requisitos, exemplos e parâmetros disponíveis, baixe o script e revise o arquivo LEIAme. Após a execução do script do PowerShell, um administrador ou editor deve revisar os indicadores sugeridos e fazer as edições necessárias antes que sejam publicados.

  

