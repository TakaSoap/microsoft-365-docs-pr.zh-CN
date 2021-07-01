---
title: 步骤 2：提供对本地应用和服务的远程访问权限
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 确保远程工作者可以访问本地资源，同时优化对 Microsoft 365 云服务的访问权限。
ms.openlocfilehash: bc446cf26ec99d3e9f81564b5474777c674603bc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229427"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="800a8-p102">步骤 2：提供对本地应用和服务的远程访问权限</span><span class="sxs-lookup"><span data-stu-id="800a8-p102">Step 2. Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="800a8-p103">如果你的组织使用远程访问 VPN 解决方案权限（通常通过网络边缘上的 VPN 服务器以及在用户的设备上安装的 VPN 客户端），你的用户可以使用远程访问 VPN 连接来访问本地应用和服务器。但是，你可能需要优化与 Microsoft 365 基于云的服务的通信。</span><span class="sxs-lookup"><span data-stu-id="800a8-p103">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers. But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="800a8-108">如果你的用户未使用 VPN 解决方案，你可以使用 Azure Active Directory (Azure AD) 应用程序代理和 Azure 点到站点 (P2S) VPN 来提供访问权限，具体取决于你的所有应用是否均基于 Web。</span><span class="sxs-lookup"><span data-stu-id="800a8-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="800a8-109">下面是用于远程访问的主要配置：</span><span class="sxs-lookup"><span data-stu-id="800a8-109">Here are the primary configurations for remote access:</span></span>

