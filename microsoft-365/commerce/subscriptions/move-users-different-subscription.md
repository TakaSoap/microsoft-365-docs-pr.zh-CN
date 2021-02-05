---
title: 将用户移动到其他订阅
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何在订阅之间移动用户。
ms.date: 07/01/2020
ms.openlocfilehash: ec9385d10cc1799509c6f1d2fa88059eecf3bd8c
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114665"
---
# <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="37480-103">将用户移动到其他订阅</span><span class="sxs-lookup"><span data-stu-id="37480-103">Move users to a different subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="37480-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="37480-104">The admin center is changing.</span></span> <span data-ttu-id="37480-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="37480-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="37480-106">如果你有多个订阅，则让用户具有一个订阅的许可证，但希望将其移动到另一个订阅，可以将他们的现有许可证替换为其他许可证。</span><span class="sxs-lookup"><span data-stu-id="37480-106">If you have more than one subscription, have users with a license for one subscription, but want to move them to another subscription, you can replace their existing license with a different one.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="37480-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="37480-107">Before you begin</span></span>

<span data-ttu-id="37480-108">你必须是全局、许可证或用户管理员才能分配许可证。</span><span class="sxs-lookup"><span data-stu-id="37480-108">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="37480-109">有关详细信息，请参阅[关于 Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="37480-109">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span>

## <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="37480-110">将用户移动到其他订阅</span><span class="sxs-lookup"><span data-stu-id="37480-110">Move users to a different subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="37480-111">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="37480-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="37480-112">选择要替换其现有许可证的用户名称旁边的圆圈。</span><span class="sxs-lookup"><span data-stu-id="37480-112">Select the circles next to the names of the users that you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="37480-113">在顶部选择“**更多选项(...)**”，然后选择“**管理产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="37480-113">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="37480-114">在“**管理产品许可证**”窗格中，选择“**替换现有产品许可证分配**”\>“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="37480-114">In the **Manage product licenses** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="37480-115">将要分配给这些用户的许可证的开关切换到"打开"位置。</span><span class="sxs-lookup"><span data-stu-id="37480-115">Switch the toggle to the **On** position for the licenses that you want to assign to these users.\</span></span>
    <span data-ttu-id="37480-116">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="37480-116">You can limit which services are available to the users.</span></span> <span data-ttu-id="37480-117">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="37480-117">Switch the toggles to the **Off** position for the services that you don't want those users to have.</span></span> <span data-ttu-id="37480-118">这将删除所选用户之前的所有许可证分配。</span><span class="sxs-lookup"><span data-stu-id="37480-118">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="37480-119">在“**替换现有产品**”窗格底部，选择“**替换**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="37480-119">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="37480-120">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="37480-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="37480-121">选中要为其替换现有许可证的用户的姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="37480-121">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="37480-122">在“**批量操作**”窗格中，选择“**编辑产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="37480-122">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="37480-123">在“**分配产品**”窗格中，选择“**替换现有产品许可证分配**”\>“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="37480-123">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="37480-124">将要分配给这些用户的许可证的开关切换到"打开"位置。</span><span class="sxs-lookup"><span data-stu-id="37480-124">Switch the toggle to the **On** position for the licenses that you want to assign to these users.\</span></span>
    <span data-ttu-id="37480-125">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="37480-125">You can limit which services are available to the users.</span></span> <span data-ttu-id="37480-126">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="37480-126">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="37480-127">这将删除所选用户之前的所有许可证分配。</span><span class="sxs-lookup"><span data-stu-id="37480-127">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="37480-128">在“**替换现有产品**”窗格底部，选择“**替换**”\>“**关闭**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="37480-128">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="37480-129">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="37480-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="37480-130">选中要为其替换现有许可证的用户的姓名旁边的框。</span><span class="sxs-lookup"><span data-stu-id="37480-130">Select the boxes next to the names of the users you want to replace existing licenses for.</span></span>
3. <span data-ttu-id="37480-131">在“**批量操作**”窗格中，选择“**编辑产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="37480-131">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="37480-132">在“**分配产品**”窗格中，选择“**替换现有产品许可证分配**”\>“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="37480-132">In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="37480-133">将要分配给这些用户的许可证的开关切换到"打开"位置。</span><span class="sxs-lookup"><span data-stu-id="37480-133">Switch the toggle to the **On** position for the licenses that you want to assign to these users.\</span></span>
    <span data-ttu-id="37480-134">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="37480-134">You can limit which services are available to the users.</span></span> <span data-ttu-id="37480-135">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="37480-135">Switch the toggles to the **Off** position for the services that you don't want that users to have.</span></span> <span data-ttu-id="37480-136">这将删除所选用户之前的所有许可证分配。</span><span class="sxs-lookup"><span data-stu-id="37480-136">Any previous license assignments for the selected users are removed.</span></span>
6. <span data-ttu-id="37480-137">在“**替换现有产品**”窗格底部，选择“**替换**”\>“**关闭**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="37480-137">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="37480-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="37480-138">Next steps</span></span>

<span data-ttu-id="37480-139">如果你不打算将未使用的许可证重新分配给[](../../managed-desktop/get-started/assign-licenses.md)其他用户，请考虑从订阅中删除许可证，这样你[](../../commerce/licenses/buy-licenses.md)无需支付多于你需要的许可证。</span><span class="sxs-lookup"><span data-stu-id="37480-139">If you’re not going to [reassign the unused licenses to other users](../../managed-desktop/get-started/assign-licenses.md), consider [removing the licenses from your subscription](../../commerce/licenses/buy-licenses.md) so that you’re not paying for more licenses than you need.</span></span>

## <a name="related-content"></a><span data-ttu-id="37480-140">相关内容</span><span class="sxs-lookup"><span data-stu-id="37480-140">Related content</span></span>

<span data-ttu-id="37480-141">[向用户分配许可证 (](../../admin/manage/assign-licenses-to-users.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="37480-141">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="37480-142">[从订阅中删除许可证 (](../../commerce/licenses/remove-licenses-from-subscription.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="37480-142">[Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md) (article)</span></span>\
<span data-ttu-id="37480-143">[在文章 (](change-plans-manually.md) 更改) </span><span class="sxs-lookup"><span data-stu-id="37480-143">[Change plans manually](change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="37480-144">[了解 Microsoft 365](../licenses/subscriptions-and-licenses.md) 商业版中的订阅和 (文章) </span><span class="sxs-lookup"><span data-stu-id="37480-144">[Understand subscriptions and licenses in Microsoft 365 for business](../licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="37480-145">[购买其他 Microsoft 365 商业版订阅 (](../buy-another-subscription.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="37480-145">[Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) (article)</span></span>