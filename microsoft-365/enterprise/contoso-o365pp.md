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
ms.openlocfilehash: 71958b2e87882e478a852db1f906f61207837854
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907670"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a><span data-ttu-id="6aa7e-103">Contoso 的 Microsoft 365 企业应用版部署</span><span class="sxs-lookup"><span data-stu-id="6aa7e-103">Microsoft 365 Apps for enterprise deployment for Contoso</span></span>

<span data-ttu-id="6aa7e-104">Contoso 将电脑升级到 Windows 10 企业版 Microsoft 365 企业应用版，以实现更有效的协作、更好的安全性和更现代化的桌面体验。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-104">Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience.</span></span> <span data-ttu-id="6aa7e-105">在评估其基础结构和业务需求后，Contoso 确定了这些部署的关键要求：</span><span class="sxs-lookup"><span data-stu-id="6aa7e-105">After they assessed their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="6aa7e-106">所有电脑都应在Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-106">All PCs should run Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="6aa7e-107">如果可能，部署应使用现有管理工具和基础结构。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-107">Deployment should use existing management tools and infrastructure when possible.</span></span>
- <span data-ttu-id="6aa7e-108">部署必须在用户设备上支持多种语言和现有体系结构。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-108">Deployment must support multiple languages and existing architectures on users' devices.</span></span>
- <span data-ttu-id="6aa7e-109">电脑应保持最新和安全，并尽量减少 IT 管理成本，并尽量减少对用户的影响。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-109">PCs should stay up-to-date and secure with minimal IT administrative costs and minimal impact to users.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="6aa7e-110">部署工具</span><span class="sxs-lookup"><span data-stu-id="6aa7e-110">Deployment tools</span></span>

<span data-ttu-id="6aa7e-111">根据要求，Contoso 选择通过 Configuration Manager Windows 10 企业版 Microsoft 365 企业应用版 Current Branch (部署) 。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-111">Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise through Configuration Manager (Current Branch).</span></span> <span data-ttu-id="6aa7e-112">Configuration Manager 可针对大型环境进行扩展，并提供对安装、更新和设置的广泛控制。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-112">Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings.</span></span> <span data-ttu-id="6aa7e-113">它还具有内置功能，以便更加轻松和高效地部署和管理Office，包括：</span><span class="sxs-lookup"><span data-stu-id="6aa7e-113">It also has built-in features to make it easier and more efficient to deploy and manage Office, including:</span></span>

- <span data-ttu-id="6aa7e-114">对等缓存，在部署到远程位置的设备时，可帮助实现有限的网络容量。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-114">Peer cache, which can help with limited network capacity when deploying to devices in remote locations.</span></span>
- <span data-ttu-id="6aa7e-115">The Office Client Management dashboard， which makes it easy to deploy Office and monitor updates and gives administrators access to the latest deployment and management features.</span><span class="sxs-lookup"><span data-stu-id="6aa7e-115">The Office Client Management dashboard, which makes it easy to deploy Office and monitor updates and gives administrators access to the latest deployment and management features.</span></span>
- <span data-ttu-id="6aa7e-116">智能语言包部署，包括自动部署与操作系统相同的语言。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-116">Intelligent language pack deployment, including automatically deploying the same language as the operating system.</span></span>
- <span data-ttu-id="6aa7e-117">一种完全受支持且易于使用的方法，用于部署期间从客户端Office现有版本的客户端。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-117">A fully supported and easy-to-use method of removing existing versions of Office from a client during deployment.</span></span>

<span data-ttu-id="6aa7e-118">除了 Configuration Manager 之外，Contoso 还使用 Toolkit for Office 加载项和[VBA（Microsoft](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)免费提供的工具）来评估其 Office 宏和加载项的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-118">In addition to Configuration Manager, Contoso used the [Readiness Toolkit for Office add-ins and VBA](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), a free tool from Microsoft, to assess compatibility issues with their Office macros and add-ins.</span></span>

## <a name="managing-deployment-and-updates"></a><span data-ttu-id="6aa7e-119">管理部署和更新</span><span class="sxs-lookup"><span data-stu-id="6aa7e-119">Managing deployment and updates</span></span>

