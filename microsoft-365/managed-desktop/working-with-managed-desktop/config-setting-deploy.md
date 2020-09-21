---
title: 在 Microsoft 托管桌面中部署可配置的设置
description: 在 Microsoft 托管桌面中部署和跟踪可配置的设置更改。
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档，部署，暂存部署，可配置的设置
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
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="dc9e3-104">部署和跟踪可配置的设置-Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="dc9e3-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="dc9e3-105">在更改设置类别并暂存部署后，"部署状态" 页允许您开始将设置部署到组。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="dc9e3-106">此页面显示每个可配置设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="dc9e3-107">通过打开设置类别，您可以将设置部署到组，并跟踪这些部署的进度。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="dc9e3-108">部署状态</span><span class="sxs-lookup"><span data-stu-id="dc9e3-108">Deployment statuses</span></span> 

<span data-ttu-id="dc9e3-109">这些是你将看到的每个部署的状态。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="dc9e3-110">状态</span><span class="sxs-lookup"><span data-stu-id="dc9e3-110">Status</span></span>  | <span data-ttu-id="dc9e3-111">说明</span><span class="sxs-lookup"><span data-stu-id="dc9e3-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="dc9e3-112">部署</span><span class="sxs-lookup"><span data-stu-id="dc9e3-112">Deploy</span></span> | <span data-ttu-id="dc9e3-113">您的更改正在等待部署到此组。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="dc9e3-114">进行中</span><span class="sxs-lookup"><span data-stu-id="dc9e3-114">In progress</span></span> | <span data-ttu-id="dc9e3-115">正在将更改应用到此组中的活动设备。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="dc9e3-116">完全</span><span class="sxs-lookup"><span data-stu-id="dc9e3-116">Complete</span></span> | <span data-ttu-id="dc9e3-117">此组中所有活动设备上的更改已完成。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="dc9e3-118">已失败</span><span class="sxs-lookup"><span data-stu-id="dc9e3-118">Failed</span></span> | <span data-ttu-id="dc9e3-119">此更改在组中的10% 的活动设备上失败，因此部署已停止。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="dc9e3-120">将使用 Microsoft 托管桌面操作自动打开支持请求，以排除部署故障。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="dc9e3-121">回复</span><span class="sxs-lookup"><span data-stu-id="dc9e3-121">Reverted</span></span> | <span data-ttu-id="dc9e3-122">更改已还原为已成功部署到所有部署组的最后更改。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="dc9e3-123">部署更改</span><span class="sxs-lookup"><span data-stu-id="dc9e3-123">Deploy changes</span></span>

<span data-ttu-id="dc9e3-124">我们将在这些说明中显示桌面背景图片。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="dc9e3-125">暂存部署后，从 "部署状态" 页部署更改。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="dc9e3-126">**部署更改**</span><span class="sxs-lookup"><span data-stu-id="dc9e3-126">**To deploy changes**</span></span>

1. <span data-ttu-id="dc9e3-127">登录到 [Microsoft 终结点管理器](https://endpoint.microsoft.com/) 并导航到 " **设备** " 菜单</span><span class="sxs-lookup"><span data-stu-id="dc9e3-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="dc9e3-128">查找 "Microsoft 托管桌面" 部分，选择 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="dc9e3-129">在 " **部署状态** " 工作区中，选择要部署的设置，然后选择要部署的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="dc9e3-130">选择 " **部署** " 以将更改部署到其中一个部署组。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="dc9e3-131">橙色警告图标表示有一个可供部署的以前的组，因此建议按顺序执行。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="dc9e3-132">我们建议按以下顺序部署到部署组： Test、First、Fast 和广义。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="dc9e3-133">当每个组中的更改完成后，状态将更改为 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="dc9e3-134">还原部署</span><span class="sxs-lookup"><span data-stu-id="dc9e3-134">Revert deployment</span></span>

<span data-ttu-id="dc9e3-135">部署更改后，可以从 **部署状态**恢复。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="dc9e3-136">还原正在 **进行** 或已 **完成**的更改时，当前部署将停止。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="dc9e3-137">设置将还原为所有组部署的最后一个版本。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="dc9e3-138">我们将显示使用桌面背景图片作为示例还原更改的步骤。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="dc9e3-139">**还原更改**</span><span class="sxs-lookup"><span data-stu-id="dc9e3-139">**To revert a change**</span></span>
1. <span data-ttu-id="dc9e3-140">登录到 [Microsoft 终结点管理器](https://endpoint.microsoft.com/) 并导航到 " **设备** " 菜单</span><span class="sxs-lookup"><span data-stu-id="dc9e3-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="dc9e3-141">查找 "Microsoft 托管桌面" 部分，选择 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="dc9e3-142">在 " **部署状态** " 工作区中，选择要还原的设置，然后选择要还原的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="dc9e3-143">在 " **需要还原此更改？**" 下，选择 " **还原部署**"。</span><span class="sxs-lookup"><span data-stu-id="dc9e3-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="dc9e3-144">其他资源</span><span class="sxs-lookup"><span data-stu-id="dc9e3-144">Additional resources</span></span>
- [<span data-ttu-id="dc9e3-145">可配置的设置概述</span><span class="sxs-lookup"><span data-stu-id="dc9e3-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="dc9e3-146">可配置设置参考</span><span class="sxs-lookup"><span data-stu-id="dc9e3-146">Configurable settings reference</span></span>](config-setting-ref.md) 
