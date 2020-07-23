---
title: 最新版本的广泛部署示例
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: 部署最新版本的组织如何使用 Windows 10 和 Microsoft 365 应用的频道。
ms.openlocfilehash: 46f36a7bd26ef190aca2a63fdaa993e420988b30
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200100"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a><span data-ttu-id="915cc-103">最新版本的广泛部署示例</span><span class="sxs-lookup"><span data-stu-id="915cc-103">Example of broad deployment for the latest releases</span></span>

<span data-ttu-id="915cc-104">此频道配置示例适用于使用最新版本的快速部署来满足这些业务优先级的组织：</span><span class="sxs-lookup"><span data-stu-id="915cc-104">This channel configuration example is for an organization that uses rapid deployment of the latest releases to fit these business priorities:</span></span>

- <span data-ttu-id="915cc-105">使用 Microsoft 应用和服务来确保业务连续性。</span><span class="sxs-lookup"><span data-stu-id="915cc-105">Ensure business continuity with Microsoft apps and services.</span></span>
- <span data-ttu-id="915cc-106">使用 Microsoft 的最新功能和修补程序，最大限度地提高设备、服务和数据安全性。</span><span class="sxs-lookup"><span data-stu-id="915cc-106">Maximize device, service, and data security with the latest features and fixes from Microsoft.</span></span>
- <span data-ttu-id="915cc-107">使用 Microsoft 的最新功能最大限度地提高用户的工作效率。</span><span class="sxs-lookup"><span data-stu-id="915cc-107">Maximize user productivity with the latest features from Microsoft.</span></span>

<span data-ttu-id="915cc-108">这些目标转化为IT任务，即在快速生产部署和早期审查之间找到平衡，并在广泛部署之前与用户和设备的代表性子集一起进行功能验证。</span><span class="sxs-lookup"><span data-stu-id="915cc-108">These goals translate to the IT task of finding the balance between rapid production deployment and early vetting with a representative subset of users and devices to validate functionally before broad deployment.</span></span>

<span data-ttu-id="915cc-109">我们的示例组织在欧洲、非洲、亚洲和美洲各地的大楼中有5000名员工。</span><span class="sxs-lookup"><span data-stu-id="915cc-109">Our example organization has 5,000 employees in buildings across the world in Europe, Africa, Asia, and the Americas.</span></span> <span data-ttu-id="915cc-110">组织中 70% 的员工使用 Microsoft 365 E3，其余的员工则使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="915cc-110">70% of the employees use Microsoft 365 E3 and the rest of the organization uses Microsoft 365 E5.</span></span>

>[!Note]
><span data-ttu-id="915cc-111">此示例旨在向你展示如何使用部署阶段和组，它们可用于多种类型和规模的组织。</span><span class="sxs-lookup"><span data-stu-id="915cc-111">This example is designed to show you how you can use deployment stages and groups, which can work for organizations of many types and sizes.</span></span>
>

<span data-ttu-id="915cc-112">此组织的 IT 基础结构：</span><span class="sxs-lookup"><span data-stu-id="915cc-112">This organization's IT infrastructure:</span></span> 

- <span data-ttu-id="915cc-113">很大程度上是同质的，Windows、Microsoft 365 应用版和 Microsoft 云服务占安装基础的60%。</span><span class="sxs-lookup"><span data-stu-id="915cc-113">Is largely homogeneous, with Windows, Microsoft 365 Apps, and Microsoft cloud services comprising 60% of the installed base.</span></span> <span data-ttu-id="915cc-114">经过多年的努力简化 IT 基础设施，一些旧版系统仍然存在。</span><span class="sxs-lookup"><span data-stu-id="915cc-114">A few legacy systems remain after an intensive, multi-year effort to simplify and streamline the IT infrastructure.</span></span>
- <span data-ttu-id="915cc-115">由经验丰富的员工负责维护，其任务是在发布版本中遵循 Microsoft 的做法，保持用户及其设备的高效性和安全性。</span><span class="sxs-lookup"><span data-stu-id="915cc-115">Is maintained by highly experienced staff and tasked with keeping users and their devices productive and secure by following Microsoft’s lead in their releases.</span></span>

## <a name="deployment-and-update-stages"></a><span data-ttu-id="915cc-116">部署和更新阶段</span><span class="sxs-lookup"><span data-stu-id="915cc-116">Deployment and update stages</span></span>