<span data-ttu-id="6aa7e-120">Microsoft 365 企业应用版新的发布模型：Office即服务。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-120">Microsoft 365 Apps for enterprise has a new release model: Office as a service.</span></span> <span data-ttu-id="6aa7e-121">服务模型使使用新功能保持最新状态变得容易。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-121">The service model makes it easy to stay up to date with new features.</span></span> <span data-ttu-id="6aa7e-122">但通常需要 IT 部门更改其部署和测试新版本。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-122">But it often requires IT departments to change how they deploy and test new releases.</span></span> <span data-ttu-id="6aa7e-123">为了最大限度地减少兼容性问题并确保其计算机保持最新，Contoso 分两个阶段Windows Office和部署计算机：</span><span class="sxs-lookup"><span data-stu-id="6aa7e-123">To minimize compatibility issues and to ensure their computers stay up to date, Contoso deployed Windows and Office in two stages:</span></span>

- <span data-ttu-id="6aa7e-124">首先，他们Microsoft 365 企业应用版组织中一小组具有代表性的设备进行部署。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-124">First, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization.</span></span> <span data-ttu-id="6aa7e-125">此试点组用于测试应用、加载项和硬件Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-125">This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="6aa7e-126">四个月后，在解决了试点组中有关应用、加载项和硬件的所有关键问题后，Contoso 将 Microsoft 365 企业应用版部署到组织中的剩余设备（广泛组）。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-126">Four months later, after addressing all critical issues with apps, add-ins, and hardware in the pilot group, Contoso deployed Microsoft 365 Apps for enterprise to the rest of the devices in the organization (the broad group).</span></span>

<span data-ttu-id="6aa7e-127">Contoso 从云Office自动更新，而不是使用 Configuration Manager 管理更新。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-127">Instead of managing updates to Office by using Configuration Manager, Contoso enabled automatic updates from the cloud.</span></span> <span data-ttu-id="6aa7e-128">基于云的更新可减少管理开销，同时确保设备保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-128">Cloud-based updates reduce administrative overhead while ensuring that devices stay up to date.</span></span>

<span data-ttu-id="6aa7e-129">Contoso 对功能更新采用与用于部署 Office 相同的两阶段方法：试点组中设备接收功能更新的时间比组织中其余组织的设备早四个月 (广泛组) 。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-129">Contoso followed the same two-stage approach for feature updates as they used for deploying Office: Devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group).</span></span> <span data-ttu-id="6aa7e-130">若要为用户启用Office，Contoso 使用了两个推荐的[更新频道](/DeployOffice/overview-update-channels)：</span><span class="sxs-lookup"><span data-stu-id="6aa7e-130">To enable this for Office, Contoso used two recommended [update channels](/DeployOffice/overview-update-channels):</span></span>

- <span data-ttu-id="6aa7e-131">试点组更新的 Enterprise 半年频道（预览）。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-131">Semi-Annual Enterprise Channel (Preview) for updates to the pilot group</span></span>
- <span data-ttu-id="6aa7e-132">Semi-Annual Enterprise频道获取广泛组更新</span><span class="sxs-lookup"><span data-stu-id="6aa7e-132">Semi-Annual Enterprise Channel for updates to the broad group</span></span>

<span data-ttu-id="6aa7e-133">因为半年 Enterprise 频道（预览）发布 Microsoft 365 企业应用版的时间比半年 Enterprise 频道早 4 个月，所以，Contoso 有时间来验证更新，无需对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-133">Because the Semi-Annual Enterprise Channel (Preview) releases a version of Microsoft 365 Apps for enterprise four months earlier than the Semi-Annual Enterprise Channel, Contoso has time to validate the updates without having to manage them.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="6aa7e-134">部署过程</span><span class="sxs-lookup"><span data-stu-id="6aa7e-134">Deployment process</span></span>

