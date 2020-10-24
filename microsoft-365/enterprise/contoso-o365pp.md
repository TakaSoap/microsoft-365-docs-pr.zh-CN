---
title: Contoso 的 Microsoft 365 企业应用版部署
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 来部署 Microsoft 365 企业应用版。
ms.openlocfilehash: 2c02c28ddba7c24592ce09d87bf6f5c9df700a2a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754340"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a><span data-ttu-id="9693c-103">Contoso 的 Microsoft 365 企业应用版部署</span><span class="sxs-lookup"><span data-stu-id="9693c-103">Microsoft 365 Apps for enterprise deployment for Contoso</span></span>

<span data-ttu-id="9693c-p101">Contoso 将他们的电脑升级到 Windows 10 企业版和 Microsoft 365 应用程序以实现更有效的协作、更好的安全性和更新式的桌面体验。在评估其基础结构和业务需求之后，Contoso 确定了部署的这些关键要求：</span><span class="sxs-lookup"><span data-stu-id="9693c-p101">Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience. After they assessed their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="9693c-106">所有电脑都应运行适用于企业的 Microsoft 365 应用。</span><span class="sxs-lookup"><span data-stu-id="9693c-106">All PCs should run Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="9693c-107">如果可能，部署应使用现有的管理工具和基础结构。</span><span class="sxs-lookup"><span data-stu-id="9693c-107">Deployment should use existing management tools and infrastructure when possible.</span></span>
- <span data-ttu-id="9693c-108">部署必须支持用户设备上的多种语言和现有体系结构。</span><span class="sxs-lookup"><span data-stu-id="9693c-108">Deployment must support multiple languages and existing architectures on users' devices.</span></span>
- <span data-ttu-id="9693c-109">电脑应保持最新并最小化 IT 管理成本和对用户的影响最小。</span><span class="sxs-lookup"><span data-stu-id="9693c-109">PCs should stay up-to-date and secure with minimal IT administrative costs and minimal impact to users.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="9693c-110">部署工具</span><span class="sxs-lookup"><span data-stu-id="9693c-110">Deployment tools</span></span>

<span data-ttu-id="9693c-p102">根据其要求，Contoso 选择通过 Configuration Manager 将 Windows 10 企业版和 Microsoft 365 应用程序部署到 Configuration Manager (当前分支) 。Configuration Manager 可扩展为大型环境，并提供对安装、更新和设置的广泛控制。它还具有内置功能，使您可以更轻松、更高效地部署和管理 Office，包括：</span><span class="sxs-lookup"><span data-stu-id="9693c-p102">Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise through Configuration Manager (Current Branch). Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Office, including:</span></span>

- <span data-ttu-id="9693c-114">对等缓存，在部署到远程位置的设备时，此缓存可帮助有限的网络容量。</span><span class="sxs-lookup"><span data-stu-id="9693c-114">Peer cache, which can help with limited network capacity when deploying to devices in remote locations.</span></span>
- <span data-ttu-id="9693c-115">Office 客户端管理仪表板，使管理员可以轻松地部署 Office 和监视器更新，并使管理员能够访问最新的部署和管理功能。</span><span class="sxs-lookup"><span data-stu-id="9693c-115">The Office Client Management dashboard, which makes it easy to deploy Office and monitor updates and gives administrators access to the latest deployment and management features.</span></span>
- <span data-ttu-id="9693c-116">智能语言包部署，包括自动部署与操作系统相同的语言。</span><span class="sxs-lookup"><span data-stu-id="9693c-116">Intelligent language pack deployment, including automatically deploying the same language as the operating system.</span></span>
- <span data-ttu-id="9693c-117">在部署过程中从客户端删除 Office 的现有版本的完全受支持且易于使用的方法。</span><span class="sxs-lookup"><span data-stu-id="9693c-117">A fully supported and easy-to-use method of removing existing versions of Office from a client during deployment.</span></span>

<span data-ttu-id="9693c-118">除了配置管理器，Contoso 还使用 [office 外接程序和 VBA 的准备工具包](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)，从 Microsoft 获取免费工具，以评估 Office 宏和外接程序的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="9693c-118">In addition to Configuration Manager, Contoso used the [Readiness Toolkit for Office add-ins and VBA](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), a free tool from Microsoft, to assess compatibility issues with their Office macros and add-ins.</span></span>

## <a name="managing-deployment-and-updates"></a><span data-ttu-id="9693c-119">管理部署和更新</span><span class="sxs-lookup"><span data-stu-id="9693c-119">Managing deployment and updates</span></span>

<span data-ttu-id="9693c-p103">适用于企业的 Microsoft 365 应用程序具有新的版本模型： Office 服务。利用服务模型，可以轻松保持最新的新功能。但通常需要 IT 部门来更改部署和测试新版本的方式。若要最大限度地减少兼容性问题，并确保其计算机保持最新，Contoso 在以下两个阶段部署了 Windows 和 Office：</span><span class="sxs-lookup"><span data-stu-id="9693c-p103">Microsoft 365 Apps for enterprise has a new release model: Office as a service. The service model makes it easy to stay up to date with new features. But it often requires IT departments to change how they deploy and test new releases. To minimize compatibility issues and to ensure their computers stay up to date, Contoso deployed Windows and Office in two stages:</span></span>

