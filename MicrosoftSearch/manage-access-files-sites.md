---
title: Gerenciar o acesso a arquivos e sites
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Uma visão geral de como os administradores podem garantir que o acesso a sites e arquivos sejam restritos corretamente em sua organização.
ms.openlocfilehash: c85cce6208743b884cce86cc11c46aab3e01254d
ms.sourcegitcommit: 70c48e470262099feb79553e36593521cc5e7abc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2021
ms.locfileid: "58835013"
---
# <a name="manage-access-to-files-and-sites"></a>Gerenciar o acesso a arquivos e sites

Nem todos os arquivos ou sites devem estar disponíveis para todos em sua organização. Os administradores e usuários podem gerenciar o acesso a informações confidenciais ou confidenciais usando soluções que melhor abordam seus problemas específicos. Se os controles de acesso adequados não são aplicados consistentemente, isso pode resultar em algo a que nos referimos como "oversharing". Tornando mais fácil encontrar informações compartilhadas em sua organização, arquivos e sites com restrições inadequadas podem ser acessados inadvertidamente usando Pesquisa da Microsoft.

Os administradores de pesquisa não podem resolver esses problemas de compartilhamento em excesso. Arquivos e sites sem acesso restrito serão divulgados nos resultados da pesquisa interna e por meio de outras vias de descoberta. No entanto, quando os controles para evitar o excesso de compartilhamento estão no local, todas as vias, incluindo a pesquisa, serão fechadas.

## <a name="solutions-to-prevent-oversharing"></a>Soluções para evitar o excesso de compartilhamento

Use as ferramentas, políticas e técnicas abaixo para restringir ou ofuscar o acesso às informações para ajudar a evitar o excesso de compartilhamento. A implementação dessas soluções exigirá acesso provável ao administrador global, de conformidade ou de segurança. Também recomendamos uma campanha interna para instruir seus usuários sobre como proteger corretamente, rotular e permissões de seus sites e arquivos.

### <a name="public-sites-or-sites-with-public-owners"></a>Sites públicos ou sites com proprietários públicos

Uma maneira de compartilhar arquivos com todos em sua organização é por meio de sites públicos ou sites com proprietários públicos. Os rótulos de sensibilidade podem impedir que os usuários criam grupos ou sites públicos. Isso é feito configurando todos os rótulos para criar grupos privados e exigindo um rótulo para grupos. Para obter detalhes, consulte Usar rótulos de sensibilidade para proteger o conteúdo em Microsoft Teams, grupos Microsoft 365 [e sites SharePoint.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) Você precisará definir um processo separado para que os usuários solicitem ou criem grupos públicos.

Outra opção é definir quem pode criar Microsoft 365 grupos em sua organização. Para obter mais informações, [consulte Create a group for users who need to create Microsoft 365 groups](/microsoft-365/solutions/manage-creation-of-groups#step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups). Um administrador global precisará configurar um processo para que os usuários enviem solicitações de criação de grupo. Também sugerimos que você informe os usuários sobre essa alteração.

Se não for possível restringir a capacidade de criar grupos para sua organização, você poderá monitorar as atividades, incluindo a criação de grupo, por meio da auditoria. Para obter detalhes sobre auditoria básica e avançada, consulte [Auditing solutions in Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview).

### <a name="shared-files"></a>Arquivos compartilhados

Para restringir o acesso a todos os arquivos classificados como confidenciais para empresas, você pode definir e aplicar classificações de dados para sua organização. Os dados de exemplo precisarão ser coletados para ajudar a treinar novos classificadores. Para obter detalhes sobre pré-requisitos e permissões, consulte [Saiba mais sobre a classificação de dados](/microsoft-365/compliance/data-classification-overview).

Para restringir o acesso de arquivos a membros de um grupo específico, como executivos, você pode criar rótulos personalizados com escopo para um grupo de segurança. Em seguida, quando um membro do grupo de segurança aplica o rótulo, restringe automaticamente o acesso ao grupo. Para saber mais sobre rótulos personalizados, consulte [Create and configure sensitivity labels and](/microsoft-365/compliance/create-sensitivity-labels) their policies and Restrict access to content by using [sensitivity labels to apply encryption](/microsoft-365/compliance/encryption-sensitivity-labels).

Para garantir que documentos e emails sejam rotulados corretamente, os administradores também podem definir uma política de rótulo padrão e exigir que os usuários os rotulem. Para mais informações, consulte [Exigir que os usuários apliquem um rótulo em seus emails e documentos](/microsoft-365/compliance/sensitivity-labels-office-apps#require-users-to-apply-a-label-to-their-email-and-documents).

Você também pode minimizar o excesso de compartilhamento de arquivos impedindo que arquivos recentes apareçam durante a pesquisa. Isso pode ser feito em um nível de grupo ou para todos em sua organização. Para impedir que arquivos recentes apareçam para um grupo, consulte [Personalização](/graph/insights-customize-item-insights-privacy)de informações de item privacidade no Microsoft Graph . Um membro do grupo poderá ver seus próprios arquivos recentes, mas outros receberão uma mensagem de que nenhum resultado foi encontrado. Para desativar arquivos recentes para todos na sua organização, você precisará desativar o Delve. Para obter detalhes, consulte [Control access to Delve](/sharepoint/delve-for-office-365-admins#control-access-to-delve).

> [!Note]
> Os usuários ainda poderão encontrar arquivos compartilhados com eles em Pesquisa da Microsoft resultados. Personalizar percepções de itens ou Delve apenas impede que arquivos apareçam na lista de arquivos recentes de um usuário.

### <a name="sites-and-files-between-groups"></a>Sites e arquivos entre grupos

Para restringir o compartilhamento de arquivos e sites entre grupos, por exemplo, uma equipe de finanças que gerencia projetos confidenciais com uma equipe de marketing, você pode definir e implementar políticas de barreira de informações. Essas barreiras também impedem outros aspectos de comunicação e colaboração em Microsoft Teams, SharePoint e OneDrive. Para obter detalhes, [consulte Learn about information barriers in Microsoft 365](/microsoft-365/compliance/information-barriers).

## <a name="get-access-insights"></a>Obter informações de acesso

A governança do Access fornece informações sobre sites com os documentos mais confidenciais e sites com excesso de compartilhamento em sua organização. Para uma visão geral, consulte [Novidades em Segurança e Conformidade no](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-new-in-security-and-compliance-in-sharepoint-and-onedrive/ba-p/1696705)SharePoint e OneDrive . Você precisará nomear [sua organização](https://forms.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) para essa visualização.