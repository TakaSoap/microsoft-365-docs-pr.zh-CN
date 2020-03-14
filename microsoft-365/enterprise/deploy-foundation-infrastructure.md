---
title: Microsoft 365 企业版底层基础结构
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解组织中部署 Microsoft 365 企业版底层基础结构（也称为核心部署）的主要阶段。
ms.openlocfilehash: 26f95b9e7fb951910b983defb8b80162f39c37a2
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633610"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure"></a><span data-ttu-id="fdd7d-103">Microsoft 365 企业版底层基础结构</span><span class="sxs-lookup"><span data-stu-id="fdd7d-103">Microsoft 365 for enterprise foundation infrastructure</span></span>

<span data-ttu-id="fdd7d-104">如果你是自行端到端部署 Microsoft 365 企业版，则应首先奠定坚实的基础，在此基础上，应用程序和服务可以在安全的环境中激发创造力和提高团队协作。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-104">If you're doing the end-to-end deployment of Microsoft 365 for enterprise yourself, you should first build a firm foundation upon which applications and services can unlock creativity and teamwork in a secure environment.</span></span> <span data-ttu-id="fdd7d-105">该底层有时称为*核心部署*。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-105">This foundation is sometimes referred to as a *core deployment*.</span></span>

<span data-ttu-id="fdd7d-106">对于为部署定义的端到端路径，你可以使用这些阶段来规划和部署 Microsoft 365 企业版的底层基础结构：</span><span class="sxs-lookup"><span data-stu-id="fdd7d-106">For a defined end-to-end path for deployment, you can use these phases to plan for and deploy the foundation infrastructure of Microsoft 365 for enterprise:</span></span>

| | <span data-ttu-id="fdd7d-107">阶段</span><span class="sxs-lookup"><span data-stu-id="fdd7d-107">Phase</span></span> | <span data-ttu-id="fdd7d-108">结果</span><span class="sxs-lookup"><span data-stu-id="fdd7d-108">Results</span></span> |
|:-------|:-----|:-----|
|![阶段 1：网络](../media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="fdd7d-110">阶段 1：网络</span><span class="sxs-lookup"><span data-stu-id="fdd7d-110">Phase 1: Networking</span></span>](networking-infrastructure.md)| <span data-ttu-id="fdd7d-111">网络已经过优化，以便访问 Microsoft 365 基于云的服务。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-111">Your network is optimized for access to Microsoft 365's cloud-based services.</span></span> |
|![阶段 2：标识](../media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="fdd7d-113">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="fdd7d-113">Phase 2: Identity</span></span>](identity-infrastructure.md)| <span data-ttu-id="fdd7d-114">管理员帐户受到保护，用户和组经过同步，并且采用强用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-114">Your admin accounts are protected, your users and groups are synchronized, and your user authentication is strong.</span></span> |
|![阶段 3：Windows 10 企业版](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="fdd7d-116">阶段 3：Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="fdd7d-116">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)| <span data-ttu-id="fdd7d-117">现有基于 Windows 的计算机可以升级至 Windows 10 企业版，并且新设备已安装了 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-117">Your existing Windows-based computers can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
|![阶段 4：Office 365 专业增强版](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="fdd7d-119">阶段 4：Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="fdd7d-119">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)| <span data-ttu-id="fdd7d-120">现有 Microsoft Office 用户可以升级到 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-120">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
|![阶段 5：移动设备管理](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="fdd7d-122">阶段 5：移动设备管理</span><span class="sxs-lookup"><span data-stu-id="fdd7d-122">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)| <span data-ttu-id="fdd7d-123">可以注册和管理你的设备。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-123">Your devices can be enrolled and managed.</span></span> |
|![阶段 6：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="fdd7d-125">阶段 6：信息保护</span><span class="sxs-lookup"><span data-stu-id="fdd7d-125">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)| <span data-ttu-id="fdd7d-126">Office 365 安全功能已启用，你的标签和策略已准备好保护文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-126">Office 365 security features are enabled and your labels and policies are ready to protect documents and email.</span></span> |

