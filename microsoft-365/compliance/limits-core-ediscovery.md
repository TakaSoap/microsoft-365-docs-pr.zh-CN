---
title: 核心电子数据展示案例的限制
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
description: 本文介绍 Microsoft 365 中核心电子数据展示案例的限制。
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423443"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="a18e8-103">核心电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="a18e8-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="a18e8-104">下表列出了核心电子数据展示事例的限制，以及与核心电子数据展示事例相关联的保留项。</span><span class="sxs-lookup"><span data-stu-id="a18e8-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="a18e8-105">有关核心电子数据展示详细信息，请参阅 [核心电子数据展示概述](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="a18e8-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="a18e8-106">限制说明</span><span class="sxs-lookup"><span data-stu-id="a18e8-106">Description of limit</span></span> | <span data-ttu-id="a18e8-107">限制</span><span class="sxs-lookup"><span data-stu-id="a18e8-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="a18e8-108">组织的最大事例数。</span><span class="sxs-lookup"><span data-stu-id="a18e8-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="a18e8-109">无限制</span><span class="sxs-lookup"><span data-stu-id="a18e8-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="a18e8-110">组织的最大案例保留数。</span><span class="sxs-lookup"><span data-stu-id="a18e8-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="a18e8-111">10,000</span><span class="sxs-lookup"><span data-stu-id="a18e8-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="a18e8-112">单个案例保留中的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="a18e8-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="a18e8-113">此限制包括用户邮箱总数以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a18e8-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="a18e8-114">1,000</span><span class="sxs-lookup"><span data-stu-id="a18e8-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="a18e8-115">单个案例保留中的最大网站数。</span><span class="sxs-lookup"><span data-stu-id="a18e8-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="a18e8-116">此限制包括 OneDrive for Business 网站、SharePoint 网站以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的网站的组合总数。</span><span class="sxs-lookup"><span data-stu-id="a18e8-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="a18e8-117">100</span><span class="sxs-lookup"><span data-stu-id="a18e8-117">100</span></span>  <br/> |
  |<span data-ttu-id="a18e8-118">核心电子数据展示主页上显示的最大事例数，以及事例中"保留、搜索"和"导出"选项卡上显示的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="a18e8-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="a18e8-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a18e8-119"><sup>1</sup></span></span> |<span data-ttu-id="a18e8-120">1,000</span><span class="sxs-lookup"><span data-stu-id="a18e8-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="a18e8-121"><sup>1</sup> 若要查看超过 1，000 个事例、保留、搜索或导出的列表，可以使用相应的 Office 365 安全与合规 PowerShell & Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a18e8-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="a18e8-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="a18e8-122">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="a18e8-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="a18e8-123">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="a18e8-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="a18e8-124">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="a18e8-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="a18e8-125">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="a18e8-126">有关与核心电子数据展示案例相关的内容搜索和导出限制详细信息，请参阅内容搜索和 [核心电子数据展示的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="a18e8-126">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>