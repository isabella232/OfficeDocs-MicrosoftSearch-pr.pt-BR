---
title: Conector do Azure DevOps Graph para a Pesquisa da Microsoft
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
description: Configurar o conector do Azure DevOps Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 8fe783c847c672223e051f4433af3e41678fe367
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097399"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="70986-103">Conector do Azure DevOps Graph (visualização)</span><span class="sxs-lookup"><span data-stu-id="70986-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="70986-104">O conector do Azure DevOps Graph permite que sua organização indexe itens de trabalho em sua instância do serviço Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="70986-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="70986-105">Depois de configurar o conector e o conteúdo de índice do Azure DevOps, os usuários finais podem procurar esses itens na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70986-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="70986-106">Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="70986-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="70986-107">Este artigo é destinado a qualquer pessoa que configure, seja executado e monitore um conector do Azure DevOps Graph.</span><span class="sxs-lookup"><span data-stu-id="70986-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="70986-108">Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector do Azure DevOps Graph.</span><span class="sxs-lookup"><span data-stu-id="70986-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="70986-109">O conector do Azure DevOps é compatível apenas com o serviço de nuvem do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="70986-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="70986-110">O Azure DevOps Server 2019, o TFS 2018, o TFS 2017, o TFS 2015 e o TFS 2013 não são compatíveis com esse conector.</span><span class="sxs-lookup"><span data-stu-id="70986-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="70986-111">Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70986-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="70986-112">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="70986-112">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="70986-113">Etapa 2: Nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="70986-113">Step 2: Name the connection</span></span>

<span data-ttu-id="70986-114">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="70986-114">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="70986-115">Etapa 3: Definir as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="70986-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="70986-116">Para se conectar à instância do Azure DevOps, [](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) você precisa do nome da organização do Azure DevOps, da ID do aplicativo e do segredo do cliente para autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="70986-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="70986-117">Registrar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="70986-117">Register an app</span></span>

<span data-ttu-id="70986-118">Registre um aplicativo no Azure DevOps para que o aplicativo Pesquisa da Microsoft possa acessar a instância.</span><span class="sxs-lookup"><span data-stu-id="70986-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="70986-119">Para saber mais, consulte a documentação do Azure DevOps sobre como [registrar um aplicativo.](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="70986-119">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true).</span></span>

<span data-ttu-id="70986-120">A tabela a seguir fornece orientações sobre como preencher o formulário de registro do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="70986-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="70986-121">Campos obrigatórios</span><span class="sxs-lookup"><span data-stu-id="70986-121">Mandatory Fields</span></span> | <span data-ttu-id="70986-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="70986-122">Description</span></span> | <span data-ttu-id="70986-123">Valor Recomendado</span><span class="sxs-lookup"><span data-stu-id="70986-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="70986-124">Nome da Empresa</span><span class="sxs-lookup"><span data-stu-id="70986-124">Company Name</span></span>         | <span data-ttu-id="70986-125">O nome da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="70986-125">The name of your company.</span></span> | <span data-ttu-id="70986-126">Usar um valor apropriado</span><span class="sxs-lookup"><span data-stu-id="70986-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="70986-127">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="70986-127">Application name</span></span>     | <span data-ttu-id="70986-128">Um valor exclusivo que identifica o aplicativo que você está autorizando.</span><span class="sxs-lookup"><span data-stu-id="70986-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="70986-129">Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="70986-129">Microsoft Search</span></span>     |
| <span data-ttu-id="70986-130">Site do aplicativo</span><span class="sxs-lookup"><span data-stu-id="70986-130">Application website</span></span>  | <span data-ttu-id="70986-131">A URL do aplicativo que solicitará acesso à instância do Azure DevOps durante a configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="70986-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="70986-132">(Obrigatório).</span><span class="sxs-lookup"><span data-stu-id="70986-132">(Required).</span></span>  | <span data-ttu-id="70986-133"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="70986-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="70986-134">URL de retorno de chamada de autorização</span><span class="sxs-lookup"><span data-stu-id="70986-134">Authorization callback URL</span></span>        | <span data-ttu-id="70986-135">Uma URL de retorno de chamada necessária para a que o servidor de autorização redireciona.</span><span class="sxs-lookup"><span data-stu-id="70986-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="70986-136"> https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="70986-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="70986-137">Escopos autorizados</span><span class="sxs-lookup"><span data-stu-id="70986-137">Authorized scopes</span></span> | <span data-ttu-id="70986-138">O escopo de acesso para o aplicativo</span><span class="sxs-lookup"><span data-stu-id="70986-138">The scope of access for the application</span></span> | <span data-ttu-id="70986-139">Selecione os seguintes escopos: Identidade (leitura), Itens de Trabalho (lidos), Grupos de Variáveis (lidos), Projeto e equipe (lido), Gráfico (lido)</span><span class="sxs-lookup"><span data-stu-id="70986-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="70986-140">Ao registrar o aplicativo com os detalhes acima, você  receberá a **ID** do aplicativo e o Segredo do Cliente que serão usados para configurar o conector.</span><span class="sxs-lookup"><span data-stu-id="70986-140">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="70986-141">Para revogar o acesso a qualquer aplicativo registrado no Azure DevOps, vá para Configurações do usuário na parte superior direita da instância do Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="70986-141">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="70986-142">Selecione Perfil e Autorizações na seção Segurança do painel lateral.</span><span class="sxs-lookup"><span data-stu-id="70986-142">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="70986-143">Passe o mouse sobre um aplicativo OAuth autorizado para ver o botão Revogar no canto dos detalhes do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="70986-143">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="70986-144">Configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="70986-144">Connection settings</span></span>

