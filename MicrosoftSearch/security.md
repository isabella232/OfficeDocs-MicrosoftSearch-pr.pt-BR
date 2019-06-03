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
ms.openlocfilehash: c8444c5c265e109d379fdfffbb033c703040a74c
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591193"
---
# <a name="security-for-microsoft-search"></a>Segurança da Pesquisa da Microsoft

Com a segurança de nível empresarial, a Pesquisa da Microsoft sempre mantém seus usuários e dados protegidos.

> [!IMPORTANT]
> Este artigo se aplica à Pesquisa do Microsoft no portal de administração do Bing. Estamos movendo o portal para o centro de administração do Microsoft 365 e, posteriormente, ele será removido. Recomendamos que você use o centro de administração do Microsoft 365 para começar. [Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)
  
## <a name="secure-by-default"></a>Segurança por padrão

A Pesquisa da Microsoft garante que as solicitações sempre sejam feitas via HTTPS. Essa proteção garante que a conexão seja criptografada de ponta a ponta para aumentar a segurança.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticação e autorização com o Azure Active Directory

A autenticação da Pesquisa da Microsoft está vinculada ao Azure Active Directory. Quando os usuários da Pesquisa da Microsoft acessam o Bing, o cabeçalho do Bing exibe as opções de entrada para uma conta Microsoft, bem como uma conta corporativa ou de estudante. Se o Bing não conseguir determinar se um usuário é um participante qualificado, os usuários podem acessar a página [Explorar Pesquisa da Microsoft](https://www.bing.com/business/explore), na qual serão redirecionados automaticamente para a página de entrada da sua organização. 
  
Os usuários podem acessar a Pesquisa da Microsoft com uma conta corporativa ou de estudante. Eles precisam entrar com as mesmas credenciais que usam para acessar os serviços do Office 365, como o SharePoint ou o Outlook. Não é possível usar uma conta Microsoft pessoal para entrar na Pesquisa da Microsoft.
  
Os usuários não podem entrar no Bing com uma conta Microsoft e uma conta corporativa ou de estudante ao mesmo tempo.
  
## <a name="single-sign-on"></a>Logon único

Se um usuário já estiver autenticado com a conta corporativa ou de estudante em outro serviço, como o Outlook ou o SharePoint, ele entrará automaticamente na Pesquisa da Microsoft ao acessar o Bing no mesmo navegador. Além disso, quando o usuário sair da Pesquisa da Microsoft, ele sairá automaticamente dos outros serviços no mesmo navegador.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Comunicação com a nuvem de forma confiável no navegador

Quando um usuário entra com sua conta corporativa ou de estudante, o Bing baixa as bibliotecas de cliente necessárias para o navegador para permitir resultados da Pesquisa da Microsoft. Em seguida, ao pesquisar, o código no navegador chama a nuvem do Office 365 para obter resultados de trabalho. Para fazer isso, a Pesquisa da Microsoft usa uma API dedicada compatível com a camada C (SOC2 Tipo 1) de acordo com a [Estrutura de conformidade para padrões e regulamentações do setor](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) do Office 365 (baixar o PDF). Isso significa que os resultados e dados do trabalho nunca fluem por meio de sistemas não compatíveis com o Bing. 
  
## <a name="permissions"></a>Permissões

Os resultados dos trabalhos recuperados das cargas de trabalho do Office 365, como o SharePoint e OneDrive for Business, têm a segurança realizada na fonte. Os usuários não podem ver os recursos, tais como documentos do Word ou apresentações do PowerPoint, que não possam ser vistos e acessados por meio do Office 365. Eles só podem visualizar seus próprios arquivos e aqueles compartilhados explícita ou implicitamente com eles pelo autor (por exemplo, por meio da associação de grupo) no SharePoint.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Proteção das consultas de usuários da parte pública do Bing

Como as pesquisas relacionadas ao trabalho podem ser confidenciais, a Pesquisa da Microsoft implementou um conjunto de medidas de confiança sobre como elas são manipuladas pela parte de resultados web públicos da Bing.
  
Independentemente da consulta do usuário conter um ou mais resultados de trabalho na resposta retornada, as seguintes medidas são executadas:
  
- Registro em Log
    
  - Todos os logs de pesquisa referentes ao tráfego da Pesquisa da Microsoft têm as identidades removidas e são armazenados separadamente do tráfego público que não for da Pesquisa da Microsoft. Eles são mantidos por 18 meses e o acesso é restrito para fins de depuração de bugs.
    
  - As consultas nesses logs não são usadas para modelar ou treinar recursos públicos, como sugestão automática ou pesquisas relacionadas na web pública.
    
  - O acesso restrito é gerenciado por vários mecanismos seguros, incluindo os grupos de segurança e outras camadas no sistema de engenharia.
    
- Pesquisar o histórico
    
  - Ao fazer login com uma conta corporativa ou de estudante, o histórico de pesquisa de um usuário não estará disponível em outros computadores ou dispositivos.
    
- Publicidade
    
  - As consultas de pesquisa corporativa nunca são compartilhadas com ou sugeridas para anunciantes.
    
  - Os logs de pesquisa de anúncios referentes à Pesquisa da Microsoft são armazenados separadamente do tráfego público.
    
  - Os anúncios nunca são direcionados para um usuário com base na sua identidade de trabalho ou da organização.
    
## <a name="gdpr"></a>RGPD

Em [21 de maio de 2018, a postagem do blog](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) da Microsoft reflete o nosso compromisso com a conformidade com o RGDP e como a Microsoft ajuda empresas e organizações a cumprir suas próprias obrigações de conformidade com o RGDP. Você pode encontrar detalhes adicionais nas [Perguntas Frequentes da Central de Confiabilidade](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs) da Microsoft. As consultas da Pesquisa da Microsoft que operam com base em dados de clientes organizacionais dentro dos Serviços Online também atenderão às obrigações do processador descritas no artigo 28, bem como refletidos nas [Perguntas Frequentes da Central de Confiabilidade](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Com relação às consultas da Pesquisa da Microsoft que forem feitas no Bing público, a Microsoft é uma controladora de dados e implementou medidas para remover a identificação das consultas, como descrito no RGPD.


