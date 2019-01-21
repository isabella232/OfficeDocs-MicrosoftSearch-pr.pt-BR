---
title: Segurança para pesquisa da Microsoft
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: Proteger seus dados da empresa e usuários, além de fornecer informações aos usuários autorizados, Microsoft Search
ms.openlocfilehash: 65cf1d49e32edbb8061a06f8da7ba644c2145e24
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378420"
---
# <a name="security-for-microsoft-search"></a>Segurança para pesquisa da Microsoft

Com a segurança em nível empresarial, Microsoft Search sempre mantém seus usuários e os dados protegidos.
  
## <a name="secure-by-default"></a>Seguro por padrão

Microsoft Search sempre garante que as solicitações são feitas via HTTPS. Esta salvaguarda garante que a conexão é criptografada ponta a ponta para aprimorar a segurança.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticação e autorização com o Active Directory do Windows Azure

A autenticação para o Microsoft Search é associada ao Active Directory do Azure. Quando os usuários do Microsoft Search ir para Bing, o Bing cabeçalho mostrará opções de entrar para uma conta da Microsoft como assim como um trabalho ou escola conta. Se o Bing não pode determinar se um usuário é um participante elegível, os usuários podem ir para a página de [Pesquisa da Microsoft explorar](https://www.bing.com/business/explore) , onde eles serão redirecionados automaticamente para a página de entrada da sua organização. 
  
Os usuários podem acessar o Microsoft Search apenas por meio de uma conta de trabalho ou da escola. Eles precisam entrar com as mesmas credenciais que usam para acessar os serviços do Office 365 such as SharePoint or Outlook. Uma conta da Microsoft pessoal não pode ser usada para entrar no Microsoft Search.
  
Os usuários não podem estar conectados ao Bing com uma conta da Microsoft e de uma conta de trabalho ou da escola ao mesmo tempo.
  
## <a name="single-sign-on"></a>Logon único

Se um usuário já estiver autenticado com sua conta de trabalho ou da escola em outro serviço, como o Outlook ou do SharePoint, eles vai ser automaticamente conectados ao Microsoft Search quando forem para Bing no mesmo navegador. Além disso, quando o usuário entra fora do Microsoft Search, eles serão automaticamente desconectados de outros serviços no mesmo navegador.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Se comunica com a nuvem confiáveis pelo navegador

Quando um usuário entrar com seus trabalhos ou conta escola, Bing baixará as bibliotecas necessárias do cliente para o navegador para permitir que os resultados do Microsoft Search. Em seguida, quando eles pesquisam, o código do navegador chama o Office 365 na nuvem para obter resultados de trabalho. Para fazer isso, o Microsoft Search usa uma API dedicada que é camada C (SOC2 tipo 1) compatíveis de acordo com o Office 365 [Estrutura de conformidade para padrões do setor e normas](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (download PDF). Isso significa que os resultados de trabalho e dados de trabalho nunca fluem através de sistemas não compatíveis do Bing. 
  
## <a name="permissions"></a>Permissões

Resultados de trabalho recuperados do cargas de trabalho do Office 365, como o SharePoint e o OneDrive for Business são segurança aparada na origem. Os usuários não podem ver recursos como documentos do Word ou apresentações do PowerPoint, eles não podem ver e acessar por meio do Office 365. Só podem ver seus próprios arquivos e os arquivos que foram compartilhados com eles pelo autor explícita ou implicitamente (por meio de uma associação de grupo, por exemplo) no SharePoint.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Protege a consultas do usuário contra a parte pública do Bing

Como as pesquisas relacionadas ao trabalho podem ser confidenciais, o Microsoft Search implementou um conjunto de medidas de confiança de como eles são manipulados pela web públicos resultados parte do Bing.
  
Se uma consulta de usuário contém um ou mais resultados de trabalho na resposta retornado, independentemente de medidas a seguir são executadas:
  
- Logging
    
  - Todos os logs de pesquisa referentes ao tráfego do Microsoft Search são identificados desprovisionamento e armazenados separadamente do tráfego do público, não - Microsoft Search. Eles estiver mantidos por 18 meses e o acesso é restrito apenas para depuração.
    
  - As consultas esses logs não são usados para o modelo ou treinar públicos recursos como sugestão automática ou relacionados a procura por web pública.
    
  - Acesso restrito é gerenciado através de vários mecanismos seguros, incluindo grupos de segurança e outras camadas dentro do sistema de engenharia.
    
- Pesquisar histórico
    
  - Quando assinado com uma conta de trabalho ou da escola, histórico de pesquisa do usuário não estará disponível em outros computadores ou dispositivos.
    
- Anunciando
    
  - Consultas de pesquisa empresarial nunca são compartilhadas com ou sugeridas para anunciantes.
    
  - Pesquisar logs de Ads referentes ao Microsoft Search são armazenados separadamente do tráfego público.
    
  - ADS nunca são direcionadas para um usuário com base em sua identidade comercial ou organização.
    
## <a name="gdpr"></a>RGPD

A [postagem de blog de 21 de maio de 2018,](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) da Microsoft reflete nosso compromisso de conformidade GDPR e como a Microsoft ajuda empresas e organizações com seus próprios obrigações de conformidade GDPR. Você pode encontrar detalhes adicionais no Microsoft [FAQ do Centro de confiança](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Consultas do Microsoft Search que operam contra os dados de cliente organizacionais clientes dentro do Online Services também atenderá os compromissos de processador descritos no artigo 28 medida refletido no [FAQ do Centro de confiança](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Com relação a consultas do Microsoft Search que vá para Bing público, a Microsoft é um controlador de dados e implementou medidas para identificar desprovisionamento as consultas, conforme descrito em GDPR.


