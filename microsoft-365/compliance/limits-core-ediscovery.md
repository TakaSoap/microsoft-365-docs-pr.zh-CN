---
title: 核心电子数据展示事例的限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍了 Microsoft 365 核心电子数据展示事例的限制。
ms.openlocfilehash: 00df8cff683701ce5ee38dca12b6f7af5b31c8b0
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351893"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="365a5-103">核心电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="365a5-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="365a5-104">下表列出了与核心电子数据展示事例相关联的核心电子数据展示事例和保留的限制。</span><span class="sxs-lookup"><span data-stu-id="365a5-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="365a5-105">有关核心电子数据展示的详细信息，请参阅[核心电子数据展示概述](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="365a5-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="365a5-106">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="365a5-106">**Description of limit**</span></span>|<span data-ttu-id="365a5-107">**限制**</span><span class="sxs-lookup"><span data-stu-id="365a5-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="365a5-108">组织的最大事例数</span><span class="sxs-lookup"><span data-stu-id="365a5-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="365a5-109">无限制</span><span class="sxs-lookup"><span data-stu-id="365a5-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="365a5-110">组织的最大事例保留数</span><span class="sxs-lookup"><span data-stu-id="365a5-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="365a5-111">10,000</span><span class="sxs-lookup"><span data-stu-id="365a5-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="365a5-112">单个事例保留中的最大邮箱数</span><span class="sxs-lookup"><span data-stu-id="365a5-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="365a5-113">1,000</span><span class="sxs-lookup"><span data-stu-id="365a5-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="365a5-114">单个事例保留中的 SharePoint 和 OneDrive for business 网站的最大数量</span><span class="sxs-lookup"><span data-stu-id="365a5-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="365a5-115">100</span><span class="sxs-lookup"><span data-stu-id="365a5-115">100</span></span>  <br/> |
  |<span data-ttu-id="365a5-116">显示在核心电子数据展示主页上的最大事例数，以及在某一事例中的保留、搜索和导出选项卡上显示的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="365a5-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="365a5-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="365a5-117"><sup>1</sup></span></span> |<span data-ttu-id="365a5-118">1,000</span><span class="sxs-lookup"><span data-stu-id="365a5-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="365a5-119"><sup>1</sup>若要查看超过1000个事例、保留、搜索或导出的列表，您可以使用相应的 Office 365 安全性 & 合规性 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="365a5-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="365a5-120">Get-compliancecase</span><span class="sxs-lookup"><span data-stu-id="365a5-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [<span data-ttu-id="365a5-121">CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="365a5-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [<span data-ttu-id="365a5-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="365a5-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [<span data-ttu-id="365a5-123">New-compliancesearchaction</span><span class="sxs-lookup"><span data-stu-id="365a5-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
