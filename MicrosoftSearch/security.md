---
title: Segurança para pesquisa da Microsoft
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: Proteger seus dados da empresa e usuários, além de fornecer informações aos usuários autorizados, Microsoft Search
ms.openlocfilehash: 5f59e0e2969ef829d7c14b07ecb47d645cc63013
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612518"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="bbee3-103">Segurança para pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="bbee3-103">Security for Microsoft Search</span></span>

<span data-ttu-id="bbee3-104">Com a segurança em nível empresarial, Microsoft Search sempre mantém seus usuários e os dados protegidos.</span><span class="sxs-lookup"><span data-stu-id="bbee3-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>
  
## <a name="secure-by-default"></a><span data-ttu-id="bbee3-105">Seguro por padrão</span><span class="sxs-lookup"><span data-stu-id="bbee3-105">Secure by default</span></span>

<span data-ttu-id="bbee3-p101">Microsoft Search sempre garante que as solicitações são feitas via HTTPS. Esta salvaguarda garante que a conexão é criptografada ponta a ponta para aprimorar a segurança.</span><span class="sxs-lookup"><span data-stu-id="bbee3-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="bbee3-108">Autenticação e autorização com o Active Directory do Windows Azure</span><span class="sxs-lookup"><span data-stu-id="bbee3-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="bbee3-p102">A autenticação para o Microsoft Search é associada ao Active Directory do Azure. Quando os usuários do Microsoft Search ir para Bing, o Bing cabeçalho mostrará opções de entrar para uma conta da Microsoft como assim como um trabalho ou escola conta. Se o Bing não pode determinar se um usuário é um participante elegível, os usuários podem ir para a página de [Pesquisa da Microsoft explorar](https://www.bing.com/business/explore) , onde eles serão redirecionados automaticamente para a página de entrada da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bbee3-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="bbee3-p103">Os usuários podem acessar o Microsoft Search apenas por meio de uma conta de trabalho ou da escola. Eles precisam entrar com as mesmas credenciais que usam para acessar os serviços do Office 365 such as SharePoint or Outlook. Uma conta da Microsoft pessoal não pode ser usada para entrar no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="bbee3-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="bbee3-115">Os usuários não podem estar conectados ao Bing com uma conta da Microsoft e de uma conta de trabalho ou da escola ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="bbee3-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="bbee3-116">Logon único</span><span class="sxs-lookup"><span data-stu-id="bbee3-116">Single sign-on</span></span>

<span data-ttu-id="bbee3-p104">Se um usuário já estiver autenticado com sua conta de trabalho ou da escola em outro serviço, como o Outlook ou do SharePoint, eles vai ser automaticamente conectados ao Microsoft Search quando forem para Bing no mesmo navegador. Além disso, quando o usuário entra fora do Microsoft Search, eles serão automaticamente desconectados de outros serviços no mesmo navegador.</span><span class="sxs-lookup"><span data-stu-id="bbee3-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="bbee3-119">Se comunica com a nuvem confiáveis pelo navegador</span><span class="sxs-lookup"><span data-stu-id="bbee3-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="bbee3-p105">Quando um usuário entrar com seus trabalhos ou conta escola, Bing baixará as bibliotecas necessárias do cliente para o navegador para permitir que os resultados do Microsoft Search. Em seguida, quando eles pesquisam, o código do navegador chama o Office 365 na nuvem para obter resultados de trabalho. Para fazer isso, o Microsoft Search usa uma API dedicada que é camada C (SOC2 tipo 1) compatíveis de acordo com o Office 365 [Estrutura de conformidade para padrões do setor e normas](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (download PDF). Isso significa que os resultados de trabalho e dados de trabalho nunca fluem através de sistemas não compatíveis do Bing.</span><span class="sxs-lookup"><span data-stu-id="bbee3-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="bbee3-124">Permissões</span><span class="sxs-lookup"><span data-stu-id="bbee3-124">Permissions</span></span>

<span data-ttu-id="bbee3-p106">Resultados de trabalho recuperados do cargas de trabalho do Office 365, como o SharePoint e o OneDrive for Business são segurança aparada na origem. Os usuários não podem ver recursos como documentos do Word ou apresentações do PowerPoint, eles não podem ver e acessar por meio do Office 365. Só podem ver seus próprios arquivos e os arquivos que foram compartilhados com eles pelo autor explícita ou implicitamente (por meio de uma associação de grupo, por exemplo) no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bbee3-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="bbee3-128">Protege a consultas do usuário contra a parte pública do Bing</span><span class="sxs-lookup"><span data-stu-id="bbee3-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="bbee3-129">Como as pesquisas relacionadas ao trabalho podem ser confidenciais, o Microsoft Search implementou um conjunto de medidas de confiança de como eles são manipulados pela web públicos resultados parte do Bing.</span><span class="sxs-lookup"><span data-stu-id="bbee3-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="bbee3-130">Se uma consulta de usuário contém um ou mais resultados de trabalho na resposta retornado, independentemente de medidas a seguir são executadas:</span><span class="sxs-lookup"><span data-stu-id="bbee3-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="bbee3-131">Logging</span><span class="sxs-lookup"><span data-stu-id="bbee3-131">Logging</span></span>
    
  - <span data-ttu-id="bbee3-p107">Todos os logs de pesquisa referentes ao tráfego do Microsoft Search são identificados desprovisionamento e armazenados separadamente do tráfego do público, não - Microsoft Search. Eles estiver mantidos por 18 meses e o acesso é restrito apenas para depuração.</span><span class="sxs-lookup"><span data-stu-id="bbee3-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="bbee3-134">As consultas esses logs não são usados para o modelo ou treinar públicos recursos como sugestão automática ou relacionados a procura por web pública.</span><span class="sxs-lookup"><span data-stu-id="bbee3-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="bbee3-135">Acesso restrito é gerenciado através de vários mecanismos seguros, incluindo grupos de segurança e outras camadas dentro do sistema de engenharia.</span><span class="sxs-lookup"><span data-stu-id="bbee3-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="bbee3-136">Pesquisar histórico</span><span class="sxs-lookup"><span data-stu-id="bbee3-136">Search history</span></span>
    
  - <span data-ttu-id="bbee3-137">Quando assinado com uma conta de trabalho ou da escola, histórico de pesquisa do usuário não estará disponível em outros computadores ou dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bbee3-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="bbee3-138">Anunciando</span><span class="sxs-lookup"><span data-stu-id="bbee3-138">Advertising</span></span>
    
  - <span data-ttu-id="bbee3-139">Consultas de pesquisa empresarial nunca são compartilhadas com ou sugeridas para anunciantes.</span><span class="sxs-lookup"><span data-stu-id="bbee3-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="bbee3-140">Pesquisar logs de Ads referentes ao Microsoft Search são armazenados separadamente do tráfego público.</span><span class="sxs-lookup"><span data-stu-id="bbee3-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="bbee3-141">ADS nunca são direcionadas para um usuário com base em sua identidade comercial ou organização.</span><span class="sxs-lookup"><span data-stu-id="bbee3-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="bbee3-142">RGPD</span><span class="sxs-lookup"><span data-stu-id="bbee3-142">GDPR</span></span>

<span data-ttu-id="bbee3-p108">A [postagem de blog de 21 de maio de 2018,](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) da Microsoft reflete nosso compromisso de conformidade GDPR e como a Microsoft ajuda empresas e organizações com seus próprios obrigações de conformidade GDPR. Você pode encontrar detalhes adicionais no Microsoft [FAQ do Centro de confiança](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Consultas do Microsoft Search que operam contra os dados de cliente organizacionais clientes dentro do Online Services também atenderá os compromissos de processador descritos no artigo 28 medida refletido no [FAQ do Centro de confiança](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Com relação a consultas do Microsoft Search que vá para Bing público, a Microsoft é um controlador de dados e implementou medidas para identificar desprovisionamento as consultas, conforme descrito em GDPR.</span><span class="sxs-lookup"><span data-stu-id="bbee3-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


