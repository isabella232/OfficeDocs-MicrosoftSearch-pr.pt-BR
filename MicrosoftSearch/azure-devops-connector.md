---
title: Conector do Azure DevOps Graph para a Pesquisa da Microsoft
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
description: Configurar o conector do Azure DevOps Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 8fe783c847c672223e051f4433af3e41678fe367
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097399"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Conector do Azure DevOps Graph (visualização)

O conector do Azure DevOps Graph permite que sua organização indexe itens de trabalho em sua instância do serviço Azure DevOps. Depois de configurar o conector e o conteúdo de índice do Azure DevOps, os usuários finais podem procurar esses itens na Pesquisa da Microsoft.

> [!NOTE]
> Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.

Este artigo é destinado a qualquer pessoa que configure, seja executado e monitore um conector do Azure DevOps Graph. Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector do Azure DevOps Graph.

>[!IMPORTANT]
>O conector do Azure DevOps é compatível apenas com o serviço de nuvem do Azure DevOps. O Azure DevOps Server 2019, o TFS 2018, o TFS 2017, o TFS 2015 e o TFS 2013 não são compatíveis com esse conector.

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Definir as configurações de conexão

Para se conectar à instância do Azure DevOps, [](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) você precisa do nome da organização do Azure DevOps, da ID do aplicativo e do segredo do cliente para autenticação OAuth.

### <a name="register-an-app"></a>Registrar um aplicativo

Registre um aplicativo no Azure DevOps para que o aplicativo Pesquisa da Microsoft possa acessar a instância. Para saber mais, consulte a documentação do Azure DevOps sobre como [registrar um aplicativo.](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)

A tabela a seguir fornece orientações sobre como preencher o formulário de registro do aplicativo:

Campos obrigatórios | Descrição | Valor Recomendado
--- | --- | ---
| Nome da Empresa         | O nome da sua empresa. | Usar um valor apropriado   |
| Nome do aplicativo     | Um valor exclusivo que identifica o aplicativo que você está autorizando.    | Pesquisa da Microsoft     |
| Site do aplicativo  | A URL do aplicativo que solicitará acesso à instância do Azure DevOps durante a configuração do conector. (Obrigatório).  | https://<span>gcs.office.</span> com/
| URL de retorno de chamada de autorização        | Uma URL de retorno de chamada necessária para a que o servidor de autorização redireciona. | https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback|
| Escopos autorizados | O escopo de acesso para o aplicativo | Selecione os seguintes escopos: Identidade (leitura), Itens de Trabalho (lidos), Grupos de Variáveis (lidos), Projeto e equipe (lido), Gráfico (lido)|

Ao registrar o aplicativo com os detalhes acima, você  receberá a **ID** do aplicativo e o Segredo do Cliente que serão usados para configurar o conector.

>[!NOTE]
>Para revogar o acesso a qualquer aplicativo registrado no Azure DevOps, vá para Configurações do usuário na parte superior direita da instância do Azure DevOps. Selecione Perfil e Autorizações na seção Segurança do painel lateral. Passe o mouse sobre um aplicativo OAuth autorizado para ver o botão Revogar no canto dos detalhes do aplicativo.

### <a name="connection-settings"></a>Configurações de conexão

Depois de registrar o aplicativo pesquisa da Microsoft com o Azure DevOps, você pode concluir a etapa de configurações de conexão. Insira o nome da sua organização, a ID do aplicativo e o segredo do cliente.

![Configurações do Aplicativo de Conexão](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>Configurar dados: selecionar projetos e campos

Você pode escolher a conexão para indexar toda a organização ou projetos específicos.

Se você optar por indexar toda a organização, os itens em todos os projetos da organização serão indexados. Novos projetos e itens serão indexados durante o próximo rastreamento depois que eles são criados.

Se você escolher projetos individuais, somente os itens de trabalho nesses projetos serão indexados.

![Configurar dados](media/ADO_Configure_data.png)

Em seguida, selecione quais campos você deseja que a conexão indexe e visualize dados nesses campos antes de prosseguir.

![Escolher propriedades](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

O conector do Azure DevOps dá suporte a permissões de pesquisa visíveis apenas para pessoas com acesso a essa fonte de  **dados** ou **a Todos.** Se você escolher Apenas as pessoas com acesso a essa fonte de **dados,** os dados indexados aparecerão nos resultados da pesquisa para usuários que têm acesso a eles com base nas permissões para usuários ou grupos no nível do caminho organização, projeto ou área no Azure DevOps. Se você escolher **Todos,** os dados indexados aparecerão nos resultados da pesquisa para todos os usuários.

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização

O conector do Azure DevOps dá suporte a agendamentos de atualização para rastreamentos completos e incrementais.
O agendamento recomendado é de uma hora para um rastreamento incremental e um dia para um rastreamento completo.

## <a name="step-8-review-connection"></a>Etapa 8: Analisar a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
