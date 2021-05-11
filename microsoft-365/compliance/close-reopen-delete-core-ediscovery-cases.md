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
description: 本文介绍如何管理核心电子数据展示事例。 这包括关闭案例、重新打开已关闭的案例和删除案例。
ms.openlocfilehash: 251ca932954071cf949c45343130f122464dcf01
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310872"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="f4784-104">关闭、重新打开和删除核心电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="f4784-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="f4784-105">本文介绍如何关闭、重新打开和删除 Microsoft 365 中的核心电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="f4784-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="f4784-106">关闭案例</span><span class="sxs-lookup"><span data-stu-id="f4784-106">Close a case</span></span>

<span data-ttu-id="f4784-107">完成核心电子数据展示案例支持的法律案件或调查后，可以关闭该案例。</span><span class="sxs-lookup"><span data-stu-id="f4784-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="f4784-108">下面是关闭案例时发生的情况：</span><span class="sxs-lookup"><span data-stu-id="f4784-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="f4784-109">如果案件集包含任何电子数据展示保留，将关闭它们。</span><span class="sxs-lookup"><span data-stu-id="f4784-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="f4784-110">关闭保留后，称为延迟保留 (30 天的宽限期) 将应用于已保留的内容位置。</span><span class="sxs-lookup"><span data-stu-id="f4784-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="f4784-111">这有助于防止立即删除内容，并且使管理员有机会在延迟保留期到期后永久删除内容之前搜索和还原内容。</span><span class="sxs-lookup"><span data-stu-id="f4784-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="f4784-112">有关详细信息，请参阅从电子数据展示保留 [中删除内容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="f4784-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="f4784-113">关闭案例仅关闭与该案例相关联的保留。</span><span class="sxs-lookup"><span data-stu-id="f4784-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="f4784-114">如果其他保留设置在内容位置上 (如诉讼保留、保留策略或不同核心电子数据展示案例的保留) 仍将保留这些保留。</span><span class="sxs-lookup"><span data-stu-id="f4784-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="f4784-115">该案例仍在安全与合规中心的"核心电子数据展示"Microsoft 365列出。</span><span class="sxs-lookup"><span data-stu-id="f4784-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f4784-116">将保留已关闭案例的详细信息、保留、搜索和成员。</span><span class="sxs-lookup"><span data-stu-id="f4784-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="f4784-117">可以在案例关闭后对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="f4784-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="f4784-118">例如，可以添加或删除成员、创建搜索和导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="f4784-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="f4784-119">活动案例和已关闭事例之间的主要区别在于关闭事例时关闭电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="f4784-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="f4784-120">关闭案件：</span><span class="sxs-lookup"><span data-stu-id="f4784-120">To close a case:</span></span>
  
