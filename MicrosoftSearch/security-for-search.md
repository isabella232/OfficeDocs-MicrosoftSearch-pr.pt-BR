---
title: Segurança e privacidade para o Microsoft Search no Bing
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Proteger os dados da sua empresa e os usuários finais enquanto fornecem informações a usuários autorizados com o Microsoft Search no Bing
ms.openlocfilehash: d3d8822b68fc730885e973c0c24c52070d50eba8
ms.sourcegitcommit: f4cb37fdf85b895337caee827fb72b5b7fcaa8ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2019
ms.locfileid: "39995383"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Segurança e privacidade para o Microsoft Search no Bing

Com medidas de segurança e privacidade aprimoradas, o Microsoft Search no Bing ajuda a proteger seus dados de usuários e locais de trabalho.

## <a name="secure-by-default"></a>Segurança por padrão

A pesquisa da Microsoft em solicitações do Bing é feita via HTTPS. A conexão é criptografada de ponta a ponta para melhorar a segurança.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticação e autorização com o Azure Active Directory

A autenticação da pesquisa da Microsoft no Bing está vinculada ao Azure Active Directory. Quando os usuários de pesquisa da Microsoft acessam o Bing, o cabeçalho do Bing mostrará as opções de entrada de uma conta da Microsoft, bem como uma conta corporativa ou de estudante. Se o Bing não puder determinar se um usuário é um participante qualificado, os usuários poderão ir para a página [explorar o Microsoft Search](https://www.bing.com/business/explore) , onde eles serão redirecionados automaticamente para a página de entrada da sua organização.
 
Os usuários podem acessar a Pesquisa da Microsoft com uma conta corporativa ou de estudante. Eles precisam entrar com as mesmas credenciais que usam para acessar os serviços do Office 365, como o SharePoint ou o Outlook. Não é possível usar uma conta Microsoft pessoal para entrar na Pesquisa da Microsoft.
    
## <a name="single-sign-on"></a>Logon único

Se um usuário já estiver autenticado com sua conta corporativa ou de estudante em outro serviço, como Outlook ou SharePoint, ele será automaticamente conectado à mesma conta corporativa ou de estudante quando acessarem o Bing no mesmo navegador. Além disso, quando o usuário sair de sua conta corporativa ou de estudante, ele será desconectado automaticamente de outros serviços do Microsoft Office no mesmo navegador.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Comunica-se com a nuvem da Microsoft a partir do navegador

Quando um usuário entra com sua conta corporativa ou de estudante, o Bing baixará as bibliotecas de cliente necessárias para o navegador para habilitar os resultados da pesquisa da Microsoft. Em seguida, quando pesquisamos, o código do navegador chama a nuvem do Office 365 para obter resultados de trabalho. Para fazer isso, o Microsoft Search usa uma API dedicada que é a camada C (SOC2 tipo 1) em conformidade com o Office 365 [Compliance Framework for Industry Standards and Regulations] (https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (download do pdf). Isso significa que os resultados de trabalho e os dados de trabalho nunca fluem por sistemas do Bing que não estão em conformidade.
  
## <a name="permissions"></a>Permissões

Os resultados dos trabalhos recuperados das cargas de trabalho do Office 365, como o SharePoint e OneDrive for Business, têm a segurança realizada na fonte. Os usuários não podem ver os recursos, tais como documentos do Word ou apresentações do PowerPoint, que não possam ser vistos e acessados por meio do Office 365. Eles só podem visualizar seus próprios arquivos e aqueles compartilhados explícita ou implicitamente com eles pelo autor (por exemplo, por meio da associação de grupo) no SharePoint.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Pesquisa da Microsoft no Bing protege as pesquisas de local de trabalho

Quando um usuário insere uma consulta de pesquisa no Microsoft Search no Bing, duas solicitações de pesquisa simultâneas ocorrem:

- Uma pesquisa dos recursos internos da sua organização.
- Uma pesquisa separada de resultados públicos do Bing.com.

Como as pesquisas de área de trabalho podem ser confidenciais, a pesquisa da Microsoft implementou um conjunto de medidas de confiança que descrevem como a pesquisa separada de resultados públicos de Bing.com é manipulada.

### <a name="logging"></a>Registro em log

<Need an intro paragraph here>

- Todos os logs de pesquisa do Bing.com que pertencem à pesquisa da Microsoft no tráfego do Bing são desassociados da sua identidade de local de trabalho.
- Se um conjunto de restrições ou limites de frequência for atendido, o que nos dá a confiança de que a consulta não é específica para uma organização específica, a consulta será tratada conforme descrito na seção pesquisa e inteligência artificial da [declaração de privacidade](https://privacy.microsoft.com/privacystatement). Por exemplo, essas consultas serão usadas para modelar e treinar recursos públicos, como sugestão automática ou pesquisas relacionadas.
- As consultas que não atenderem o conjunto de restrições ou limites de frequência serão armazenadas separadamente do tráfego público, não do Microsoft Search.

### <a name="advertising"></a>Publicidade

O anúncio mostrado no Bing.com em conexão com pesquisas de local de trabalho é apenas relacionado ao conteúdo das consultas de pesquisa. Os anúncios nunca serão direcionados aos usuários com base na identidade do local de trabalho.
     
## <a name="gdpr"></a>RGPD

A [postagem de blog de 21 de maio de 2018,](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) a Microsoft reflete nosso compromisso com a conformidade do rgpd e como a Microsoft ajuda empresas e organizações com suas próprias obrigações de conformidade do rgpd. Você pode encontrar mais detalhes na FAQ da [central de confiabilidade](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)da Microsoft. 

As consultas de pesquisa da Microsoft executadas em relação aos recursos internos do cliente e os resultados retornados são considerados dados do cliente e, como tal, também atendem aos compromissos do processador descritos no artigo 28, conforme refletido na [FAQ da central de confiabilidade](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs). Com relação às consultas da pesquisa da Microsoft que vão para o Bing público, a Microsoft está em conformidade com suas obrigações do RGPD como um controlador de dados.

