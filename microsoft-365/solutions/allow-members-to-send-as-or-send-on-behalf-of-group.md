---
title: 允许成员作为组发送或代表组发送
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 了解如何允许成员以 Microsoft 365 组的形式发送电子邮件，或代表 Microsoft 365 组发送电子邮件。
ms.openlocfilehash: 2abf0668411ccd08db5bbd8408605dcd0aa2d832
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613565"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="2e038-103">允许成员作为组发送或代表组发送</span><span class="sxs-lookup"><span data-stu-id="2e038-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="2e038-104">已被授予 " **代理发送** " 或 **"代表发送"** 权限的 Microsoft 365 组的成员可以作为组或代表组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2e038-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="2e038-105">本文介绍管理员如何设置这些权限。</span><span class="sxs-lookup"><span data-stu-id="2e038-105">This article explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="2e038-106">例如，如果 Megan Bowen 是 Microsoft 365 的 **培训** 组的一部分，并且对该组具有 " **代理发送** " 权限，则如果她将电子邮件作为组发送，则它看起来就像是电子邮件发送的 " **培训** 组"。</span><span class="sxs-lookup"><span data-stu-id="2e038-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="2e038-107">" **代表发送** " 权限允许用户代表 Microsoft 365 组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2e038-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="2e038-108">例如，如果 Alex Wilber 是 **市场营销** Microsoft 365 组的一部分，并且拥有 " **代表发送** " 权限并将电子邮件作为组发送，则电子邮件看起来好像是由 **Alex Wilber 代表行销** 发送的。</span><span class="sxs-lookup"><span data-stu-id="2e038-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e038-109">您可以为给定用户配置 " **代理发送** " 或 **"代表发送** "，但不能同时配置两者。</span><span class="sxs-lookup"><span data-stu-id="2e038-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="2e038-110">如果同时配置两者，则默认为 " **代理发送**"。</span><span class="sxs-lookup"><span data-stu-id="2e038-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="2e038-111">请参阅 [通过或代表 Microsoft 365 组发送电子邮件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) ，了解如何使用 Outlook 和 Web 上的 outlook 从组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2e038-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="2e038-112">允许成员以组的形式发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="2e038-112">Allow members to send email as a group</span></span>

<span data-ttu-id="2e038-113">本节介绍如何允许用户在 exchange Online 中 (EAC) 在 [exchange 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104) 中以组的形式发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2e038-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="2e038-114">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>中，转到 " **收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="2e038-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="2e038-115">在 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 要允许用户发送的组中选择 "编辑编辑组" 图标。  </span><span class="sxs-lookup"><span data-stu-id="2e038-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="2e038-116">选择 " **组委派**"。</span><span class="sxs-lookup"><span data-stu-id="2e038-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="2e038-117">在 " **代理发送** " 部分中，选择 **+** 用于添加要作为组发送的用户的符号。</span><span class="sxs-lookup"><span data-stu-id="2e038-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    !["代理发送" 对话框的屏幕截图](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="2e038-119">键入从列表中搜索或选取用户。</span><span class="sxs-lookup"><span data-stu-id="2e038-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="2e038-120">选择 **"确定"** ，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="2e038-120">Select **OK** and **Save**.</span></span>
    
    ![从列表中搜索或选取用户的类型](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="2e038-122">允许成员代表组发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="2e038-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="2e038-123">本节介绍如何允许用户代表 exchange Online 中的组在 Exchange 管理中心内发送电子邮件 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="2e038-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="2e038-124">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>中，转到 " **收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="2e038-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="2e038-125">在 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 要允许用户发送的组中选择 "编辑编辑组" 图标。</span><span class="sxs-lookup"><span data-stu-id="2e038-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="2e038-126">选择 " **组委派**"。</span><span class="sxs-lookup"><span data-stu-id="2e038-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="2e038-127">在 "代表发送" 部分中，选择 **+** 用于添加要作为组发送的用户的符号。</span><span class="sxs-lookup"><span data-stu-id="2e038-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    !["代表发送" 对话框的屏幕截图](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="2e038-129">键入从列表中搜索或选取用户。</span><span class="sxs-lookup"><span data-stu-id="2e038-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="2e038-130">选择 **"确定"** ，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="2e038-130">Select **OK** and **Save**.</span></span>
    
    ![从列表中搜索或选取用户的类型](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="2e038-132">相关文章</span><span class="sxs-lookup"><span data-stu-id="2e038-132">Related articles</span></span>

[<span data-ttu-id="2e038-133">协作治理规划分步</span><span class="sxs-lookup"><span data-stu-id="2e038-133">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="2e038-134">创建协作管理计划</span><span class="sxs-lookup"><span data-stu-id="2e038-134">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="2e038-135">了解有关 Microsoft 365 组的详细信息</span><span class="sxs-lookup"><span data-stu-id="2e038-135">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="2e038-136">外接 Add-recipientpermission</span><span class="sxs-lookup"><span data-stu-id="2e038-136">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="2e038-137">Remove-unifiedgroup</span><span class="sxs-lookup"><span data-stu-id="2e038-137">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
