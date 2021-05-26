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
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657632"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="f410c-103">关闭或删除Advanced eDiscovery案例</span><span class="sxs-lookup"><span data-stu-id="f410c-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="f410c-104">完成案例支持的法律案件或调查Advanced eDiscovery，可以关闭或删除案例。</span><span class="sxs-lookup"><span data-stu-id="f410c-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="f410c-105">您还可以重新打开已关闭的案例。</span><span class="sxs-lookup"><span data-stu-id="f410c-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="f410c-106">关闭案例</span><span class="sxs-lookup"><span data-stu-id="f410c-106">Close a case</span></span>

<span data-ttu-id="f410c-107">下面是关闭事件案例时Advanced eDiscovery情况：</span><span class="sxs-lookup"><span data-stu-id="f410c-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="f410c-108">如果案例包含任何保留内容位置，这些保留将被关闭。</span><span class="sxs-lookup"><span data-stu-id="f410c-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="f410c-109">关闭保留后，称为延迟保留 (30 天的宽限期) 将应用于已保留的内容位置。</span><span class="sxs-lookup"><span data-stu-id="f410c-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="f410c-110">这有助于防止立即删除内容，并给予管理员搜索或恢复将在延迟保留期过期后永久删除的内容的机会。</span><span class="sxs-lookup"><span data-stu-id="f410c-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="f410c-111">有关详细信息，请参阅从电子数据展示保留 [中删除内容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="f410c-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="f410c-112">关闭案例仅关闭与该案例相关联的保留。</span><span class="sxs-lookup"><span data-stu-id="f410c-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="f410c-113">如果其他保留位于内容位置 (如诉讼保留、核心电子数据展示保留或其他 Advanced eDiscovery 案例的保留) 仍将保留这些保留。</span><span class="sxs-lookup"><span data-stu-id="f410c-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="f410c-114">该案例仍在安全与合规中心的"电子数据展示"Microsoft 365列出。</span><span class="sxs-lookup"><span data-stu-id="f410c-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f410c-115">将保留已关闭案例的详细信息、保留、搜索和成员。</span><span class="sxs-lookup"><span data-stu-id="f410c-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="f410c-116">可以在案例关闭后对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="f410c-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="f410c-117">例如，您可以添加或删除成员、创建搜索、导出搜索结果以及准备搜索结果以在 Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="f410c-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="f410c-118">活动事例和已关闭事例的主要区别在于当事例关闭时，保留已关闭。</span><span class="sxs-lookup"><span data-stu-id="f410c-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="f410c-119">关闭案件：</span><span class="sxs-lookup"><span data-stu-id="f410c-119">To close a case:</span></span>

1. <span data-ttu-id="f410c-120">在 **高级电子数据展示** 页面上，选择要关闭的案件。</span><span class="sxs-lookup"><span data-stu-id="f410c-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="f410c-121">在" **设置** 选项卡上，**"案例信息**"下， 点击 **选择**。</span><span class="sxs-lookup"><span data-stu-id="f410c-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="f410c-122">在"案例信息"飞出页面底部，单击 **" (...") "** 更多选项"，然后单击"**关闭案例"。**</span><span class="sxs-lookup"><span data-stu-id="f410c-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   !["更多选项"菜单中用于关闭事件Advanced eDiscovery选项](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="f410c-124&quot;>完成结束过程可能需要多达 60 分钟。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f410c-124&quot;>It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name=&quot;reopen-a-closed-case&quot;></a><span data-ttu-id=&quot;f410c-125&quot;>重新打开已关闭的案例</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f410c-125&quot;>Reopen a closed case</span></span>

<span data-ttu-id=&quot;f410c-126&quot;>当重新打开Advanced eDiscovery案例时，关闭案例时已就位的任何保留不会自动恢复。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f410c-126&quot;>When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id=&quot;f410c-127&quot;>重新打开案例后，你必须转到保留选项卡并打开以前的保留。 </span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f410c-127&quot;>After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id=&quot;f410c-128&quot;>要打开保留，请选择它以显示弹出页面，然后将 **状态** 开关设置为 **“开”**。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f410c-128&quot;>To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id=&quot;f410c-129&quot;>重新打开已关闭案例：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f410c-129&quot;>To reopen a closed case:</span></span>

1. <span data-ttu-id=&quot;f410c-130&quot;>在 **高级电子数据展示** 页面上，选择要关闭的案件。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f410c-130&quot;>On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id=&quot;f410c-131&quot;>在&quot; **设置** 选项卡上，**&quot;案例信息**&quot;下， 点击 **选择**。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;f410c-131&quot;>On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id=&quot;f410c-132&quot;>在&quot;案例信息&quot;飞出页面底部，单击&quot; (**...") "** 更多 **选项**"，然后单击"**重新打开案例"。**</span><span class="sxs-lookup"><span data-stu-id="f410c-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   !["更多选项"菜单中用于重新打开Advanced eDiscovery选项](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="f410c-134">可能需要 60 分钟才能完成重新打开过程。</span><span class="sxs-lookup"><span data-stu-id="f410c-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="f410c-135">删除案例</span><span class="sxs-lookup"><span data-stu-id="f410c-135">Delete a case</span></span>

<span data-ttu-id="f410c-136">可以删除活动用例和已关闭Advanced eDiscovery案例。</span><span class="sxs-lookup"><span data-stu-id="f410c-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="f410c-137">删除案例时，与该案例关联的所有组件（例如保管人列表、通信、搜索、审阅集和导出作业）都将被删除。</span><span class="sxs-lookup"><span data-stu-id="f410c-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="f410c-138">从合规中心内"Advanced eDiscovery"页面上Microsoft 365事例列表。</span><span class="sxs-lookup"><span data-stu-id="f410c-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f410c-139">无法恢复或重新打开已删除的案例。</span><span class="sxs-lookup"><span data-stu-id="f410c-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="f410c-140">在数据泄漏方案中，删除审阅集内项目的唯一方法就是删除Advanced eDiscovery案例。</span><span class="sxs-lookup"><span data-stu-id="f410c-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="f410c-141">其他"搜索和清除"方法不会从审阅集中删除项目。</span><span class="sxs-lookup"><span data-stu-id="f410c-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="f410c-142">在删除案例之前 (是处于活动状态还是已关闭) ，您必须先删除与该案例关联的所有保留。 </span><span class="sxs-lookup"><span data-stu-id="f410c-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="f410c-143">这包括删除状态为"关"的 **保留**。</span><span class="sxs-lookup"><span data-stu-id="f410c-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="f410c-144">删除与案例相关联的保留项：</span><span class="sxs-lookup"><span data-stu-id="f410c-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="f410c-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span><span class="sxs-lookup"><span data-stu-id="f410c-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="f410c-146">单击要删除的保留。</span><span class="sxs-lookup"><span data-stu-id="f410c-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="f410c-147">在飞出页面上，单击删除 **保留**。</span><span class="sxs-lookup"><span data-stu-id="f410c-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="f410c-148">删除案件：</span><span class="sxs-lookup"><span data-stu-id="f410c-148">To delete a case:</span></span>

1. <span data-ttu-id="f410c-149">在 **高级电子数据展示** 页面上，选择要关闭的案件。</span><span class="sxs-lookup"><span data-stu-id="f410c-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="f410c-150">在" **设置** 选项卡上，**"案例信息**"下， 点击 **选择**。</span><span class="sxs-lookup"><span data-stu-id="f410c-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="f410c-151">在"案例信息"飞出页底部，单击 **" (...")\*\*\*\*更多选项**"，然后单击"删除 **大小写"。**</span><span class="sxs-lookup"><span data-stu-id="f410c-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   !["更多选项"菜单中用于删除Advanced eDiscovery选项](..\Media\DeleteAdvancedeDiscoveryCase.png)
