---
title: Gerenciar conectores do Microsoft Graph para o Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gerenciar conectores do Microsoft Graph para o Microsoft Search.
ms.openlocfilehash: 5aab310a05d073221918a8aaa80ea1e06c818e51
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949575"
---
# <a name="manage-your-connector-for-microsoft-search"></a>Gerenciar seu conector para a pesquisa da Microsoft

Para acessar e gerenciar seus conectores, você deve ser designado como um administrador de pesquisa para o seu locatário. Entre em contato com o administrador de locatários para provisionar a função de administrador de pesquisa.

## <a name="get-started"></a>Introdução

1. Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com).
2. Vá até **configurações** > **** > **conectores**de pesquisa da Microsoft.

Para cada tipo de conector, o [centro de administração do Microsoft 365](https://admin.microsoft.com) suporta as operações mostradas na tabela a seguir:

**Operação** | **Conector integrado da Microsoft** | **Parceiro ou conector criado de forma personalizada**
--- | --- | ---
Adicionar uma conexão | : heavy_check_mark: (consulte [Configurar o conector integrado da Microsoft](configure-connector.md)) | : x: (consulte seu parceiro ou UX de administração de conector criado para personalizar)
Exclua uma conexão | :heavy_check_mark: | :heavy_check_mark:
Editar uma conexão publicada | : heavy_check_mark: nome<br></br> : heavy_check_mark: Descrição<br></br> : heavy_check_mark: credenciais de autenticação para sua fonte de dados externa<br></br> : heavy_check_mark: credenciais de gateway para sua fonte de dados local<br></br> : heavy_check_mark: atualizar agendamento<br></br> | : heavy_check_mark: nome<br></br> : heavy_check_mark: Descrição
Editar uma conexão de rascunho | :heavy_check_mark: | x

## <a name="monitor-your-connection-status"></a>Monitorar o status da conexão
Após criar uma conexão, o número de itens processados é exibido na guia **conectores** da página de **pesquisa da Microsoft** . Depois que o rastreamento completo inicial for concluído com êxito, o progresso dos rastreamentos incrementais periódicos é exibido. Esta página fornece informações sobre as operações diárias do conector e uma visão geral dos logs e histórico de erros.

Quatro Estados aparecem na coluna **status** em cada conexão:
* **Sincronização**. O conector está rastreando os dados da fonte para indexar os itens existentes e fazer qualquer atualização.
* **Habilitado**: a conexão está habilitada e não há nenhum rastreamento ativo em execução nela. **Hora da última sincronização** indica quando ocorreu o último rastreamento bem-sucedido. A conexão é tão recente quanto o horário da última sincronização.
* Em **pausa**. Os rastreamentos são pausados pelos administradores por meio da opção PAUSE. O próximo rastreamento é executado somente quando ele é reiniciado manualmente. No entanto, os dados dessa conexão continuam a ser pesquisados.
* **Falhou**. A conexão teve uma falha crítica. Este erro requer intervenção manual. O administrador precisa tomar a ação apropriada com base na mensagem de erro mostrada. Os dados que foram indexados até que o erro ocorreu é pesquisável.

### <a name="monitor-errors"></a>Monitorar erros
Para cada **conector ativo** na guia **conectores** , qualquer erro de rastreamento existente aparecerá na guia **erro** . A guia lista os códigos de erro, a contagem de cada um e as opções de download de log de erros. Confira o exemplo na imagem a seguir. Selecione um **código de erro** para exibir os detalhes do erro.

![Lista de conectores com um conector selecionado e o painel de detalhes mostrando 3 erros para esse conector.](media/errormonitoring1.png)

Para exibir os detalhes específicos de um erro, selecione seu código de erro. Uma tela aparece com detalhes do erro e um link. Os erros mais recentes aparecem na parte superior. Confira o exemplo na tabela a seguir.

![Lista de conectores com um conector selecionado e o painel de detalhes, mostrando a lista de erros do conector. ](media/errormonitoring2.png)

## <a name="preview-limitations"></a>Limitações de visualização
* Quando você **publica** um conector criado pela Microsoft, pode levar alguns minutos até que a conexão seja criada. Durante esse tempo, a conexão mostrará seu status como pendente. Além disso, não há atualização automática, portanto, você precisa atualizar manualmente.
* O [centro de administração do Microsoft 365](https://admin.microsoft.com) não dá suporte à exibição e edição do **esquema de pesquisa** após a publicação de uma conexão. Para editar o esquema de pesquisa, exclua sua conexão e crie uma nova.
* Quando você gerencia a agenda de **atualização**da sua conexão, o número de itens que sincroniza durante cada sessão é exibido. No entanto, o histórico de sincronização não está disponível.
