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
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412791"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="6e43c-104">关闭、重新打开和删除核心电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="6e43c-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="6e43c-105">本文介绍如何在 Microsoft 365 中关闭、重新打开和删除核心电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="6e43c-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="6e43c-106">关闭事例</span><span class="sxs-lookup"><span data-stu-id="6e43c-106">Close a case</span></span>

<span data-ttu-id="6e43c-107">当核心电子数据展示事例支持的法律案例或调查完成后，您可以关闭该事例。</span><span class="sxs-lookup"><span data-stu-id="6e43c-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="6e43c-108">以下是在关闭事例时将会发生的情况：</span><span class="sxs-lookup"><span data-stu-id="6e43c-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="6e43c-109">如果案例在电子数据展示保留中包含任何内容位置，这些保留将被禁用。</span><span class="sxs-lookup"><span data-stu-id="6e43c-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="6e43c-110">关闭保留后，30天宽限期（称为*延迟保留*）将应用于处于保留状态的内容位置。</span><span class="sxs-lookup"><span data-stu-id="6e43c-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="6e43c-111">这有助于防止立即删除内容，并使管理员能够在延迟保留期到期之后永久删除内容之前，搜索并还原内容。</span><span class="sxs-lookup"><span data-stu-id="6e43c-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="6e43c-112">有关详细信息，请参阅[删除电子数据展示保留中的内容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="6e43c-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="6e43c-113">仅关闭案例只会关闭与该案例相关的保留。</span><span class="sxs-lookup"><span data-stu-id="6e43c-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="6e43c-114">如果将其他保留放置在内容位置（如诉讼保留、保留策略或来自不同核心电子数据展示案例的保留），仍将保留这些保留项。</span><span class="sxs-lookup"><span data-stu-id="6e43c-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="6e43c-115">该事例仍列在 Microsoft 365 合规性中心的核心电子数据展示页面中。</span><span class="sxs-lookup"><span data-stu-id="6e43c-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6e43c-116">已关闭事例的详细信息、保留、搜索和成员将保留。</span><span class="sxs-lookup"><span data-stu-id="6e43c-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="6e43c-117">您可以在关闭案例后对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="6e43c-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="6e43c-118">例如，您可以添加或移除成员、创建搜索和导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="6e43c-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="6e43c-119">活动和已关闭的事例之间的主要区别在于，在关闭事例时，电子数据展示保留功能将关闭。</span><span class="sxs-lookup"><span data-stu-id="6e43c-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="6e43c-120">若要关闭事例：</span><span class="sxs-lookup"><span data-stu-id="6e43c-120">To close a case:</span></span>
  
1. <span data-ttu-id="6e43c-121">在 Microsoft 365 合规性中心中，单击 "**电子数据展示**  >  **核心**" 以显示您的组织中的核心电子数据展示事例的列表。</span><span class="sxs-lookup"><span data-stu-id="6e43c-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="6e43c-122">单击要关闭的事例的名称。</span><span class="sxs-lookup"><span data-stu-id="6e43c-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="6e43c-123">将显示 "**管理此案例**" 弹出页面。</span><span class="sxs-lookup"><span data-stu-id="6e43c-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="6e43c-124">在 "**管理事例状态**" 下，单击 "**关闭事例**"。</span><span class="sxs-lookup"><span data-stu-id="6e43c-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="6e43c-125">将显示一条警告，指出与事例关联的保留将被禁用。</span><span class="sxs-lookup"><span data-stu-id="6e43c-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="6e43c-126">单击 **"是"** 关闭该事例。</span><span class="sxs-lookup"><span data-stu-id="6e43c-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="6e43c-127">"**管理此事例**" 弹出页面上的状态从 "**活动**" 更改为 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="6e43c-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="6e43c-128">关闭 "**管理此案例**" 页。</span><span class="sxs-lookup"><span data-stu-id="6e43c-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="6e43c-129">在**核心电子数据展示**页面上，单击 "**刷新**" 以更新已关闭事例的状态。</span><span class="sxs-lookup"><span data-stu-id="6e43c-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="6e43c-130">完成关闭过程可能需要长达60分钟。</span><span class="sxs-lookup"><span data-stu-id="6e43c-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="6e43c-131">在此过程完成后，将在**核心电子数据展示**页面上将该案例的状态更改为 "**已关闭**"。</span><span class="sxs-lookup"><span data-stu-id="6e43c-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="6e43c-132">再次单击该事例的名称以显示 "**管理此案例**" 飞出页面，其中包含有关该事例何时关闭和关闭的时间的信息。</span><span class="sxs-lookup"><span data-stu-id="6e43c-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="6e43c-133">重新打开已关闭的事例</span><span class="sxs-lookup"><span data-stu-id="6e43c-133">Reopen a closed case</span></span>

