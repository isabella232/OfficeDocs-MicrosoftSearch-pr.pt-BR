---
title: Conector de Graph do Azure Data Lake para Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector de Armazenamento do Azure Data Lake Graph Gen2 para Pesquisa da Microsoft
ms.openlocfilehash: f60de4252e514f84bc92daf4ea65c535cf40a13d
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701395"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Conector do Azure Data Lake Armazenamento Gen2 Graph

O conector de Graph do Azure Data Lake Armazenamento Gen2 permite que os usuários em sua organização pesquisem arquivos armazenados em contas do [Azure Blob Armazenamento](/azure/storage/blobs/storage-blobs-introduction) e do [Azure Data Lake Gen 2 Armazenamento.](/azure/storage/blobs/data-lake-storage-introduction)

> [!NOTE]
> Leia o [**artigo Configurar seu Graph conector para**](configure-connector.md) entender as instruções gerais Graph configuração de conectores.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector do Azure Data Lake Armazenamento Gen2. Ele complementa o processo de instalação geral e mostra instruções que se aplicam apenas ao conector do Azure Data Lake Armazenamento Gen2. Este artigo também inclui informações sobre [Limitações.](#limitations)

No artigo, usamos *o Azure Armazenamento* como um termo genérico para o [Azure Blob Armazenamento](/azure/storage/blobs/storage-blobs-introduction) e o [Azure Data Lake Gen 2 Armazenamento](/azure/storage/blobs/data-lake-storage-introduction).

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: adicionar um conector Graph no Centro de administração do Microsoft 365

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão

Insira a cadeia de caracteres de conexão de armazenamento principal. Essa cadeia de caracteres é necessária para permitir o acesso à sua conta de armazenamento. Para encontrar sua cadeia de caracteres de conexão,  vá para o [portal do Azure](https://ms.portal.azure.com/#home) e navegue até a seção Chaves da sua conta Armazenamento Azure relevante.

Se você preferir não fornecer o **AccountKey** (um parâmetro na cadeia de caracteres de conexão de armazenamento principal), conceda acesso ao nosso serviço de conectores do Graph para as seguintes funções:

* Armazenamento Blob Data Reader
* Armazenamento Colaborador de Dados da Fila
* Armazenamento Blob Delegator

Navegue até a guia **Controle** de Acesso da sua conta do Azure Armazenamento e siga as instruções para conceder acesso ao seguinte aplicativo:

* **ID do aplicativo de** primeira parte: 56c1da01-2129-48f7-9355-af6d59d42766
* **Nome do aplicativo de primeira parte: Graph** de conector

### <a name="storage-account-and-queue-notifications-optional"></a>Armazenamento de conta e de fila (Opcional)

O suporte para processar alterações em tempo real no serviço Graph conectores pode ser adicionado no futuro. Nesse caso, monitoraremos as notificações de alteração do Azure Armazenamento armazenadas em uma fila. Você precisará criar uma fila na mesma conta que sua conta do Azure Armazenamento.

Depois de criar uma fila, vá até a guia **Eventos** na página fila para configurar a **Assinatura de Evento**. Escolha todos os eventos Blob que a fila receberá e conecte a fila à conta do Azure Armazenamento.

## <a name="step-4-assign-property-labels"></a>Etapa 4: Atribuir rótulos de propriedade

Você pode atribuir uma propriedade de origem a cada rótulo escolhendo a partir de um menu de opções. Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá melhores resultados de pesquisa para usuários finais.

## <a name="step-5-manage-schema"></a>Etapa 5: Gerenciar esquema

Na tela **Gerenciar Esquema,** você pode alterar os atributos de esquema associados às propriedades, as opções são **Consulta,** **Pesquisa,** **Recuperação** e **Refinar**. Você também pode adicionar aliases opcionais e escolher a **propriedade** Content.

## <a name="step-6-manage-search-permissions"></a>Etapa 6: Gerenciar permissões de pesquisa

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Você pode optar por ingerir as Listas de Controle de Acesso (ACLs) da sua conta do [Azure Data Lake Gen 2 Armazenamento.](/azure/storage/blobs/data-lake-storage-introduction) Quando essas permissões de pesquisa são definidas, o conteúdo da pesquisa é cortado com base nas permissões do usuário Azure Active Directory [.](/azure/active-directory/) Como alternativa, você pode optar por tornar todo o conteúdo indexado de sua conta de armazenamento visível para todos em sua organização. Nesse caso, todos na sua organização terão acesso a todos os dados em sua conta de armazenamento.

O conector de Graph do Azure Data Armazenamento Lake Graph dá suporte a permissões de pesquisa visíveis para Todos **ou** Somente pessoas com acesso a essa fonte **de dados**. Os dados indexados que aparecem nos resultados da pesquisa podem estar visíveis para os usuários da organização que têm acesso a cada item.

### <a name="azure-blob-storage"></a>Azure Storage Blob

Para uma conexão com o [Azure Blob Armazenamento](/azure/storage/blobs/storage-blobs-introduction), todo o conteúdo indexado da fonte configurada fica visível para todos na sua organização. As listas de controle de acesso não são suportadas no nível blob no Azure Blob Armazenamento.

## <a name="step-7-set-the-refresh-schedule"></a>Etapa 7: Definir o cronograma de atualização

Na tela **Atualizar Configurações,** você pode definir o intervalo de rastreamento incremental e o intervalo de rastreamento completo. Os intervalos padrão para o conector do Azure Data Lake Armazenamento Gen2 são 15 minutos para um rastreamento incremental e uma semana para um rastreamento completo.

## <a name="step-8-review-connection"></a>Etapa 8: Revisar conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitações

Uma conexão publicada para o Azure Blob Armazenamento não pode ser reconfigurada para o Azure Data Lake Armazenamento fonte Gen2 e o contrário. Nesses cenários, é recomendável configurar uma nova conexão.

Além disso, o tamanho dos arquivos precisa ser de 4 MB ou menos para que ele seja rastreado. Os tipos de arquivo atualmente suportados são:

* Word (docx, .docm, .dotx, .dotm)
* PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)
* Excel (.xlsx, .xlsm)
* Formatos Office herdado (.doc, .dot, etc.)
* Texto (.txt)
* HTML
* PDF

Arquivos binários como imagens (.jpg, .bmp etc.) não são suportados. Por exemplo, se um arquivo .docx contém apenas imagens, ele pode ser ignorado porque ele não retornou nenhum conteúdo.