<span data-ttu-id="fdd7d-127">将从最基本的阶段（网络和标识）开始，然后创建基础结构设置和组层，以：</span><span class="sxs-lookup"><span data-stu-id="fdd7d-127">The phases start with the most foundational (networking and identity), and then create layers of infrastructure settings and groups to:</span></span>

- <span data-ttu-id="fdd7d-128">在设备上安装最新、最安全的 Windows 版本，并保证其处于最新状态。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-128">Install the most current and secure version of Windows on your devices and keep it current.</span></span>
- <span data-ttu-id="fdd7d-129">在设备上安装最新的 Microsoft Office 版本，并保证其处于最新状态。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-129">Install the most current version of Microsoft Office on your devices and keep it current.</span></span>
- <span data-ttu-id="fdd7d-130">管理组织的设备及其对应用的访问。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-130">Manage your organization's devices and their access to apps.</span></span>
- <span data-ttu-id="fdd7d-131">保护这些设备和云中的信息。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-131">Protect the information on those devices and in the cloud.</span></span>

<span data-ttu-id="fdd7d-132">但是，你可以灵活地配置和部署阶段中的各个阶段和步骤，以满足你的 IT 资源和业务需求。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-132">However, you have the flexibility of configuring and rolling out the phases or steps within phases to fit your IT resources and business needs.</span></span>

- <span data-ttu-id="fdd7d-133">**如果你是较小或较新的组织**，请根据需要按照各个阶段操作，以便有条不紊地构建基础结构。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-133">**If you are a smaller or newer organization**, follow the phases as needed to methodically build out your infrastructure.</span></span> <span data-ttu-id="fdd7d-134">有关针对非企业的简化部署，请单击[此处](deploy-foundation-infrastructure-non-enterprises.md)。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-134">For a simplified deployment for non-enterprises, click [here](deploy-foundation-infrastructure-non-enterprises.md).</span></span>

-  <span data-ttu-id="fdd7d-135">**如果你是企业组织**，请将阶段视作 IT 基础架构的层，而不是定义的路径，并确定如何更好地工作，以最终满足组织中每个层的要求。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-135">**If you are an enterprise organization**, view the phases as layers of IT infrastructure, rather than a defined path, and determine how to best work toward eventual adherence to the requirements for each layer across your organization.</span></span>

<span data-ttu-id="fdd7d-136">在每个阶段结束时，你可以检查其*退出条件*，其中包括必须满足的必要条件以及可以考虑的可选条件。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-136">At the end of each phase, you should examine its *exit criteria*, which include required conditions that you must meet and optional conditions to consider.</span></span> <span data-ttu-id="fdd7d-137">每个阶段的退出条件可确保本地和云基础结构以及相应的端到端配置满足 Microsoft 365 企业版部署的要求。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-137">Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 for enterprise deployment.</span></span>

<span data-ttu-id="fdd7d-138">如需查看内容的组织方式，请观看此短片。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-138">To see how the content is structured, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="fdd7d-139">以下是 Microsoft 365 企业版整体部署指南中的底层基础结构：</span><span class="sxs-lookup"><span data-stu-id="fdd7d-139">Here's the foundation infrastructure in the overall Microsoft 365 for enterprise deployment guide:</span></span>

