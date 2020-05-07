---
title: 允许成员作为组发送或代表组发送
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: 了解如何允许成员以 Microsoft 365 组的形式发送电子邮件，或代表 Microsoft 365 组发送电子邮件。
ms.openlocfilehash: ce4527321468ee01864177fc1a607fab6a474481
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049383"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="462ff-103">允许成员作为组发送或代表组发送</span><span class="sxs-lookup"><span data-stu-id="462ff-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="462ff-104">已被授予 "**代理发送**" 或 **"代表发送"** 权限的 Microsoft 365 组的成员可以作为组或代表组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="462ff-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="462ff-105">本主题介绍管理员如何设置这些权限。</span><span class="sxs-lookup"><span data-stu-id="462ff-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="462ff-106">例如，如果 Megan Bowen 是 Microsoft 365 的**培训**组的一部分，并且对该组具有 "**代理发送**" 权限，则如果她将电子邮件作为组发送，则它看起来就像是电子邮件发送的 "**培训**组"。</span><span class="sxs-lookup"><span data-stu-id="462ff-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="462ff-107">"**代表发送**" 权限允许用户代表 Microsoft 365 组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="462ff-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="462ff-108">例如，如果 Alex Wilber 是**市场营销**Microsoft 365 组的一部分，并且拥有 "**代表发送**" 权限并将电子邮件作为组发送，则电子邮件看起来好像是由**Alex Wilber 代表行销**发送的。</span><span class="sxs-lookup"><span data-stu-id="462ff-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="462ff-109">您可以为给定用户配置 "**代理发送**" 或 **"代表发送**"，但不能同时配置两者。</span><span class="sxs-lookup"><span data-stu-id="462ff-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="462ff-110">如果同时配置两者，则默认为 "**代理发送**"。</span><span class="sxs-lookup"><span data-stu-id="462ff-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="462ff-111">请参阅[通过或代表 Microsoft 365 组发送电子邮件](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)，了解如何使用 Outlook 和 Web 上的 outlook 从组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="462ff-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="462ff-112">允许成员以组的形式发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="462ff-112">Allow members to send email as a group</span></span>

<span data-ttu-id="462ff-113">本节介绍如何在 Exchange Online 中允许用户以组身份在[exchange 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104)（EAC）中发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="462ff-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="462ff-114">在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>中，转到 "**收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="462ff-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="462ff-115">选择要允许用户以](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)其身份发送的组上的 "**编辑**![编辑组" 图标。  </span><span class="sxs-lookup"><span data-stu-id="462ff-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="462ff-116">选择 "**组委派**"。</span><span class="sxs-lookup"><span data-stu-id="462ff-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="462ff-117">在 "**代理发送**" 部分中， **+** 选择用于添加要作为组发送的用户的符号。</span><span class="sxs-lookup"><span data-stu-id="462ff-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![选择加号以添加要作为 Microsoft 365 组发送的用户。](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="462ff-119">键入从列表中搜索或选取用户。</span><span class="sxs-lookup"><span data-stu-id="462ff-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="462ff-120">选择 **"确定"** ，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="462ff-120">Select **OK** and **Save**.</span></span>
    
    ![从列表中搜索或选取用户的类型](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="462ff-122">允许成员代表组发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="462ff-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="462ff-123">本节介绍如何在 Exchange Online 中允许用户代表组在 Exchange 管理中心（EAC）中发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="462ff-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="462ff-124">在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>中，转到 "**收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="462ff-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="462ff-125">在要允许用户发送](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)的组中选择 "**编辑** ![编辑组" 图标。</span><span class="sxs-lookup"><span data-stu-id="462ff-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="462ff-126">选择 "**组委派**"。</span><span class="sxs-lookup"><span data-stu-id="462ff-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="462ff-127">在 "代表发送" 部分中，选择**+** 用于添加要作为组发送的用户的符号。</span><span class="sxs-lookup"><span data-stu-id="462ff-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![选择加号以添加要作为 Microsoft 365 组发送的用户。](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="462ff-129">键入从列表中搜索或选取用户。</span><span class="sxs-lookup"><span data-stu-id="462ff-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="462ff-130">选择 **"确定"** ，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="462ff-130">Select **OK** and **Save**.</span></span>
    
    ![从列表中搜索或选取用户的类型](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="462ff-132">相关文章</span><span class="sxs-lookup"><span data-stu-id="462ff-132">Related articles</span></span>

[<span data-ttu-id="462ff-133">了解有关 Microsoft 365 组的详细信息</span><span class="sxs-lookup"><span data-stu-id="462ff-133">Learn more about Microsoft 365 groups</span></span>](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="462ff-134">外接 Add-recipientpermission</span><span class="sxs-lookup"><span data-stu-id="462ff-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="462ff-135">Remove-unifiedgroup</span><span class="sxs-lookup"><span data-stu-id="462ff-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
