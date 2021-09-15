---
title: Conector de Graph de Pesquisa da Microsoft
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
description: Configurar o conector de Graph do Graph Atlassian para Pesquisa da Microsoft
ms.openlocfilehash: 0b4b1dc0ed1f9e9d3ca57f98dc3878f63e68d510
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375602"
---
# <a name="atlassian-jira-graph-connector-preview"></a>Conector de Graph de Graph Atlassian (visualização)

O conector de Graph de Jira da Atlassian permite que sua organização indexe problemas Jira. Depois de configurar o conector e o conteúdo do índice a partir do site Jira, os usuários finais podem pesquisar esses itens Pesquisa da Microsoft.

> [!NOTE]
> Leia o [**artigo Instalação do conector Graph para**](configure-connector.md) entender as instruções gerais Graph configuração de conectores.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector de Graph Atlassian Jira. Ele complementa o processo de instalação geral e mostra instruções que se aplicam apenas ao conector de Graph Atlassian Jira.

>[!IMPORTANT]
>O conector de Graph Jira da Atlassian suporta apenas instâncias hospedadas na nuvem Jira. As versões do Jira Server e do Data Center Jira não são suportadas por esse conector.

## <a name="before-you-get-started"></a>Antes de começar
Você deve ser o administrador do locatário M365 da sua organização, bem como o administrador do site Jira da sua organização.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: adicionar um conector Graph no Centro de administração do Microsoft 365
Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão
Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão
Para se conectar ao site Jira, use a URL do site Jira. Uma URL de site de nuvem Jira normalmente se parece *com https://<organization_name>.atlassian.net/*. Você pode escolher Autenticação Básica ou OAuth 2.0 (recomendado) para autenticar no seu site Jira.

