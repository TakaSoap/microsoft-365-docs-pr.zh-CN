---
title: 在 Microsoft 托管桌面中部署可配置的设置
description: 在 Microsoft 托管桌面中部署和跟踪可配置的设置更改。
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档, 部署, 暂存部署, 可配置的设置
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/12/2019
ms.openlocfilehash: fd0e0750332fa8f650cfc4756f8eb108be2a71df
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051123"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="64caf-104">部署和跟踪可配置的设置-Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="64caf-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="64caf-p101">在更改设置类别并暂存部署后, 您可以部署和跟踪部署状态的部署进度。此页面显示每个可配置设置的摘要。打开设置类别以查看每个部署及其详细信息, 以部署更改。</span><span class="sxs-lookup"><span data-stu-id="64caf-p101">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status. This page shows a summary of each configurable setting. Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="64caf-108">部署状态</span><span class="sxs-lookup"><span data-stu-id="64caf-108">Deployment statuses</span></span> 

<span data-ttu-id="64caf-109">这些是你将看到的每个部署的 statues。</span><span class="sxs-lookup"><span data-stu-id="64caf-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="64caf-110">状态</span><span class="sxs-lookup"><span data-stu-id="64caf-110">Status</span></span>  | <span data-ttu-id="64caf-111">说明</span><span class="sxs-lookup"><span data-stu-id="64caf-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="64caf-112">部署</span><span class="sxs-lookup"><span data-stu-id="64caf-112">Deploy</span></span> | <span data-ttu-id="64caf-113">您所做的更改正在等待部署到此环。</span><span class="sxs-lookup"><span data-stu-id="64caf-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="64caf-114">正在进行</span><span class="sxs-lookup"><span data-stu-id="64caf-114">In progress</span></span> | <span data-ttu-id="64caf-115">正在将更改应用到此环中的设备。</span><span class="sxs-lookup"><span data-stu-id="64caf-115">The change is being applied to devices in this ring.</span></span> 
<span data-ttu-id="64caf-116">完全</span><span class="sxs-lookup"><span data-stu-id="64caf-116">Complete</span></span> | <span data-ttu-id="64caf-117">正在将更改应用到此环中的设备。</span><span class="sxs-lookup"><span data-stu-id="64caf-117">The change is being applied to devices in this ring.</span></span> 
<span data-ttu-id="64caf-118">Failed</span><span class="sxs-lookup"><span data-stu-id="64caf-118">Failed</span></span> | <span data-ttu-id="64caf-119">更改在环中的 10% 设备上失败, 因此部署已停止。</span><span class="sxs-lookup"><span data-stu-id="64caf-119">The change failed on a 10 percent of devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="64caf-120">将使用 Microsoft 托管桌面操作自动打开支持请求, 以排除部署故障。</span><span class="sxs-lookup"><span data-stu-id="64caf-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="64caf-121">回复</span><span class="sxs-lookup"><span data-stu-id="64caf-121">Reverted</span></span> | <span data-ttu-id="64caf-122">更改已恢复为已成功部署到所有部署环的最后一次更改。</span><span class="sxs-lookup"><span data-stu-id="64caf-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="64caf-123">部署更改</span><span class="sxs-lookup"><span data-stu-id="64caf-123">Deploy changes</span></span>

<span data-ttu-id="64caf-p102">我们将在这些说明中显示桌面背景图片。暂存部署后, 从部署状态部署更改。</span><span class="sxs-lookup"><span data-stu-id="64caf-p102">We’ll show Desktop background picture in these instructions. After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="64caf-126">**部署更改**</span><span class="sxs-lookup"><span data-stu-id="64caf-126">**To deploy changes**</span></span>

1. <span data-ttu-id="64caf-127">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="64caf-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="64caf-128">在 "**设置**" 下, 选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="64caf-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="64caf-129">在 "**部署状态**" 工作区中, 选择要部署的设置, 然后选择要部署的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="64caf-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="64caf-130">选择 "**部署**" 以将更改部署到某个部署环中。</span><span class="sxs-lookup"><span data-stu-id="64caf-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![可配置的设置部署状态概述](images/deploy-cs-overview.png)

<span data-ttu-id="64caf-132">Microsoft 托管桌面建议按此顺序部署到部署环: Test、First、Fast 和广义。</span><span class="sxs-lookup"><span data-stu-id="64caf-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="64caf-133">当每个环中的更改完成时, 状态将更改为 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="64caf-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![可配置的设置部署完成](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="64caf-135">还原部署</span><span class="sxs-lookup"><span data-stu-id="64caf-135">Revert deployment</span></span>

<span data-ttu-id="64caf-136">我们将在这些说明中显示桌面背景图片。</span><span class="sxs-lookup"><span data-stu-id="64caf-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="64caf-p103">部署更改后, 可以从**部署状态**恢复。还原正在**进行**或已**完成**的更改时, 当前部署将停止。设置将还原为所有环部署的最后一个版本。</span><span class="sxs-lookup"><span data-stu-id="64caf-p103">After you’ve deployed a change, you can revert from **Deployment status**. When you revert a change that is **In progress** or **Complete**, the current deployment stops. The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="64caf-140">**还原更改**</span><span class="sxs-lookup"><span data-stu-id="64caf-140">**To revert a change**</span></span>
1. <span data-ttu-id="64caf-141">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="64caf-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="64caf-142">在 "**设置**" 下, 选择 "**可配置**"。</span><span class="sxs-lookup"><span data-stu-id="64caf-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="64caf-143">在 "**部署状态**" 工作区中, 选择要还原的设置, 然后选择要还原的暂存部署。</span><span class="sxs-lookup"><span data-stu-id="64caf-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="64caf-144">在 "**需要还原此更改**" 下, 选择 "**还原部署**"。</span><span class="sxs-lookup"><span data-stu-id="64caf-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![可配置的设置部署还原](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="64caf-146">其他资源</span><span class="sxs-lookup"><span data-stu-id="64caf-146">Additional resources</span></span>
- [<span data-ttu-id="64caf-147">可配置的设置概述</span><span class="sxs-lookup"><span data-stu-id="64caf-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="64caf-148">可配置的设置参考</span><span class="sxs-lookup"><span data-stu-id="64caf-148">Configurable settings reference</span></span>](config-setting-ref.md) 