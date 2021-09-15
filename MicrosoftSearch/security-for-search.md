---
title: Segurança e privacidade para Pesquisa da Microsoft no Bing
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Proteja os dados e os usuários finais da sua empresa enquanto fornece informações aos usuários autorizados com Pesquisa da Microsoft em Bing
ms.openlocfilehash: bf3629b2508c705d19e3b7b772c6f3672063a6f1
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375699"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Segurança e privacidade para Pesquisa da Microsoft no Bing

Com medidas aprimoradas de privacidade e segurança, Pesquisa da Microsoft em Bing ajuda a proteger seus usuários e dados de local de trabalho.

## <a name="secure-by-default"></a>Segurança por padrão

Pesquisa da Microsoft em Bing solicitações são feitas por HTTPS. A conexão é criptografada de ponta a ponta para segurança aprimorada.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticação e autorização com o Azure Active Directory

A autenticação Pesquisa da Microsoft no Bing está vinculada a Azure Active Directory. Quando Pesquisa da Microsoft usuários vão para Bing, o Bing de Bing mostrará opções de login para uma conta da Microsoft, bem como uma conta de trabalho ou de estudante. Se Bing não puder determinar se um usuário é um participante qualificado, os usuários poderão ir para a página [Explorar](https://www.bing.com/business/explore) Pesquisa da Microsoft, onde serão redirecionados automaticamente para a página de login da sua organização.

Os usuários podem acessar a Pesquisa da Microsoft com uma conta corporativa ou de estudante. Eles precisam entrar com as mesmas credenciais que usam para acessar os serviços do Office 365, como o SharePoint ou o Outlook. Não é possível usar uma conta Microsoft pessoal para entrar na Pesquisa da Microsoft.

## <a name="single-sign-on"></a>Logon único

Se um usuário já estiver autenticado com sua conta de trabalho ou de estudante em outro serviço, como Outlook ou SharePoint, ele será automaticamente assinado na mesma conta de trabalho ou de estudante quando for para o Bing no mesmo navegador. Além disso, quando o usuário sair de sua conta de trabalho ou de estudante, ele será automaticamente assinado de outros serviços Microsoft Office no mesmo navegador.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Comunica-se com a nuvem da Microsoft a partir do navegador

Quando um usuário entrar com sua conta de trabalho ou de estudante, Bing baixará as bibliotecas de clientes necessárias para o navegador para habilitar Pesquisa da Microsoft resultados. Em seguida, quando eles pesquisam, o código no navegador chama a nuvem Office 365 para obter resultados de trabalho. Para fazer isso, Pesquisa da Microsoft usa uma API dedicada que é operada de acordo com os objetivos de controle do SSAE 18 SOC2 Tipo 1. Isso significa que os resultados do trabalho e os dados de trabalho não fluem por sistemas Bing que estão sujeitos a objetivos de controle de processamento de dados menos rigorosos do que os resultados do trabalho em si estão sujeitos quando processados nos Serviços Office 365 Core Online.
  
## <a name="permissions"></a>Permissões

Os resultados dos trabalhos recuperados das cargas de trabalho do Office 365, como o SharePoint e OneDrive for Business, têm a segurança realizada na fonte. Os usuários não podem ver os recursos, tais como documentos do Word ou apresentações do PowerPoint, que não possam ser vistos e acessados por meio do Office 365. Eles só podem visualizar seus próprios arquivos e aqueles compartilhados explícita ou implicitamente com eles pelo autor (por exemplo, por meio da associação de grupo) no SharePoint.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Pesquisa da Microsoft no Bing protege pesquisas no local de trabalho

Quando um usuário insiro uma consulta de pesquisa no Pesquisa da Microsoft em Bing, duas solicitações de pesquisa simultâneas ocorrem:

- Uma pesquisa dos recursos internos da sua organização.
- Uma pesquisa separada de resultados públicos de Bing.com.

Como as pesquisas no local de trabalho podem ser confidenciais, Pesquisa da Microsoft implementou um conjunto de medidas de confiança que descrevem como a pesquisa separada de resultados públicos do Bing.com é manipulada.

### <a name="logging"></a>Registrar em log

- Todos os Bing de pesquisa.com que pertencem Pesquisa da Microsoft no Bing tráfego são desassociados de sua identidade de local de trabalho.
- Se um conjunto de restrições ou limites de frequência for atendido, o que nos dará confiança de que a consulta não é específica de uma organização específica, a consulta será tratada conforme descrito na seção Pesquisa e inteligência artificial da Declaração de [Privacidade.](https://privacy.microsoft.com/privacystatement) Por exemplo, essas consultas serão usadas para modelar e treinar recursos públicos, como a agregação automática ou pesquisas relacionadas.
- As consultas que não atenderem o conjunto de restrições ou limites de frequência serão armazenadas separadamente do tráfego público, não do Microsoft Search.

### <a name="advertising"></a>Publicidade

A publicidade mostrada em Bing.com em conexão com pesquisas no local de trabalho está relacionada exclusivamente ao conteúdo das consultas de pesquisa. Os anúncios nunca serão direcionados aos usuários com base na identidade do local de trabalho.

## <a name="gdpr"></a>RGPD

A postagem de blog de 21 de maio de [2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) da Microsoft reflete nosso compromisso com a conformidade com o RGPD e como a Microsoft ajuda empresas e organizações com suas próprias obrigações de conformidade do RGPD. Você pode encontrar detalhes adicionais na Perguntas frequentes da Central [de Confiações da](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)Microsoft.

Pesquisa da Microsoft consultas executadas em relação aos recursos internos e resultados retornados de um cliente são considerados Dados do Cliente e, como tal, também atendem aos compromissos do processador descritos no artigo 28, como refletido nas perguntas frequentes da Central de Confiações [.](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs) Em relação às consultas de Pesquisa da Microsoft que vão para o público Bing, a Microsoft cumpre suas obrigações de RGPD como um controlador de dados.
