---
title: Contoso 的 Microsoft 365 企业应用版部署
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 来部署 Microsoft 365 企业应用版。
ms.openlocfilehash: de6a5348a49a490afa3c3ac632e66026966e2ef3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695154"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a><span data-ttu-id="f36a0-103">Contoso 的 Microsoft 365 企业应用版部署</span><span class="sxs-lookup"><span data-stu-id="f36a0-103">Microsoft 365 Apps for enterprise deployment for Contoso</span></span>

<span data-ttu-id="f36a0-p101">Contoso 将其电脑升级到 Windows 10 企业版和Microsoft 365 企业应用版，以实现更有效的协作、更好的安全性和更具现代化的桌面体验。在评估其基础结构和业务需要后，Contoso 为部署标识了这些关键要求：</span><span class="sxs-lookup"><span data-stu-id="f36a0-p101">Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience. After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="f36a0-106">所有电脑应运行 Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="f36a0-106">All PCs should run Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="f36a0-107">在可能的情况下，部署应使用现有管理工具和基础结构</span><span class="sxs-lookup"><span data-stu-id="f36a0-107">Deployment should use existing management tools and infrastructure when possible</span></span>
- <span data-ttu-id="f36a0-108">部署必须支持在最终用户设备上使用多种语言和现有体系结构</span><span class="sxs-lookup"><span data-stu-id="f36a0-108">Deployment must support multiple languages and existing architectures on end-user devices</span></span>
- <span data-ttu-id="f36a0-109">电脑应保持安装最新更新和安全性、使用最低的 IT 管理成本，并尽量减少对最终用户带来的影响</span><span class="sxs-lookup"><span data-stu-id="f36a0-109">PCs should stay up-to-date and secure with minimal IT administrative costs and with minimal impact to end-users</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="f36a0-110">部署工具</span><span class="sxs-lookup"><span data-stu-id="f36a0-110">Deployment tools</span></span>

<span data-ttu-id="f36a0-p102">基于其要求，Contoso 选择使用 Configuration Manager（当前分支）来部署 Windows 10 企业版和 Microsoft 365 企业应用版。Configuration Manager 针对大型环境进行扩展，并在安装、更新和设置过程中提供广泛的控制。它还具有内置功能，使其能够更为轻松和高效地部署和管理 Office，其中包括：</span><span class="sxs-lookup"><span data-stu-id="f36a0-p102">Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise with Configuration Manager (Current Branch). Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Office, including:</span></span>

- <span data-ttu-id="f36a0-114">对等缓存，在部署偏远位置的设备时，可帮助节省有限的网络容量</span><span class="sxs-lookup"><span data-stu-id="f36a0-114">Peer cache, which can help with limited network capacity when deploying to devices in remote locations</span></span>
- <span data-ttu-id="f36a0-115">Office 客户端管理仪表板，可轻松部署 Office 和监视更新，使管理员能够访问最新的部署和管理功能。</span><span class="sxs-lookup"><span data-stu-id="f36a0-115">The Office Client Management dashboard, which makes it easy to deploy Office and monitor updates and gives administrators access to the latest deployment and management features</span></span>
- <span data-ttu-id="f36a0-116">智能语言包部署，包括将同一语言自动作为操作系统部署。</span><span class="sxs-lookup"><span data-stu-id="f36a0-116">Intelligent language pack deployment, including automatically deploying the same language as the operating system</span></span>
- <span data-ttu-id="f36a0-117">在部署期间，将 Office 的现有版本从客户端删除的完全支持和易于使用的方法。</span><span class="sxs-lookup"><span data-stu-id="f36a0-117">Fully supported and easy-to-use method of removing existing versions of Office from a client during deployment</span></span>

<span data-ttu-id="f36a0-118">除 Configuration Manager 以外，Contoso 还使用 [Readiness Toolkit](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)（Microsoft 提供的一个免费工具）来评估有关其 Office 宏和加载项的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="f36a0-118">In addition to Configuration Manager, Contoso used the [Readiness Toolkit](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), a free tool from Microsoft, to assess compatibility issues with their Office macros and add-ins.</span></span>

## <a name="managing-the-deployment-and-updates"></a><span data-ttu-id="f36a0-119">管理部署和更新</span><span class="sxs-lookup"><span data-stu-id="f36a0-119">Managing the deployment and updates</span></span>

