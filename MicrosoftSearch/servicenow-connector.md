---
title: Conector do ServiceNow para pesquisa da Microsoft
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.date: 10/08/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do ServiceNow para pesquisa da Microsoft
ms.openlocfilehash: b83bf04dc06ffab26a0067d15b36a99496c199a8
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949588"
---
# <a name="servicenow-connector"></a>Conector do ServiceNow

Com o conector do ServiceNow, sua organização pode indexar artigos de base de conhecimento que são visíveis para todos os usuários da sua organização. Depois de configurar o conector e o conteúdo do índice do ServiceNow, os usuários finais podem pesquisar esses artigos de qualquer cliente de pesquisa da Microsoft.  

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector do ServiceNow. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados
Para se conectar aos seus dados do ServiceNow, você precisa da **URL de instância do servicenow**da sua organização, as credenciais dessa conta e a ID do cliente e o segredo do cliente para autenticação OAuth.  

A URL da **instância do ServiceNow** da sua organização normalmente parece **https://&lt;seu-organization-Domain>. Service-Now.com**. Juntamente com esta URL, você precisará de uma conta para configurar a conexão com o ServiceNow, bem como para permitir que a pesquisa da Microsoft atualize periodicamente os artigos do ServiceNow com base no agendamento de atualização.

Para autenticar e sincronizar o conteúdo do ServiceNow, escolha um dos dois métodos com suporte: 
1. Autenticação básica 
2. OAuth (recomendado)

> [!Note]
> Para usar o OAuth para autenticação, um administrador do ServiceNow precisa provisionar um ponto de extremidade na sua instância do ServiceNow, para que o aplicativo de pesquisa da Microsoft possa acessar a instância. Para saber mais, confira [criar um ponto de extremidade para os clientes acessar a instância](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) na documentação do ServiceNow.

A tabela a seguir fornece orientação sobre como preencher o formulário de criação de ponto de extremidade:

**Field** | **Descrição** | **Valor recomendado**
--- | --- | ---
Nome | Esse valor exclusivo identifica o aplicativo para o qual você precisa de acesso OAuth. | Pesquisa da Microsoft
ID do cliente | Uma ID exclusiva somente leitura, gerada automaticamente, para o aplicativo. A instância usa a ID do cliente quando ele solicita um token de acesso. | NA
Segredo do cliente | Com essa cadeia de caracteres secreta compartilhada, a instância do ServiceNow e a pesquisa da Microsoft autorizam comunicações entre si. | Siga as práticas recomendadas de segurança tratando isso como uma senha.
URL de redirecionamento | Uma URL de retorno de chamada necessária para a qual o servidor de autorização é redirecionado. | Confira o [retorno de chamada OAuth](https://gcs.office.com/v1.0/admin/oauth/callback).
URL do Logotipo | Uma URL que contém a imagem do logotipo do aplicativo. | NA
Ativo | Marque a caixa de seleção para tornar o registro de aplicativo ativo. | Definido como ativo
Duração do token de atualização | O número de segundos que um token de atualização é válido. Por padrão, os tokens de atualização expiram em 100 dias (8640000 segundos). | 31.536.000 (1 ano)
Vida útil do token de acesso | O número de segundos que um token de acesso é válido. | 43.200 (12 horas)

## <a name="set-a-sync-filter"></a>Definir um filtro de sincronização 
Com um filtro de sincronização, você pode especificar condições para sincronizar artigos. É como uma cláusula **Where** em uma instrução **SQL SELECT** . Por exemplo, você pode optar por indexar apenas artigos publicados e ativos. A página de configuração do SyncNow descreve como capturar e definir um filtro de sincronização.

## <a name="manage-the-search-schema"></a>Gerenciar o esquema de pesquisa
Após a conexão bem-sucedida, configure o mapeamento de esquema de pesquisa. Você pode escolher quais propriedades tornar **consultáveis**, **pesquisáveis**e **recuperáveis**.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa
O conector do ServiceNow oferece suporte apenas às permissões de pesquisa visíveis para **todos**. Dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários da organização.
 
## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização 
O conector do ServiceNow suporta agendas de atualização para rastreamentos completos e incrementais. Recomendamos que você defina ambas.

Um cronograma de rastreamento completo localiza artigos excluídos que foram previamente sincronizados com o índice de pesquisa da Microsoft e quaisquer artigos que tenham sido movidos do filtro de sincronização. Quando você se conecta pela primeira vez ao ServiceNow, um rastreamento completo é executado para sincronizar todos os artigos da base de conhecimento. Para sincronizar novos itens e fazer atualizações, você precisa agendar rastreamentos incrementais.

O padrão recomendado é um dia para um rastreamento completo e quatro horas para um rastreamento incremental.
