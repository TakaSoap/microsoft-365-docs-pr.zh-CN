---
title: 为组织配置待筛选邮件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: '了解如何使用 PowerShell 为组织中所有用户或特定用户启用或禁用待筛选Exchange功能。 '
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915898"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="3e5fc-103">为组织配置待筛选邮件</span><span class="sxs-lookup"><span data-stu-id="3e5fc-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="3e5fc-104">[重点收件箱](../setup/configure-focused-inbox.md) 将替换待筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="3e5fc-105">了解更多信息 [：更新重点收件箱和待筛选邮件计划](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="3e5fc-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="3e5fc-106">作为管理员，您可能必须管理待筛选邮件功能Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="3e5fc-107">若要为组织的用户打开/关闭待筛选邮件功能，必须使用 Exchange PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="3e5fc-108"> (个人可以使用以下说明打开/关闭它：关闭[/打开](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)待筛选邮件Outlook。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="3e5fc-109">请参阅将[PowerShell](/powershell/exchange/exchange-online-powershell)与 Exchange Online 一连接 Exchange Online [PowerShell，](/powershell/exchange/connect-to-exchange-online-powershell)详细了解如何Exchange PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="3e5fc-110">您需要具有至少具有 Exchange 服务管理员角色且能够使用 PowerShell Exchange Online帐户。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="3e5fc-111">使用 PowerShell 打开待筛选Exchange功能</span><span class="sxs-lookup"><span data-stu-id="3e5fc-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="3e5fc-112">可以通过运行 [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet 手动为邮箱启用待筛选邮件功能。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="3e5fc-113">您还可以通过运行 [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet 查看组织中邮箱的待筛选邮件设置。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="3e5fc-114">为名为 Allie Bellew 的单个用户打开待筛选邮件功能</span><span class="sxs-lookup"><span data-stu-id="3e5fc-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="3e5fc-115">使用 PowerShell Exchange待筛选邮件功能</span><span class="sxs-lookup"><span data-stu-id="3e5fc-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="3e5fc-116">可以通过运行 [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet 手动禁用邮箱的待筛选邮件功能。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet.</span></span> <span data-ttu-id="3e5fc-117">您还可以通过运行[Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet 查看组织中邮箱的待筛选邮件设置。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="3e5fc-118">关闭名为 Allie Bellew 的单个用户的待筛选邮件功能：</span><span class="sxs-lookup"><span data-stu-id="3e5fc-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="3e5fc-119">如果使用 PowerShell 批量创建用户，则需要针对每个用户的邮箱运行 [Set-Clutter](/powershell/module/exchange/set-clutter) 来管理待筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="3e5fc-120">何时对 Web 上的用户显示待筛选邮件Outlook开关？</span><span class="sxs-lookup"><span data-stu-id="3e5fc-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="3e5fc-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="3e5fc-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="3e5fc-122">作为管理员，您可以使用 PowerShell 重新启用待筛选邮件Exchange功能。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="3e5fc-123">完成此操作后，重点收件箱将关闭，待筛选邮件功能将再次处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3e5fc-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="3e5fc-124">**如果你将 Web 上的Outlook订阅一Microsoft 365 商业高级版：**</span><span class="sxs-lookup"><span data-stu-id="3e5fc-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="3e5fc-125">如果用户当前已启用待筛选邮件功能：</span><span class="sxs-lookup"><span data-stu-id="3e5fc-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="3e5fc-126">将显示待筛选邮件设置</span><span class="sxs-lookup"><span data-stu-id="3e5fc-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="3e5fc-127">如果用户当前已启用重点收件箱：</span><span class="sxs-lookup"><span data-stu-id="3e5fc-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="3e5fc-128">不会显示待筛选邮件设置</span><span class="sxs-lookup"><span data-stu-id="3e5fc-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="3e5fc-129">如果"待筛选邮件"或"重点收件箱"均未启用：</span><span class="sxs-lookup"><span data-stu-id="3e5fc-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="3e5fc-130">待筛选邮件和重点收件箱均显示为用户邮件邮箱中的设置</span><span class="sxs-lookup"><span data-stu-id="3e5fc-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="3e5fc-131">**如果你使用的是 Outlook.com：**</span><span class="sxs-lookup"><span data-stu-id="3e5fc-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="3e5fc-132">如果用户当前已启用待筛选邮件功能：</span><span class="sxs-lookup"><span data-stu-id="3e5fc-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="3e5fc-133">将显示待筛选邮件设置</span><span class="sxs-lookup"><span data-stu-id="3e5fc-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="3e5fc-134">如果用户当前已启用重点收件箱：</span><span class="sxs-lookup"><span data-stu-id="3e5fc-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="3e5fc-135">不会显示待筛选邮件设置</span><span class="sxs-lookup"><span data-stu-id="3e5fc-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="3e5fc-136">如果"待筛选邮件"或"重点收件箱"均未启用：</span><span class="sxs-lookup"><span data-stu-id="3e5fc-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="3e5fc-137">待筛选邮件和重点收件箱均显示为用户邮件邮箱中的设置</span><span class="sxs-lookup"><span data-stu-id="3e5fc-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="3e5fc-138">如果用户在过去某一时间点启用重点收件箱：</span><span class="sxs-lookup"><span data-stu-id="3e5fc-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="3e5fc-139">永远不会显示待筛选邮件设置</span><span class="sxs-lookup"><span data-stu-id="3e5fc-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="3e5fc-140">否则，</span><span class="sxs-lookup"><span data-stu-id="3e5fc-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="3e5fc-141">将显示待筛选邮件设置</span><span class="sxs-lookup"><span data-stu-id="3e5fc-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="3e5fc-142">相关文章</span><span class="sxs-lookup"><span data-stu-id="3e5fc-142">Related articles</span></span>
<span data-ttu-id="3e5fc-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="3e5fc-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="3e5fc-144">使用待筛选邮件对邮件中的低优先级Outlook</span><span class="sxs-lookup"><span data-stu-id="3e5fc-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="3e5fc-145">使用待筛选邮件对 OWA 中的低优先级邮件进行排序</span><span class="sxs-lookup"><span data-stu-id="3e5fc-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="3e5fc-146">关闭待筛选邮件Outlook</span><span class="sxs-lookup"><span data-stu-id="3e5fc-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
