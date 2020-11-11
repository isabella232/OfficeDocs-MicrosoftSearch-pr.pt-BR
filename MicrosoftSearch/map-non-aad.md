---
title: Mapeando identidades não-AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: etapas sobre como mapear identidades não-AAD
ms.openlocfilehash: be479cfd9dad585e83b5a39ff3ce4a84b9d41676
ms.sourcegitcommit: 77ec27736f3c8434b2ac47e10897ac2606ee8a03
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48992826"
---
# <a name="map-your-non-azure-ad-identities"></a>Mapear suas identidades não pertencentes ao Azure AD  

Este artigo apresenta as etapas de mapeamento de suas identidades não do Azure AD para suas identidades do Azure AD para que as pessoas na sua lista de controle de acesso (ACL) com identidades não Azure AD possam ver os resultados de pesquisa do conector com o escopo.

Essas etapas só são relevantes para os administradores de pesquisa que estão Configurando os conectores do [ServiceNow](servicenow-connector.md) ou do [Salesforce](salesforce-connector.md) pela Microsoft com permissões de pesquisa para "apenas pessoas com acesso a esta fonte de dados" e tipo de identidade "não AAD".

>[!NOTE]
>Se você estiver configurando um conector do Salesforce e selecionar **apenas pessoas com acesso a essa fonte de dados** e tipo de identidade do **AAD** na tela de permissões de pesquisa, consulte o artigo [map your Azure ad Identities](map-aad.md) para obter etapas sobre como mapear identidades do Azure AD.  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a>Etapas para mapeamento de suas propriedades não do Azure AD

### <a name="1-select-an-azure-ad-user-property"></a>1. Selecione uma propriedade de usuário do Azure AD  

Você pode selecionar a propriedade de usuário do Azure AD para a qual você está criando o mapeamento. Esta é a propriedade de destino para a qual você deseja mapear suas identidades não do Azure AD.  

Você pode selecionar uma das seguintes propriedades do Azure AD:

| Propriedade do Azure AD    | Definição           | Exemplo         |
| :------------------- | :------------------- |:--------------- |
| Nome UPN  | Um UPN consiste em um prefixo UPN (o nome da conta de usuário) e um sufixo UPN (um nome de domínio DNS). O prefixo é Unido ao sufixo usando o símbolo "@". | us1@contoso.onmicrosoft.com |
| ID do Azure AD                 | Uma ID do Azure AD para um determinado usuário é o único GUID do usuário.                 | 58006c96-9e6e-45ea-8c88-4a56851eefad            |
| IDENTIFICAÇÃO de segurança (SID) do Active Directory                  | SID (identificador de segurança) é um identificador exclusivo que o Active Directory usa para identificar objetos como entidade de segurança.                  | S-1-5-21-453406510-812318184-4183662089             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a>2. selecione Propriedades de usuário não do Azure AD para mapear

Você pode selecionar as propriedades não do Azure AD obtidas da fonte de dados para aplicar as expressões regulares. Para saber mais sobre onde encontrar essas propriedades na sua fonte de dados, consulte as páginas do [ServiceNow](servicenow-connector.md) e do [Salesforce](salesforce-connector.md) .  

Você pode selecionar uma propriedade de usuário não do Azure AD na lista suspensa e fornecer uma expressão regular a ser aplicada nesses valores de Propriedade do usuário. Para saber mais sobre expressões regulares, confira [referência de expressões regulares]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).  

Veja a seguir alguns exemplos de expressões regulares e suas saídas aplicadas a uma cadeia de caracteres de amostra: 

| Cadeia de caracteres de amostra                  | Expressão regular                 | Saída da expressão regular na cadeia de caracteres de amostra           |
| :------------------- | :------------------- |:---------------|
| Alexis Vasquez  | .* | Alexis Vasquez |
| Alexis Vasquez                 | ..$                 | ez            |
| Alexis Vasquez                  | (\w +) $                  | Vasquez             |

Você pode adicionar quantas Propriedades de usuário não pertencente ao Azure você quiser as expressões. Você pode aplicar diferentes expressões regulares à mesma propriedade de usuário se sua fórmula final garantir isso.  

### <a name="3-create-formula-to-complete-mapping"></a>3. criar fórmula para concluir o mapeamento

Você pode combinar as saídas de expressões regulares aplicadas a cada uma das suas propriedades de usuário não do Azure AD para formar a propriedade do Azure AD selecionada na etapa 1.

Na caixa Fórmula, " {0} " corresponde à saída da expressão regular aplicada à *primeira* propriedade não Azure AD que você selecionou. " {1} " corresponde à saída da expressão regular aplicada à *segunda* propriedade não Azure AD que você selecionou. " {2} " corresponde à saída da expressão regular aplicada à *terceira* propriedade não do Azure AD e assim por diante.  

Veja a seguir alguns exemplos de fórmulas com exemplos de resultados de expressões regulares e saídas de fórmulas: 

| Fórmula de exemplo                  | Valor de {0} no usuário de exemplo                 | Valor de {1} no usuário de exemplo           | Saída da fórmula                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso. com  | FirstName | LastName |firstname.lastname@contoso.com
| {0}@domain. com                 | ID                 |             |userid@domain.com

Depois de fornecer sua fórmula, você pode, opcionalmente, clicar em **Visualizar** para ver uma visualização de cinco usuários aleatórios da fonte de dados com seus respectivos mapeamentos de usuários aplicados. A saída da visualização inclui o valor das propriedades de usuário não do Azure AD selecionadas na etapa 2 para esses usuários e a saída da fórmula final fornecida na etapa 3 para esse usuário. Também indica se a saída da fórmula pode ser resolvida para um usuário do Azure AD no locatário por meio de um ícone de "sucesso" ou "falha".  

>[!NOTE]
>Você ainda pode prosseguir com a criação de sua conexão se um ou mais mapeamentos de usuário tiverem um status de "falha" após você clicar em **Visualização**. A visualização mostra 5 usuários aleatórios e seus mapeamentos da fonte de dados. Se o mapeamento fornecido não mapear todos os usuários, você pode experimentar esse caso.

## <a name="sample-non-azure-ad-mapping"></a>Exemplo de mapeamento não Azure AD

Confira o instantâneo abaixo para obter um exemplo de mapeamento não Azure AD.

![Instantâneo de exemplo de como preencher a página de mapeamento não pertencente ao Azure AD](media/non-aad-mapping.png)

## <a name="limitations"></a>Limitações  

- Só há suporte para um mapeamento para todos os usuários. Não há suporte para mapeamentos condicionais.  

- Não é possível alterar o mapeamento depois que a conexão é publicada.  

- Atualmente, somente as expressões baseadas em Regex em relação às propriedades do usuário não AAD têm suporte para a transformação.

- Há apenas 3 identidades do Azure AD que você pode escolher para mapear (UPN, ID do Azure AD e SID do AD).