---
title: Configurar a Pesquisa da Microsoft
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar a Pesquisa da Microsoft pela primeira vez.
ms.openlocfilehash: d8b796e0ff61972f3e244c1a5af98319884769dc
ms.sourcegitcommit: ef1eb2bdf31dccd34f0fdc4aa7a0841ebd44f211
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2019
ms.locfileid: "39663056"
---
# <a name="set-up-microsoft-search"></a><span data-ttu-id="a8d6a-103">Configurar a Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8d6a-103">Set up Microsoft Search</span></span>

<span data-ttu-id="a8d6a-104">O Microsoft Search fornece uma interface amigável para ajudar os usuários a localizar informações como arquivos e documentos, sites internos e ferramentas de negócios, pessoas e grupos, locais e direções, conversas e respostas.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-104">Microsoft Search provides a user-friendly interface to help users find information like files and documents, internal sites and business tools, people and groups, locations and directions, conversations and answers.</span></span> <span data-ttu-id="a8d6a-105">Ele faz isso acessando com segurança todas as fontes de dados, incluindo emails, arquivos, arquivos do SharePoint, conteúdo do OneDrive e outros recursos compartilhados, bem como a Internet na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-105">It does this by securely accessing all data sources, including emails, files, SharePoint files, OneDrive content, and other shared resources as well as the internet in the user’s organization.</span></span>

