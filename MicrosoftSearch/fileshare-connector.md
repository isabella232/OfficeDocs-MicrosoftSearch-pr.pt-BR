---
title: Conector de compartilhamento de arquivos
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurar o conector de compartilhamento de arquivos para o Microsoft Search
ms.openlocfilehash: bf9fb730abd4ca6e42b681893525bbe3dd8a1419
ms.sourcegitcommit: 249f41723dd6fda1e93ee1a8f3f7571ef066454b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750893"
---
# <a name="file-share-connector"></a>Conector de compartilhamento de arquivos

Com o conector de gráfico de compartilhamento de arquivos, os usuários da sua organização podem pesquisar compartilhamentos de arquivos do Windows locais.

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector de compartilhamento de arquivos. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

## <a name="install-graph-connector-agent"></a>Instalar o agente do conector do Graph

Para indexar seus compartilhamentos de arquivos do Windows, você deve instalar e registrar o software de [agente do conector do Graph](on-prem-agent.md) .

## <a name="content-requirements"></a>Requisitos de conteúdo

### <a name="file-types"></a>Tipos de arquivo

O conteúdo dos seguintes formatos pode ser indexado e pesquisado: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, NWS, OBT, OBD,, PPS, ODS, ODT, a, PDF, POT e PPS, o e o formato. XLS, o, o, o XML e o formato ZIP do. Somente o conteúdo textual desses formatos é indexado. Todo o conteúdo multimídia é ignorado. Para qualquer arquivo que não pertença a esse formato, os metadados sozinhos serão indexados.

### <a name="file-size-limits"></a>Limites de tamanho de arquivo

O tamanho máximo de arquivo com suporte é de 100 MB. Arquivos que excederem 100 MB não serão indexados. O limite máximo de tamanho processado é de 4 MB. O processamento pára quando o tamanho de um arquivo atinge 4 MB. Portanto, algumas frases presentes no arquivo podem não funcionar para pesquisa.

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados

Na página **conectar-se à fonte de dados** , selecione **compartilhamento de arquivos** e forneça o nome, a ID de conexão e a descrição. Na próxima página, forneça o caminho para o compartilhamento de arquivos e selecione seu agente do conector de gráfico instalado anteriormente. Insira as credenciais de uma conta de usuário do [Microsoft Windows](https://microsoft.com/windows) com acesso de leitura a todos os arquivos no compartilhamento de arquivos.

## <a name="preserve-last-access-time"></a>Preservar o horário do último acesso

Quando o conector tenta rastrear um arquivo, o campo "último horário de acesso" em seus metadados é atualizado. Se você depender desse campo para qualquer solução de arquivamento e backup e não quiser atualizá-lo quando o conector acessá-lo, você pode configurar essa opção na página **Configurações avançadas** .

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa

Você pode restringir a permissão para pesquisar qualquer arquivo com base nas listas de controle de acesso do compartilhamento ou nas listas de controle de acesso do sistema de arquivos de novas tecnologias (NTFS). Se você quiser usar as listas de controle de acesso de compartilhamento, selecione a opção apropriada na página **Configurações avançadas** . Se quiser usar as listas de controle de acesso NTFS, selecione a opção apropriada na página **gerenciar permissões de pesquisa** .

## <a name="assign-property-labels"></a>Atribuir rótulos de propriedade

Você pode atribuir uma propriedade Source a cada rótulo escolhendo a partir de um menu de opções. Embora esta etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.

## <a name="manage-schema"></a>Gerenciar esquema

Na tela **gerenciar esquema** , você tem a opção de alterar os atributos de esquema (**consultável**, **pesquisável**, **recuperável** e **refinável**) associados às propriedades, adicionar aliases opcionais e escolher a propriedade **Content** .

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização

O intervalo de agendamento de atualização padrão recomendado é de 15 minutos, mas você pode alterá-lo com base em suas preferências.

## <a name="result-layout"></a>Layout do resultado

Recomendamos que você use o layout de resultado padrão para exibir os resultados do conector FileShare, pois ele tem ícones e controles apropriados que o ajudam a navegar até o caminho do arquivo. Se você criar um novo layout de resultado, ele substituirá o padrão.
