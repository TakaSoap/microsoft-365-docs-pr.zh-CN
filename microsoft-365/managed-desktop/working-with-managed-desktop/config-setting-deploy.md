---
title: 在 Microsoft 托管桌面中部署可配置设置
description: 在 Microsoft 托管桌面中部署和跟踪可配置设置更改。
keywords: Microsoft 托管桌面， Microsoft 365， 服务， 文档， 部署， 分步部署， 可配置设置
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104530"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="7e45b-104">部署和跟踪可配置设置 - Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="7e45b-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="7e45b-105">对设置类别进行更改并部署后，"部署状态"页允许您开始将设置部署到组。</span><span class="sxs-lookup"><span data-stu-id="7e45b-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="7e45b-106">此页面显示每个可配置设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="7e45b-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="7e45b-107">通过打开设置类别，可以将设置部署到组并跟踪这些部署的进度。</span><span class="sxs-lookup"><span data-stu-id="7e45b-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="7e45b-108">部署状态</span><span class="sxs-lookup"><span data-stu-id="7e45b-108">Deployment statuses</span></span> 

<span data-ttu-id="7e45b-109">这些状态将针对每个部署显示。</span><span class="sxs-lookup"><span data-stu-id="7e45b-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="7e45b-110">状态</span><span class="sxs-lookup"><span data-stu-id="7e45b-110">Status</span></span>  | <span data-ttu-id="7e45b-111">说明</span><span class="sxs-lookup"><span data-stu-id="7e45b-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="7e45b-112">部署</span><span class="sxs-lookup"><span data-stu-id="7e45b-112">Deploy</span></span> | <span data-ttu-id="7e45b-113">您的更改正在等待部署到此组。</span><span class="sxs-lookup"><span data-stu-id="7e45b-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="7e45b-114">正在进行</span><span class="sxs-lookup"><span data-stu-id="7e45b-114">In progress</span></span> | <span data-ttu-id="7e45b-115">更改将应用于此组的活动设备。</span><span class="sxs-lookup"><span data-stu-id="7e45b-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="7e45b-116">完成</span><span class="sxs-lookup"><span data-stu-id="7e45b-116">Complete</span></span> | <span data-ttu-id="7e45b-117">此组中所有活动设备上完成更改。</span><span class="sxs-lookup"><span data-stu-id="7e45b-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="7e45b-118">已失败</span><span class="sxs-lookup"><span data-stu-id="7e45b-118">Failed</span></span> | <span data-ttu-id="7e45b-119">更改在组中 10% 的活动设备上失败，因此部署已停止。</span><span class="sxs-lookup"><span data-stu-id="7e45b-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="7e45b-120">将自动使用 Microsoft 托管桌面操作打开支持请求，以对部署进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="7e45b-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="7e45b-121">已还原</span><span class="sxs-lookup"><span data-stu-id="7e45b-121">Reverted</span></span> | <span data-ttu-id="7e45b-122">更改已还原为已成功部署到所有部署组的最后一个更改。</span><span class="sxs-lookup"><span data-stu-id="7e45b-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="7e45b-123">部署更改</span><span class="sxs-lookup"><span data-stu-id="7e45b-123">Deploy changes</span></span>

<span data-ttu-id="7e45b-124">我们将在这些说明中显示桌面背景图片。</span><span class="sxs-lookup"><span data-stu-id="7e45b-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="7e45b-125">在部署阶段后，从"部署状态"页部署更改。</span><span class="sxs-lookup"><span data-stu-id="7e45b-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="7e45b-126">**部署更改**</span><span class="sxs-lookup"><span data-stu-id="7e45b-126">**To deploy changes**</span></span>

1. <span data-ttu-id="7e45b-127">登录到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 并导航到 **"设备"** 菜单</span><span class="sxs-lookup"><span data-stu-id="7e45b-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="7e45b-128">查找"Microsoft 托管桌面"部分，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="7e45b-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="7e45b-129">在 **"部署** 状态工作区"中，选择要部署的设置，然后选择要部署的分步部署。</span><span class="sxs-lookup"><span data-stu-id="7e45b-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="7e45b-130">选择 **"** 部署"将更改部署到其中一个部署组。</span><span class="sxs-lookup"><span data-stu-id="7e45b-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="7e45b-131">橙色警告图标表示有上一个组可供部署，建议按顺序排列。</span><span class="sxs-lookup"><span data-stu-id="7e45b-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="7e45b-132">我们建议按此顺序部署到部署组：Test、First、Fast 和 Broad。</span><span class="sxs-lookup"><span data-stu-id="7e45b-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="7e45b-133">在每个组中完成更改后，状态将更改为 **"完成"。**</span><span class="sxs-lookup"><span data-stu-id="7e45b-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="7e45b-134">还原部署</span><span class="sxs-lookup"><span data-stu-id="7e45b-134">Revert deployment</span></span>

<span data-ttu-id="7e45b-135">部署更改后，可以从部署状态 **还原**。</span><span class="sxs-lookup"><span data-stu-id="7e45b-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="7e45b-136">当还原为"正在进行"或"已完成 **"** 更改时，当前部署将停止。 </span><span class="sxs-lookup"><span data-stu-id="7e45b-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="7e45b-137">该设置将恢复为部署到所有组的上一版本。</span><span class="sxs-lookup"><span data-stu-id="7e45b-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="7e45b-138">我们将以桌面背景图片为例，显示还原更改的步骤。</span><span class="sxs-lookup"><span data-stu-id="7e45b-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="7e45b-139">**还原更改**</span><span class="sxs-lookup"><span data-stu-id="7e45b-139">**To revert a change**</span></span>
1. <span data-ttu-id="7e45b-140">登录到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 并导航到 **"设备"** 菜单</span><span class="sxs-lookup"><span data-stu-id="7e45b-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="7e45b-141">查找"Microsoft 托管桌面"部分，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="7e45b-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="7e45b-142">在 **"部署** 状态工作区"中，选择要还原的设置，然后选择要还原的分步部署。</span><span class="sxs-lookup"><span data-stu-id="7e45b-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="7e45b-143">在 **"需要还原此更改？"下，** 选择"**还原部署"。**</span><span class="sxs-lookup"><span data-stu-id="7e45b-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="7e45b-144">其他资源</span><span class="sxs-lookup"><span data-stu-id="7e45b-144">Additional resources</span></span>
- [<span data-ttu-id="7e45b-145">可配置的设置概述</span><span class="sxs-lookup"><span data-stu-id="7e45b-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="7e45b-146">可配置设置参考</span><span class="sxs-lookup"><span data-stu-id="7e45b-146">Configurable settings reference</span></span>](config-setting-ref.md) 
