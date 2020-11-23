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
description: Etapas sobre como mapear identidades não-AAD
ms.openlocfilehash: cd7d0eb17678d69ec1966e4472b38c1f18c30809
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367654"
---
# <a name="map-your-non-azure-ad-identities"></a><span data-ttu-id="42142-103">Mapear suas identidades não pertencentes ao Azure AD</span><span class="sxs-lookup"><span data-stu-id="42142-103">Map your non-Azure AD Identities</span></span>  

<span data-ttu-id="42142-104">Este artigo apresenta as etapas de mapeamento de suas identidades não do Azure AD para suas identidades do Azure AD para que as pessoas na sua lista de controle de acesso (ACL) com identidades não Azure AD possam ver os resultados de pesquisa do conector com o escopo.</span><span class="sxs-lookup"><span data-stu-id="42142-104">This article walks you through the steps of mapping your non-Azure AD identities to your Azure AD identities so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="42142-105">Essas etapas só são relevantes para os administradores de pesquisa que estão Configurando os conectores do [ServiceNow](servicenow-connector.md) ou do [Salesforce](salesforce-connector.md) pela Microsoft com permissões de pesquisa para "apenas pessoas com acesso a esta fonte de dados" e tipo de identidade "não AAD".</span><span class="sxs-lookup"><span data-stu-id="42142-105">These steps are only relevant to search administrators who are setting up a [ServiceNow](servicenow-connector.md) or [Salesforce](salesforce-connector.md) connectors by Microsoft with search permissions for "Only people with access to this data source" and identity type "Non-AAD."</span></span>

>[!NOTE]
><span data-ttu-id="42142-106">Se você estiver configurando um conector do Salesforce e selecionar **apenas pessoas com acesso a essa fonte de dados** e tipo de identidade do **AAD** na tela de permissões de pesquisa, consulte o artigo [map your Azure ad Identities](map-aad.md) para obter etapas sobre como mapear identidades do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="42142-106">If you are setting up a Salesforce connector and select **Only people with access to this data source** and identity type **AAD** on the search permissions screen, refer to the [Map your Azure AD Identities](map-aad.md) article for steps on how to map Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a><span data-ttu-id="42142-107">Etapas para mapeamento de suas propriedades não do Azure AD</span><span class="sxs-lookup"><span data-stu-id="42142-107">Steps for mapping your non-Azure AD properties</span></span>

### <a name="1-select-an-azure-ad-user-property"></a><span data-ttu-id="42142-108">1. Selecione uma propriedade de usuário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="42142-108">1. Select an Azure AD user property</span></span>  

<span data-ttu-id="42142-109">Você pode selecionar a propriedade de usuário do Azure AD para a qual você está criando o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="42142-109">You can select the Azure AD user property you are creating the mapping for.</span></span> <span data-ttu-id="42142-110">Esta é a propriedade de destino para a qual você deseja mapear suas identidades não do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="42142-110">This is the target property you are aiming to map your non-Azure AD identities to.</span></span>  

<span data-ttu-id="42142-111">Você pode selecionar uma das seguintes propriedades do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="42142-111">You can select one of the following Azure AD properties:</span></span>

