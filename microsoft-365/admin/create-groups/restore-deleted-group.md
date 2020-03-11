---
title: 还原已删除的 Office 365 组
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 了解如何还原已删除的 Office 365 组。
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583159"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="63b8b-103">还原已删除的 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="63b8b-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="63b8b-104">如果已删除某个组，默认情况下它将保留30天。</span><span class="sxs-lookup"><span data-stu-id="63b8b-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="63b8b-105">这30天的期限被视为 "软删除"，因为您仍可以还原组。</span><span class="sxs-lookup"><span data-stu-id="63b8b-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="63b8b-106">30天后，该组及其关联的内容将被永久删除且无法还原。</span><span class="sxs-lookup"><span data-stu-id="63b8b-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="63b8b-107">还原组时，还可还原以下内容：</span><span class="sxs-lookup"><span data-stu-id="63b8b-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="63b8b-108">Azure Active Directory （AD） Office 365 组对象、属性和成员。</span><span class="sxs-lookup"><span data-stu-id="63b8b-108">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="63b8b-109">组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="63b8b-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="63b8b-110">Exchange Online 共享的收件箱和日历。</span><span class="sxs-lookup"><span data-stu-id="63b8b-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="63b8b-111">SharePoint Online 团队网站和文件。</span><span class="sxs-lookup"><span data-stu-id="63b8b-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="63b8b-112">OneNote 笔记本</span><span class="sxs-lookup"><span data-stu-id="63b8b-112">OneNote notebook</span></span>
    
- <span data-ttu-id="63b8b-113">Planner</span><span class="sxs-lookup"><span data-stu-id="63b8b-113">Planner</span></span>
    
- <span data-ttu-id="63b8b-114">Teams</span><span class="sxs-lookup"><span data-stu-id="63b8b-114">Teams</span></span>

- <span data-ttu-id="63b8b-115">Yammer 组和组内容（如果已从 Yammer 创建了 Office 365 组）</span><span class="sxs-lookup"><span data-stu-id="63b8b-115">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="63b8b-116">使用 Outlook 还原您拥有的组</span><span class="sxs-lookup"><span data-stu-id="63b8b-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="63b8b-117">如果您是 Office 365 组的所有者，则可以通过执行以下步骤在 Outlook 中自行还原组：</span><span class="sxs-lookup"><span data-stu-id="63b8b-117">If you are the owner of an Office 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="63b8b-118">在 "[已删除的组" 页](https://outlook.office.com/people/group/deleted)上，选择 "**组**" 节点下的 "**管理组**" 选项，然后选择 "**已删除**"。</span><span class="sxs-lookup"><span data-stu-id="63b8b-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="63b8b-119">单击要还原的组旁边的 "**还原**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="63b8b-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="63b8b-120">如果此处未显示已删除的组，请与管理员联系。</span><span class="sxs-lookup"><span data-stu-id="63b8b-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="63b8b-121">在 Microsoft 365 管理中心中还原组</span><span class="sxs-lookup"><span data-stu-id="63b8b-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="63b8b-122">如果您是全局管理员或组管理员，则可以在 Microsoft 365 管理中心中还原已删除的组：</span><span class="sxs-lookup"><span data-stu-id="63b8b-122">If you are a global administrator or a groups admin, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="63b8b-123">转到位于 [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com) 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="63b8b-123">Go to the admin center at [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="63b8b-124">展开 "**组**"，然后单击 "**已删除组**"。</span><span class="sxs-lookup"><span data-stu-id="63b8b-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="63b8b-125">选择要还原的组，然后单击 "**还原组**"。</span><span class="sxs-lookup"><span data-stu-id="63b8b-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="63b8b-126">永久删除 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="63b8b-126">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="63b8b-127">有时，您可能希望永久清除组，而无需等待30天软删除期过期。</span><span class="sxs-lookup"><span data-stu-id="63b8b-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="63b8b-128">若要执行此操作，启动 PowerShell 并运行此命令，获取组的对象 ID：</span><span class="sxs-lookup"><span data-stu-id="63b8b-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="63b8b-129">记下要永久删除的一个或几个组的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="63b8b-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="63b8b-130">清除组后可永久删除该组及其数据。</span><span class="sxs-lookup"><span data-stu-id="63b8b-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="63b8b-131">若要清除组，请在 PowerShell 中运行此命令：</span><span class="sxs-lookup"><span data-stu-id="63b8b-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="63b8b-p103">若要确认是否成功清除该组，请再次运行  *Get-AzureADMSDeletedGroup*  cmdlet 以确认该组不再出现在软删除的组列表中。某些情况下，要永久删除该组及其所有数据可能需要长达 24 小时。</span><span class="sxs-lookup"><span data-stu-id="63b8b-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="63b8b-134">对 Office 365 组有疑问？</span><span class="sxs-lookup"><span data-stu-id="63b8b-134">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="63b8b-135">访问[Microsoft 技术社区](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)以发布问题并参与有关 Office 365 组的对话。</span><span class="sxs-lookup"><span data-stu-id="63b8b-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="63b8b-136">相关文章</span><span class="sxs-lookup"><span data-stu-id="63b8b-136">Related articles</span></span>

[<span data-ttu-id="63b8b-137">使用 PowerShell 管理 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="63b8b-137">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="63b8b-138">使用 Remove-UnifiedGroup cmdlet 删除组</span><span class="sxs-lookup"><span data-stu-id="63b8b-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="63b8b-139">管理连接了组的团队网站设置</span><span class="sxs-lookup"><span data-stu-id="63b8b-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="63b8b-140">在 Outlook 中删除组</span><span class="sxs-lookup"><span data-stu-id="63b8b-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
