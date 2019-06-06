---
title: Segurança da Pesquisa da Microsoft
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
ROBOTS: NOINDEX
description: Proteja seus dados corporativos e dos usuários, além de fornecer informações aos usuários autorizados com a Pesquisa da Microsoft
ms.openlocfilehash: 4e5e23e5e1389c95d28ede66e06707f9856a3770
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727930"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="f56a3-103">Segurança da Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f56a3-103">Security for Microsoft Search</span></span>

<span data-ttu-id="f56a3-104">Com a segurança de nível empresarial, a Pesquisa da Microsoft sempre mantém seus usuários e dados protegidos.</span><span class="sxs-lookup"><span data-stu-id="f56a3-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>


## <a name="secure-by-default"></a><span data-ttu-id="f56a3-105">Segurança por padrão</span><span class="sxs-lookup"><span data-stu-id="f56a3-105">Secure by default</span></span>

<span data-ttu-id="f56a3-p101">A Pesquisa da Microsoft garante que as solicitações sempre sejam feitas via HTTPS. Essa proteção garante que a conexão seja criptografada de ponta a ponta para aumentar a segurança.</span><span class="sxs-lookup"><span data-stu-id="f56a3-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="f56a3-108">Autenticação e autorização com o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f56a3-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="f56a3-p102">A autenticação da Pesquisa da Microsoft está vinculada ao Azure Active Directory. Quando os usuários da Pesquisa da Microsoft acessam o Bing, o cabeçalho do Bing exibe as opções de entrada para uma conta Microsoft, bem como uma conta corporativa ou de estudante. Se o Bing não conseguir determinar se um usuário é um participante qualificado, os usuários podem acessar a página [Explorar Pesquisa da Microsoft](https://www.bing.com/business/explore), na qual serão redirecionados automaticamente para a página de entrada da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f56a3-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="f56a3-p103">Os usuários podem acessar a Pesquisa da Microsoft com uma conta corporativa ou de estudante. Eles precisam entrar com as mesmas credenciais que usam para acessar os serviços do Office 365, como o SharePoint ou o Outlook. Não é possível usar uma conta Microsoft pessoal para entrar na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f56a3-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="f56a3-115">Os usuários não podem entrar no Bing com uma conta Microsoft e uma conta corporativa ou de estudante ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f56a3-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="f56a3-116">Logon único</span><span class="sxs-lookup"><span data-stu-id="f56a3-116">Single sign-on</span></span>

<span data-ttu-id="f56a3-p104">Se um usuário já estiver autenticado com a conta corporativa ou de estudante em outro serviço, como o Outlook ou o SharePoint, ele entrará automaticamente na Pesquisa da Microsoft ao acessar o Bing no mesmo navegador. Além disso, quando o usuário sair da Pesquisa da Microsoft, ele sairá automaticamente dos outros serviços no mesmo navegador.</span><span class="sxs-lookup"><span data-stu-id="f56a3-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="f56a3-119">Comunicação com a nuvem de forma confiável no navegador</span><span class="sxs-lookup"><span data-stu-id="f56a3-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="f56a3-p105">Quando um usuário entra com sua conta corporativa ou de estudante, o Bing baixa as bibliotecas de cliente necessárias para o navegador para permitir resultados da Pesquisa da Microsoft. Em seguida, ao pesquisar, o código no navegador chama a nuvem do Office 365 para obter resultados de trabalho. Para fazer isso, a Pesquisa da Microsoft usa uma API dedicada compatível com a camada C (SOC2 Tipo 1) de acordo com a [Estrutura de conformidade para padrões e regulamentações do setor](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) do Office 365 (baixar o PDF). Isso significa que os resultados e dados do trabalho nunca fluem por meio de sistemas não compatíveis com o Bing.</span><span class="sxs-lookup"><span data-stu-id="f56a3-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="f56a3-124">Permissões</span><span class="sxs-lookup"><span data-stu-id="f56a3-124">Permissions</span></span>

