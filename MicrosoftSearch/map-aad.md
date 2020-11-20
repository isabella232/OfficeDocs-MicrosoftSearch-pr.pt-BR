---
title: Mapeando identidades do AAD
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
description: Etapas sobre como mapear identidades do AAD
ms.openlocfilehash: db0378e596c560edebd2ceb942e6327b47a5286b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367699"
---
# <a name="map-your-azure-ad-identities"></a><span data-ttu-id="b12a5-103">Mapear suas identidades do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b12a5-103">Map your Azure AD Identities</span></span>  

<span data-ttu-id="b12a5-104">Este artigo apresenta as etapas de mapeamento de suas identidades do Azure AD para um identificador exclusivo para sua fonte de dados (identidade não-Azure AD) para que as pessoas em sua lista de controle de acesso (ACL) com identidades não do Azure AD possam ver os resultados de pesquisa do conector com escopo.</span><span class="sxs-lookup"><span data-stu-id="b12a5-104">This article walks you through the steps of mapping your Azure AD identities to a unique identifier for your data source (non-Azure AD identity) so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="b12a5-105">Essas etapas só são relevantes para os administradores de pesquisa que estão Configurando um conector [Salesforce](salesforce-connector.md) pela Microsoft com permissões de pesquisa para "apenas pessoas com acesso a esta fonte de dados" e tipo de identidade "AAD".</span><span class="sxs-lookup"><span data-stu-id="b12a5-105">These steps are only relevant to search administrators who are setting up a [Salesforce](salesforce-connector.md) connector by Microsoft with search permissions for "Only people with access to this data source" and identity type "AAD."</span></span> <span data-ttu-id="b12a5-106">As etapas a seguir explicam como mapear suas propriedades de usuário do Azure AD para as **IDs de Federação** dos usuários.</span><span class="sxs-lookup"><span data-stu-id="b12a5-106">The following steps walk you through how to map your Azure AD user properties to your users' **Federation IDs**.</span></span>

>[!NOTE]
><span data-ttu-id="b12a5-107">Se você estiver configurando [um conector do Salesforce](salesforce-connector.md) e selecionar **apenas as pessoas com acesso a essa fonte de dados** e tipo de identidade **não-AAD** na tela de permissões de pesquisa, consulte o artigo [map your non-Azure ad Identities](map-non-aad.md) para obter etapas sobre como mapear identidades não pertencentes ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b12a5-107">If you are setting up a [Salesforce connector](salesforce-connector.md) and select **Only people with access to this data source** and identity type **non-AAD** on the search permissions screen, refer to the [Map your non-Azure AD Identities](map-non-aad.md) article for steps on how to map non-Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-azure-ad-properties"></a><span data-ttu-id="b12a5-108">Etapas para mapeamento de suas propriedades do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b12a5-108">Steps for mapping your Azure AD properties</span></span>

### <a name="1-select-azure-ad-user-properties-to-map"></a><span data-ttu-id="b12a5-109">1. selecionar Propriedades de usuário do Azure AD para mapear</span><span class="sxs-lookup"><span data-stu-id="b12a5-109">1. Select Azure AD user properties to map</span></span>

<span data-ttu-id="b12a5-110">Você pode selecionar as propriedades do Azure AD que você precisa mapear para a ID de Federação.</span><span class="sxs-lookup"><span data-stu-id="b12a5-110">You can select the Azure AD properties you need to map to the Federation ID.</span></span>

<span data-ttu-id="b12a5-111">Você pode selecionar uma propriedade de usuário do Azure AD na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b12a5-111">You can select an Azure AD user property from the dropdown.</span></span> <span data-ttu-id="b12a5-112">Você também pode adicionar tantas propriedades de usuário do Azure AD quantas quiser se essas propriedades forem necessárias para criar o mapeamento de ID de Federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b12a5-112">You can also add as many Azure AD user properties as you would like if these properties are necessary to create the Federation ID mapping for your organization.</span></span>

### <a name="2-create-formula-to-complete-mapping"></a><span data-ttu-id="b12a5-113">2. criar fórmula para concluir o mapeamento</span><span class="sxs-lookup"><span data-stu-id="b12a5-113">2. Create formula to complete mapping</span></span>

<span data-ttu-id="b12a5-114">Você pode combinar os valores das propriedades de usuário do Azure AD para formar a ID de Federação exclusiva.</span><span class="sxs-lookup"><span data-stu-id="b12a5-114">You can combine the values of the Azure AD user properties to form the unique Federation ID.</span></span>

<span data-ttu-id="b12a5-115">Na caixa Fórmula, " {0} " corresponde à *primeira* Propriedade do Azure AD que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="b12a5-115">In the formula box, "{0}" corresponds to the *first* Azure AD property you selected.</span></span> <span data-ttu-id="b12a5-116">" {1} " corresponde à *segunda* Propriedade do Azure AD que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="b12a5-116">"{1}" corresponds to the *second* Azure AD property you selected.</span></span> <span data-ttu-id="b12a5-117">" {2} " corresponde à *terceira* Propriedade do Azure AD e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="b12a5-117">"{2}" corresponds to the *third* Azure AD property, and so on.</span></span>  