<span data-ttu-id="6aa7e-135">为完成 Office 的部署，Contoso 实施了以下过程，其中包括来自 Microsoft 的最佳做法建议：</span><span class="sxs-lookup"><span data-stu-id="6aa7e-135">To complete the deployment of Office, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="6aa7e-136">在部署之前，Contoso 使用 Toolkit 和 VBA 的 Readiness Office 测试其应用和 Office 外接程序来评估其与 Microsoft 365 企业应用版 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-136">Before deployment, Contoso used the Readiness Toolkit for Office add-in and VBA to test their apps and Office Add-ins to assess their compatibility with Microsoft 365 Apps for enterprise.</span></span>
1. <span data-ttu-id="6aa7e-137">在 Configuration Manager 中，他们在客户端设备上启用了对等缓存，这有助于在部署到远程位置的客户端设备时具有有限的网络容量。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-137">In Configuration Manager, they enabled peer cache on their client devices, which helps with limited network capacity when deploying to client devices in remote locations.</span></span> 
1. <span data-ttu-id="6aa7e-138">Contoso 在 Configuration Manager 中将两个部署组定义为设备集合：试点组和广泛组。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-138">Contoso defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group.</span></span> <span data-ttu-id="6aa7e-139">试点组包括一小组跨组织的代表设备，用于对应用、加载项和硬件进行附加测试，Windows 10 企业版Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-139">The pilot group, which included a small set of representative devices across the organization, was used for additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise.</span></span>
1. <span data-ttu-id="6aa7e-140">他们通过使用 Office 客户端管理仪表板和 Office 365 Installer 向导为 Office 创建了部署包，这两者都是 Configuration Manager 控制台的一部分。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-140">They created deployment packages for Office by using the Office Client Management dashboard and the Office 365 Installer wizard, which are both part of the Configuration Manager console.</span></span> <span data-ttu-id="6aa7e-141">他们构建了两Microsoft 365 企业应用版包，一个适用于 Semi-Annual Enterprise Channel (Preview) 上的试点组，另一个适用于 Semi-Annual Enterprise Channel 上的广泛组。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-141">They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel.</span></span>
2. <span data-ttu-id="6aa7e-142">每个Office包都包含英语、法语和德语语言包。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-142">Each Office package included English, French, and German Language packs.</span></span> <span data-ttu-id="6aa7e-143">如果设备所需的语言未包含在 Office 程序包中，则会自动从 Office 内容分发网络 (CDN) 。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-143">If a device required a language that wasn't included in the Office package, that language pack was automatically downloaded from the Office Content Delivery Network (CDN).</span></span>
3. <span data-ttu-id="6aa7e-144">在安装 Microsoft 365 企业应用版前，它们使用 Office 包中的内置功能来自动删除所有现有的 Office 的 MSI 版本。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-144">They used the built-in feature in the Office package to automatically remove all existing MSI versions of Office before installing Microsoft 365 Apps for enterprise.</span></span>
4. <span data-ttu-id="6aa7e-145">在 Configuration Manager 中，他们部署了 Windows，Office程序包跨网络部署到分发点。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-145">In Configuration Manager, they deployed the Windows and Office packages to distribution points across their network.</span></span> <span data-ttu-id="6aa7e-146">然后，他们运行 Configuration Manager 部署任务序列，将试点Microsoft 365 企业应用版包部署到试点组。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-146">Then they ran the Configuration Manager deployment task sequences to deploy the pilot Microsoft 365 Apps for enterprise package to the pilot group.</span></span>
5. <span data-ttu-id="6aa7e-147">在解决了试点组的兼容性问题后，Contoso 运行任务序列以将Microsoft 365 企业应用版包部署到广泛组。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-147">After they addressed compatibility issues with the pilot group, Contoso ran the task sequences to deploy the Microsoft 365 Apps for enterprise package to the broad group.</span></span>

<span data-ttu-id="6aa7e-148">因为 Contoso 选择从云中自动更新设备，所以无需在 Configuration Manager 中管理过程。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-148">Because Contoso chose to automatically update devices from the cloud, there was no need to manage the process in Configuration Manager.</span></span> <span data-ttu-id="6aa7e-149">其设备会直接从基于云的自动更新，该更新通道是在初始部署中定义的。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-149">Their devices are automatically updated directly from the cloud-based on the update channel that was defined in the initial deployment.</span></span>

<span data-ttu-id="6aa7e-150">下面是 Contoso Microsoft 365 企业应用版安装和持续更新部署体系结构。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-150">Here is the Contoso Microsoft 365 Apps for enterprise installation and ongoing updates deployment architecture.</span></span>

![用于部署的 Contoso 部署Microsoft 365 企业应用版](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a><span data-ttu-id="6aa7e-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6aa7e-152">Next step</span></span>

<span data-ttu-id="6aa7e-153">了解 Contoso[](contoso-mdm.md)如何使用 Microsoft Intune Microsoft 365 企业版来管理其设备和他们在组织中运行的应用。</span><span class="sxs-lookup"><span data-stu-id="6aa7e-153">Learn how Contoso is [using Microsoft Intune](contoso-mdm.md) in Microsoft 365 for enterprise to manage its devices and the apps that they run across the organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="6aa7e-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6aa7e-154">See also</span></span>

[<span data-ttu-id="6aa7e-155">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="6aa7e-155">Microsoft 365 Apps for enterprise</span></span>](/deployoffice/deployment-guide-microsoft-365-apps)

[<span data-ttu-id="6aa7e-156">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="6aa7e-156">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6aa7e-157">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="6aa7e-157">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)