<span data-ttu-id="a8d6a-106">Para saber mais sobre os recursos da Pesquisa da Microsoft, confira [Visão Geral da Pesquisa da Microsoft](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="a8d6a-106">To learn more about Microsoft Search features, see [Microsoft Search Overview](overview-microsoft-search.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="a8d6a-107">Introdução</span><span class="sxs-lookup"><span data-stu-id="a8d6a-107">Get Started</span></span>

<span data-ttu-id="a8d6a-108">A Pesquisa da Microsoft está ativada por padrão para todos os aplicativos da Microsoft compatíveis, como parte do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-108">Microsoft Search is turned on by default for all Microsoft apps that supports it, as a part of Microsoft 365.</span></span> <span data-ttu-id="a8d6a-109">Não há necessidade de configuração, mas você pode melhorar a experiência de pesquisa geral da Microsoft por meio de algumas tarefas administrativas básicas.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-109">There is no setup required, but you can improve the overall Microsoft Search experience through some basic administrative tasks.</span></span>

<span data-ttu-id="a8d6a-110">Você administra a Pesquisa da Microsoft a partir do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-110">You manage Microsoft Search from Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="a8d6a-111">No centro de administração do Microsoft 365, acesse **Configurações** > **Pesquisa da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-111">In Microsoft 365 admin center, go to **Settings** > **Microsoft Search**.</span></span>

<span data-ttu-id="a8d6a-112">**Observação:** se você NÃO estiver vendo a Pesquisa da Microsoft em **Configurações**, habilite a opção**Experimente a visualização** no canto superior direito de qualquer página do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-112">**Note:** If you are NOT seeing Microsoft Search under **Settings**, turn on the **Try the preview** switch in the right top corner of any admin center page.</span></span>

<span data-ttu-id="a8d6a-113">Como administrador, você deve considerar algumas coisas que podem tornar a experiência da Pesquisa da Microsoft eficiente e amigável em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-113">As an admin you should consider a few things that can make the Microsoft Search experience efficient and user friendly in your organization.</span></span>

## <a name="step-1-assign-search-admin-and-search-editor"></a><span data-ttu-id="a8d6a-114">Etapa 1: atribuir o administrador de pesquisa e o editor de pesquisa</span><span class="sxs-lookup"><span data-stu-id="a8d6a-114">Step 1: Assign Search admin and Search editor</span></span>

<span data-ttu-id="a8d6a-115">Na Pesquisa da Microsoft, você pode gerenciar as configurações de pesquisa e o conteúdo da sua organização, atribuindo estas duas funções aos usuários:</span><span class="sxs-lookup"><span data-stu-id="a8d6a-115">In Microsoft Search, you can manage your organization’s search settings and content by assigning these roles to users:</span></span>

1. <span data-ttu-id="a8d6a-116">**Administrador de Pesquisa**: Essa função pode criar e gerenciar conteúdo de resultados de pesquisa e definir configurações de consulta para melhorar os resultados de pesquisa na organização.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-116">**Search admin:** This role can create and manage search result content and define query settings for improved search results within the organization.</span></span> <span data-ttu-id="a8d6a-117">O administrador de Pesquisa gerencia a configuração da Pesquisa da Microsoft e pode realizar todas as tarefas de gerenciamento de conteúdo que um editor de Pesquisa pode.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-117">Search admin manages the Microsoft Search configuration and can perform all of the content-management tasks a Search editor can.</span></span>
2. <span data-ttu-id="a8d6a-118">**Editor de Pesquisa:** Cria, gerencia e exclui conteúdo para a Pesquisa da Microsoft no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-118">**Search editor:** Creates, manages, and deletes content for Microsoft Search in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a8d6a-119">Essa função pode criar e gerenciar conteúdos editoriais, como perguntas frequentes e respostas, locais importantes e localizações, sites e aplicativos pesquisados e usados com frequência.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-119">This role can create and manage editorial content, such as frequently asked questions and answers, important places and locations, frequently searched and used sites and apps.</span></span>

<span data-ttu-id="a8d6a-120">Atualmente, as funções de administrador e de editor de Pesquisa devem ser atribuídas por um administrador global. Para saber mais, confira [Atribuir funções de administrador](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="a8d6a-120">Currently, the Search admin and Search editor roles must be assigned by a global admin. For more information, see [Assign admin roles](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>

<span data-ttu-id="a8d6a-121">Os administradores de pesquisa influenciam diretamente a experiência de pesquisa dos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-121">Search administrators directly influence the search experience for end users.</span></span> <span data-ttu-id="a8d6a-122">Isso inclui escolher os tipos de resultados que você deseja destacar para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-122">This includes choosing the types of results you want to surface to your users.</span></span> <span data-ttu-id="a8d6a-123">Pode ser difícil para uma pessoa escolher e criar conteúdo autoritativo em muitos tópicos diferentes pelos quais os usuários pesquisam em uma organização.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-123">It may be difficult for one person to choose and create authoritative content on many different topics that users search for in an organization.</span></span> <span data-ttu-id="a8d6a-124">Recomendamos que você aproveite a experiência e o conhecimento dos especialistas no assunto (SME) e de outros usuários, adicionando-os como editores da Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-124">We recommend that you leverage the expertise and knowledge of subject matter experts (SME) and other users by adding them as Search editors.</span></span>

## <a name="step-2-create-answers"></a><span data-ttu-id="a8d6a-125">Etapa 2: criar respostas</span><span class="sxs-lookup"><span data-stu-id="a8d6a-125">Step 2: Create answers</span></span>

<span data-ttu-id="a8d6a-126">A Pesquisa da Microsoft fornece aos administradores ferramentas que eles podem usar para criar uma experiência de pesquisa robusta para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-126">Microsoft Search provides administrators with tools that they can use to build a robust search experience for their users.</span></span> <span data-ttu-id="a8d6a-127">No Microsoft Search, os administradores têm três conteúdos de pesquisa diferentes que podem ser criados para uma melhor experiência de pesquisa e aprimorar a "localização" do conteúdo:</span><span class="sxs-lookup"><span data-stu-id="a8d6a-127">In Microsoft Search, administrators have three different search contents that they can create for a better search experience and to improve the "findability" of content:</span></span>

<span data-ttu-id="a8d6a-128">Os indicadores são o tipo de resposta mais comumente usado.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-128">Bookmarks are the most commonly used answer type.</span></span> <span data-ttu-id="a8d6a-129">Eles promovem os melhores resultados possíveis para as consultas dos seus usuários na parte superior dos resultados da pesquisa e facilitam a localização dos usuários para localizar o que estão procurando.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-129">They promote the best possible results for your users’ queries to the top of the search results and make it easy for your users to find what they are looking for.</span></span>
<span data-ttu-id="a8d6a-130">Conteúdo informativo disponível para todos; por exemplo, informações sobre a empresa, ajuda para aplicativos do Windows e do Office, etc. Conteúdo que as pessoas na organização geralmente pesquisam em seus trabalhos diários.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-130">Informational content that is available for everyone; for example, information about the company, help for Windows and Office apps, etc. Content that people in the organization generally search for in their day-to-day work.</span></span> <span data-ttu-id="a8d6a-131">Pesquisas comuns relacionadas ao trabalho incluem benefícios de funcionários, relatórios de tempo e despesas, envio de pedidos de compras e obtenção de ajuda de serviços de TI.</span><span class="sxs-lookup"><span data-stu-id="a8d6a-131">Common work-related searches include employee benefits, time and expense reporting, submitting purchase orders, and getting help from IT services.</span></span>

<span data-ttu-id="a8d6a-132">Para criar e gerenciar respostas, consulte [Plan Your Content](plan-your-content.md).</span><span class="sxs-lookup"><span data-stu-id="a8d6a-132">For creating and managing answers, see [Plan your content](plan-your-content.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8d6a-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a8d6a-133">Next steps</span></span>

<span data-ttu-id="a8d6a-134">Se quiser saber mais sobre como os usuários usarão o Microsoft Search, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="a8d6a-134">If you'd like to learn more about how your users will use Microsoft Search, see the following articles:</span></span>

- [<span data-ttu-id="a8d6a-135">Encontre o que você precisa com a Pesquisa da Microsoft no Office</span><span class="sxs-lookup"><span data-stu-id="a8d6a-135">Find what you need with Microsoft Search in Office</span></span>](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446)
- [<span data-ttu-id="a8d6a-136">Centro de Treinamento do Office 365</span><span class="sxs-lookup"><span data-stu-id="a8d6a-136">Office 365 Training Center</span></span>](https://support.office.com/office-training-center)
- [<span data-ttu-id="a8d6a-137">Centro de pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8d6a-137">Microsoft Search Center</span></span>](https://support.office.com/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc)
