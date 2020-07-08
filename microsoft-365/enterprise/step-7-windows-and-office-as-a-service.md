---
title: 步骤 7 - Windows 和 Office 服务
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何在环境中为实现 Windows 和 Office 服务做好准备。
ms.openlocfilehash: e9de339c6bc66e5cd3c02af5f6a53c32b7573b1f
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678998"
---
# <a name="step-7-windows-and-office-servicing"></a><span data-ttu-id="89fe6-103">步骤 7：Windows 和 Office 服务</span><span class="sxs-lookup"><span data-stu-id="89fe6-103">Step 7: Windows and Office Servicing</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><span data-ttu-id="89fe6-104"><strong>步骤 7：Windows 和 Office 服务</strong></span><span class="sxs-lookup"><span data-stu-id="89fe6-104"><strong>Step 7: Windows and Office Servicing</strong></span></span></p>
<p><span data-ttu-id="89fe6-105">Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations.</span><span class="sxs-lookup"><span data-stu-id="89fe6-105">Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations.</span></span> <span data-ttu-id="89fe6-106">Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</span><span class="sxs-lookup"><span data-stu-id="89fe6-106">Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</span></span></p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="89fe6-107">Windows 和 Office 服务是我们建议部署过程轮的第七步，其中涉及正在计划的准备半年功能更新的各个方面。。</span><span class="sxs-lookup"><span data-stu-id="89fe6-107">Windows and Office Servicing is the seventh step in our recommended deployment process wheel covering the planning aspects of preparing for semi-annual updates to features.</span></span> <span data-ttu-id="89fe6-108">若要查看的完整桌面部署过程，请访问[桌面部署中心](https://aka.ms/HowToShift)。</span><span class="sxs-lookup"><span data-stu-id="89fe6-108">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="89fe6-109">Windows 10 和 Microsoft 365 企业应用版都引入了新的服务选项、支持模型和更新时间线。</span><span class="sxs-lookup"><span data-stu-id="89fe6-109">Both Windows 10 and Microsoft 365 Apps for enterprise introduce new servicing options, support models, and update timelines.</span></span> <span data-ttu-id="89fe6-110">这些更改简化了保持最新功能的过程。</span><span class="sxs-lookup"><span data-stu-id="89fe6-110">These changes simplify the process for staying current on the latest features.</span></span> <span data-ttu-id="89fe6-111">除了这些更新之外，还提供了新的配置选项，以支持满足你需求的服务计划。</span><span class="sxs-lookup"><span data-stu-id="89fe6-111">Along with these updates are new configuration options to enable servicing plans that meet your needs.</span></span> <span data-ttu-id="89fe6-112">了解如何准备半年频道更新，它们在 Windows 10 和 Microsoft 365 企业应用版中提供新特性和功能，并利用 Microsoft Endpoint Configuration Manager（当前分支）中的新功能。</span><span class="sxs-lookup"><span data-stu-id="89fe6-112">Let's learn how to prepare for semi-annual channel updates offering new features and capabilities in Windows 10 and Microsoft 365 Apps for enterprise while leveraging new features within Microsoft Endpoint Configuration Manager (Current Branch).</span></span>

[<span data-ttu-id="89fe6-113">帮助客户过渡到 Windows 10 和 Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="89fe6-113">Helping customers shift to Windows 10 and Microsoft 365 Apps for enterprise</span></span>](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a><span data-ttu-id="89fe6-114">更新类型</span><span class="sxs-lookup"><span data-stu-id="89fe6-114">Update Types</span></span>

<span data-ttu-id="89fe6-115">更新分为两个主要类别：功能更新，然后是质量和安全更新，其中包含累积安全性、可靠性和 bug 修复。</span><span class="sxs-lookup"><span data-stu-id="89fe6-115">Updates fall into two main categories, feature updates and then quality and security updates which contain cumulative security, reliability and bug fixes.</span></span> <span data-ttu-id="89fe6-116">在频率方面，Windows 和 Office 都提供了一个半年频道，在每年的 3 月和 9 月发布两次新功能，而质量和安全更新则是每月发布一次。</span><span class="sxs-lookup"><span data-stu-id="89fe6-116">In terms of cadence both Windows and Office deliver a semi-annual channel which delivers new features twice per year around March and September while quality and security Updates occur Monthly.</span></span> <span data-ttu-id="89fe6-117">此外，Office 365 应用的独特之处在于，我们提供完全支持的当前频道选项，其中的更新同时包含新功能和质量更新。</span><span class="sxs-lookup"><span data-stu-id="89fe6-117">Additionally, unique to Office 365 applications, we offer a fully-supported Current Channel option where updates contain both new features and quality updates.</span></span>

<span data-ttu-id="89fe6-118">如果你习惯了桌面 OS 和应用更新之间的更长的周期，你可能会思考；</span><span class="sxs-lookup"><span data-stu-id="89fe6-118">If you’re used to a longer cycle between desktop OS and app updates, you might be wondering;</span></span>

  - <span data-ttu-id="89fe6-119">更新是否兼容？</span><span class="sxs-lookup"><span data-stu-id="89fe6-119">Will the updates be compatible?</span></span>

  - <span data-ttu-id="89fe6-120">我需要继续对用户进行重新培训吗？</span><span class="sxs-lookup"><span data-stu-id="89fe6-120">Will I need to keep retraining my users?</span></span>

  - <span data-ttu-id="89fe6-121">有哪些风险？</span><span class="sxs-lookup"><span data-stu-id="89fe6-121">And what are the risks?</span></span>

<span data-ttu-id="89fe6-122">为了回答这些问题以及更频繁地交付新功能的基本原理，我们将阐明此方法的一些优点</span><span class="sxs-lookup"><span data-stu-id="89fe6-122">To answer those questions and the rationale for delivering new capabilities more frequently, we’ll some of the advantages of this approach</span></span>

### <a name="feature-update-benefits"></a><span data-ttu-id="89fe6-123">功能更新优势</span><span class="sxs-lookup"><span data-stu-id="89fe6-123">Feature Update Benefits</span></span>

<span data-ttu-id="89fe6-124">First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year.</span><span class="sxs-lookup"><span data-stu-id="89fe6-124">First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year.</span></span> <span data-ttu-id="89fe6-125">Why?</span><span class="sxs-lookup"><span data-stu-id="89fe6-125">Why?</span></span> <span data-ttu-id="89fe6-126">With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current.</span><span class="sxs-lookup"><span data-stu-id="89fe6-126">With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current.</span></span> <span data-ttu-id="89fe6-127">Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.</span><span class="sxs-lookup"><span data-stu-id="89fe6-127">Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.</span></span>

[<span data-ttu-id="89fe6-128">Windows 即服务的快速指南</span><span class="sxs-lookup"><span data-stu-id="89fe6-128">Quick guide to Windows as a service</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[<span data-ttu-id="89fe6-129">通过使用 Windows 10 安全功能来缓解威胁</span><span class="sxs-lookup"><span data-stu-id="89fe6-129">Mitigate threats by using Windows 10 security features</span></span>](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a><span data-ttu-id="89fe6-130">累积更新模型优势</span><span class="sxs-lookup"><span data-stu-id="89fe6-130">Cumulative Update Model Benefits</span></span>

<span data-ttu-id="89fe6-131">Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past.</span><span class="sxs-lookup"><span data-stu-id="89fe6-131">Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past.</span></span> <span data-ttu-id="89fe6-132">It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office.</span><span class="sxs-lookup"><span data-stu-id="89fe6-132">It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office.</span></span> <span data-ttu-id="89fe6-133">As you can imagine, this creates a nearly impossible set of test matrices for support.</span><span class="sxs-lookup"><span data-stu-id="89fe6-133">As you can imagine, this creates a nearly impossible set of test matrices for support.</span></span> <span data-ttu-id="89fe6-134">Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.</span><span class="sxs-lookup"><span data-stu-id="89fe6-134">Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.</span></span>

<span data-ttu-id="89fe6-135">With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced.</span><span class="sxs-lookup"><span data-stu-id="89fe6-135">With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced.</span></span> <span data-ttu-id="89fe6-136">Each update builds upon updates from previous months and contains all of the fixes that you need to get current.</span><span class="sxs-lookup"><span data-stu-id="89fe6-136">Each update builds upon updates from previous months and contains all of the fixes that you need to get current.</span></span> <span data-ttu-id="89fe6-137">Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.</span><span class="sxs-lookup"><span data-stu-id="89fe6-137">Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.</span></span>

### <a name="expanded-validation-of-updates"></a><span data-ttu-id="89fe6-138">扩展更新验证</span><span class="sxs-lookup"><span data-stu-id="89fe6-138">Expanded Validation of Updates</span></span>

<span data-ttu-id="89fe6-139">另一个优点是，在我们推出更新以实现广泛部署之前，我们会首先通过 [Office](https://products.office.com/office-insider?tab=Windows-Desktop) 和 [Windows](https://insider.windows.com/) 的预览体验计划发布内部版本，这让我们可以在广泛发布更新之前收集诊断数据和反馈。</span><span class="sxs-lookup"><span data-stu-id="89fe6-139">Another advantage is that, before we roll out updates for broad deployment, we first release builds via the Insider programs for [Office](https://products.office.com/office-insider?tab=Windows-Desktop) and [Windows](https://insider.windows.com/), and this allows us to gather diagnostic data and feedback ahead of us releasing updates broadly.</span></span> <span data-ttu-id="89fe6-140">目前，预览体验计划对所有人开放，这样可以预先了解更新。</span><span class="sxs-lookup"><span data-stu-id="89fe6-140">Now the Insider programs are open to everyone so that you can get ahead of understanding the updates.</span></span> <span data-ttu-id="89fe6-141">当发布更新时，我们将从上百万个配置中接收诊断数据，因此当我们推出更新时，质量更易于预测</span><span class="sxs-lookup"><span data-stu-id="89fe6-141">By the time we release updates we will have received diagnostic data from millions of configurations, so when we do roll out updates, quality is now inherently more predictable</span></span>

<span data-ttu-id="89fe6-142">还有一点，由于 Microsoft 365 企业应用版预览体验计划内部版本反映了每月频道更新，因此如果针对 Office 使用半年频道来提供每年两次的功能更新（Windows 同样如此），则也可以使用半年企业频道（预览）版本来提前验证这些内部版本。</span><span class="sxs-lookup"><span data-stu-id="89fe6-142">AND one more thing, because Microsoft 365 Apps for enterprise Insider builds reflect monthly channel updates, if you are using semi-annual channel for Office to deliver feature updates twice per year aligned to Windows, you can validate those builds early as well using the Semi-Annual Enterprise Channel (Preview) releases.</span></span>

### <a name="supporting-management-tools"></a><span data-ttu-id="89fe6-143">支持管理工具</span><span class="sxs-lookup"><span data-stu-id="89fe6-143">Supporting Management Tools</span></span>

<span data-ttu-id="89fe6-144">We've also thought through how to make the deployment of updates seamless to you.</span><span class="sxs-lookup"><span data-stu-id="89fe6-144">We've also thought through how to make the deployment of updates seamless to you.</span></span> <span data-ttu-id="89fe6-145">Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.</span><span class="sxs-lookup"><span data-stu-id="89fe6-145">Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.</span></span>

[<span data-ttu-id="89fe6-146">使用 Configuration Manager 部署 Windows 10 更新</span><span class="sxs-lookup"><span data-stu-id="89fe6-146">Deploy Windows 10 updates using Configuration Manager</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[<span data-ttu-id="89fe6-147">使用 Configuration Manager 来管理 Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="89fe6-147">Manage Microsoft 365 Apps for enterprise with Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a><span data-ttu-id="89fe6-148">Windows 和 Office 频道概述</span><span class="sxs-lookup"><span data-stu-id="89fe6-148">Overview of Windows and Office Channels</span></span>

<span data-ttu-id="89fe6-149">Windows 10 提供三个服务频道：</span><span class="sxs-lookup"><span data-stu-id="89fe6-149">Windows 10 offers three servicing channels:</span></span>

- <span data-ttu-id="89fe6-150">[**Windows 预览体验计划**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider)适合于组织用于对下一次功能更新中所含的功能进行测试和提供反馈</span><span class="sxs-lookup"><span data-stu-id="89fe6-150">[**Windows Insider Program**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider) for organizations to test and provide feedback on features shipped in the next feature update</span></span>
- <span data-ttu-id="89fe6-151">**半年度频道**每年提供两次的功能更新发布提供新功能</span><span class="sxs-lookup"><span data-stu-id="89fe6-151">**Semi-Annual Channel** provides new functionality with Feature Update releases twice per year</span></span>
- <span data-ttu-id="89fe6-152">**长期服务频道**专用于需要更长服务选项的特殊设备</span><span class="sxs-lookup"><span data-stu-id="89fe6-152">**Long Term Servicing Channel** is designed only for specialized devices needing a longer servicing option</span></span>

<span data-ttu-id="89fe6-153">Microsoft 365 提供 4 个服务频道：</span><span class="sxs-lookup"><span data-stu-id="89fe6-153">Microsoft 365 offers four servicing channels:</span></span>

- <span data-ttu-id="89fe6-154">[**Office 预览体验计划**](https://products.office.com/office-insider)适合于组织用于对仍在开发中的最新 Office 特性和功能进行测试并提供反馈</span><span class="sxs-lookup"><span data-stu-id="89fe6-154">[**Office Insider Program**](https://products.office.com/office-insider) for organizations to test and provide feedback on the newest Office features and functionalities still in development</span></span>
- <span data-ttu-id="89fe6-155">**当前频道**用于在最新 Office 功能推出后立即将其提供给用户</span><span class="sxs-lookup"><span data-stu-id="89fe6-155">**Current Channel** to provide users with the newest Office features as soon as they're available</span></span>
- <span data-ttu-id="89fe6-156">**半年企业频道**每年只提供两次新功能和新特性</span><span class="sxs-lookup"><span data-stu-id="89fe6-156">**Semi-Annual Enterprise Channel** provides new functionality with new features only twice per year</span></span>
- <span data-ttu-id="89fe6-157">**半年企业频道（预览）** 是 Office 的完全支持内部版本，支持试点用户和应用程序兼容性测试人员测试和验证下一个半年企业频道</span><span class="sxs-lookup"><span data-stu-id="89fe6-157">**Semi-Annual Enterprise Channel (Preview)** is a fully supported build of Office that enables pilot users and application compatibility testers to test and validate the next Semi-Annual Enterprise Channel</span></span>

<span data-ttu-id="89fe6-158">有关 Windows 和 Office 服务频道的详细信息，请查阅以下文档：</span><span class="sxs-lookup"><span data-stu-id="89fe6-158">For detailed information about Windows and Office servicing channels please review the below documentation:</span></span>

- [<span data-ttu-id="89fe6-159">Windows 即服务概述</span><span class="sxs-lookup"><span data-stu-id="89fe6-159">Overview of Windows as a Service</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels)
- [<span data-ttu-id="89fe6-160">Microsoft 365 应用版更新通道概述</span><span class="sxs-lookup"><span data-stu-id="89fe6-160">Overview of update channels for Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a><span data-ttu-id="89fe6-161">分阶段部署更新</span><span class="sxs-lookup"><span data-stu-id="89fe6-161">Phased Deployment of Updates</span></span>

<span data-ttu-id="89fe6-162">Now let’s shift gears to how you will roll out these updates.</span><span class="sxs-lookup"><span data-stu-id="89fe6-162">Now let’s shift gears to how you will roll out these updates.</span></span> <span data-ttu-id="89fe6-163">For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment.</span><span class="sxs-lookup"><span data-stu-id="89fe6-163">For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment.</span></span> <span data-ttu-id="89fe6-164">Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.</span><span class="sxs-lookup"><span data-stu-id="89fe6-164">Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.</span></span>

### <a name="monthly-updating"></a><span data-ttu-id="89fe6-165">每月更新</span><span class="sxs-lookup"><span data-stu-id="89fe6-165">Monthly Updating</span></span>

<span data-ttu-id="89fe6-166">The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates.</span><span class="sxs-lookup"><span data-stu-id="89fe6-166">The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates.</span></span> <span data-ttu-id="89fe6-167">As mentioned, the cumulative nature of monthly updates means each will increase in size per month.</span><span class="sxs-lookup"><span data-stu-id="89fe6-167">As mentioned, the cumulative nature of monthly updates means each will increase in size per month.</span></span>

#### <a name="express-updates"></a><span data-ttu-id="89fe6-168">快速更新</span><span class="sxs-lookup"><span data-stu-id="89fe6-168">Express Updates</span></span>

<span data-ttu-id="89fe6-169">Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly.</span><span class="sxs-lookup"><span data-stu-id="89fe6-169">Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly.</span></span> <span data-ttu-id="89fe6-170">In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.</span><span class="sxs-lookup"><span data-stu-id="89fe6-170">In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.</span></span>

[<span data-ttu-id="89fe6-171">Windows 10 质量更新说明和增量更新结语</span><span class="sxs-lookup"><span data-stu-id="89fe6-171">Windows 10 quality updates explained & the end of delta updates</span></span>](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

<span data-ttu-id="89fe6-172">适用于企业的 Windows 更新和 Windows Server Update Services 长期以来支持快速更新，但我们现在已将该支持扩展到 Microsoft Endpoint Configuration Manager（当前分支版本），这样它也可以使用快速更新。</span><span class="sxs-lookup"><span data-stu-id="89fe6-172">Windows Update for Business and Windows Server Update Services have supported express updates for a long time, but we've now extended that support to Microsoft Endpoint Configuration Manager (Current Branch) so that it can also use Express Updates.</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a><span data-ttu-id="89fe6-173">二进制增量压缩</span><span class="sxs-lookup"><span data-stu-id="89fe6-173">Binary Delta Compression</span></span>

<span data-ttu-id="89fe6-174">只有在从 Microsoft 365 企业应用版的最新版本进行更新时，才能在 Office 中使用二进制增量压缩。因此，要使用这种方法，需要从之前的版本进行更新，而且不能跳过更新。</span><span class="sxs-lookup"><span data-stu-id="89fe6-174">Binary Delta Compression in Office is only used if you're updating from the most recent version of Microsoft 365 Apps for enterprise-- so to use this approach you need to be updating from the previous build and can’t skip updates.</span></span>

<span data-ttu-id="89fe6-175">Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process.</span><span class="sxs-lookup"><span data-stu-id="89fe6-175">Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process.</span></span> <span data-ttu-id="89fe6-176">Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.</span><span class="sxs-lookup"><span data-stu-id="89fe6-176">Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.</span></span>

### <a name="semi-annual-updates"></a><span data-ttu-id="89fe6-177">半年更新</span><span class="sxs-lookup"><span data-stu-id="89fe6-177">Semi-Annual Updates</span></span>

<span data-ttu-id="89fe6-178">以上便是每月更新的注意事项，现在让我们继续讨论更大规模的半年更新。</span><span class="sxs-lookup"><span data-stu-id="89fe6-178">So those are your considerations for monthly updates, now let’s move to the larger, semi-annual updates.</span></span>

<span data-ttu-id="89fe6-179">正如我们在“设备和应用就绪情况”中所介绍的，你将希望使用我们在“部署过程轮”步骤 1 中设置的相同准备工具开始准备这些更大的更新。</span><span class="sxs-lookup"><span data-stu-id="89fe6-179">As we covered in Device and App Readiness, you’ll want to begin your preparation for these larger updates using the same readiness tools we set up in Step 1 of the deployment process wheel.</span></span>

<span data-ttu-id="89fe6-180">As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="89fe6-180">As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune.</span></span> <span data-ttu-id="89fe6-181">If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.</span><span class="sxs-lookup"><span data-stu-id="89fe6-181">If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[<span data-ttu-id="89fe6-182">Windows 半年频道</span><span class="sxs-lookup"><span data-stu-id="89fe6-182">Windows Semi-Annual Channel</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[<span data-ttu-id="89fe6-183">Microsoft 365 应用版的半年企业频道</span><span class="sxs-lookup"><span data-stu-id="89fe6-183">Semi-Annual Enterprise Channel for Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a><span data-ttu-id="89fe6-184">升级任务序列</span><span class="sxs-lookup"><span data-stu-id="89fe6-184">Upgrade Task Sequences</span></span>

<span data-ttu-id="89fe6-185">通过标准软件更新管理例程来安装更大的功能更新是受支持的选项，但是许多组织将会选择使用 Microsoft Endpoint Configuration Manager（当前分支版本）中的升级任务序列或 Microsoft Deployment Toolkit。</span><span class="sxs-lookup"><span data-stu-id="89fe6-185">Installing the larger feature updates via standard software update management routines is a supported option, but many organizations will opt to use an Upgrade Task Sequence with Microsoft Endpoint Configuration Manager (Current Branch) or the Microsoft Deployment Toolkit.</span></span>

<span data-ttu-id="89fe6-186">可通过任务序列在安装功能更新之前创建自定义检查或任务，并且可以在更新安装本身完成之后执行自定义任务 – 更新后任务可能包括更新期间暂停服务（如果需要）、驱动程序安装和更换、应用程序升级或任务栏和 Windows 10“开始”菜单的个性化设置。</span><span class="sxs-lookup"><span data-stu-id="89fe6-186">A Task Sequence allows you to create custom checks or tasks BEFORE to the installing the Feature Update and allows you to perform custom tasks AFTER the update installation itself has completed – post-update tasks might include temporarily suspending services if needed during the update, driver installation and replacement, application upgrades or taskbar and Windows 10 Start personalization settings.</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

<span data-ttu-id="89fe6-187">If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control.</span><span class="sxs-lookup"><span data-stu-id="89fe6-187">If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control.</span></span> <span data-ttu-id="89fe6-188">While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences.</span><span class="sxs-lookup"><span data-stu-id="89fe6-188">While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences.</span></span> <span data-ttu-id="89fe6-189">One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade.</span><span class="sxs-lookup"><span data-stu-id="89fe6-189">One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade.</span></span> <span data-ttu-id="89fe6-190">This approach ensures that your user productivity is less impacted.</span><span class="sxs-lookup"><span data-stu-id="89fe6-190">This approach ensures that your user productivity is less impacted.</span></span>

[<span data-ttu-id="89fe6-191">在 Configuration Manager 中创建升级 OS 的任务序列</span><span class="sxs-lookup"><span data-stu-id="89fe6-191">Create a task sequence to upgrade an OS in Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a><span data-ttu-id="89fe6-192">对功能更新的半年频道支持</span><span class="sxs-lookup"><span data-stu-id="89fe6-192">Semi-annual channel support for feature updates</span></span>

<span data-ttu-id="89fe6-193">[如 2018 年 9 月所宣布](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)，半年频道更新的支持时间线将使用以下模型。</span><span class="sxs-lookup"><span data-stu-id="89fe6-193">[As announced in September 2018](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), support timeline for semi-annual channel updates will use the following model.</span></span>

  - <span data-ttu-id="89fe6-194">从版本 1607 开始，所有目前支持的 Windows 10 企业版和教育版功能更新将自初始发布之日起提供 30 个月的支持。</span><span class="sxs-lookup"><span data-stu-id="89fe6-194">All currently supported feature updates of Windows 10 Enterprise and Education, starting with version 1607, will be supported for 30 months from their original release date.</span></span>

  - <span data-ttu-id="89fe6-195">从 1809 开始，所有目标定在 9 月的未来功能更新将自发布之日起提供 30 个月的支持。</span><span class="sxs-lookup"><span data-stu-id="89fe6-195">All future feature updates, starting with 1809, with a targeting September will be supported for 30 months from their release date.</span></span>

  - <span data-ttu-id="89fe6-196">从 1903 开始，所有目标定在 3 月的未来功能更新将自发布之日起继续提供 18 个月的支持。</span><span class="sxs-lookup"><span data-stu-id="89fe6-196">Future feature updates targeting March and starting with 1903 will continue to be supported for 18 months from their release date.</span></span>

  - <span data-ttu-id="89fe6-197">Microsoft 365 企业应用版的半年更新可持续 18 个月</span><span class="sxs-lookup"><span data-stu-id="89fe6-197">Microsoft 365 Apps for enterprise semi-annual updates continue to be supported for 18 months</span></span>

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a><span data-ttu-id="89fe6-198">任务序列之外的其他安装自动化选项</span><span class="sxs-lookup"><span data-stu-id="89fe6-198">Additional setup automation options outside of task sequences</span></span>

<span data-ttu-id="89fe6-199">如果不使用升级任务序列，现在可以在预安装阶段（在安装程序运行其兼容性检查之前）或者在预提交阶段（在应用升级之前），在功能更新期间运行自定义操作或应用驱动程序文件。</span><span class="sxs-lookup"><span data-stu-id="89fe6-199">If you don’t use Upgrade Task Sequences, you can now run custom actions or apply driver files during feature updates in the Pre-install phase – before setup runs its compatibility checks – or in the pre-commit phase – before the upgrade is applied.</span></span>

[<span data-ttu-id="89fe6-200">Windows 10 安装版本 1803 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="89fe6-200">What's new in Windows 10 setup, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a><span data-ttu-id="89fe6-201">后续步骤</span><span class="sxs-lookup"><span data-stu-id="89fe6-201">Next Step</span></span> 

## <a name="step-8-user-communications-and-training"></a>[<span data-ttu-id="89fe6-202">步骤 8：用户通信和培训</span><span class="sxs-lookup"><span data-stu-id="89fe6-202">Step 8: User Communications and Training</span></span>](https://aka.ms/mdd8)

## <a name="previous-step"></a><span data-ttu-id="89fe6-203">上一步</span><span class="sxs-lookup"><span data-stu-id="89fe6-203">Previous Step</span></span> 

## <a name="step-6-os-deployment-and-feature-updates"></a>[<span data-ttu-id="89fe6-204">步骤 6：OS 部署和功能更新</span><span class="sxs-lookup"><span data-stu-id="89fe6-204">Step 6 OS Deployment and Feature Updates</span></span>](https://aka.ms/mdd6)
