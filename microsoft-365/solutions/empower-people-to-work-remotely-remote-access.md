---
title: 步骤 2. 提供对本地应用和服务的远程访问权限。
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
description: 确保远程工作者可以访问本地资源，同时优化对 Microsoft 365 云服务的访问权限。
ms.openlocfilehash: fb91451b52c55f2cad1e0efefe19a044ce1cc37b
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002442"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="b73bc-104">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="b73bc-104">Step 2.</span></span> <span data-ttu-id="b73bc-105">提供对本地应用和服务的远程访问权限。</span><span class="sxs-lookup"><span data-stu-id="b73bc-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="b73bc-106">如果你的组织使用远程访问 VPN 解决方案（通常通过网络边缘上的 VPN 服务器以及在用户的设备上安装的 VPN 客户端），你的用户可以使用远程访问 VPN 连接来访问本地应用和服务器。</span><span class="sxs-lookup"><span data-stu-id="b73bc-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="b73bc-107">但是，你可能需要优化与 Microsoft 365 基于云的服务的通信。</span><span class="sxs-lookup"><span data-stu-id="b73bc-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="b73bc-108">如果你的用户未使用 VPN 解决方案，你可以使用 Azure Active Directory (Azure AD) 应用程序代理和 Azure 点到站点 (P2S) VPN 来提供访问权限，具体取决于你的所有应用是否均基于 Web。</span><span class="sxs-lookup"><span data-stu-id="b73bc-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="b73bc-109">有三种主要配置：</span><span class="sxs-lookup"><span data-stu-id="b73bc-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="b73bc-110">你已在使用远程访问 VPN 解决方案。</span><span class="sxs-lookup"><span data-stu-id="b73bc-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="b73bc-111">你使用的不是远程访问 VPN 解决方案，你有混合标识，只需远程访问基于 Web 的本地应用。</span><span class="sxs-lookup"><span data-stu-id="b73bc-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="b73bc-112">你使用的不是远程访问 VPN 解决方案，并且你需要访问本地应用，其中一些应用并非基于 Web。</span><span class="sxs-lookup"><span data-stu-id="b73bc-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="b73bc-113">借助远程访问连接，还可以使用[远程桌面](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop)将用户连接到本地电脑。</span><span class="sxs-lookup"><span data-stu-id="b73bc-113">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="b73bc-114">例如，远程工作者可使用远程桌面从其 Windows、iOS 或 Android 设备连接到其办公室的电脑。</span><span class="sxs-lookup"><span data-stu-id="b73bc-114">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="b73bc-115">远程连接后，他们可以像坐在电脑前一样使用它。</span><span class="sxs-lookup"><span data-stu-id="b73bc-115">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="b73bc-116">优化 Microsoft 365 云服务远程访问 VPN 客户端的性能</span><span class="sxs-lookup"><span data-stu-id="b73bc-116">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="b73bc-117">如果远程工作者正在使用传统的 VPN 客户端来获取对组织网络的远程访问权限，请验证该 VPN 客户端是否支持拆分隧道。</span><span class="sxs-lookup"><span data-stu-id="b73bc-117">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="b73bc-118">如果没有拆分隧道，所有远程工作通信都将通过 VPN 连接发送。在这种情况下，必须将其转发到组织的边缘设备、进行处理，然后在 Internet 上发送。</span><span class="sxs-lookup"><span data-stu-id="b73bc-118">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![来自无隧道的 VPN 客户端的网络流量](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="b73bc-120">Microsoft 365 通信必须通过你的组织获取间接路由，它可能是面向远离 VPN 客户端物理位置的 Microsoft 网络入口点的转发。</span><span class="sxs-lookup"><span data-stu-id="b73bc-120">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="b73bc-121">此间接路径会增加网络流量的延迟并降低整体性能。</span><span class="sxs-lookup"><span data-stu-id="b73bc-121">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="b73bc-122">借助拆分隧道，你可以将 VPN 客户端配置为排除通过 VPN 连接发送到组织网络的特定类型的通信。</span><span class="sxs-lookup"><span data-stu-id="b73bc-122">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="b73bc-123">要优化 Microsoft 365 云资源的访问权限，请将拆分隧道 VPN 客户端配置为排除通过 VPN 连接的流向**优化**类别 Microsoft 365 终结点的流量。</span><span class="sxs-lookup"><span data-stu-id="b73bc-123">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="b73bc-124">有关详细信息，请参阅 [Office 365 终结点类别](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)。</span><span class="sxs-lookup"><span data-stu-id="b73bc-124">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="b73bc-125">请在[此处](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)查看优化类别终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="b73bc-125">See the list of Optimize category endpoints [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

