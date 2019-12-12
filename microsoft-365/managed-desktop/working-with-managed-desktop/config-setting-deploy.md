---
title: 在 Microsoft 托管桌面中部署可配置的设置
description: 在 Microsoft 托管桌面中部署和跟踪可配置的设置更改。
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档，部署，暂存部署，可配置的设置
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 244070c7fd2d5c98f87990bcb4ef6de96ca5a90c
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962239"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="fbb04-104">部署和跟踪可配置的设置-Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="fbb04-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="fbb04-105">在更改设置类别并暂存部署后，"部署状态" 页允许您开始将设置部署到组。</span><span class="sxs-lookup"><span data-stu-id="fbb04-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="fbb04-106">此页面显示每个可配置设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="fbb04-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="fbb04-107">通过打开设置类别，您可以将设置部署到组，并跟踪这些部署的进度。</span><span class="sxs-lookup"><span data-stu-id="fbb04-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="fbb04-108">部署状态</span><span class="sxs-lookup"><span data-stu-id="fbb04-108">Deployment statuses</span></span> 

<span data-ttu-id="fbb04-109">这些是你将看到的每个部署的状态。</span><span class="sxs-lookup"><span data-stu-id="fbb04-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="fbb04-110">状态</span><span class="sxs-lookup"><span data-stu-id="fbb04-110">Status</span></span>  | <span data-ttu-id="fbb04-111">说明</span><span class="sxs-lookup"><span data-stu-id="fbb04-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="fbb04-112">部署</span><span class="sxs-lookup"><span data-stu-id="fbb04-112">Deploy</span></span> | <span data-ttu-id="fbb04-113">您的更改正在等待部署到此组。</span><span class="sxs-lookup"><span data-stu-id="fbb04-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="fbb04-114">进行中</span><span class="sxs-lookup"><span data-stu-id="fbb04-114">In progress</span></span> | <span data-ttu-id="fbb04-115">正在将更改应用到此组中的活动设备。</span><span class="sxs-lookup"><span data-stu-id="fbb04-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="fbb04-116">完全</span><span class="sxs-lookup"><span data-stu-id="fbb04-116">Complete</span></span> | <span data-ttu-id="fbb04-117">此组中所有活动设备上的更改已完成。</span><span class="sxs-lookup"><span data-stu-id="fbb04-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="fbb04-118">已失败</span><span class="sxs-lookup"><span data-stu-id="fbb04-118">Failed</span></span> | <span data-ttu-id="fbb04-119">此更改在组中的10% 的活动设备上失败，因此部署已停止。</span><span class="sxs-lookup"><span data-stu-id="fbb04-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="fbb04-120">将使用 Microsoft 托管桌面操作自动打开支持请求，以排除部署故障。</span><span class="sxs-lookup"><span data-stu-id="fbb04-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="fbb04-121">回复</span><span class="sxs-lookup"><span data-stu-id="fbb04-121">Reverted</span></span> | <span data-ttu-id="fbb04-122">更改已还原为已成功部署到所有部署组的最后更改。</span><span class="sxs-lookup"><span data-stu-id="fbb04-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="fbb04-123">部署更改</span><span class="sxs-lookup"><span data-stu-id="fbb04-123">Deploy changes</span></span>

<span data-ttu-id="fbb04-124">我们将在这些说明中显示桌面背景图片。</span><span class="sxs-lookup"><span data-stu-id="fbb04-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="fbb04-125">暂存部署后，从 "部署状态" 页部署更改。</span><span class="sxs-lookup"><span data-stu-id="fbb04-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="fbb04-126">**部署更改**</span><span class="sxs-lookup"><span data-stu-id="fbb04-126">**To deploy changes**</span></span>

1. <span data-ttu-id="fbb04-127">登录到[Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="fbb04-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="fbb04-128">在 "**设置**" 下，选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="fbb04-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="fbb04-129">在 "**部署状态**" 工作区中，选择要部署的设置，然后选择要部署的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="fbb04-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="fbb04-130">选择 "**部署**" 以将更改部署到其中一个部署组。</span><span class="sxs-lookup"><span data-stu-id="fbb04-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="fbb04-131">![部署状态工作区。</span><span class="sxs-lookup"><span data-stu-id="fbb04-131">![Deployment status workspace.</span></span> <span data-ttu-id="fbb04-132">右侧的 "受信任的网站" 窗格。</span><span class="sxs-lookup"><span data-stu-id="fbb04-132">Trusted sites pane on the right.</span></span> <span data-ttu-id="fbb04-133">"部署组" 部分包含三列：部署组、设备和状态。</span><span class="sxs-lookup"><span data-stu-id="fbb04-133">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="fbb04-134">在 "状态" 列中，突出显示 "部署"。](images/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="fbb04-134">In the status column, "deploy" is highlighted.](images/1deployedit.png)</span></span>
<span data-ttu-id="fbb04-135">我们建议按以下顺序部署到部署组： Test、First、Fast 和广义。</span><span class="sxs-lookup"><span data-stu-id="fbb04-135">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="fbb04-136">当每个组中的更改完成后，状态将更改为 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="fbb04-136">When changes complete in each group, the status changes to **Complete**.</span></span>

![包含日期更新、版本、测试、首、快速和广泛的列的部署状态工作区。](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="fbb04-139">还原部署</span><span class="sxs-lookup"><span data-stu-id="fbb04-139">Revert deployment</span></span>

<span data-ttu-id="fbb04-140">部署更改后，可以从**部署状态**恢复。</span><span class="sxs-lookup"><span data-stu-id="fbb04-140">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="fbb04-141">还原正在**进行**或已**完成**的更改时，当前部署将停止。</span><span class="sxs-lookup"><span data-stu-id="fbb04-141">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="fbb04-142">设置将还原为所有组部署的最后一个版本。</span><span class="sxs-lookup"><span data-stu-id="fbb04-142">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="fbb04-143">我们将显示使用桌面背景图片作为示例还原更改的步骤。</span><span class="sxs-lookup"><span data-stu-id="fbb04-143">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="fbb04-144">**还原更改**</span><span class="sxs-lookup"><span data-stu-id="fbb04-144">**To revert a change**</span></span>
1. <span data-ttu-id="fbb04-145">登录到[Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="fbb04-145">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="fbb04-146">在 "**设置**" 下，选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="fbb04-146">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="fbb04-147">在 "**部署状态**" 工作区中，选择要还原的设置，然后选择要还原的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="fbb04-147">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="fbb04-148">在 "**需要还原此更改？**" 下，选择 "**还原部署**"。</span><span class="sxs-lookup"><span data-stu-id="fbb04-148">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![部署状态工作区。](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="fbb04-152">其他资源</span><span class="sxs-lookup"><span data-stu-id="fbb04-152">Additional resources</span></span>
- [<span data-ttu-id="fbb04-153">可配置的设置概述</span><span class="sxs-lookup"><span data-stu-id="fbb04-153">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="fbb04-154">可配置设置参考</span><span class="sxs-lookup"><span data-stu-id="fbb04-154">Configurable settings reference</span></span>](config-setting-ref.md) 
