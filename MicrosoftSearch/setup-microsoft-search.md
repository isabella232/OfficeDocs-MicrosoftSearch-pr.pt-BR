---
title: Configurar a Pesquisa da Microsoft
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
ms.openlocfilehash: 55ff009a17f63bfdaa1edf1e14fddfe132e20000
ms.sourcegitcommit: 4eeb78066fd13e906daed3add003398bd9d0f6ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2019
ms.locfileid: "35917574"
---
# <a name="set-up-microsoft-search"></a>Configurar a Pesquisa da Microsoft

A Pesquisa da Microsoft fornece uma interface amigável para ajudar os usuários a encontrarem informações, como arquivos e documentos, sites internos e ferramentas de negócios, pessoas e grupos, locais e trajetos, conversas e respostas, acessando com segurança todas as fontes de dados, incluindo emails, arquivos e arquivos do SharePoint, Conteúdo do OneDrive e outros recursos compartilhados, bem como a Internet na organização do usuário.

Para saber mais sobre os recursos da Pesquisa da Microsoft, confira [Visão Geral da Pesquisa da Microsoft](overview-microsoft-search.md).

## <a name="get-started"></a>Introdução

A Pesquisa da Microsoft está ativada por padrão para todos os aplicativos da Microsoft compatíveis, como parte do Microsoft 365. Tudo o que um usuário precisa fazer é entrar com uma conta de trabalho ou escola e usar um navegador com o Bing definido como o provedor de pesquisa padrão.

Você administra a Pesquisa da Microsoft a partir do centro de administração do Microsoft 365.

1. No centro de administração do Microsoft 365, acesse **Configurações** > **Microsoft**.

**Observação:** se você NÃO estiver vendo a Pesquisa da Microsoft em **Configurações**, habilite a opção**Experimente a visualização** no canto superior direito de qualquer página do centro de administração.

Como administrador, você deve considerar algumas coisas que podem tornar a experiência da Pesquisa da Microsoft eficiente e amigável em sua organização.

## <a name="step-1-check-access-level-of-your-users"></a>Etapa 1: Verifique o nível de acesso de seus usuários

A Pesquisa da Microsoft respeita as configurações de segurança da fonte de conteúdo. O que os usuários veem nos resultados da pesquisa depende das permissões e dos níveis de acesso. Revise o nível de acesso dos usuários em sua organização para garantir que os usuários encontrem apenas conteúdo que eles possam acessar.

