---
title: Azure data Lake Connector para Microsoft Search
ms.author: v-pamcn
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do Gen2 de armazenamento do Azure data Lake para o Microsoft Search
ms.openlocfilehash: bedd7307ca2add52408bb9a5e3b3b21fd75df258
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949528"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Conector Gen2 de armazenamento do Azure data Lake

Com o conector [Gen2 de armazenamento do Azure data Lake](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) , os usuários em sua organização podem pesquisar arquivos e seu conteúdo. Esse conector acessa os dados armazenados em contêineres de blob do Azure e pastas habilitadas para hierarquia dentro de uma conta do Azure data Lake Storage Gen 2.

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector de Gen2 de armazenamento do Azure data Lake. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados

### <a name="primary-storage-connection-string"></a>Cadeia de conexão de armazenamento principal 
Na tela **autenticação e configuração** , forneça a cadeia de conexão de armazenamento principal. Essa cadeia de caracteres é necessária para permitir o acesso à sua conta de armazenamento. Para encontrar a cadeia de conexão, vá para o [portal do Azure](https://ms.portal.azure.com/#home) e navegue até a seção **chaves** da conta do Gen2 de armazenamento do Azure data Lake. Copie e cole a cadeia de conexão no campo apropriado na tela.

Se não quiser fornecer o **AccountKey** (um parâmetro na cadeia de conexão de armazenamento principal), você terá que conceder acesso de leitura ao nosso serviço de conectores de gráfico. Na guia **controle de acesso** de sua conta do Gen2 de armazenamento do Azure data Lake, siga as instruções nessa página para conceder acesso ao seguinte aplicativo:
* **ID do aplicativo de terceiros:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Nome do aplicativo de parte inicial:** Serviço do conector do Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Notificações de conta e fila de armazenamento (opcional)
O suporte para processar alterações em tempo real no serviço de conectores do Graph pode ser adicionado no futuro. Nesse caso, monitoraremos as notificações de alteração do Gen2 de armazenamento do Azure data Lake armazenadas em uma fila. Você precisará criar uma fila na mesma conta que seu Gen2 de armazenamento do Azure data Lake ou em outra conta de armazenamento.

Depois de criar uma fila, vá para a guia **eventos** na página fila para configurar a assinatura do evento. Escolha todos os eventos BLOB que a fila receberá e conecte a fila à conta de armazenamento do Azure data Lake Storage Gen2.

## <a name="manage-the-search-schema"></a>Gerenciar o esquema de pesquisa
Na tela **gerenciar esquema** , você tem a opção de alterar os atributos de esquema (**consultável**, **pesquisável**e **recuperável**) associados às propriedades gerenciadas. Esses atributos de propriedade gerenciada são dados indexados de sua conta do Gen2 de armazenamento do Azure data Lake.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa
Na tela **gerenciar permissões de pesquisa** , você pode optar por absorver as listas de controle de acesso (ACLs) da conta de armazenamento. Quando essas permissões de pesquisa são definidas, o conteúdo da pesquisa é cortado com base nas permissões atribuídas ao usuário conectado do Azure AD que está pesquisando o conteúdo. Como alternativa, você pode escolher tornar todo o conteúdo indexado da conta de armazenamento visível para todos em sua organização. Nesse caso, todos em sua organização terão acesso a todos os dados em sua conta de armazenamento.
 
## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização
Na tela **configurações de atualização** , você pode definir o intervalo de rastreamento incremental e o intervalo de rastreamento completo. Os intervalos padrão para o conector do Gen2 de armazenamento do Azure data Lake são 15 minutos para um rastreamento incremental e uma semana para um rastreamento completo.
 
## <a name="limitations"></a>Limitações
Atualmente, o acesso multiprotocolo do Gen2 de armazenamento do data Lake do Azure está disponível somente no centro dos Estados Unidos, oeste dos EUA, Canadá, leste dos EUA, leste da Ásia, nordeste da Europa, leste da Ásia, sudoeste da Europa, oeste da Austrália, oeste leste, oeste leste, West US2 e Brasil Sul.

Para obter atualizações e mais informações, consulte [acesso multiprotocolo no Azure data Lake Storage (versão prévia)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access).