![来自有隧道的 VPN 客户端的网络流量](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="b73bc-127">这允许 VPN 客户端直接通过 Internet 发送和接收重要的 Microsoft 365 云服务流量并发送到 Microsoft 网络最近的入口点。</span><span class="sxs-lookup"><span data-stu-id="b73bc-127">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="b73bc-128">有关更多信息和指导，请参阅[使用 VPN 拆分隧道为远程用户优化 Office 365 连接](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)。</span><span class="sxs-lookup"><span data-stu-id="b73bc-128">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="b73bc-129">在所有应用均为 Web 应用且你具有混合标识的情况下部署远程访问</span><span class="sxs-lookup"><span data-stu-id="b73bc-129">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="b73bc-130">如果远程工作者使用的不是传统的 VPN 客户端，并且你的本地用户帐户和组与 Azure AD 同步，则可以使用 Azure AD 应用程序代理为 Intranet 服务器上托管的基于 Web 的应用程序实现安全的远程访问。</span><span class="sxs-lookup"><span data-stu-id="b73bc-130">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="b73bc-131">基于 Web 的应用程序包括 SharePoint 网站、Outlook Web Access 服务器或任何其他基于 Web 的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="b73bc-131">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="b73bc-132">下面是 Azure AD 应用程序代理的组件。</span><span class="sxs-lookup"><span data-stu-id="b73bc-132">Here are the components of Azure AD Application Proxy.</span></span>

![Azure AD 应用程序代理的组件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="b73bc-134">有关详细信息，请参阅此 [Azure AD 应用程序代理概述](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。</span><span class="sxs-lookup"><span data-stu-id="b73bc-134">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="b73bc-135">在并非所有应用均为 Web 应用的情况下部署远程访问</span><span class="sxs-lookup"><span data-stu-id="b73bc-135">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="b73bc-136">如果远程工作者使用的不是传统的 VPN 客户端，并且你的任何应用不是基于 Web，则可以使用 Azure 点到站点 (P2S) VPN。</span><span class="sxs-lookup"><span data-stu-id="b73bc-136">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="b73bc-137">P2S VPN 连接通过 Azure 虚拟网络创建从远程工作者的设备到组织网络的安全连接。</span><span class="sxs-lookup"><span data-stu-id="b73bc-137">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Azure P2S VPN 的组件](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="b73bc-139">有关详细信息，请参阅此 [P2S VPN 概述](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about)。</span><span class="sxs-lookup"><span data-stu-id="b73bc-139">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="b73bc-140">部署 Windows 虚拟桌面，以便为使用个人设备的远程工作者提供远程访问权限</span><span class="sxs-lookup"><span data-stu-id="b73bc-140">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="b73bc-141">要为仅可使用自己的个人和非托管设备的远程工作者提供支持，请使用 Azure 中的 Windows 虚拟桌面创建并分配虚拟桌面，以便用户在家中使用。</span><span class="sxs-lookup"><span data-stu-id="b73bc-141">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span>

<span data-ttu-id="b73bc-142">虚拟电脑可以像连接到组织网络的电脑一样操作。</span><span class="sxs-lookup"><span data-stu-id="b73bc-142">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

<span data-ttu-id="b73bc-143">有关详细信息，请参阅此 [Windows 虚拟桌面概述](https://docs.microsoft.com/azure/virtual-desktop/overview)。</span><span class="sxs-lookup"><span data-stu-id="b73bc-143">For more information, see [this overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="b73bc-144">用于远程访问的管理员技术资源</span><span class="sxs-lookup"><span data-stu-id="b73bc-144">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="b73bc-145">如何快速优化远程办公人员的 Office 365 流量并降低你的基础结构上的负载</span><span class="sxs-lookup"><span data-stu-id="b73bc-145">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="b73bc-146">使用 VPN 拆分隧道为远程用户优化 Office 365 连接</span><span class="sxs-lookup"><span data-stu-id="b73bc-146">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="b73bc-147">步骤 2 的结果</span><span class="sxs-lookup"><span data-stu-id="b73bc-147">Results of Step 2</span></span>

<span data-ttu-id="b73bc-148">为远程工作者部署远程访问解决方案后：</span><span class="sxs-lookup"><span data-stu-id="b73bc-148">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="b73bc-149">远程访问配置</span><span class="sxs-lookup"><span data-stu-id="b73bc-149">Remote access configuration</span></span> | <span data-ttu-id="b73bc-150">结果</span><span class="sxs-lookup"><span data-stu-id="b73bc-150">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="b73bc-151">远程访问 VPN 解决方案已到位</span><span class="sxs-lookup"><span data-stu-id="b73bc-151">A remote access VPN solution is in place</span></span> | <span data-ttu-id="b73bc-152">已经针对拆分隧道和 Microsoft 365 终结点的“优化”类别配置远程访问 VPN 客户端。</span><span class="sxs-lookup"><span data-stu-id="b73bc-152">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="b73bc-153">没有远程访问 VPN 解决方案，并且只需远程访问基于 Web 的本地应用</span><span class="sxs-lookup"><span data-stu-id="b73bc-153">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="b73bc-154">已配置 Azure 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="b73bc-154">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="b73bc-155">没有远程访问 VPN 解决方案，并且需要访问本地应用，其中一些应用并非基于 Web</span><span class="sxs-lookup"><span data-stu-id="b73bc-155">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="b73bc-156">已配置 Azure P2S VPN。</span><span class="sxs-lookup"><span data-stu-id="b73bc-156">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="b73bc-157">远程工作人员正在家中使用自己的个人设备</span><span class="sxs-lookup"><span data-stu-id="b73bc-157">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="b73bc-158">已配置 Windows 虚拟桌面。</span><span class="sxs-lookup"><span data-stu-id="b73bc-158">You have configured Windows Virtual Desktop.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="b73bc-159">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b73bc-159">Next step</span></span>

<span data-ttu-id="b73bc-160">继续执行[步骤 3](empower-people-to-work-remotely-manage-endpoints.md)，以管理你的设备、电脑和其他终结点。</span><span class="sxs-lookup"><span data-stu-id="b73bc-160">Continue with [Step 3](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
