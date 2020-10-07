---
title: 步骤 2. 提供对本地应用和服务的远程访问权限。
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/27/2020
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
ms.openlocfilehash: 52a338822c28f6ae044f13f60664d66816d6ce5c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377243"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="084e4-104">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="084e4-104">Step 2.</span></span> <span data-ttu-id="084e4-105">提供对本地应用和服务的远程访问权限。</span><span class="sxs-lookup"><span data-stu-id="084e4-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="084e4-106">如果你的组织使用远程访问 VPN 解决方案（通常通过网络边缘上的 VPN 服务器以及在用户的设备上安装的 VPN 客户端），你的用户可以使用远程访问 VPN 连接来访问本地应用和服务器。</span><span class="sxs-lookup"><span data-stu-id="084e4-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="084e4-107">但是，你可能需要优化与 Microsoft 365 基于云的服务的通信。</span><span class="sxs-lookup"><span data-stu-id="084e4-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="084e4-108">如果你的用户未使用 VPN 解决方案，你可以使用 Azure Active Directory (Azure AD) 应用程序代理和 Azure 点到站点 (P2S) VPN 来提供访问权限，具体取决于你的所有应用是否均基于 Web。</span><span class="sxs-lookup"><span data-stu-id="084e4-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="084e4-109">有三种主要配置：</span><span class="sxs-lookup"><span data-stu-id="084e4-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="084e4-110">你已在使用远程访问 VPN 解决方案。</span><span class="sxs-lookup"><span data-stu-id="084e4-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="084e4-111">你使用的不是远程访问 VPN 解决方案，你有混合标识，只需远程访问基于 Web 的本地应用。</span><span class="sxs-lookup"><span data-stu-id="084e4-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="084e4-112">你使用的不是远程访问 VPN 解决方案，并且你需要访问本地应用，其中一些应用并非基于 Web。</span><span class="sxs-lookup"><span data-stu-id="084e4-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="084e4-113">请参阅此流程图，了解本文中讨论的远程访问配置选项。</span><span class="sxs-lookup"><span data-stu-id="084e4-113">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![远程访问配置流程图](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="084e4-115">借助远程访问连接，还可以使用[远程桌面](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop)将用户连接到本地电脑。</span><span class="sxs-lookup"><span data-stu-id="084e4-115">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="084e4-116">例如，远程工作者可使用远程桌面从其 Windows、iOS 或 Android 设备连接到其办公室的电脑。</span><span class="sxs-lookup"><span data-stu-id="084e4-116">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="084e4-117">远程连接后，他们可以像坐在电脑前一样使用它。</span><span class="sxs-lookup"><span data-stu-id="084e4-117">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="084e4-118">优化 Microsoft 365 云服务远程访问 VPN 客户端的性能</span><span class="sxs-lookup"><span data-stu-id="084e4-118">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="084e4-119">如果远程工作者正在使用传统的 VPN 客户端来获取对组织网络的远程访问权限，请验证该 VPN 客户端是否支持拆分隧道。</span><span class="sxs-lookup"><span data-stu-id="084e4-119">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="084e4-120">如果没有拆分隧道，所有远程工作通信都将通过 VPN 连接发送。在这种情况下，必须将其转发到组织的边缘设备、进行处理，然后在 Internet 上发送。</span><span class="sxs-lookup"><span data-stu-id="084e4-120">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![来自无隧道的 VPN 客户端的网络流量](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="084e4-122">Microsoft 365 通信必须通过你的组织获取间接路由，它可能是面向远离 VPN 客户端物理位置的 Microsoft 网络入口点的转发。</span><span class="sxs-lookup"><span data-stu-id="084e4-122">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="084e4-123">此间接路径会增加网络流量的延迟并降低整体性能。</span><span class="sxs-lookup"><span data-stu-id="084e4-123">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="084e4-124">借助拆分隧道，你可以将 VPN 客户端配置为排除通过 VPN 连接发送到组织网络的特定类型的通信。</span><span class="sxs-lookup"><span data-stu-id="084e4-124">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="084e4-125">要优化 Microsoft 365 云资源的访问权限，请将拆分隧道 VPN 客户端配置为排除通过 VPN 连接的流向**优化**类别 Microsoft 365 终结点的流量。</span><span class="sxs-lookup"><span data-stu-id="084e4-125">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="084e4-126">有关详细信息，请参阅 [Office 365 终结点类别](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories)。</span><span class="sxs-lookup"><span data-stu-id="084e4-126">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="084e4-127">请在[此处](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)查看优化类别终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="084e4-127">See the list of Optimize category endpoints [here](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

