---
title: 使用 PowerShell 创建 Microsoft 365 报告
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: 摘要：使用适用于 Microsoft 365 的 PowerShell 创建无法在 Microsoft 365 管理中心生成的报告。
ms.openlocfilehash: 10000f62b1d6a747cf0373623c6038b080666e1a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753974"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="f1f70-103">使用 PowerShell 创建 Microsoft 365 报告</span><span class="sxs-lookup"><span data-stu-id="f1f70-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="f1f70-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="f1f70-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f1f70-105">Microsoft 365 管理中心提供了许多不同的报告。</span><span class="sxs-lookup"><span data-stu-id="f1f70-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f1f70-106">但这些报告仅提供了如此多的信息，有时您需要更多的信息。</span><span class="sxs-lookup"><span data-stu-id="f1f70-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="f1f70-107">这是你需要适用于 Microsoft 365 的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f1f70-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="f1f70-108">这些文章介绍了如何使用适用于 Microsoft 365 的 PowerShell 从你的 Microsoft 365 租户获取信息：</span><span class="sxs-lookup"><span data-stu-id="f1f70-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="f1f70-109">使用 PowerShell for Microsoft 365 开始报告：</span><span class="sxs-lookup"><span data-stu-id="f1f70-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="f1f70-110">为什么需要使用 PowerShell for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1f70-110">Why you need to use PowerShell for Microsoft 365</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
    
- <span data-ttu-id="f1f70-111">用户帐户和许可证报告：</span><span class="sxs-lookup"><span data-stu-id="f1f70-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="f1f70-112">使用 PowerShell 查看 Microsoft 365 许可证和服务</span><span class="sxs-lookup"><span data-stu-id="f1f70-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="f1f70-113">使用 PowerShell 查看 Microsoft 365 许可和未经许可的用户</span><span class="sxs-lookup"><span data-stu-id="f1f70-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="f1f70-114">使用 PowerShell 查看 Microsoft 365 帐户许可证和服务详细信息</span><span class="sxs-lookup"><span data-stu-id="f1f70-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="f1f70-115">使用 PowerShell 查看 Microsoft 365 用户帐户</span><span class="sxs-lookup"><span data-stu-id="f1f70-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="f1f70-116">SharePoint Online 报告：</span><span class="sxs-lookup"><span data-stu-id="f1f70-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="f1f70-117">SharePoint Online 命令行管理程序入门</span><span class="sxs-lookup"><span data-stu-id="f1f70-117">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="f1f70-118">Remove-spositegroup-获取指定网站集上的所有组</span><span class="sxs-lookup"><span data-stu-id="f1f70-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="f1f70-119">Exchange Online 报告：</span><span class="sxs-lookup"><span data-stu-id="f1f70-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="f1f70-120">使用 Exchange Online PowerShell 显示邮箱</span><span class="sxs-lookup"><span data-stu-id="f1f70-120">Use Exchange Online PowerShell to display mailbox</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="f1f70-121">相关 articlesl</span><span class="sxs-lookup"><span data-stu-id="f1f70-121">Related articlesl</span></span>

[<span data-ttu-id="f1f70-122">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1f70-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f1f70-123">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="f1f70-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f1f70-124">使用 PowerShell 管理 SharePoint</span><span class="sxs-lookup"><span data-stu-id="f1f70-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f1f70-125">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="f1f70-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  