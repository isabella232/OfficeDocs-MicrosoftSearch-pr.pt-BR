---
title: Conector do Azure Data Lake Graph para Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do Azure Data Lake Storage Gen2 Graph para a Pesquisa da Microsoft
ms.openlocfilehash: da508694929d3c83a456c664aa4613b09a1b14a3
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084853"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Conector do Azure Data Lake Storage Gen2 Graph

O conector do Azure Data Lake Storage Gen2 Graph permite que os usuários em sua organização pesquisem arquivos armazenados nas contas de Armazenamento de Blob do [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e [do Azure Data Lake Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

> [!NOTE]
> Leia o artigo [**Configurar seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.

Este artigo é destinado a qualquer pessoa que configure, executa e monitore um conector do Azure Data Lake Storage Gen2. Ele complementa o processo de configuração geral e mostra instruções que se aplicam somente ao conector do Azure Data Lake Storage Gen2. Este artigo também inclui informações sobre [limitações.](#limitations)

No artigo, usamos o Armazenamento do *Azure* como um termo genérico para o Armazenamento de Blob do [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e o Armazenamento do [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Definir as configurações de conexão

Insira sua cadeia de caracteres de conexão de armazenamento principal. Essa cadeia de caracteres é necessária para permitir o acesso à sua conta de armazenamento. Para encontrar a cadeia de conexão, vá para  o portal do [Azure](https://ms.portal.azure.com/#home) e navegue até a seção Chaves da sua conta de Armazenamento do Azure relevante.

Se você preferir não fornecer o **AccountKey** (um parâmetro na cadeia de conexão de armazenamento principal), conceda acesso ao nosso Serviço de Conectores do Graph para as seguintes funções:

* Leitor de Dados de Blob de Armazenamento
* Colaborador de Dados da Fila de Armazenamento
* Delegator de Blob de Armazenamento

Navegue até **a guia Controle** de Acesso da sua conta de Armazenamento do Azure e siga as instruções para conceder acesso ao seguinte aplicativo:

* **ID** do aplicativo de terceiros: 56c1da01-2129-48f7-9355-af6d59d42766
* **Nome do aplicativo de terceiros:** Serviço de Conector do Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Notificações de fila e conta de armazenamento (opcional)

O suporte para processar alterações em tempo real no Serviço de Conectores do Graph pode ser adicionado no futuro. Nesse caso, monitoraremos as notificações de alteração de Armazenamento do Azure armazenadas em uma fila. Você precisará criar uma fila na mesma conta que sua conta de Armazenamento do Azure.

Depois de criar uma fila, vá para a guia **Eventos** na página da fila para configurar a **Assinatura de Evento.** Escolha todos os eventos blob que a fila receberá e conecte a fila à conta de Armazenamento do Azure.

## <a name="step-4-assign-property-labels"></a>Etapa 4: Atribuir rótulos de propriedade

Você pode atribuir uma propriedade de origem a cada rótulo escolhendo em um menu de opções. Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá melhores resultados de pesquisa para usuários finais.

## <a name="step-5-manage-schema"></a>Etapa 5: Gerenciar esquema

Na tela **Gerenciar** Esquema, você pode alterar os atributos de esquema associados às propriedades, as opções são **Consulta** **,** **Pesquisa,** Recuperar e **Refinar.** Você também pode adicionar aliases opcionais e escolher **a propriedade** Content.

## <a name="step-6-manage-search-permissions"></a>Etapa 6: Gerenciar permissões de pesquisa

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Você pode optar por ingerir as LISTAS de Controle de Acesso (ACLs) da sua conta de armazenamento do [Azure Data Lake Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Quando essas permissões de pesquisa são definidas, o conteúdo de pesquisa é cortado com base nas permissões do usuário assinado no [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/) Como alternativa, você pode optar por tornar todo o conteúdo indexado de sua conta de armazenamento visível para todos em sua organização. Nesse caso, todos em sua organização terão acesso a todos os dados em sua conta de armazenamento.

O conector do Azure Data Lake Storage Gen2 Graph dá suporte a permissões de pesquisa visíveis para Todos **ou** somente as pessoas com acesso a **essa fonte de dados.** Os dados indexados que aparecem nos resultados da pesquisa podem estar visíveis para os usuários na organização que têm acesso a cada item.

### <a name="azure-blob-storage"></a>Armazenamento de BLOBs do Microsoft Azure

Para uma conexão com o Armazenamento de Blob do [Azure,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)todo o conteúdo indexado da fonte configurada fica visível para todos em sua organização. As listas de controle de acesso não são suportadas no nível de Blob no Armazenamento de Blob do Azure.

## <a name="step-7-set-the-refresh-schedule"></a>Etapa 7: Definir o agendamento de atualização

Na tela **Atualizar Configurações,** você pode definir o intervalo de rastreamento incremental e o intervalo de rastreamento completo. Os intervalos padrão para o conector do Azure Data Lake Storage Gen2 são 15 minutos para um rastreamento incremental e uma semana para um rastreamento completo.

## <a name="step-8-review-connection"></a>Etapa 8: Analisar a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitações

Uma conexão publicada para o Armazenamento de Blob do Azure não pode ser reconfigurada para a origem do Azure Data Lake Storage Gen2 e o contrário. Nesses cenários, é recomendável configurar uma nova conexão.

Além disso, o tamanho dos arquivos precisa ser de 4 MB ou menos para que ele seja rastreado. Os tipos de arquivo atualmente suportados são:

* Word (docx, .docm, .dotx, .dotm)
* PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)
* Excel (.xlsx, .xlsm)
* Formatos herddos do Office (.doc, .dot, etc.)
* Texto (.txt)
* HTML
* PDF

Arquivos binários, como imagens (.jpg, .bmp, etc.) não são suportados. Por exemplo, se um arquivo .docx contiver apenas imagens, ele poderá ser ignorado porque não retornou nenhum conteúdo.