<span data-ttu-id="915cc-117">根据最新版本的快速部署目标，此示例组织使用两步部署过程。</span><span class="sxs-lookup"><span data-stu-id="915cc-117">Based on rapid deployment goals of the latest release, this example organization uses a two-step deployment process.</span></span>

1. <span data-ttu-id="915cc-118">**使用预览或试点部署：** 与早期采用者、IT 人员、拥有代表配置的用户，和培训人员一起验证和迭代。</span><span class="sxs-lookup"><span data-stu-id="915cc-118">**Use a preview or pilot deployment:** Validate and iterate with early adopters, IT staff, users with representative configurations, and training staff.</span></span> 

   <span data-ttu-id="915cc-119">在新功能推出到组织的其余部分之前，早期采用者、IT 职员、和拥有代表配置的用户可与其他应用和设备验证功能。</span><span class="sxs-lookup"><span data-stu-id="915cc-119">The early adopters, IT staff, users with representative configurations can validate functionality with other apps and on devices before the new features roll out to the rest of the organization.</span></span>

   <span data-ttu-id="915cc-120">更改管理员在大范围推出新功能前，会提前了解新功能，并可以计划消息传递和推出。</span><span class="sxs-lookup"><span data-stu-id="915cc-120">Change managers have an early peek at the new features before widespread rollout and can plan messaging and rollout.</span></span>

   <span data-ttu-id="915cc-121">在大范围推出前，培训人员可规划新内部课程或为新功能更新现有课程。</span><span class="sxs-lookup"><span data-stu-id="915cc-121">Training staff can plan new internal courses or update existing courses for the new features before widespread rollout.</span></span>

2. <span data-ttu-id="915cc-122">**生产部署** 按区域、部门或其他部署方法向所有剩余用户推出。</span><span class="sxs-lookup"><span data-stu-id="915cc-122">**Production deployment:** Roll out to all remaining users by region, department, or other deployment method.</span></span>

## <a name="deployment-configuration-for-windows-10"></a><span data-ttu-id="915cc-123">为 Windows 10 部署配置</span><span class="sxs-lookup"><span data-stu-id="915cc-123">Deployment configuration for Windows 10</span></span>

<span data-ttu-id="915cc-124">总体目标是在一组代表用户验证发布预览频道更改后，广泛部署最新的半年频道版本。</span><span class="sxs-lookup"><span data-stu-id="915cc-124">The overall goal is to perform a broad deployment of the latest Semi-Annual Channel release after validation of Release Preview Channel changes by a group of representative users and their devices.</span></span>

