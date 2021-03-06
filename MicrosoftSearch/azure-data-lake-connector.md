---
title: Conector do Azure Data Lake Graph para Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do Azure Data Lake Storage Gen2 Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 2bb9570bc3b0a5adef7ac72ea1620c4f22a8aefb
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508882"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Conector do Gráfico de Armazenamento gen2 do Azure Data Lake

O conector do Azure Data Lake Storage Gen2 Graph permite que os usuários em sua organização pesquisem arquivos armazenados em contas de Armazenamento de Blob do [Azure Blob](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e do [Azure Data Lake Gen 2 Storage.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

> [!NOTE]
> Leia o [**artigo Configurar seu conector do Graph**](configure-connector.md) para entender as instruções gerais de configuração dos conectores do Graph.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector de armazenamento do Azure Data Lake Gen2. Ele complementa o processo de instalação geral e mostra instruções que se aplicam apenas ao conector de armazenamento do Azure Data Lake Gen2. Este artigo também inclui informações sobre [Limitações.](#limitations)

No artigo, usamos o *Armazenamento do Azure como* um termo genérico para Armazenamento de Blob do [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e Armazenamento do [Azure Data Lake Gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector graph no centro de administração do Microsoft 365

Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão

Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão

Insira a cadeia de caracteres de conexão de armazenamento principal. Essa cadeia de caracteres é necessária para permitir o acesso à sua conta de armazenamento. Para encontrar sua cadeia de caracteres de conexão,  vá para o [portal do Azure](https://ms.portal.azure.com/#home) e navegue até a seção Chaves da sua conta de Armazenamento relevante do Azure.

Se você preferir não fornecer o **AccountKey** (um parâmetro na cadeia de caracteres de conexão de armazenamento principal), conceda acesso ao nosso Serviço de Conectores do Graph para as seguintes funções:

* Leitor de Dados de Blob de Armazenamento
* Colaborador de dados da fila de armazenamento
* Delegator de Blob de Armazenamento

Navegue até a guia **Controle** de Acesso da sua conta de Armazenamento do Azure e siga as instruções para conceder acesso ao seguinte aplicativo:

* **ID do aplicativo de** primeira parte: 56c1da01-2129-48f7-9355-af6d59d42766
* **Nome do aplicativo de primeira parte:** Serviço de Conector do Graph

### <a name="storage-account-and-queue-notifications-optional"></a>Notificações de conta de armazenamento e fila (Opcional)

O suporte para processar alterações em tempo real no Serviço de Conectores do Graph pode ser adicionado no futuro. Nesse caso, monitoraremos as notificações de alteração de armazenamento do Azure armazenadas em uma fila. Você precisará criar uma fila na mesma conta que sua conta de Armazenamento do Azure.

Depois de criar uma fila, vá até a guia **Eventos** na página fila para configurar a **Assinatura de Evento**. Escolha todos os eventos Blob que a fila receberá e conecte a fila à conta de Armazenamento do Azure.

## <a name="step-4-assign-property-labels"></a>Etapa 4: Atribuir rótulos de propriedade

Você pode atribuir uma propriedade de origem a cada rótulo escolhendo a partir de um menu de opções. Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá melhores resultados de pesquisa para usuários finais.

## <a name="step-5-manage-schema"></a>Etapa 5: Gerenciar esquema

Na tela **Gerenciar Esquema,** você pode alterar os atributos de esquema associados às propriedades, as opções são **Consulta,** **Pesquisa,** **Recuperação** e **Refinar**. Você também pode adicionar aliases opcionais e escolher a **propriedade** Content.

## <a name="step-6-manage-search-permissions"></a>Etapa 6: Gerenciar permissões de pesquisa

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Você pode optar por ingerir as Listas de Controle de Acesso (ACLs) da sua conta de Armazenamento do [Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Quando essas permissões de pesquisa são definidas, o conteúdo da pesquisa é cortado com base nas permissões do usuário assinado no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/). Como alternativa, você pode optar por tornar todo o conteúdo indexado de sua conta de armazenamento visível para todos em sua organização. Nesse caso, todos na sua organização terão acesso a todos os dados em sua conta de armazenamento.

O conector do Azure Data Lake Storage Gen2 Graph dá suporte a permissões de pesquisa visíveis para Todos **ou** Somente pessoas com acesso a essa fonte **de dados**. Os dados indexados que aparecem nos resultados da pesquisa podem estar visíveis para os usuários da organização que têm acesso a cada item.

### <a name="azure-blob-storage"></a>Azure Storage Blob

Para uma conexão com o Armazenamento de Blob do [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), todo o conteúdo indexado da fonte configurada fica visível para todos na sua organização. As listas de controle de acesso não são suportadas no nível blob no Armazenamento de Blob do Azure.

## <a name="step-7-set-the-refresh-schedule"></a>Etapa 7: Definir o cronograma de atualização

Na tela **Atualizar Configurações,** você pode definir o intervalo de rastreamento incremental e o intervalo de rastreamento completo. Os intervalos padrão para o conector gen2 de armazenamento do Azure Data Lake são 15 minutos para um rastreamento incremental e uma semana para um rastreamento completo.

## <a name="step-8-review-connection"></a>Etapa 8: Revisar conexão

Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitações

Uma conexão publicada para o Armazenamento de Blob do Azure não pode ser reconfigurada para a fonte de armazenamento do Azure Data Lake Gen2 e o contrário. Nesses cenários, é recomendável configurar uma nova conexão.

Além disso, o tamanho dos arquivos precisa ser de 4 MB ou menos para que ele seja rastreado. Os tipos de arquivo atualmente suportados são:

* Word (docx, .docm, .dotx, .dotm)
* PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)
* Excel (.xlsx, .xlsm)
* Formatos herddos do Office (.doc, .dot, etc.)
* Texto (.txt)
* HTML
* PDF

Arquivos binários como imagens (.jpg, .bmp, etc.) não são suportados. Por exemplo, se um arquivo .docx contiver apenas imagens, ele poderá ser ignorado porque não retornou nenhum conteúdo.
