---
title: Conector do Graph de compartilhamento de arquivos para a Pesquisa da Microsoft
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
ROBOTS: NoIndex
description: Configurar o conector gráfico de compartilhamento de arquivos para a Pesquisa da Microsoft
ms.openlocfilehash: 792e853e5d2b7a23835dc031ff4ba4c09d619f9c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031607"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>Conector graph de compartilhamento de arquivos

O conector graph de compartilhamento de arquivos permite que os usuários em sua organização pesquisem compartilhamentos de arquivos do Windows no local.

> [!NOTE]
> Leia o [**artigo Instalação do conector do Graph**](configure-connector.md) para entender o processo de configuração geral dos conectores do Graph.

## <a name="before-you-get-started"></a>Antes de começar

### <a name="install-the-graph-connector-agent"></a>Instalar o agente de conector do Graph

Para indexar seus compartilhamentos de arquivos do Windows, você deve instalar e registrar o agente conector do Graph. Consulte [Instalar o agente de conector do Graph](on-prem-agent.md) para saber mais.  

### <a name="content-requirements"></a>Requisitos de conteúdo

### <a name="file-types"></a>Tipos de arquivo

O conteúdo dos seguintes formatos pode ser indexado e pesquisado: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP. Somente o conteúdo textual desses formatos é indexado. Todo o conteúdo multimídia é ignorado. Para qualquer arquivo que não pertença a esse formato, os metadados são indexados.

### <a name="file-size-limits"></a>Limites de tamanho de arquivo

O tamanho máximo do arquivo com suporte é de 100 MB. Os arquivos que excedem 100 MB não são indexados. O limite máximo de tamanho pós-processado é 4 MB. O processamento é interrompido quando o tamanho de um arquivo atinge 4 MB. Portanto, algumas frases presentes no arquivo podem não funcionar para pesquisa.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector graph no centro de administração do Microsoft 365

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão

Na página **Conectar-se à fonte de** dados, selecione **Compartilhamento** de arquivos e forneça o nome, a ID da conexão e a descrição. Na próxima página, forneça o caminho para o compartilhamento de arquivos e selecione o agente de conector do Graph instalado anteriormente. Insira as credenciais de uma conta de usuário do [Microsoft Windows](https://microsoft.com/windows) com acesso de leitura a todos os arquivos no compartilhamento de arquivos.

### <a name="preserve-last-access-time"></a>Preservar a última hora de acesso

Quando o conector tenta rastrear um arquivo, o campo "última hora de acesso" em seus metadados é atualizado. Se você depender desse campo para qualquer solução de arquivamento e backup e não quiser atualizá-lo quando o conector acessá-lo, você poderá configurar essa opção na página Configurações **Avançadas.**

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

Você pode restringir a permissão para pesquisar qualquer arquivo com base em Listas de Controle do Share Access ou Listas de Controle de Acesso do Sistema de Arquivos de Nova Tecnologia (NTFS), selecionando a opção desejada na página Gerenciar permissões **de** pesquisa. As contas de usuário e os grupos fornecidos nessas Listas de Controle de Acesso devem ser gerenciados pelo Active Directory (AD). Se você estiver usando qualquer outro sistema para gerenciamento de contas de usuário, poderá selecionar a opção "todos", que permite que os usuários pesquisem todos os arquivos sem restrições de acesso. No entanto, quando os usuários tentam abrir o arquivo, os controles de acesso definidos na origem se aplicam.

Observe que as janelas por padrão fornece permissão 'Ler' para 'Todos' em AcLs do Share quando uma pasta é compartilhada na rede. Por extensão, se você estiver escolhendo Compartilhar ACLs em **Gerenciar** permissões de pesquisa, os usuários poderão pesquisar todos os arquivos. Se você quiser restringir o acesso, remova o acesso 'Leitura' para 'Todos' em compartilhamentos de arquivos e forneça acesso somente aos usuários e grupos desejados. Em seguida, o conector lê essas restrições de acesso e as aplica à pesquisa.

Você pode escolher Compartilhar ACLs somente se o caminho de compartilhamento fornecido seguir o formato de caminho UNC. Você pode criar um caminho no formato UNC indo para 'Compartilhamento Avançado' na opção 'Compartilhamento'.

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Etapa 8: Revisar conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->