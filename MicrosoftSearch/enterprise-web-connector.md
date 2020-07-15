---
title: Conector de sites corporativos para o Microsoft Search
ms.author: mounika.narayanan
author: monaray
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
ms.openlocfilehash: fcda5db9b294e3d70bb27879f1bb0efb43ad6936
ms.sourcegitcommit: 0b5e3764822f64532c8a8e14b8e56e35141a558d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127637"
---
# <a name="enterprise-websites-connector"></a>Conector de sites corporativos

Com o conector de sites corporativos, sua organização pode indexar artigos e **conteúdo de seus sites voltados para o lado interno**. Depois de configurar o conector e sincronizar o conteúdo do site, os usuários finais podem pesquisar o conteúdo de qualquer cliente de pesquisa da Microsoft.

Este artigo é para os administradores do [Microsoft 365](https://www.microsoft.com/microsoft-365) ou qualquer pessoa que configure, execute e monitore um conector de sites da empresa. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.  

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados 
Para se conectar à sua fonte de dados, você precisará da URL raiz e de uma forma de autenticação: nenhum, autenticação básica ou OAuth 2,0 com o [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).

### <a name="authentication"></a>Autenticação 
A autenticação básica exige um nome de usuário e uma senha. Crie essa conta de bot usando o centro de [Administração](https://admin.microsoft.com)do Microsoft 365.

O OAuth 2,0 com o [Azure ad](https://docs.microsoft.com/azure/active-directory/) requer uma ID de recurso, uma ID de cliente e um segredo do cliente.

Para obter mais informações, consulte [autorizar o acesso aos aplicativos Web do Azure Active Directory usando o fluxo de concessão de código OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registre-se com os seguintes valores:

**Nome:** Pesquisa da Microsoft <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Para obter os valores para o recurso, client_id e client_secret, acesse **usar o código de autorização para solicitar um token de acesso** na página da Web da URL de redirecionamento.

Para obter mais informações, consulte [QuickStart: registrar um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="root-url"></a>URL raiz
A URL raiz é o que inicia o rastreamento e é usado para autenticação. Você pode obter a URL da home page do site que deseja rastrear.

## <a name="select-the-source-properties"></a>Selecionar as propriedades de origem 
As propriedades de origem são definidas com base no formato de dados do site da empresa. No entanto, você pode criar uma **lista de exclusão** para excluir algumas URLs de serem rastreadas se esse conteúdo for confidencial ou não valer para o rastreamento. Para criar uma lista de exclusão, navegue pela URL raiz. Você tem a opção de adicionar as URLs excluídas à lista durante o processo de configuração.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa 
Não há suporte para listas de controle de acesso (ACLs). Portanto, recomendamos que você conecte somente os sites que estão visíveis para qualquer usuário dentro da sua organização.

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização
O conector de sites corporativos suporta apenas um rastreamento completo. Isso significa que o conector lê todo o conteúdo do site em todos os rastreamentos. Para garantir que o conector tenha tempo suficiente para ler o conteúdo, recomendamos que você defina um intervalo grande de agendamento de atualização. Recomendamos uma atualização agendada entre uma e duas semanas.

## <a name="troubleshooting"></a>Solução de problemas
Ao ler o conteúdo do site, o rastreamento pode encontrar alguns erros de origem que são representados pelos códigos de erro detalhados abaixo. Para obter mais informações sobre os tipos de erros, acesse a página de **detalhes do erro** depois de selecionar a conexão. Clique no **código de erro** para ver erros mais detalhados. Consulte também [gerenciar o conector](https://docs.microsoft.com/microsoftsearch/manage-connector) para saber mais.

 Código de erro Detalhado | Mensagem de erro
 --- | --- 
 6001   | O site que está sendo tentado indexar não está acessível 
 6005 | A página de origem que está sendo tentada por indexação foi bloqueada por configuração de robots.txt.
 6008 | Não é possível resolver o DNS
 6009 | Para todos os erros do lado do cliente (exceto HTTP 404, 408), confira os códigos de erro HTTP 4xx para obter detalhes.
 6013 | Não foi possível encontrar a página de origem que está sendo tentada indexar. (Erro HTTP 404)
 6018 | A página de origem não está respondendo e a solicitação atingiu o tempo limite. (Erro HTTP 408)
 6021 | A página de origem que está sendo tentada indexar não tem conteúdo textual na página.
 6023 | A página de origem que está sendo tentada indexar não é suportada (não uma página HTML)
 6024 | A página de origem que está tentando indexação tem conteúdo sem suporte.

* Os erros 6001-6013 ocorrem quando a fonte de dados não está acessível devido a um problema de rede ou quando a própria fonte de dados é excluída, movida ou renomeada. Verifique se os detalhes da fonte de dados fornecidos ainda são válidos.
* Erros 6021-6024 o erro ocorre quando a fonte de dados contém conteúdo não textual na página ou quando a página não é um HTML. Verifique a fonte de dados e adicione esta página na lista de exclusão ou ignore o erro.

## <a name="limitations"></a>Limitações
O conector de sites corporativos não dá suporte à pesquisa de dados em **páginas da Web dinâmicas**. Exemplos de páginas da Web em sistemas de gerenciamento de conteúdo, como o [Confluence](https://www.atlassian.com/software/confluence) e o [Unily](https://www.unily.com/) ou os bancos de dados que armazenam o conteúdo do site.