| Serviço         | Descrição                                                                                                                                                                                                                                         |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Grupos          | [Adicionar ou remover membros dos grupos](https://docs.microsoft.com/office365/admin/create-groups/add-or-remove-members-from-groups)                                                                                                                     |
| Pessoas          | Você pode ocultar que determinados usuários sejam pesquisados em sua lista de endereços, configurando o parâmetro `HiddenFromAddressListEnabled` para `true`, usando o cmdlet [Set-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-user). |
| Microsoft Teams | [Gerenciar o acesso de usuários ao Microsoft Teams](https://docs.microsoft.com/microsoftteams/user-access)                                                                                                                                                      |
| OneDrive        | [Gerenciar o compartilhamento](https://docs.microsoft.com/OneDrive/manage-sharing)                                                                                                                                                                                |
| SharePoint      | 
  [Permissões de planejamento](https://docs.microsoft.com/pt-BR/sharepoint/plan-your-permissions-strategy)<br> 
  [Criar níveis de permissões](https://docs.microsoft.com/pt-BR/sharepoint/how-to-create-and-edit-permission-levels)                          |
| OneNote         | Não é possível pesquisar arquivos inseridos no OneNote. [Alterar as permissões de um bloco de anotações no OneDrive](https://support.office.com/article/B9600CCF-045A-40E6-9913-4A7EB02869A5)                                                                    |
| Yammer          | [Configurações de segurança do Yammer](https://docs.microsoft.com/Yammer/manage-security-and-compliance/yammer-security-settings)                                                                                                                               |

## <a name="step-2-assign-search-admin-and-search-editor"></a>Etapa 2: Atribua o administrador e editor da Pesquisa da Microsoft

Há duas funções de administrador limitadas para ajudá-lo a oferecer suporte à Pesquisa da Microsoft - **Administrador de Pesquisa** e **Editor de Pesquisa**.

> [!NOTE]
> A função do administrador e do editor da Pesquisa só concedem permissões ao centro de administração do Microsoft 365, não à **Pesquisa da Microsoft herdada no portal de administração do Bing**. É necessário ser um administrador global para gerenciar a Pesquisa da Microsoft no portal herdado.

Os administradores da Pesquisa influenciam diretamente a experiência de pesquisa para usuários finais. Isso inclui escolher os tipos de resultados que você deseja destacar para seus usuários. Pode ser difícil para uma pessoa escolher e criar conteúdo autoritativo em muitos tópicos diferentes pelos quais os usuários pesquisam em uma organização. Recomendamos que você aproveite a experiência e o conhecimento dos especialistas no assunto (SME) e de outros usuários, adicionando-os como editores da Pesquisa.

Na Pesquisa da Microsoft, você pode gerenciar as configurações de pesquisa e o conteúdo da sua organização, atribuindo estas duas funções aos usuários:

1. **Administrador de Pesquisa**: Essa função pode criar e gerenciar conteúdo de resultados de pesquisa e definir configurações de consulta para melhorar os resultados de pesquisa na organização. O administrador de Pesquisa gerencia a configuração da Pesquisa da Microsoft e pode realizar todas as tarefas de gerenciamento de conteúdo que um editor de Pesquisa pode.
2. **Editor de Pesquisa:** Cria, gerencia e exclui conteúdo para a Pesquisa da Microsoft no centro de administração do Microsoft 365. Essa função pode criar e gerenciar conteúdos editoriais, como perguntas frequentes e respostas, locais importantes e localizações, sites e aplicativos pesquisados e usados com frequência.

Atualmente, as funções de administrador e de Editor de Pesquisa devem ser atribuídas por um administrador global. Para saber mais, confira [Atribuir funções de administrador](https://docs.microsoft.com/pt-BR/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).

## <a name="step-3-make-content-easy-to-find"></a>Etapa 3: Torne o conteúdo fácil de encontrar

A Pesquisa da Microsoft fornece aos administradores ferramentas que eles podem usar para criar uma experiência de pesquisa robusta para seus usuários. Na Pesquisa da Microsoft, os administradores têm três conteúdos de pesquisa diferentes que podem ser criados para uma melhor experiência de pesquisa e para melhorar a localização do conteúdo:

- **Indicadores:** Os indicadores são semelhantes aos resultados promovidos no SharePoint e ajudam a promover os melhores resultados possíveis para as consultas do usuário na parte superior dos resultados da pesquisa, facilitando a localização de sites internos importantes.
- **Perguntas e Respostas:** as P e R são semelhantes às perguntas frequentes, e geralmente estão em formato de pergunta e resposta. Elas fornecem as melhores respostas possíveis para perguntas relacionadas ao trabalho do usuário.
- **Localizações:** Localizações são endereços que ajudam os usuários a localizarem os edifícios, escritórios e campi de sua organização.

Quanto mais Indicadores, P e R e Locais você tiver, mais valor e benefício os usuários terão. No entanto, um excesso destes pode acarretar uma sobrecarga de gerenciamento substancial, pois eles devem ser revisados e atualizados periodicamente para manter os resultados relevantes.

Aqui estão alguns exemplos de conteúdo para os quais você deve considerar criar indicadores para os seus usuários:

- Informações sobre a organização, produtos ou serviços.
- Conteúdo informativo que está disponível para todos; por exemplo, informações sobre a empresa, ajuda para aplicativos do Windows e do Office, etc.
- Conteúdo que as pessoas na organização geralmente pesquisam no trabalho cotidiano. Pesquisas comuns relacionadas ao trabalho incluem benefícios de funcionários, relatórios de tempo e despesas, envio de pedidos de compras e obtenção de ajuda de serviços de TI.

Para criar e gerenciar conteúdo de pesquisa, consulte [Tornar o conteúdo fácil de encontrar](make-content-easy-to-find.md).

## <a name="step-4-test-single-sign-on"></a>Etapa 4: Testar o logon único

A Pesquisa da Microsoft usa o Azure Active Directory (AAD) para autenticar e autorizar o acesso aos dados da sua organização. Isso significa que seus usuários são automaticamente conectados à sua conta corporativa ou de estudante quando você faz logon em um aplicativo do Office 365 ou no Windows 10.

Recomendamos que os usuários da Pesquisa da Microsoft usem o logon único, pois este reduz o número de vezes que os usuários são solicitados a fazer logon. Os administradores devem testar o logon único com um pequeno grupo de usuários para ajudar a identificar problemas de configuração de bloqueio.

Para usuários do Chrome no Windows 10, o logon único funciona somente quando a extensão de logon do Windows 10 e AAD para o Chrome está instalada. Depois de instalada, você pode usar a extensão do Chrome para autenticar facilmente com AAD ao fazer logon em sites compatíveis, incluindo o Office 365 e o Bing. Esta funcionalidade está disponível apenas para usuários autorizados.

Para baixar e instalar a extensão de logon do Windows 10 e AAD para o Chrome, acesse a [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2090961).

## <a name="step-5-training-and-communication"></a>Etapa 5: Treinamento e comunicação

Estabeleça recursos de autoatendimento que os funcionários possam acessar facilmente por conta própria. Isso ajudará a reduzir a carga total sobre você e sua equipe para impulsionar constantemente as comunicações e auxiliar no autotreinamento e na educação dos funcionários. Forneça aos seus usuários comunicações, perguntas frequentes, vídeos e treinamentos ou webinars gravados. Aqui estão alguns links úteis para começar:

- [Encontre o que você precisa com a Pesquisa da Microsoft no Office](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Centro de Treinamento do Office 365](https://support.office.com/office-training-center)
- 
  [Centro de pesquisa da Microsoft](https://support.office.com/pt-BR/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)

## <a name="trying-out-microsoft-search-in-bing"></a>Experimentando a Pesquisa da Microsoft no Bing

Você pode desativar a **Pesquisa da Microsoft no Bing**. Se desativada, os usuários não verão o conteúdo da organização na pesquisa do Bing. Por padrão, a Pesquisa da Microsoft no Bing está ativada. Recomendamos que você mantenha a Pesquisa da Microsoft ativada no Bing para obter uma melhor experiência de usuário.

Vá até **Configurações** > **Serviços e suplementos** > **Pesquisa da Microsoft no Bing** para ativá-la ou desativá-la.
