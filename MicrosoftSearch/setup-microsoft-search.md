---
title: Configurar a **Pesquisa da Microsoft**
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar a Pesquisa da Microsoft pela primeira vez.
ms.openlocfilehash: 3b872370dc2058c56637b836f8f78b7ed8e6680e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591049"
---
# <a name="set-up-microsoft-search"></a>Configurar a Pesquisa da Microsoft

A **Pesquisa da Microsoft** fornece uma interface amigável para ajudar os usuários a encontrarem informações, como arquivos e documentos, sites internos e ferramentas de negócios, pessoas e grupos, locais e trajetos, conversas e respostas, acessando com segurança todas as fontes de dados, incluindo emails, arquivos e arquivos do SharePoint, Conteúdo do OneDrive e outros recursos compartilhados, bem como a Internet na organização do usuário.

Para saber mais sobre os recursos da **Pesquisa da Microsoft**, consulte [Visão geral da pesquisa da Microsoft](overview-microsoft-search.md).

## <a name="get-started"></a>Introdução

A **Pesquisa da Microsoft** está ativada por padrão para todos os aplicativos da Microsoft compatíveis, como parte do Microsoft 365. Tudo o que um usuário precisa fazer é entrar com uma conta de trabalho ou escola e usar um navegador com o Bing definido como o provedor de pesquisa padrão.

Você administra a **Pesquisa da Microsoft** a partir do **centro de administração do Microsoft 365**. Entre usando seu logon com credenciais de administrador e escolha o bloco **Administrador** na lista de aplicativos do Office 365 (Clique no ícone do **Inicializador de aplicativos** no canto superior esquerdo da lista de aplicativos). No **centro de administração do Microsoft 365**, selecione **Pesquisa da Microsoft** em **Configurações** no painel de navegação esquerdo. 

**Observação:** Se você estiver vendo a**Pesquisa da Microsoft** em**Configurações** no**centro de administração do Microsoft 365**, habilite a opção **Experimente a visualização** no canto superior direito do centro de administração. 

Como administrador, você deve considerar algumas coisas que podem tornar a experiência da **Pesquisa da Microsoft** eficiente e amigável em sua organização.

### <a name="step-1-check-access-level-of-your-users"></a>Etapa 1: verifique o nível de acesso de seus usuários

A **Pesquisa da Microsoft** respeita as configurações de segurança da fonte de conteúdo. O que os usuários veem nos resultados da pesquisa depende das permissões e dos níveis de acesso. Revise o nível de acesso dos usuários em sua organização para garantir que os usuários encontrem apenas conteúdo que eles possam acessar.