<span data-ttu-id="b12a5-118">Veja a seguir alguns exemplos de fórmulas com exemplos de resultados de expressões regulares e saídas de fórmulas:</span><span class="sxs-lookup"><span data-stu-id="b12a5-118">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span>

| <span data-ttu-id="b12a5-119">Fórmula de exemplo</span><span class="sxs-lookup"><span data-stu-id="b12a5-119">Sample formula</span></span>                  | <span data-ttu-id="b12a5-120">Valor da propriedade {0} de um usuário de amostra</span><span class="sxs-lookup"><span data-stu-id="b12a5-120">Value of property {0} for a sample user</span></span>                 | <span data-ttu-id="b12a5-121">Valor da propriedade {1} de um usuário de amostra</span><span class="sxs-lookup"><span data-stu-id="b12a5-121">Value of property {1} for a sample user</span></span>           | <span data-ttu-id="b12a5-122">Saída da fórmula</span><span class="sxs-lookup"><span data-stu-id="b12a5-122">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="b12a5-123">{0}.{1} @contoso. com</span><span class="sxs-lookup"><span data-stu-id="b12a5-123">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="b12a5-124">FirstName</span><span class="sxs-lookup"><span data-stu-id="b12a5-124">firstname</span></span> | <span data-ttu-id="b12a5-125">LastName</span><span class="sxs-lookup"><span data-stu-id="b12a5-125">lastname</span></span> |<span data-ttu-id="b12a5-126">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b12a5-126">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="b12a5-127">{0}@domain. com</span><span class="sxs-lookup"><span data-stu-id="b12a5-127">{0}@domain.com</span></span>                 | <span data-ttu-id="b12a5-128">ID</span><span class="sxs-lookup"><span data-stu-id="b12a5-128">userid</span></span>                 |             |<span data-ttu-id="b12a5-129">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="b12a5-129">userid@domain.com</span></span>

<span data-ttu-id="b12a5-130">Depois de fornecer sua fórmula, você pode, opcionalmente, clicar em **Visualizar** para ver uma visualização de cinco usuários aleatórios da fonte de dados com seus respectivos mapeamentos de usuários aplicados.</span><span class="sxs-lookup"><span data-stu-id="b12a5-130">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="b12a5-131">A saída da visualização inclui o valor das propriedades de usuário do Azure AD selecionadas na etapa 1 para esses usuários e a saída da fórmula final fornecida na etapa 2 para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="b12a5-131">The output of the preview includes the value of the Azure AD user properties selected in step 1 for those users and the output of the final formula provided in step 2 for that user.</span></span> <span data-ttu-id="b12a5-132">Também indica se a saída da fórmula pode ser resolvida para um usuário do Azure AD no locatário por meio de um ícone de "sucesso" ou "falha".</span><span class="sxs-lookup"><span data-stu-id="b12a5-132">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="b12a5-133">Você ainda pode prosseguir com a criação de sua conexão se um ou mais mapeamentos de usuário tiverem um status de "falha" após você clicar em **Visualização**.</span><span class="sxs-lookup"><span data-stu-id="b12a5-133">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="b12a5-134">A visualização mostra 5 usuários aleatórios e seus mapeamentos da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b12a5-134">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="b12a5-135">Se o mapeamento fornecido não mapear todos os usuários, você pode experimentar esse caso.</span><span class="sxs-lookup"><span data-stu-id="b12a5-135">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-azure-ad-mapping"></a><span data-ttu-id="b12a5-136">Exemplo de mapeamento do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b12a5-136">Sample Azure AD mapping</span></span>

<span data-ttu-id="b12a5-137">Confira o instantâneo abaixo para obter um exemplo de mapeamento do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b12a5-137">See the snapshot below for a sample Azure AD mapping.</span></span>

![Instantâneo de exemplo de como preencher a página de mapeamento do Azure AD](media/aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="b12a5-139">Limitações</span><span class="sxs-lookup"><span data-stu-id="b12a5-139">Limitations</span></span>  

- <span data-ttu-id="b12a5-140">Só há suporte para um mapeamento para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="b12a5-140">Only one mapping is supported for all users.</span></span> <span data-ttu-id="b12a5-141">Não há suporte para mapeamentos condicionais.</span><span class="sxs-lookup"><span data-stu-id="b12a5-141">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="b12a5-142">Não é possível alterar o mapeamento depois que a conexão é publicada.</span><span class="sxs-lookup"><span data-stu-id="b12a5-142">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="b12a5-143">Não há suporte para as expressões baseadas em Regex nas propriedades de usuário do Azure AD para a transformação de ID de Federação do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b12a5-143">Regex-based expressions against the Azure AD user properties are not supported for the Azure AD to Federation ID transformation.</span></span>