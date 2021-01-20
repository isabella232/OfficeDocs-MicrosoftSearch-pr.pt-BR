---
title: Conector MediaWiki para a Pesquisa da Microsoft
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
description: Configurar o conector MediaWiki para a Pesquisa da Microsoft
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905944"
---
# <a name="mediawiki-connector"></a>Conector MediaWiki

Com o conector MediaWiki, sua organização pode descobrir e indexar dados de um wiki criado usando o software MediaWiki. Esse conector indexa o conteúdo especificado na Pesquisa da Microsoft e oferece suporte a rastreamentos periódicos para manter o índice atualizado.

Este artigo é destinado a administradores do Microsoft 365 ou qualquer pessoa que configure, executa e monitore um conector MediaWiki Graph. Ele complementa as instruções gerais fornecidas no artigo [Configurar seu conector do Graph.](configure-connector.md) Se você ainda não tiver feito isso, leia todo o artigo Configurar seu conector do Graph para entender o processo de configuração geral.

Cada etapa do processo de instalação é listada abaixo, juntamente com uma observação que indica que você deve seguir as instruções gerais de instalação OU outras instruções que se aplicam apenas aos conectores MediaWiki Graph. Este artigo também inclui informações sobre limitações [para](#limitations) conectores MediaWiki Graph. 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: adicionar um conector do Graph no centro de administração do Microsoft 365.
Siga as instruções gerais de configuração.

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão.
Siga as instruções gerais de configuração.
 
## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Definir as configurações de conexão.
Insira sua **URL wiki** e escolha o tipo **de autenticação** no menu suspenso de opções. As opções são **None**, **Basic** e **OAuth 2.0 AAD**.

Se você escolher **Básico** como o tipo de autenticação, será necessário fornecer o nome **de** usuário e **a** senha para o wiki.

Se você escolher **OAuth 2.0 AAD** como o tipo de autenticação, será necessário fornecer a **ID** de recurso da instalação wiki. Você também precisará fornecer a **ID** do cliente e o segredo **do** cliente gerados na página de registro do aplicativo AAD. 

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa
O conector MediaWiki só dá suporte a permissões de pesquisa visíveis para **Todos.** Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização.

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade
Siga as instruções gerais de configuração.

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema
Siga as instruções gerais de configuração.

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização
Siga as instruções gerais de configuração.

## <a name="step-8-review-connection"></a>Etapa 8: Analisar a conexão
Siga as instruções gerais de configuração.

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Limitações
O conector MediaWiki tem estas limitações na versão de visualização:

* Oferece suporte somente a wikis baseados em nuvem.
* Dá suporte apenas ao Basic ou ao OAuth 2.0 com a autenticação do Azure Active Directory ou do Azure.
* Não dá suporte à seleção de namespace para indexação. Indexa apenas os namespaces Principal, Categoria e Arquivo.
* Não dá suporte a ACLs (Listas de Controle de Acesso). Assim, as páginas indexadas ficam visíveis para todos os usuários na organização.