<span data-ttu-id="f36a0-p103">Microsoft 365 企业应用版推出了新的版本模式：Office 即服务。使用该服务模式能够轻松保持最新功能，但通常要求 IT 部门对部署和测试新版本的方法进行更改。为了最大程度减少任何兼容性问题并确保其计算机安装最新更新，Contoso 分两个阶段部署 Windows 和 Office：</span><span class="sxs-lookup"><span data-stu-id="f36a0-p103">Microsoft 365 Apps for enterprise has a new release model: Office as a service. The service model makes it easy to stay up to date with new features, but often requires a change in approach for IT departments in how new releases are deployed and tested. To minimize any compatibility issues and to ensure their computers stayed up to date, Contoso deployed Windows and Office in two stages:</span></span> 

- <span data-ttu-id="f36a0-p104">在第一阶段，它们将 Microsoft 365 企业应用版部署到一小组跨组织的代表设备。这一试点组用于测试 Microsoft 365 企业应用版中的应用、加载项和硬件</span><span class="sxs-lookup"><span data-stu-id="f36a0-p104">For the first stage, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization. This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="f36a0-125">四个月后，在解决了试点组中有关应用、加载项和硬件的所有关键问题后，Contoso 将 Microsoft 365 企业应用版部署到组织中的剩余设备（广泛组）。</span><span class="sxs-lookup"><span data-stu-id="f36a0-125">Four months later, after addressing all critical issues with apps, add-ins, and hardware in the pilot group, Contoso deployed Microsoft 365 Apps for enterprise to the rest of the devices in the organization (the broad group).</span></span> 

<span data-ttu-id="f36a0-p105">Contoso 从云中启用自动更新，而非使用 Configuration Manager 来管理 Office 的更新。基于云的更新可在减少其管理开销的同时确保设备安装最新更新。</span><span class="sxs-lookup"><span data-stu-id="f36a0-p105">Instead of managing updates to Office with Configuration Manager, Contoso enabled automatic updates from the cloud. Cloud-based updates reduced their administrative overhead while ensuring the devices stayed up to date.</span></span> 