![Microsoft 365 企业版整体部署指南中的底层基础结构](../media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a><span data-ttu-id="fdd7d-141">概览</span><span class="sxs-lookup"><span data-stu-id="fdd7d-141">At-a-glance</span></span>

<span data-ttu-id="fdd7d-142">[Microsoft 365 企业版底层基础结构海报](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)是一个可查看各阶段相关情况的中心位置：</span><span class="sxs-lookup"><span data-stu-id="fdd7d-142">The [Microsoft 365 for enterprise foundation infrastructure poster](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf) is a central location for you to view, for each phase:</span></span>

- <span data-ttu-id="fdd7d-143">所处阶段对管理员和用户的整体目标</span><span class="sxs-lookup"><span data-stu-id="fdd7d-143">The overall goals of the phase for administrators and users</span></span>
- <span data-ttu-id="fdd7d-144">服务、功能和工具</span><span class="sxs-lookup"><span data-stu-id="fdd7d-144">The services, features, and tools</span></span>
- <span data-ttu-id="fdd7d-145">针对规划的关键设计决策</span><span class="sxs-lookup"><span data-stu-id="fdd7d-145">The key design decisions for planning</span></span>
- <span data-ttu-id="fdd7d-146">配置结果</span><span class="sxs-lookup"><span data-stu-id="fdd7d-146">The configuration results</span></span>
- <span data-ttu-id="fdd7d-147">新用户的载入进度</span><span class="sxs-lookup"><span data-stu-id="fdd7d-147">The process for onboarding a new user</span></span>
- <span data-ttu-id="fdd7d-148">监视和更新方式</span><span class="sxs-lookup"><span data-stu-id="fdd7d-148">How to monitor and update</span></span>

<span data-ttu-id="fdd7d-149">[![Microsoft 365 企业版基础结构海报图像](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)</span><span class="sxs-lookup"><span data-stu-id="fdd7d-149">[![Image for the Microsoft 365 for enterprise foundation infrastructure poster](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)</span></span>

<span data-ttu-id="fdd7d-150">要下载海报副本，请单击[此处](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-150">To download a copy of the poster, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf).</span></span>


## <a name="infrastructure-configuration-vs-user-rollout"></a><span data-ttu-id="fdd7d-151">基础结构配置与用户部署</span><span class="sxs-lookup"><span data-stu-id="fdd7d-151">Infrastructure configuration vs. user rollout</span></span>

<span data-ttu-id="fdd7d-152">底层基础结构是一组经过配置的软件和服务，如果针对某一用户将它们组合到一起，可以充分利用 Microsoft 365 企业版具有的全部功能和保护。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-152">The foundation infrastructure is a set of configured software and services that, when combined together for a user, allow them to take advantage of the entire spectrum of capabilities and protections that Microsoft 365 for enterprise offers.</span></span> <span data-ttu-id="fdd7d-153">端到端部署旅程的最终目标是将此基础结构应用于所有用户及其基于 Windows 的设备。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-153">The ultimate destination of your end-to-end deployment journey is to have this infrastructure apply to all of your users and their Windows-based devices.</span></span> 

<span data-ttu-id="fdd7d-154">但是，必须注意的是，Microsoft 365 企业版底层基础结构与为用户部署软件和服务无关。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-154">However, it is important to note that the Microsoft 365 for enterprise foundation infrastructure is independent of the rollout of software and services to your users.</span></span> <span data-ttu-id="fdd7d-155">***你可以配置底层基础结构层，而无需将这些曾部署到所有用户中。***</span><span class="sxs-lookup"><span data-stu-id="fdd7d-155">***You can configure the layers of the foundation infrastructure without having to roll out those layers to all of your users.***</span></span>

<span data-ttu-id="fdd7d-156">可在将元素部署到组织办公室、区域或部门的众多用户之前配置、测试和试用底层基础结构的元素。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-156">It is possible to configure, test, and pilot elements of the foundation infrastructure well ahead of the rollout of those elements to the multitude of your users in the offices, regions, or divisions of your organization.</span></span>

<span data-ttu-id="fdd7d-157">例如，你可以为以下对象创建设置：</span><span class="sxs-lookup"><span data-stu-id="fdd7d-157">For example, you create the settings for:</span></span>

| <span data-ttu-id="fdd7d-158">阶段</span><span class="sxs-lookup"><span data-stu-id="fdd7d-158">Phase</span></span> | <span data-ttu-id="fdd7d-159">结果</span><span class="sxs-lookup"><span data-stu-id="fdd7d-159">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="fdd7d-160">标识</span><span class="sxs-lookup"><span data-stu-id="fdd7d-160">Identity</span></span> | <span data-ttu-id="fdd7d-161">帐户同步和适用于基于条件访问策略的组。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-161">Account synchronization and groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="fdd7d-162">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="fdd7d-162">Windows 10 Enterprise</span></span> | <span data-ttu-id="fdd7d-163">将运行 Windows 7 或 Windows 8.1 的计算机自动升级到相应的 Windows 10 企业版的组。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-163">Groups to automatically upgrade computers running Windows 7 or Windows 8.1 to Windows 10 Enterprise in place.</span></span> |
| <span data-ttu-id="fdd7d-164">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="fdd7d-164">Office 365 ProPlus</span></span> | <span data-ttu-id="fdd7d-165">为使用 Office 2010、Office 2013 或 Office 2016 的用户自动部署 Office 365 的组。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-165">Groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="fdd7d-166">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="fdd7d-166">Mobile device management</span></span> | <span data-ttu-id="fdd7d-167">适合于设备注册和基于设备的条件访问策略的组。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-167">Groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="fdd7d-168">信息保护</span><span class="sxs-lookup"><span data-stu-id="fdd7d-168">Information protection</span></span> | <span data-ttu-id="fdd7d-169">Office 365 敏感度标签组。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-169">Groups for Office 365 sensitivity labels.</span></span> |

<span data-ttu-id="fdd7d-170">准备好为用户部署此基础结构的元素时，你可以：</span><span class="sxs-lookup"><span data-stu-id="fdd7d-170">When you are ready to rollout elements of this infrastructure to users, you:</span></span>

| <span data-ttu-id="fdd7d-171">阶段</span><span class="sxs-lookup"><span data-stu-id="fdd7d-171">Phase</span></span> | <span data-ttu-id="fdd7d-172">部署操作</span><span class="sxs-lookup"><span data-stu-id="fdd7d-172">Rollout action</span></span> |
|:-------|:-----|
| <span data-ttu-id="fdd7d-173">标识</span><span class="sxs-lookup"><span data-stu-id="fdd7d-173">Identity</span></span> | <span data-ttu-id="fdd7d-174">将用户帐户添加到基于标识的条件访问策略组。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-174">Add user accounts to the groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="fdd7d-175">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="fdd7d-175">Windows 10 Enterprise</span></span> | <span data-ttu-id="fdd7d-176">将帐户添加到组，以便为使用 Windows 7 或 Windows 8.1 的用户自动部署 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-176">Add accounts to the groups to automatically deploy Windows 10 Enterprise in place for users with Windows 7 or Windows 8.1.</span></span> |
| <span data-ttu-id="fdd7d-177">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="fdd7d-177">Office 365 ProPlus</span></span> | <span data-ttu-id="fdd7d-178">将用户帐户添加到组，以便为使用 Office 2010、Office 2013 或 Office 2016 的用户自动部署 Office 365 的组。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-178">Add user accounts to the groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="fdd7d-179">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="fdd7d-179">Mobile device management</span></span> | <span data-ttu-id="fdd7d-180">将帐户添加到适合于设备注册和基于设备的条件访问策略的组。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-180">Add accounts to the groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="fdd7d-181">信息保护</span><span class="sxs-lookup"><span data-stu-id="fdd7d-181">Information protection</span></span> | <span data-ttu-id="fdd7d-182">将用户帐户添加到敏感度标签组中。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-182">Add user accounts to the groups for sensitivity labels.</span></span> |

<span data-ttu-id="fdd7d-183">底层基础结构的阶段或元素完成、测试和试用之后，你可以为用户部署已安装的软件（例如 Windows 10 企业版和 Office 365 专业增强版）以及基于云的服务和保护（如设备注册和条件访问策略），以最适合你的业务目标和 IT 资源。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-183">Once phases or elements of the foundation infrastructure are completed, tested, and piloted, you can roll out installed software, such as Windows 10 Enterprise and Office 365 ProPlus, and cloud-based services and protections, such as device enrollment and conditional access policies, to your users in the manner that best fits your business goals and IT resources.</span></span>

## <a name="deployment-and-project-management-strategies"></a><span data-ttu-id="fdd7d-184">部署和项目管理策略</span><span class="sxs-lookup"><span data-stu-id="fdd7d-184">Deployment and project management strategies</span></span>

<span data-ttu-id="fdd7d-185">若要就如何为组织的试点用户和其他用户进对底层基础结构的不同阶段进行项目管理给出一些看法，请参阅[部署战略](deployment-strategies-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-185">To give you some ideas on how to approach the project management of the different phases of the foundation infrastructure for pilot users and the rest of your organization, see [deployment strategies](deployment-strategies-microsoft-365-enterprise.md).</span></span>

## <a name="deployment-for-non-enterprises"></a><span data-ttu-id="fdd7d-186">针对非企业的部署</span><span class="sxs-lookup"><span data-stu-id="fdd7d-186">Deployment for non-enterprises</span></span>

<span data-ttu-id="fdd7d-187">如果你的组织规模较小，而 Microsoft 365 商业版不适合你，请参阅[针对非企业的部署](deploy-foundation-infrastructure-non-enterprises.md)以了解简化的部署方法。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-187">If your organization is smaller and Microsoft 365 Business is not suitable for you, see [deployment for non-enterprises](deploy-foundation-infrastructure-non-enterprises.md) for a simplified deployment method.</span></span>


## <a name="next-step"></a><span data-ttu-id="fdd7d-188">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fdd7d-188">Next step</span></span>

| <span data-ttu-id="fdd7d-189">我当前的境况</span><span class="sxs-lookup"><span data-stu-id="fdd7d-189">Where I am</span></span> | <span data-ttu-id="fdd7d-190">我需要达成的目标</span><span class="sxs-lookup"><span data-stu-id="fdd7d-190">Where I need to go</span></span> |
|:-------|:-----|
| <span data-ttu-id="fdd7d-191">我现在有针对 Office 365、企业移动性 + 安全性 (EMS) 或 Windows 10 企业版的基础结构。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-191">I have existing infrastructure for Office 365, Enterprise Mobility + Security (EMS), or Windows 10 Enterprise</span></span> | <span data-ttu-id="fdd7d-192">请首先[利用现有基础结构部署](deploy-with-existing-infrastructure.md)，了解各阶段的退出条件。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-192">Start with [Deploy with existing infrastructure](deploy-with-existing-infrastructure.md), which steps you through the exit criteria for each phase.</span></span> |
| <span data-ttu-id="fdd7d-193">我要作为企业从头开始</span><span class="sxs-lookup"><span data-stu-id="fdd7d-193">I'm starting from scratch as an enterprise</span></span> | <span data-ttu-id="fdd7d-194">通过[阶段 1：网络](networking-infrastructure.md)开启你的端到端部署旅程。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-194">Begin your end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span> |
| <span data-ttu-id="fdd7d-195">我要以非企业的身份从头开始</span><span class="sxs-lookup"><span data-stu-id="fdd7d-195">I'm starting from scratch as a non-enterprise</span></span> | <span data-ttu-id="fdd7d-196">通过[针对非企业的部署](deploy-foundation-infrastructure-non-enterprises.md)开启你的端到端部署旅程。</span><span class="sxs-lookup"><span data-stu-id="fdd7d-196">Begin your end-to-end deployment journey with [Deployment for non-enterprises](deploy-foundation-infrastructure-non-enterprises.md).</span></span> |
