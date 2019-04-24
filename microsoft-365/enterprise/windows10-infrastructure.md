---
title: 适用于 Microsoft 365 企业版的 Windows 10 企业版基础结构
description: 提供了在 Microsoft 365 企业版中将 Windows 10 企业版部署到电脑上所需步骤的高级别指南。
keywords: microsoft 365, microsoft 365 企业版, microsoft 365 文档, Windows 10 企业版, 部署
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 88517c6b8de95c54ee9a2e47d4545266eb198249
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289429"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="9176a-104">阶段 3：Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="9176a-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="9176a-105">Microsoft 365 企业版包括 Windows 10 企业版, 为您提供用于执行更多和保持安全保护的工具。</span><span class="sxs-lookup"><span data-stu-id="9176a-105">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="9176a-106">Windows 10 企业版:</span><span class="sxs-lookup"><span data-stu-id="9176a-106">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="9176a-107">**集成为简单起见**-充分利用云的功能来帮助降低管理当今新式 IT 设备环境的复杂性, 而不考虑大小。</span><span class="sxs-lookup"><span data-stu-id="9176a-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="9176a-108">**具有智能安全性**-它是最安全的 Windows 发布, 具有旨在协同工作以更好地保护组织的智能安全功能。</span><span class="sxs-lookup"><span data-stu-id="9176a-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="9176a-109">**实现创造性和团队合作**-解锁创造性和团队合作, 以提供用户最喜爱的工作体验。</span><span class="sxs-lookup"><span data-stu-id="9176a-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="9176a-110">您需要了解部署 Windows 10 操作系统的不同方法, 并为您的组织选择正确的方法。</span><span class="sxs-lookup"><span data-stu-id="9176a-110">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="9176a-111">根据你的 Microsoft 365 企业版订阅, 还需要配置 windows 10 服务和安全功能, 以充分利用 windows 10。</span><span class="sxs-lookup"><span data-stu-id="9176a-111">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

