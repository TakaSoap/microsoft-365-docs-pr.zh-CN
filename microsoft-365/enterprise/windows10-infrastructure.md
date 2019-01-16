---
title: Microsoft 365 enterprise 的 Windows 10 企业基础结构
description: 在 Microsoft 365 Enterprise 的一部分部署 Pc 上的 Windows 10 Enterprise 所需的步骤提供高级指导。
keywords: Microsoft 365 Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业部署
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865403"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="2e2c8-104">阶段 3：Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="2e2c8-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="2e2c8-p101">Microsoft 365 企业版包括 Windows 10 Enterprise，为您提供的工具来执行操作的详细信息，并保持安全。Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="2e2c8-p101">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure. Windows 10 Enterprise:</span></span>

- <span data-ttu-id="2e2c8-107">**为了简单起见集成**的工具在云中的强大功能可帮助减少管理今天的复杂性的现代 IT 设备环境，无论大小。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="2e2c8-108">**具有智能安全**-以往任何时候都是最安全的版本的 Windows、 智能安全功能，旨在协同工作以更好地保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="2e2c8-109">**使创造和团队协作**-解除对创造和团队合作，以提供最高效体验的用户和 IT 将喜欢的事物。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="2e2c8-p102">您需要了解不同的方式可以部署 Windows 10 操作系统，然后选择适合您的组织。根据您的 Microsoft 365 企业版订阅，也有 Windows 10 服务和安全功能，您需要配置为充分利用 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-p102">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization. Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

