---
title: 管理Office功能显示在新增功能中
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
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
description: 使用 Microsoft 365 管理中心中的"Office 中的新增功能"，确定当用户在 Windows > 上的 Office 应用 中选择"帮助""Office 应用 新增功能"时要显示或隐藏的 Microsoft 365 功能。 Office
ms.openlocfilehash: 319d5c0aabb0a61b01872acaeeb3ad362b72de37
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924831"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a><span data-ttu-id="0c04d-103">管理Office功能显示在新增功能中</span><span class="sxs-lookup"><span data-stu-id="0c04d-103">Manage which Office‎ features appear in What's New</span></span>

<span data-ttu-id="0c04d-104">当发布Office功能时，当用户在 Windows 上的应用中选择"帮助""新增功能"时，Office收到一条  >  Windows。</span><span class="sxs-lookup"><span data-stu-id="0c04d-104">When an important ‎Office‎ feature is released, users will get a message about it when they choose **Help** > **What's New** in their ‎‎Office‎‎ app on ‎Windows‎.</span></span>

<span data-ttu-id="0c04d-105">可以使用管理中心中的"Office中的新增功能"控制显示用户Microsoft 365消息。</span><span class="sxs-lookup"><span data-stu-id="0c04d-105">You can control which of these feature messages your users are shown by using the **What's new in Office** feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0c04d-106">如果您决定向用户隐藏功能消息，则始终可以稍后返回，并决定向用户显示它。</span><span class="sxs-lookup"><span data-stu-id="0c04d-106">If you decide to hide a feature message to your users, you can always come back later and decide to show it to them.</span></span>

> [!NOTE]
> - <span data-ttu-id="0c04d-107">向用户隐藏功能消息不会在功能策略中Office 应用。</span><span class="sxs-lookup"><span data-stu-id="0c04d-107">Hiding a feature message from your users doesn't disable the feature in the Office app.</span></span>
> - <span data-ttu-id="0c04d-108">必须分配有全局管理员角色或 Office 应用管理员角色，才能使用"Office **新增功能**。</span><span class="sxs-lookup"><span data-stu-id="0c04d-108">You must be assigned either the Global admin role or the Office apps admin role to use the **What's new in Office** feature.</span></span>

## <a name="show-or-hide-new-features"></a><span data-ttu-id="0c04d-109">显示或隐藏新功能</span><span class="sxs-lookup"><span data-stu-id="0c04d-109">Show or hide new features</span></span> 

1. <span data-ttu-id="0c04d-110">In the Microsoft 365 admin center， under **设置，** choose **Org settings**.</span><span class="sxs-lookup"><span data-stu-id="0c04d-110">In the Microsoft 365 admin center, under **Settings**, choose **Org settings**.</span></span>
2. <span data-ttu-id="0c04d-111">在"**服务"** 选项卡上，选择"服务 **中的新增Office"。**</span><span class="sxs-lookup"><span data-stu-id="0c04d-111">On the **Services** tab, choose **What's new in Office**.</span></span>
3. <span data-ttu-id="0c04d-112">单击功能名称时，将显示一个飞出面板，并包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="0c04d-112">When you click on the feature name, a fly-out panel appears with the following information:</span></span>
     - <span data-ttu-id="0c04d-113">功能简短说明。</span><span class="sxs-lookup"><span data-stu-id="0c04d-113">A short description of the feature.</span></span>
     - <span data-ttu-id="0c04d-114">指向文章的链接，以了解有关该功能的更多内容。</span><span class="sxs-lookup"><span data-stu-id="0c04d-114">A link to an article to learn more about the feature.</span></span>
     - <span data-ttu-id="0c04d-115">功能Office应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="0c04d-115">The Office applications that the feature appears in.</span></span>
     - <span data-ttu-id="0c04d-116">第一 (版本) 该功能可用于该频道。</span><span class="sxs-lookup"><span data-stu-id="0c04d-116">The first version (release) that the feature is available in for that channel.</span></span>
