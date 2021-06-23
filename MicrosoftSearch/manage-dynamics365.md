---
title: Pesquisa de federação do Dynamics 365 (visualização)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Gerenciar como o conteúdo do Dynamics 365 aparece nos resultados da pesquisa
ms.openlocfilehash: 5f642bcb026358e57258e5e736fc263616fc4b05
ms.sourcegitcommit: f07a2e578b6c9ed5a1a3b22266cca371782870a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53067934"
---
# <a name="dynamics-365-federation-search-preview"></a><span data-ttu-id="e4584-103">Pesquisa de federação do Dynamics 365 (visualização)</span><span class="sxs-lookup"><span data-stu-id="e4584-103">Dynamics 365 federation search (preview)</span></span>

## <a name="microsoft-search-federation-and-connectors"></a><span data-ttu-id="e4584-104">Pesquisa da Microsoft Federação e conectores</span><span class="sxs-lookup"><span data-stu-id="e4584-104">Microsoft Search Federation and connectors</span></span>

<span data-ttu-id="e4584-105">Para ajudar a Pesquisa da Microsoft mais útil, apresentamos Pesquisa da Microsoft Federação.</span><span class="sxs-lookup"><span data-stu-id="e4584-105">To help make Microsoft Search more useful, we're introducing Microsoft Search Federation.</span></span> <span data-ttu-id="e4584-106">Com a pesquisa federada, as organizações podem tornar os dados nesses cenários acessíveis em Pesquisa da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e4584-106">With federated search, organizations can make data in these scenarios accessible in Microsoft Search:</span></span>

* <span data-ttu-id="e4584-107">Dados em sistemas que estão sujeitos a requisitos estritos de conformidade</span><span class="sxs-lookup"><span data-stu-id="e4584-107">Data in systems that are subject to strict compliance requirements</span></span>
* <span data-ttu-id="e4584-108">Dados que não podem deixar limites do sistema</span><span class="sxs-lookup"><span data-stu-id="e4584-108">Data that can't leave system boundaries</span></span>
* <span data-ttu-id="e4584-109">Dados confidenciais armazenados no local que sua organização não deseja indexar na nuvem</span><span class="sxs-lookup"><span data-stu-id="e4584-109">Sensitive data stored on-prem that your organization doesn’t want indexed on the cloud</span></span>

<span data-ttu-id="e4584-110">Os dados acessados por meio de uma conexão de pesquisa federada não são indexados Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4584-110">Data accessed through a federated search connection isn't indexed in Microsoft Search.</span></span> <span data-ttu-id="e4584-111">Além disso, usando conectores integrados da Microsoft, é fácil configurar conexões de pesquisa federadas.</span><span class="sxs-lookup"><span data-stu-id="e4584-111">Also, using built-in connectors from Microsoft, it's easy to set up federated search connections.</span></span> <span data-ttu-id="e4584-112">Nosso conector do Dynamics 365 está atualmente em visualização.</span><span class="sxs-lookup"><span data-stu-id="e4584-112">Our Dynamics 365 connector is currently in preview.</span></span> <span data-ttu-id="e4584-113">Se você estiver interessado em ingressar na visualização, nos avise [em](https://aka.ms/D365FederationSearchPreview)aka.ms/D365FederationSearchPreview .</span><span class="sxs-lookup"><span data-stu-id="e4584-113">If you're interested in joining the preview, let us know at [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span></span>

## <a name="dynamics-365-federation-connector"></a><span data-ttu-id="e4584-114">Conector de federação do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e4584-114">Dynamics 365 federation connector</span></span>

