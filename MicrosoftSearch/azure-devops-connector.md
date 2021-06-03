---
title: Azure DevOps Graph conector para Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector Azure DevOps Graph para a Pesquisa da Microsoft
ms.openlocfilehash: bfe04a022360a968424b673ad03ba05f27c8c333
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720948"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="378f4-103">Azure DevOps Graph conector (visualização)</span><span class="sxs-lookup"><span data-stu-id="378f4-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="378f4-104">O Azure DevOps Graph conector permite que sua organização indexe itens de trabalho em sua instância do Azure DevOps serviço.</span><span class="sxs-lookup"><span data-stu-id="378f4-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="378f4-105">Depois de configurar o conector e o conteúdo de índice Azure DevOps, os usuários finais poderão pesquisar esses itens na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="378f4-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="378f4-106">Leia o [**artigo Instalação do conector Graph para**](configure-connector.md) entender as instruções gerais Graph configuração de conectores.</span><span class="sxs-lookup"><span data-stu-id="378f4-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="378f4-107">Este artigo é para qualquer pessoa que configure, executa e monitore um conector Azure DevOps Graph usuário.</span><span class="sxs-lookup"><span data-stu-id="378f4-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="378f4-108">Ele complementa o processo de instalação geral e mostra instruções que se aplicam apenas ao conector Azure DevOps Graph de segurança.</span><span class="sxs-lookup"><span data-stu-id="378f4-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="378f4-109">O Azure DevOps conector suporta apenas o serviço Azure DevOps nuvem.</span><span class="sxs-lookup"><span data-stu-id="378f4-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="378f4-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 e TFS 2013 não são suportados por esse conector.</span><span class="sxs-lookup"><span data-stu-id="378f4-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="378f4-111">Etapa 1: adicionar um conector Graph no centro de Microsoft 365 de administração</span><span class="sxs-lookup"><span data-stu-id="378f4-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="378f4-112">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="378f4-112">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="378f4-113">Etapa 2: nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="378f4-113">Step 2: Name the connection</span></span>

<span data-ttu-id="378f4-114">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="378f4-114">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="378f4-115">Etapa 3: Configurar as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="378f4-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="378f4-116">Para se conectar à sua instância Azure DevOps, você [](/azure/devops/organizations/accounts/create-organization) precisa do nome da sua Azure DevOps, sua ID de aplicativo e segredo do cliente para autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="378f4-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="378f4-117">Registrar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="378f4-117">Register an app</span></span>

<span data-ttu-id="378f4-118">Registre um aplicativo no Azure DevOps para que o aplicativo de Pesquisa da Microsoft possa acessar a instância.</span><span class="sxs-lookup"><span data-stu-id="378f4-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="378f4-119">Para saber mais, confira Azure DevOps sobre como registrar [um aplicativo.](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)</span><span class="sxs-lookup"><span data-stu-id="378f4-119">To learn more, see Azure DevOps documentation on how to [register an app](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="378f4-120">A tabela a seguir fornece orientações sobre como preencher o formulário de registro do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="378f4-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="378f4-121">Campos Obrigatórios</span><span class="sxs-lookup"><span data-stu-id="378f4-121">Mandatory Fields</span></span> | <span data-ttu-id="378f4-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="378f4-122">Description</span></span> | <span data-ttu-id="378f4-123">Valor Recomendado</span><span class="sxs-lookup"><span data-stu-id="378f4-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="378f4-124">Nome da empresa</span><span class="sxs-lookup"><span data-stu-id="378f4-124">Company Name</span></span>         | <span data-ttu-id="378f4-125">O nome da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="378f4-125">The name of your company.</span></span> | <span data-ttu-id="378f4-126">Usar um valor apropriado</span><span class="sxs-lookup"><span data-stu-id="378f4-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="378f4-127">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="378f4-127">Application name</span></span>     | <span data-ttu-id="378f4-128">Um valor exclusivo que identifica o aplicativo que você está autorizando.</span><span class="sxs-lookup"><span data-stu-id="378f4-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="378f4-129">Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="378f4-129">Microsoft Search</span></span>     |
| <span data-ttu-id="378f4-130">Site do aplicativo</span><span class="sxs-lookup"><span data-stu-id="378f4-130">Application website</span></span>  | <span data-ttu-id="378f4-131">A URL do aplicativo que solicitará acesso à sua instância Azure DevOps durante a instalação do conector.</span><span class="sxs-lookup"><span data-stu-id="378f4-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="378f4-132">(Obrigatório).</span><span class="sxs-lookup"><span data-stu-id="378f4-132">(Required).</span></span>  | <span data-ttu-id="378f4-133"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="378f4-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="378f4-134">URL de retorno de chamada de autorização</span><span class="sxs-lookup"><span data-stu-id="378f4-134">Authorization callback URL</span></span>        | <span data-ttu-id="378f4-135">Uma URL de retorno de chamada necessária para a que o servidor de autorização redireciona.</span><span class="sxs-lookup"><span data-stu-id="378f4-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="378f4-136"> https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="378f4-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="378f4-137">Escopos autorizados</span><span class="sxs-lookup"><span data-stu-id="378f4-137">Authorized scopes</span></span> | <span data-ttu-id="378f4-138">O escopo de acesso para o aplicativo</span><span class="sxs-lookup"><span data-stu-id="378f4-138">The scope of access for the application</span></span> | <span data-ttu-id="378f4-139">Selecione os seguintes escopos: Identidade (leitura), Itens de Trabalho (leitura), Grupos Variáveis (leitura), Project e equipe (leitura), Graph (leitura)</span><span class="sxs-lookup"><span data-stu-id="378f4-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