Saiba mais sobre como [planejar permissões](https://docs.microsoft.com/pt-BR/sharepoint/plan-your-permissions-strategy) e [criar níveis de permissões](https://docs.microsoft.com/pt-BR/sharepoint/how-to-create-and-edit-permission-levels).

### <a name="step-2-assign-search-admin-and-search-editor"></a>Etapa 2: atribua o administrador de pesquisa e o editor de pesquisa

Há duas novas funções no **Centro de administração do Microsoft** – administrador de pesquisa e editor de pesquisa.  Administrador global, que tem privilégios completos, atribui as funções de administrador aos usuários com a função de administrador de pesquisa. Os administradores de pesquisa podem delegar as funções de administrador de pesquisa ou de editor de pesquisa para outros usuários. Para saber mais sobre as diferentes funções de administrador, consulte [Sobre as funções de administrador do Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide).

**Observação:** essas duas funções novas – administrador de pesquisa e editor de pesquisa – estão disponíveis somente no **Centro de administração do Microsoft 365**, e não no portal de administração herdado. 

Os administradores de pesquisa influenciam diretamente a experiência de pesquisa dos usuários finais. Isso inclui escolher os tipos de resultados que você deseja destacar para seus usuários. Pode ser difícil para uma pessoa escolher e criar conteúdo autoritativo em muitos tópicos diferentes pelos quais os usuários pesquisam em uma organização. Recomendamos que você aproveite a experiência e o conhecimento de especialistas no assunto (SMEs) e outros usuários adicionando-os como editores. 

Na **Pesquisa da Microsoft**, você pode gerenciar as configurações de pesquisa e o conteúdo da sua organização usando duas novas funções:
1. **Administrador de Pesquisa**: essa função pode criar e gerenciar conteúdo de resultados de pesquisa e definir configurações de consulta para melhorar os resultados de pesquisa na organização. O administrador de pesquisa gerencia a configuração da **Pesquisa da Microsoft** e designa editores de pesquisa para criarem conteúdo.
2. **Editor de Pesquisa:** Cria, gerencia e exclui conteúdo para a **Pesquisa da Microsoft** no centro de administração do Microsoft 365. Essa função pode criar e gerenciar conteúdo editorial, como perguntas e respostas frequentes, lugares e locais importantes, sites e aplicativos pesquisados e usados com frequência, etc. Ela, no entanto, não garante acesso para gerenciar configurações de pesquisa.

Para atribuir funções de administrador, consulte [Atribuir direitos de administrador no Office 365 for business](https://docs.microsoft.com/pt-BR/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).

### <a name="step-3-make-content-easy-to-find"></a>Etapa 3: torne o conteúdo fácil de encontrar 

A **Pesquisa da Microsoft** fornece aos administradores ferramentas que eles podem usar para criar uma experiência de pesquisa robusta para seus usuários. Na **Pesquisa da Microsoft**, os administradores têm três conteúdos de pesquisa diferentes que podem ser criados para uma melhor experiência de pesquisa e para melhorar a localização do conteúdo:
- **Indicador**: os indicadores são semelhantes aos resultados promovidos no SharePoint e ajudam a promover os melhores resultados possíveis para as consultas do usuário na parte superior dos resultados da pesquisa, facilitando a localização de sites internos importantes. 
- **Perguntas e Respostas:** as P e R são semelhantes às perguntas frequentes, e geralmente estão em formato de pergunta e resposta. Elas fornecem as melhores respostas possíveis para perguntas relacionadas ao trabalho do usuário.
- **Local:** o local é um endereço que ajuda os usuários a localizarem os edifícios, escritórios e campi de sua organização. 

Quanto mais Indicadores, P e R e Locais você tiver, mais valor e benefício os usuários terão. No entanto, um excesso destes pode acarretar uma sobrecarga de gerenciamento substancial, pois eles devem ser revisados e atualizados periodicamente para manter os resultados relevantes.

Aqui estão alguns exemplos de conteúdo para os quais você deve considerar criar indicadores para os seus usuários:
- Informações sobre a organização, produtos ou serviços.
- Conteúdo informativo que está disponível para todos; por exemplo, informações sobre a empresa, ajuda para aplicativos do Windows e do Office, etc. 
- Conteúdo que as pessoas na organização geralmente pesquisam no trabalho cotidiano. Pesquisas comuns relacionadas ao trabalho incluem benefícios de funcionários, relatórios de tempo e despesas, envio de pedidos de compras e obtenção de ajuda de serviços de TI. 

Para criar e gerenciar conteúdo de pesquisa, consulte [Como tornar o conteúdo fácil de encontrar](make-content-easy-to-find.md).

### <a name="step-4-test-single-sign-on"></a>Etapa 4: testar o logon único
A **Pesquisa da Microsoft** usa o Azure Active Directory (AAD) para autenticar e autorizar o acesso aos dados da sua organização.  Isso significa que seus usuários são automaticamente conectados à sua conta corporativa ou de estudante quando você faz logon em um aplicativo do Office 365 ou no Windows 10.

Recomendamos que os usuários da **Pesquisa da Microsoft** usem o logon único, pois este reduz o número de vezes que os usuários são solicitados a fazer logon. Os administradores devem testar o logon único com um pequeno grupo de usuários para ajudar a identificar problemas de configuração de bloqueio. 

Para usuários do Chrome no Windows 10, o logon único funciona somente quando a extensão de logon do Windows 10 e AAD para o Chrome está instalada. Depois de instalada, você pode usar a extensão do Chrome para autenticar facilmente com AAD ao fazer logon em sites compatíveis, incluindo o Office 365 e o Bing. Esta funcionalidade está disponível apenas para usuários autorizados. 

Para baixar e instalar a extensão de logon do Windows 10 e AAD para o Chrome, acesse a [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2090961).

### <a name="step-5-training-and-communication"></a>Etapa 5: Treinamento e comunicação
Estabeleça recursos de autoatendimento que os funcionários possam acessar facilmente por conta própria. Isso ajudará a reduzir a carga total sobre você e sua equipe para impulsionar constantemente as comunicações e auxiliar no autotreinamento e na educação dos funcionários. Forneça aos seus usuários comunicações, perguntas frequentes, vídeos e treinamentos ou webinars gravados. Aqui estão alguns links úteis para começar:
- [Encontre o que você precisa com a Pesquisa da Microsoft no Office](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Centro de Treinamento do Office 365](https://support.office.com/office-training-center)
- 
  [Centro de pesquisa da Microsoft](https://support.office.com/pt-BR/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)

### <a name="trying-out-microsoft-search-in-bing"></a>Experimentando a **Pesquisa da Microsoft** no Bing 
O administrador da **Pesquisa da Microsoft** pode desativar a **Pesquisa da Microsoft** no Bing. Se desativada, os usuários não verão o conteúdo da organização na pesquisa do Bing. Por padrão, a **Pesquisa da Microsoft** se encontra ativada no Bing. Recomendamos que você mantenha a **Pesquisa da Microsoft** ativada no Bing para ter uma melhor experiência do usuário. 

Se você quiser testar a **Pesquisa da Microsoft** em um locatário de teste ou quiser testar a experiência de pesquisa antes de disponibilizá-la para todos os usuários, desative a **Pesquisa da Microsoft**.
Para ativar/desativar a **Pesquisa da Microsoft** no Bing, vá para **Serviços e suplementos** no **centro de administração do Microsoft 365** e ative/desative a **Pesquisa da Microsoft no Bing**.
