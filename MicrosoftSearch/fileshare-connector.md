---
title: Conector do Graph de compartilhamento de arquivos para a Pesquisa da Microsoft
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
ROBOTS: NoIndex
description: Configurar o conector do Graph de compartilhamento de arquivos para a Pesquisa da Microsoft
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097417"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>Conector do Graph de compartilhamento de arquivos

O conector do Graph de compartilhamento de arquivos permite que os usuários em sua organização pesquisem compartilhamentos de arquivos locais do Windows.

> [!NOTE]
> Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.

## <a name="before-you-get-started"></a>Antes de começar

### <a name="install-the-graph-connector-agent"></a>Instalar o agente do conector do Graph

Para indexar seus compartilhamentos de arquivos do Windows, você deve instalar e registrar o agente do conector do Graph. Consulte [Instalar o agente do conector do Graph](on-prem-agent.md) para saber mais.  

### <a name="content-requirements"></a>Requisitos de conteúdo

### <a name="file-types"></a>Tipos de arquivo

O conteúdo dos seguintes formatos pode ser indexado e pesquisado: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP. Somente o conteúdo textual desses formatos é indexado. Todo o conteúdo multimídia é ignorado. Para qualquer arquivo que não pertença a esse formato, os metadados são indexados.

### <a name="file-size-limits"></a>Limites de tamanho de arquivo

O tamanho máximo de arquivo com suporte é de 100 MB. Os arquivos com mais de 100 MB não são indexados. O limite máximo de tamanho pós-processado é de 4 MB. O processamento é interrompido quando o tamanho de um arquivo atinge 4 MB. Portanto, algumas frases presentes no arquivo podem não funcionar para pesquisa.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Definir as configurações de conexão

Na página **Conectar-se à fonte de dados,** selecione **compartilhamento de** arquivos e forneça o nome, a ID da conexão e a descrição. Na próxima página, forneça o caminho para o compartilhamento de arquivos e selecione o agente de conector do Graph instalado anteriormente. Insira as credenciais de uma conta [de usuário do Microsoft Windows](https://microsoft.com/windows) com acesso de leitura a todos os arquivos no compartilhamento de arquivos.

### <a name="preserve-last-access-time"></a>Preservar a hora do último acesso

Quando o conector tenta rastrear um arquivo, o campo "horário do último acesso" em seus metadados é atualizado. Se você depender desse campo para qualquer solução de arquivamento e backup e não quiser atualizá-lo quando o conector o acessar, poderá configurar essa opção na página Configurações **Avançadas.**

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

Você pode restringir a permissão para pesquisar qualquer arquivo com base em Listas de Controle de Acesso de Compartilhamento ou Listas de Controle de Acesso do Sistema de Arquivos de Nova Tecnologia (NTFS). Se você quiser usar As Listas de Controle de Acesso, selecione a opção apropriada na **página Configurações Avançadas.** Se você quiser usar listas de controle de acesso NTFS, selecione a opção apropriada na **página Gerenciar permissões de** pesquisa.

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Etapa 8: Analisar a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