| <span data-ttu-id="42142-112">Propriedade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="42142-112">Azure AD property</span></span>    | <span data-ttu-id="42142-113">Definição</span><span class="sxs-lookup"><span data-stu-id="42142-113">Definition</span></span>           | <span data-ttu-id="42142-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="42142-114">Example</span></span>         |
| :------------------- | :------------------- |:--------------- |
| <span data-ttu-id="42142-115">Nome UPN</span><span class="sxs-lookup"><span data-stu-id="42142-115">User Principal Name (UPN)</span></span>  | <span data-ttu-id="42142-116">Um UPN consiste em um prefixo UPN (o nome da conta de usuário) e um sufixo UPN (um nome de domínio DNS).</span><span class="sxs-lookup"><span data-stu-id="42142-116">A UPN consists of a UPN prefix (the user account name) and a UPN suffix (a DNS domain name).</span></span> <span data-ttu-id="42142-117">O prefixo é Unido ao sufixo usando o símbolo "@".</span><span class="sxs-lookup"><span data-stu-id="42142-117">The prefix is joined with the suffix using the "@" symbol.</span></span> | <span data-ttu-id="42142-118">us1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="42142-118">us1@contoso.onmicrosoft.com</span></span> |
| <span data-ttu-id="42142-119">ID do Azure AD</span><span class="sxs-lookup"><span data-stu-id="42142-119">Azure AD ID</span></span>                 | <span data-ttu-id="42142-120">Uma ID do Azure AD para um determinado usuário é o único GUID do usuário.</span><span class="sxs-lookup"><span data-stu-id="42142-120">An Azure AD ID for a given user is the unique GUID of the user.</span></span>                 | <span data-ttu-id="42142-121">58006c96-9e6e-45ea-8c88-4a56851eefad</span><span class="sxs-lookup"><span data-stu-id="42142-121">58006c96-9e6e-45ea-8c88-4a56851eefad</span></span>            |
| <span data-ttu-id="42142-122">IDENTIFICAÇÃO de segurança (SID) do Active Directory</span><span class="sxs-lookup"><span data-stu-id="42142-122">Active Directory Security ID (SID)</span></span>                  | <span data-ttu-id="42142-123">SID (identificador de segurança) é um identificador exclusivo que o Active Directory usa para identificar objetos como entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="42142-123">SID (Security Identifier) is a unique identifier that Active Directory uses to identify objects as security principal.</span></span>                  | <span data-ttu-id="42142-124">S-1-5-21-453406510-812318184-4183662089</span><span class="sxs-lookup"><span data-stu-id="42142-124">S-1-5-21-453406510-812318184-4183662089</span></span>             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a><span data-ttu-id="42142-125">2. selecione Propriedades de usuário não do Azure AD para mapear</span><span class="sxs-lookup"><span data-stu-id="42142-125">2. Select non-Azure AD user properties to map</span></span>

<span data-ttu-id="42142-126">Você pode selecionar as propriedades não do Azure AD obtidas da fonte de dados para aplicar as expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="42142-126">You can select non-Azure AD properties pulled from your data source to apply regular expressions on.</span></span> <span data-ttu-id="42142-127">Para saber mais sobre onde encontrar essas propriedades na sua fonte de dados, consulte as páginas do [ServiceNow](servicenow-connector.md) e do [Salesforce](salesforce-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="42142-127">To learn more about where to find these properties in your data source, see the [ServiceNow](servicenow-connector.md) and [Salesforce](salesforce-connector.md) pages.</span></span>  

<span data-ttu-id="42142-128">Você pode selecionar uma propriedade de usuário não do Azure AD na lista suspensa e fornecer uma expressão regular a ser aplicada nesses valores de Propriedade do usuário.</span><span class="sxs-lookup"><span data-stu-id="42142-128">You can select a non-Azure AD user property from the dropdown and provide a regular expression to be applied on those user property values.</span></span> <span data-ttu-id="42142-129">Para saber mais sobre expressões regulares, confira [referência de expressões regulares]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).</span><span class="sxs-lookup"><span data-stu-id="42142-129">To learn more about regular expressions, see [regular expression reference]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>  

<span data-ttu-id="42142-130">Veja a seguir alguns exemplos de expressões regulares e suas saídas aplicadas a uma cadeia de caracteres de amostra:</span><span class="sxs-lookup"><span data-stu-id="42142-130">Below are some examples of regular expressions and their outputs applied to a sample string:</span></span> 

