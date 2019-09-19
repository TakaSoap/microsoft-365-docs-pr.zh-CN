---
title: 在 Microsoft 托管桌面中部署可配置的设置
description: 在 Microsoft 托管桌面中部署和跟踪可配置的设置更改。
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档，部署，暂存部署，可配置的设置
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5b6a2756514e94cb4f96141d6e7c9f6f2a6dd7ff
ms.sourcegitcommit: a4657a499967751d4c2dfc6cd1904258ab8be193
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "37040787"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="95f48-104">部署和跟踪可配置的设置-Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="95f48-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="95f48-105">在更改设置类别并暂存部署后，"部署状态" 页允许您开始将设置部署到组。</span><span class="sxs-lookup"><span data-stu-id="95f48-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="95f48-106">此页面显示每个可配置设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="95f48-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="95f48-107">通过打开设置类别，您可以将设置部署到组，并跟踪这些部署的进度。</span><span class="sxs-lookup"><span data-stu-id="95f48-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="95f48-108">部署状态</span><span class="sxs-lookup"><span data-stu-id="95f48-108">Deployment statuses</span></span> 

<span data-ttu-id="95f48-109">这些是你将看到的每个部署的状态。</span><span class="sxs-lookup"><span data-stu-id="95f48-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="95f48-110">状态</span><span class="sxs-lookup"><span data-stu-id="95f48-110">Status</span></span>  | <span data-ttu-id="95f48-111">说明</span><span class="sxs-lookup"><span data-stu-id="95f48-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="95f48-112">部署</span><span class="sxs-lookup"><span data-stu-id="95f48-112">Deploy</span></span> | <span data-ttu-id="95f48-113">您的更改正在等待部署到此组。</span><span class="sxs-lookup"><span data-stu-id="95f48-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="95f48-114">进行中</span><span class="sxs-lookup"><span data-stu-id="95f48-114">In progress</span></span> | <span data-ttu-id="95f48-115">正在将更改应用到此组中的活动设备。</span><span class="sxs-lookup"><span data-stu-id="95f48-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="95f48-116">完全</span><span class="sxs-lookup"><span data-stu-id="95f48-116">Complete</span></span> | <span data-ttu-id="95f48-117">此组中所有活动设备上的更改已完成。</span><span class="sxs-lookup"><span data-stu-id="95f48-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="95f48-118">Failed</span><span class="sxs-lookup"><span data-stu-id="95f48-118">Failed</span></span> | <span data-ttu-id="95f48-119">此更改在组中的 10% 的活动设备上失败，因此部署已停止。</span><span class="sxs-lookup"><span data-stu-id="95f48-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="95f48-120">将使用 Microsoft 托管桌面操作自动打开支持请求，以排除部署故障。</span><span class="sxs-lookup"><span data-stu-id="95f48-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="95f48-121">回复</span><span class="sxs-lookup"><span data-stu-id="95f48-121">Reverted</span></span> | <span data-ttu-id="95f48-122">更改已还原为已成功部署到所有部署组的最后更改。</span><span class="sxs-lookup"><span data-stu-id="95f48-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="95f48-123">部署更改</span><span class="sxs-lookup"><span data-stu-id="95f48-123">Deploy changes</span></span>

<span data-ttu-id="95f48-124">我们将在这些说明中显示桌面背景图片。</span><span class="sxs-lookup"><span data-stu-id="95f48-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="95f48-125">暂存部署后，从 "部署状态" 页部署更改。</span><span class="sxs-lookup"><span data-stu-id="95f48-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="95f48-126">**部署更改**</span><span class="sxs-lookup"><span data-stu-id="95f48-126">**To deploy changes**</span></span>

1. <span data-ttu-id="95f48-127">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="95f48-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="95f48-128">在 "**设置**" 下，选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="95f48-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="95f48-129">在 "**部署状态**" 工作区中，选择要部署的设置，然后选择要部署的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="95f48-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="95f48-130">选择 "**部署**" 以将更改部署到其中一个部署组。</span><span class="sxs-lookup"><span data-stu-id="95f48-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="95f48-131">![可配置的设置部署](images/1deployedit.png)状态概述 Microsoft 托管桌面建议按此顺序部署到部署组： Test、First、Fast 和广义。</span><span class="sxs-lookup"><span data-stu-id="95f48-131">![Configurable settings deployment status overview](images/1deployedit.png) Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="95f48-132">当每个组中的更改完成后，状态将更改为 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="95f48-132">When changes complete in each group, the status changes to **Complete**.</span></span>

![可配置的设置部署完成](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="95f48-134">还原部署</span><span class="sxs-lookup"><span data-stu-id="95f48-134">Revert deployment</span></span>

<span data-ttu-id="95f48-135">部署更改后，可以从**部署状态**恢复。</span><span class="sxs-lookup"><span data-stu-id="95f48-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="95f48-136">还原正在**进行**或已**完成**的更改时，当前部署将停止。</span><span class="sxs-lookup"><span data-stu-id="95f48-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="95f48-137">设置将还原为所有组部署的最后一个版本。</span><span class="sxs-lookup"><span data-stu-id="95f48-137">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="95f48-138">我们将显示使用桌面背景图片作为示例还原更改的步骤。</span><span class="sxs-lookup"><span data-stu-id="95f48-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="95f48-139">**还原更改**</span><span class="sxs-lookup"><span data-stu-id="95f48-139">**To revert a change**</span></span>
1. <span data-ttu-id="95f48-140">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="95f48-140">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="95f48-141">在 "**设置**" 下，选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="95f48-141">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="95f48-142">在 "**部署状态**" 工作区中，选择要还原的设置，然后选择要还原的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="95f48-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="95f48-143">在 "**需要还原此更改**" 下，选择 "**还原部署**"。</span><span class="sxs-lookup"><span data-stu-id="95f48-143">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![可配置的设置部署还原](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="95f48-145">其他资源</span><span class="sxs-lookup"><span data-stu-id="95f48-145">Additional resources</span></span>
- [<span data-ttu-id="95f48-146">可配置的设置概述</span><span class="sxs-lookup"><span data-stu-id="95f48-146">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="95f48-147">可配置的设置参考</span><span class="sxs-lookup"><span data-stu-id="95f48-147">Configurable settings reference</span></span>](config-setting-ref.md) 