<span data-ttu-id="e4584-115">O Microsoft Dynamics 365 é uma linha de aplicativos corporativos inteligentes projetados para planejamento de recursos corporativos e gerenciamento de relacionamento com o cliente.</span><span class="sxs-lookup"><span data-stu-id="e4584-115">Microsoft Dynamics 365 is a line of intelligent business applications designed for enterprise resource planning and customer relationship management.</span></span> <span data-ttu-id="e4584-116">Com a federação do Dynamics 365, o Pesquisa da Microsoft oferece uma experiência de pesquisa perfeita, permitindo que os usuários encontrem facilmente os dados de clientes e negócios mais relevantes armazenados no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e4584-116">With Dynamics 365 federation, Microsoft Search provides a seamless search experience, enabling users to easily find the most relevant customer and business data stored in Dynamics 365.</span></span> <span data-ttu-id="e4584-117">O conector de federação do Dynamics 365 oferece alguns benefícios importantes:</span><span class="sxs-lookup"><span data-stu-id="e4584-117">The Dynamics 365 federation connector provides some key benefits:</span></span>

* <span data-ttu-id="e4584-118">**Fácil de administrar:** Processo simplificado para configurar e manter a conexão de pesquisa com uma instância do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e4584-118">**Easy to administer:** Streamlined process to configure and maintain the search connection to a Dynamics 365 instance.</span></span>
* <span data-ttu-id="e4584-119">**Fácil de usar:** Os usuários podem encontrar facilmente e rapidamente informações importantes armazenadas no Dynamics 365, incluindo contas, contatos, oportunidades abertas e muito mais.</span><span class="sxs-lookup"><span data-stu-id="e4584-119">**Easy to use:** Users can easily and quickly find key information stored in Dynamics 365, including accounts, contacts, open opportunities, and more.</span></span>
* <span data-ttu-id="e4584-120">**Conteúdo mais rico:** Para tornar os resultados de pesquisa do Dynamics 365 mais úteis, eles incluem informações importantes, como contatos e detalhes da conta.</span><span class="sxs-lookup"><span data-stu-id="e4584-120">**Richer content:** To make Dynamics 365 search results more useful, they include key information like leads, contacts, and account details.</span></span>
* <span data-ttu-id="e4584-121">**Proteção de dados integrado:** Os resultados do Dynamics 365 só serão exibidos para usuários que tenham acesso à instância conectada.</span><span class="sxs-lookup"><span data-stu-id="e4584-121">**Built-in data protection:** Dynamics 365 results will only appear for users that have access to the connected instance.</span></span>
* <span data-ttu-id="e4584-122">**Experiência de pesquisa unificada:** Para manter uma experiência coesiva, os resultados do Dynamics 365 são consistentes em todos os pontos de entrada da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e4584-122">**Unified search experience:** To maintain a cohesive experience, Dynamics 365 results are consistent across all search entry points.</span></span> <span data-ttu-id="e4584-123">Onde quer que você pesquise, você obterá os mesmos resultados com a mesma aparência.</span><span class="sxs-lookup"><span data-stu-id="e4584-123">Wherever you search, you'll get the same results with the same look and feel.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="e4584-124">O que os usuários experimentam</span><span class="sxs-lookup"><span data-stu-id="e4584-124">What users experience</span></span>

<span data-ttu-id="e4584-125">As respostas do Dynamics 365 aparecem nos resultados da pesquisa em todas as Pesquisa da Microsoft, incluindo SharePoint Online, Bing e Office.</span><span class="sxs-lookup"><span data-stu-id="e4584-125">Dynamics 365 answers appear in search results across all Microsoft Search canvases, including SharePoint Online, Bing, and Office.</span></span>

:::image type="content" alt-text="Captura de tela das respostas do Dynamics 365 em SharePoint, Bing e Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

<span data-ttu-id="e4584-127">Na resposta, é fácil ver mais resultados de pesquisa do Dynamics 365 usando o link mais resultados do **Dynamics 365.**</span><span class="sxs-lookup"><span data-stu-id="e4584-127">From the answer, it's easy to see more Dynamics 365 search results by using the **More Dynamics 365 results** link.</span></span> <span data-ttu-id="e4584-128">Ele leva os usuários para uma página de resultados do Dynamics 365 dedicada com mais resultados relevantes para sua consulta.</span><span class="sxs-lookup"><span data-stu-id="e4584-128">It takes users to a dedicated Dynamics 365 results page with more results relevant to their query.</span></span>

:::image type="content" alt-text="Captura de tela do Dynamics 365 vertical e resultados em SharePoint, Bing e Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

