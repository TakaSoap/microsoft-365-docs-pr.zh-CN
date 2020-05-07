---
title: 3. 部署设备、电脑和其他终结点的终结点管理
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: 使用 Microsoft Endpoint Manager 管理管理设备、电脑和其他终结点。
ms.openlocfilehash: 2a5b047aabb95d0b60c46fe3bec339e723adee0e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049576"
---
# <a name="3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="3acdd-103">3. 部署设备、电脑和其他终结点的终结点管理</span><span class="sxs-lookup"><span data-stu-id="3acdd-103">3. Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="3acdd-104">使用远程工作者，需要支持越来越多的个人设备。</span><span class="sxs-lookup"><span data-stu-id="3acdd-104">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="3acdd-105">终结点管理是一种基于策略的安全方法，要求设备在获得对资源的访问权限之前满足特定条件。</span><span class="sxs-lookup"><span data-stu-id="3acdd-105">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="3acdd-106">Microsoft Endpoint Manager 提供新式工作区和新式管理功能，使你的数据在云中和本地保持安全。</span><span class="sxs-lookup"><span data-stu-id="3acdd-106">Microsoft Endpoint Manager delivers a modern workplace and modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="3acdd-107">Endpoint Manager 通过结合以下可能已知和正在使用的服务，提供用于管理移动设备、台式计算机、虚拟机、嵌入式设备和服务器的服务和工具。</span><span class="sxs-lookup"><span data-stu-id="3acdd-107">Endpoint Manager provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![用于终结点管理的组件](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="3acdd-109">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3acdd-109">Microsoft Intune</span></span>

<span data-ttu-id="3acdd-110">Intune 旨在帮助你在不管理用于访问组织数据的设备时保护数据。</span><span class="sxs-lookup"><span data-stu-id="3acdd-110">Intune is designed to help you safeguard data when you don’t manage the devices used to access organization data.</span></span> <span data-ttu-id="3acdd-111">Intune 应用保护策略与 Azure AD 条件访问相结合，提供对移动设备上的数据的精细控制。</span><span class="sxs-lookup"><span data-stu-id="3acdd-111">Intune app protection policies combined with Azure AD Conditional Access provide granular control over data on mobile devices.</span></span> <span data-ttu-id="3acdd-112">借助 Intune，你还可以定义全面的策略，仅允许适当人员在适当条件下访问你的公司数据，并通过控制其在 Office、Outlook 和其他移动应用中使用数据的方式来确保数据持续受保护。</span><span class="sxs-lookup"><span data-stu-id="3acdd-112">Intune also enables you to define comprehensive policies that allow only the right people under the right conditions to access your company data and ensure the data stays protected by controlling how they use it within Office, Outlook and other mobile apps.</span></span>