<span data-ttu-id="2e2c8-112">Windows 10 启用 Microsoft 365 企业版这些战略业务方案：</span><span class="sxs-lookup"><span data-stu-id="2e2c8-112">Windows 10 enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="2e2c8-113">通过使员工能够发现、共享和改进整个组织的文件、信息和想法，充分利用集体知识和专长</span><span class="sxs-lookup"><span data-stu-id="2e2c8-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="2e2c8-114">随时随地跨设备安全工作，在保持灵活工作方式的同时实现更多功能</span><span class="sxs-lookup"><span data-stu-id="2e2c8-114">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="2e2c8-115">提供尽可安心的控件和可见性，行业认证达标且符合全球标准</span><span class="sxs-lookup"><span data-stu-id="2e2c8-115">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="2e2c8-116">保护信息并降低数据丢失的风险</span><span class="sxs-lookup"><span data-stu-id="2e2c8-116">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="2e2c8-117">检测防范外部威胁-监视器报告和分析活动迅速做出反应以提供组织的安全</span><span class="sxs-lookup"><span data-stu-id="2e2c8-117">Detect and protect against external threats --Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="2e2c8-118">保护您的用户和其帐户</span><span class="sxs-lookup"><span data-stu-id="2e2c8-118">Protect your users and their accounts</span></span>
- <span data-ttu-id="2e2c8-119">帮助组织增强隐私和合规性以符合一般数据保护条例 (GDPR)</span><span class="sxs-lookup"><span data-stu-id="2e2c8-119">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>
- <span data-ttu-id="2e2c8-120">获取最新信息并使用最新的桌面软件和设备，同时降低安全风险并最大限度提高 IT 效率</span><span class="sxs-lookup"><span data-stu-id="2e2c8-120">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="2e2c8-121">有关详细信息，请参阅[使用 Microsoft 365 实现数字化化转型](http://transform.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-121">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

>[!Note]
><span data-ttu-id="2e2c8-122">若要同时部署 Windows 10 企业版和 Office 365 专业增强版，并迁移到[新式桌面](https://www.microsoft.com/microsoft-365/modern-desktop)，请参阅[新式桌面部署中心](http://aka.ms/howtoshift)。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-122">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="2e2c8-123">Windows 10 部署</span><span class="sxs-lookup"><span data-stu-id="2e2c8-123">Windows 10 deployment</span></span>

<span data-ttu-id="2e2c8-p103">有多种方法可以为您的组织中部署 Windows 10 Enterprise。在这里，我们将专注于如何配置和部署 Windows 10 Enterprise 映像通过这些现代的部署方案。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-p103">There are multiple ways you can deploy Windows 10 Enterprise for your organization. Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="2e2c8-126">部署方案</span><span class="sxs-lookup"><span data-stu-id="2e2c8-126">Deployment scenario</span></span> | <span data-ttu-id="2e2c8-127">何时使用它</span><span class="sxs-lookup"><span data-stu-id="2e2c8-127">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="2e2c8-128">使用 System Center Configuration Manager 作为就地升级</span><span class="sxs-lookup"><span data-stu-id="2e2c8-128">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="2e2c8-129">如果您需要升级 Windows 7 或<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager （当前分支）</a>与当前托管到 Windows 10 Enterprise 的<a href="https://aka.ms/windows-10-release-information" target="_blank">当前版本</a>的 Windows 8.1 计算机和您的计算机，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-129">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="2e2c8-130">使用 Windows 自动执行某些操作</span><span class="sxs-lookup"><span data-stu-id="2e2c8-130">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="2e2c8-p104">如果要设置新有 Windows 10 Enterprise 1703 或更高版本预安装版本的 Windows 计算机，请选择此选项。最终用户将启动安装程序使用通过输入其工作所需的配置或学校帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-p104">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed. End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="2e2c8-p105">如果这些部署方案不适合您组织的需要，您可以了解其他方案，并了解功能和限制的[Windows 10 部署方案](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的每个。您还可以在您自己的<a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 部署规划</a>。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-p105">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="2e2c8-135">您可以使用这些文章了解有关 Windows 10 的详细信息：</span><span class="sxs-lookup"><span data-stu-id="2e2c8-135">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="2e2c8-136">Microsoft 365 Enterprise 产品页</span><span class="sxs-lookup"><span data-stu-id="2e2c8-136">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="2e2c8-137">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e2c8-137">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="2e2c8-138">部署和更新 Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e2c8-138">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="2e2c8-139">其他服务和功能</span><span class="sxs-lookup"><span data-stu-id="2e2c8-139">Additional services and features</span></span>
<span data-ttu-id="2e2c8-140">作为 Windows 10 企业的部署的一部分，您可以添加这些其他服务和功能。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-140">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="2e2c8-141">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="2e2c8-141">Windows Analytics</span></span>

<span data-ttu-id="2e2c8-142">Windows 使用诊断数据提供丰富的、 可操作的信息，以帮助您获得深度见解运营效率和您的环境中的 Windows 10 设备的运行状况。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-142">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="2e2c8-143">升级准备-升级准备将帮助您将移动到 Windows 10 和获得最新的 Windows 10 功能更新。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-143">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="2e2c8-144">更新合规性-更新合规性被面向 IT 管理员用户想要获取其所有 Windows 10 设备，无需任何其他基础结构要求的整体视图。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-144">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="2e2c8-145">设备运行状况-您可以使用设备运行状况主动检测和修正最终用户产生影响的问题。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-145">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="2e2c8-146">有关详细信息，请参阅[Windows 分析 Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) 。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-146">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="2e2c8-147">Windows 安全</span><span class="sxs-lookup"><span data-stu-id="2e2c8-147">Windows security</span></span>

<span data-ttu-id="2e2c8-p106">Windows 10 提供了功能来帮助保护抵御威胁，帮助您保护您的设备，并帮助访问控制。使用 Windows 10，您可以获取从开始保护您的设备右侧的重要的安全功能。Microsoft 365 E3 将添加业务、 Windows Defender 应用程序控制和 Windows 信息保护安全功能，如 Windows Hello。与 Microsoft 365 E5 从 Microsoft 365 E3 安全以及基于云的安全功能和 Windows Defender 高级威胁保护获取所有保护。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-p106">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control. With Windows 10, you get critical security features that protect your device right from the start. Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection. With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Windows Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="2e2c8-152">若要了解有关您获取 Windows 10 Enterprise 和获取指导如何部署、 管理、 配置和解决三个关键安全功能的安全功能的详细信息，请参阅[第 5 步： 部署 Windows 10 企业安全功能](windows10-enable-security-features.md)。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-152">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="2e2c8-153">Microsoft 如何使用 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="2e2c8-153">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2e2c8-154">若要查看 Microsoft 内部并了解公司如何规划、 部署，以及管理更新的 Windows 10，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2e2c8-154">To peek inside Microsoft and learn how the company planned for, deployed, and is managing updates for Windows 10, see:</span></span>

- [<span data-ttu-id="2e2c8-155">为组织准备 Windows 10 无缝部署</span><span class="sxs-lookup"><span data-stu-id="2e2c8-155">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="2e2c8-156">在 Microsoft 中采用 Windows 作为服务</span><span class="sxs-lookup"><span data-stu-id="2e2c8-156">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="2e2c8-157">在 Microsoft 中将 Windows 10 部署为就地升级</span><span class="sxs-lookup"><span data-stu-id="2e2c8-157">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="2e2c8-158">使用 Windows Hello 企业版实现功能强大的用户身份验证</span><span class="sxs-lookup"><span data-stu-id="2e2c8-158">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="2e2c8-159">[Windows 10 部署：来自 Microsoft IT 部门的提示和技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)（视频）</span><span class="sxs-lookup"><span data-stu-id="2e2c8-159">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="2e2c8-160">Windows Defender ATP 有助于检测到复杂的威胁</span><span class="sxs-lookup"><span data-stu-id="2e2c8-160">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="2e2c8-161">[使用 Windows Defender 和 Windows Defender ATP 保护现代企业的安全](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP)（视频）</span><span class="sxs-lookup"><span data-stu-id="2e2c8-161">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="2e2c8-162">Contoso 如何使用 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="2e2c8-162">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2e2c8-163">请参阅如何 Contoso Corporation、 虚构但代表性跨国企业、[部署 Windows 10 Enterprise](contoso-win10.md)。</span><span class="sxs-lookup"><span data-stu-id="2e2c8-163">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="2e2c8-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2e2c8-164">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="2e2c8-165">准备您的组织 Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2e2c8-165">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
