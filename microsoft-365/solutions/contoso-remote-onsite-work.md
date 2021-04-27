---
title: Contoso 的 COVID-19 响应和支持远程和现场工作
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso Corporation 如何响应 COVID-19 病毒，并设计其软件安装和更新基础结构，用于远程和现场工作。
ms.openlocfilehash: 0bded43f03dd529ffdf463818a93af70e10eed89
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028976"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a><span data-ttu-id="bfde0-103">Contoso 的 COVID-19 响应和支持远程和现场工作</span><span class="sxs-lookup"><span data-stu-id="bfde0-103">Contoso's COVID-19 response and support for remote and onsite work</span></span>

<span data-ttu-id="bfde0-104">Contoso 始终支持远程工作者，这些工作者通过巴黎总部的中央 VPN 服务器访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="bfde0-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="bfde0-105">Contoso 已颁发给所有远程工作者托管的笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="bfde0-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="bfde0-106">本地工作人员混合使用台式计算机和笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="bfde0-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="bfde0-107">Contoso 对 COVID-19 的响应</span><span class="sxs-lookup"><span data-stu-id="bfde0-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="bfde0-108">随着 COVID-19 病毒的爆发，突然，只有基本工作者都是远程工作者。</span><span class="sxs-lookup"><span data-stu-id="bfde0-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="bfde0-109">Contoso 通过远程访问本地资源和使用 Microsoft 365 云服务在线，将员工从家转移到工作并开展其主要活动来做出响应。</span><span class="sxs-lookup"><span data-stu-id="bfde0-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="bfde0-110">Contoso 在巴黎总部办公室拥有远程访问 VPN 服务器，以支持其 25% 的已远程工作人员，但迅速移动以扩展其远程访问容量以支持 90% 的员工。</span><span class="sxs-lookup"><span data-stu-id="bfde0-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="bfde0-111">Contoso 在每个附属办事处部署了远程访问 VPN 服务器，以便远程工作人员使用区域关闭入口点来访问 Contoso Intranet。</span><span class="sxs-lookup"><span data-stu-id="bfde0-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="bfde0-112">Contoso 还更新了安装在笔记本电脑、平板电脑和智能手机上的 VPN 客户端的配置，以便拆分隧道，以便 Office 365 终结点的 Optimize 集的流量绕过 VPN 连接并直接通过 Internet 发送。</span><span class="sxs-lookup"><span data-stu-id="bfde0-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="bfde0-113">有关详细信息，请参阅使用 VPN 拆分隧道为远程用户 [优化 Office 365 连接](../enterprise/microsoft-365-vpn-split-tunnel.md)。</span><span class="sxs-lookup"><span data-stu-id="bfde0-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="bfde0-114">下面是在巴黎总部和每个附属办事处安装了 VPN 设备的配置结果。</span><span class="sxs-lookup"><span data-stu-id="bfde0-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Contoso 的 VPN 基础结构](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

<span data-ttu-id="bfde0-116">安装了 VPN 客户端的远程工作者使用 DNS 查找区域最近的办公室并连接到安装在那里的 VPN 设备。</span><span class="sxs-lookup"><span data-stu-id="bfde0-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="bfde0-117">使用拆分隧道，到 Microsoft 365 优化终结点的流量将直接发送到区域最近的 Microsoft 365 网络位置。</span><span class="sxs-lookup"><span data-stu-id="bfde0-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="bfde0-118">所有其他流量通过 VPN 连接发送到 VPN 设备。</span><span class="sxs-lookup"><span data-stu-id="bfde0-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-remote-and-onsite-work"></a><span data-ttu-id="bfde0-119">Contoso 对远程和现场工作的支持</span><span class="sxs-lookup"><span data-stu-id="bfde0-119">Contoso’s support for remote and onsite work</span></span>

<span data-ttu-id="bfde0-120">在区域锁定期间进行初始更改以支持大多数远程工作者后，Contoso 进行了基础结构更改以支持工作者可能从事的远程和现场工作：</span><span class="sxs-lookup"><span data-stu-id="bfde0-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support remote and onsite work in which a worker could be:</span></span>

- <span data-ttu-id="bfde0-121">始终远程。</span><span class="sxs-lookup"><span data-stu-id="bfde0-121">Always remote.</span></span>
- <span data-ttu-id="bfde0-122">始终现场。</span><span class="sxs-lookup"><span data-stu-id="bfde0-122">Always onsite.</span></span>
- <span data-ttu-id="bfde0-123">现场和远程的组合。</span><span class="sxs-lookup"><span data-stu-id="bfde0-123">A combination of onsite and remote.</span></span>

