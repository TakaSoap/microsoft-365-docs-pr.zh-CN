---
title: 从共享邮箱删除许可证
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: '从共享邮箱中删除许可证以将其分配给其他用户。 '
ms.openlocfilehash: 1acd549936212db7f722355ed1f2518ff6bbac18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915682"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="b9689-103">从共享邮箱中删除许可证</span><span class="sxs-lookup"><span data-stu-id="b9689-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b9689-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="b9689-104">The admin center is changing.</span></span> <span data-ttu-id="b9689-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="b9689-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b9689-106">共享邮箱通常不需要许可证。</span><span class="sxs-lookup"><span data-stu-id="b9689-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="b9689-107">按照以下说明从共享邮箱中删除许可证，以便你可以将其分配给用户或返回许可证，以便无需为不需要的许可证付费。</span><span class="sxs-lookup"><span data-stu-id="b9689-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="b9689-108">在下列情况下需要许可证：</span><span class="sxs-lookup"><span data-stu-id="b9689-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="b9689-109">共享邮箱使用的存储空间超过 50 GB。</span><span class="sxs-lookup"><span data-stu-id="b9689-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="b9689-110">共享邮箱使用就地存档。</span><span class="sxs-lookup"><span data-stu-id="b9689-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="b9689-111">共享邮箱置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="b9689-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="b9689-112">共享邮箱分配有 Microsoft Defender 许可证。</span><span class="sxs-lookup"><span data-stu-id="b9689-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="b9689-113">删除许可证</span><span class="sxs-lookup"><span data-stu-id="b9689-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b9689-114">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="b9689-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b9689-115">您需要从"活动用户"页中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="b9689-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b9689-116">无法从"共享邮箱"页面删除许可证，因为许可证是用户设置。</span><span class="sxs-lookup"><span data-stu-id="b9689-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="b9689-117">选择共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="b9689-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="b9689-118">在" **许可证和应用"** 选项卡中，展开 **"许可证** "并取消选中要删除的许可证的框。</span><span class="sxs-lookup"><span data-stu-id="b9689-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="b9689-119">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="b9689-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="b9689-120">返回到"**活动用户"** 页面时，共享邮箱的状态将为 **"未授权"。**</span><span class="sxs-lookup"><span data-stu-id="b9689-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b9689-121">你仍然支付许可证费用。</span><span class="sxs-lookup"><span data-stu-id="b9689-121">You're still paying for the license.</span></span> <span data-ttu-id="b9689-122">若要停止付费， [请从订阅中删除许可证](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="b9689-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="b9689-123">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="b9689-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9689-124">您需要从"活动用户"页中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="b9689-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b9689-125">无法从"共享邮箱"页面删除许可证，因为许可证是用户设置。</span><span class="sxs-lookup"><span data-stu-id="b9689-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="b9689-126">选择共享邮箱，**然后选择"产品** 许可证"旁边的 **"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="b9689-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="b9689-127">在"**产品许可证"** 页中，将要删除的许可证的开关设置为"关闭"。</span><span class="sxs-lookup"><span data-stu-id="b9689-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="b9689-128">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b9689-128">Select **Save**.</span></span>

5. <span data-ttu-id="b9689-129">返回到"**活动用户"** 页面时，共享邮箱的状态将为 **"未授权"。**</span><span class="sxs-lookup"><span data-stu-id="b9689-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b9689-130">你仍然支付许可证费用。</span><span class="sxs-lookup"><span data-stu-id="b9689-130">You're still paying for the license.</span></span> <span data-ttu-id="b9689-131">若要停止付费， [请从订阅中删除许可证](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="b9689-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b9689-132">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="b9689-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9689-133">您需要从"活动用户"页中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="b9689-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="b9689-134">无法从"共享邮箱"页面删除许可证，因为许可证是用户设置。</span><span class="sxs-lookup"><span data-stu-id="b9689-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="b9689-135">选择共享邮箱，**然后选择"产品** 许可证"旁边的 **"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="b9689-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="b9689-136">在"**产品许可证"** 页中，将要删除的许可证的开关设置为"关闭"。</span><span class="sxs-lookup"><span data-stu-id="b9689-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="b9689-137">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b9689-137">Select **Save**.</span></span>

5. <span data-ttu-id="b9689-138">返回到"**活动用户"** 页面时，共享邮箱的状态将为 **"未授权"。**</span><span class="sxs-lookup"><span data-stu-id="b9689-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="b9689-139">你仍然支付许可证费用。</span><span class="sxs-lookup"><span data-stu-id="b9689-139">You're still paying for the license.</span></span> <span data-ttu-id="b9689-140">若要停止付费， [请从订阅中删除许可证](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="b9689-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="b9689-141">相关文章</span><span class="sxs-lookup"><span data-stu-id="b9689-141">Related articles</span></span>

[<span data-ttu-id="b9689-142">关于共享邮箱</span><span class="sxs-lookup"><span data-stu-id="b9689-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="b9689-143">创建共享邮箱</span><span class="sxs-lookup"><span data-stu-id="b9689-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="b9689-144">配置共享邮箱</span><span class="sxs-lookup"><span data-stu-id="b9689-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="b9689-145">将用户邮箱转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="b9689-145">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="b9689-146">解决共享邮箱问题</span><span class="sxs-lookup"><span data-stu-id="b9689-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)