<span data-ttu-id="915cc-125">了解更多关于 Windows 10 部署方法和策略的信息，请参阅[Windows 10 部署](https://docs.microsoft.com/windows/deployment/)。</span><span class="sxs-lookup"><span data-stu-id="915cc-125">See [Windows 10 deployment](https://docs.microsoft.com/windows/deployment/) for more information on Windows 10 deployment methods and strategies.</span></span>

| <span data-ttu-id="915cc-126">阶段</span><span class="sxs-lookup"><span data-stu-id="915cc-126">Stage</span></span> | <span data-ttu-id="915cc-127">频道</span><span class="sxs-lookup"><span data-stu-id="915cc-127">Channel</span></span> | <span data-ttu-id="915cc-128">部署组</span><span class="sxs-lookup"><span data-stu-id="915cc-128">Deployment group</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="915cc-129">试点</span><span class="sxs-lookup"><span data-stu-id="915cc-129">Pilot</span></span> |  <span data-ttu-id="915cc-130">**发布预览频道**</span><span class="sxs-lookup"><span data-stu-id="915cc-130">**Release Preview Channel**</span></span>  <ul><li><span data-ttu-id="915cc-131">目的：将功能更新部署到 IT 人员和早期采用者，用于验证代表设备和配置（语言、第三方应用）。</span><span class="sxs-lookup"><span data-stu-id="915cc-131">Purpose: Deployment of feature updates to IT staff and early adopters for validation on representative devices and configurations (languages, 3rd party apps).</span></span> </li><li> <span data-ttu-id="915cc-132">状态：对商业客户完全兼容和支持，不会与支持的协议对立。</span><span class="sxs-lookup"><span data-stu-id="915cc-132">State: Fully compliant and supported for commercial customers and it does not count against your support agreements.</span></span> </li></ul> | <span data-ttu-id="915cc-133">**Win10ReleasePreviewChannel**（示例名称）</span><span class="sxs-lookup"><span data-stu-id="915cc-133">**Win10ReleasePreviewChannel** (example name)</span></span> <br><br> <span data-ttu-id="915cc-134">成员是包含以下内容的组：</span><span class="sxs-lookup"><span data-stu-id="915cc-134">Members are groups containing:</span></span> <ul><li> <span data-ttu-id="915cc-135">跨部门和位置的 Windows 应用爱好者</span><span class="sxs-lookup"><span data-stu-id="915cc-135">Windows enthusiasts across departments and locations</span></span> </li><li> <span data-ttu-id="915cc-136">配置需要验证的职员</span><span class="sxs-lookup"><span data-stu-id="915cc-136">Staff with configurations that need validation</span></span> </li><li> <span data-ttu-id="915cc-137">IT 管理员和 IT 部署职员</span><span class="sxs-lookup"><span data-stu-id="915cc-137">IT admins and IT deployment staff</span></span> </li><li> <span data-ttu-id="915cc-138">更换经理</span><span class="sxs-lookup"><span data-stu-id="915cc-138">Change managers</span></span> </li><li> <span data-ttu-id="915cc-139">内部培训人员</span><span class="sxs-lookup"><span data-stu-id="915cc-139">Internal training staff</span></span> </li></ul> |
| <span data-ttu-id="915cc-140">生产</span><span class="sxs-lookup"><span data-stu-id="915cc-140">Production</span></span> |  <span data-ttu-id="915cc-141">**半年频道**</span><span class="sxs-lookup"><span data-stu-id="915cc-141">**Semi-Annual Channel**</span></span>  <ul><li><span data-ttu-id="915cc-142">目的：将最新功能更新广泛部署到组织的其他部分。</span><span class="sxs-lookup"><span data-stu-id="915cc-142">Purpose: Broad deployment of the latest feature updates to the rest of the organization.</span></span> </li><li> <span data-ttu-id="915cc-143">状态：完全兼容和支持。</span><span class="sxs-lookup"><span data-stu-id="915cc-143">State: Fully compliant and supported.</span></span> </li></ul> | <span data-ttu-id="915cc-144">**Win10SemiAnnualChannel**（示例名称）</span><span class="sxs-lookup"><span data-stu-id="915cc-144">**Win10SemiAnnualChannel** (example name)</span></span> <br><br> <span data-ttu-id="915cc-145">成员是不在 Win10ReleasePreviewChannel 组的所有用户。</span><span class="sxs-lookup"><span data-stu-id="915cc-145">Members are all users that are not in the Win10ReleasePreviewChannel group.</span></span> |
||||

<span data-ttu-id="915cc-146">此组织采用的最佳做法是，采用与部署半年频道版本（如 Windows 更新网站或 Windows Server Update Services）相同的方式部署发布预览频道有效负载，并且对两个频道更新采用相同的策略。</span><span class="sxs-lookup"><span data-stu-id="915cc-146">This organization uses the best practice of deploying the Release Preview Channel payload in the same way as they deploy Semi-Annual Channel releases, such as Windows Update or Windows Server Update Services, and that they apply the same policies for both channel updates.</span></span>

<span data-ttu-id="915cc-147">正在进行的更新进程：</span><span class="sxs-lookup"><span data-stu-id="915cc-147">Ongoing updates process:</span></span>

1. <span data-ttu-id="915cc-148">发布预览频道更改将部署到 Win10ReleasePreviewChannel （示例名称）部署组。</span><span class="sxs-lookup"><span data-stu-id="915cc-148">Release Preview Channel changes are deployed to the Win10ReleasePreviewChannel (example name) deployment group.</span></span>
2. <span data-ttu-id="915cc-149">Win10ReleasePreviewChannel 组成员确认发布预览频道更改对IT部署人员有用，他们可以向 Microsoft 提供反馈，并等待下一个发布预览频道更改进行其他验证。</span><span class="sxs-lookup"><span data-stu-id="915cc-149">Win10ReleasePreviewChannel group members confirm that Release Preview Channel changes are working to IT deployment staff, who can provide feedback to Microsoft and wait for the next Release Preview Channel changes for additional validation.</span></span>
3. <span data-ttu-id="915cc-150">半年频道功能更改将部署到 Win10SemiAnnualChannel 部署组。</span><span class="sxs-lookup"><span data-stu-id="915cc-150">Semi-Annual Channel feature changes are deployed to the Win10SemiAnnualChannel deployment group.</span></span> 

>[!Note]
><span data-ttu-id="915cc-151">虽然半年频道是推荐频道，但是你的IT部门应利用管理工具决定何时在他们的内部部署并推出最新的半年频道。</span><span class="sxs-lookup"><span data-stu-id="915cc-151">While the Semi-Annual Channel is the recommended channel, your IT department should utilize their management tools and determine when to deploy the latest Semi-Annual Channel release within their organization and then roll it out in waves.</span></span>
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a><span data-ttu-id="915cc-152">为 Microsoft 365 应用版部署配置</span><span class="sxs-lookup"><span data-stu-id="915cc-152">Deployment configuration for Microsoft 365 Apps</span></span>

<span data-ttu-id="915cc-153">总体目标是一组代表用户验证当前频道（预览版）更改后，广泛部署最新的当前频道版本。</span><span class="sxs-lookup"><span data-stu-id="915cc-153">The overall goal is to perform a broad deployment of the latest Current Channel release after validation of Current Channel (Preview) changes by a group of representative users.</span></span>

<span data-ttu-id="915cc-154">了解更多 Microsoft 365 应用版部署方法和策略的信息，请参阅[Microsoft 365 应用版部署](https://docs.microsoft.com/deployoffice/plan-office-365-proplus)。 </span><span class="sxs-lookup"><span data-stu-id="915cc-154">See [Microsoft 365 Apps deployment](https://docs.microsoft.com/deployoffice/plan-office-365-proplus) for more information on Microsoft 365 Apps deployment methods and strategies.</span></span>

| <span data-ttu-id="915cc-155">阶段</span><span class="sxs-lookup"><span data-stu-id="915cc-155">Stage</span></span> | <span data-ttu-id="915cc-156">频道</span><span class="sxs-lookup"><span data-stu-id="915cc-156">Channel</span></span> | <span data-ttu-id="915cc-157">部署组</span><span class="sxs-lookup"><span data-stu-id="915cc-157">Deployment group</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="915cc-158">试点</span><span class="sxs-lookup"><span data-stu-id="915cc-158">Pilot</span></span> |  <span data-ttu-id="915cc-159">**当前频道（预览）**</span><span class="sxs-lookup"><span data-stu-id="915cc-159">**Current Channel (Preview)**</span></span> <ul><li> <span data-ttu-id="915cc-160">目的：{让组中的代表性的用户一窥 Microsoft 365 应用版的新功能} 在使用当前频道（预览）用户测试并进入生产状态后立即部署功能更新。</span><span class="sxs-lookup"><span data-stu-id="915cc-160">Purpose: {give a group of representative users a sneak peek of new Microsoft 365 Apps features} Deployment of feature updates as soon as they are tested with Current Channel (Preview) users and are production-ready.</span></span> </li><li> <span data-ttu-id="915cc-161">状态：完全兼容和支持。</span><span class="sxs-lookup"><span data-stu-id="915cc-161">State: Fully compliant and supported.</span></span></li><li> <span data-ttu-id="915cc-162">频率：每月更新 2-3 次。</span><span class="sxs-lookup"><span data-stu-id="915cc-162">How often: Updates 2-3 times each month.</span></span> </li></ul> | <span data-ttu-id="915cc-163">**AppsCurrentChannelPreview**（示例名称）</span><span class="sxs-lookup"><span data-stu-id="915cc-163">**AppsCurrentChannelPreview** (example name)</span></span> <br><br> <span data-ttu-id="915cc-164">成员是包含以下内容的组：</span><span class="sxs-lookup"><span data-stu-id="915cc-164">Members are groups containing:</span></span> <ul><li> <span data-ttu-id="915cc-165">跨部门和位置的 Office 应用爱好者</span><span class="sxs-lookup"><span data-stu-id="915cc-165">Office apps enthusiasts across departments and locations</span></span> </li><li> <span data-ttu-id="915cc-166">配置需要验证的职员</span><span class="sxs-lookup"><span data-stu-id="915cc-166">Staff with configurations that need validation</span></span> </li><li> <span data-ttu-id="915cc-167">IT 管理员和 IT 部署职员</span><span class="sxs-lookup"><span data-stu-id="915cc-167">IT admins and IT deployment staff</span></span> </li><li> <span data-ttu-id="915cc-168">更换经理</span><span class="sxs-lookup"><span data-stu-id="915cc-168">Change managers</span></span> </li><li> <span data-ttu-id="915cc-169">内部培训人员</span><span class="sxs-lookup"><span data-stu-id="915cc-169">Internal training staff</span></span> </li></ul>|
| <span data-ttu-id="915cc-170">生产</span><span class="sxs-lookup"><span data-stu-id="915cc-170">Production</span></span> | <span data-ttu-id="915cc-171">**当前频道**</span><span class="sxs-lookup"><span data-stu-id="915cc-171">**Current Channel**</span></span> <ul><li> <span data-ttu-id="915cc-172">目的：将最新功能更新广泛部署到组织的其他部分。</span><span class="sxs-lookup"><span data-stu-id="915cc-172">Purpose: Broad deployment of the latest feature updates to the rest of the organization.</span></span> </li><li> <span data-ttu-id="915cc-173">状态：完全兼容和支持。</span><span class="sxs-lookup"><span data-stu-id="915cc-173">State: Fully compliant and supported.</span></span> </li></ul> |  <span data-ttu-id="915cc-174">**AppsCurrentChannel** （示例名称）</span><span class="sxs-lookup"><span data-stu-id="915cc-174">**AppsCurrentChannel** (example name)</span></span> <br><br> <span data-ttu-id="915cc-175">成员是所有不在 AppsCurrentChannelPreview 组的用户。</span><span class="sxs-lookup"><span data-stu-id="915cc-175">Members are all users that are not in the AppsCurrentChannelPreview group.</span></span> |
|||

<span data-ttu-id="915cc-176">正在进行的更新进程：</span><span class="sxs-lookup"><span data-stu-id="915cc-176">Ongoing updates process:</span></span>

1. <span data-ttu-id="915cc-177">当前频道 (预览) 更改将部署到 AppsCurrentChannelPreview 部署组。</span><span class="sxs-lookup"><span data-stu-id="915cc-177">Current Channel (Preview) changes are deployed to the AppsCurrentChannelPreview deployment group.</span></span>
2. <span data-ttu-id="915cc-178">AppsCurrentChannelPreview 组成员确认当前频道（预览版）的更改对IT部署人员有用，他们可以向 Microsoft 提供反馈，并等待下一个当前频道（预览版）版本进行其他验证。</span><span class="sxs-lookup"><span data-stu-id="915cc-178">AppsCurrentChannelPreview group members confirm that Current Channel (Preview) changes are working to IT deployment staff, who can provide feedback to Microsoft and wait for the next Current Channel (Preview) release for additional validation.</span></span>
3. <span data-ttu-id="915cc-179">当前通道更改将部署到 AppsCurrentChannel 部署组。</span><span class="sxs-lookup"><span data-stu-id="915cc-179">Current Channel changes are deployed to the AppsCurrentChannel deployment group.</span></span> 

## <a name="visual-summary"></a><span data-ttu-id="915cc-180">视觉摘要</span><span class="sxs-lookup"><span data-stu-id="915cc-180">Visual summary</span></span>

<span data-ttu-id="915cc-181">这些是此示例组织使用的产品、频道和部署组。</span><span class="sxs-lookup"><span data-stu-id="915cc-181">Here are the products, their channels, and the deployment groups used by this example organization.</span></span> 

![为最新版本的广泛部署部署组](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a><span data-ttu-id="915cc-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="915cc-183">See also</span></span>

[<span data-ttu-id="915cc-184">部署和更新频道示例配置</span><span class="sxs-lookup"><span data-stu-id="915cc-184">Deployment and update channel example configurations</span></span>](deploy-update-channels-examples.md)

[<span data-ttu-id="915cc-185">部署指南</span><span class="sxs-lookup"><span data-stu-id="915cc-185">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="915cc-186">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="915cc-186">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
