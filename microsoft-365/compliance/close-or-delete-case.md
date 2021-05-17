---
title: 关闭或删除事例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解在关闭或删除受调查案例支持的调查Advanced eDiscovery法律案件时会发生什么情况。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419058"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="c81cd-103">关闭或删除Advanced eDiscovery案例</span><span class="sxs-lookup"><span data-stu-id="c81cd-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="c81cd-104">完成案例支持的法律案件或调查Advanced eDiscovery，可以关闭或删除案例。</span><span class="sxs-lookup"><span data-stu-id="c81cd-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="c81cd-105">您还可以重新打开已关闭的案例。</span><span class="sxs-lookup"><span data-stu-id="c81cd-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="c81cd-106">关闭案例</span><span class="sxs-lookup"><span data-stu-id="c81cd-106">Close a case</span></span>

<span data-ttu-id="c81cd-107">下面是关闭事件案例时Advanced eDiscovery情况：</span><span class="sxs-lookup"><span data-stu-id="c81cd-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="c81cd-108">如果案例包含任何保留内容位置，这些保留将被关闭。</span><span class="sxs-lookup"><span data-stu-id="c81cd-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="c81cd-109">关闭保留后，称为延迟保留 (30 天的宽限期) 将应用于已保留的内容位置。</span><span class="sxs-lookup"><span data-stu-id="c81cd-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="c81cd-110">这有助于防止立即删除内容，并给予管理员搜索或恢复将在延迟保留期过期后永久删除的内容的机会。</span><span class="sxs-lookup"><span data-stu-id="c81cd-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="c81cd-111">有关详细信息，请参阅从电子数据展示保留 [中删除内容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="c81cd-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="c81cd-112">关闭案例仅关闭与该案例相关联的保留。</span><span class="sxs-lookup"><span data-stu-id="c81cd-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="c81cd-113">如果其他保留位于内容位置 (如诉讼保留、核心电子数据展示保留或其他 Advanced eDiscovery 案例的保留) 仍将保留这些保留。</span><span class="sxs-lookup"><span data-stu-id="c81cd-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="c81cd-114">该案例仍在安全与合规中心的"电子数据展示"Microsoft 365列出。</span><span class="sxs-lookup"><span data-stu-id="c81cd-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c81cd-115">将保留已关闭案例的详细信息、保留、搜索和成员。</span><span class="sxs-lookup"><span data-stu-id="c81cd-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="c81cd-116">可以在案例关闭后对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="c81cd-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="c81cd-117">例如，您可以添加或删除成员、创建搜索、导出搜索结果以及准备搜索结果以在 Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="c81cd-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="c81cd-118">活动事例和已关闭事例的主要区别在于当事例关闭时，保留已关闭。</span><span class="sxs-lookup"><span data-stu-id="c81cd-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="c81cd-119">关闭案件：</span><span class="sxs-lookup"><span data-stu-id="c81cd-119">To close a case:</span></span>

1. <span data-ttu-id="c81cd-120">在 **高级电子数据展示** 页面上，选择要关闭的案件。</span><span class="sxs-lookup"><span data-stu-id="c81cd-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="c81cd-121">在" **设置** 选项卡上，**"案例信息**"下， 点击 **选择**。</span><span class="sxs-lookup"><span data-stu-id="c81cd-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="c81cd-122">单击 **关闭案件**。</span><span class="sxs-lookup"><span data-stu-id="c81cd-122">Click **Close case**.</span></span>

   <span data-ttu-id="c81cd-123">完成结束过程可能需要多达 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="c81cd-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="c81cd-124">重新打开已关闭的案例</span><span class="sxs-lookup"><span data-stu-id="c81cd-124">Reopen a closed case</span></span>

<span data-ttu-id="c81cd-125">当重新打开Advanced eDiscovery案例时，关闭案例时已就位的任何保留不会自动恢复。</span><span class="sxs-lookup"><span data-stu-id="c81cd-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="c81cd-126">重新打开案例后，你必须转到保留选项卡并打开以前的保留。 </span><span class="sxs-lookup"><span data-stu-id="c81cd-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="c81cd-127">要打开保留，请选择它以显示弹出页面，然后将 **状态** 开关设置为 **“开”**。</span><span class="sxs-lookup"><span data-stu-id="c81cd-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="c81cd-128">重新打开已关闭案例：</span><span class="sxs-lookup"><span data-stu-id="c81cd-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="c81cd-129">在 **高级电子数据展示** 页面上，选择要关闭的案件。</span><span class="sxs-lookup"><span data-stu-id="c81cd-129">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="c81cd-130">在" **设置** 选项卡上，**"案例信息**"下， 点击 **选择**。</span><span class="sxs-lookup"><span data-stu-id="c81cd-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="c81cd-131">单击 **重新打开案件**。</span><span class="sxs-lookup"><span data-stu-id="c81cd-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="c81cd-132">可能需要 60 分钟才能完成重新打开过程。</span><span class="sxs-lookup"><span data-stu-id="c81cd-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="c81cd-133">删除案例</span><span class="sxs-lookup"><span data-stu-id="c81cd-133">Delete a case</span></span>

<span data-ttu-id="c81cd-134">可以删除活动用例和已关闭Advanced eDiscovery案例。</span><span class="sxs-lookup"><span data-stu-id="c81cd-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="c81cd-135">删除案例时，与该案例关联的所有组件（例如保管人列表、通信、搜索、审阅集和导出作业）都将被删除。</span><span class="sxs-lookup"><span data-stu-id="c81cd-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="c81cd-136">从合规中心内"Advanced eDiscovery"页面上Microsoft 365事例列表。</span><span class="sxs-lookup"><span data-stu-id="c81cd-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c81cd-137">无法恢复或重新打开已删除的案例。</span><span class="sxs-lookup"><span data-stu-id="c81cd-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="c81cd-138">在数据泄漏方案中，删除审阅集内项目的唯一方法就是删除Advanced eDiscovery案例。</span><span class="sxs-lookup"><span data-stu-id="c81cd-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="c81cd-139">其他"搜索和清除"方法不会从审阅集中删除项目。</span><span class="sxs-lookup"><span data-stu-id="c81cd-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="c81cd-140">在删除案例之前 (是处于活动状态还是已关闭) ，您必须先删除与该案例关联的所有保留。 </span><span class="sxs-lookup"><span data-stu-id="c81cd-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="c81cd-141">这包括删除状态为"关"的 **保留**。</span><span class="sxs-lookup"><span data-stu-id="c81cd-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="c81cd-142">删除与案例相关联的保留项：</span><span class="sxs-lookup"><span data-stu-id="c81cd-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="c81cd-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span><span class="sxs-lookup"><span data-stu-id="c81cd-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="c81cd-144">单击要删除的保留。</span><span class="sxs-lookup"><span data-stu-id="c81cd-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="c81cd-145">在飞出页面上，单击删除 **保留**。</span><span class="sxs-lookup"><span data-stu-id="c81cd-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="c81cd-146">删除案件：</span><span class="sxs-lookup"><span data-stu-id="c81cd-146">To delete a case:</span></span>

1. <span data-ttu-id="c81cd-147">在 **高级电子数据展示** 页面上，选择要关闭的案件。</span><span class="sxs-lookup"><span data-stu-id="c81cd-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="c81cd-148">在" **设置** 选项卡上，**"案例信息**"下， 点击 **选择**。</span><span class="sxs-lookup"><span data-stu-id="c81cd-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="c81cd-149">单击 **删除案件**。</span><span class="sxs-lookup"><span data-stu-id="c81cd-149">Click **Delete case**.</span></span>