| <span data-ttu-id="42142-131">Cadeia de caracteres de amostra</span><span class="sxs-lookup"><span data-stu-id="42142-131">Sample String</span></span>                  | <span data-ttu-id="42142-132">Expressão regular</span><span class="sxs-lookup"><span data-stu-id="42142-132">Regular expression</span></span>                 | <span data-ttu-id="42142-133">Saída da expressão regular na cadeia de caracteres de amostra</span><span class="sxs-lookup"><span data-stu-id="42142-133">Output of regular expression on sample string</span></span>           |
| :------------------- | :------------------- |:---------------|
| <span data-ttu-id="42142-134">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="42142-134">Alexis Vasquez</span></span>  | <span data-ttu-id="42142-135">.\*</span><span class="sxs-lookup"><span data-stu-id="42142-135">.\*</span></span> | <span data-ttu-id="42142-136">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="42142-136">Alexis Vasquez</span></span> |
| <span data-ttu-id="42142-137">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="42142-137">Alexis Vasquez</span></span>                 | <span data-ttu-id="42142-138">..$</span><span class="sxs-lookup"><span data-stu-id="42142-138">..$</span></span>                 | <span data-ttu-id="42142-139">ez</span><span class="sxs-lookup"><span data-stu-id="42142-139">ez</span></span>            |
| <span data-ttu-id="42142-140">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="42142-140">Alexis Vasquez</span></span>                  | <span data-ttu-id="42142-141">(\w +) $</span><span class="sxs-lookup"><span data-stu-id="42142-141">(\w+)$</span></span>                  | <span data-ttu-id="42142-142">Vasquez</span><span class="sxs-lookup"><span data-stu-id="42142-142">Vasquez</span></span>             |

<span data-ttu-id="42142-143">Você pode adicionar quantas Propriedades de usuário não pertencente ao Azure você quiser as expressões.</span><span class="sxs-lookup"><span data-stu-id="42142-143">You can add as many non-Azure AD user properties as you would like expressions for.</span></span> <span data-ttu-id="42142-144">Você pode aplicar diferentes expressões regulares à mesma propriedade de usuário se sua fórmula final garantir isso.</span><span class="sxs-lookup"><span data-stu-id="42142-144">You can apply different regular expressions to the same user property if your final formula warrants that.</span></span>  

### <a name="3-create-formula-to-complete-mapping"></a><span data-ttu-id="42142-145">3. criar fórmula para concluir o mapeamento</span><span class="sxs-lookup"><span data-stu-id="42142-145">3. Create formula to complete mapping</span></span>

<span data-ttu-id="42142-146">Você pode combinar as saídas de expressões regulares aplicadas a cada uma das suas propriedades de usuário não do Azure AD para formar a propriedade do Azure AD selecionada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="42142-146">You can combine the outputs of the regular expressions applied to each of your non-Azure AD user properties to form the Azure AD property selected in step 1.</span></span>

<span data-ttu-id="42142-147">Na caixa Fórmula, " {0} " corresponde à saída da expressão regular aplicada à *primeira* propriedade não Azure AD que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="42142-147">In the formula box, "{0}" corresponds to the output of the regular expression applied to the *first* non-Azure AD property you selected.</span></span> <span data-ttu-id="42142-148">" {1} " corresponde à saída da expressão regular aplicada à *segunda* propriedade não Azure AD que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="42142-148">"{1}" corresponds to the output of the regular expression applied to the *second* non-Azure AD property you selected.</span></span> <span data-ttu-id="42142-149">" {2} " corresponde à saída da expressão regular aplicada à *terceira* propriedade não do Azure AD e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="42142-149">"{2}" corresponds to the output of the regular expression applied to the *third* non-Azure AD property, and so on.</span></span>  

<span data-ttu-id="42142-150">Veja a seguir alguns exemplos de fórmulas com exemplos de resultados de expressões regulares e saídas de fórmulas:</span><span class="sxs-lookup"><span data-stu-id="42142-150">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span> 