- <span data-ttu-id="9693c-124">首先，他们将 Microsoft 365 应用程序部署到整个组织中的一小部分代表性设备。</span><span class="sxs-lookup"><span data-stu-id="9693c-124">First, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization.</span></span> <span data-ttu-id="9693c-125">此试点组用于测试适用于企业的 Microsoft 365 应用程序的应用、加载项和硬件。</span><span class="sxs-lookup"><span data-stu-id="9693c-125">This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="9693c-126">四个月后，在解决了试点组中有关应用、加载项和硬件的所有关键问题后，Contoso 将 Microsoft 365 企业应用版部署到组织中的剩余设备（广泛组）。</span><span class="sxs-lookup"><span data-stu-id="9693c-126">Four months later, after addressing all critical issues with apps, add-ins, and hardware in the pilot group, Contoso deployed Microsoft 365 Apps for enterprise to the rest of the devices in the organization (the broad group).</span></span>

<span data-ttu-id="9693c-127">Contoso 启用了来自云的自动更新，而不是使用配置管理器管理 Office 更新。</span><span class="sxs-lookup"><span data-stu-id="9693c-127">Instead of managing updates to Office by using Configuration Manager, Contoso enabled automatic updates from the cloud.</span></span> <span data-ttu-id="9693c-128">基于云的更新可减少管理开销，同时确保设备保持最新。</span><span class="sxs-lookup"><span data-stu-id="9693c-128">Cloud-based updates reduce administrative overhead while ensuring that devices stay up to date.</span></span>

