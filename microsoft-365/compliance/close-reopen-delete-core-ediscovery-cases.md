---
title: 关闭、重新打开和删除核心电子数据展示事例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍如何管理核心电子数据展示事例。 这包括关闭事例、重新打开已关闭事例和删除案例。
ms.openlocfilehash: 45282486c2c3b1d00b99a1cda5968b3bb042f6c2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208414"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="9a766-104">关闭、重新打开和删除核心电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="9a766-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="9a766-105">本文介绍如何在 Microsoft 365 中关闭、重新打开和删除核心电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="9a766-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="9a766-106">关闭事例</span><span class="sxs-lookup"><span data-stu-id="9a766-106">Close a case</span></span>

<span data-ttu-id="9a766-107">当核心电子数据展示事例支持的法律案例或调查完成后，您可以关闭该事例。</span><span class="sxs-lookup"><span data-stu-id="9a766-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="9a766-108">以下是在关闭事例时将会发生的情况：</span><span class="sxs-lookup"><span data-stu-id="9a766-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="9a766-109">如果案例在电子数据展示保留中包含任何内容位置，这些保留将被禁用。</span><span class="sxs-lookup"><span data-stu-id="9a766-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="9a766-110">这可能会导致用户或通过自动过程（如删除策略）永久删除或清除内容。</span><span class="sxs-lookup"><span data-stu-id="9a766-110">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="9a766-111">仅关闭案例只会关闭与该案例相关的保留。</span><span class="sxs-lookup"><span data-stu-id="9a766-111">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="9a766-112">如果将其他保留放置在内容位置（如诉讼保留、保留策略或来自不同核心电子数据展示案例的保留），仍将保留这些保留项。</span><span class="sxs-lookup"><span data-stu-id="9a766-112">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="9a766-113">该事例仍列在 Microsoft 365 合规性中心的核心电子数据展示页面中。</span><span class="sxs-lookup"><span data-stu-id="9a766-113">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9a766-114">已关闭事例的详细信息、保留、搜索和成员将保留。</span><span class="sxs-lookup"><span data-stu-id="9a766-114">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="9a766-115">您可以在关闭案例后对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="9a766-115">You can edit a case after it's closed.</span></span> <span data-ttu-id="9a766-116">例如，您可以添加或移除成员、创建搜索和导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="9a766-116">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="9a766-117">活动和已关闭的事例之间的主要区别在于，在关闭事例时，电子数据展示保留功能将关闭。</span><span class="sxs-lookup"><span data-stu-id="9a766-117">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="9a766-118">若要关闭事例：</span><span class="sxs-lookup"><span data-stu-id="9a766-118">To close a case:</span></span>
  
1. <span data-ttu-id="9a766-119">在 Microsoft 365 合规性中心中，单击 "**电子数据展示**  >  **核心**" 以显示您的组织中的核心电子数据展示事例的列表。</span><span class="sxs-lookup"><span data-stu-id="9a766-119">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="9a766-120">单击要关闭的事例的名称。</span><span class="sxs-lookup"><span data-stu-id="9a766-120">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="9a766-121">将显示 "**管理此案例**" 弹出页面。</span><span class="sxs-lookup"><span data-stu-id="9a766-121">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="9a766-122">在 "**管理事例状态**" 下，单击 "**关闭事例**"。</span><span class="sxs-lookup"><span data-stu-id="9a766-122">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="9a766-123">将显示一条警告，指出与事例关联的保留将被禁用。</span><span class="sxs-lookup"><span data-stu-id="9a766-123">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="9a766-124">单击 **"是"** 关闭该事例。</span><span class="sxs-lookup"><span data-stu-id="9a766-124">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="9a766-125">"**管理此事例**" 弹出页面上的状态从 "**活动**" 更改为 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="9a766-125">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="9a766-126">关闭 "**管理此案例**" 页。</span><span class="sxs-lookup"><span data-stu-id="9a766-126">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="9a766-127">在**核心电子数据展示**页面上，单击 "**刷新**" 以更新已关闭事例的状态。</span><span class="sxs-lookup"><span data-stu-id="9a766-127">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="9a766-128">完成关闭过程可能需要长达60分钟。</span><span class="sxs-lookup"><span data-stu-id="9a766-128">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="9a766-129">在此过程完成后，将在**核心电子数据展示**页面上将该案例的状态更改为 "**已关闭**"。</span><span class="sxs-lookup"><span data-stu-id="9a766-129">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="9a766-130">再次单击该事例的名称以显示 "**管理此案例**" 飞出页面，其中包含有关该事例何时关闭和关闭的时间的信息。</span><span class="sxs-lookup"><span data-stu-id="9a766-130">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="9a766-131">重新打开已关闭的事例</span><span class="sxs-lookup"><span data-stu-id="9a766-131">Reopen a closed case</span></span>

