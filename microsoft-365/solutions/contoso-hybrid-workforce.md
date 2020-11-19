---
title: Contoso 的 COVID-19 响应和对混合劳动力的支持
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
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso Corporation 如何响应 COVID pandemic，并为混合劳动力设计其软件安装和更新基础结构。
ms.openlocfilehash: a29ffee1413f60da30ad34aa62ca465ca16e0430
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357944"
---
# <a name="contosos-covid-19-response-and-support-for-a-hybrid-workforce"></a><span data-ttu-id="620cd-103">Contoso 的 COVID-19 响应和对混合劳动力的支持</span><span class="sxs-lookup"><span data-stu-id="620cd-103">Contoso's COVID-19 response and support for a hybrid workforce</span></span>

<span data-ttu-id="620cd-104">Contoso 始终支持通过巴黎总部的中央 VPN 服务器访问本地资源的远程工作人员。</span><span class="sxs-lookup"><span data-stu-id="620cd-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="620cd-105">Contoso 已将所有远程工作人员颁发为托管便携式计算机。</span><span class="sxs-lookup"><span data-stu-id="620cd-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="620cd-106">内部部署工作人员混合了台式计算机和便携式计算机。</span><span class="sxs-lookup"><span data-stu-id="620cd-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="620cd-107">Contoso 对 COVID 的响应-19</span><span class="sxs-lookup"><span data-stu-id="620cd-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="620cd-108">使用 COVID-19 pandemic 的 onset，您就会突然拥有远程工作人员的所有重要工作人员。</span><span class="sxs-lookup"><span data-stu-id="620cd-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="620cd-109">Contoso 通过将其员工的工作方式转移到家庭中，并通过远程访问本地资源并使用 Microsoft 365 云服务进行联机来响应其主要活动。</span><span class="sxs-lookup"><span data-stu-id="620cd-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="620cd-110">Contoso 在巴黎总部办事处拥有远程访问 VPN 服务器，以支持其已有的远程员工的25%，但快速移动以扩大 it 的远程访问能力，以支持其员工的90%。</span><span class="sxs-lookup"><span data-stu-id="620cd-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="620cd-111">Contoso 在每个卫星办公室中部署了远程访问 VPN 服务器，以便远程工作人员可以使用地区组织关闭入口点访问 Contoso intranet。</span><span class="sxs-lookup"><span data-stu-id="620cd-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="620cd-112">Contoso 还更新了用于拆分隧道的便携式电脑、平板电脑和智能手机上安装的 VPN 客户端的配置，以便优化 Office 365 终结点集的流量绕过 VPN 连接，并通过 internet 直接发送。</span><span class="sxs-lookup"><span data-stu-id="620cd-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="620cd-113">有关详细信息，请参阅 [使用 VPN 拆分隧道为远程用户优化 Office 365 连接](../enterprise/microsoft-365-vpn-split-tunnel.md)。</span><span class="sxs-lookup"><span data-stu-id="620cd-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="620cd-114">下面是安装在巴黎总部和每个卫星办公室中的 VPN 设备生成的配置。</span><span class="sxs-lookup"><span data-stu-id="620cd-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Contoso 的 VPN 基础结构](../media/contoso-hybrid-workforce/contoso-vpn-infrastructure.png)

<span data-ttu-id="620cd-116">具有已安装的 VPN 客户端的远程工作人员使用 DNS 查找地区组织最近的 office，并连接到此处安装的 VPN 设备。</span><span class="sxs-lookup"><span data-stu-id="620cd-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="620cd-117">通过拆分隧道，到 Microsoft 365 的流量优化终结点将直接发送到最近的地区组织 Microsoft 365 网络位置。</span><span class="sxs-lookup"><span data-stu-id="620cd-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="620cd-118">所有其他流量通过 VPN 连接发送到 VPN 设备。</span><span class="sxs-lookup"><span data-stu-id="620cd-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-a-dynamic-hybrid-workforce"></a><span data-ttu-id="620cd-119">Contoso 对动态混合劳动力的支持</span><span class="sxs-lookup"><span data-stu-id="620cd-119">Contoso’s support for a dynamic hybrid workforce</span></span>

<span data-ttu-id="620cd-120">在区域 lockdowns 期间进行的大多数远程工作者支持的初始更改之后，Contoso 进行了基础结构更改，以支持工作人员可在其中执行以下操作的混合劳动力：</span><span class="sxs-lookup"><span data-stu-id="620cd-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support a hybrid workforce in which a worker could be:</span></span>

- <span data-ttu-id="620cd-121">始终远程。</span><span class="sxs-lookup"><span data-stu-id="620cd-121">Always remote.</span></span>
- <span data-ttu-id="620cd-122">始终为本地。</span><span class="sxs-lookup"><span data-stu-id="620cd-122">Always on-premises.</span></span>
- <span data-ttu-id="620cd-123">远程和本地的组合。</span><span class="sxs-lookup"><span data-stu-id="620cd-123">A combination of remote and on-premises.</span></span>

