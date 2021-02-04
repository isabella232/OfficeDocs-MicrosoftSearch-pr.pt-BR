---
title: Conector do Graph de sites corporativos para a Pesquisa da Microsoft
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
description: Configurar o conector do Graph de sites corporativos para a Pesquisa da Microsoft
ms.openlocfilehash: 526b36a798f50bed457832d576ffebd15820184d
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097426"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a>Conector do Graph de sites corporativos

O conector do Graph de sites corporativos permite que sua organização indexe artigos e **conteúdo de seus sites voltados para o interior.** Depois de configurar o conector e sincronizar o conteúdo do site, os usuários finais podem pesquisar esse conteúdo em qualquer cliente da Pesquisa da Microsoft.

> [!NOTE]
> Leia o artigo [**Configurar seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.

Este artigo é destinado a qualquer pessoa que configure, seja executado e monitore um conector de sites corporativos. Ele complementa o processo de configuração geral e mostra instruções que se aplicam somente ao conector de sites corporativos. Este artigo também inclui informações sobre solução [de problemas](#troubleshooting) e [limitações.](#limitations)

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Definir as configurações de conexão

Para se conectar à sua fonte de dados, você precisa preencher a URL raiz do site, selecionar uma fonte de rastreamento e o tipo de autenticação que você gostaria de usar: None, Basic Authentication ou OAuth 2.0 com [o Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/) Depois de concluir essas informações, selecione Testar Conexão para verificar suas configurações.

### <a name="url"></a>URL

Use o campo URL para especificar a raiz do site que você gostaria de rastrear. O conector de sites corporativos usará essa URL como ponto de partida e seguirá todos os links dessa URL para seu rastreamento.

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>Modo de rastreamento: nuvem ou local (visualização)

O modo de rastreamento determina o tipo de sites que você deseja indexar, na nuvem ou no local. Para os sites da nuvem, selecione **Nuvem** como o modo de rastreamento.

Além disso, o conector agora dá suporte ao rastreamento de sites locais. Esse modo está em visualização. Para acessar seus dados locais, você deve primeiro instalar e configurar o agente do conector do Graph. Para saber mais, consulte Agente [de conector do Graph.](https://docs.microsoft.com/microsoftsearch/on-prem-agent)

Para seus sites locais,  selecione Agente como o  modo de rastreamento e, no campo Agente Local, escolha o agente do conector do Graph que você instalou e configurou anteriormente.  

> [!div class="mx-imgBorder"]
> ![Captura de tela do painel Configurações de Conexão para o Enterprise Web Connector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>Autenticação

A Autenticação Básica requer um nome de usuário e senha. Crie essa conta de bot usando o Centro [de administração do Microsoft 365.](https://admin.microsoft.com)

O OAuth 2.0 com [o Azure AD](https://docs.microsoft.com/azure/active-directory/) requer uma ID de recurso, ID do Cliente e Segredo do Cliente. O OAuth 2.0 só funciona com o modo nuvem.

Para obter mais informações, consulte Autorizar o acesso a aplicativos Web do Azure Active Directory usando o fluxo de concessão de código [do OAuth 2.0.](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code) Registre-se com os seguintes valores:

**Nome:** Pesquisa da Microsoft <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Para obter os valores do recurso, client_id e client_secret, vá para Usar o código de autorização para solicitar um **token** de acesso na página da Web da URL de redirecionamento.

Para obter ainda mais informações, consulte [Guia de início rápido: registrar um aplicativo com a plataforma de identidade da Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a>Etapa 3a: Adicionar URLs a excluir (restrições de rastreamento opcionais)

Há duas maneiras de impedir que as páginas sejam rastreadas: não permitir que elas sejam rastreadas em seu arquivo robots.txt ou adicioná-las à lista de exclusão.

### <a name="support-for-robotstxt"></a>Suporte para robots.txt

O conector verifica se há um arquivo robots.txt para seu site raiz e, se existir, ele seguirá e respeitará as direções encontradas nesse arquivo. Se você não quiser que o conector rastrear determinadas páginas ou diretórios em seu site, poderá chamar essas páginas ou diretórios nas declarações "Não permitir" no arquivo robots.txt usuário.

### <a name="add-urls-to-exclude"></a>Adicionar URLs a excluir

Opcionalmente, você  pode criar uma lista de exclusão para excluir algumas URLs do rastreamento se esse conteúdo for sensível ou não vale a pena rastrear. Para criar uma lista de exclusão, navegue pela URL raiz. Você pode adicionar as URLs excluídas à lista durante o processo de configuração.

## <a name="step-4-assign-property-labels"></a>Etapa 4: Atribuir rótulos de propriedade

Você pode atribuir uma propriedade de origem a cada rótulo escolhendo em um menu de opções. Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.

## <a name="step-5-manage-schema"></a>Etapa 5: Gerenciar esquema

Na  tela Gerenciar Esquema, você pode alterar os atributos de esquema (as opções são **Consulta** **,** **Pesquisa,** Recuperar e **Refinar**) associadas às propriedades, adicionar aliases opcionais e escolher a propriedade **Content.**

## <a name="step-6-manage-search-permissions"></a>Etapa 6: Gerenciar permissões de pesquisa

O conector de sites corporativos só dá suporte a permissões de pesquisa visíveis para **Todos.** Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização.

## <a name="step-7-set-the-refresh-schedule"></a>Etapa 7: Definir o agendamento de atualização

O conector de sites corporativos só oferece suporte a uma atualização completa. Isso significa que o conector fará um re-wl de todo o conteúdo do site durante cada atualização. Para garantir que o conector tenha tempo suficiente para rastrear o conteúdo, recomendamos definir um intervalo de agendamento de atualização grande. Recomendamos uma atualização agendada entre uma e duas semanas.

## <a name="step-8-review-connection"></a>Etapa 8: Analisar a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Solução de problemas

Ao ler o conteúdo do site, o rastreamento pode encontrar alguns erros de origem, que são representados pelos códigos de erro detalhados abaixo. Para obter mais informações sobre os tipos de erros, vá para a página de detalhes **do** erro depois de selecionar a conexão. Selecione o **código de** erro para ver erros mais detalhados. Consulte também Gerenciar [seu conector para](https://docs.microsoft.com/microsoftsearch/manage-connector) saber mais.

 Código de erro detalhado | Mensagem de erro
 --- | ---
 6001 | O site que está sendo tentado indexar não está acessível
 6005 | A página de origem que está sendo tentada para indexar foi bloqueada de acordo com robots.txt configuração.
 6008 | Não é possível resolver o DNS
 6009 | Para todos os erros do lado do cliente (exceto HTTP 404, 408), consulte códigos de erro HTTP 4xx para obter detalhes.
 6013 | Não foi possível encontrar a página de origem que está sendo tentada indexar. (Erro HTTP 404)
 6018 | A página de origem não está respondendo e a solicitação chegou ao fim. (Erro HTTP 408)
 6021 | A página de origem que está sendo tentada para indexar não tem conteúdo textual na página.
 6023 | A página de origem que está sendo tentada para indexar não é compatível (não uma página HTML)
 6024 | A página de origem que está sendo tentada para indexar tem conteúdo sem suporte.

* Os erros 6001-6013 ocorrem quando a fonte de dados não está acessível devido a um problema de rede ou quando a própria fonte de dados é excluída, movida ou renomeada. Verifique se os detalhes da fonte de dados fornecidos ainda são válidos.
* Os erros 6021-6024 ocorrem quando a fonte de dados contém conteúdo não textual na página ou quando a página não é um HTML. Verifique a fonte de dados e adicione esta página à lista de exclusão ou ignore o erro.

## <a name="limitations"></a>Limitações

O conector de sites corporativos não dá suporte à pesquisa de dados em **páginas da Web dinâmicas.** Exemplos dessas páginas da Web estão em sistemas de gerenciamento de conteúdo como [Confluência](https://www.atlassian.com/software/confluence) e [Unily](https://www.unily.com/) ou bancos de dados que armazenam conteúdo de site.