<span data-ttu-id="9176a-112">Windows 10 为 Microsoft 365 企业版启用了这些战略业务方案:</span><span class="sxs-lookup"><span data-stu-id="9176a-112">Windows 10 enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="9176a-113">通过使员工能够发现、共享和改进整个组织的文件、信息和想法，充分利用集体知识和专长</span><span class="sxs-lookup"><span data-stu-id="9176a-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="9176a-114">随时随地跨设备安全工作，在保持灵活工作方式的同时实现更多功能</span><span class="sxs-lookup"><span data-stu-id="9176a-114">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="9176a-115">提供尽可安心的控件和可见性，行业认证达标且符合全球标准</span><span class="sxs-lookup"><span data-stu-id="9176a-115">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="9176a-116">保护信息并降低数据丢失的风险</span><span class="sxs-lookup"><span data-stu-id="9176a-116">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="9176a-117">检测并保护外部威胁-监视、报告和分析活动以及时响应以提供组织安全性</span><span class="sxs-lookup"><span data-stu-id="9176a-117">Detect and protect against external threats --Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="9176a-118">保护你的用户及其帐户</span><span class="sxs-lookup"><span data-stu-id="9176a-118">Protect your users and their accounts</span></span>
- <span data-ttu-id="9176a-119">帮助组织增强隐私和合规性以符合一般数据保护条例 (GDPR)</span><span class="sxs-lookup"><span data-stu-id="9176a-119">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>
- <span data-ttu-id="9176a-120">获取最新信息并使用最新的桌面软件和设备，同时降低安全风险并最大限度提高 IT 效率</span><span class="sxs-lookup"><span data-stu-id="9176a-120">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="9176a-121">有关详细信息，请参阅[使用 Microsoft 365 实现数字化化转型](http://transform.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="9176a-121">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

>[!Note]
><span data-ttu-id="9176a-122">若要同时部署 Windows 10 企业版和 Office 365 专业增强版，并迁移到[新式桌面](https://www.microsoft.com/microsoft-365/modern-desktop)，请参阅[新式桌面部署中心](http://aka.ms/howtoshift)。</span><span class="sxs-lookup"><span data-stu-id="9176a-122">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="9176a-123">Windows 10 部署</span><span class="sxs-lookup"><span data-stu-id="9176a-123">Windows 10 deployment</span></span>

<span data-ttu-id="9176a-124">您可以通过多种方式为您的组织部署 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="9176a-124">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="9176a-125">在这里, 我们将重点介绍如何通过这些新式部署方案配置和部署 Windows 10 企业版映像。</span><span class="sxs-lookup"><span data-stu-id="9176a-125">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="9176a-126">部署方案</span><span class="sxs-lookup"><span data-stu-id="9176a-126">Deployment scenario</span></span> | <span data-ttu-id="9176a-127">何时使用</span><span class="sxs-lookup"><span data-stu-id="9176a-127">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="9176a-128">使用 System Center Configuration Manager 作为就地升级</span><span class="sxs-lookup"><span data-stu-id="9176a-128">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="9176a-129">如果需要将 windows 7 或 windows 8.1 计算机升级到<a href="https://aka.ms/windows-10-release-information" target="_blank">当前版本</a>的 windows 10 企业版, 并且您的计算机当前是使用<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (当前分支)</a>进行管理的, 请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="9176a-129">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="9176a-130">使用 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="9176a-130">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="9176a-131">如果要设置 windows 10 企业版、版本1703或更高版本预安装的新 Windows 计算机, 请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="9176a-131">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="9176a-132">最终用户将使用所需的配置来启动安装程序, 方法是输入其工作或学校帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="9176a-132">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="9176a-133">如果这些部署方案不能满足您组织的需求, 您可以了解其他方案并了解每个方案在[Windows 10 部署方案](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的功能和限制。</span><span class="sxs-lookup"><span data-stu-id="9176a-133">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="9176a-134">您还可以对<a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 部署进行规划</a>。</span><span class="sxs-lookup"><span data-stu-id="9176a-134">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="9176a-135">您可以通过以下文章了解有关 Windows 10 的详细信息:</span><span class="sxs-lookup"><span data-stu-id="9176a-135">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="9176a-136">Microsoft 365 Enterprise 产品页</span><span class="sxs-lookup"><span data-stu-id="9176a-136">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="9176a-137">Windows 10</span><span class="sxs-lookup"><span data-stu-id="9176a-137">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="9176a-138">部署和更新 Windows 10</span><span class="sxs-lookup"><span data-stu-id="9176a-138">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="9176a-139">其他服务和功能</span><span class="sxs-lookup"><span data-stu-id="9176a-139">Additional services and features</span></span>
<span data-ttu-id="9176a-140">作为 Windows 10 企业版部署的一部分, 您可以添加这些额外的服务和功能。</span><span class="sxs-lookup"><span data-stu-id="9176a-140">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="9176a-141">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="9176a-141">Windows Analytics</span></span>

<span data-ttu-id="9176a-142">Windows 使用诊断数据提供丰富的可操作信息, 以帮助您深入了解操作效率以及环境中 Windows 10 设备的运行状况。</span><span class="sxs-lookup"><span data-stu-id="9176a-142">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="9176a-143">升级准备情况-升级准备情况将帮助您移动到 Windows 10, 并在新的 Windows 10 功能更新中保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="9176a-143">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="9176a-144">更新合规性-更新合规性面向希望获取其所有 Windows 10 设备的整体视图的 IT 管理员, 而无需任何其他基础结构要求。</span><span class="sxs-lookup"><span data-stu-id="9176a-144">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="9176a-145">设备运行状况-你可以使用设备运行状况主动检测并修正最终用户影响的问题。</span><span class="sxs-lookup"><span data-stu-id="9176a-145">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="9176a-146">有关详细信息, 请参阅[Windows Analytics 概述](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)。</span><span class="sxs-lookup"><span data-stu-id="9176a-146">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="9176a-147">Windows 安全</span><span class="sxs-lookup"><span data-stu-id="9176a-147">Windows security</span></span>

<span data-ttu-id="9176a-148">Windows 10 提供了一些功能, 可帮助保护抵御威胁、帮助保护设备和帮助访问控制。</span><span class="sxs-lookup"><span data-stu-id="9176a-148">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="9176a-149">使用 Windows 10 时, 你可以从一开始就获得保护设备的关键安全功能。</span><span class="sxs-lookup"><span data-stu-id="9176a-149">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="9176a-150">Microsoft 365 E3 添加了诸如 windows Hello 企业版、windows Defender 应用程序控制和 windows 信息保护等安全功能。</span><span class="sxs-lookup"><span data-stu-id="9176a-150">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="9176a-151">使用 microsoft 365 E5, 你可以从 microsoft 365 E3 security 和基于云的安全功能和 Windows Defender 高级威胁防护中获得所有保护。</span><span class="sxs-lookup"><span data-stu-id="9176a-151">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Windows Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="9176a-152">若要了解有关使用 Windows 10 企业版获取的安全功能的详细信息, 并获取有关如何部署、管理、配置三个关键 ecurity 功能并对其进行故障排除的指导, 请参阅[步骤 5: 部署 Windows 10 企业版安全功能](windows10-enable-security-features.md)。</span><span class="sxs-lookup"><span data-stu-id="9176a-152">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="9176a-153">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="9176a-153">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9176a-154">若要查看并了解公司如何规划、部署和管理 Windows 10 的更新, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="9176a-154">To peek inside Microsoft and learn how the company planned for, deployed, and is managing updates for Windows 10, see:</span></span>

- [<span data-ttu-id="9176a-155">为组织准备 Windows 10 无缝部署</span><span class="sxs-lookup"><span data-stu-id="9176a-155">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="9176a-156">在 Microsoft 中采用 Windows 作为服务</span><span class="sxs-lookup"><span data-stu-id="9176a-156">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="9176a-157">在 Microsoft 中将 Windows 10 部署为就地升级</span><span class="sxs-lookup"><span data-stu-id="9176a-157">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="9176a-158">使用 Windows Hello 企业版实现功能强大的用户身份验证</span><span class="sxs-lookup"><span data-stu-id="9176a-158">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="9176a-159">[Windows 10 部署：来自 Microsoft IT 部门的提示和技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)（视频）</span><span class="sxs-lookup"><span data-stu-id="9176a-159">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="9176a-160">Windows Defender ATP 有助于检测到复杂的威胁</span><span class="sxs-lookup"><span data-stu-id="9176a-160">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="9176a-161">[使用 Windows Defender 和 Windows Defender ATP 保护现代企业的安全](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP)（视频）</span><span class="sxs-lookup"><span data-stu-id="9176a-161">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="9176a-162">Contoso 是如何使用 Microsoft 365 企业版的</span><span class="sxs-lookup"><span data-stu-id="9176a-162">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9176a-163">请参阅 Contoso Corporation, 它是一个虚构但具有代表性的多国企业,[部署了 Windows 10 企业版](contoso-win10.md)。</span><span class="sxs-lookup"><span data-stu-id="9176a-163">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="9176a-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9176a-164">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="9176a-165">为 Windows 10 企业版准备组织</span><span class="sxs-lookup"><span data-stu-id="9176a-165">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