1. <span data-ttu-id="f4784-121">在Microsoft 365中心，单击 **"电子数据** 展示  >  **核心**"以显示组织中核心电子数据展示事例的列表。</span><span class="sxs-lookup"><span data-stu-id="f4784-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="f4784-122">单击要关闭的案例的名称。</span><span class="sxs-lookup"><span data-stu-id="f4784-122">Click the name of the case that you want to close.</span></span>

   ![案例主页上的关闭案例](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="f4784-124">在主页上的"状态"**下**，单击"**关闭大小写"。**</span><span class="sxs-lookup"><span data-stu-id="f4784-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="f4784-125">将显示一条警告，指出将关闭与案例关联的保留。</span><span class="sxs-lookup"><span data-stu-id="f4784-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="f4784-126">单击 **"是** "关闭案例。</span><span class="sxs-lookup"><span data-stu-id="f4784-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="f4784-127">案例主页上的状态从"活动 **"更改为"\*\*\*\*关闭"。**</span><span class="sxs-lookup"><span data-stu-id="f4784-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="f4784-128">在" **核心电子数据展示"** 页上，单击 **"刷新** "以更新已关闭案例的状态。</span><span class="sxs-lookup"><span data-stu-id="f4784-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="f4784-129">完成结束过程可能需要多达 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="f4784-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="f4784-130">该过程完成后，在核心电子数据展示页面上将案例的状态更改为"已关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="f4784-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="f4784-131">重新打开已关闭的案例</span><span class="sxs-lookup"><span data-stu-id="f4784-131">Reopen a closed case</span></span>

<span data-ttu-id="f4784-132">重新打开案例时，关闭案例时已就位的任何电子数据展示保留不会自动恢复。</span><span class="sxs-lookup"><span data-stu-id="f4784-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="f4784-133">重新打开案例后，你必须转到保留页并打开以前的保留。 </span><span class="sxs-lookup"><span data-stu-id="f4784-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="f4784-134">要打开保留，请选择它以显示弹出页面，然后将 **状态** 开关设置为 **“开”**。</span><span class="sxs-lookup"><span data-stu-id="f4784-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="f4784-135">在Microsoft 365中心，单击 **"电子数据** 展示  >  **核心**"以显示组织中核心电子数据展示事例的列表。</span><span class="sxs-lookup"><span data-stu-id="f4784-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="f4784-136">单击要重新打开的案例的名称。</span><span class="sxs-lookup"><span data-stu-id="f4784-136">Click the name of the case that you want to reopen.</span></span>

   ![重新打开已关闭的案例](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="f4784-138">在主页上的"状态"**下**，单击"**重新打开案例"。**</span><span class="sxs-lookup"><span data-stu-id="f4784-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="f4784-139">将显示一条警告，指出关闭案例时与案例关联的保留不会自动打开。</span><span class="sxs-lookup"><span data-stu-id="f4784-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="f4784-140">单击 **"是** "重新打开该案例。</span><span class="sxs-lookup"><span data-stu-id="f4784-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="f4784-141">案例主页飞出页面上的状态从 **"已关闭"** 更改为"**活动"。**</span><span class="sxs-lookup"><span data-stu-id="f4784-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="f4784-142">在" **核心电子数据展示"** 页上，单击" **刷新** "以更新重新打开案例的状态。</span><span class="sxs-lookup"><span data-stu-id="f4784-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="f4784-143">可能需要 60 分钟才能完成重新打开过程。</span><span class="sxs-lookup"><span data-stu-id="f4784-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="f4784-144">该过程完成后，在核心电子数据展示页面上将案例的状态更改为"活动 **"。**</span><span class="sxs-lookup"><span data-stu-id="f4784-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

7. <span data-ttu-id="f4784-145"> (可选) 若要启用与重新打开的案例关联的任何保留项，请转到保留选项卡，选择保留，然后选择保留项飞出页面上的"状态"下的复选框。 </span><span class="sxs-lookup"><span data-stu-id="f4784-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="f4784-146">删除案例</span><span class="sxs-lookup"><span data-stu-id="f4784-146">Delete a case</span></span>

<span data-ttu-id="f4784-147">还可以删除主动和已关闭的核心电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="f4784-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="f4784-148">删除事例时，将删除事例的所有搜索和导出，并且从事例合规中心中"核心电子数据展示"页上的事例Microsoft 365事例列表。</span><span class="sxs-lookup"><span data-stu-id="f4784-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f4784-149">不能重新打开已删除的大小写。</span><span class="sxs-lookup"><span data-stu-id="f4784-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="f4784-150">必须先删除与 (相关联的所有电子数据展示保留) ，然后才能删除案例。 </span><span class="sxs-lookup"><span data-stu-id="f4784-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="f4784-151">这包括删除状态为"关"的 **保留**。</span><span class="sxs-lookup"><span data-stu-id="f4784-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="f4784-152">若要删除电子数据展示保留，请：</span><span class="sxs-lookup"><span data-stu-id="f4784-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="f4784-153">转到 **要** 删除的保留项选项卡。</span><span class="sxs-lookup"><span data-stu-id="f4784-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="f4784-154">选择要删除的保留。</span><span class="sxs-lookup"><span data-stu-id="f4784-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="f4784-155">在飞出页面上， **单击删除**。</span><span class="sxs-lookup"><span data-stu-id="f4784-155">On the flyout page, click **Delete**.</span></span>

      ![删除电子数据展示保留](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="f4784-157">删除案件：</span><span class="sxs-lookup"><span data-stu-id="f4784-157">To delete a case:</span></span>

1. <span data-ttu-id="f4784-158">在Microsoft 365中心，单击 **"电子数据** 展示  >  **核心**"以显示组织中核心电子数据展示事例的列表。</span><span class="sxs-lookup"><span data-stu-id="f4784-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="f4784-159">单击要删除的案例的名称。</span><span class="sxs-lookup"><span data-stu-id="f4784-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="f4784-160">在案例主页上的"状态"**下**，单击"**删除大小写"。**</span><span class="sxs-lookup"><span data-stu-id="f4784-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![重新打开已关闭的案例](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="f4784-162">如果你尝试删除的案例仍包含电子数据展示保留，你将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="f4784-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="f4784-163">您必须删除与案例关联的所有保留，然后重试以删除该案例。</span><span class="sxs-lookup"><span data-stu-id="f4784-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