4. <span data-ttu-id="0c04d-117">选择 **"向用户隐藏"。**</span><span class="sxs-lookup"><span data-stu-id="0c04d-117">Choose **Hide from users**.</span></span> <span data-ttu-id="0c04d-118">或者，如果你之前隐藏该功能，请选择"**向用户显示"。**</span><span class="sxs-lookup"><span data-stu-id="0c04d-118">Or, if you previously hid the feature, choose **Show to users**.</span></span>

<span data-ttu-id="0c04d-119">还可以选择"管理哪些功能Office **功能** 显示在"新增功能"页上，**然后选择"隐藏**"或"显示 **"。**</span><span class="sxs-lookup"><span data-stu-id="0c04d-119">You can also select multiple features on the **Manage which ‎Office‎ features appear in What's New** page, and then choose either **Hide** or **Show**.</span></span>

> [!NOTE]
> - <span data-ttu-id="0c04d-120">如果某个功能在多个应用Office，将该功能设置为 **隐藏** 将隐藏所有这些应用中的功能Office消息。</span><span class="sxs-lookup"><span data-stu-id="0c04d-120">If a feature is available in multiple Office apps, setting the feature to **Hidden** hides the feature message in all of those Office apps.</span></span>
> - <span data-ttu-id="0c04d-121">默认情况下，所有功能消息都向用户显示。</span><span class="sxs-lookup"><span data-stu-id="0c04d-121">All feature messages are shown to users by default.</span></span> <span data-ttu-id="0c04d-122">这是所有功能的默认状态，只有选择隐藏或显示功能消息时，状态才发生更改。</span><span class="sxs-lookup"><span data-stu-id="0c04d-122">This is the default status for all features, and the status only changes if you have chosen to hide or show a feature message.</span></span>
> - <span data-ttu-id="0c04d-123">还可以从管理中心Office"管理中心"Microsoft 365 应用版"新增功能 [https://config.office.com](https://config.office.com) () 。</span><span class="sxs-lookup"><span data-stu-id="0c04d-123">You can also get to the **What's new in Office** feature from the Microsoft 365 Apps admin center ([https://config.office.com](https://config.office.com)).</span></span> <span data-ttu-id="0c04d-124">此功能位于自定义  >  **新增管理下**。</span><span class="sxs-lookup"><span data-stu-id="0c04d-124">The feature is found under **Customization** > **What's New Management**.</span></span>

## <a name="list-of-features"></a><span data-ttu-id="0c04d-125">功能列表</span><span class="sxs-lookup"><span data-stu-id="0c04d-125">List of features</span></span>

<span data-ttu-id="0c04d-126">可以筛选"管理哪些功能Office **功能显示在"新增功能"页上**。</span><span class="sxs-lookup"><span data-stu-id="0c04d-126">You can filter which features appear on the **Manage which ‎Office‎ features appear in What's New** page.</span></span> <span data-ttu-id="0c04d-127">可以按频道、应用程序或状态或它们的组合进行筛选。</span><span class="sxs-lookup"><span data-stu-id="0c04d-127">You can filter by channel, application, or status, or by some combination of them.</span></span>

<span data-ttu-id="0c04d-128">根据以下计划在页面上显示新功能：</span><span class="sxs-lookup"><span data-stu-id="0c04d-128">New features appear on the page based on the following schedule:</span></span>

