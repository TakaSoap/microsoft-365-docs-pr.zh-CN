---
title: 在审核日志中搜索用户和管理员活动
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 审核日志是一个统一的审核日志。 为什么是统一的审核日志？ 由于组织订阅的大多数服务中的事件都记录在可以搜索的单个审核日志中。 这意味着您可以在这些服务中搜索用户和管理员活动：
ms.openlocfilehash: 95f5025e4831223c93251c7c22d1f43d44086d48
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625092"
---
# <a name="search-the-audit-log-for-user-and-admin-activity"></a><span data-ttu-id="ef631-106">在审核日志中搜索用户和管理员活动</span><span class="sxs-lookup"><span data-stu-id="ef631-106">Search the audit log for user and admin activity</span></span>

<span data-ttu-id="ef631-107">审核日志是一个统一的审核日志。</span><span class="sxs-lookup"><span data-stu-id="ef631-107">The audit log is a unified audit log.</span></span> <span data-ttu-id="ef631-108">为什么是统一的审核日志？</span><span class="sxs-lookup"><span data-stu-id="ef631-108">Why a unified audit log?</span></span> <span data-ttu-id="ef631-109">由于组织中的大多数服务所订阅的事件将记录在可以搜索的单个审核日志中。</span><span class="sxs-lookup"><span data-stu-id="ef631-109">Because events from most services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="ef631-110">这意味着您可以在这些服务中搜索用户和管理员活动：</span><span class="sxs-lookup"><span data-stu-id="ef631-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="ef631-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ef631-111">SharePoint</span></span>
- <span data-ttu-id="ef631-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="ef631-112">OneDrive</span></span>
- <span data-ttu-id="ef631-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="ef631-113">Exchange</span></span>
- <span data-ttu-id="ef631-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ef631-114">Azure Active Directory</span></span>
- <span data-ttu-id="ef631-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ef631-115">Microsoft Teams</span></span>
- <span data-ttu-id="ef631-116">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="ef631-116">eDiscovery</span></span>
- <span data-ttu-id="ef631-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="ef631-117">Power BI</span></span>
- <span data-ttu-id="ef631-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="ef631-118">Yammer</span></span>
- <span data-ttu-id="ef631-119">Sway</span><span class="sxs-lookup"><span data-stu-id="ef631-119">Sway</span></span>
- <span data-ttu-id="ef631-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="ef631-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="ef631-121">设置审核</span><span class="sxs-lookup"><span data-stu-id="ef631-121">Set up auditing</span></span>
  
<span data-ttu-id="ef631-122">在搜索审核日志之前，必须执行一些操作。</span><span class="sxs-lookup"><span data-stu-id="ef631-122">There's few things you have to do before you can search the audit log.</span></span>
  
- <span data-ttu-id="ef631-123">[打开审核日志搜索](turn-audit-log-search-on-or-off.md)以开始记录可搜索的事件</span><span class="sxs-lookup"><span data-stu-id="ef631-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="ef631-124">[启用邮箱审核](enable-mailbox-auditing.md)，以便您可以搜索与邮箱相关的事件;例如，当用户登录到其邮箱或清除其 "可恢复的项目" 文件夹中的项目时</span><span class="sxs-lookup"><span data-stu-id="ef631-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="ef631-125">搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="ef631-125">Search the audit log</span></span>
  
<span data-ttu-id="ef631-126">启用审核后，可以从多个 Microsoft 365 服务中搜索数百个不同类型的事件。</span><span class="sxs-lookup"><span data-stu-id="ef631-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Microsoft 365 services.</span></span>
  
- <span data-ttu-id="ef631-127">[在审核日志中搜索](search-the-audit-log-in-security-and-compliance.md)用户和管理员活动</span><span class="sxs-lookup"><span data-stu-id="ef631-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="ef631-128">了解搜索结果中包含的每个审核记录[的详细属性](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="ef631-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="ef631-129">搜索由管理员和合规经理执行的[与电子数据展示相关的活动](search-for-ediscovery-activities-in-the-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="ef631-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