<span data-ttu-id="3acdd-113">有关详细信息，请参阅此 [Microsoft Intune 概述](https://docs.microsoft.com/intune/fundamentals/what-is-intune)。</span><span class="sxs-lookup"><span data-stu-id="3acdd-113">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="3acdd-114">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3acdd-114">Configuration Manager</span></span>

<span data-ttu-id="3acdd-115">Configuration Manager 是一种本地管理解决方案，可用于管理网络上或基于 Internet 的台式机、服务器和笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="3acdd-115">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="3acdd-116">可通过云使其与 Intune、Azure AD、Microsoft Defender ATP 和其他云服务集成。</span><span class="sxs-lookup"><span data-stu-id="3acdd-116">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender ATP, and other cloud services.</span></span> <span data-ttu-id="3acdd-117">使用 Configuration Manager 部署应用程序、软件更新和操作系统。</span><span class="sxs-lookup"><span data-stu-id="3acdd-117">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="3acdd-118">还可以实时监视客户端上的合规性、查询和操作等。</span><span class="sxs-lookup"><span data-stu-id="3acdd-118">You can also monitor compliance, query and act on clients in real time, and much more.</span></span>

<span data-ttu-id="3acdd-119">有关详细信息，请参阅此 [Configuration Manager 概述](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="3acdd-119">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="3acdd-120">协同管理</span><span class="sxs-lookup"><span data-stu-id="3acdd-120">Co-management</span></span>

<span data-ttu-id="3acdd-121">协同管理使用 Intune 和其他 Microsoft 365 云服务，将现有的 Configuration Manager 投资与云相结合。</span><span class="sxs-lookup"><span data-stu-id="3acdd-121">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="3acdd-122">由你选择将 Configuration Manager 还是 Intune 作为 7 个不同工作负载组的管理机构。</span><span class="sxs-lookup"><span data-stu-id="3acdd-122">You choose whether Configuration Manager or Intune is the management authority for the seven different workload groups.</span></span>

<span data-ttu-id="3acdd-123">作为 Endpoint Manager 的一部分，协同管理使用云功能，包括条件访问。</span><span class="sxs-lookup"><span data-stu-id="3acdd-123">As part of Endpoint Manager, co-management uses cloud features, including Conditional Access.</span></span> <span data-ttu-id="3acdd-124">在云中使用 Intune 运行其他任务时，可将某些任务保留为本地。</span><span class="sxs-lookup"><span data-stu-id="3acdd-124">You keep some tasks on-premises, while running other tasks in the cloud with Intune.</span></span>

<span data-ttu-id="3acdd-125">有关详细信息，请参阅此[协同管理概述](https://docs.microsoft.com/mem/configmgr/comanage/overview)。</span><span class="sxs-lookup"><span data-stu-id="3acdd-125">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="3acdd-126">桌面分析</span><span class="sxs-lookup"><span data-stu-id="3acdd-126">Desktop Analytics</span></span>

<span data-ttu-id="3acdd-127">桌面分析是一种基于云的服务，可与 Configuration Manager 集成并为你提供洞察和情报，以便就 Windows 客户端作出明智决策。</span><span class="sxs-lookup"><span data-stu-id="3acdd-127">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="3acdd-128">它将组织中的数据与连接到 Microsoft 云服务的数百万台设备的数据合并。</span><span class="sxs-lookup"><span data-stu-id="3acdd-128">It combines data from your organization with data aggregated from millions of devices connected to Microsoft cloud services.</span></span> <span data-ttu-id="3acdd-129">借助桌面分析，可以创建在组织中运行的应用程序清单、评估与最新 Windows 10 功能更新的应用兼容性、识别兼容性问题、接收基于已启用云的数据见解的缓解建议、在最小的设备组中创建代表整个应用程序和驱动程序的试验组，并将 Windows 10 部署到试点和生产管理的设备。</span><span class="sxs-lookup"><span data-stu-id="3acdd-129">With Desktop Analytics, you can create an inventory of apps running in your organization, assess app compatibility with the latest Windows 10 feature updates, identify compatibility issues, and receive mitigation suggestions based on cloud-enabled data insights, create pilot groups that represent the entire application and driver estate across a minimal set of devices, and deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="3acdd-130">有关详细信息，请参阅此[桌面分析概述](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)。</span><span class="sxs-lookup"><span data-stu-id="3acdd-130">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="3acdd-131">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="3acdd-131">Windows Autopilot</span></span>

<span data-ttu-id="3acdd-132">Windows Autopilot 是一个零接触、自助式的 Windows 部署平台。</span><span class="sxs-lookup"><span data-stu-id="3acdd-132">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="3acdd-133">它包括一组用于设置和预配置新设备，以使它们可供高效使用的技术。</span><span class="sxs-lookup"><span data-stu-id="3acdd-133">It includes a collection of technologies used to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="3acdd-134">还可以使用 Windows Autopilot 来重置、恢复设备并重新调整其用途。</span><span class="sxs-lookup"><span data-stu-id="3acdd-134">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> <span data-ttu-id="3acdd-135">此解决方案可以让 IT 部门通过轻松简单的流程，在几乎不需要管理基础结构的情况下实现上述目标。</span><span class="sxs-lookup"><span data-stu-id="3acdd-135">This solution enables an IT department to achieve the above with little to no infrastructure to manage, with a process that's easy and simple.</span></span> <span data-ttu-id="3acdd-136">从用户的角度来看，只需几个简单操作便可以使其设备准备就绪，以供使用。</span><span class="sxs-lookup"><span data-stu-id="3acdd-136">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> <span data-ttu-id="3acdd-137">从 IT 专业人员的角度来看，最终用户所需的交互将只有连接到网络并验证其凭据。</span><span class="sxs-lookup"><span data-stu-id="3acdd-137">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="3acdd-138">有关详细信息，请参阅此 [Windows Autopilot 概述](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="3acdd-138">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="3acdd-139">用于终结点管理的管理员技术资源</span><span class="sxs-lookup"><span data-stu-id="3acdd-139">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="3acdd-140">注册托管设备以实现安全，利用未托管设备的应用设置，并使用设备和应用策略</span><span class="sxs-lookup"><span data-stu-id="3acdd-140">Enroll managed devices for security, leverage app settings for unmanaged devices, and use device and app policies</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [<span data-ttu-id="3acdd-141">如何注册用于移动设备管理 (MDM) 的不同类型的设备</span><span class="sxs-lookup"><span data-stu-id="3acdd-141">How to enroll different types of devices for mobile device management (MDM)</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="3acdd-142">如何向最终用户讲解 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3acdd-142">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a><span data-ttu-id="3acdd-143">步骤 3 的结果</span><span class="sxs-lookup"><span data-stu-id="3acdd-143">Results of Step 3</span></span>

<span data-ttu-id="3acdd-144">你正在使用 Endpoint Manager 功能套件来管理移动设备、台式计算机、虚拟机、嵌入式设备和服务器。</span><span class="sxs-lookup"><span data-stu-id="3acdd-144">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="3acdd-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3acdd-145">Next step</span></span>

<span data-ttu-id="3acdd-146">继续执行[步骤 4](empower-people-to-work-remotely-teams-productivity-apps.md)，提供对本地应用和服务的远程访问权限。</span><span class="sxs-lookup"><span data-stu-id="3acdd-146">Continue with [Step 4](empower-people-to-work-remotely-teams-productivity-apps.md) to provide remote access to on-premises apps and services.</span></span>
