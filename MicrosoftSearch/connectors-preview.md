---
title: Visualização de conectores
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Saiba mais sobre a visualização de conectores do Microsoft Graph para o Microsoft Search.
ms.openlocfilehash: 592e108fe0333e4faf8ff2e4618f9d5216847b8a
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367663"
---
# <a name="microsoft-graph-connectors-preview-release-and-features"></a><span data-ttu-id="2b731-103">Versão e recursos do Microsoft Graph Connector Preview</span><span class="sxs-lookup"><span data-stu-id="2b731-103">Microsoft Graph connectors preview release and features</span></span>

<span data-ttu-id="2b731-104">Agora, os conectores do Microsoft Graph e as APIs de pesquisa da Microsoft estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2b731-104">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="2b731-105">A distribuição inicial será para os clientes configurados para lançamento direcionado.</span><span class="sxs-lookup"><span data-stu-id="2b731-105">The initial rollout will be to customers configured for Targeted Release.</span></span> <span data-ttu-id="2b731-106">Após a conclusão da distribuição para todos os locatários, o índice de utilização de cota de conectores ficará sujeito à cobrança.</span><span class="sxs-lookup"><span data-stu-id="2b731-106">Upon rollout completion to all tenants, index quota utilization from connectors content will become subject to billing.</span></span> <span data-ttu-id="2b731-107">Veja [requisitos de licenciamento e preços](licensing.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2b731-107">See [Licensing requirements and pricing](licensing.md) for more information.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="2b731-108">Configurar lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="2b731-108">Set up Targeted release</span></span>

<span data-ttu-id="2b731-109">Se você quiser usar conectores de gráfico em seu locatário durante a distribuição, você deve optar pelo lançamento direcionado.</span><span class="sxs-lookup"><span data-stu-id="2b731-109">If you want to use Graph connectors in your tenant during rollout, you must opt into Targeted release.</span></span> <span data-ttu-id="2b731-110">Para saber mais sobre a opção de lançamento direcionado e como configurá-la, confira [configurar as opções de lançamento padrão ou direcionadas no Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="2b731-110">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="preview-features"></a><span data-ttu-id="2b731-111">Recursos de visualização</span><span class="sxs-lookup"><span data-stu-id="2b731-111">Preview features</span></span>

<span data-ttu-id="2b731-112">Embora os conectores do Microsoft Graph e as APIs de pesquisa da Microsoft agora estejam disponíveis em geral, há vários recursos que permanecerão em visualização.</span><span class="sxs-lookup"><span data-stu-id="2b731-112">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that will remain in preview.</span></span>

<span data-ttu-id="2b731-113">O conjunto de conectores e recursos na visualização incluem:</span><span class="sxs-lookup"><span data-stu-id="2b731-113">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="2b731-114">Conector DevOps do Azure</span><span class="sxs-lookup"><span data-stu-id="2b731-114">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="2b731-115">Conector do Salesforce</span><span class="sxs-lookup"><span data-stu-id="2b731-115">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="2b731-116">[Conector do ServiceNow](servicenow.md) com permissões de pesquisa que usam ACLs de origem</span><span class="sxs-lookup"><span data-stu-id="2b731-116">[ServiceNow connector](servicenow.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="2b731-117">Gerenciar o cluster de resultados</span><span class="sxs-lookup"><span data-stu-id="2b731-117">Manage result cluster</span></span>](result-cluster.md)