---
title: 适用于 Microsoft 365 企业版的 Windows 10 企业版基础结构
description: 提供了在 Microsoft 365 企业版中将 Windows 10 企业版部署到电脑上所需步骤的高级别指南。
keywords: Microsoft 365，Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业版，部署
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 3b4a0174e96fec1591bcac7ba58bcc7d57db8c87
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552682"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="7a33f-104">阶段 3：Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="7a33f-104">Phase 3: Windows 10 Enterprise</span></span>

![阶段 3：Windows 10 企业版](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="7a33f-106">Microsoft 365 企业版包括 Windows 10 企业版，为您提供用于执行更多和保持安全保护的工具。</span><span class="sxs-lookup"><span data-stu-id="7a33f-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="7a33f-107">Windows 10 企业版：</span><span class="sxs-lookup"><span data-stu-id="7a33f-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="7a33f-108">**集成为简单起见**-充分利用云的功能来帮助降低管理当今新式 IT 设备环境的复杂性，而不考虑大小。</span><span class="sxs-lookup"><span data-stu-id="7a33f-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="7a33f-109">**具有智能安全性**-它是最安全的 Windows 发布，具有旨在协同工作以更好地保护组织的智能安全功能。</span><span class="sxs-lookup"><span data-stu-id="7a33f-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="7a33f-110">**实现创造性和团队合作**-解锁创造性和团队合作，以提供用户最喜爱的工作体验。</span><span class="sxs-lookup"><span data-stu-id="7a33f-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="7a33f-111">您需要了解部署 Windows 10 操作系统的不同方法，并为您的组织选择正确的方法。</span><span class="sxs-lookup"><span data-stu-id="7a33f-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="7a33f-112">根据你的 Microsoft 365 企业版订阅，还需要配置 Windows 10 服务和安全功能，以充分利用 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="7a33f-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="7a33f-113">若要同时将 Windows 10 企业版和 Microsoft 365 应用程序部署到企业并转到[新式桌面](https://www.microsoft.com/microsoft-365/modern-desktop)，请参阅[新式桌面部署中心](https://aka.ms/howtoshift)。</span><span class="sxs-lookup"><span data-stu-id="7a33f-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="7a33f-114">Windows 10 部署</span><span class="sxs-lookup"><span data-stu-id="7a33f-114">Windows 10 deployment</span></span>

<span data-ttu-id="7a33f-115">您可以通过多种方式为您的组织部署 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="7a33f-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="7a33f-116">在这里，我们将重点介绍如何通过这些新式部署方案配置和部署 Windows 10 企业版映像。</span><span class="sxs-lookup"><span data-stu-id="7a33f-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="7a33f-117">部署方案</span><span class="sxs-lookup"><span data-stu-id="7a33f-117">Deployment scenario</span></span> | <span data-ttu-id="7a33f-118">何时使用</span><span class="sxs-lookup"><span data-stu-id="7a33f-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="7a33f-119">使用 Microsoft 终结点配置管理器作为就地升级</span><span class="sxs-lookup"><span data-stu-id="7a33f-119">Using Microsoft Endpoint Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="7a33f-120">如果您需要将 Windows 7 或 Windows 8.1 计算机升级到<a href="https://aka.ms/windows-10-release-information" target="_blank">当前版本</a>的 Windows 10 企业版，并且您的计算机当前是使用<a href="https://docs.microsoft.com/mem/configmgr/core/understand/introduction" target="_blank">Configuration Manager (当前分支) </a>管理的，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7a33f-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://docs.microsoft.com/mem/configmgr/core/understand/introduction" target="_blank">Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="7a33f-121">使用 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="7a33f-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="7a33f-122">如果要设置 Windows 10 企业版、版本1703或更高版本预安装的新 Windows 计算机，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7a33f-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="7a33f-123">最终用户将使用所需的配置来启动安装程序，方法是输入其工作或学校帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="7a33f-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="7a33f-124">如果这些部署方案不能满足您组织的需求，您可以了解其他方案并了解每个方案在[Windows 10 部署方案](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的功能和限制。</span><span class="sxs-lookup"><span data-stu-id="7a33f-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="7a33f-125">也可以自行<a href="https://aka.ms/planforwin10deployment" target="_blank">计划 Windows 10 部署</a>。</span><span class="sxs-lookup"><span data-stu-id="7a33f-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="7a33f-126">您可以通过以下文章了解有关 Windows 10 的详细信息：</span><span class="sxs-lookup"><span data-stu-id="7a33f-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="7a33f-127">Microsoft 365 Enterprise 产品页</span><span class="sxs-lookup"><span data-stu-id="7a33f-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="7a33f-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7a33f-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="7a33f-129">部署和更新 Windows 10</span><span class="sxs-lookup"><span data-stu-id="7a33f-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="7a33f-130">其他服务和功能</span><span class="sxs-lookup"><span data-stu-id="7a33f-130">Additional services and features</span></span>
<span data-ttu-id="7a33f-131">作为 Windows 10 企业版部署的一部分，您可以添加这些额外的服务和功能。</span><span class="sxs-lookup"><span data-stu-id="7a33f-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="desktop-analytics"></a><span data-ttu-id="7a33f-132">桌面分析</span><span class="sxs-lookup"><span data-stu-id="7a33f-132">Desktop Analytics</span></span>

<span data-ttu-id="7a33f-133">Windows 使用诊断数据提供丰富的可操作信息，以帮助您深入了解操作效率以及环境中 Windows 10 设备的运行状况。</span><span class="sxs-lookup"><span data-stu-id="7a33f-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="7a33f-134">升级准备情况-升级准备情况将帮助您移动到 Windows 10，并在新的 Windows 10 功能更新中保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="7a33f-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="7a33f-135">更新合规性-更新合规性面向希望获取其所有 Windows 10 设备的整体视图的 IT 管理员，而无需任何其他基础结构要求。</span><span class="sxs-lookup"><span data-stu-id="7a33f-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="7a33f-136">设备运行状况-你可以使用设备运行状况主动检测并修正最终用户影响的问题。</span><span class="sxs-lookup"><span data-stu-id="7a33f-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="7a33f-137">有关详细信息，请参阅[桌面 Analytics 概述](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)。</span><span class="sxs-lookup"><span data-stu-id="7a33f-137">See [Desktop Analytics Overview](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="7a33f-138">Windows 安全</span><span class="sxs-lookup"><span data-stu-id="7a33f-138">Windows security</span></span>

<span data-ttu-id="7a33f-139">Windows 10 提供了一些功能，可帮助保护抵御威胁、帮助保护设备和帮助访问控制。</span><span class="sxs-lookup"><span data-stu-id="7a33f-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="7a33f-140">使用 Windows 10 时，你可以从一开始就获得保护设备的关键安全功能。</span><span class="sxs-lookup"><span data-stu-id="7a33f-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="7a33f-141">Microsoft 365 E3 添加了诸如 Windows Hello 企业版、Windows Defender 应用程序控制和 Windows 信息保护等安全功能。</span><span class="sxs-lookup"><span data-stu-id="7a33f-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="7a33f-142">使用 Microsoft 365 E5，你可以从 Microsoft 365 E3 security 和基于云的安全功能以及 Microsoft Defender 高级威胁防护中获得所有保护。</span><span class="sxs-lookup"><span data-stu-id="7a33f-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="7a33f-143">若要了解有关使用 Windows 10 企业版获取的安全功能的详细信息，并获取有关如何部署、管理、配置三种关键安全功能以及排除这些问题的指导，请参阅[步骤5：部署 Windows 10 企业版安全功能](windows10-enable-security-features.md)。</span><span class="sxs-lookup"><span data-stu-id="7a33f-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key security features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="7a33f-144">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="7a33f-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7a33f-145">查看并了解公司如何[部署 Windows 10 企业版，以及如何使用强大的身份验证、Intune 和 Microsoft DEFENDER ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6)。</span><span class="sxs-lookup"><span data-stu-id="7a33f-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="7a33f-146">Contoso 是如何使用 Microsoft 365 企业版的</span><span class="sxs-lookup"><span data-stu-id="7a33f-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7a33f-147">请参阅 Contoso Corporation，它是一个虚构但具有代表性的多国企业，[部署了 Windows 10 企业版](contoso-win10.md)。</span><span class="sxs-lookup"><span data-stu-id="7a33f-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="7a33f-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7a33f-149">Next step</span></span>

|||
|:-------|:-----|
|![第 1 步](../media/stepnumbers/Step1.png)| [<span data-ttu-id="7a33f-151">为 Windows 10 企业版准备组织</span><span class="sxs-lookup"><span data-stu-id="7a33f-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
