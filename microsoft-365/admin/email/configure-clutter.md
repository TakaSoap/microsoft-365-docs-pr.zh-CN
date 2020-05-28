---
title: 为您的组织配置邮件筛选
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
description: '了解如何使用 Exchange PowerShell 为组织中的所有用户或特定用户启用或禁用杂乱功能。 '
ms.openlocfilehash: 069cf7569ebb3654e979100291f6754693b24def
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400132"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="a0a17-103">为您的组织配置邮件筛选</span><span class="sxs-lookup"><span data-stu-id="a0a17-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="a0a17-104">[重点收件箱](../setup/configure-focused-inbox.md)将替换混乱。</span><span class="sxs-lookup"><span data-stu-id="a0a17-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="a0a17-105">了解详细信息：[更新重点收件箱和我们关于待筛选计划](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="a0a17-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="a0a17-106">作为管理员，您可能需要在 Microsoft 365 中管理邮件筛选功能。</span><span class="sxs-lookup"><span data-stu-id="a0a17-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="a0a17-107">若要为组织中的用户打开/关闭筛选功能，必须使用 Exchange PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a0a17-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="a0a17-108">（个人可以使用以下说明打开/关闭它：[关闭/打开 Outlook 中的杂乱功能](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)。）</span><span class="sxs-lookup"><span data-stu-id="a0a17-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="a0a17-109">请查看[使用 PowerShell With Exchange online](https://go.microsoft.com/fwlink/?LinkID=402831) ，并[连接到 Exchange online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) ，以了解有关使用 exchange PowerShell 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a0a17-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="a0a17-110">您需要拥有至少具有 Exchange 服务管理员角色的帐户，并且能够使用 PowerShell 连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="a0a17-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="a0a17-111">使用 Exchange PowerShell 打开杂乱</span><span class="sxs-lookup"><span data-stu-id="a0a17-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="a0a17-112">您可以通过运行 "[设置筛选](https://go.microsoft.com/fwlink/?LinkID=834446)" cmdlet 对邮箱手动启用筛选。</span><span class="sxs-lookup"><span data-stu-id="a0a17-112">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="a0a17-113">您还可以通过运行 "邮件[筛选](https://go.microsoft.com/fwlink/?LinkID=834759)" cmdlet 来查看组织中邮箱的杂乱设置。</span><span class="sxs-lookup"><span data-stu-id="a0a17-113">You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="a0a17-114">为名为 Allie Bellew 的单个用户打开杂乱的邮件</span><span class="sxs-lookup"><span data-stu-id="a0a17-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="a0a17-115">使用 Exchange PowerShell 禁用混乱</span><span class="sxs-lookup"><span data-stu-id="a0a17-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="a0a17-116">您可以通过运行 "[设置筛选](https://go.microsoft.com/fwlink/?LinkID=834446)" cmdlet 对邮箱手动禁用垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="a0a17-116">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet.</span></span> <span data-ttu-id="a0a17-117">您还可以通过运行 "邮件[筛选](https://go.microsoft.com/fwlink/?LinkID=834759)" cmdlet 来查看组织中邮箱的**杂乱**设置。</span><span class="sxs-lookup"><span data-stu-id="a0a17-117">You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="a0a17-118">对名为 Allie Bellew 的单个用户关闭筛选：</span><span class="sxs-lookup"><span data-stu-id="a0a17-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="a0a17-119">如果使用 PowerShell 批量创建用户，则需要对每个用户的邮箱运行[设置混乱](https://go.microsoft.com/fwlink/?LinkID=834446)，以管理杂乱。</span><span class="sxs-lookup"><span data-stu-id="a0a17-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="a0a17-120">何时对 web 上的 Outlook 中的用户显示 "杂乱" 开关？</span><span class="sxs-lookup"><span data-stu-id="a0a17-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="a0a17-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="a0a17-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="a0a17-122">作为管理员，你可以使用 Exchange PowerShell 重新启用筛选。</span><span class="sxs-lookup"><span data-stu-id="a0a17-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="a0a17-123">完成此操作后，将关闭重点收件箱，并再次激活杂乱的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="a0a17-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="a0a17-124">**如果您使用的是 Microsoft 365 商业高级订阅的 web 上的 Outlook：**</span><span class="sxs-lookup"><span data-stu-id="a0a17-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="a0a17-125">如果用户当前启用了邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="a0a17-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="a0a17-126">出现 "邮件" 设置</span><span class="sxs-lookup"><span data-stu-id="a0a17-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="a0a17-127">如果用户当前启用了重点收件箱：</span><span class="sxs-lookup"><span data-stu-id="a0a17-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="a0a17-128">杂乱设置不会显示</span><span class="sxs-lookup"><span data-stu-id="a0a17-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="a0a17-129">如果没有启用 "杂乱" 或 "重点收件箱"：</span><span class="sxs-lookup"><span data-stu-id="a0a17-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="a0a17-130">"杂乱" 和 "重点收件箱" 显示为用户的邮件设置中的选项</span><span class="sxs-lookup"><span data-stu-id="a0a17-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="a0a17-131">**如果您使用的是 Outlook.com：**</span><span class="sxs-lookup"><span data-stu-id="a0a17-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="a0a17-132">如果用户当前启用了邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="a0a17-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="a0a17-133">出现 "邮件" 设置</span><span class="sxs-lookup"><span data-stu-id="a0a17-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="a0a17-134">如果用户当前启用了重点收件箱：</span><span class="sxs-lookup"><span data-stu-id="a0a17-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="a0a17-135">杂乱设置不会显示</span><span class="sxs-lookup"><span data-stu-id="a0a17-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="a0a17-136">如果没有启用 "杂乱" 或 "重点收件箱"：</span><span class="sxs-lookup"><span data-stu-id="a0a17-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="a0a17-137">"杂乱" 和 "重点收件箱" 显示为用户的邮件设置中的选项</span><span class="sxs-lookup"><span data-stu-id="a0a17-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="a0a17-138">如果用户在过去某一点启用了重点收件箱：</span><span class="sxs-lookup"><span data-stu-id="a0a17-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="a0a17-139">垃圾邮件设置将永远不会出现</span><span class="sxs-lookup"><span data-stu-id="a0a17-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="a0a17-140">无权</span><span class="sxs-lookup"><span data-stu-id="a0a17-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="a0a17-141">将显示 "杂乱" 设置</span><span class="sxs-lookup"><span data-stu-id="a0a17-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="a0a17-142">相关文章</span><span class="sxs-lookup"><span data-stu-id="a0a17-142">Related articles</span></span>
<span data-ttu-id="a0a17-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="a0a17-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="a0a17-144">使用杂乱在 Outlook 中对低优先级邮件进行排序</span><span class="sxs-lookup"><span data-stu-id="a0a17-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/use-clutter-to-sort-low-priority-messages-in-outlook-7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="a0a17-145">使用杂乱在 OWA 中对低优先级邮件进行排序</span><span class="sxs-lookup"><span data-stu-id="a0a17-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="a0a17-146">关闭 Outlook 中的杂乱功能</span><span class="sxs-lookup"><span data-stu-id="a0a17-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

