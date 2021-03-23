---
title: Conector do Azure DevOps Graph para Pesquisa da Microsoft
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
description: Configurar o conector do Azure DevOps Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 9352f619e0a48bc2dac8441107f87f725211ab13
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031310"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Conector do Azure DevOps Graph (visualização)

O conector do Azure DevOps Graph permite que sua organização indexe itens de trabalho em sua instância do serviço Azure DevOps. Depois de configurar o conector e o conteúdo de índice do Azure DevOps, os usuários finais podem pesquisar esses itens na Pesquisa da Microsoft.

> [!NOTE]
> Leia o [**artigo Instalação do conector do Graph**](configure-connector.md) para entender as instruções gerais de configuração dos conectores do Graph.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector do Azure DevOps Graph. Ele complementa o processo de instalação geral e mostra instruções que se aplicam apenas ao conector do Azure DevOps Graph.

>[!IMPORTANT]
>O conector do Azure DevOps dá suporte apenas ao serviço de nuvem do Azure DevOps. Não há suporte para o Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 e TFS 2013.

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector graph no centro de administração do Microsoft 365

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão

Para se conectar à sua instância do Azure DevOps, você precisa do nome da organização do Azure [DevOps,](/azure/devops/organizations/accounts/create-organization) sua ID de aplicativo e segredo do cliente para autenticação OAuth.

### <a name="register-an-app"></a>Registrar um aplicativo

Registre um aplicativo no Azure DevOps para que o aplicativo da Pesquisa da Microsoft possa acessar a instância. Para saber mais, confira a documentação do Azure DevOps sobre como [registrar um aplicativo](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).

A tabela a seguir fornece orientações sobre como preencher o formulário de registro do aplicativo:

Campos Obrigatórios | Descrição | Valor Recomendado
--- | --- | ---
| Nome da empresa         | O nome da sua empresa. | Usar um valor apropriado   |
| Nome do aplicativo     | Um valor exclusivo que identifica o aplicativo que você está autorizando.    | Pesquisa da Microsoft     |
| Site do aplicativo  | A URL do aplicativo que solicitará acesso à sua instância do Azure DevOps durante a instalação do conector. (Obrigatório).  | https://<span>gcs.office.</span> com/
| URL de retorno de chamada de autorização        | Uma URL de retorno de chamada necessária para a que o servidor de autorização redireciona. | https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback|
| Escopos autorizados | O escopo de acesso para o aplicativo | Selecione os seguintes escopos: Identidade (leitura), Itens de Trabalho (leitura), Grupos Variáveis (leitura), Projeto e equipe (leitura), Graph (leitura)|

Ao registrar o aplicativo com os detalhes acima, você receberá a **ID** do aplicativo e o **Segredo** do Cliente que serão usados para configurar o conector.

>[!NOTE]
>Para revogar o acesso a qualquer aplicativo registrado no Azure DevOps, acesse Configurações do usuário na parte superior direita da instância do Azure DevOps. Selecione Perfil e, em seguida, selecione Autorizações na seção Segurança do painel lateral. Passe o mouse sobre um aplicativo OAuth autorizado para ver o botão Revogar no canto dos detalhes do aplicativo.

### <a name="connection-settings"></a>Configurações de conexão

Depois de registrar o aplicativo de Pesquisa da Microsoft com o Azure DevOps, você pode concluir a etapa de configurações de conexão. Insira o nome da sua organização, a ID do aplicativo e o segredo do cliente.

![Configurações do Aplicativo de Conexão](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>Configurar dados: selecionar projetos e campos

Você pode escolher a conexão para indexar toda a organização ou projetos específicos.

Se você optar por indexar toda a organização, os itens em todos os projetos da organização serão indexados. Novos projetos e itens serão indexados durante o próximo rastreamento depois que eles são criados.

Se você escolher projetos individuais, somente os itens de trabalho nesses projetos serão indexados.

![Configurar dados](media/ADO_Configure_data.png)

Em seguida, selecione quais campos você deseja que a conexão indexe e visualize dados nesses campos antes de prosseguir.

![Escolher propriedades](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

O conector do Azure DevOps dá suporte a permissões de pesquisa visíveis somente para pessoas com acesso a essa fonte de  **dados** ou a **Todos.** Se você escolher Somente pessoas com acesso a essa fonte de **dados,** os dados indexados aparecerão nos resultados da pesquisa para usuários que têm acesso a eles com base em permissões para usuários ou grupos no nível de caminho organização, projeto ou área no Azure DevOps. Se você escolher **Todos**, os dados indexados aparecerão nos resultados da pesquisa para todos os usuários.

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização

O conector do Azure DevOps dá suporte a agendas de atualização para rastreamentos completos e incrementais.
A agenda recomendada é de uma hora para um rastreamento incremental e um dia para um rastreamento completo.

## <a name="step-8-review-connection"></a>Etapa 8: Revisar conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->