>[!IMPORTANT]
><span data-ttu-id="378f4-140">Os escopos autorizados selecionados para o aplicativo devem corresponder aos escopos exatamente como listado acima.</span><span class="sxs-lookup"><span data-stu-id="378f4-140">The authorized scopes that you select for the app should match the scopes exactly as listed above.</span></span> <span data-ttu-id="378f4-141">Se você omitir um dos escopos autorizados na lista ou adicionar outro escopo, a autorização falhará.</span><span class="sxs-lookup"><span data-stu-id="378f4-141">If you omit one of the authorized scopes in the list, or add another scope, the authorization will fail.</span></span>

<span data-ttu-id="378f4-142">Ao registrar o aplicativo com os detalhes acima, você receberá a **ID** do aplicativo e o **Segredo** do Cliente que serão usados para configurar o conector.</span><span class="sxs-lookup"><span data-stu-id="378f4-142">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="378f4-143">Para revogar o acesso a qualquer aplicativo registrado Azure DevOps, acesse Configurações do usuário na parte superior direita da sua Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="378f4-143">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="378f4-144">Selecione Perfil e, em seguida, selecione Autorizações na seção Segurança do painel lateral.</span><span class="sxs-lookup"><span data-stu-id="378f4-144">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="378f4-145">Passe o mouse sobre um aplicativo OAuth autorizado para ver o botão Revogar no canto dos detalhes do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="378f4-145">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="378f4-146">Configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="378f4-146">Connection settings</span></span>

<span data-ttu-id="378f4-147">Depois de registrar o aplicativo de Pesquisa da Microsoft com Azure DevOps, você pode concluir a etapa de configurações de conexão.</span><span class="sxs-lookup"><span data-stu-id="378f4-147">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="378f4-148">Insira o nome da sua organização, a ID do aplicativo e o segredo do cliente.</span><span class="sxs-lookup"><span data-stu-id="378f4-148">Enter your organization name, App ID, and Client secret.</span></span>

![Aplicativo de conexão Configurações](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="378f4-150">Configurar dados: selecionar projetos e campos</span><span class="sxs-lookup"><span data-stu-id="378f4-150">Configure data: select projects and fields</span></span>

<span data-ttu-id="378f4-151">Você pode escolher a conexão para indexar toda a organização ou projetos específicos.</span><span class="sxs-lookup"><span data-stu-id="378f4-151">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="378f4-152">Se você optar por indexar toda a organização, os itens em todos os projetos da organização serão indexados.</span><span class="sxs-lookup"><span data-stu-id="378f4-152">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="378f4-153">Novos projetos e itens serão indexados durante o próximo rastreamento depois que eles são criados.</span><span class="sxs-lookup"><span data-stu-id="378f4-153">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="378f4-154">Se você escolher projetos individuais, somente os itens de trabalho nesses projetos serão indexados.</span><span class="sxs-lookup"><span data-stu-id="378f4-154">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurar dados](media/ADO_Configure_data.png)