<span data-ttu-id="9a766-132">重新打开案例时，将不会自动恢复已关闭事例的任何电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="9a766-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="9a766-133">重新打开案例后，必须转到 "**保留**" 页面并打开以前的保留。</span><span class="sxs-lookup"><span data-stu-id="9a766-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="9a766-134">若要打开保留，请选择它以显示弹出页面，然后将**状态**切换设置为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="9a766-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="9a766-135">在 Microsoft 365 合规性中心中，单击 "**电子数据展示**  >  **核心**" 以显示您的组织中的核心电子数据展示事例的列表。</span><span class="sxs-lookup"><span data-stu-id="9a766-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="9a766-136">单击要重新打开的事例的名称。</span><span class="sxs-lookup"><span data-stu-id="9a766-136">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="9a766-137">将显示 "**管理此案例**" 弹出页面。</span><span class="sxs-lookup"><span data-stu-id="9a766-137">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="9a766-138">在 "**管理案例状态**" 下，单击 "**重新打开事例**"。</span><span class="sxs-lookup"><span data-stu-id="9a766-138">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="9a766-139">将显示一条警告，指出在关闭时与该事例相关联的保留不会自动打开。</span><span class="sxs-lookup"><span data-stu-id="9a766-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="9a766-140">单击 **"是"** 重新打开该事例。</span><span class="sxs-lookup"><span data-stu-id="9a766-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="9a766-141">"**管理此事例**" 弹出页面上的状态从 "**已关闭**" 更改为 "**活动**"。</span><span class="sxs-lookup"><span data-stu-id="9a766-141">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="9a766-142">关闭 "**管理此案例**" 页。</span><span class="sxs-lookup"><span data-stu-id="9a766-142">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="9a766-143">在**核心电子数据展示**页面上，单击 "**刷新**" 以更新重新打开的事例的状态。</span><span class="sxs-lookup"><span data-stu-id="9a766-143">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="9a766-144">最长可能需要60分钟才能完成重新打开过程。</span><span class="sxs-lookup"><span data-stu-id="9a766-144">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="9a766-145">在此过程完成后，将在**核心电子数据展示**页面上将该案例的状态更改为 "**活动**"。</span><span class="sxs-lookup"><span data-stu-id="9a766-145">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="9a766-146">删除案例</span><span class="sxs-lookup"><span data-stu-id="9a766-146">Delete a case</span></span>

<span data-ttu-id="9a766-147">您还可以删除活动和已关闭的核心电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="9a766-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="9a766-148">删除案例时，将删除事例中的所有搜索和导出，并将该事例从 Microsoft 365 合规性中心的**核心电子数据展示**页面上的事例列表中删除。</span><span class="sxs-lookup"><span data-stu-id="9a766-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9a766-149">无法重新打开已删除的事例。</span><span class="sxs-lookup"><span data-stu-id="9a766-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="9a766-150">必须先删除与事例相关联的*所有*电子数据展示保留，然后才能删除该事例（无论是处于活动状态还是已关闭状态）。</span><span class="sxs-lookup"><span data-stu-id="9a766-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="9a766-151">这包括删除状态为 "**关**" 的保留。</span><span class="sxs-lookup"><span data-stu-id="9a766-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="9a766-152">删除电子数据展示保留：</span><span class="sxs-lookup"><span data-stu-id="9a766-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="9a766-153">转到 "**保留**" 选项卡（如果要删除）。</span><span class="sxs-lookup"><span data-stu-id="9a766-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="9a766-154">单击要删除的保留。</span><span class="sxs-lookup"><span data-stu-id="9a766-154">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="9a766-155">在弹出页面上，单击 "**删除保留**"。</span><span class="sxs-lookup"><span data-stu-id="9a766-155">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="9a766-156">删除案例：</span><span class="sxs-lookup"><span data-stu-id="9a766-156">To delete a case:</span></span>

1. <span data-ttu-id="9a766-157">在 Microsoft 365 合规性中心中，单击 "**电子数据展示**  >  **核心**" 以显示您的组织中的核心电子数据展示事例的列表。</span><span class="sxs-lookup"><span data-stu-id="9a766-157">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="9a766-158">单击要删除的事例的名称。</span><span class="sxs-lookup"><span data-stu-id="9a766-158">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="9a766-159">在弹出页面上的 "**管理大小写状态**" 下，单击 "**删除大小写**"。</span><span class="sxs-lookup"><span data-stu-id="9a766-159">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="9a766-160">如果你尝试删除的案例仍包含电子数据展示保留，将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="9a766-160">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="9a766-161">您必须删除与该事例相关的所有保留，然后再尝试删除该事例。</span><span class="sxs-lookup"><span data-stu-id="9a766-161">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
