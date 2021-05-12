---
title: Gerenciar conectores do Microsoft Graph para Pesquisa da Microsoft
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gerenciar conectores do Microsoft Graph para Pesquisa da Microsoft.
ms.openlocfilehash: 685b501f3afe25d75c13a1fe6cc2c1b5db8a3511
ms.sourcegitcommit: e5d695c40b68c2f1fa082fa9de20b9aa6d5b8050
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52325164"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>Monitorar as suas conexões

Para acessar e gerenciar seus conectores, você deve ser designado como administrador de pesquisa para seu locatário. Entre em contato com o administrador do locatário para provisioná-lo para a função de administrador de pesquisa.

## <a name="connection-operations"></a>Operações de conexão

Navegue até [a guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no centro de administração [do Microsoft 365.](https://admin.microsoft.com)

Para cada tipo de conector, o Centro de administração do [Microsoft 365](https://admin.microsoft.com) dá suporte às operações mostradas na tabela a seguir:

Operation | Conectores de gráfico da Microsoft | Conectores de parceiros ou gráficos
--- | --- | ---
Adicionar uma conexão | :heavy_check_mark: (Consulte Visão [geral da Instalação](configure-connector.md)) | :x: (Consulte seu parceiro ou UX de administrador de conector personalizado)
Excluir uma conexão | :heavy_check_mark: | :heavy_check_mark:
Editar uma conexão publicada | :heavy_check_mark: Nome e Descrição<br></br> :heavy_check_mark: Configurações de conexão<br></br> :heavy_check_mark: Rótulos de propriedades<br></br> :heavy_check_mark: Esquema<br></br> :heavy_check_mark: Agenda de atualização<br></br> | :heavy_check_mark: Nome<br></br> :heavy_check_mark: Descrição
Editar uma conexão de rascunho | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>Monitorar seu estado de conexão

Depois de criar uma conexão, o número de itens **processados** aparece na guia Conectores na **página Pesquisa da Microsoft.** Depois que o rastreamento completo inicial for concluído com êxito, o progresso de rastreamentos incrementais periódicos será exibido. Esta página fornece informações sobre as operações diárias do conector e uma visão geral dos logs e do histórico de erros.

Cinco estados aparecem na coluna **Estado em** cada conexão:

* **Sincronizando**. O conector está rastreando os dados da fonte para indexar os itens existentes e fazer qualquer atualização.

* **Pronto**: a conexão está pronta e não há rastreamento ativo em execução contra ela. **O último tempo de** sincronização indica quando ocorreu o último rastreamento bem-sucedido. A conexão é tão recente quanto a última hora de sincronização.

* **Pausado**. Os rastreamentos são pausados pelos administradores por meio da opção de pausa. O próximo rastreamento é executado somente quando é retomado manualmente. No entanto, os dados dessa conexão continuam a ser pesquisáveis.

* **Falha**. A conexão teve uma falha crítica. Esse erro requer intervenção manual. O administrador precisa tomar a ação apropriada com base na mensagem de erro mostrada. Os dados indexados até o erro ocorrer são pesquisáveis.

* **Delete Failed**. Falha na exclusão da conexão. Dependendo do motivo da falha, os dados ainda podem ser indexados, a cota de item ainda pode ser consumida e os rastreamentos ainda podem ser executados para a conexão. É recomendável tentar excluir a conexão novamente neste estado.

## <a name="monitor-your-index-quota-utilization"></a>Monitorar a utilização da cota de índice

A cota de índice disponível e o consumo são exibidos na página inicial dos conectores.

![Barra de utilização de cota de índice](media/quota_utilization.png)
 
>[!NOTE]
>Durante o período de visualização, todas as organizações que estavam tentando os conectores do Graph foram fornecidas uma cota fixa gratuita de até 2 milhões de itens em todas as conexões. Com os conectores do Graph geralmente disponíveis, a cota gratuita expirará em 1º de abril de 2021 para as organizações que têm usado conectores graph na visualização.
>Os conectores do Graph criado pela Microsoft rotulados como ["Visualização"](./connectors-overview.md) não serão incluídos na cota de índice total cobrada para sua organização. No entanto, ele contará para o número máximo de 10 conexões que você pode configurar para sua organização e o número máximo de 7 milhões de itens que sua organização pode indexar entre conexões; cada conexão é limitada a 700.000 itens. 

A barra de utilização de cota indicará vários estados com base no consumo de cota pela sua organização:

Estado | Níveis de utilização de cota
--- | --- 
Normal | 0-79%
Alto | 80-89%
Crítico | 90%-99%
Completo | 100%

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

O número de itens indexados também será exibido com cada conexão. O número de itens indexados por cada conexão contribui para a cota total disponível para sua organização.

Quando a cota de índice é excedida para sua organização, todas as conexões ativas serão impactadas e essas conexões operarão **no estado limite excedido.** Nesse estado, suas conexões ativas  

* Não será possível adicionar novos itens.

* Será possível atualizar ou excluir itens existentes.

Para corrigir isso, você pode fazer qualquer um dos seguintes:

* Saiba como comprar cota de índice para sua organização em [Requisitos de licenciamento e preços.](licensing.md)

* Identifique conexões que tenham muito conteúdo sendo ingerido e atualize-as para indexar menos itens para dar espaço para cota. Para atualizar a conexão, você deve excluir e criar uma nova conexão com um novo filtro de ingestão que traz menos itens.

* Excluir permanentemente uma ou mais conexões