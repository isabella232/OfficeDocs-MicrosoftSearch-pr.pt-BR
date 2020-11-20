---
title: Azure data Lake Connector para Microsoft Search
ms.author: monaray
author: monaray97
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
ms.openlocfilehash: 860c923c62495c7df20152fb530797e390949305
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367582"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Conector Gen2 de armazenamento do Azure data Lake

Com o conector Gen2 de armazenamento do Azure data Lake, os usuários em sua organização podem pesquisar arquivos armazenados no [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e nas contas de [armazenamento do Azure data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) .

Este artigo é para os administradores do [Microsoft 365](https://www.microsoft.com/microsoft-365) ou qualquer pessoa que configure, execute e monitore um conector de Gen2 de armazenamento do Azure data Lake. Ele oferece uma visão geral da configuração do conector, recursos, limitações e técnicas de solução de problemas. No artigo, usamos o *armazenamento do Azure* como um termo genérico para o [armazenamento de blob do Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e o [armazenamento do Azure data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados

### <a name="primary-storage-connection-string"></a>Cadeia de conexão de armazenamento principal

Na tela **autenticação e configuração** , forneça a cadeia de conexão de armazenamento principal. Essa cadeia de caracteres é necessária para permitir o acesso à sua conta de armazenamento. Para encontrar a cadeia de conexão, vá para o [portal do Azure](https://ms.portal.azure.com/#home) e navegue até a seção **chaves** da conta de armazenamento do Azure relevante. Copie e cole a cadeia de conexão no campo apropriado na tela.

Se você não preferir fornecer **AccountKey** (um parâmetro na cadeia de conexão de armazenamento principal), será necessário conceder acesso ao nosso serviço de conectores de gráfico para as seguintes funções.

* Leitor de dados de blob de armazenamento
* Colaborador de dados da fila de armazenamento
* Delegante de blob de armazenamento (somente para armazenamento hierárquico)

Navegue até a guia **controle de acesso** de sua conta de armazenamento do Azure e siga as instruções para conceder acesso ao seguinte aplicativo:

* **ID do aplicativo de terceiros:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Nome do aplicativo de parte inicial:** Serviço do conector do Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Notificações de conta e fila de armazenamento (opcional)

O suporte para processar alterações em tempo real no serviço de conectores do Graph pode ser adicionado no futuro. Nesse caso, monitoraremos as notificações de alteração de armazenamento do Azure armazenadas em uma fila. Você precisará criar uma fila na mesma conta que sua conta de armazenamento do Azure.

Depois de criar uma fila, vá para a guia **eventos** na página fila para configurar a **assinatura do evento**. Escolha todos os eventos BLOB que a fila receberá e conecte a fila à conta de armazenamento do Azure.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa

### <a name="azure-data-lake-gen-2"></a>Azure data Lake Gen 2

Na tela **gerenciar permissões de pesquisa** , você pode optar por absorver as listas de controle de acesso (ACLs) da conta de [armazenamento do Azure data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) . Quando essas permissões de pesquisa são definidas, o conteúdo da pesquisa é cortado com base nas permissões atribuídas ao usuário conectado do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) que está pesquisando o conteúdo. Como alternativa, você pode escolher tornar todo o conteúdo indexado da conta de armazenamento visível para todos em sua organização. Nesse caso, todos em sua organização terão acesso a todos os dados em sua conta de armazenamento.

### <a name="azure-blob-storage"></a>Azure Storage Blob

Para uma conexão com o [armazenamento de blob do Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), todo o conteúdo indexado da fonte configurada é visível para todos em sua organização. Não há suporte para listas de controle de acesso em nível de blob no armazenamento de blob do Azure.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa

O conector do Gen2 de armazenamento do Azure data Lake oferece suporte a permissões de pesquisa visíveis para **todos** ou **apenas pessoas com acesso a essa fonte de dados**. Os dados indexados que aparecem nos resultados da pesquisa podem ser visíveis para todos os usuários da organização ou apenas para os usuários que têm acesso a cada item.

## <a name="assign-property-labels"></a>Atribuir rótulos de propriedade

Você pode atribuir uma propriedade Source a cada rótulo escolhendo a partir de um menu de opções. Embora esta etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.

## <a name="manage-schema"></a>Gerenciar esquema

Na tela **gerenciar esquema** , você tem a opção de alterar os atributos de esquema (**consultável**, **pesquisável**, **recuperável** e **refinável**) associados às propriedades, adicionar aliases opcionais e escolher a propriedade **Content** .

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização

Na tela **configurações de atualização** , você pode definir o intervalo de rastreamento incremental e o intervalo de rastreamento completo. Os intervalos padrão para o conector do Gen2 de armazenamento do Azure data Lake são 15 minutos para um rastreamento incremental e uma semana para um rastreamento completo.

## <a name="limitations"></a>Limitações

Uma conexão publicada para o armazenamento de blob do Azure não pode ser reconfigurada para a fonte Gen2 de armazenamento do Azure data Lake e vice-versa. Nesses cenários, é recomendável configurar uma nova conexão.
