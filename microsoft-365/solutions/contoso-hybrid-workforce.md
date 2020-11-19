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
# <a name="contosos-covid-19-response-and-support-for-a-hybrid-workforce"></a>Contoso 的 COVID-19 响应和对混合劳动力的支持

Contoso 始终支持通过巴黎总部的中央 VPN 服务器访问本地资源的远程工作人员。 Contoso 已将所有远程工作人员颁发为托管便携式计算机。 内部部署工作人员混合了台式计算机和便携式计算机。

## <a name="contosos-response-to-covid-19"></a>Contoso 对 COVID 的响应-19

使用 COVID-19 pandemic 的 onset，您就会突然拥有远程工作人员的所有重要工作人员。 Contoso 通过将其员工的工作方式转移到家庭中，并通过远程访问本地资源并使用 Microsoft 365 云服务进行联机来响应其主要活动。

Contoso 在巴黎总部办事处拥有远程访问 VPN 服务器，以支持其已有的远程员工的25%，但快速移动以扩大 it 的远程访问能力，以支持其员工的90%。 Contoso 在每个卫星办公室中部署了远程访问 VPN 服务器，以便远程工作人员可以使用地区组织关闭入口点访问 Contoso intranet。

Contoso 还更新了用于拆分隧道的便携式电脑、平板电脑和智能手机上安装的 VPN 客户端的配置，以便优化 Office 365 终结点集的流量绕过 VPN 连接，并通过 internet 直接发送。 有关详细信息，请参阅 [使用 VPN 拆分隧道为远程用户优化 Office 365 连接](../enterprise/microsoft-365-vpn-split-tunnel.md)。

下面是安装在巴黎总部和每个卫星办公室中的 VPN 设备生成的配置。 

![Contoso 的 VPN 基础结构](../media/contoso-hybrid-workforce/contoso-vpn-infrastructure.png)

具有已安装的 VPN 客户端的远程工作人员使用 DNS 查找地区组织最近的 office，并连接到此处安装的 VPN 设备。 通过拆分隧道，到 Microsoft 365 的流量优化终结点将直接发送到最近的地区组织 Microsoft 365 网络位置。 所有其他流量通过 VPN 连接发送到 VPN 设备。

## <a name="contosos-support-for-a-dynamic-hybrid-workforce"></a>Contoso 对动态混合劳动力的支持

在区域 lockdowns 期间进行的大多数远程工作者支持的初始更改之后，Contoso 进行了基础结构更改，以支持工作人员可在其中执行以下操作的混合劳动力：

- 始终远程。
- 始终为本地。
- 远程和本地的组合。

Microsoft 365 标识、安全性和合规性功能是为实现零信任而设计的，无论用户及其设备的位置如何，都能正常工作。 有关详细信息，请参阅 [零信任](https://www.microsoft.com/security/business/zero-trust)。

但是，管理软件的新安装和更新取决于设备的位置，因为要安装的软件可能来自内部部署源或 internet 源。 Contoso IT 架构师根据设备的位置（而不是工作人员）设计他们的新安装和更新基础结构。

它们指定了两种类型的设备：专用本地和漫游。

### <a name="dedicated-on-premises"></a>专用本地

专用的本地设备是指从不离开 Contoso intranet 且未安装 VPN 客户端的台式机或服务器计算机。 这些本地设备继续使用 Microsoft 终结点配置管理器及其分发点来安装和更新 Windows 10、Microsoft 365 Apps for enterprise 和 Edge 浏览器。

### <a name="roaming"></a>漫游

漫游设备可以离开 Contoso intranet，并包括发布到许多 office 工作人员和所有远程工作人员和其他组织拥有的设备（例如智能手机和平板电脑）安装了 Contoso VPN 客户端的便携式计算机。 

由于可在任意给定时间将这些设备连接到 Internet，因此他们使用 Intune 或其他基于云的服务来安装和更新 Windows 10、Microsoft 365 Apps for enterprise 和 Edge。 它们不使用现有的本地配置管理器分发点。

这意味着漫游设备的某些安装和更新将通过 internet 进行，同时在本地进行，并连接到 intranet。 但 Contoso IT 架构师认为，配置的简单性比 internet 的 intranet 带宽优化更重要，尤其是当大多数远程工作人员很少连接到 intranet 时。

下面是生成的基础结构。

![Contoso 的安装和更新基础结构](../media/contoso-hybrid-workforce/contoso-updates-infrastructure.png)

通过将设备的计算机帐户设为以下组之一的成员来确定安装和更新行为：

- OnPremDevices

  设备上的 Configuration Manager 客户端使用分发点进行安装和更新。

- RoamingDevices

  Intune 和设备上的其他设置指定使用 Microsoft 365 网络进行安装和更新。

## <a name="new-onboarding-process"></a>新的载入过程

对于向新工作人员或在数据中心中的新服务器发出的新专用本地设备，当工作人员登录时，基于 OnPremDevices 组中设备的成员身份的 Configuration Manager 客户端将下载并安装 Windows 10、Microsoft 365 应用程序的最新更新和本地 Configuration Manager 分发点的边缘。 完成后，专用的本地设备即可供使用，并使用这些分发点进行持续更新。

对于颁发给新工作人员的新远程设备，当工作人员登录时，设备将基于其在 RoamingDevices 组中的成员身份，联系 Intune 云服务和其他服务并下载并安装最新的 Windows 10、Microsoft 365 Apps for enterprise 和 Edge 的更新。 完成后，远程设备即可供使用，并使用已安装的 VPN 客户端访问本地资源和 Microsoft 365 网络以进行持续更新。

## <a name="next-step"></a>后续步骤

[为你的组织中的远程工作人员准备工作](empower-people-to-work-remotely.md) 。
