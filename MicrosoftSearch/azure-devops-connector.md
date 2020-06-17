---
title: Azure DevOps Connector para Microsoft Search
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do Azure DevOps para o Microsoft Search
ms.openlocfilehash: f424cf2be2e701bbdfc21a67bfcc3c3d5cf5e866
ms.sourcegitcommit: 582c24fa3c5b960a4026d6af212044ba7da25e59
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44742180"
---
# <a name="azure-devops-connector"></a>Conector DevOps do Azure

Com o conector DevOps do Azure, sua organização pode indexar itens de trabalho em sua instância do serviço do Azure DevOps. Depois de configurar o conector e o conteúdo do índice do Azure DevOps, os usuários finais podem pesquisar esses itens no Microsoft Search.

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector do DevOps do Azure. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

>[!IMPORTANT]
>O conector do Azure DevOps oferece suporte somente ao serviço de nuvem do Azure DevOps. O Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 e TFS 2013 não são suportados por esse conector.

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados

Para se conectar à sua instância do Azure DevOps, você precisa do seu Azure DevOps nome da [organização](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) , sua ID do aplicativo e o segredo do cliente para autenticação OAuth.

### <a name="register-an-app"></a>Registrar um aplicativo

Você deve registrar um aplicativo no Azure DevOps para que o aplicativo de pesquisa da Microsoft possa acessar a instância. Para saber mais, confira a documentação do Azure DevOps sobre como [registrar um aplicativo](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).

A tabela a seguir fornece orientação sobre como preencher o formulário de registro de aplicativo:

 **Campos obrigatórios** | **Descrição**      | **Valor recomendado**
--- | --- | ---
| Nome da empresa         | Este é o nome da sua empresa. | Usar um valor apropriado   |
| Nome do aplicativo     | Esse valor exclusivo identifica o aplicativo que você está autorizando.    | Pesquisa da Microsoft     |
| Site do aplicativo  | Este campo obrigatório é a URL do aplicativo que solicitará acesso à instância do DevOps do Azure durante a configuração do conector.  | <https://gcs.office.com/>                |
| URL de retorno de chamada de autorização        | Uma URL de retorno de chamada necessária para a qual o servidor de autorização é redirecionado. | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| Escopos autorizados | Este é o escopo de acesso para o aplicativo | Selecione os seguintes escopos: identidade (leitura), itens de trabalho (leitura), grupos de variáveis (leitura), projeto e equipe (leitura)|

Ao registrar o aplicativo com os detalhes acima, você receberá a **ID do aplicativo** e o **segredo do cliente** que será usado para configurar o conector.

>[!NOTE]
>Para revogar o acesso a qualquer aplicativo registrado no Azure DevOps, acesse configurações do usuário na parte superior direita de sua instância do Azure DevOps. Clique em perfil e, em seguida, clique em autorizações na seção segurança do painel lateral. Passe o mouse sobre um aplicativo OAuth autorizado para ver o botão revogar no canto dos detalhes do aplicativo.

### <a name="connection-settings"></a>Configurações de conexão

Após registrar o aplicativo de pesquisa da Microsoft com o Azure DevOps, você pode concluir a etapa de configurações de conexão. Insira o nome da sua organização, a ID do aplicativo e o segredo do cliente.

![Configurações do aplicativo de conexão](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a>Selecionar projetos e campos

Você pode escolher para que a conexão seja indexada para toda a organização ou para projetos específicos.

Se você optar por indexar toda a organização, os itens em todos os projetos da organização serão indexados. Novos projetos e itens serão indexados durante o próximo rastreamento após serem criados. Se você escolher projetos individuais, somente os itens de trabalho nesses projetos serão indexados.

![Configurar dados](media/ADO_Configure_data.png)

Em seguida, selecione quais campos você deseja que a conexão indexe e visualize dados nesses campos antes de prosseguir.

![Escolher Propriedades](media/ADO_choose_properties.png)

## <a name="manage-the-search-schema"></a>Gerenciar o esquema de pesquisa

Configure o mapeamento de esquema de pesquisa. Você pode escolher quais propriedades tornar **consultáveis**, **pesquisáveis** e **recuperáveis**.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa

No momento, o conector do Azure DevOps oferece suporte apenas **às permissões de pesquisa visíveis para todos**. Dados indexados aparecerão nos resultados da pesquisa para todos os usuários.

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização

O conector do Azure DevOps suporta agendas de atualização para rastreamentos completos e incrementais. Um rastreamento completo localiza itens de trabalho excluídos que foram sincronizados anteriormente com o índice de pesquisa da Microsoft. Um rastreamento completo é executado para sincronizar todos os itens de trabalho. Para sincronizar novos itens de trabalho e atualizações para itens de trabalho existentes, você precisa agendar rastreamentos incrementais.

O cronograma recomendado é uma hora para um rastreamento incremental e um dia para um rastreamento completo.