<span data-ttu-id="f56a3-p106">Os resultados dos trabalhos recuperados das cargas de trabalho do Office 365, como o SharePoint e OneDrive for Business, têm a segurança realizada na fonte. Os usuários não podem ver os recursos, tais como documentos do Word ou apresentações do PowerPoint, que não possam ser vistos e acessados por meio do Office 365. Eles só podem visualizar seus próprios arquivos e aqueles compartilhados explícita ou implicitamente com eles pelo autor (por exemplo, por meio da associação de grupo) no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f56a3-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="f56a3-128">Proteção das consultas de usuários da parte pública do Bing</span><span class="sxs-lookup"><span data-stu-id="f56a3-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="f56a3-129">Como as pesquisas relacionadas ao trabalho podem ser confidenciais, a Pesquisa da Microsoft implementou um conjunto de medidas de confiança sobre como elas são manipuladas pela parte de resultados web públicos da Bing.</span><span class="sxs-lookup"><span data-stu-id="f56a3-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="f56a3-130">Independentemente da consulta do usuário conter um ou mais resultados de trabalho na resposta retornada, as seguintes medidas são executadas:</span><span class="sxs-lookup"><span data-stu-id="f56a3-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="f56a3-131">Registro em Log</span><span class="sxs-lookup"><span data-stu-id="f56a3-131">Logging</span></span>
    
  - <span data-ttu-id="f56a3-p107">Todos os logs de pesquisa referentes ao tráfego da Pesquisa da Microsoft têm as identidades removidas e são armazenados separadamente do tráfego público que não for da Pesquisa da Microsoft. Eles são mantidos por 18 meses e o acesso é restrito para fins de depuração de bugs.</span><span class="sxs-lookup"><span data-stu-id="f56a3-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="f56a3-134">As consultas nesses logs não são usadas para modelar ou treinar recursos públicos, como sugestão automática ou pesquisas relacionadas na web pública.</span><span class="sxs-lookup"><span data-stu-id="f56a3-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="f56a3-135">O acesso restrito é gerenciado por vários mecanismos seguros, incluindo os grupos de segurança e outras camadas no sistema de engenharia.</span><span class="sxs-lookup"><span data-stu-id="f56a3-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="f56a3-136">Pesquisar o histórico</span><span class="sxs-lookup"><span data-stu-id="f56a3-136">Search history</span></span>
    
  - <span data-ttu-id="f56a3-137">Ao fazer login com uma conta corporativa ou de estudante, o histórico de pesquisa de um usuário não estará disponível em outros computadores ou dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f56a3-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="f56a3-138">Publicidade</span><span class="sxs-lookup"><span data-stu-id="f56a3-138">Advertising</span></span>
    
  - <span data-ttu-id="f56a3-139">As consultas de pesquisa corporativa nunca são compartilhadas com ou sugeridas para anunciantes.</span><span class="sxs-lookup"><span data-stu-id="f56a3-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="f56a3-140">Os logs de pesquisa de anúncios referentes à Pesquisa da Microsoft são armazenados separadamente do tráfego público.</span><span class="sxs-lookup"><span data-stu-id="f56a3-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="f56a3-141">Os anúncios nunca são direcionados para um usuário com base na sua identidade de trabalho ou da organização.</span><span class="sxs-lookup"><span data-stu-id="f56a3-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="f56a3-142">RGPD</span><span class="sxs-lookup"><span data-stu-id="f56a3-142">GDPR</span></span>

<span data-ttu-id="f56a3-p108">Em [21 de maio de 2018, a postagem do blog](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) da Microsoft reflete o nosso compromisso com a conformidade com o RGDP e como a Microsoft ajuda empresas e organizações a cumprir suas próprias obrigações de conformidade com o RGDP. Você pode encontrar detalhes adicionais nas [Perguntas Frequentes da Central de Confiabilidade](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs) da Microsoft. As consultas da Pesquisa da Microsoft que operam com base em dados de clientes organizacionais dentro dos Serviços Online também atenderão às obrigações do processador descritas no artigo 28, bem como refletidos nas [Perguntas Frequentes da Central de Confiabilidade](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Com relação às consultas da Pesquisa da Microsoft que forem feitas no Bing público, a Microsoft é uma controladora de dados e implementou medidas para remover a identificação das consultas, como descrito no RGPD.</span><span class="sxs-lookup"><span data-stu-id="f56a3-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


