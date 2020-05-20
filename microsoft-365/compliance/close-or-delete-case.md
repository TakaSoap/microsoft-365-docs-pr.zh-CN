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
description: 了解当关闭或删除高级电子数据展示事例支持的调查或合法案例时，会发生什么情况。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292408"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="75811-103">关闭或删除高级电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="75811-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="75811-104">当高级电子数据展示事例支持的法律案例或调查完成后，您可以关闭或删除事例。</span><span class="sxs-lookup"><span data-stu-id="75811-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="75811-105">您还可以重新打开已关闭的案例。</span><span class="sxs-lookup"><span data-stu-id="75811-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="75811-106">关闭事例</span><span class="sxs-lookup"><span data-stu-id="75811-106">Close a case</span></span>

<span data-ttu-id="75811-107">以下是在关闭高级电子数据展示事例时会发生的情况：</span><span class="sxs-lookup"><span data-stu-id="75811-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="75811-108">如果事例包含处于保留状态的任何内容位置，则这些保留将被禁用。</span><span class="sxs-lookup"><span data-stu-id="75811-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="75811-109">这可能会导致用户或通过自动过程（如删除策略）永久删除或清除内容。</span><span class="sxs-lookup"><span data-stu-id="75811-109">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="75811-110">仅关闭案例只会关闭与该案例相关的保留。</span><span class="sxs-lookup"><span data-stu-id="75811-110">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="75811-111">如果其他保留项放置在内容位置（如诉讼保留、核心电子数据展示保留或来自不同高级电子数据展示事例的保留），则仍将保留这些保留。</span><span class="sxs-lookup"><span data-stu-id="75811-111">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="75811-112">该事例仍列在 Microsoft 365 合规性中心的电子数据展示页面中。</span><span class="sxs-lookup"><span data-stu-id="75811-112">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="75811-113">已关闭事例的详细信息、保留、搜索和成员将保留。</span><span class="sxs-lookup"><span data-stu-id="75811-113">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="75811-114">您可以在关闭案例后对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="75811-114">You can edit a case after it's closed.</span></span> <span data-ttu-id="75811-115">例如，您可以在高级电子数据展示中添加或删除成员、创建搜索、导出搜索结果并准备用于分析的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="75811-115">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="75811-116">活动和已关闭的事例之间的主要区别是在关闭事例时，保留功能将关闭。</span><span class="sxs-lookup"><span data-stu-id="75811-116">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="75811-117">若要关闭事例：</span><span class="sxs-lookup"><span data-stu-id="75811-117">To close a case:</span></span>

1. <span data-ttu-id="75811-118">在 "**高级电子数据展示**" 页上，选择要关闭的大小写。</span><span class="sxs-lookup"><span data-stu-id="75811-118">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="75811-119">在 "**设置**" 选项卡上的 "**事例信息**" 下，单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="75811-119">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="75811-120">单击 "**关闭事例**"。</span><span class="sxs-lookup"><span data-stu-id="75811-120">Click **Close case**.</span></span>

   <span data-ttu-id="75811-121">完成关闭过程可能需要长达60分钟。</span><span class="sxs-lookup"><span data-stu-id="75811-121">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="75811-122">重新打开已关闭的事例</span><span class="sxs-lookup"><span data-stu-id="75811-122">Reopen a closed case</span></span>

<span data-ttu-id="75811-123">当您重新打开高级电子数据展示事例时，在关闭该事例时将不会自动恢复这些保留。</span><span class="sxs-lookup"><span data-stu-id="75811-123">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="75811-124">重新打开案例后，必须转到 "**保留**" 选项卡，并启用以前的保留。</span><span class="sxs-lookup"><span data-stu-id="75811-124">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="75811-125">若要打开保留，请选择它以显示弹出页面，然后将**状态**切换设置为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="75811-125">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="75811-126">重新打开已关闭的事例：</span><span class="sxs-lookup"><span data-stu-id="75811-126">To reopen a closed case:</span></span>

1. <span data-ttu-id="75811-127">在 "**高级电子数据展示**" 页上，选择要删除的大小写。</span><span class="sxs-lookup"><span data-stu-id="75811-127">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="75811-128">在 "**设置**" 选项卡上的 "**事例信息**" 下，单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="75811-128">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="75811-129">单击 "**重新打开大小写**"。</span><span class="sxs-lookup"><span data-stu-id="75811-129">Click **Reopen case**.</span></span>

   <span data-ttu-id="75811-130">最长可能需要60分钟才能完成重新打开过程。</span><span class="sxs-lookup"><span data-stu-id="75811-130">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="75811-131">删除案例</span><span class="sxs-lookup"><span data-stu-id="75811-131">Delete a case</span></span>

<span data-ttu-id="75811-132">您可以删除活动的和已关闭的高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="75811-132">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="75811-133">删除案例时，将删除与该事例关联的所有组件，如保管人、通信、搜索、审阅集和导出作业的列表。</span><span class="sxs-lookup"><span data-stu-id="75811-133">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="75811-134">将从 Microsoft 365 合规性中心的 "**高级电子数据展示**" 页上的事例列表中删除该事例。</span><span class="sxs-lookup"><span data-stu-id="75811-134">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="75811-135">无法恢复或重新打开已删除的事例。</span><span class="sxs-lookup"><span data-stu-id="75811-135">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="75811-136">在 data 外泄方案中，删除审阅集中的项目的唯一方法是删除高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="75811-136">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="75811-137">其他 "搜索和清除" 方法不会从审阅集中删除项目。</span><span class="sxs-lookup"><span data-stu-id="75811-137">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="75811-138">必须先删除与事例关联的*所有*保留，然后才能删除事例（无论是处于活动状态还是已关闭状态）。</span><span class="sxs-lookup"><span data-stu-id="75811-138">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="75811-139">这包括删除状态为 "**关**" 的保留。</span><span class="sxs-lookup"><span data-stu-id="75811-139">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="75811-140">删除与事例关联的保留：</span><span class="sxs-lookup"><span data-stu-id="75811-140">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="75811-141">转到要删除的高级电子数据展示事例中的 "**保留**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="75811-141">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="75811-142">单击要删除的保留。</span><span class="sxs-lookup"><span data-stu-id="75811-142">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="75811-143">在弹出页面上，单击 "**删除保留**"。</span><span class="sxs-lookup"><span data-stu-id="75811-143">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="75811-144">删除案例：</span><span class="sxs-lookup"><span data-stu-id="75811-144">To delete a case:</span></span>

1. <span data-ttu-id="75811-145">在 "**高级电子数据展示**" 页上，选择要删除的大小写。</span><span class="sxs-lookup"><span data-stu-id="75811-145">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="75811-146">在 "**设置**" 选项卡上的 "**事例信息**" 下，单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="75811-146">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="75811-147">单击 "**删除大小写**"。</span><span class="sxs-lookup"><span data-stu-id="75811-147">Click **Delete case**.</span></span>
