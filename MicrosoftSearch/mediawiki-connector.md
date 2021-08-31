---
title: Conector de Graph MediaWiki para Pesquisa da Microsoft
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
description: Configurar o conector de Graph MediaWiki para Pesquisa da Microsoft
ms.openlocfilehash: 7e1c308eb1785dd7fec23fac7e9002957a0d50ca
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701945"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>Conector de Graph MediaWiki

O conector Graph MediaWiki permite que sua organização descubra e indexe dados de um wiki criado usando o software MediaWiki. Esse conector indexa o conteúdo especificado em Pesquisa da Microsoft e oferece suporte a rastreamentos periódicos para manter o índice atualizado.

> [!NOTE]
> Leia o [**artigo Instalação do conector Graph para**](configure-connector.md) entender as instruções gerais Graph configuração de conectores.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector de Graph MediaWiki. Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector de Graph MediaWiki. Este artigo também inclui informações sobre [Limitações.](#limitations)

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: adicionar um conector Graph no Centro de administração do Microsoft 365

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão

Insira sua **URL wiki** e escolha o tipo **autenticação** no menu suspenso de opções. As opções são **None**, **Basic** e **OAuth 2.0 AAD**.

Se você escolher **Basic como** o tipo de Autenticação, precisará fornecer o **Nome** de Usuário e Senha **para** o wiki.

Se você escolher **OAuth 2.0 AAD** como o tipo de Autenticação, precisará fornecer a **ID** de Recurso da instalação wiki. Você também precisará fornecer a **ID do Cliente** e o **segredo do** cliente gerado na página de registro do Aplicativo AAD.

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

O conector MediaWiki só dá suporte a permissões de pesquisa visíveis para **Todos.** Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização.

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Etapa 8: Revisar conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Limitações

O conector MediaWiki tem essas limitações na versão de visualização:

* Oferece suporte apenas a wikis baseados em nuvem.
* Oferece suporte apenas ao Basic ou ao OAuth 2.0 com Azure Active Directory ou autenticação do Azure.
* Não dá suporte à seleção de namespace para indexação. Indexa somente namespaces Main, Category e File.
* Não dá suporte a Listas de Controle de Acesso (ACLs). Assim, as páginas indexadas ficam visíveis para todos os usuários na organização.