| <span data-ttu-id="42142-151">Fórmula de exemplo</span><span class="sxs-lookup"><span data-stu-id="42142-151">Sample formula</span></span>                  | <span data-ttu-id="42142-152">Valor de {0} no usuário de exemplo</span><span class="sxs-lookup"><span data-stu-id="42142-152">Value of {0} on sample user</span></span>                 | <span data-ttu-id="42142-153">Valor de {1} no usuário de exemplo</span><span class="sxs-lookup"><span data-stu-id="42142-153">Value of {1} on sample user</span></span>           | <span data-ttu-id="42142-154">Saída da fórmula</span><span class="sxs-lookup"><span data-stu-id="42142-154">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="42142-155">{0}.{1} @contoso. com</span><span class="sxs-lookup"><span data-stu-id="42142-155">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="42142-156">FirstName</span><span class="sxs-lookup"><span data-stu-id="42142-156">firstname</span></span> | <span data-ttu-id="42142-157">LastName</span><span class="sxs-lookup"><span data-stu-id="42142-157">lastname</span></span> |<span data-ttu-id="42142-158">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="42142-158">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="42142-159">{0}@domain. com</span><span class="sxs-lookup"><span data-stu-id="42142-159">{0}@domain.com</span></span>                 | <span data-ttu-id="42142-160">ID</span><span class="sxs-lookup"><span data-stu-id="42142-160">userid</span></span>                 |             |<span data-ttu-id="42142-161">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="42142-161">userid@domain.com</span></span>

<span data-ttu-id="42142-162">Depois de fornecer sua fórmula, você pode, opcionalmente, clicar em **Visualizar** para ver uma visualização de cinco usuários aleatórios da fonte de dados com seus respectivos mapeamentos de usuários aplicados.</span><span class="sxs-lookup"><span data-stu-id="42142-162">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="42142-163">A saída da visualização inclui o valor das propriedades de usuário não do Azure AD selecionadas na etapa 2 para esses usuários e a saída da fórmula final fornecida na etapa 3 para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="42142-163">The output of the preview includes the value of the non-Azure AD user properties selected in step 2 for those users and the output of the final formula provided in step 3 for that user.</span></span> <span data-ttu-id="42142-164">Também indica se a saída da fórmula pode ser resolvida para um usuário do Azure AD no locatário por meio de um ícone de "sucesso" ou "falha".</span><span class="sxs-lookup"><span data-stu-id="42142-164">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="42142-165">Você ainda pode prosseguir com a criação de sua conexão se um ou mais mapeamentos de usuário tiverem um status de "falha" após você clicar em **Visualização**.</span><span class="sxs-lookup"><span data-stu-id="42142-165">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="42142-166">A visualização mostra 5 usuários aleatórios e seus mapeamentos da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="42142-166">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="42142-167">Se o mapeamento fornecido não mapear todos os usuários, você pode experimentar esse caso.</span><span class="sxs-lookup"><span data-stu-id="42142-167">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-non-azure-ad-mapping"></a><span data-ttu-id="42142-168">Exemplo de mapeamento não Azure AD</span><span class="sxs-lookup"><span data-stu-id="42142-168">Sample non-Azure AD mapping</span></span>

<span data-ttu-id="42142-169">Confira o instantâneo abaixo para obter um exemplo de mapeamento não Azure AD.</span><span class="sxs-lookup"><span data-stu-id="42142-169">See the snapshot below for a sample non-Azure AD mapping.</span></span>

![Instantâneo de exemplo de como preencher a página de mapeamento não pertencente ao Azure AD](media/non-aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="42142-171">Limitações</span><span class="sxs-lookup"><span data-stu-id="42142-171">Limitations</span></span>  

- <span data-ttu-id="42142-172">Só há suporte para um mapeamento para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="42142-172">Only one mapping is supported for all users.</span></span> <span data-ttu-id="42142-173">Não há suporte para mapeamentos condicionais.</span><span class="sxs-lookup"><span data-stu-id="42142-173">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="42142-174">Não é possível alterar o mapeamento depois que a conexão é publicada.</span><span class="sxs-lookup"><span data-stu-id="42142-174">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="42142-175">Atualmente, somente as expressões baseadas em Regex em relação às propriedades do usuário não AAD têm suporte para a transformação.</span><span class="sxs-lookup"><span data-stu-id="42142-175">Only regex-based expressions against the non-AAD user properties are currently supported for the transformation.</span></span>

- <span data-ttu-id="42142-176">Há apenas 3 identidades do Azure AD que você pode escolher para mapear (UPN, ID do Azure AD e SID do AD).</span><span class="sxs-lookup"><span data-stu-id="42142-176">There are only 3 Azure AD identities you can choose to map to (UPN, Azure AD ID, and AD SID).</span></span>