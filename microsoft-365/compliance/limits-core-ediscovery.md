---
title: 核心电子数据展示案例中的限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍了 Microsoft 365 中核心电子数据展示案例的限制。
ms.openlocfilehash: e18e1e6c1d9d7ecd78deaf267be72ccdc9d1ba5d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905884"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="27f8a-103">核心电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="27f8a-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="27f8a-104">下表列出了与核心电子数据展示事例关联的核心电子数据展示事例和保留项的限制。</span><span class="sxs-lookup"><span data-stu-id="27f8a-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="27f8a-105">有关核心电子数据展示详细信息，请参阅核心 [电子数据展示概述](./get-started-core-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="27f8a-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="27f8a-106">限制说明</span><span class="sxs-lookup"><span data-stu-id="27f8a-106">Description of limit</span></span> | <span data-ttu-id="27f8a-107">限制</span><span class="sxs-lookup"><span data-stu-id="27f8a-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="27f8a-108">组织的最大事例数。</span><span class="sxs-lookup"><span data-stu-id="27f8a-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="27f8a-109">无限制</span><span class="sxs-lookup"><span data-stu-id="27f8a-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="27f8a-110">组织的最大案例保留数。</span><span class="sxs-lookup"><span data-stu-id="27f8a-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="27f8a-111">10,000</span><span class="sxs-lookup"><span data-stu-id="27f8a-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="27f8a-112">单个案例保留中的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="27f8a-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="27f8a-113">此限制包括用户邮箱总数，以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的邮箱总数。</span><span class="sxs-lookup"><span data-stu-id="27f8a-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="27f8a-114">1,000</span><span class="sxs-lookup"><span data-stu-id="27f8a-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="27f8a-115">单个案例保留中的最大网站数。</span><span class="sxs-lookup"><span data-stu-id="27f8a-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="27f8a-116">此限制包括 OneDrive for Business 网站、SharePoint 网站以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的网站总数。</span><span class="sxs-lookup"><span data-stu-id="27f8a-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="27f8a-117">100</span><span class="sxs-lookup"><span data-stu-id="27f8a-117">100</span></span>  <br/> |
  |<span data-ttu-id="27f8a-118">核心电子数据展示主页上显示的最大事例数，以及事例中"保留项、搜索"和"导出"选项卡上显示的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="27f8a-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="27f8a-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="27f8a-119"><sup>1</sup></span></span> |<span data-ttu-id="27f8a-120">1,000</span><span class="sxs-lookup"><span data-stu-id="27f8a-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="27f8a-121"><sup>1</sup> 若要查看超过 1，000 个事例、保留、搜索或导出的列表，可以使用相应的 Office 365 安全&合规性 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="27f8a-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="27f8a-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="27f8a-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="27f8a-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="27f8a-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="27f8a-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="27f8a-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="27f8a-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="27f8a-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="27f8a-126">有关与与核心电子数据展示案例相关的内容搜索和导出限制详细信息，请参阅内容搜索和 [核心电子数据展示的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="27f8a-126">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>