<span data-ttu-id="e4584-130">Clicar ou tocar em qualquer resultado abre o Dynamics 365 e mostra as informações detalhadas.</span><span class="sxs-lookup"><span data-stu-id="e4584-130">Clicking or tapping any result opens Dynamics 365 and shows the detailed information.</span></span>

:::image type="content" alt-text="Captura de tela da página de detalhes no Dynamics 365" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

<span data-ttu-id="e4584-132">Não importa onde seus usuários iniciem a pesquisa, sua experiência será consistente e permitirá que eles encontrem rapidamente os resultados mais relevantes do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e4584-132">No matter where your users start their search their experience will be consistent and enable them to quickly find the most relevant Dynamics 365 results.</span></span> <span data-ttu-id="e4584-133">Confira nosso vídeo do Microsoft Build 2021 para uma demonstração.</span><span class="sxs-lookup"><span data-stu-id="e4584-133">Check out our Microsoft Build 2021 video for a demonstration.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4P83t]

## <a name="supported-query-patterns"></a><span data-ttu-id="e4584-134">Padrões de consulta com suporte</span><span class="sxs-lookup"><span data-stu-id="e4584-134">Supported query patterns</span></span>

<span data-ttu-id="e4584-135">Tanto a linguagem natural quanto as consultas de nome do produto são suportadas ao usar Pesquisa da Microsoft para encontrar resultados do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e4584-135">Both natural language and product name queries are supported when using Microsoft Search to find Dynamics 365 results.</span></span> <span data-ttu-id="e4584-136">Além disso, as consultas do Dynamics 365 não são sensíveis a casos.</span><span class="sxs-lookup"><span data-stu-id="e4584-136">Also, Dynamics 365 queries aren't case sensitive.</span></span> <span data-ttu-id="e4584-137">Use padrões de idioma natural para localizar contatos, conta e oportunidades -- pelo nome do cliente ou local -- e outras consultas usadas com frequência.</span><span class="sxs-lookup"><span data-stu-id="e4584-137">Use natural language patterns to find contact, account, and opportunities--by customer name or location--and other frequently used queries.</span></span> <span data-ttu-id="e4584-138">Veja alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="e4584-138">Here are a few examples:</span></span>

* <span data-ttu-id="e4584-139">Who é o contato da Contoso</span><span class="sxs-lookup"><span data-stu-id="e4584-139">Who is the contact for Contoso</span></span>
* <span data-ttu-id="e4584-140">Oportunidades abertas para Contoso</span><span class="sxs-lookup"><span data-stu-id="e4584-140">Open opportunities for Contoso</span></span>
* <span data-ttu-id="e4584-141">Quais são as oportunidades abertas em Seattle</span><span class="sxs-lookup"><span data-stu-id="e4584-141">What are open opportunities in Seattle</span></span>
* <span data-ttu-id="e4584-142">Quais são as contas em Seattle</span><span class="sxs-lookup"><span data-stu-id="e4584-142">What are the accounts in Seattle</span></span>
* <span data-ttu-id="e4584-143">Quais são os contatos em Seattle</span><span class="sxs-lookup"><span data-stu-id="e4584-143">What are the contacts in Seattle</span></span>
* <span data-ttu-id="e4584-144">Quais são os meus leads que fecham este mês</span><span class="sxs-lookup"><span data-stu-id="e4584-144">What are my leads closing this month</span></span>
* <span data-ttu-id="e4584-145">Chamada telefônica de alta prioridade</span><span class="sxs-lookup"><span data-stu-id="e4584-145">High priority phone call</span></span>
* <span data-ttu-id="e4584-146">Contatar emails ausentes</span><span class="sxs-lookup"><span data-stu-id="e4584-146">Contact missing emails</span></span>

<span data-ttu-id="e4584-147">Os padrões de nome do produto suportam um intervalo de aplicativos do Dynamics 365 e disparam os resultados do Dynamics 365, independentemente de onde aparecem em uma consulta:</span><span class="sxs-lookup"><span data-stu-id="e4584-147">Product name patterns support a range of Dynamics 365 applications and will trigger Dynamics 365 results regardless of where they appear in a query:</span></span>

