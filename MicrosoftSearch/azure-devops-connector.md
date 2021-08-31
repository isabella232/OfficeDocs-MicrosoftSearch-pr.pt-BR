---
title: Azure DevOps Graph conector para Pesquisa da Microsoft
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
description: Configurar o conector Azure DevOps Graph para Pesquisa da Microsoft
ms.openlocfilehash: fcf381a92ef397f900b300ca667fa80067a6672a
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701386"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Azure DevOps Graph conector (visualização)

O Azure DevOps Graph conector permite que sua organização indexe itens de trabalho em sua instância do Azure DevOps serviço. Depois de configurar o conector e o conteúdo de índice Azure DevOps, os usuários finais poderão pesquisar esses itens Pesquisa da Microsoft.

> [!NOTE]
> Leia o [**artigo Instalação do conector Graph para**](configure-connector.md) entender as instruções gerais Graph configuração de conectores.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector Azure DevOps Graph usuário. Ele complementa o processo de instalação geral e mostra instruções que se aplicam apenas ao conector Azure DevOps Graph de segurança.

>[!IMPORTANT]
>O Azure DevOps conector suporta apenas o serviço Azure DevOps nuvem. Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 e TFS 2013 não são suportados por esse conector.

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: adicionar um conector Graph no Centro de administração do Microsoft 365

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão

Para se conectar à sua instância Azure DevOps, você [](/azure/devops/organizations/accounts/create-organization) precisa do nome da sua Azure DevOps, sua ID de aplicativo e segredo do cliente para autenticação OAuth.

### <a name="register-an-app"></a>Registrar um aplicativo

Registre um aplicativo no Azure DevOps para que o Pesquisa da Microsoft possa acessar a instância. Para saber mais, confira Azure DevOps sobre como registrar [um aplicativo.](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)

A tabela a seguir fornece orientações sobre como preencher o formulário de registro do aplicativo:

Campos Obrigatórios | Descrição | Valor Recomendado
--- | --- | ---
| Nome da empresa         | O nome da sua empresa. | Usar um valor apropriado   |
| Nome do aplicativo     | Um valor exclusivo que identifica o aplicativo que você está autorizando.    | Pesquisa da Microsoft     |
| Site do aplicativo  | A URL do aplicativo que solicitará acesso à sua instância Azure DevOps durante a instalação do conector. (Obrigatório).  | https://<span>gcs.office.</span> com/
| URL de retorno de chamada de autorização        | Uma URL de retorno de chamada necessária para a que o servidor de autorização redireciona. | https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback|
| Escopos autorizados | O escopo de acesso para o aplicativo | Selecione os seguintes escopos: Identidade (leitura), Itens de Trabalho (leitura), Grupos Variáveis (leitura), Project e equipe (leitura), Graph (leitura), Análise (leitura)|

>[!IMPORTANT]
>Os escopos autorizados selecionados para o aplicativo devem corresponder aos escopos exatamente como listado acima. Se você omitir um dos escopos autorizados na lista ou adicionar outro escopo, a autorização falhará.

Ao registrar o aplicativo com os detalhes acima, você receberá a **ID** do aplicativo e o **Segredo** do Cliente que serão usados para configurar o conector.

>[!NOTE]
>Para revogar o acesso a qualquer aplicativo registrado Azure DevOps, acesse Configurações do usuário na parte superior direita da sua Azure DevOps. Selecione Perfil e, em seguida, selecione Autorizações na seção Segurança do painel lateral. Passe o mouse sobre um aplicativo OAuth autorizado para ver o botão Revogar no canto dos detalhes do aplicativo.

### <a name="connection-settings"></a>Configurações de conexão

Após registrar o aplicativo Pesquisa da Microsoft com Azure DevOps, você pode concluir a etapa de configurações de conexão. Insira o nome da sua organização, a ID do aplicativo e o segredo do cliente.

![Conexão aplicativo Configurações.](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>Configurar dados: selecionar projetos e campos

Você pode escolher a conexão para indexar toda a organização ou projetos específicos.

Se você optar por indexar toda a organização, os itens em todos os projetos da organização serão indexados. Novos projetos e itens serão indexados durante o próximo rastreamento depois que eles são criados.

Se você escolher projetos individuais, somente os itens de trabalho nesses projetos serão indexados.

![Configurar dados.](media/ADO_Configure_data.png)

Em seguida, selecione quais campos você deseja que a conexão indexe e visualize dados nesses campos antes de prosseguir.

![Escolha propriedades.](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

O Azure DevOps conector dá suporte a permissões de pesquisa visíveis somente para pessoas com acesso a essa fonte de  **dados** ou a **Todos.** Se você escolher Somente pessoas com acesso a essa fonte de **dados,** os dados indexados aparecerão nos resultados da pesquisa para usuários que têm acesso a eles com base em permissões para usuários ou grupos na Organização, nível de caminho de Project ou Área no Azure DevOps. Se você escolher **Todos**, os dados indexados aparecerão nos resultados da pesquisa para todos os usuários.

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização

O Azure DevOps conector suporta agendamentos de atualização para rastreamentos completos e incrementais.
A agenda recomendada é de uma hora para um rastreamento incremental e um dia para um rastreamento completo.

## <a name="step-8-review-connection"></a>Etapa 8: Revisar conexão

Siga as instruções [gerais de instalação](./configure-connector.md).

>[!TIP]
>**Tipo de resultado padrão**
>* O Azure DevOps conector registra automaticamente um tipo [de resultado](./customize-search-page.md#step-2-create-result-types) depois que o conector é publicado. O tipo de resultado usa um layout de [resultado](./customize-results-layout.md) gerado dinamicamente com base nos campos selecionados na etapa 3. 
>* Você pode gerenciar o tipo de resultado navegando até [**Tipos de**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) resultado no [Centro de administração do Microsoft 365](https://admin.microsoft.com). O tipo de resultado padrão será nomeado como " `ConnectionId` Padrão". Por exemplo, se sua id de conexão for `AzureDevOps` , seu layout de resultado será nomeado: "AzureDevOpsDefault"
>* Além disso, você pode optar por criar seu próprio tipo de resultado, se necessário.

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="troubleshooting"></a>Solução de problemas
A seguir, um erro comum observado durante a configuração do conector e seu possível motivo.

| Etapa de configuração | Mensagem de erro | Possíveis motivos |
| ------------ | ------------ | ------------ |
|  | `The account associated with the connector doesn't have permission to access the item.` | O aplicativo registrado não tem nenhum dos escopos OAuth necessários. (Observação - Um novo requisito de escopo OAuth 'Analytics:read' foi introduzido em 31/08/2021)  |

<!---## Limitations-->
<!---Insert limitations for this data source-->