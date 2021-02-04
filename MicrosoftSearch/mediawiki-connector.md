---
title: Conector MediaWiki Graph para a Pesquisa da Microsoft
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
description: Configurar o conector MediaWiki Graph para a Pesquisa da Microsoft
ms.openlocfilehash: e2b2b7c506d92623dd0f68801312c1820b5b9d4e
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097390"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>Conector MediaWiki Graph

O conector MediaWiki Graph permite que sua organização descubra e indexe dados de um wiki criado usando o software MediaWiki. Esse conector indexa o conteúdo especificado na Pesquisa da Microsoft e oferece suporte a rastreamentos periódicos para manter o índice atualizado.

> [!NOTE]
> Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector MediaWiki Graph. Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector MediaWiki Graph. Este artigo também inclui informações sobre [limitações.](#limitations)

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Definir as configurações de conexão

Insira sua **URL wiki** e escolha o tipo **de autenticação** no menu suspenso de opções. As opções são **None**, **Basic** e **OAuth 2.0 AAD**.

Se você escolher **Básico** como o tipo de autenticação, será necessário fornecer o nome **de** usuário e **a** senha para o wiki.

Se você escolher **OAuth 2.0 AAD** como o tipo de autenticação, será necessário fornecer a **ID** de recurso da instalação wiki. Você também precisará fornecer a **ID** do cliente e o segredo **do** cliente gerados na página de registro do aplicativo AAD.

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

O conector MediaWiki só dá suporte a permissões de pesquisa visíveis para **Todos.** Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização.

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Etapa 8: Analisar a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Limitações

O conector MediaWiki tem estas limitações na versão de visualização:

* Oferece suporte somente a wikis baseados em nuvem.
* Dá suporte apenas ao Basic ou ao OAuth 2.0 com a autenticação do Azure Active Directory ou do Azure.
* Não dá suporte à seleção de namespace para indexação. Indexa apenas os namespaces Principal, Categoria e Arquivo.
* Não dá suporte a ACLs (Listas de Controle de Acesso). Assim, as páginas indexadas ficam visíveis para todos os usuários na organização.