![来自有隧道的 VPN 客户端的网络流量](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="084e4-129">这允许 VPN 客户端直接通过 Internet 发送和接收重要的 Microsoft 365 云服务流量并发送到 Microsoft 网络最近的入口点。</span><span class="sxs-lookup"><span data-stu-id="084e4-129">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="084e4-130">有关更多信息和指导，请参阅[使用 VPN 拆分隧道为远程用户优化 Office 365 连接](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?)。</span><span class="sxs-lookup"><span data-stu-id="084e4-130">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="084e4-131">在所有应用均为 Web 应用且你具有混合标识的情况下部署远程访问</span><span class="sxs-lookup"><span data-stu-id="084e4-131">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="084e4-132">如果远程工作者使用的不是传统的 VPN 客户端，并且你的本地用户帐户和组与 Azure AD 同步，则可以使用 Azure AD 应用程序代理为 Intranet 服务器上托管的基于 Web 的应用程序实现安全的远程访问。</span><span class="sxs-lookup"><span data-stu-id="084e4-132">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="084e4-133">基于 Web 的应用程序包括 SharePoint 网站、Outlook Web Access 服务器或任何其他基于 Web 的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="084e4-133">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="084e4-134">下面是 Azure AD 应用程序代理的组件。</span><span class="sxs-lookup"><span data-stu-id="084e4-134">Here are the components of Azure AD Application Proxy.</span></span>

![Azure AD 应用程序代理的组件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="084e4-136">有关详细信息，请参阅此 [Azure AD 应用程序代理概述](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)和[有关使用 Azure AD 应用程序代理的第 3 部分视频](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)。</span><span class="sxs-lookup"><span data-stu-id="084e4-136">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) and the [Part 3 video on using Azure AD Application Proxy](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security).</span></span>

>[!Note]
><span data-ttu-id="084e4-137">Microsoft 365 订阅中不包含 Azure AD 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="084e4-137">Azure AD Application Proxy is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="084e4-138">你必须使用单独的 Azure 订阅来进行付费。</span><span class="sxs-lookup"><span data-stu-id="084e4-138">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="084e4-139">在并非所有应用均为 Web 应用的情况下部署远程访问</span><span class="sxs-lookup"><span data-stu-id="084e4-139">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="084e4-140">如果远程工作者使用的不是传统的 VPN 客户端，并且你的任何应用不是基于 Web，则可以使用 Azure 点到站点 (P2S) VPN。</span><span class="sxs-lookup"><span data-stu-id="084e4-140">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="084e4-141">P2S VPN 连接通过 Azure 虚拟网络创建从远程工作者的设备到组织网络的安全连接。</span><span class="sxs-lookup"><span data-stu-id="084e4-141">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Azure P2S VPN 的组件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="084e4-143">有关详细信息，请参阅此 [P2S VPN 概述](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about)。</span><span class="sxs-lookup"><span data-stu-id="084e4-143">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

>[!Note]
><span data-ttu-id="084e4-144">Microsoft 365 订阅中不包含 Azure P2S VPN。</span><span class="sxs-lookup"><span data-stu-id="084e4-144">Azure P2S VPN is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="084e4-145">你必须使用单独的 Azure 订阅来进行付费。</span><span class="sxs-lookup"><span data-stu-id="084e4-145">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="084e4-146">部署 Windows 虚拟桌面，以便为使用个人设备的远程工作者提供远程访问权限</span><span class="sxs-lookup"><span data-stu-id="084e4-146">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="084e4-147">要为仅可使用自己的个人和非托管设备的远程工作者提供支持，请使用 Azure 中的 Windows 虚拟桌面创建并分配虚拟桌面，以便用户在家中使用。</span><span class="sxs-lookup"><span data-stu-id="084e4-147">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span> <span data-ttu-id="084e4-148">虚拟电脑可以像连接到组织网络的电脑一样操作。</span><span class="sxs-lookup"><span data-stu-id="084e4-148">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

![Azure Windows 虚拟桌面的组件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

<span data-ttu-id="084e4-150">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="084e4-150">For more information, see:</span></span> 

- <span data-ttu-id="084e4-151">[Windows 虚拟桌面概述](https://docs.microsoft.com/azure/virtual-desktop/overview)。</span><span class="sxs-lookup"><span data-stu-id="084e4-151">[This overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>
- <span data-ttu-id="084e4-152">[有关使用 Windows 虚拟桌面支持远程工作者的第 2 部分视频](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity)。</span><span class="sxs-lookup"><span data-stu-id="084e4-152">[The Part 2 video on using Windows Virtual Desktop for remote workers](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity).</span></span>

>[!Note]
><span data-ttu-id="084e4-153">Microsoft 365 订阅中不包含 Windows 虚拟桌面。</span><span class="sxs-lookup"><span data-stu-id="084e4-153">Windows Virtual Desktop is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="084e4-154">你必须使用单独的 Azure 订阅来进行付费。</span><span class="sxs-lookup"><span data-stu-id="084e4-154">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a><span data-ttu-id="084e4-155">使用远程桌面服务网关保护你的远程桌面服务连接</span><span class="sxs-lookup"><span data-stu-id="084e4-155">Protect your Remote Desktop Services connections with the Remote Desktop Services Gateway</span></span>

<span data-ttu-id="084e4-156">如果使用远程桌面服务 (RDS) 来允许员工连接到本地网络上基于 Windows 的计算机，则应在边缘网络中使用 Microsoft 远程桌面服务网关。</span><span class="sxs-lookup"><span data-stu-id="084e4-156">If you are using Remote Desktop Services (RDS) to allow employees to connect into Windows-based computers on your on-premises network, you should use a Microsoft Remote Desktop Services gateway in your edge network.</span></span> <span data-ttu-id="084e4-157">该网关使用安全套接字层 (SSL) 对通信进行加密，并防止托管 RDS 的系统直接暴露在 Internet 上。</span><span class="sxs-lookup"><span data-stu-id="084e4-157">The gateway uses Secure Sockets Layer (SSL) to encrypt communications and prevents the system hosting RDS from being directly exposed to the Internet.</span></span>

![带远程桌面服务网关的远程桌面服务连接](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

<span data-ttu-id="084e4-159">请参阅[这篇文章](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/)，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="084e4-159">See [this article](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) for more information.</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="084e4-160">用于远程访问的管理员技术资源</span><span class="sxs-lookup"><span data-stu-id="084e4-160">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="084e4-161">如何快速优化远程办公人员的 Office 365 流量并降低你的基础结构上的负载</span><span class="sxs-lookup"><span data-stu-id="084e4-161">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="084e4-162">使用 VPN 拆分隧道为远程用户优化 Office 365 连接</span><span class="sxs-lookup"><span data-stu-id="084e4-162">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="084e4-163">步骤 2 的结果</span><span class="sxs-lookup"><span data-stu-id="084e4-163">Results of Step 2</span></span>

<span data-ttu-id="084e4-164">为远程工作者部署远程访问解决方案后：</span><span class="sxs-lookup"><span data-stu-id="084e4-164">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="084e4-165">远程访问配置</span><span class="sxs-lookup"><span data-stu-id="084e4-165">Remote access configuration</span></span> | <span data-ttu-id="084e4-166">结果</span><span class="sxs-lookup"><span data-stu-id="084e4-166">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="084e4-167">远程访问 VPN 解决方案已到位</span><span class="sxs-lookup"><span data-stu-id="084e4-167">A remote access VPN solution is in place</span></span> | <span data-ttu-id="084e4-168">已经针对拆分隧道和 Microsoft 365 终结点的“优化”类别配置远程访问 VPN 客户端。</span><span class="sxs-lookup"><span data-stu-id="084e4-168">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="084e4-169">没有远程访问 VPN 解决方案，并且只需远程访问基于 Web 的本地应用</span><span class="sxs-lookup"><span data-stu-id="084e4-169">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="084e4-170">已配置 Azure 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="084e4-170">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="084e4-171">没有远程访问 VPN 解决方案，并且需要访问本地应用，其中一些应用并非基于 Web</span><span class="sxs-lookup"><span data-stu-id="084e4-171">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="084e4-172">已配置 Azure P2S VPN。</span><span class="sxs-lookup"><span data-stu-id="084e4-172">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="084e4-173">远程工作人员正在家中使用自己的个人设备</span><span class="sxs-lookup"><span data-stu-id="084e4-173">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="084e4-174">已配置 Windows 虚拟桌面。</span><span class="sxs-lookup"><span data-stu-id="084e4-174">You have configured Windows Virtual Desktop.</span></span> |
| <span data-ttu-id="084e4-175">远程工作者将使用到本地系统的 RDS 连接</span><span class="sxs-lookup"><span data-stu-id="084e4-175">Remote workers are using RDS connections to on-premises systems</span></span> | <span data-ttu-id="084e4-176">已在边缘网络中部署远程桌面服务网关。</span><span class="sxs-lookup"><span data-stu-id="084e4-176">You have deployed a Remote Desktop Services gateway in your edge network.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="084e4-177">后续步骤</span><span class="sxs-lookup"><span data-stu-id="084e4-177">Next step</span></span>

<span data-ttu-id="084e4-178">继续[步骤 3](empower-people-to-work-remotely-security-compliance.md)，部署 Microsoft 365 安全和合规性服务，以保护你的应用、数据和设备。</span><span class="sxs-lookup"><span data-stu-id="084e4-178">Continue with [Step 3](empower-people-to-work-remotely-security-compliance.md) to deploy Microsoft 365 security and compliance services to protect your apps, data, and devices.</span></span>
