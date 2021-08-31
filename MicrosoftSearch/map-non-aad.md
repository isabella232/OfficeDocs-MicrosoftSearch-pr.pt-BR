---
title: Mapeamento de identidades não AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Etapas sobre como mapear identidades não AAD
ms.openlocfilehash: e90db3bb8d20a0389ddbf2d2845bf91843513404
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701954"
---
# <a name="map-your-non-azure-ad-identities"></a>Mapear suas identidades que não são do Azure AD  

Este artigo orienta você pelas etapas de mapeamento de suas identidades não Azure AD para suas identidades do Azure AD para que as pessoas em sua Lista de Controle de Acesso (ACL) com identidades que não são do Azure AD possam ver os resultados da pesquisa do conector com escopo para elas.

Essas etapas são relevantes apenas para administradores de pesquisa que estão configurando um [conector serviceNow](servicenow-connector.md) ou [Salesforce](salesforce-connector.md) pela Microsoft com permissões de pesquisa para "Somente pessoas com acesso a essa fonte de dados" e tipo de identidade "Não-AAD".

>[!NOTE]
>Se você estiver configurando um  conector do Salesforce e selecionar Somente pessoas com acesso a essa fonte de dados e tipo de identidade **AAD** na tela de permissões de pesquisa, consulte o artigo Mapear suas Identidades do [Azure AD](map-aad.md) para ver as etapas sobre como mapear identidades do Azure AD.  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a>Etapas para mapear suas propriedades que não são do Azure AD

### <a name="1-select-an-azure-ad-user-property"></a>1. Selecione uma propriedade de usuário do Azure AD  

Você pode selecionar a propriedade de usuário do Azure AD para a que você está criando o mapeamento. Esta é a propriedade de destino que você está visando mapear suas identidades não-Azure AD.  

Você pode selecionar uma das seguintes propriedades do Azure AD:

| Propriedade do Azure AD    | Definição           | Exemplo         |
| :------------------- | :------------------- |:--------------- |
| Nome UPN  | Um UPN consiste em um prefixo UPN (o nome da conta de usuário) e um sufixo UPN (um nome de domínio DNS). O prefixo é ingressado com o sufixo usando o símbolo "@". | us1@contoso.onmicrosoft.com |
| Azure AD ID                 | Uma ID do Azure AD para um determinado usuário é o GUID exclusivo do usuário.                 | 58006c96-9e6e-45ea-8c88-4a56851eefad            |
| ID de Segurança do Active Directory (SID)                  | SID (Identificador de Segurança) é um identificador exclusivo que o Active Directory usa para identificar objetos como entidades de segurança.                  | S-1-5-21-453406510-812318184-4183662089             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a>2. Selecione propriedades de usuário que não são do Azure AD para mapear

Você pode selecionar propriedades que não são do Azure AD retiradas de sua fonte de dados para aplicar expressões regulares. Para saber mais sobre onde encontrar essas propriedades em sua fonte de dados, consulte as [páginas ServiceNow](servicenow-connector.md) e [Salesforce.](salesforce-connector.md)  

Você pode selecionar uma propriedade de usuário que não seja do Azure AD no menu suspenso e fornecer uma expressão regular a ser aplicada a esses valores de propriedade do usuário. Para saber mais sobre expressões regulares, consulte [referência de expressão regular]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).  

A seguir estão alguns exemplos de expressões regulares e suas saídas aplicadas a uma cadeia de caracteres de exemplo: 

| Cadeia de caracteres de exemplo                  | Expressão regular                 | Saída de expressão regular na cadeia de caracteres de exemplo           |
| :------------------- | :------------------- |:---------------|
| Alexia Vasquez  | .* | Alexia Vasquez |
| Alexia Vasquez                 | ..$                 | ez            |
| Alexia Vasquez                  | (\w+)$                  | Vasquez             |

Você pode adicionar quantas propriedades de usuário que não são do Azure AD como você gostaria de expressões. Você pode aplicar expressões regulares diferentes à mesma propriedade do usuário se a fórmula final o justificar.  

### <a name="3-create-formula-to-complete-mapping"></a>3. Criar fórmula para concluir o mapeamento

Você pode combinar as saídas das expressões regulares aplicadas a cada uma das suas propriedades de usuário que não são do Azure AD para formar a propriedade do Azure AD selecionada na etapa 1.

Na caixa de fórmula, " " corresponde à saída da expressão regular aplicada à primeira propriedade {0} não-Azure AD selecionada.  " " corresponde à saída da expressão regular aplicada à segunda propriedade {1} não-Azure AD selecionada.  " " corresponde à saída da expressão regular aplicada à terceira propriedade {2} não-Azure AD e assim por diante.   

A seguir estão alguns exemplos de fórmulas com saídas de expressão regular de exemplo e saídas de fórmula: 

| Fórmula de exemplo                  | Valor de {0} usuário de exemplo                 | Valor de {1} usuário de exemplo           | Saída da fórmula                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso.com  | firstname | lastname |firstname.lastname@contoso.com
| {0}@domain.com                 | userid                 |             |userid@domain.com

Depois de fornecer sua fórmula, você pode, opcionalmente, clicar em **Visualizar** para ver uma visualização de cinco usuários aleatórios de sua fonte de dados com seus respectivos mapeamentos de usuário aplicados. A saída da visualização inclui o valor das propriedades de usuário que não são do Azure AD selecionadas na etapa 2 para esses usuários e a saída da fórmula final fornecida na etapa 3 para esse usuário. Ele também indica se a saída da fórmula poderia ser resolvida para um usuário do Azure AD em seu locatário por meio de um ícone "Sucesso" ou "Falha".  

>[!NOTE]
>Você ainda pode prosseguir com a criação de sua conexão se um ou mais mapeamentos de usuário tiver um status "Falha" depois de clicar em **Visualizar**. A visualização mostra 5 usuários aleatórios e seus mapeamentos de sua fonte de dados. Se o mapeamento que você fornece não mapear todos os usuários, você poderá experimentar esse caso.

## <a name="sample-non-azure-ad-mapping"></a>Exemplo de mapeamento do Azure AD

Consulte o instantâneo abaixo para um exemplo de mapeamento que não seja do Azure AD.

![Exemplo de instantâneo de como preencher a página de mapeamento que não é do Azure AD.](media/non-aad-mapping.png)

## <a name="limitations"></a>Limitações  

- Há suporte para apenas um mapeamento para todos os usuários. Não há suporte para mapeamentos condicionais.  

- Não é possível alterar o mapeamento depois que a conexão for publicada.  

- Somente expressões baseadas em regex em propriedades de usuário não AAD são suportadas atualmente para a transformação.

- Há apenas 3 identidades do Azure AD para as quais você pode optar por mapear (UPN, ID do Azure AD e SID do AD).