|<span data-ttu-id="0c04d-129">频道</span><span class="sxs-lookup"><span data-stu-id="0c04d-129">Channel</span></span>|<span data-ttu-id="0c04d-130">日期</span><span class="sxs-lookup"><span data-stu-id="0c04d-130">Date</span></span>|<span data-ttu-id="0c04d-131">采取行动</span><span class="sxs-lookup"><span data-stu-id="0c04d-131">Take action</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0c04d-132">**Current**</span><span class="sxs-lookup"><span data-stu-id="0c04d-132">**Current**</span></span> <br/> |<span data-ttu-id="0c04d-133">当月 15 日</span><span class="sxs-lookup"><span data-stu-id="0c04d-133">15th of the month</span></span>  <br/> |<span data-ttu-id="0c04d-134">1 - 每月发布前的 3 周</span><span class="sxs-lookup"><span data-stu-id="0c04d-134">1 - 3 weeks before the monthly release</span></span> <br/> |
|<span data-ttu-id="0c04d-135">**月度企业版**</span><span class="sxs-lookup"><span data-stu-id="0c04d-135">**Monthly Enterprise**</span></span> <br/> |<span data-ttu-id="0c04d-136">当月的第一天</span><span class="sxs-lookup"><span data-stu-id="0c04d-136">First of the month</span></span>  <br/> |<span data-ttu-id="0c04d-137">在引入新功能的主要版本前两周</span><span class="sxs-lookup"><span data-stu-id="0c04d-137">Two weeks before the major release that brings new features</span></span> |
|<span data-ttu-id="0c04d-138">**半年预览Enterprise (预览)**</span><span class="sxs-lookup"><span data-stu-id="0c04d-138">**Semi-Annual Enterprise (Preview)**</span></span> <br/> |<span data-ttu-id="0c04d-139">9 月 1 日到 3 月 1 日</span><span class="sxs-lookup"><span data-stu-id="0c04d-139">Sept 1 and March 1</span></span> <br/> | <span data-ttu-id="0c04d-140">在引入新功能的主要版本前 2 周</span><span class="sxs-lookup"><span data-stu-id="0c04d-140">2 weeks before the major release that brings new features</span></span>|
|<span data-ttu-id="0c04d-141">**半年Enterprise**</span><span class="sxs-lookup"><span data-stu-id="0c04d-141">**Semi-Annual Enterprise**</span></span> <br/> |<span data-ttu-id="0c04d-142">1 月 1 日到 7 月 1 日</span><span class="sxs-lookup"><span data-stu-id="0c04d-142">Jan 1 and July 1</span></span> <br/> | <span data-ttu-id="0c04d-143">在引入新功能的主要版本前 2 周</span><span class="sxs-lookup"><span data-stu-id="0c04d-143">2 weeks before the major release that brings new features</span></span><br/> |

<span data-ttu-id="0c04d-144">有关何时向每个更新频道发布新版本的信息，请参阅更新历史记录Microsoft 365 应用版 ([按](/officeupdates/update-history-microsoft365-apps-by-date)日期) 。</span><span class="sxs-lookup"><span data-stu-id="0c04d-144">For more information about when new versions are released to each update channel, see [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date).</span></span>

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a><span data-ttu-id="0c04d-145">将"Office中的新增功能"卡片添加到管理中心主页</span><span class="sxs-lookup"><span data-stu-id="0c04d-145">Add the "What's new in Office" card to the admin center home page</span></span>

1. <span data-ttu-id="0c04d-146">在"Microsoft 365"页面上 **，选择页面** 顶部的"添加卡片"</span><span class="sxs-lookup"><span data-stu-id="0c04d-146">On the Microsoft 365 admin page, choose **Add card** on top of the page</span></span>
2. <span data-ttu-id="0c04d-147">找到 **"管理Office功能显示在"新增功能"** 中，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="0c04d-147">Locate **Manage which Office features appear in What's New** in the list and choose it.</span></span>
3. <span data-ttu-id="0c04d-148">卡片位于主页上后，可以选择"Office中的新增功能"来显示[或隐藏组织](#show-or-hide-new-features)的功能。</span><span class="sxs-lookup"><span data-stu-id="0c04d-148">Once the card is on your home page, you can choose **What's new in Office** to [show or hide the features](#show-or-hide-new-features) for your organization.</span></span>


## <a name="related-articles"></a><span data-ttu-id="0c04d-149">相关文章</span><span class="sxs-lookup"><span data-stu-id="0c04d-149">Related articles</span></span>

[<span data-ttu-id="0c04d-150">Office新增管理现已普遍可用</span><span class="sxs-lookup"><span data-stu-id="0c04d-150">Office What's New management is now generally available</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)