### <a name="basic-auth"></a>Basic Auth
Insira o nome de usuário da sua conta (geralmente ID de email) e o token de API para autenticar usando autenticação básica. Para saber mais sobre como gerar um token de API, consulte a documentação do Atlassian sobre como gerenciar tokens de API para sua [conta Atlassian.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Registre um aplicativo no Atlassian Jira para que o aplicativo Pesquisa da Microsoft possa acessar a instância. Para saber mais, confira Documentação de Suporte da Atlassian sobre como [habilitar o OAuth 2.0](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-).

As etapas a seguir fornecem orientações sobre como registrar o aplicativo:

1. Entre no console [do Desenvolvedor Atlassian](https://developer.atlassian.com/console/myapps/) com sua conta de administrador do Atlassian Jira.
2. Clique em `Create` e selecione `OAuth 2.0 integration`
3. Forneça um nome apropriado para o aplicativo e crie o novo aplicativo.
4. Navegue `Permissions` até a partir do painel de navegação à esquerda. Clique `Add` em `Jira platform REST API` . Depois de adicionado, `Configure` clique em e adicione os seguintes escopos - e `View Jira issue data` `Manage Jira global settings` `View user profiles` .
5. Navegue `Authorization` até a partir do painel de navegação à esquerda. Adicione a URL de retorno `https://gcs.office.com/v1.0/admin/oauth/callback` de chamada e salve as alterações.
6. Navegue `Settings` até a partir do painel de navegação à esquerda. Você receberá o `Client ID` e `Secret` nesta página.

Ao registrar o aplicativo com os detalhes acima, você obterá a **ID do Cliente** e **o Segredo.** Conclua a etapa de configurações de conexão usando-as.

### <a name="step-3a-configure-data-select-projects"></a>Etapa 3a: Configurar dados: Selecionar projetos

Você pode escolher a conexão para indexar todo o site Jira ou apenas projetos específicos.

* Se você optar por indexar todo o site Jira, os problemas Jira em todos os projetos do site serão indexados. Novos projetos e problemas serão indexados durante o próximo rastreamento depois que eles são criados.
* Se você escolher projetos individuais, somente os problemas Jira nesses projetos serão indexados.

Você pode optar ainda por filtrar os problemas Jira que serão indexados de duas maneiras.
* Especifique **o período de tempo modificado do problema**. Isso indexará apenas os problemas Jira criados ou modificados no período de tempo selecionado em uma base de rolagem **com** base no rastreamento atual.
* Especifique **o JQL**. Isso indexa apenas os problemas Jira retornados após a filtragem com base no Jira Query Language (JQL) fornecido. Para saber mais sobre como usar o JQL, consulte Documentação de Suporte atlassiano sobre como usar a pesquisa avançada com a [linguagem de consulta Jira](https://support.atlassian.com/jira-service-management-cloud/docs/use-advanced-search-with-jira-query-language-jql/)

> [!TIP]
> Você pode usar o filtro JQL para indexar apenas tipos de problema Jira específicos usando "*issueType in (Bug,Improvement)*"

### <a name="step-3b-configure-data-select-properties"></a>Etapa 3b: Configurar dados: Selecionar propriedades

Selecione quais campos você deseja que a conexão indexe e visualize dados nesses campos antes de prosseguir. Alguns campos já estão selecionados por padrão e não podem ser removidos.

O conector de Graph do Atlassian Jira pode indexar tanto os campos de problema padrão quanto os campos de problema criados personalizados.

> [!NOTE]
> Se um campo criado personalizado selecionado não estiver presente em alguns tipos de problema Jira, o campo será ingerido como *NULL* (em branco).

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

O conector de Graph do Atlassian dá suporte  **** a permissões de pesquisa visíveis para Todos ou Somente pessoas com acesso a essa fonte **de dados.** Se você escolher **Todos**, os dados indexados aparecerão nos resultados da pesquisa para todos os usuários. Se você escolher **Somente pessoas com acesso** a essa fonte de dados, os dados indexados aparecerão nos resultados da pesquisa para usuários que têm acesso a eles. No Atlassian Jira, as permissões de segurança são definidas usando esquemas de permissão de projeto que contêm grupos de nível de site e funções de projeto. A segurança do nível de problema também pode ser definida usando esquemas de permissão de nível de problema.

Se você escolher **Somente** pessoas com acesso a essa fonte de dados, você precisará escolher se seu site Jira tem usuários Azure Active Directory (AAD) provisionados ou usuários não AAD.

Para identificar qual opção é adequada para sua organização:

1. Escolha a **opção AAD** se a ID  de Email dos usuários Jira for igual à UPN (UserPrincipalName) de usuários no AAD.
2. Escolha a **opção Não-AAD** se a ID  de email dos usuários Jira for diferente do UserPrincipalName (UPN) de usuários no AAD. 

>[!NOTE]
> * Se você escolher a AAD como o tipo de fonte de identidade, o conector mapeia as IDs de Email dos usuários obtidos de Jira diretamente para a propriedade UPN do AAD.
> * Se você escolheu "Non-AAD" para o tipo de identidade, consulte Mapear suas Identidades não [Azure AD](map-non-aad.md) para obter instruções sobre como mapear as identidades. Você pode usar essa opção para fornecer a expressão regular de mapeamento de ID de Email para UPN.

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização

O conector de Graph de Jira da Atlassian dá suporte a agendas de atualização para rastreamentos completos e incrementais.
A agenda recomendada é de uma hora para um rastreamento incremental e um dia para um rastreamento completo.

## <a name="step-8-review-connection"></a>Etapa 8: Revisar conexão

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="troubleshooting"></a>Solução de problemas
Abaixo está uma lista de erros comuns observados durante a configuração do conector e seus possíveis motivos.

| Etapa de configuração | Mensagem de erro | Possíveis motivos |
| ------------ | ------------ | ------------ |
| Configurações de conexão | A solicitação está incorreta ou foi mal formada. | URL incorreta do site Jira |
| Configurações de conexão | Não é possível alcançar o serviço de nuvem Jira para seu site Jira. | URL incorreta do site Jira |
| Configurações de conexão | O cliente não tem permissão para executar a ação. | Token de API inválido fornecido para auth básico |


## <a name="limitations"></a>Limitações
A seguir estão as limitações conhecidas do conector de Graph do Atlassian Jira:
* As versões do Servidor Jira e do Data Center não são suportadas.