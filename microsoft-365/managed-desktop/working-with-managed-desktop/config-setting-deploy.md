---
title: 在 Microsoft 托管桌面中部署可配置的设置
description: 在 Microsoft 托管桌面中部署和跟踪可配置的设置更改。
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档，部署，暂存部署，可配置的设置
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e6946c138cb6fde15e35374b447038d5c302187e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085745"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="22b12-104">部署和跟踪可配置的设置-Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="22b12-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="22b12-105">在更改设置类别并暂存部署后，"部署状态" 页允许您开始将设置部署到组。</span><span class="sxs-lookup"><span data-stu-id="22b12-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="22b12-106">此页面显示每个可配置设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="22b12-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="22b12-107">通过打开设置类别，您可以将设置部署到组，并跟踪这些部署的进度。</span><span class="sxs-lookup"><span data-stu-id="22b12-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="22b12-108">部署状态</span><span class="sxs-lookup"><span data-stu-id="22b12-108">Deployment statuses</span></span> 

<span data-ttu-id="22b12-109">这些是你将看到的每个部署的状态。</span><span class="sxs-lookup"><span data-stu-id="22b12-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="22b12-110">状态</span><span class="sxs-lookup"><span data-stu-id="22b12-110">Status</span></span>  | <span data-ttu-id="22b12-111">说明</span><span class="sxs-lookup"><span data-stu-id="22b12-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="22b12-112">部署</span><span class="sxs-lookup"><span data-stu-id="22b12-112">Deploy</span></span> | <span data-ttu-id="22b12-113">您的更改正在等待部署到此组。</span><span class="sxs-lookup"><span data-stu-id="22b12-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="22b12-114">进行中</span><span class="sxs-lookup"><span data-stu-id="22b12-114">In progress</span></span> | <span data-ttu-id="22b12-115">正在将更改应用到此组中的活动设备。</span><span class="sxs-lookup"><span data-stu-id="22b12-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="22b12-116">完全</span><span class="sxs-lookup"><span data-stu-id="22b12-116">Complete</span></span> | <span data-ttu-id="22b12-117">此组中所有活动设备上的更改已完成。</span><span class="sxs-lookup"><span data-stu-id="22b12-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="22b12-118">Failed</span><span class="sxs-lookup"><span data-stu-id="22b12-118">Failed</span></span> | <span data-ttu-id="22b12-119">此更改在组中的10% 的活动设备上失败，因此部署已停止。</span><span class="sxs-lookup"><span data-stu-id="22b12-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="22b12-120">将使用 Microsoft 托管桌面操作自动打开支持请求，以排除部署故障。</span><span class="sxs-lookup"><span data-stu-id="22b12-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="22b12-121">回复</span><span class="sxs-lookup"><span data-stu-id="22b12-121">Reverted</span></span> | <span data-ttu-id="22b12-122">更改已还原为已成功部署到所有部署组的最后更改。</span><span class="sxs-lookup"><span data-stu-id="22b12-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="22b12-123">部署更改</span><span class="sxs-lookup"><span data-stu-id="22b12-123">Deploy changes</span></span>

<span data-ttu-id="22b12-124">我们将在这些说明中显示桌面背景图片。</span><span class="sxs-lookup"><span data-stu-id="22b12-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="22b12-125">暂存部署后，从 "部署状态" 页部署更改。</span><span class="sxs-lookup"><span data-stu-id="22b12-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="22b12-126">**部署更改**</span><span class="sxs-lookup"><span data-stu-id="22b12-126">**To deploy changes**</span></span>

1. <span data-ttu-id="22b12-127">登录到[Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="22b12-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="22b12-128">在 "**设置**" 下，选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="22b12-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="22b12-129">在 "**部署状态**" 工作区中，选择要部署的设置，然后选择要部署的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="22b12-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="22b12-130">选择 "**部署**" 以将更改部署到其中一个部署组。</span><span class="sxs-lookup"><span data-stu-id="22b12-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="22b12-131">橙色警告图标表示有一个可供部署的以前的组，因此建议按顺序执行。</span><span class="sxs-lookup"><span data-stu-id="22b12-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<span data-ttu-id="22b12-132">![部署状态工作区。</span><span class="sxs-lookup"><span data-stu-id="22b12-132">![Deployment status workspace.</span></span> <span data-ttu-id="22b12-133">右侧的 "受信任的网站" 窗格。</span><span class="sxs-lookup"><span data-stu-id="22b12-133">Trusted sites pane on the right.</span></span> <span data-ttu-id="22b12-134">"部署组" 部分包含三列：部署组、设备和状态。</span><span class="sxs-lookup"><span data-stu-id="22b12-134">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="22b12-135">在 "状态" 列中，突出显示 "部署"。](../../media/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="22b12-135">In the status column, "deploy" is highlighted.](../../media/1deployedit.png)</span></span>
<span data-ttu-id="22b12-136">我们建议按以下顺序部署到部署组： Test、First、Fast 和广义。</span><span class="sxs-lookup"><span data-stu-id="22b12-136">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="22b12-137">当每个组中的更改完成后，状态将更改为 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="22b12-137">When changes complete in each group, the status changes to **Complete**.</span></span>

![包含日期更新、版本、测试、首、快速和广泛的列的部署状态工作区。](../../media/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="22b12-140">还原部署</span><span class="sxs-lookup"><span data-stu-id="22b12-140">Revert deployment</span></span>

<span data-ttu-id="22b12-141">部署更改后，可以从**部署状态**恢复。</span><span class="sxs-lookup"><span data-stu-id="22b12-141">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="22b12-142">还原正在**进行**或已**完成**的更改时，当前部署将停止。</span><span class="sxs-lookup"><span data-stu-id="22b12-142">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="22b12-143">设置将还原为所有组部署的最后一个版本。</span><span class="sxs-lookup"><span data-stu-id="22b12-143">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="22b12-144">我们将显示使用桌面背景图片作为示例还原更改的步骤。</span><span class="sxs-lookup"><span data-stu-id="22b12-144">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="22b12-145">**还原更改**</span><span class="sxs-lookup"><span data-stu-id="22b12-145">**To revert a change**</span></span>
1. <span data-ttu-id="22b12-146">登录到[Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="22b12-146">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="22b12-147">在 "**设置**" 下，选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="22b12-147">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="22b12-148">在 "**部署状态**" 工作区中，选择要还原的设置，然后选择要还原的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="22b12-148">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="22b12-149">在 "**需要还原此更改？**" 下，选择 "**还原部署**"。</span><span class="sxs-lookup"><span data-stu-id="22b12-149">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![部署状态工作区。](../../media/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="22b12-153">其他资源</span><span class="sxs-lookup"><span data-stu-id="22b12-153">Additional resources</span></span>
- [<span data-ttu-id="22b12-154">可配置的设置概述</span><span class="sxs-lookup"><span data-stu-id="22b12-154">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="22b12-155">可配置设置参考</span><span class="sxs-lookup"><span data-stu-id="22b12-155">Configurable settings reference</span></span>](config-setting-ref.md) 
