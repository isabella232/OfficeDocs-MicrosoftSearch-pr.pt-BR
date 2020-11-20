---
title: Azure DevOps Connector para Microsoft Search
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do Azure DevOps para o Microsoft Search
ms.openlocfilehash: b9c566e3e07bfca6d4d25b14915f0160f3928b15
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367546"
---
# <a name="azure-devops-connector-preview"></a><span data-ttu-id="92b89-103">Azure DevOps Connector (visualização)</span><span class="sxs-lookup"><span data-stu-id="92b89-103">Azure DevOps connector (preview)</span></span>

<span data-ttu-id="92b89-104">Com o conector DevOps do Azure, sua organização pode indexar itens de trabalho em sua instância do serviço do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="92b89-104">With the Azure DevOps connector, your organization can index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="92b89-105">Depois de configurar o conector e o conteúdo do índice do Azure DevOps, os usuários finais podem pesquisar esses itens no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="92b89-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

<span data-ttu-id="92b89-106">Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector do DevOps do Azure.</span><span class="sxs-lookup"><span data-stu-id="92b89-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure DevOps connector.</span></span> <span data-ttu-id="92b89-107">Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="92b89-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="92b89-108">O conector do Azure DevOps oferece suporte somente ao serviço de nuvem do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="92b89-108">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="92b89-109">O Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 e TFS 2013 não são suportados por esse conector.</span><span class="sxs-lookup"><span data-stu-id="92b89-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span> 

## <a name="connect-to-a-data-source"></a><span data-ttu-id="92b89-110">Conectar-se a uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="92b89-110">Connect to a data source</span></span>

<span data-ttu-id="92b89-111">Para se conectar à sua instância do Azure DevOps, você precisa do seu Azure DevOps nome da [organização](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) , sua ID do aplicativo e o segredo do cliente para autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="92b89-111">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="92b89-112">Registrar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="92b89-112">Register an app</span></span>

