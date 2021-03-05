---
title: Gerenciar conectores do Microsoft Graph para Pesquisa da Microsoft
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gerenciar conectores do Microsoft Graph para Pesquisa da Microsoft.
ms.openlocfilehash: 488b6e9452e381f8fc64ad06c6f063aa170ca7f5
ms.sourcegitcommit: 3ed4d21510020045d25e8c5b7e168013d96c1b7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50464036"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>Monitorar as suas conexões

Para acessar e gerenciar seus conectores, você deve ser designado como administrador de pesquisa para seu locatário. Entre em contato com o administrador do locatário para provisioná-lo para a função de administrador de pesquisa.

## <a name="connection-operations"></a>Operações de conexão

Navegue até [a guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no centro de administração [do Microsoft 365.](https://admin.microsoft.com)

Para cada tipo de conector, o Centro de administração do [Microsoft 365](https://admin.microsoft.com) dá suporte às operações mostradas na tabela a seguir:

Operation | Conector criado pela Microsoft | Conector de parceiro ou personalizado
--- | --- | ---
Adicionar uma conexão | :heavy_check_mark: (Consulte [Configure your Microsoft-built connector](configure-connector.md)) | :x: (Consulte seu parceiro ou UX de administrador de conector personalizado)
Excluir uma conexão | :heavy_check_mark: | :heavy_check_mark:
Editar uma conexão publicada | :heavy_check_mark: Nome<br></br> :heavy_check_mark: Descrição<br></br> :heavy_check_mark: credenciais de autenticação para sua fonte de dados externa<br></br> :heavy_check_mark: Credenciais de gateway para sua fonte de dados local<br></br> :heavy_check_mark: Agenda de atualização<br></br> | :heavy_check_mark: Nome<br></br> :heavy_check_mark: Descrição
Editar uma conexão de rascunho | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>Monitorar o status da conexão

Depois de criar uma conexão, o número de itens **processados** aparece na guia Conectores na **página Pesquisa da Microsoft.** Depois que o rastreamento completo inicial for concluído com êxito, o progresso de rastreamentos incrementais periódicos será exibido. Esta página fornece informações sobre as operações diárias do conector e uma visão geral dos logs e do histórico de erros.

Quatro estados aparecem na coluna **Status** em cada conexão:

* **Sincronizando**. O conector está rastreando os dados da fonte para indexar os itens existentes e fazer qualquer atualização.

* **Habilitado**: a conexão está habilitada e não há rastreamento ativo em execução contra ela. **O último tempo de** sincronização indica quando ocorreu o último rastreamento bem-sucedido. A conexão é tão recente quanto a última hora de sincronização.

* **Pausado**. Os rastreamentos são pausados pelos administradores por meio da opção de pausa. O próximo rastreamento é executado somente quando é retomado manualmente. No entanto, os dados dessa conexão continuam a ser pesquisáveis.

* **Falha**. A conexão teve uma falha crítica. Esse erro requer intervenção manual. O administrador precisa tomar a ação apropriada com base na mensagem de erro mostrada. Os dados indexados até o erro ocorrer são pesquisáveis.

## <a name="monitor-your-index-quota-utilization"></a>Monitorar a utilização da cota de índice

A cota de índice disponível e o consumo são exibidos na página inicial dos conectores.

![Barra de utilização de cota de índice](media/quota_utilization.png)

>[!NOTE]
>Durante o período de visualização, todas as organizações que estavam tentando os conectores do Graph foram fornecidas uma cota fixa gratuita de até 2 milhões de itens em todas as conexões. Com os conectores do Graph geralmente disponíveis, a cota gratuita expirará em 1º de abril de 2021 para as organizações que têm usado conectores graph na visualização.
>Os conectores do Graph criado pela Microsoft rotulados como ["Visualização"](connectors-preview.md) não serão incluídos na cota de índice total cobrada para sua organização. No entanto, ele contará para o número máximo de 10 conexões que você pode configurar para sua organização e o número máximo de 7 milhões de itens que sua organização pode indexar entre conexões; cada conexão é limitada a 700.000 itens. 

A barra de utilização de cota indicará vários estados com base no consumo de cota pela sua organização:

Estado | Consumo de cotas
--- | ---
Normal | 1-69%
Alto | 70-89%
Crítico | 90%-99%
Completo | 100%

O número de itens indexados também será exibido com cada conexão. O número de itens indexados por cada conexão contribui para a cota total disponível para sua organização.

Quando a cota de índice é excedida para sua organização, todas as conexões ativas serão impactadas e essas conexões operarão **no estado limite excedido.** Nesse estado, suas conexões ativas  

* Não será possível adicionar novos itens.

* Será possível atualizar ou excluir itens existentes.

Para corrigir isso, você pode fazer qualquer um dos seguintes:

* Saiba como comprar cota de índice para sua organização em [Requisitos de licenciamento e preços.](licensing.md)

* Identifique conexões que tenham muito conteúdo sendo ingerido e atualize-as para indexar menos itens para dar espaço para cota. Para atualizar a conexão, você deve excluir e criar uma nova conexão com um novo filtro de ingestão que traz menos itens.

* Excluir permanentemente uma ou mais conexões