<span data-ttu-id="70986-145">Depois de registrar o aplicativo pesquisa da Microsoft com o Azure DevOps, você pode concluir a etapa de configurações de conexão.</span><span class="sxs-lookup"><span data-stu-id="70986-145">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="70986-146">Insira o nome da sua organização, a ID do aplicativo e o segredo do cliente.</span><span class="sxs-lookup"><span data-stu-id="70986-146">Enter your organization name, App ID, and Client secret.</span></span>

![Configurações do Aplicativo de Conexão](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="70986-148">Configurar dados: selecionar projetos e campos</span><span class="sxs-lookup"><span data-stu-id="70986-148">Configure data: select projects and fields</span></span>

<span data-ttu-id="70986-149">Você pode escolher a conexão para indexar toda a organização ou projetos específicos.</span><span class="sxs-lookup"><span data-stu-id="70986-149">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="70986-150">Se você optar por indexar toda a organização, os itens em todos os projetos da organização serão indexados.</span><span class="sxs-lookup"><span data-stu-id="70986-150">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="70986-151">Novos projetos e itens serão indexados durante o próximo rastreamento depois que eles são criados.</span><span class="sxs-lookup"><span data-stu-id="70986-151">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="70986-152">Se você escolher projetos individuais, somente os itens de trabalho nesses projetos serão indexados.</span><span class="sxs-lookup"><span data-stu-id="70986-152">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurar dados](media/ADO_Configure_data.png)

<span data-ttu-id="70986-154">Em seguida, selecione quais campos você deseja que a conexão indexe e visualize dados nesses campos antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="70986-154">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Escolher propriedades](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="70986-156">Etapa 4: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="70986-156">Step 4: Manage search permissions</span></span>

<span data-ttu-id="70986-157">O conector do Azure DevOps dá suporte a permissões de pesquisa visíveis apenas para pessoas com acesso a essa fonte de  **dados** ou **a Todos.**</span><span class="sxs-lookup"><span data-stu-id="70986-157">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="70986-158">Se você escolher Apenas as pessoas com acesso a essa fonte de **dados,** os dados indexados aparecerão nos resultados da pesquisa para usuários que têm acesso a eles com base nas permissões para usuários ou grupos no nível do caminho organização, projeto ou área no Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="70986-158">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="70986-159">Se você escolher **Todos,** os dados indexados aparecerão nos resultados da pesquisa para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="70986-159">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="70986-160">Etapa 5: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="70986-160">Step 5: Assign property labels</span></span>

<span data-ttu-id="70986-161">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="70986-161">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="70986-162">Etapa 6: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="70986-162">Step 6: Manage schema</span></span>

<span data-ttu-id="70986-163">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="70986-163">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="70986-164">Etapa 7: Escolher configurações de atualização</span><span class="sxs-lookup"><span data-stu-id="70986-164">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="70986-165">O conector do Azure DevOps dá suporte a agendamentos de atualização para rastreamentos completos e incrementais.</span><span class="sxs-lookup"><span data-stu-id="70986-165">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="70986-166">O agendamento recomendado é de uma hora para um rastreamento incremental e um dia para um rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="70986-166">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="70986-167">Etapa 8: Analisar a conexão</span><span class="sxs-lookup"><span data-stu-id="70986-167">Step 8: Review connection</span></span>

<span data-ttu-id="70986-168">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="70986-168">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