* <span data-ttu-id="e4584-148">D365</span><span class="sxs-lookup"><span data-stu-id="e4584-148">D365</span></span>
* <span data-ttu-id="e4584-149">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e4584-149">Dynamics 365</span></span>
* <span data-ttu-id="e4584-150">Dynamics365</span><span class="sxs-lookup"><span data-stu-id="e4584-150">Dynamics365</span></span>
* <span data-ttu-id="e4584-151">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="e4584-151">Dynamics CRM</span></span>
* <span data-ttu-id="e4584-152">Dynamics Sales</span><span class="sxs-lookup"><span data-stu-id="e4584-152">Dynamics Sales</span></span>
* <span data-ttu-id="e4584-153">Dynamics Customer Service</span><span class="sxs-lookup"><span data-stu-id="e4584-153">Dynamics Customer Service</span></span>
* <span data-ttu-id="e4584-154">Serviço Dynamics</span><span class="sxs-lookup"><span data-stu-id="e4584-154">Dynamics Service</span></span>
* <span data-ttu-id="e4584-155">Dynamics Field Service</span><span class="sxs-lookup"><span data-stu-id="e4584-155">Dynamics Field Service</span></span>

## <a name="configure-the-dynamics-365-connector"></a><span data-ttu-id="e4584-156">Configurar o conector do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e4584-156">Configure the Dynamics 365 connector</span></span>

<span data-ttu-id="e4584-157">Com essa configuração simples, você pode habilitar a experiência de pesquisa de federação do Dynamics 365 para pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e4584-157">With this simple configuration, you can enable the Dynamics 365 federation search experience for people in your organization.</span></span>

1. <span data-ttu-id="e4584-158">No [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [Fontes de dados](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span><span class="sxs-lookup"><span data-stu-id="e4584-158">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [Data sources](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span></span>

2. <span data-ttu-id="e4584-159">Na seção Aplicativos e serviços da Microsoft, em Microsoft Dynamics 365, selecione **Gerenciar** para abrir o painel do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e4584-159">In the Microsoft apps and services section, under Microsoft Dynamics 365, select **Manage** to open the Microsoft Dynamics 365 panel.</span></span>

3. <span data-ttu-id="e4584-160">Habilita o conector para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e4584-160">Enable the connector for your organization.</span></span>

4. <span data-ttu-id="e4584-161">Na lista **Pontos de** Extremidade, selecione seu ambiente do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e4584-161">In the **Endpoints** list, select your Dynamics 365 environment.</span></span>

5. <span data-ttu-id="e4584-162">Na **ID da Conexão,** insira uma ID exclusiva para essa conexão.</span><span class="sxs-lookup"><span data-stu-id="e4584-162">In the **Connection ID**, enter a unique ID for this connection.</span></span>

6. <span data-ttu-id="e4584-163">Revise e selecione a caixa de seleção consentimento.</span><span class="sxs-lookup"><span data-stu-id="e4584-163">Review and select the consent check box.</span></span>

7. <span data-ttu-id="e4584-164">Selecione **Salvar** para concluir a configuração da conexão.</span><span class="sxs-lookup"><span data-stu-id="e4584-164">Select **Save** to finish the connection setup.</span></span>

:::image type="content" alt-text="Captura de tela do painel de configuração do Dynamics 365 no Centro de administração do Microsoft 365" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

<span data-ttu-id="e4584-166">Quando a instalação for concluída, as respostas e verticais do Dynamics 365 aparecerão somente para usuários com uma licença válida do Dynamics 365 e acesso ao ambiente conectado do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e4584-166">When the setup is complete, Dynamics 365 answers and vertical will only appear for users with a valid Dynamics 365 license and access to the connected Dynamics 365 environment.</span></span> <span data-ttu-id="e4584-167">A qualquer momento, você pode retornar a essas configurações e alterar o ambiente do ponto de extremidade de conexão ou desativar a conexão.</span><span class="sxs-lookup"><span data-stu-id="e4584-167">At any time, you can return to these settings and change the connection endpoint environment or deactivate the connection.</span></span>
