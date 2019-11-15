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
ms.openlocfilehash: c2495487b24b11512a182434f72a90044a439d5d
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626269"
---
# <a name="enterprise-websites-connector"></a>Conector de sites corporativos

Com o conector de sites corporativos, sua organização pode indexar artigos e **conteúdo de seus sites voltados para o lado interno**. Depois de configurar o conector e sincronizar o conteúdo do site, os usuários finais podem pesquisar o conteúdo de qualquer cliente de pesquisa da Microsoft.

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector de sites da empresa. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.  

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados 
Para se conectar à sua fonte de dados, você precisará da URL raiz e de uma forma de autenticação (autenticação básica ou OAuth 2,0 com o Azure AD).

### <a name="root-url"></a>URL raiz
A URL raiz é o que inicia o rastreamento e é usado para autenticação. Você pode obter a URL da home page do site que deseja rastrear.

### <a name="authentication"></a>Autenticação 
A autenticação básica exige um nome de usuário e uma senha. Crie essa conta de bot usando o [centro de administração do Microsoft 365](https://admin.microsoft.com).

O OAuth 2,0 com o Azure AD requer uma ID de locatário, ID de recurso, ID de cliente e segredo do cliente.
Para obter mais informações, consulte [autorizar o acesso aos aplicativos Web do Azure Active Directory usando o fluxo de concessão de código OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registre-se com os seguintes valores:
* **Nome:** Pesquisa da Microsoft
* **Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Para obter os valores de Tenant, Resource, client_id e client_secret nomeados, acesse **usar o código de autorização para solicitar um token de acesso** na página da Web URL de redirecionamento.

Para obter mais informações, consulte [QuickStart: registrar um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="reverse-proxy-url"></a>URL de proxy reverso 
O conector de sites da empresa é baseado em nuvem, portanto, não acessa o conteúdo local. Para fornecer esse acesso, instale um proxy reverso. Um proxy reverso fornece acesso seguro e confiável a sites locais. Recomendamos o proxy de aplicativo do Azure (AAP).

O requisito de proxy reverso para a URL raiz e autenticação é o mesmo que o conteúdo baseado em nuvem, exceto pelo fato de que a URL raiz e a autenticação são fornecidas pelo servidor de proxy reverso.

Veja [considerações de segurança para acessar aplicativos remotamente com o proxy de aplicativo do Azure ad](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).

## <a name="select-the-source-properties"></a>Selecionar as propriedades de origem 
As propriedades de origem são definidas com base no formato de dados do site da empresa. No entanto, você pode criar uma **lista de exclusão** para excluir algumas URLs de serem rastreadas, pois esse conteúdo pode ser confidencial ou não vale a pena ser rastreado. Para criar uma lista de exclusão, navegue pela URL raiz. Você tem a opção de adicionar as URLs excluídas à lista durante o processo de configuração.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa 
Não há suporte para listas de controle de acesso (ACLs). Portanto, é aconselhável conectar somente os sites que estão visíveis a qualquer usuário dentro da sua organização.

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização
O conector de sites corporativos suporta apenas um rastreamento completo. Isso significa que o conector lê todo o conteúdo do site em todos os rastreamentos. Para garantir que o conector tenha tempo suficiente para ler o conteúdo, é recomendável definir um intervalo grande de agendamento de atualização. Recomendamos uma atualização agendada entre três dias e duas semanas.

## <a name="limitations"></a>Limitações 
O conector de sites corporativos não dá suporte à pesquisa de dados em páginas da Web dinâmicas. Exemplos de páginas da Web em sistemas de gerenciamento de conteúdo, como o Confluence e o Unily ou os bancos de dados que armazenam o conteúdo do site.