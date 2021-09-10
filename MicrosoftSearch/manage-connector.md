---
title: Gerenciar conectores Graph Microsoft para Pesquisa da Microsoft
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Gerenciar conectores Graph Microsoft para Pesquisa da Microsoft.
ms.openlocfilehash: dd82114ff6aa651b57ce1941685840906ecf7318
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973387"
---
# <a name="monitor-your-connections"></a>Monitorar as suas conexões

Para acessar e gerenciar seus conectores, você deve ser designado como administrador de pesquisa para seu locatário. Entre em contato com o administrador do locatário para provisioná-lo para a função de administrador de pesquisa.

## <a name="connection-operations"></a>Operações de conexão

Navegue até [a guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no [Centro de administração do Microsoft 365](https://admin.microsoft.com).

Para cada tipo de conector, o [Centro de administração do Microsoft 365](https://admin.microsoft.com) suporta as operações mostradas na tabela a seguir:

Operation | Conectores de gráfico da Microsoft | Conectores Graph parceiros
--- | --- | ---
Adicionar uma conexão | :heavy_check_mark: (Consulte Visão [geral da Instalação](configure-connector.md)) | :x: (Consulte seu parceiro ou UX de administrador de conector personalizado)
Excluir uma conexão | :heavy_check_mark: | :heavy_check_mark:
Editar uma conexão publicada | :heavy_check_mark: Nome e Descrição<br></br> :heavy_check_mark: Configurações de conexão<br></br> :heavy_check_mark: Rótulos de propriedades<br></br> :heavy_check_mark: Esquema<br></br> :heavy_check_mark: Agenda de atualização<br></br> | :heavy_check_mark: Nome<br></br> :heavy_check_mark: Descrição
Editar uma conexão de rascunho | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>Monitorar seu estado de conexão

Depois de criar uma conexão, o número de itens **processados** aparece na guia Conectores **na** Pesquisa da Microsoft página. Depois que o rastreamento completo inicial for concluído com êxito, o progresso de rastreamentos incrementais periódicos será exibido. Esta página fornece informações sobre as operações diárias do conector e uma visão geral dos logs e do histórico de erros.

Cinco estados aparecem na coluna **Estado em** cada conexão:

* **Sincronizando**. O conector está rastreando os dados da fonte para indexar os itens existentes e fazer qualquer atualização.

* **Pronto**: a conexão está pronta e não há rastreamento ativo em execução contra ela. **O último tempo de** sincronização indica quando ocorreu o último rastreamento bem-sucedido. A conexão é tão recente quanto a última hora de sincronização.

* **Pausado**. Os rastreamentos são pausados pelos administradores por meio da opção de pausa. O próximo rastreamento é executado somente quando é retomado manualmente. No entanto, os dados dessa conexão continuam a ser pesquisáveis.

* **Falha**. A conexão teve uma falha crítica. Esse erro requer intervenção manual. O administrador precisa tomar a ação apropriada com base na mensagem de erro mostrada. Os dados indexados até o erro ocorrer são pesquisáveis.

* **Delete Failed**. Falha na exclusão da conexão. Dependendo do motivo da falha, os dados ainda podem ser indexados, a cota de item ainda pode ser consumida e os rastreamentos ainda podem ser executados para a conexão. É recomendável tentar excluir a conexão novamente neste estado.

## <a name="monitor-your-index-quota-utilization"></a>Monitorar a utilização da cota de índice

A cota de índice disponível e o consumo são exibidos na página inicial dos conectores.

:::image type="content" alt-text="Barra de utilização de cota de índice." source="media/quota_utilization.png" lightbox="media/quota_utilization.png":::

A barra de utilização de cota indicará vários estados com base no consumo de cota pela sua organização:

Estado | Níveis de utilização de cota
--- | --- 
Normal | 0-79%
Alto | 80-89%
Crítica | 90%-99%
Completo | 100%

O número de itens indexados também será exibido com cada conexão. O número de itens indexados por cada conexão contribui para a cota total disponível para sua organização.

Quando a cota de índice é excedida para sua organização, todas as conexões ativas serão impactadas e essas conexões operarão **no estado limite excedido.** Nesse estado, suas conexões ativas  

* Não será possível adicionar novos itens.

* Será possível atualizar ou excluir itens existentes.

Para corrigir isso, você pode fazer qualquer um dos seguintes:

* Saiba como comprar cota de índice para sua organização em [Requisitos de licenciamento e preços.](licensing.md)

* Identifique conexões que tenham muito conteúdo sendo ingerido e atualize-as para indexar menos itens para dar espaço para cota. Para atualizar a conexão, você deve excluir e criar uma nova conexão com um novo filtro de ingestão que traz menos itens.

* Exclua permanentemente uma ou mais conexões.
