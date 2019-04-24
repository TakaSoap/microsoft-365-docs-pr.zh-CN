---
title: 阶段 4：Office 365 专业增强版
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 这些步骤用于部署 Microsoft 365 企业版 Office 365 专业增强版基础结构。
ms.openlocfilehash: c4fc3805dd2ea97e1a9797e5adfc31ab83f028ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290933"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="45016-103">阶段 4：Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="45016-103">Phase 4: Office 365 ProPlus</span></span>

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="45016-104">\*\* 这适用于 Microsoft 365 企业版和 Microsoft 365 教育版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="45016-104">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="45016-p101">Microsoft 365 企业版包括 Office 365 专业增强版，即订阅版本的 Office。与 Office 2016 一样，Office 365 专业增强版包含所有 Office 应用程序，而且都将直接安装到客户端设备上。与 Office 2016 不同的是，Office 365 专业增强版会定期更新以推出新功能，并且采用基于用户的许可模型，允许用户在最多 5 台设备上安装 Office。有关详细信息，请参阅[有关企业版中的 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="45016-p101">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office. Like Office 2016, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices. Unlike Office 2016, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on up to 5 devices. For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="45016-p102">在这个阶段，会将 Office 365 专业增强版作为 Microsoft 365 企业版的一部分部署到客户端设备。除了此项指导，建议使用 [Microsoft Fastrack](https://fasttrack.microsoft.com/office)，以帮助进行部署。</span><span class="sxs-lookup"><span data-stu-id="45016-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="45016-111">Office 365 专业增强版为 Microsoft 365 企业版提供这些战略业务方案：</span><span class="sxs-lookup"><span data-stu-id="45016-111">Office 365 ProPlus enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="45016-112">实时或按自己的时间协作处理文档，以简化合著过程</span><span class="sxs-lookup"><span data-stu-id="45016-112">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="45016-113">通过使员工能够发现、共享和改进整个组织的文件、信息和想法，充分利用集体知识和专长</span><span class="sxs-lookup"><span data-stu-id="45016-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="45016-114">使用户能够改变业务流程并提高效率</span><span class="sxs-lookup"><span data-stu-id="45016-114">Empower users to transform business processes and increase efficiency</span></span>
- <span data-ttu-id="45016-115">管理项目、任务和截止时间以达到业务目标</span><span class="sxs-lookup"><span data-stu-id="45016-115">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="45016-116">使用智能协作进行设计、编写、内容发现等等，以帮助你出色完成工作</span><span class="sxs-lookup"><span data-stu-id="45016-116">Use intelligent assistance for design, writing, content discovery, and more to help your work shine</span></span>
- <span data-ttu-id="45016-117">发现见解、分析数据并分享你的发现，帮助每个人做出合理的决定</span><span class="sxs-lookup"><span data-stu-id="45016-117">Discover insights, analyze your data, and share your findings to help everyone make informed decisions</span></span>
- <span data-ttu-id="45016-118">与你的团队进行沟通以了解情况，征求意见，建立凝聚力和共识</span><span class="sxs-lookup"><span data-stu-id="45016-118">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="45016-119">与全球各地的合作伙伴、同事和客户就定期和临时的电话会议以及与各种规模小组的在线会议进行沟通</span><span class="sxs-lookup"><span data-stu-id="45016-119">Communicate with partners, colleagues, and customers around the world for scheduled and ad hoc calls and online meetings with groups of all sizes</span></span>
- <span data-ttu-id="45016-120">存储和共享组织内部和外部的文件，以跨组织边界无缝工作</span><span class="sxs-lookup"><span data-stu-id="45016-120">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="45016-121">随时随地跨设备安全工作，在保持灵活工作方式的同时实现更多功能</span><span class="sxs-lookup"><span data-stu-id="45016-121">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="45016-122">提供尽可安心的控件和可见性，行业认证达标且符合全球标准</span><span class="sxs-lookup"><span data-stu-id="45016-122">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="45016-123">保护信息并降低数据丢失的风险</span><span class="sxs-lookup"><span data-stu-id="45016-123">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="45016-124">获取最新信息并使用最新的桌面软件和设备，同时降低安全风险并最大限度提高 IT 效率</span><span class="sxs-lookup"><span data-stu-id="45016-124">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="45016-125">有关详细信息，请参阅[使用 Microsoft 365 实现数字化化转型](http://transform.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="45016-125">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

<span data-ttu-id="45016-126">如果已部署 Office 365 专业增强版，请查看这一阶段的[退出条件](office365proplus-exit-criteria.md)，以确保其满足 Microsoft 365 企业版的必备条件。</span><span class="sxs-lookup"><span data-stu-id="45016-126">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="45016-127">若要同时部署 Windows 10 企业版和 Office 365 专业增强版，并迁移到[新式桌面](https://www.microsoft.com/microsoft-365/modern-desktop)，请参阅[新式桌面部署中心](http://aka.ms/howtoshift)。</span><span class="sxs-lookup"><span data-stu-id="45016-127">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="45016-128">第 1 步：评估环境</span><span class="sxs-lookup"><span data-stu-id="45016-128">Step 1: Assess your environment</span></span>

<span data-ttu-id="45016-p103">在部署 Office 365 专业增强版之前，请遵循[评估部署 Office 365 专业增强版的环境和要求](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)中的指导。此评估包括系统要求、客户端设备的详细信息（如体系结构和所需语言）、许可要求、网络能力和应用程序兼容性。完成该评估将有助于你在规划部署中做出关键决策。</span><span class="sxs-lookup"><span data-stu-id="45016-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="45016-132">步骤 2：规划部署</span><span class="sxs-lookup"><span data-stu-id="45016-132">Step 2: Plan your deployment</span></span>

<span data-ttu-id="45016-p104">评估环境后，按照[规划 Office 365 专业增强版部署](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)中的指导来创建部署计划。此计划可包括以下决策：</span><span class="sxs-lookup"><span data-stu-id="45016-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="45016-135">如何部署 Office，包括要使用哪种工具（如 System Center Configuration Manager 或 Office 部署工具 [ODT]），以及从何处安装 Office</span><span class="sxs-lookup"><span data-stu-id="45016-135">How to deploy Office, including what tool to use (such as System Center Configuration Manger or the Office Deployment Tool [ODT]) and where to install Office from</span></span>
- <span data-ttu-id="45016-136">如何管理 Office 更新</span><span class="sxs-lookup"><span data-stu-id="45016-136">How to manage updates to Office</span></span>
- <span data-ttu-id="45016-137">使用哪个更新通道（Office 更新通道将控制用户接收其 Office 应用程序功能更新的频率）</span><span class="sxs-lookup"><span data-stu-id="45016-137">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="45016-138">要使用的 Office 安装程序包和部署组，包括应对什么样的用户安装哪些 Office 应用程序和语言</span><span class="sxs-lookup"><span data-stu-id="45016-138">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="45016-139">[规划文章](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)列出了所有这些选项的最佳做法，包括管理部署、管理更新、定义安装程序包和创建部署组。</span><span class="sxs-lookup"><span data-stu-id="45016-139">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="45016-140">步骤 3：部署</span><span class="sxs-lookup"><span data-stu-id="45016-140">Step 3: Deploy</span></span>

<span data-ttu-id="45016-141">基于步骤 2 中的部署计划，选择所需的部署方式：</span><span class="sxs-lookup"><span data-stu-id="45016-141">Based on your deployment plan from step 2, choose how you want to deploy:</span></span>

- <span data-ttu-id="45016-142">**[使用 System Center Configuration Manager 部署 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager)：** 使用配置管理器管理部署，并从网络上的分发点下载并部署 Office</span><span class="sxs-lookup"><span data-stu-id="45016-142">**[Deploy Office 365 ProPlus with System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="45016-143">**[从云中使用 ODT 部署 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud)：** 使用 ODT 管理部署，并在客户端设备上直接从 Office CDN 安装 Office</span><span class="sxs-lookup"><span data-stu-id="45016-143">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="45016-144">**[从本地源使用 ODT 部署 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source)：** 使用 ODT 管理部署，并从网络上的本地源下载和部署 Office</span><span class="sxs-lookup"><span data-stu-id="45016-144">**[Deploy Office 365 ProPlus with the ODT from a local source](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Manage your deployment with the ODT, and download and deploy Office from a local source on your network</span></span> 

- <span data-ttu-id="45016-145">**[从 Office 门户自助安装 Office 365 专业增强版](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658)：** 从 Office 门户管理部署，并让用户在其客户端设备上直接从门户安装 Office</span><span class="sxs-lookup"><span data-stu-id="45016-145">**[Self-install Office 365 ProPlus from the Office portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="45016-p105">许多组织将针对不同用户使用这些选项组合。例如，组织可能使用配置管理器对大部分用户部署 Office，但对不经常连接到内部网络的一小组工作人员启用自助安装。</span><span class="sxs-lookup"><span data-stu-id="45016-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="45016-p106">如果组织使用配置管理器，建议升级到 Current Branch 并更新到当前版本。有关详细信息，请参阅[应使用配置管理器的哪个分支？](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="45016-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="45016-150">Microsoft 如何使用 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="45016-150">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="45016-151">通过下面这些资源，了解 Microsoft 专家如何计划并在 Microsoft 365 企业版中部署了 Office 365 专业增强版：</span><span class="sxs-lookup"><span data-stu-id="45016-151">Learn how the experts at Microsoft planned for and deployed Office 365 ProPlus in Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="45016-152">部署和更新 Microsoft Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="45016-152">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- <span data-ttu-id="45016-153">[自动化和更新通道有助于部署 Microsoft Office 365 专业增强版](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus)（视频）</span><span class="sxs-lookup"><span data-stu-id="45016-153">[Automation and update channels help deploy Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (video)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="45016-154">Contoso 是如何使用 Microsoft 365 企业版的</span><span class="sxs-lookup"><span data-stu-id="45016-154">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="45016-155">了解 Contoso Corporation（虚构但具代表性的跨国企业）是如何[部署 Office 365 专业增强版](contoso-o365pp.md)的。</span><span class="sxs-lookup"><span data-stu-id="45016-155">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="45016-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="45016-156">Next step</span></span>

[<span data-ttu-id="45016-157">Office 365 专业增强版基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="45016-157">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
