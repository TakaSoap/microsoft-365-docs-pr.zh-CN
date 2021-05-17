---
title: 还原已删除的Microsoft 365组
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: 了解如何还原已删除的Microsoft 365组。
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910542"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="e5ade-103">还原已删除的Microsoft 365组</span><span class="sxs-lookup"><span data-stu-id="e5ade-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="e5ade-104">如果已删除某个组，默认情况下该组将保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="e5ade-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="e5ade-105">此 30 天期限被视为"软删除"，因为您仍可以还原组。</span><span class="sxs-lookup"><span data-stu-id="e5ade-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="e5ade-106">30 天后，该组及其关联内容将永久删除且无法还原。</span><span class="sxs-lookup"><span data-stu-id="e5ade-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="e5ade-107">还原组时，还可还原以下内容：</span><span class="sxs-lookup"><span data-stu-id="e5ade-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="e5ade-108">Azure Active Directory (组) Microsoft 365、属性和成员创建 AD。</span><span class="sxs-lookup"><span data-stu-id="e5ade-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="e5ade-109">组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e5ade-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="e5ade-110">Exchange Online共享收件箱和日历。</span><span class="sxs-lookup"><span data-stu-id="e5ade-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="e5ade-111">SharePoint联机团队网站和文件。</span><span class="sxs-lookup"><span data-stu-id="e5ade-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="e5ade-112">OneNote 笔记本</span><span class="sxs-lookup"><span data-stu-id="e5ade-112">OneNote notebook</span></span>
    
- <span data-ttu-id="e5ade-113">Planner</span><span class="sxs-lookup"><span data-stu-id="e5ade-113">Planner</span></span>
    
- <span data-ttu-id="e5ade-114">Teams</span><span class="sxs-lookup"><span data-stu-id="e5ade-114">Teams</span></span>

- <span data-ttu-id="e5ade-115">Yammer组和组 (如果Microsoft 365组是Yammer) </span><span class="sxs-lookup"><span data-stu-id="e5ade-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="e5ade-116">本文介绍仅还原Microsoft 365组。</span><span class="sxs-lookup"><span data-stu-id="e5ade-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="e5ade-117">所有其他组在删除后无法还原。</span><span class="sxs-lookup"><span data-stu-id="e5ade-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="e5ade-118">还原组</span><span class="sxs-lookup"><span data-stu-id="e5ade-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="e5ade-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="e5ade-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="e5ade-120">如果你是组的所有者，Microsoft 365以下步骤在 Web 上的Outlook中自己还原组：</span><span class="sxs-lookup"><span data-stu-id="e5ade-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="e5ade-121">在"[已删除的组"页上](https://outlook.office.com/people/group/deleted)**，选择"** 组"节点下的"管理组"选项，然后选择"**已删除"。**</span><span class="sxs-lookup"><span data-stu-id="e5ade-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="e5ade-122">单击要 **还原** 的组旁边的"还原"选项卡。</span><span class="sxs-lookup"><span data-stu-id="e5ade-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="e5ade-123">如果此处未显示已删除的组，请与管理员联系。</span><span class="sxs-lookup"><span data-stu-id="e5ade-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="e5ade-124">管理中心</span><span class="sxs-lookup"><span data-stu-id="e5ade-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="e5ade-125">如果你是全局管理员或组管理员，可以在管理中心还原Microsoft 365组：</span><span class="sxs-lookup"><span data-stu-id="e5ade-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="e5ade-126">转到[管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e5ade-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="e5ade-127">展开 **"组**"，然后单击"**已删除组"。**</span><span class="sxs-lookup"><span data-stu-id="e5ade-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="e5ade-128">选择要还原的组，然后单击"还原 **组"。**</span><span class="sxs-lookup"><span data-stu-id="e5ade-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="e5ade-129">在某些情况下，可能需要 24 小时才能还原组及其所有数据。</span><span class="sxs-lookup"><span data-stu-id="e5ade-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="e5ade-130">对组Microsoft 365问题？</span><span class="sxs-lookup"><span data-stu-id="e5ade-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="e5ade-131">请访问[Microsoft 技术Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)发布问题并参与有关用户Microsoft 365对话。</span><span class="sxs-lookup"><span data-stu-id="e5ade-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="e5ade-132">相关文章</span><span class="sxs-lookup"><span data-stu-id="e5ade-132">Related articles</span></span>

[<span data-ttu-id="e5ade-133">使用 PowerShell Microsoft 365组</span><span class="sxs-lookup"><span data-stu-id="e5ade-133">Manage Microsoft 365 Groups with PowerShell</span></span>](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[<span data-ttu-id="e5ade-134">使用 Remove-UnifiedGroup cmdlet 删除组</span><span class="sxs-lookup"><span data-stu-id="e5ade-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](/powershell/module/exchange/remove-unifiedgroup)
  
[<span data-ttu-id="e5ade-135">管理连接了组的团队网站设置</span><span class="sxs-lookup"><span data-stu-id="e5ade-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="e5ade-136">在 Outlook 中删除组</span><span class="sxs-lookup"><span data-stu-id="e5ade-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)