<span data-ttu-id="620cd-124">Microsoft 365 标识、安全性和合规性功能是为实现零信任而设计的，无论用户及其设备的位置如何，都能正常工作。</span><span class="sxs-lookup"><span data-stu-id="620cd-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="620cd-125">有关详细信息，请参阅 [零信任](https://www.microsoft.com/security/business/zero-trust)。</span><span class="sxs-lookup"><span data-stu-id="620cd-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="620cd-126">但是，管理软件的新安装和更新取决于设备的位置，因为要安装的软件可能来自内部部署源或 internet 源。</span><span class="sxs-lookup"><span data-stu-id="620cd-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="620cd-127">Contoso IT 架构师根据设备的位置（而不是工作人员）设计他们的新安装和更新基础结构。</span><span class="sxs-lookup"><span data-stu-id="620cd-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="620cd-128">它们指定了两种类型的设备：专用本地和漫游。</span><span class="sxs-lookup"><span data-stu-id="620cd-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="620cd-129">专用本地</span><span class="sxs-lookup"><span data-stu-id="620cd-129">Dedicated on-premises</span></span>

<span data-ttu-id="620cd-130">专用的本地设备是指从不离开 Contoso intranet 且未安装 VPN 客户端的台式机或服务器计算机。</span><span class="sxs-lookup"><span data-stu-id="620cd-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="620cd-131">这些本地设备继续使用 Microsoft 终结点配置管理器及其分发点来安装和更新 Windows 10、Microsoft 365 Apps for enterprise 和 Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="620cd-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="620cd-132">漫游</span><span class="sxs-lookup"><span data-stu-id="620cd-132">Roaming</span></span>

<span data-ttu-id="620cd-133">漫游设备可以离开 Contoso intranet，并包括发布到许多 office 工作人员和所有远程工作人员和其他组织拥有的设备（例如智能手机和平板电脑）安装了 Contoso VPN 客户端的便携式计算机。</span><span class="sxs-lookup"><span data-stu-id="620cd-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="620cd-134">由于可在任意给定时间将这些设备连接到 Internet，因此他们使用 Intune 或其他基于云的服务来安装和更新 Windows 10、Microsoft 365 Apps for enterprise 和 Edge。</span><span class="sxs-lookup"><span data-stu-id="620cd-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="620cd-135">它们不使用现有的本地配置管理器分发点。</span><span class="sxs-lookup"><span data-stu-id="620cd-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="620cd-136">这意味着漫游设备的某些安装和更新将通过 internet 进行，同时在本地进行，并连接到 intranet。</span><span class="sxs-lookup"><span data-stu-id="620cd-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="620cd-137">但 Contoso IT 架构师认为，配置的简单性比 internet 的 intranet 带宽优化更重要，尤其是当大多数远程工作人员很少连接到 intranet 时。</span><span class="sxs-lookup"><span data-stu-id="620cd-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="620cd-138">下面是生成的基础结构。</span><span class="sxs-lookup"><span data-stu-id="620cd-138">Here is the resulting infrastructure.</span></span>

![Contoso 的安装和更新基础结构](../media/contoso-hybrid-workforce/contoso-updates-infrastructure.png)

<span data-ttu-id="620cd-140">通过将设备的计算机帐户设为以下组之一的成员来确定安装和更新行为：</span><span class="sxs-lookup"><span data-stu-id="620cd-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="620cd-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="620cd-141">OnPremDevices</span></span>

  <span data-ttu-id="620cd-142">设备上的 Configuration Manager 客户端使用分发点进行安装和更新。</span><span class="sxs-lookup"><span data-stu-id="620cd-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="620cd-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="620cd-143">RoamingDevices</span></span>

  <span data-ttu-id="620cd-144">Intune 和设备上的其他设置指定使用 Microsoft 365 网络进行安装和更新。</span><span class="sxs-lookup"><span data-stu-id="620cd-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="620cd-145">新的载入过程</span><span class="sxs-lookup"><span data-stu-id="620cd-145">New onboarding process</span></span>

<span data-ttu-id="620cd-146">对于向新工作人员或在数据中心中的新服务器发出的新专用本地设备，当工作人员登录时，基于 OnPremDevices 组中设备的成员身份的 Configuration Manager 客户端将下载并安装 Windows 10、Microsoft 365 应用程序的最新更新和本地 Configuration Manager 分发点的边缘。</span><span class="sxs-lookup"><span data-stu-id="620cd-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="620cd-147">完成后，专用的本地设备即可供使用，并使用这些分发点进行持续更新。</span><span class="sxs-lookup"><span data-stu-id="620cd-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="620cd-148">对于颁发给新工作人员的新远程设备，当工作人员登录时，设备将基于其在 RoamingDevices 组中的成员身份，联系 Intune 云服务和其他服务并下载并安装最新的 Windows 10、Microsoft 365 Apps for enterprise 和 Edge 的更新。</span><span class="sxs-lookup"><span data-stu-id="620cd-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="620cd-149">完成后，远程设备即可供使用，并使用已安装的 VPN 客户端访问本地资源和 Microsoft 365 网络以进行持续更新。</span><span class="sxs-lookup"><span data-stu-id="620cd-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="620cd-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="620cd-150">Next step</span></span>

<span data-ttu-id="620cd-151">[为你的组织中的远程工作人员准备工作](empower-people-to-work-remotely.md) 。</span><span class="sxs-lookup"><span data-stu-id="620cd-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>
