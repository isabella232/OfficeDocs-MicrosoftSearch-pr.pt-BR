---
title: Conector de nuvem Graph confluência para Pesquisa da Microsoft
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector de Graph Nuvem de Confluência para Pesquisa da Microsoft
ms.openlocfilehash: baf6139257c8bf8e40bc997e2a408efb4fc2549f
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973366"
---
<!---Previous ms.author: kam1 --->

# <a name="confluence-cloud-graph-connector-preview"></a>Conector de nuvem Graph confluência (Visualização)

O conector de nuvem Graph confluência permite que sua organização indexe o conteúdo de Confluência. Depois de configurar o conector e os dados de índice do site confluência, os usuários finais podem pesquisar por esse conteúdo em Pesquisa da Microsoft.

>[!NOTE]
>Confluence Cloud Graph Connector está em visualização. Se você deseja obter acesso antecipado para experimentar, inscreva-se usando [<b> este formulário </b>](https://forms.office.com/r/duLxv8Nf8U).  

Este artigo é para Microsoft 365 administradores ou qualquer pessoa que configure, executa e monitore um conector Graph Nuvem de Confluência. Ele complementa as instruções gerais fornecidas no [artigo Configurar seu](configure-connector.md) Graph conector. Se você ainda não tiver feito isso, leia todo o artigo Configurar o conector Graph para entender o processo de instalação geral.

Cada etapa no processo de instalação é listada abaixo juntamente com uma observação que indica que você deve seguir as instruções [](#troubleshooting) gerais de instalação OU outras instruções que se aplicam apenas ao conector de Graph nuvem de confluência, incluindo informações sobre Solução de Problemas e Limitações. [](#limitations)


## <a name="before-you-get-started"></a>Antes de começar
Você deve ser o administrador do locatário M365 da sua organização, bem como o administrador do site de Confluência da sua organização.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: adicionar um conector Graph no Centro de administração do Microsoft 365
Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão
Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão
Para se conectar ao site confluência, use a URL do site. Uma URL de site de nuvem de confluência normalmente se parece *com https://<organization_name>.atlassian.net/*. Você pode escolher Autenticação Básica ou OAuth 2.0 (recomendado) para autenticar no seu site de Confluência.

### <a name="basic-auth"></a>Basic Auth
Insira o nome de usuário da sua conta (geralmente ID de email) e o token de API para autenticar usando autenticação básica. Para saber mais sobre como gerar um token de API, consulte a documentação do Atlassian sobre como gerenciar tokens de API para sua [conta Atlassian.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Registre um aplicativo na Nuvem de Confluência para que o Pesquisa da Microsoft possa acessar a instância. Para saber mais, confira Documentação de Suporte da Atlassian sobre como [habilitar o OAuth 2.0](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-).

As etapas a seguir fornecem orientações sobre como registrar o aplicativo:

1. Entre no [console do Desenvolvedor Atlassian](https://developer.atlassian.com/console/myapps/) com sua conta de administrador da Confluência Atlassian.
2. Clique em `Create` e selecione `OAuth 2.0 integration`
3. Forneça um nome apropriado para o aplicativo e crie o novo aplicativo.
4. Navegue `Permissions` até a partir do painel de navegação à esquerda. Clique `Add` em `Confluence API` . Depois de adicionado, `Configure` clique em e adicione os seguintes escopos - , , , `Read Confluence space summary` , , , , e `Read Confluence content properties` `Read Confluence detailed content` `Read Confluence content summary` `Read content permission in Confluence` `Read user` `Read user groups` `Search Confluence content and space summaries` .
5. Navegue `Authorization` até a partir do painel de navegação à esquerda. Adicione a URL de retorno `https://gcs.office.com/v1.0/admin/oauth/callback` de chamada e salve as alterações.
6. Navegue `Settings` até a partir do painel de navegação à esquerda. Você receberá o `Client ID` e `Secret` nesta página.

Ao registrar o aplicativo com os detalhes acima, você obterá a **ID do Cliente** e **o Segredo.** Conclua a etapa de configurações de conexão usando-as.

## <a name="step-4-select-properties-and-filter-data"></a>Etapa 4: selecionar propriedades e filtrar dados

Nesta etapa, você pode adicionar ou remover propriedades disponíveis de sua fonte de dados confluência. Microsoft 365 já selecionou algumas propriedades por padrão.

Com uma cadeia de caracteres CQL (Linguagem de Consulta de Confluência), você pode especificar condições para sincronizar páginas. É como uma cláusula **Where** em uma **instrução SQL Select.** Por exemplo, você pode optar por indexar somente as páginas modificadas nos últimos dois anos. Para saber mais sobre como criar sua própria cadeia de caracteres de consulta, consulte [Pesquisa Avançada usando CQL](https://developer.atlassian.com/server/confluence/advanced-searching-using-cql/). Por padrão, todos os blogs e páginas serão indexados pelo conector.

Use o botão de resultados de visualização para verificar os valores de exemplo das propriedades selecionadas e da cadeia de caracteres CQL.

## <a name="step-5-manage-search-permissions"></a>Etapa 5: Gerenciar permissões de pesquisa

O conector de nuvem Graph confluência dá suporte a permissões de pesquisa visíveis para  **Todas ou** Somente pessoas com acesso a essa fonte **de dados.** Se você escolher **Todos**, os dados indexados aparecerão nos resultados da pesquisa para todos os usuários. Se você escolher **Somente pessoas com acesso** a essa fonte de dados, os dados indexados aparecerão nos resultados da pesquisa para usuários que têm acesso a eles.

Na Nuvem de Confluência, as permissões de segurança para usuários e grupos são definidas usando permissões de espaço e restrições de página. Confluence Cloud Graph Connector aplica permissões de espaço se não houver restrições de página. As restrições de nível de página, se presentes, terão precedência sobre permissões de espaço.

Se você escolher **Somente** pessoas com acesso a essa fonte de dados, será necessário escolher se o site confluência tem usuários provisionados Azure Active Directory (AAD) ou usuários não AAD.

Para identificar qual opção é adequada para sua organização:

1. Escolha a **opção AAD** se a ID  de Email dos usuários confluência for igual à UPN (UserPrincipalName) de usuários no AAD.
2. Escolha a **opção Não-AAD** se a ID  de email dos usuários confluência for diferente do UserPrincipalName (UPN) de usuários no AAD. 

>[!NOTE]
> * Se você escolher a AAD como o tipo de fonte de identidade, o conector mapeia as IDs de Email dos usuários obtidos da Confluência diretamente para a propriedade UPN do AAD.
> * Se você escolheu "Non-AAD" para o tipo de identidade, consulte Mapear suas Identidades não [Azure AD](map-non-aad.md) para obter instruções sobre como mapear as identidades. Você pode usar essa opção para fornecer a expressão regular de mapeamento de ID de Email para UPN.

## <a name="step-6-assign-property-labels"></a>Etapa 6: Atribuir rótulos de propriedade

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-7-manage-schema"></a>Etapa 7: Gerenciar esquema

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-8-choose-refresh-settings"></a>Etapa 8: Escolher configurações de atualização

Siga as instruções [gerais de instalação](./configure-connector.md).

>[!NOTE]
>Para atualizações de permissão de acesso, somente o rastreamento completo agendado será aplicado.

## <a name="step-9-review-connection"></a>Etapa 9: Analisar Conexão

Siga as instruções [gerais de instalação](./configure-connector.md).

Depois de publicar a conexão, você precisa personalizar a página de resultados da pesquisa. Para saber mais sobre como personalizar resultados de pesquisa, consulte [Personalizar a página de resultados da pesquisa](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).

## <a name="troubleshooting"></a>Solução de problemas
Abaixo está uma lista de erros comuns observados durante a configuração do conector e seus possíveis motivos.

| Etapa de configuração | Mensagem de erro | Possíveis motivos |
| ------------ | ------------ | ------------ |
| Configurações de conexão | A solicitação está incorreta ou foi mal formada. | URL incorreta do site confluência |
| Configurações de conexão | Não é possível alcançar o serviço de nuvem confluência para seu site de Confluência. | URL incorreta do site confluência |
| Configurações de conexão | O cliente não tem permissão para executar a ação. | Token de API inválido fornecido para auth básico |
| Selecionar propriedades | Nenhuma mensagem de erro e nenhum resultado de visualização | Verifique se a consulta CQL é válida |

## <a name="limitations"></a>Limitações
O conector de Graph nuvem de confluência tem as seguintes limitações conhecidas em sua versão mais recente:

- O Conector de Nuvem de Confluência não indexa arquivos de anexos e comentários.
- As implantações do Servidor de Indexação e do Data Center serão lançadas como um conector separado.