<span data-ttu-id="6e43c-134">重新打开案例时，将不会自动恢复已关闭事例的任何电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="6e43c-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="6e43c-135">重新打开案例后，必须转到 "**保留**" 页面并打开以前的保留。</span><span class="sxs-lookup"><span data-stu-id="6e43c-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="6e43c-136">若要打开保留，请选择它以显示弹出页面，然后将**状态**切换设置为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="6e43c-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="6e43c-137">在 Microsoft 365 合规性中心中，单击 "**电子数据展示**  >  **核心**" 以显示您的组织中的核心电子数据展示事例的列表。</span><span class="sxs-lookup"><span data-stu-id="6e43c-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="6e43c-138">单击要重新打开的事例的名称。</span><span class="sxs-lookup"><span data-stu-id="6e43c-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="6e43c-139">将显示 "**管理此案例**" 弹出页面。</span><span class="sxs-lookup"><span data-stu-id="6e43c-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="6e43c-140">在 "**管理案例状态**" 下，单击 "**重新打开事例**"。</span><span class="sxs-lookup"><span data-stu-id="6e43c-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="6e43c-141">将显示一条警告，指出在关闭时与该事例相关联的保留不会自动打开。</span><span class="sxs-lookup"><span data-stu-id="6e43c-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="6e43c-142">单击 **"是"** 重新打开该事例。</span><span class="sxs-lookup"><span data-stu-id="6e43c-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="6e43c-143">"**管理此事例**" 弹出页面上的状态从 "**已关闭**" 更改为 "**活动**"。</span><span class="sxs-lookup"><span data-stu-id="6e43c-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="6e43c-144">关闭 "**管理此案例**" 页。</span><span class="sxs-lookup"><span data-stu-id="6e43c-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="6e43c-145">在**核心电子数据展示**页面上，单击 "**刷新**" 以更新重新打开的事例的状态。</span><span class="sxs-lookup"><span data-stu-id="6e43c-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="6e43c-146">最长可能需要60分钟才能完成重新打开过程。</span><span class="sxs-lookup"><span data-stu-id="6e43c-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="6e43c-147">在此过程完成后，将在**核心电子数据展示**页面上将该案例的状态更改为 "**活动**"。</span><span class="sxs-lookup"><span data-stu-id="6e43c-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="6e43c-148">删除案例</span><span class="sxs-lookup"><span data-stu-id="6e43c-148">Delete a case</span></span>

<span data-ttu-id="6e43c-149">您还可以删除活动和已关闭的核心电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="6e43c-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="6e43c-150">删除案例时，将删除事例中的所有搜索和导出，并将该事例从 Microsoft 365 合规性中心的**核心电子数据展示**页面上的事例列表中删除。</span><span class="sxs-lookup"><span data-stu-id="6e43c-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6e43c-151">无法重新打开已删除的事例。</span><span class="sxs-lookup"><span data-stu-id="6e43c-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="6e43c-152">必须先删除与事例相关联的*所有*电子数据展示保留，然后才能删除该事例（无论是处于活动状态还是已关闭状态）。</span><span class="sxs-lookup"><span data-stu-id="6e43c-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="6e43c-153">这包括删除状态为 "**关**" 的保留。</span><span class="sxs-lookup"><span data-stu-id="6e43c-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="6e43c-154">删除电子数据展示保留：</span><span class="sxs-lookup"><span data-stu-id="6e43c-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="6e43c-155">转到 "**保留**" 选项卡（如果要删除）。</span><span class="sxs-lookup"><span data-stu-id="6e43c-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="6e43c-156">单击要删除的保留。</span><span class="sxs-lookup"><span data-stu-id="6e43c-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="6e43c-157">在弹出页面上，单击 "**删除保留**"。</span><span class="sxs-lookup"><span data-stu-id="6e43c-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="6e43c-158">删除案例：</span><span class="sxs-lookup"><span data-stu-id="6e43c-158">To delete a case:</span></span>

1. <span data-ttu-id="6e43c-159">在 Microsoft 365 合规性中心中，单击 "**电子数据展示**  >  **核心**" 以显示您的组织中的核心电子数据展示事例的列表。</span><span class="sxs-lookup"><span data-stu-id="6e43c-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="6e43c-160">单击要删除的事例的名称。</span><span class="sxs-lookup"><span data-stu-id="6e43c-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="6e43c-161">在弹出页面上的 "**管理大小写状态**" 下，单击 "**删除大小写**"。</span><span class="sxs-lookup"><span data-stu-id="6e43c-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="6e43c-162">如果你尝试删除的案例仍包含电子数据展示保留，将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="6e43c-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="6e43c-163">您必须删除与该事例相关的所有保留，然后再尝试删除该事例。</span><span class="sxs-lookup"><span data-stu-id="6e43c-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
