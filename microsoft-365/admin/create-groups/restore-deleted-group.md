---
title: 还原已删除的组
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 了解如何还原已删除的 Microsoft 365 组。
ms.openlocfilehash: 30e267a149bc18c2425d4ea38423b887116794c6
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681642"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="2ba46-103">还原已删除的组</span><span class="sxs-lookup"><span data-stu-id="2ba46-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="2ba46-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="2ba46-104">The admin center is changing.</span></span> <span data-ttu-id="2ba46-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="2ba46-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

> [!NOTE]
> <span data-ttu-id="2ba46-106">本文介绍仅还原 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="2ba46-106">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="2ba46-107">删除后，所有其他组都不能还原。</span><span class="sxs-lookup"><span data-stu-id="2ba46-107">All other groups cannot be restored once deleted.</span></span>

<span data-ttu-id="2ba46-108">如果已删除某个组，默认情况下它将保留30天。</span><span class="sxs-lookup"><span data-stu-id="2ba46-108">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="2ba46-109">这30天的期限被视为 "软删除"，因为您仍可以还原组。</span><span class="sxs-lookup"><span data-stu-id="2ba46-109">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="2ba46-110">30天后，该组及其关联的内容将被永久删除且无法还原。</span><span class="sxs-lookup"><span data-stu-id="2ba46-110">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="2ba46-111">还原组时，还可还原以下内容：</span><span class="sxs-lookup"><span data-stu-id="2ba46-111">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="2ba46-112">Azure Active Directory (AD) Microsoft 365 组对象、属性和成员。</span><span class="sxs-lookup"><span data-stu-id="2ba46-112">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="2ba46-113">组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2ba46-113">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="2ba46-114">Exchange Online 共享的收件箱和日历。</span><span class="sxs-lookup"><span data-stu-id="2ba46-114">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="2ba46-115">SharePoint Online 团队网站和文件。</span><span class="sxs-lookup"><span data-stu-id="2ba46-115">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="2ba46-116">OneNote 笔记本</span><span class="sxs-lookup"><span data-stu-id="2ba46-116">OneNote notebook</span></span>
    
- <span data-ttu-id="2ba46-117">Planner</span><span class="sxs-lookup"><span data-stu-id="2ba46-117">Planner</span></span>
    
- <span data-ttu-id="2ba46-118">Teams</span><span class="sxs-lookup"><span data-stu-id="2ba46-118">Teams</span></span>

- <span data-ttu-id="2ba46-119">Yammer group and group content (如果 Microsoft 365 组是从 Yammer 创建的) </span><span class="sxs-lookup"><span data-stu-id="2ba46-119">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="2ba46-120">使用 web 上的 Outlook 还原您拥有的组</span><span class="sxs-lookup"><span data-stu-id="2ba46-120">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="2ba46-121">如果你是 Microsoft 365 组的所有者，则可以通过执行以下步骤，在 web 上的 Outlook 中自行还原组：</span><span class="sxs-lookup"><span data-stu-id="2ba46-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="2ba46-122">在 "[已删除的组" 页](https://outlook.office.com/people/group/deleted)上，选择 "**组**" 节点下的 "**管理组**" 选项，然后选择 "**已删除**"。</span><span class="sxs-lookup"><span data-stu-id="2ba46-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="2ba46-123">单击要还原的组旁边的 " **还原** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2ba46-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="2ba46-124">如果此处未显示已删除的组，请与管理员联系。</span><span class="sxs-lookup"><span data-stu-id="2ba46-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2ba46-125">在 Microsoft 365 管理中心中还原组</span><span class="sxs-lookup"><span data-stu-id="2ba46-125">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="2ba46-126">如果您是全局管理员或组管理员，则可以在 Microsoft 365 管理中心中还原已删除的组：</span><span class="sxs-lookup"><span data-stu-id="2ba46-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="2ba46-127">转到[管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="2ba46-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="2ba46-128">展开 " **组**"，然后单击 " **已删除组**"。</span><span class="sxs-lookup"><span data-stu-id="2ba46-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="2ba46-129">选择要还原的组，然后单击 " **还原组**"。</span><span class="sxs-lookup"><span data-stu-id="2ba46-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="2ba46-130">在某些情况下，可能需要长达24小时才能还原组及其所有数据。</span><span class="sxs-lookup"><span data-stu-id="2ba46-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="2ba46-131">永久删除 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="2ba46-131">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="2ba46-132">有时，您可能希望永久清除组，而无需等待30天软删除期过期。</span><span class="sxs-lookup"><span data-stu-id="2ba46-132">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="2ba46-133">若要执行此操作，启动 PowerShell 并运行此命令，获取组的对象 ID：</span><span class="sxs-lookup"><span data-stu-id="2ba46-133">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="2ba46-134">记下要永久删除的一个或几个组的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="2ba46-134">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="2ba46-135">清除组后可永久删除该组及其数据。</span><span class="sxs-lookup"><span data-stu-id="2ba46-135">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="2ba46-136">若要清除组，请在 PowerShell 中运行此命令：</span><span class="sxs-lookup"><span data-stu-id="2ba46-136">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="2ba46-p105">若要确认是否成功清除该组，请再次运行  *Get-AzureADMSDeletedGroup*  cmdlet 以确认该组不再出现在软删除的组列表中。某些情况下，要永久删除该组及其所有数据可能需要长达 24 小时。</span><span class="sxs-lookup"><span data-stu-id="2ba46-p105">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="2ba46-139">遇到有关 Microsoft 365 组的问题？</span><span class="sxs-lookup"><span data-stu-id="2ba46-139">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="2ba46-140">访问 [Microsoft 技术社区](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) 以发布问题，并参与有关 Microsoft 365 组的对话。</span><span class="sxs-lookup"><span data-stu-id="2ba46-140">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="2ba46-141">相关文章</span><span class="sxs-lookup"><span data-stu-id="2ba46-141">Related articles</span></span>

[<span data-ttu-id="2ba46-142">使用 PowerShell 管理 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="2ba46-142">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="2ba46-143">使用 Remove-UnifiedGroup cmdlet 删除组</span><span class="sxs-lookup"><span data-stu-id="2ba46-143">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="2ba46-144">管理连接了组的团队网站设置</span><span class="sxs-lookup"><span data-stu-id="2ba46-144">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="2ba46-145">在 Outlook 中删除组</span><span class="sxs-lookup"><span data-stu-id="2ba46-145">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