<span data-ttu-id="bfde0-124">Microsoft 365 标识、安全性和合规性功能专为零信任设计，无论用户及其设备的位置如何，这些功能均可运行。</span><span class="sxs-lookup"><span data-stu-id="bfde0-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="bfde0-125">有关详细信息，请参阅零 [信任](https://www.microsoft.com/security/business/zero-trust)。</span><span class="sxs-lookup"><span data-stu-id="bfde0-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="bfde0-126">但是，管理软件的新安装和更新取决于设备的位置，因为要安装的软件可能来自本地或 Internet 源。</span><span class="sxs-lookup"><span data-stu-id="bfde0-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="bfde0-127">Contoso IT 架构师根据设备的位置（而不是工作者）设计了新的安装和更新基础结构。</span><span class="sxs-lookup"><span data-stu-id="bfde0-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="bfde0-128">他们指定了两种类型的设备：专用本地和漫游。</span><span class="sxs-lookup"><span data-stu-id="bfde0-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="bfde0-129">专用本地</span><span class="sxs-lookup"><span data-stu-id="bfde0-129">Dedicated on-premises</span></span>

<span data-ttu-id="bfde0-130">专用本地设备是永远不会离开 Contoso Intranet 且未安装 VPN 客户端的桌面或服务器计算机。</span><span class="sxs-lookup"><span data-stu-id="bfde0-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="bfde0-131">这些本地设备继续使用 Microsoft Endpoint Configuration Manager 及其分发点来安装和更新 Windows 10、Microsoft 365 企业应用版和 Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="bfde0-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="bfde0-132">漫游</span><span class="sxs-lookup"><span data-stu-id="bfde0-132">Roaming</span></span>

<span data-ttu-id="bfde0-133">漫游设备可以离开 Contoso Intranet，并包括颁发给许多办公室工作人员、所有远程工作人员以及其他组织拥有的设备（如安装了 Contoso VPN 客户端的智能手机和平板电脑）的笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="bfde0-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="bfde0-134">由于这些设备可以在任何给定时间连接到 Internet，因此它们使用 Intune 或其他基于云的服务来安装和更新 Windows 10、Microsoft 365 企业应用版和 Edge。</span><span class="sxs-lookup"><span data-stu-id="bfde0-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="bfde0-135">它们不使用现有的本地 Configuration Manager 分发点。</span><span class="sxs-lookup"><span data-stu-id="bfde0-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="bfde0-136">这意味着漫游设备的一些安装和更新将在漫游设备位于本地并连接到 Intranet 时通过 Internet 完成。</span><span class="sxs-lookup"><span data-stu-id="bfde0-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="bfde0-137">但 Contoso IT 架构师认为，配置简单性比优化 Intranet 带宽到 Internet 更重要，尤其是当大多数远程工作人员很少连接到 Intranet 时。</span><span class="sxs-lookup"><span data-stu-id="bfde0-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="bfde0-138">下面是生成的基础结构。</span><span class="sxs-lookup"><span data-stu-id="bfde0-138">Here is the resulting infrastructure.</span></span>

![Contoso 的安装和更新基础结构](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

<span data-ttu-id="bfde0-140">安装和更新行为由使设备的计算机帐户成为以下组之一的成员来确定：</span><span class="sxs-lookup"><span data-stu-id="bfde0-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="bfde0-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="bfde0-141">OnPremDevices</span></span>

  <span data-ttu-id="bfde0-142">设备上 Configuration Manager 客户端使用分发点进行安装和更新。</span><span class="sxs-lookup"><span data-stu-id="bfde0-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="bfde0-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="bfde0-143">RoamingDevices</span></span>

  <span data-ttu-id="bfde0-144">Intune 和设备上的其他设置指定使用 Microsoft 365 网络进行安装和更新。</span><span class="sxs-lookup"><span data-stu-id="bfde0-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="bfde0-145">新的载入过程</span><span class="sxs-lookup"><span data-stu-id="bfde0-145">New onboarding process</span></span>

<span data-ttu-id="bfde0-146">对于颁发给新工作者或数据中心中新服务器的新的专用本地设备，当工作者登录时，基于设备在 OnPremDevices 组的成员身份的 Configuration Manager 客户端从本地 Configuration Manager 分发点下载并安装 Windows 10、Microsoft 365 企业应用版和 Edge 的最新更新。</span><span class="sxs-lookup"><span data-stu-id="bfde0-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="bfde0-147">完成后，专用本地设备即可供使用，并使用这些分发点进行持续更新。</span><span class="sxs-lookup"><span data-stu-id="bfde0-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="bfde0-148">对于颁发给新工作者的新远程设备，当工作者登录时，该设备会基于其 RoamingDevices 组的成员身份联系 Intune 云服务和其他服务，并下载并安装 Windows 10、Microsoft 365 企业应用版和 Edge 的最新更新。</span><span class="sxs-lookup"><span data-stu-id="bfde0-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="bfde0-149">完成后，远程设备即可供使用，并使用已安装的 VPN 客户端访问本地资源和 Microsoft 365 网络，以持续更新。</span><span class="sxs-lookup"><span data-stu-id="bfde0-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="bfde0-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bfde0-150">Next step</span></span>

<span data-ttu-id="bfde0-151">[为组织的远程](empower-people-to-work-remotely.md) 工作者提供能力。</span><span class="sxs-lookup"><span data-stu-id="bfde0-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>
