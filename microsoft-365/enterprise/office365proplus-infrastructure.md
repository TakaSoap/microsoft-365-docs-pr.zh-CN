---
title: 阶段 4：Office 365 专业增强版
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 这些步骤用于部署 Microsoft 365 企业版 Office 365 专业增强版基础结构。
ms.openlocfilehash: 05615c4c9020326da6b2e3e97b162dbb8d132854
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033647"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="c7c2c-103">阶段 4：Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="c7c2c-103">Phase 4: Office 365 ProPlus</span></span>

![阶段 4：Office 365 专业增强版](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="c7c2c-105">\*\* 这适用于 Microsoft 365 企业版和 Microsoft 365 教育版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="c7c2c-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="c7c2c-106">Microsoft 365 企业版包括 Office 365 专业增强版，即 Office 的订阅版本。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-106">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office.</span></span> <span data-ttu-id="c7c2c-107">与 Office 2019 一样，Office 365 专业增强版包含所有 Office 应用程序，这些应用程序直接安装在客户端设备上。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-107">Like Office 2019, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="c7c2c-108">与 Office 2019 不同的是，Office 365 专业增强版会定期更新新功能，并拥有基于用户的许可模型，允许用户在多个设备上安装 Office。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-108">Unlike Office 2019, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="c7c2c-109">有关详细信息，请参阅[关于企业中的 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-109">For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="c7c2c-p102">在这个阶段，会将 Office 365 专业增强版作为 Microsoft 365 企业版的一部分部署到客户端设备。除了此项指导，建议使用 [Microsoft Fastrack](https://fasttrack.microsoft.com/office)，以帮助进行部署。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="c7c2c-112">如果已部署 Office 365 专业增强版，请查看这一阶段的[退出条件](office365proplus-exit-criteria.md)，以确保其满足 Microsoft 365 企业版的必备条件。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-112">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="c7c2c-113">要同时部署 Windows 10 企业版和 Office 365 专业增强版，请参阅[桌面部署中心](desktop-deployment-center-home.md)。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="c7c2c-114">第 1 步：评估环境</span><span class="sxs-lookup"><span data-stu-id="c7c2c-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="c7c2c-p103">在部署 Office 365 专业增强版之前，请遵循[评估部署 Office 365 专业增强版的环境和要求](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)中的指导。此评估包括系统要求、客户端设备的详细信息（如体系结构和所需语言）、许可要求、网络能力和应用程序兼容性。完成该评估将有助于你在规划部署中做出关键决策。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="c7c2c-118">步骤 2：规划部署</span><span class="sxs-lookup"><span data-stu-id="c7c2c-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="c7c2c-p104">评估环境后，按照[规划 Office 365 专业增强版部署](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)中的指导来创建部署计划。此计划可包括以下决策：</span><span class="sxs-lookup"><span data-stu-id="c7c2c-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="c7c2c-121">如何部署 Office，包括要使用哪种工具（如 System Center Configuration Manager 或 Office 部署工具），以及从何处安装 Office</span><span class="sxs-lookup"><span data-stu-id="c7c2c-121">How to deploy Office, including what tool to use (such as System Center Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="c7c2c-122">如何管理 Office 更新</span><span class="sxs-lookup"><span data-stu-id="c7c2c-122">How to manage updates to Office</span></span>
- <span data-ttu-id="c7c2c-123">使用哪个更新通道（Office 更新通道将控制用户接收其 Office 应用程序功能更新的频率）</span><span class="sxs-lookup"><span data-stu-id="c7c2c-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="c7c2c-124">要使用的 Office 安装程序包和部署组，包括应对什么样的用户安装哪些 Office 应用程序和语言</span><span class="sxs-lookup"><span data-stu-id="c7c2c-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="c7c2c-125">[规划文章](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)列出了所有这些选项的最佳做法，包括管理部署、管理更新、定义安装程序包和创建部署组。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="c7c2c-126">步骤 3：部署</span><span class="sxs-lookup"><span data-stu-id="c7c2c-126">Step 3: Deploy</span></span>

<span data-ttu-id="c7c2c-127">基于部署计划，选择所需的部署方式：</span><span class="sxs-lookup"><span data-stu-id="c7c2c-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="c7c2c-128">**[使用 System Center Configuration Manager 部署 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager)：** 使用配置管理器管理部署，并从网络上的分发点下载并部署 Office</span><span class="sxs-lookup"><span data-stu-id="c7c2c-128">**[Deploy Office 365 ProPlus with System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="c7c2c-129">**[从云中使用 ODT 部署 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud)：** 使用 ODT 管理部署，并在客户端设备上直接从 Office CDN 安装 Office</span><span class="sxs-lookup"><span data-stu-id="c7c2c-129">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="c7c2c-130">**[从 Office 门户自助安装 Office 365 专业增强版](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658)：** 从 Office 门户管理部署，并让用户在其客户端设备上直接从门户安装 Office</span><span class="sxs-lookup"><span data-stu-id="c7c2c-130">**[Self-install Office 365 ProPlus from the Office portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="c7c2c-p105">许多组织将针对不同用户使用这些选项组合。例如，组织可能使用配置管理器对大部分用户部署 Office，但对不经常连接到内部网络的一小组工作人员启用自助安装。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="c7c2c-p106">如果组织使用配置管理器，建议升级到 Current Branch 并更新到当前版本。有关详细信息，请参阅[应使用配置管理器的哪个分支？](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="c7c2c-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c7c2c-135">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="c7c2c-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c7c2c-136">了解 Microsoft 的专家如何[部署和管理 Office 365 专业增强版更新](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7)。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-136">Learn how the experts at Microsoft are [deploying and mananging updates for Office 365 ProPlus](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="c7c2c-137">Contoso 是如何使用 Microsoft 365 企业版的</span><span class="sxs-lookup"><span data-stu-id="c7c2c-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c7c2c-138">了解 Contoso Corporation（虚构但具代表性的跨国企业）是如何[部署 Office 365 专业增强版](contoso-o365pp.md)的。</span><span class="sxs-lookup"><span data-stu-id="c7c2c-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="c7c2c-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c7c2c-140">Next step</span></span>

[<span data-ttu-id="c7c2c-141">Office 365 专业增强版基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="c7c2c-141">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