<span data-ttu-id="f36a0-p106">Contoso 使用了与部署 Office 时相同的两阶段功能更新方法：试点组中的设备收到功能更新的时间比组织中的剩余组（广泛组）中的设备早 4 个月。为了为 Office 启用此功能，Contoso 使用了两个推荐的[更新频道](https://docs.microsoft.com/DeployOffice/overview-update-channels)：</span><span class="sxs-lookup"><span data-stu-id="f36a0-p106">Contoso followed the same two-stage approach for feature updates that they used for deploying Office: devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group). To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-update-channels):</span></span> 

- <span data-ttu-id="f36a0-130">试点组更新的 Enterprise 半年频道（预览）。</span><span class="sxs-lookup"><span data-stu-id="f36a0-130">Semi-Annual Enterprise Channel (Preview) for updates to the pilot group</span></span> 
- <span data-ttu-id="f36a0-131">广泛组更新的 Enterprise 半年频道。</span><span class="sxs-lookup"><span data-stu-id="f36a0-131">Semi-Annual Enterprise Channel for updates to the broad group.</span></span> 

<span data-ttu-id="f36a0-132">因为半年 Enterprise 频道（预览）发布 Microsoft 365 企业应用版的时间比半年 Enterprise 频道早 4 个月，所以，Contoso 有时间来验证更新，无需对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="f36a0-132">Because the Semi-Annual Enterprise Channel (Preview) releases a version of Microsoft 365 Apps for enterprise four months earlier than the Semi-Annual Enterprise Channel, Contoso has time to validate the updates without having to manage them.</span></span> 

## <a name="deployment-process"></a><span data-ttu-id="f36a0-133">部署过程</span><span class="sxs-lookup"><span data-stu-id="f36a0-133">Deployment process</span></span>

<span data-ttu-id="f36a0-134">为完成 Office 的部署，Contoso 实施了以下过程，其中包括来自 Microsoft 的最佳做法建议：</span><span class="sxs-lookup"><span data-stu-id="f36a0-134">To complete the deployment of Office, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="f36a0-135">在部署前，它们使用了 Readiness Toolkit 来测试其应用和 Office 加载项，以评估其与 Microsoft 365 企业应用版的兼容性。</span><span class="sxs-lookup"><span data-stu-id="f36a0-135">Before deploying, they used the Readiness Toolkit to test their apps and Office add-ins to assess their compatibility with Microsoft 365 Apps for enterprise.</span></span>
2. <span data-ttu-id="f36a0-136">在 Configuration Manager 中，Contoso 在其客户端设备上启用了对等缓存，在部署到偏远位置的客户端设备时，这有助于节省有限的网络容量。</span><span class="sxs-lookup"><span data-stu-id="f36a0-136">In Configuration Manager, Contoso enabled peer cache on their client devices, which helped with limited network capacity when deploying to client devices in remote locations.</span></span> 
3. <span data-ttu-id="f36a0-p107">它们将两个部署组作为 Configuration Manager 中的设备集合来定义：试点组和广泛组。试点组包含一小组跨组织的代表设备，用于对 Windows 10 企业版和 Microsoft 365 企业应用版中的应用、加载项和硬件执行其他测试。</span><span class="sxs-lookup"><span data-stu-id="f36a0-p107">They defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group. The pilot group, which included a small set of representative devices across the organization, was used to do additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span></span> 
4. <span data-ttu-id="f36a0-p108">它们使用 Office 客户端管理仪表板和 Office 365 安装程序向导（两者都是 Configuration Manager 控制台的一部分）为 Office 创建了部署包。生成了两个 Microsoft 365 企业应用版包，一个适用于半年 Enterprise 频道（预览）的试点组，另一个适用于半年 Enterprise 频道的广泛组。</span><span class="sxs-lookup"><span data-stu-id="f36a0-p108">They created deployment packages for Office using the Office Client Management dashboard and the Office 365 Installer wizard, both of which are part of the Configuration Manager console. They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel.</span></span> 
5. <span data-ttu-id="f36a0-p109">作为每个 Office 包的一部分，它们包含了英语、法语和德语包。如果某个设备要求的语言不在 Office 包内，则从 Office 内容交付网络 (CDN) 自动下载该语言。</span><span class="sxs-lookup"><span data-stu-id="f36a0-p109">As part of each Office package, they included English, French, and German Language packs. If a device required a language not included in the Office package, it was automatically downloaded from the Office Content Delivery Network (CDN).</span></span>
6. <span data-ttu-id="f36a0-143">在安装 Microsoft 365 企业应用版前，它们使用 Office 包中的内置功能来自动删除所有现有的 Office 的 MSI 版本。</span><span class="sxs-lookup"><span data-stu-id="f36a0-143">They used the built-in feature in the Office package to automatically remove all existing MSI versions of Office before installing Microsoft 365 Apps for enterprise.</span></span>
7. <span data-ttu-id="f36a0-144">在 Configuration Manager 中，它们将 Windows 和 Office 包部署到跨其网络的分发点，然后运行 Configuration Manager 部署任务序列，以将试点 Microsoft 365 企业应用版包部署到试点组。</span><span class="sxs-lookup"><span data-stu-id="f36a0-144">In Configuration Manager, they deployed the Windows and Office packages to distribution points across their network, and then ran the Configuration Manager deployment task sequences to deploy the pilot Microsoft 365 Apps for enterprise package to the pilot group.</span></span>
8. <span data-ttu-id="f36a0-145">在解决了试点组中的任何兼容性问题后，Contoso 运行任务序列，以将广泛 Microsoft 365 企业应用版包部署到广泛组。</span><span class="sxs-lookup"><span data-stu-id="f36a0-145">After addressing any compatibility issues with the pilot group, Contoso ran the task sequences to deploy the broad Microsoft 365 Apps for enterprise package to the broad group.</span></span>

<span data-ttu-id="f36a0-146">因为 Contoso 选择从云中自动更新设备，所以无需在 Configuration Manager 中管理过程。</span><span class="sxs-lookup"><span data-stu-id="f36a0-146">Because Contoso chose to automatically update devices from the cloud, there was no need to manage the process in Configuration Manager.</span></span> <span data-ttu-id="f36a0-147">将直接从云中自动更新其设备，具体取决于作为初始部署定义的更新频道。</span><span class="sxs-lookup"><span data-stu-id="f36a0-147">Their devices are automatically updated directly from the cloud-based on the update channel that was defined as part of the initial deployment.</span></span> 

<span data-ttu-id="f36a0-148">下面是 Contoso 的 Microsoft 365 企业应用版安装和持续更新部署体系结构。</span><span class="sxs-lookup"><span data-stu-id="f36a0-148">Here is Contoso’s Microsoft 365 Apps for enterprise installation and ongoing updates deployment architecture.</span></span>

![Contoso 的 Microsoft 365 企业应用版部署基础结构](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a><span data-ttu-id="f36a0-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f36a0-150">Next step</span></span>

<span data-ttu-id="f36a0-151">[了解](contoso-mdm.md) Contoso 如何在 microsoft 365 for 企业版中使用 microsoft Intune 来管理其设备以及在其组织中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f36a0-151">[Learn](contoso-mdm.md) how Contoso is using Microsoft Intune in Microsoft 365 for enterprise to manage its devices and the apps that run on them across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="f36a0-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f36a0-152">See also</span></span>

[<span data-ttu-id="f36a0-153">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="f36a0-153">Microsoft 365 Apps for enterprise</span></span>](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[<span data-ttu-id="f36a0-154">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="f36a0-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f36a0-155">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="f36a0-155">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
