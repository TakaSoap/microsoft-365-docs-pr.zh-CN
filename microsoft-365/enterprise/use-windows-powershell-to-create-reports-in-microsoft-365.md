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
description: 摘要：使用 PowerShell for Microsoft 365创建无法通过管理中心Microsoft 365的报告。
ms.openlocfilehash: dc183ae8a315bf788befc85474d0647802ac91ee
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222775"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="fe3da-103">使用 PowerShell 创建 Microsoft 365 报告</span><span class="sxs-lookup"><span data-stu-id="fe3da-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="fe3da-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="fe3da-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fe3da-105">管理中心提供了许多不同的Microsoft 365报告。</span><span class="sxs-lookup"><span data-stu-id="fe3da-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fe3da-106">但是这些报告仅提供太多信息，有时你还需要更多信息。</span><span class="sxs-lookup"><span data-stu-id="fe3da-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="fe3da-107">这就是需要 PowerShell 进行Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="fe3da-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="fe3da-108">这些文章介绍如何使用 PowerShell for Microsoft 365从你的租户Microsoft 365信息：</span><span class="sxs-lookup"><span data-stu-id="fe3da-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="fe3da-109">开始使用 PowerShell 进行报告，Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="fe3da-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="fe3da-110">为什么需要使用 PowerShell for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe3da-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="fe3da-111">用户帐户和许可证报告：</span><span class="sxs-lookup"><span data-stu-id="fe3da-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="fe3da-112">使用 PowerShell Microsoft 365许可证和服务</span><span class="sxs-lookup"><span data-stu-id="fe3da-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="fe3da-113">使用 PowerShell Microsoft 365许可和未授权的用户</span><span class="sxs-lookup"><span data-stu-id="fe3da-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="fe3da-114">使用 PowerShell Microsoft 365帐户许可证和服务详细信息</span><span class="sxs-lookup"><span data-stu-id="fe3da-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="fe3da-115">使用 PowerShell Microsoft 365用户帐户</span><span class="sxs-lookup"><span data-stu-id="fe3da-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="fe3da-116">SharePoint Online 报告：</span><span class="sxs-lookup"><span data-stu-id="fe3da-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="fe3da-117">SharePoint Online 命令行管理程序入门</span><span class="sxs-lookup"><span data-stu-id="fe3da-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="fe3da-118">Get-SPOSiteGroup - 获取指定网站集上的所有组</span><span class="sxs-lookup"><span data-stu-id="fe3da-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="fe3da-119">Exchange Online 报告：</span><span class="sxs-lookup"><span data-stu-id="fe3da-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="fe3da-120">使用 Exchange Online PowerShell 显示邮箱</span><span class="sxs-lookup"><span data-stu-id="fe3da-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="fe3da-121">相关文章l</span><span class="sxs-lookup"><span data-stu-id="fe3da-121">Related articlesl</span></span>

[<span data-ttu-id="fe3da-122">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe3da-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fe3da-123">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="fe3da-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fe3da-124">使用 PowerShell SharePoint管理服务</span><span class="sxs-lookup"><span data-stu-id="fe3da-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fe3da-125">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="fe3da-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