<span data-ttu-id="92b89-113">Você deve registrar um aplicativo no Azure DevOps para que o aplicativo de pesquisa da Microsoft possa acessar a instância.</span><span class="sxs-lookup"><span data-stu-id="92b89-113">You must register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="92b89-114">Para saber mais, confira a documentação do Azure DevOps sobre como [registrar um aplicativo](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span><span class="sxs-lookup"><span data-stu-id="92b89-114">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span></span> 

<span data-ttu-id="92b89-115">A tabela a seguir fornece orientação sobre como preencher o formulário de registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="92b89-115">The following table provides guidance on how to fill out the app registration form:</span></span>

 <span data-ttu-id="92b89-116">**Campos obrigatórios**</span><span class="sxs-lookup"><span data-stu-id="92b89-116">**Mandatory Fields**</span></span> | <span data-ttu-id="92b89-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="92b89-117">**Description**</span></span>      | <span data-ttu-id="92b89-118">**Valor recomendado**</span><span class="sxs-lookup"><span data-stu-id="92b89-118">**Recommended Value**</span></span> 
--- | --- | --- 
| <span data-ttu-id="92b89-119">Nome da empresa</span><span class="sxs-lookup"><span data-stu-id="92b89-119">Company Name</span></span>         | <span data-ttu-id="92b89-120">Este é o nome da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="92b89-120">This is the name of your company.</span></span> | <span data-ttu-id="92b89-121">Usar um valor apropriado</span><span class="sxs-lookup"><span data-stu-id="92b89-121">Use an appropriate value</span></span>   | 
| <span data-ttu-id="92b89-122">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="92b89-122">Application name</span></span>     | <span data-ttu-id="92b89-123">Esse valor exclusivo identifica o aplicativo que você está autorizando.</span><span class="sxs-lookup"><span data-stu-id="92b89-123">This unique value identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="92b89-124">Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="92b89-124">Microsoft Search</span></span>     | 
| <span data-ttu-id="92b89-125">Site do aplicativo</span><span class="sxs-lookup"><span data-stu-id="92b89-125">Application website</span></span>  | <span data-ttu-id="92b89-126">Este campo obrigatório é a URL do aplicativo que solicitará acesso à instância do DevOps do Azure durante a configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="92b89-126">This required field is the URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span>  | <https://gcs.office.com/>                | 
| <span data-ttu-id="92b89-127">URL de retorno de chamada de autorização</span><span class="sxs-lookup"><span data-stu-id="92b89-127">Authorization callback URL</span></span>        | <span data-ttu-id="92b89-128">Uma URL de retorno de chamada necessária para a qual o servidor de autorização é redirecionado.</span><span class="sxs-lookup"><span data-stu-id="92b89-128">A required callback URL that the authorization server redirects to.</span></span> | <https://gcs.office.com/v1.0/admin/oauth/callback>| 
| <span data-ttu-id="92b89-129">Escopos autorizados</span><span class="sxs-lookup"><span data-stu-id="92b89-129">Authorized scopes</span></span> | <span data-ttu-id="92b89-130">Este é o escopo de acesso para o aplicativo</span><span class="sxs-lookup"><span data-stu-id="92b89-130">This is the scope of access for the application</span></span> | <span data-ttu-id="92b89-131">Selecione os seguintes escopos: identidade (leitura), itens de trabalho (leitura), grupos de variáveis (leitura), projeto e equipe (leitura), gráfico (leitura)</span><span class="sxs-lookup"><span data-stu-id="92b89-131">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>| 

<span data-ttu-id="92b89-132">Ao registrar o aplicativo com os detalhes acima, você receberá a **ID do aplicativo** e o **segredo do cliente** que será usado para configurar o conector.</span><span class="sxs-lookup"><span data-stu-id="92b89-132">On registering the app with the details above, you will get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="92b89-133">Para revogar o acesso a qualquer aplicativo registrado no Azure DevOps, acesse configurações do usuário na parte superior direita de sua instância do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="92b89-133">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="92b89-134">Clique em perfil e, em seguida, clique em autorizações na seção segurança do painel lateral.</span><span class="sxs-lookup"><span data-stu-id="92b89-134">Click on Profile and then click on Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="92b89-135">Passe o mouse sobre um aplicativo OAuth autorizado para ver o botão revogar no canto dos detalhes do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="92b89-135">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="92b89-136">Configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="92b89-136">Connection settings</span></span>

<span data-ttu-id="92b89-137">Após registrar o aplicativo de pesquisa da Microsoft com o Azure DevOps, você pode concluir a etapa de configurações de conexão.</span><span class="sxs-lookup"><span data-stu-id="92b89-137">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="92b89-138">Insira o nome da sua organização, a ID do aplicativo e o segredo do cliente.</span><span class="sxs-lookup"><span data-stu-id="92b89-138">Enter your organization name, App ID, and Client secret.</span></span>

![Configurações do aplicativo de conexão](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a><span data-ttu-id="92b89-140">Selecionar projetos e campos</span><span class="sxs-lookup"><span data-stu-id="92b89-140">Select projects and fields</span></span>

<span data-ttu-id="92b89-141">Você pode escolher para que a conexão seja indexada para toda a organização ou para projetos específicos.</span><span class="sxs-lookup"><span data-stu-id="92b89-141">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="92b89-142">Se você optar por indexar toda a organização, os itens em todos os projetos da organização serão indexados.</span><span class="sxs-lookup"><span data-stu-id="92b89-142">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="92b89-143">Novos projetos e itens serão indexados durante o próximo rastreamento após serem criados.</span><span class="sxs-lookup"><span data-stu-id="92b89-143">New projects and items will be indexed during the next crawl after they are created.</span></span> <span data-ttu-id="92b89-144">Se você escolher projetos individuais, somente os itens de trabalho nesses projetos serão indexados.</span><span class="sxs-lookup"><span data-stu-id="92b89-144">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurar dados](media/ADO_Configure_data.png)

<span data-ttu-id="92b89-146">Em seguida, selecione quais campos você deseja que a conexão indexe e visualize dados nesses campos antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="92b89-146">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Escolher Propriedades](media/ADO_choose_properties.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="92b89-148">Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="92b89-148">Manage search permissions</span></span>

<span data-ttu-id="92b89-149">O conector do Azure DevOps oferece suporte a permissões de pesquisa visíveis para  **apenas as pessoas com acesso a essa fonte de dados ou a** **todos**.</span><span class="sxs-lookup"><span data-stu-id="92b89-149">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="92b89-150">Se você escolher **apenas as pessoas com acesso a essa fonte de dados**, os dados indexados aparecerão nos resultados da pesquisa para usuários que têm acesso com base em permissões a usuários ou grupos na organização, no nível do caminho do projeto ou da área no Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="92b89-150">If you choose **Only people with access to this data source**,indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="92b89-151">Se você escolher **todos**, os dados indexados serão exibidos nos resultados da pesquisa para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="92b89-151">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="92b89-152">Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="92b89-152">Assign property labels</span></span>

<span data-ttu-id="92b89-153">Você pode atribuir uma propriedade Source a cada rótulo escolhendo a partir de um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="92b89-153">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="92b89-154">Embora esta etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="92b89-154">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="92b89-155">Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="92b89-155">Manage schema</span></span>

<span data-ttu-id="92b89-156">Na tela **gerenciar esquema** , você tem a opção de alterar os atributos de esquema (**consultável**, **pesquisável**, **recuperável** e **refinável**) associados às propriedades, adicionar aliases opcionais e escolher a propriedade **Content** .</span><span class="sxs-lookup"><span data-stu-id="92b89-156">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="92b89-157">Definir o agendamento de atualização</span><span class="sxs-lookup"><span data-stu-id="92b89-157">Set the refresh schedule</span></span>

<span data-ttu-id="92b89-158">O conector do Azure DevOps suporta agendas de atualização para rastreamentos completos e incrementais.</span><span class="sxs-lookup"><span data-stu-id="92b89-158">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="92b89-159">Um rastreamento completo localiza itens de trabalho excluídos que foram sincronizados anteriormente com o índice de pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92b89-159">A full crawl finds deleted work items that were previously synced to the Microsoft Search index.</span></span> <span data-ttu-id="92b89-160">Um rastreamento completo é executado para sincronizar todos os itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="92b89-160">A full crawl runs to sync all the work items.</span></span> <span data-ttu-id="92b89-161">Para sincronizar novos itens de trabalho e atualizações para itens de trabalho existentes, você precisa agendar rastreamentos incrementais.</span><span class="sxs-lookup"><span data-stu-id="92b89-161">To sync new work items and updates to existing work items, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="92b89-162">O cronograma recomendado é uma hora para um rastreamento incremental e um dia para um rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="92b89-162">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span> 