- <span data-ttu-id="800a8-110">你已在使用远程访问 VPN 解决方案。</span><span class="sxs-lookup"><span data-stu-id="800a8-110">You are already using a remote access VPN solution.</span></span>
- <span data-ttu-id="800a8-111">你没有使用远程访问 VPN 解决方案，而是希望远程工作者使用其自己的个人计算机。</span><span class="sxs-lookup"><span data-stu-id="800a8-111">You are not using a remote access VPN solution and you want your remote workers to use their personal computers.</span></span>
- <span data-ttu-id="800a8-112">你使用的不是远程访问 VPN 解决方案，你有混合标识，只需远程访问基于 Web 的本地应用。</span><span class="sxs-lookup"><span data-stu-id="800a8-112">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
- <span data-ttu-id="800a8-113">你使用的不是远程访问 VPN 解决方案，并且你需要访问本地应用，其中一些应用并非基于 Web。</span><span class="sxs-lookup"><span data-stu-id="800a8-113">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="800a8-114">请参阅此流程图，了解本文中讨论的远程访问配置选项。</span><span class="sxs-lookup"><span data-stu-id="800a8-114">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![远程访问配置流程图](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="800a8-116">借助远程访问连接，还可以使用[远程桌面](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop)将用户连接到本地电脑。</span><span class="sxs-lookup"><span data-stu-id="800a8-116">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="800a8-117">例如，远程工作者可使用远程桌面从其 Windows、iOS 或 Android 设备连接到其办公室的电脑。</span><span class="sxs-lookup"><span data-stu-id="800a8-117">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS, or Android device.</span></span> <span data-ttu-id="800a8-118">远程连接后，他们可以像坐在电脑前一样使用它。</span><span class="sxs-lookup"><span data-stu-id="800a8-118">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="800a8-119">优化 Microsoft 365 云服务远程访问 VPN 客户端的性能</span><span class="sxs-lookup"><span data-stu-id="800a8-119">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="800a8-120">如果远程工作者正在使用传统的 VPN 客户端来获取对组织网络的远程访问权限，请验证该 VPN 客户端是否支持拆分隧道。</span><span class="sxs-lookup"><span data-stu-id="800a8-120">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="800a8-121">如果没有拆分隧道，所有远程工作通信都将通过 VPN 连接发送。在这种情况下，必须将其转发到组织的边缘设备、进行处理，然后在 Internet 上发送。</span><span class="sxs-lookup"><span data-stu-id="800a8-121">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![来自无隧道的 VPN 客户端的网络流量](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="800a8-p105">Microsoft 365 通信必须通过你的组织获取间接路由，该路由可以转发到远离 VPN 客户端物理位置的 Microsoft 网络入口点。此间接路径会增加网络流量的延迟，并降低整体性能。</span><span class="sxs-lookup"><span data-stu-id="800a8-p105">Microsoft 365 traffic must take an indirect route through your organization, which could be forwarded to a Microsoft network entry point far away from the VPN client’s physical location. This indirect path adds latency to the network traffic and decreases overall performance.</span></span>

<span data-ttu-id="800a8-125">借助拆分隧道，你可以将 VPN 客户端配置为排除通过 VPN 连接发送到组织网络的特定类型的通信。</span><span class="sxs-lookup"><span data-stu-id="800a8-125">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="800a8-126">要优化 Microsoft 365 云资源的访问权限，请将拆分隧道 VPN 客户端配置为排除通过 VPN 连接的流向 **优化** 类别 Microsoft 365 终结点的流量。</span><span class="sxs-lookup"><span data-stu-id="800a8-126">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="800a8-127">有关详细信息，请参阅 [Office 365 终结点类别](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)。</span><span class="sxs-lookup"><span data-stu-id="800a8-127">For more information, see [Office 365 endpoint categories](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="800a8-128">请查看[此列表](../enterprise/urls-and-ip-address-ranges.md)，了解如何优化类别终结点。</span><span class="sxs-lookup"><span data-stu-id="800a8-128">See [this list](../enterprise/urls-and-ip-address-ranges.md) of Optimize category endpoints.</span></span>

<span data-ttu-id="800a8-129">下面是生成的流量流，其中流入 Microsoft 365 云应用的大多数流量都绕过 VPN 连接。</span><span class="sxs-lookup"><span data-stu-id="800a8-129">Here is the resulting traffic flow, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![来自有隧道的 VPN 客户端的网络流量](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="800a8-131">这允许 VPN 客户端直接通过 Internet 发送和接收重要的 Microsoft 365 云服务流量并发送到 Microsoft 网络最近的入口点。</span><span class="sxs-lookup"><span data-stu-id="800a8-131">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="800a8-132">有关更多信息和指导，请参阅[使用 VPN 拆分隧道为远程用户优化 Office 365 连接](../enterprise/microsoft-365-vpn-split-tunnel.md)。</span><span class="sxs-lookup"><span data-stu-id="800a8-132">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="800a8-133">在所有应用均为 Web 应用且你具有混合标识的情况下部署远程访问</span><span class="sxs-lookup"><span data-stu-id="800a8-133">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="800a8-p107">如果远程工作者没有使用传统的 VPN 客户端，而且你的本地用户帐户和组与 Azure AD 同步，则可以使用 Azure AD 应用程序代理为本地服务器上托管的基于 Web 的应用程序提供安全的远程访问。基于 Web 的应用程序包括 SharePoint Server 网站、Outlook Web 访问服务器或任何其他基于 Web 的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="800a8-p107">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on on-premises servers. Web-based applications include SharePoint Server sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span>

<span data-ttu-id="800a8-136">下面是 Azure AD 应用程序代理的组件。</span><span class="sxs-lookup"><span data-stu-id="800a8-136">Here are the components of Azure AD Application Proxy.</span></span>

![Azure AD 应用程序代理的组件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="800a8-138">有关详细信息，请参阅此 [Azure AD 应用程序代理概述](/azure/active-directory/manage-apps/application-proxy)。</span><span class="sxs-lookup"><span data-stu-id="800a8-138">For more information, see this [overview of Azure AD Application Proxy](/azure/active-directory/manage-apps/application-proxy).</span></span>

> [!NOTE]
> <span data-ttu-id="800a8-139">Microsoft 365 订阅中不包含 Azure AD 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="800a8-139">Azure AD Application Proxy is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="800a8-140">你必须使用单独的 Azure 订阅来进行付费。</span><span class="sxs-lookup"><span data-stu-id="800a8-140">You must pay for usage with a separate Azure subscription.</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="800a8-141">在并非所有应用均为 Web 应用的情况下部署远程访问</span><span class="sxs-lookup"><span data-stu-id="800a8-141">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="800a8-142">如果远程工作者没有使用传统的 VPN 客户端，而且你有应用未基于 Web，那么你可使用 Azure 点到站点 (P2S) VPN。</span><span class="sxs-lookup"><span data-stu-id="800a8-142">If your remote workers are not using a traditional VPN client and you have apps that are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="800a8-143">P2S VPN 连接通过 Azure 虚拟网络创建从远程工作者的设备到组织网络的安全连接。</span><span class="sxs-lookup"><span data-stu-id="800a8-143">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span>

![Azure P2S VPN 的组件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="800a8-145">有关详细信息，请参阅此 [P2S VPN 概述](/azure/vpn-gateway/point-to-site-about)。</span><span class="sxs-lookup"><span data-stu-id="800a8-145">For more information, see this [overview of P2S VPN](/azure/vpn-gateway/point-to-site-about).</span></span>

> [!NOTE]
> <span data-ttu-id="800a8-146">Microsoft 365 订阅中不包含 Azure P2S VPN。</span><span class="sxs-lookup"><span data-stu-id="800a8-146">Azure P2S VPN is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="800a8-147">你必须使用单独的 Azure 订阅来进行付费。</span><span class="sxs-lookup"><span data-stu-id="800a8-147">You must pay for usage with a separate Azure subscription.</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="800a8-148">部署 Windows 虚拟桌面，以便为使用个人设备的远程工作者提供远程访问权限</span><span class="sxs-lookup"><span data-stu-id="800a8-148">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span>

<span data-ttu-id="800a8-p110">要为仅可使用自己的个人和非托管设备的远程工作者提供支持，请使用 Azure 中的 Windows 虚拟桌面创建并分配虚拟桌面，以便用户在家中使用。虚拟电脑可以像连接到组织网络的电脑一样操作。</span><span class="sxs-lookup"><span data-stu-id="800a8-p110">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home. Virtualized PCs can act just like PCs connected to your organization network.</span></span>

![Azure Windows 虚拟桌面的组件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

<span data-ttu-id="800a8-152">有关详细信息，请参阅此 [Windows 虚拟桌面概述](/azure/virtual-desktop/overview)。</span><span class="sxs-lookup"><span data-stu-id="800a8-152">For more information, see this [overview of Windows Virtual Desktop](/azure/virtual-desktop/overview).</span></span>

> [!NOTE]
><span data-ttu-id="800a8-153">Microsoft 365 订阅中不包含 Windows 虚拟桌面。</span><span class="sxs-lookup"><span data-stu-id="800a8-153">Windows Virtual Desktop is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="800a8-154">你必须使用单独的 Azure 订阅来进行付费。</span><span class="sxs-lookup"><span data-stu-id="800a8-154">You must pay for usage with a separate Azure subscription.</span></span>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a><span data-ttu-id="800a8-155">使用远程桌面服务网关保护你的远程桌面服务连接</span><span class="sxs-lookup"><span data-stu-id="800a8-155">Protect your Remote Desktop Services connections with the Remote Desktop Services Gateway</span></span>

<span data-ttu-id="800a8-156">如果使用远程桌面服务 (RDS) 来允许员工连接到本地网络上基于 Windows 的计算机，则应在边缘网络中使用 Microsoft 远程桌面服务网关。</span><span class="sxs-lookup"><span data-stu-id="800a8-156">If you are using Remote Desktop Services (RDS) to allow employees to connect into Windows-based computers on your on-premises network, you should use a Microsoft Remote Desktop Services gateway in your edge network.</span></span> <span data-ttu-id="800a8-157">网关使用传输层安全性 （TLS） 加密通信流，并阻止托管 RDS 本地计算机直接向 Internet 公开。</span><span class="sxs-lookup"><span data-stu-id="800a8-157">The gateway uses Transport Layer Security (TLS) to encrypt traffic and prevents the on-premises computer hosting RDS from being directly exposed to the Internet.</span></span>

![带远程桌面服务网关的远程桌面服务连接](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

<span data-ttu-id="800a8-159">请参阅[这篇文章](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/)，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="800a8-159">See [this article](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) for more information.</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="800a8-160">用于远程访问的管理员技术资源</span><span class="sxs-lookup"><span data-stu-id="800a8-160">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="800a8-161">如何快速优化远程办公人员的 Office 365 流量并降低你的基础结构上的负载</span><span class="sxs-lookup"><span data-stu-id="800a8-161">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="800a8-162">使用 VPN 拆分隧道为远程用户优化 Office 365 连接</span><span class="sxs-lookup"><span data-stu-id="800a8-162">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="results-of-step-2"></a><span data-ttu-id="800a8-163">步骤 2 的结果</span><span class="sxs-lookup"><span data-stu-id="800a8-163">Results of Step 2</span></span>

<span data-ttu-id="800a8-164">为远程工作者部署远程访问解决方案后：</span><span class="sxs-lookup"><span data-stu-id="800a8-164">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="800a8-165">远程访问配置</span><span class="sxs-lookup"><span data-stu-id="800a8-165">Remote access configuration</span></span> | <span data-ttu-id="800a8-166">结果</span><span class="sxs-lookup"><span data-stu-id="800a8-166">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="800a8-167">远程访问 VPN 解决方案已到位</span><span class="sxs-lookup"><span data-stu-id="800a8-167">A remote access VPN solution is in place</span></span> | <span data-ttu-id="800a8-168">已经针对拆分隧道和 Microsoft 365 终结点的“优化”类别配置远程访问 VPN 客户端。</span><span class="sxs-lookup"><span data-stu-id="800a8-168">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="800a8-169">没有远程访问 VPN 解决方案，并且只需远程访问基于 Web 的本地应用</span><span class="sxs-lookup"><span data-stu-id="800a8-169">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="800a8-170">已配置 Azure 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="800a8-170">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="800a8-171">没有远程访问 VPN 解决方案，并且需要访问本地应用，其中一些应用并非基于 Web</span><span class="sxs-lookup"><span data-stu-id="800a8-171">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="800a8-172">已配置 Azure P2S VPN。</span><span class="sxs-lookup"><span data-stu-id="800a8-172">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="800a8-173">远程工作人员正在家中使用自己的个人设备</span><span class="sxs-lookup"><span data-stu-id="800a8-173">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="800a8-174">已配置 Windows 虚拟桌面。</span><span class="sxs-lookup"><span data-stu-id="800a8-174">You have configured Windows Virtual Desktop.</span></span> |
| <span data-ttu-id="800a8-175">远程工作者将使用到本地系统的 RDS 连接</span><span class="sxs-lookup"><span data-stu-id="800a8-175">Remote workers are using RDS connections to on-premises systems</span></span> | <span data-ttu-id="800a8-176">已在边缘网络中部署远程桌面服务网关。</span><span class="sxs-lookup"><span data-stu-id="800a8-176">You have deployed a Remote Desktop Services gateway in your edge network.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="800a8-177">后续步骤</span><span class="sxs-lookup"><span data-stu-id="800a8-177">Next step</span></span>

<span data-ttu-id="800a8-178">[![步骤 3：部署 Microsoft 365 安全和合规性服务](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="800a8-178">[![Step 3: Deploy Microsoft 365 security and compliance services](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span></span>

<span data-ttu-id="800a8-179">继续[步骤 3](empower-people-to-work-remotely-security-compliance.md)，部署 Microsoft 365 安全和合规性服务，以保护你的应用、数据和设备。</span><span class="sxs-lookup"><span data-stu-id="800a8-179">Continue with [Step 3](empower-people-to-work-remotely-security-compliance.md) to deploy Microsoft 365 security and compliance services to protect your apps, data, and devices.</span></span>