<span data-ttu-id="378f4-156">Em seguida, selecione quais campos você deseja que a conexão indexe e visualize dados nesses campos antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="378f4-156">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Escolher propriedades](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="378f4-158">Etapa 4: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="378f4-158">Step 4: Manage search permissions</span></span>

<span data-ttu-id="378f4-159">O Azure DevOps conector dá suporte a permissões de pesquisa visíveis somente para pessoas com acesso a essa fonte de  **dados** ou a **Todos.**</span><span class="sxs-lookup"><span data-stu-id="378f4-159">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="378f4-160">Se você escolher Somente pessoas com acesso a essa fonte de **dados,** os dados indexados aparecerão nos resultados da pesquisa para usuários que têm acesso a eles com base em permissões para usuários ou grupos na Organização, nível de caminho de Project ou Área no Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="378f4-160">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="378f4-161">Se você escolher **Todos**, os dados indexados aparecerão nos resultados da pesquisa para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="378f4-161">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="378f4-162">Etapa 5: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="378f4-162">Step 5: Assign property labels</span></span>

<span data-ttu-id="378f4-163">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="378f4-163">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="378f4-164">Etapa 6: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="378f4-164">Step 6: Manage schema</span></span>

<span data-ttu-id="378f4-165">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="378f4-165">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="378f4-166">Etapa 7: Escolher configurações de atualização</span><span class="sxs-lookup"><span data-stu-id="378f4-166">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="378f4-167">O Azure DevOps conector suporta agendamentos de atualização para rastreamentos completos e incrementais.</span><span class="sxs-lookup"><span data-stu-id="378f4-167">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="378f4-168">A agenda recomendada é de uma hora para um rastreamento incremental e um dia para um rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="378f4-168">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="378f4-169">Etapa 8: Revisar conexão</span><span class="sxs-lookup"><span data-stu-id="378f4-169">Step 8: Review connection</span></span>

<span data-ttu-id="378f4-170">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="378f4-170">Follow the general [setup instructions](./configure-connector.md).</span></span>

>[!TIP]
><span data-ttu-id="378f4-171">**Tipo de resultado padrão**</span><span class="sxs-lookup"><span data-stu-id="378f4-171">**Default Result type**</span></span>
>* <span data-ttu-id="378f4-172">O Azure DevOps conector registra automaticamente um tipo [de resultado](./customize-search-page.md#step-2-create-the-result-types) depois que o conector é publicado.</span><span class="sxs-lookup"><span data-stu-id="378f4-172">The Azure DevOps connector automatically registers a [result type](./customize-search-page.md#step-2-create-the-result-types) once the connector is published.</span></span> <span data-ttu-id="378f4-173">O tipo de resultado usa um layout de [resultado](./customize-results-layout.md) gerado dinamicamente com base nos campos selecionados na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="378f4-173">The result type uses a dynamically generated [result layout](./customize-results-layout.md) based on the fields selected in step 3.</span></span> 
>* <span data-ttu-id="378f4-174">Você pode gerenciar o tipo de resultado navegando até [**Tipos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) de resultado no Microsoft 365 [de administração.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="378f4-174">You can manage the result type by navigating to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="378f4-175">O tipo de resultado padrão será nomeado como " `ConnectionId` Padrão".</span><span class="sxs-lookup"><span data-stu-id="378f4-175">The default result type will be named as "`ConnectionId`Default".</span></span> <span data-ttu-id="378f4-176">Por exemplo, se sua id de conexão for `AzureDevOps` , seu layout de resultado será nomeado: "AzureDevOpsDefault"</span><span class="sxs-lookup"><span data-stu-id="378f4-176">For example, if your connection id is `AzureDevOps`, your result layout will be named: "AzureDevOpsDefault"</span></span>
>* <span data-ttu-id="378f4-177">Além disso, você pode optar por criar seu próprio tipo de resultado, se necessário.</span><span class="sxs-lookup"><span data-stu-id="378f4-177">Also, you can choose to create your own result type if needed.</span></span>

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->