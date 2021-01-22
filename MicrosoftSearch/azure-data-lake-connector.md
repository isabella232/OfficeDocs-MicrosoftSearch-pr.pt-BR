---
title: Conector do Azure Data Lake para Pesquisa da Microsoft
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
description: Configurar o conector do Azure Data Lake Storage Gen2 para a Pesquisa da Microsoft
ms.openlocfilehash: 8891c9a1fdf5397c397a941b5131f014db9e7a54
ms.sourcegitcommit: 597c338bf9c1c425747ac74a9a1ae57c5e8957ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49920718"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Conector do Azure Data Lake Storage Gen2

Com o conector do Azure Data Lake Storage Gen2, os usuários em sua organização podem pesquisar arquivos armazenados nas contas de Armazenamento de Blob do [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e [do Azure Data Lake Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

Este artigo é destinado a administradores do [Microsoft 365](https://www.microsoft.com/microsoft-365) ou qualquer pessoa que configure, executa e monitore um conector do Azure Data Lake Storage Gen2. Ele fornece uma visão geral da configuração do conector, recursos, limitações e técnicas de solução de problemas. No artigo, usamos o Armazenamento do *Azure* como um termo genérico para o Armazenamento de Blob do [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e o Armazenamento do [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

## <a name="connect-to-a-data-source"></a>Conectar a uma fonte de dados

### <a name="primary-storage-connection-string"></a>Cadeia de conexão de armazenamento principal

Na tela **Autenticação e configuração,** forneça a Cadeia de Conexão de Armazenamento Principal. Essa cadeia de caracteres é necessária para permitir o acesso à sua conta de armazenamento. Para encontrar a cadeia de conexão, vá para  o portal do [Azure](https://ms.portal.azure.com/#home) e navegue até a seção Chaves da sua conta de Armazenamento do Azure relevante. Copie e colar a cadeia de conexão no campo apropriado na tela.

Se você não preferir fornecer o **AccountKey** (um parâmetro na cadeia de conexão de armazenamento principal), você precisará conceder acesso ao nosso Serviço de Conectores do Graph para as funções a seguir. (Esse recurso só tem suporte para armazenamento hierárquico. O armazenamento de Blob tradicional terá que fornecer AccountKey.)
* Leitor de Dados de Blob de Armazenamento
* Colaborador de dados da fila de armazenamento
* Delegator de Blob de Armazenamento

Navegue até **a guia Controle** de Acesso da sua conta de Armazenamento do Azure e siga as instruções para conceder acesso ao seguinte aplicativo:

* **ID** do aplicativo de terceiros: 56c1da01-2129-48f7-9355-af6d59d42766
* **Nome do aplicativo de terceiros:** Serviço de Conector do Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Notificações de fila e conta de armazenamento (opcional)

O suporte para processar alterações em tempo real no Serviço de Conectores do Graph pode ser adicionado no futuro. Nesse caso, monitoraremos as notificações de alteração de Armazenamento do Azure armazenadas em uma fila. Você precisará criar uma fila na mesma conta que sua conta de Armazenamento do Azure.

Depois de criar uma fila, vá para a guia **Eventos** na página da fila para configurar a **Assinatura de Evento.** Escolha todos os eventos blob que a fila receberá e conecte a fila à conta de Armazenamento do Azure.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Na tela **Gerenciar permissões de** pesquisa, você pode optar por ingerir as LISTAS de Controle de Acesso (ACLs) da sua conta de armazenamento do [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Quando essas permissões de pesquisa são definidas, o conteúdo de pesquisa é cortado com base nas permissões atribuídas ao usuário do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) que está pesquisando o conteúdo. Como alternativa, você pode optar por tornar todo o conteúdo indexado de sua conta de armazenamento visível para todos em sua organização. Nesse caso, todos em sua organização terão acesso a todos os dados em sua conta de armazenamento.

### <a name="azure-blob-storage"></a>Armazenamento de BLOBs do Microsoft Azure

Para uma conexão com o Armazenamento de Blob do [Azure,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)todo o conteúdo indexado da fonte configurada fica visível para todos em sua organização. As listas de controle de acesso não são suportadas no nível de Blob no Armazenamento de Blob do Azure.

## <a name="search-permissions"></a>Permissões de pesquisa

O conector do Azure Data Lake Storage  Gen2 oferece suporte a permissões de pesquisa visíveis para todas as pessoas ou somente pessoas com **acesso a essa fonte de dados.** Os dados indexados que aparecem nos resultados da pesquisa podem estar visíveis para todos os usuários na organização ou apenas para os usuários que têm acesso a cada item.

## <a name="assign-property-labels"></a>Atribuir rótulos de propriedade

Você pode atribuir uma propriedade de origem a cada rótulo escolhendo em um menu de opções. Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.

## <a name="manage-schema"></a>Gerenciar esquema

Na  tela Gerenciar Esquema, você tem a opção de alterar os atributos de esquema (**queryable**, **searchable**, **retrievable** e **refinable**) associados às propriedades, adicionar aliases opcionais e escolher a propriedade **Content.**

## <a name="set-the-refresh-schedule"></a>Definir a agenda de atualização

Na tela **Atualizar Configurações,** você pode definir o intervalo de rastreamento incremental e o intervalo de rastreamento completo. Os intervalos padrão para o conector do Azure Data Lake Storage Gen2 são 15 minutos para um rastreamento incremental e uma semana para um rastreamento completo.

## <a name="limitations"></a>Limitações

Uma conexão publicada para o Armazenamento de Blob do Azure não pode ser reconfigurada para a fonte do Azure Data Lake Storage Gen2 e vice-versa. Nesses cenários, é recomendável configurar uma nova conexão.
