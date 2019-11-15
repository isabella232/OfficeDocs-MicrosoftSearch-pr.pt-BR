---
title: Integrar o PowerApps
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: Incluir aplicativos baseados em navegador nos resultados dos indicadores da pesquisa da Microsoft
ms.openlocfilehash: e3fda45bbc7bef5634fb08a7dd6fc0143d6da054
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626833"
---
# <a name="integrate-powerapps"></a>Integrar o PowerApps
   
Ajudar os usuários a concluir tarefas, como inserir o tempo de férias ou relatar despesas integrando o PowerApps existente em seus indicadores. O PowerApps integrado aparece dentro de um resultado de indicador, eliminando a necessidade de acessar um site diferente ou abrir uma ferramenta separada, o que poupa tempo e esforço.
  
## <a name="what-are-powerapps"></a>O que são PowerApps?

PowerApps é um serviço que permite criar aplicativos de negócios que são executados em um navegador, telefone ou tablet sem necessidade de nenhuma experiência de codificação. Saiba mais:
  
- [Aprendizagem Orientada](https://docs.microsoft.com/learn/browse/?products=powerapps)
    
- [Documentação](https://docs.microsoft.com/powerapps/)
    
## <a name="add-a-powerapp-to-a-bookmark"></a>Adicionar um PowerApp a um indicador

PowerApps funcionam em qualquer navegador e em qualquer dispositivo, e leva menos de um minuto para adicioná-los.
  
1. [Encontre a ID do aplicativo para o PowerApp](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que você deseja integrar.
    
2. No portal de administração de pesquisa da Microsoft, acesse **indicadores**
    
3. Adicione um indicador ou localize um indicador existente ao qual você deseja adicionar um PowerApp
    
4. Nas configurações de indicador, clique em **aplicativo avançado**e em **Adicionar um aplicativo avançado**
    
5. Insira ou cole a ID do aplicativo
    
    A altura e a largura são automaticamente adicionadas. Os indicadores são compatíveis com orientações tipo retrato e paisagem; porém, no momento, o tamanho não pode ser alterado.
    
6. A visualização do indicador mostra como o PowerApp será exibido no resultado do indicador
    
    O PowerApp na visualização é totalmente funcional para facilitar o teste e o uso.
    
7. Clique em **Publicar**
    
Quando um usuário autorizado da Microsoft Search pesquisa no Bing para qualquer uma das palavras-chave ou reservadas do indicador, o PowerApp aparecerá no resultado do indicador.