<span data-ttu-id="9693c-129">Contoso 对功能更新的使用相同的两阶段方法，因为它们用于部署 Office：引导组中的设备接收到的功能更新早于组织中其他地方的设备的四个月 (广泛的组) 。</span><span class="sxs-lookup"><span data-stu-id="9693c-129">Contoso followed the same two-stage approach for feature updates as they used for deploying Office: Devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group).</span></span> <span data-ttu-id="9693c-130">若要为 Office 启用此项，Contoso 使用了两个推荐的 [更新通道](https://docs.microsoft.com/DeployOffice/overview-update-channels)：</span><span class="sxs-lookup"><span data-stu-id="9693c-130">To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-update-channels):</span></span>

- <span data-ttu-id="9693c-131">试点组更新的 Enterprise 半年频道（预览）。</span><span class="sxs-lookup"><span data-stu-id="9693c-131">Semi-Annual Enterprise Channel (Preview) for updates to the pilot group</span></span>
- <span data-ttu-id="9693c-132">为广泛的组更新 Semi-Annual 企业渠道</span><span class="sxs-lookup"><span data-stu-id="9693c-132">Semi-Annual Enterprise Channel for updates to the broad group</span></span>

<span data-ttu-id="9693c-133">因为半年 Enterprise 频道（预览）发布 Microsoft 365 企业应用版的时间比半年 Enterprise 频道早 4 个月，所以，Contoso 有时间来验证更新，无需对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="9693c-133">Because the Semi-Annual Enterprise Channel (Preview) releases a version of Microsoft 365 Apps for enterprise four months earlier than the Semi-Annual Enterprise Channel, Contoso has time to validate the updates without having to manage them.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="9693c-134">部署过程</span><span class="sxs-lookup"><span data-stu-id="9693c-134">Deployment process</span></span>

<span data-ttu-id="9693c-135">为完成 Office 的部署，Contoso 实施了以下过程，其中包括来自 Microsoft 的最佳做法建议：</span><span class="sxs-lookup"><span data-stu-id="9693c-135">To complete the deployment of Office, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="9693c-136">在部署之前，Contoso 使用 Office 外接程序和 VBA 的准备情况工具包来测试其应用和 Office 加载项，以评估与 Microsoft 365 应用程序的兼容性，以供企业使用。</span><span class="sxs-lookup"><span data-stu-id="9693c-136">Before deployment, Contoso used the Readiness Toolkit for Office add-in and VBA to test their apps and Office Add-ins to assess their compatibility with Microsoft 365 Apps for enterprise.</span></span>
1. <span data-ttu-id="9693c-137">在配置管理器中，他们在其客户端设备上启用了对等缓存，这有助于在远程位置部署到客户端设备时具有有限的网络容量。</span><span class="sxs-lookup"><span data-stu-id="9693c-137">In Configuration Manager, they enabled peer cache on their client devices, which helps with limited network capacity when deploying to client devices in remote locations.</span></span> 
1. <span data-ttu-id="9693c-138">Contoso 在配置管理器中将两个部署组定义为设备集合：一个试点组和一个广泛的组。</span><span class="sxs-lookup"><span data-stu-id="9693c-138">Contoso defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group.</span></span> <span data-ttu-id="9693c-139">在整个组织中包含一小组代表设备的试点组用于对应用、外接程序和具有 Windows 10 企业版的 Microsoft 365 应用程序的硬件进行额外测试。</span><span class="sxs-lookup"><span data-stu-id="9693c-139">The pilot group, which included a small set of representative devices across the organization, was used for additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span></span>
1. <span data-ttu-id="9693c-140">他们通过使用 Office 客户端管理仪表板和 Office 365 安装程序向导（这两个都是 Configuration Manager 控制台的一部分）为 Office 创建了部署程序包。</span><span class="sxs-lookup"><span data-stu-id="9693c-140">They created deployment packages for Office by using the Office Client Management dashboard and the Office 365 Installer wizard, which are both part of the Configuration Manager console.</span></span> <span data-ttu-id="9693c-141">他们为企业包构建了两个 Microsoft 365 应用程序，一个用于 Semi-Annual 企业频道 (Preview) 上的试点组，另一个用于 Semi-Annual 企业频道上的广泛组。</span><span class="sxs-lookup"><span data-stu-id="9693c-141">They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel.</span></span>
2. <span data-ttu-id="9693c-142">每个 Office 程序包包括英语、法语和德语语言包。</span><span class="sxs-lookup"><span data-stu-id="9693c-142">Each Office package included English, French, and German Language packs.</span></span> <span data-ttu-id="9693c-143">如果设备需要的语言不包含在 Office 程序包中，则会自动从 Office 内容传递网络 (CDN) 下载该语言包。</span><span class="sxs-lookup"><span data-stu-id="9693c-143">If a device required a language that wasn't included in the Office package, that language pack was automatically downloaded from the Office Content Delivery Network (CDN).</span></span>
3. <span data-ttu-id="9693c-144">在安装 Microsoft 365 企业应用版前，它们使用 Office 包中的内置功能来自动删除所有现有的 Office 的 MSI 版本。</span><span class="sxs-lookup"><span data-stu-id="9693c-144">They used the built-in feature in the Office package to automatically remove all existing MSI versions of Office before installing Microsoft 365 Apps for enterprise.</span></span>
4. <span data-ttu-id="9693c-145">在配置管理器中，他们将 Windows 和 Office 包部署到其网络中的分发点。</span><span class="sxs-lookup"><span data-stu-id="9693c-145">In Configuration Manager, they deployed the Windows and Office packages to distribution points across their network.</span></span> <span data-ttu-id="9693c-146">然后，他们运行 Configuration Manager 部署任务序列，以将 Microsoft 365 应用程序的试点 Microsoft 应用程序包部署到试点组。</span><span class="sxs-lookup"><span data-stu-id="9693c-146">Then they ran the Configuration Manager deployment task sequences to deploy the pilot Microsoft 365 Apps for enterprise package to the pilot group.</span></span>
5. <span data-ttu-id="9693c-147">在他们解决了试点组的兼容性问题之后，Contoso 运行任务序列以将适用于企业的 Microsoft 365 应用程序包部署到广泛的组中。</span><span class="sxs-lookup"><span data-stu-id="9693c-147">After they addressed compatibility issues with the pilot group, Contoso ran the task sequences to deploy the Microsoft 365 Apps for enterprise package to the broad group.</span></span>

<span data-ttu-id="9693c-148">因为 Contoso 选择从云中自动更新设备，所以无需在 Configuration Manager 中管理过程。</span><span class="sxs-lookup"><span data-stu-id="9693c-148">Because Contoso chose to automatically update devices from the cloud, there was no need to manage the process in Configuration Manager.</span></span> <span data-ttu-id="9693c-149">他们的设备将根据初始部署中定义的更新通道，直接从云自动更新。</span><span class="sxs-lookup"><span data-stu-id="9693c-149">Their devices are automatically updated directly from the cloud-based on the update channel that was defined in the initial deployment.</span></span>

<span data-ttu-id="9693c-150">以下是 Contoso Microsoft 365 应用程序的企业安装和持续更新部署体系结构。</span><span class="sxs-lookup"><span data-stu-id="9693c-150">Here is the Contoso Microsoft 365 Apps for enterprise installation and ongoing updates deployment architecture.</span></span>

![适用于企业的 Microsoft 365 应用的 Contoso 部署基础结构](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a><span data-ttu-id="9693c-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9693c-152">Next step</span></span>

<span data-ttu-id="9693c-153">了解 Contoso 如何在 Microsoft 365 for 企业版中 [使用 Microsoft Intune](contoso-mdm.md) 来管理其设备以及他们在组织中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9693c-153">Learn how Contoso is [using Microsoft Intune](contoso-mdm.md) in Microsoft 365 for enterprise to manage its devices and the apps that they run across the organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="9693c-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9693c-154">See also</span></span>

[<span data-ttu-id="9693c-155">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="9693c-155">Microsoft 365 Apps for enterprise</span></span>](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[<span data-ttu-id="9693c-156">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="9693c-156">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9693c-157">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="9693c-157">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
