---
title: Conector de sites corporativos para o Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector de sites da empresa para o Microsoft Search
ms.openlocfilehash: 443e903e0fa371d2a056fd4bf06310eb2627b11c
ms.sourcegitcommit: 031e7c595496d9faed9038725b04f3c8b5f9ccbd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604766"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a>Conector de sites corporativos

Com o conector de sites corporativos, sua organização pode indexar artigos e **conteúdo de seus sites voltados para o lado interno**. Depois de configurar o conector e sincronizar o conteúdo do site, os usuários finais podem pesquisar o conteúdo de qualquer cliente de pesquisa da Microsoft.

Este artigo é para os administradores do [Microsoft 365](https://www.microsoft.com/microsoft-365) ou qualquer pessoa que configure, execute e monitore um conector de sites da empresa. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.  

## <a name="connection-settings"></a>Configurações de conexão

Para se conectar à sua fonte de dados, você precisará preencher a URL raiz do site, selecionar uma fonte de rastreamento e o tipo de autenticação que gostaria de usar: nenhum, autenticação básica ou OAuth 2,0 com [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/). Depois de concluir essas informações, clique em testar conexão para verificar suas configurações.

### <a name="url"></a>URL

Use o campo URL para especificar a raiz do site que você deseja rastrear. O conector de sites corporativos usará essa URL como o ponto de partida e seguirá todos os links desta URL para o rastreamento.

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>Modo de rastreamento: nuvem ou local (visualização)

O modo de rastreamento determina o tipo de sites que você deseja indexar, tanto na nuvem quanto no local. Para seus sites de nuvem, selecione **nuvem** como o modo de rastreamento.

Além disso, o conector agora oferece suporte ao rastreamento de sites locais. Este modo está em visualização. Para acessar seus dados locais, primeiro você deve instalar e configurar o agente do conector do Graph. Para saber mais, confira [agente do conector do Graph](https://docs.microsoft.com/microsoftsearch/on-prem-agent).

Para os sites locais, selecione **agente** como o modo de rastreamento e, no campo **agente local** , escolha o agente do conector do Graph que você instalou e configurou anteriormente.  

![Captura de tela do painel de configurações de conexão para o Enterprise Web Connector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>Autenticação

A autenticação básica exige um nome de usuário e uma senha. Crie essa conta de bot usando o [centro de administração do Microsoft 365](https://admin.microsoft.com).

O OAuth 2,0 com o [Azure ad](https://docs.microsoft.com/azure/active-directory/) requer uma ID de recurso, uma ID de cliente e um segredo do cliente. O OAuth 2,0 só funciona com o modo de nuvem.

Para obter mais informações, consulte [autorizar o acesso aos aplicativos Web do Azure Active Directory usando o fluxo de concessão de código OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registre-se com os seguintes valores:

**Nome:** Pesquisa da Microsoft <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Para obter os valores para o recurso, client_id e client_secret, acesse **usar o código de autorização para solicitar um token de acesso** na página da Web da URL de redirecionamento.

Para obter mais informações, consulte [QuickStart: registrar um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="support-for-robotstxt"></a>Suporte para robots.txt

O conector verifica se há um arquivo de robots.txt para o site raiz e, se houver algum, ele seguirá e respeitará as direções encontradas nesse arquivo. Se você não quiser que o conector rastreie determinadas páginas ou diretórios no seu site, você pode chamar essas páginas ou diretórios nas declarações "não permitir" no arquivo robots.txt.

## <a name="add-urls-to-exclude"></a>Adicionar URLs a serem excluídas

Opcionalmente, você pode criar uma **lista de exclusão** para excluir algumas URLs de serem rastreadas se esse conteúdo for confidencial ou não valer para o rastreamento. Para criar uma lista de exclusão, navegue pela URL raiz. Você tem a opção de adicionar as URLs excluídas à lista durante o processo de configuração.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa

O conector de sites da empresa oferece suporte apenas às permissões de pesquisa visíveis para **todos**. Dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários da organização.

## <a name="assign-property-labels"></a>Atribuir rótulos de propriedade

Você pode atribuir uma propriedade Source a cada rótulo escolhendo a partir de um menu de opções. Embora esta etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.

## <a name="manage-schema"></a>Gerenciar esquema

Na tela **gerenciar esquema** , você tem a opção de alterar os atributos de esquema (**consultável**, **pesquisável**, **recuperável** e **refinável**) associados às propriedades, adicionar aliases opcionais e escolher a propriedade **Content** .

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização

O conector de sites corporativos suporta apenas uma atualização completa. Isso significa que o conector irá rastrear novamente todo o conteúdo do site durante cada atualização. Para garantir que o conector tenha tempo suficiente para rastrear o conteúdo, recomendamos que você defina um intervalo grande de agendamento de atualização. Recomendamos uma atualização agendada entre uma e duas semanas.

## <a name="troubleshooting"></a>Solução de problemas

Ao ler o conteúdo do site, o rastreamento pode encontrar alguns erros de origem, que são representados pelos códigos de erro detalhados abaixo. Para obter mais informações sobre os tipos de erros, acesse a página de **detalhes do erro** depois de selecionar a conexão. Clique no **código de erro** para ver erros mais detalhados. Consulte também [gerenciar o conector](https://docs.microsoft.com/microsoftsearch/manage-connector) para saber mais.

 Código de erro Detalhado | Mensagem de erro
 --- | ---
 6001 | O site que está sendo tentado indexar não está acessível
 6005 | A página de origem que está sendo tentada por indexação foi bloqueada por configuração de robots.txt.
 6008 | Não é possível resolver o DNS
 6009 | Para todos os erros do lado do cliente (exceto HTTP 404, 408), consulte códigos de erro HTTP 4xx para obter detalhes.
 6013 | Não foi possível encontrar a página de origem que está sendo tentada indexar. (Erro HTTP 404)
 6018 | A página de origem não está respondendo e a solicitação atingiu o tempo limite. (Erro HTTP 408)
 6021 | A página de origem que está sendo tentada indexar não tem conteúdo textual na página.
 6023 | A página de origem que está sendo tentada indexar não é suportada (não uma página HTML)
 6024 | A página de origem que está tentando indexação tem conteúdo sem suporte.

* Os erros 6001-6013 ocorrem quando a fonte de dados não está acessível devido a um problema de rede ou quando a própria fonte de dados é excluída, movida ou renomeada. Verifique se os detalhes da fonte de dados fornecidos ainda são válidos.
* Os erros 6021-6024 ocorrem quando a fonte de dados contém conteúdo não textual na página ou quando a página não é um HTML. Verifique a fonte de dados e adicione esta página na lista de exclusão ou ignore o erro.

## <a name="limitations"></a>Limitações

O conector de sites corporativos não dá suporte à pesquisa de dados em **páginas da Web dinâmicas**. Exemplos de páginas da Web em sistemas de gerenciamento de conteúdo, como o [Confluence](https://www.atlassian.com/software/confluence) e o [Unily](https://www.unily.com/) ou os bancos de dados que armazenam o conteúdo do site.

## <a name="next-steps"></a>Próximas etapas

Após publicar a conexão, você precisa personalizar a página de resultados da pesquisa. Para saber mais sobre como personalizar os resultados da pesquisa, confira [Personalizar a página de resultados da pesquisa](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).
