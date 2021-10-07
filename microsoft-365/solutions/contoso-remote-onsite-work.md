---
title: Contoso 的 COVID-19 响应和支持混合工作
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso Corporation 如何响应 COVID-19 病毒，并针对混合工作设计其软件安装和更新基础结构。
ms.openlocfilehash: 9ed3857c97bd82bd03a6a192bec5666f22e0589a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207483"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a>Contoso 的 COVID-19 响应和支持混合工作

Contoso 始终支持远程工作者，这些工作者通过巴黎总部的中央 VPN 服务器访问本地资源。 Contoso 向所有远程工作者颁发了托管笔记本电脑。 本地工作人员混合使用台式计算机和笔记本电脑。

## <a name="contosos-response-to-covid-19"></a>Contoso 对 COVID-19 的响应

随着 COVID-19 病毒的爆发，突然，只有基本工作者都是远程工作者。 Contoso 通过远程访问本地资源和使用云服务在线方式将员工从家Microsoft 365活动作为响应。

Contoso 在巴黎总部办公室拥有远程访问 VPN 服务器，以支持 25% 的已远程工作人员，但迅速移动以扩展其远程访问容量以支持 90% 的员工。 Contoso 在每个附属办事处部署了远程访问 VPN 服务器，以便远程工作人员使用区域关闭入口点来访问 Contoso Intranet。

Contoso 还更新了安装在笔记本电脑、平板电脑和智能手机上用于拆分隧道的 VPN 客户端的配置，以便 Office 365 优化终结点集的流量绕过 VPN 连接并直接通过 Internet 发送。 有关详细信息，请参阅S [optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md)。

下面是在巴黎总部和每个附属办事处安装了 VPN 设备的配置结果。 

![Contoso 的 VPN 基础结构。](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

安装了 VPN 客户端的远程工作者使用 DNS 查找区域最近的办公室并连接到安装在那里的 VPN 设备。 通过拆分隧道，Microsoft 365 Optimize 终结点的流量将直接发送到区域最近的Microsoft 365位置。 所有其他流量通过 VPN 连接发送到 VPN 设备。

## <a name="contosos-support-for-hybrid-work"></a>Contoso 对混合工作的支持

在区域锁定期间进行初始更改以支持大多数远程工作者后，Contoso 进行了基础结构更改以支持工作者可能为的混合工作：

- 始终远程。
- 始终现场。
- 现场和远程的组合。

Microsoft 365标识、安全性和合规性功能专为零信任设计，无论用户及其设备的位置如何，这些功能均可运行。 有关详细信息，请参阅零 [信任](https://www.microsoft.com/security/business/zero-trust)。

但是，管理软件的新安装和更新取决于设备的位置，因为要安装的软件可能来自本地或 Internet 源。 Contoso IT 架构师根据设备的位置（而不是工作者）设计了新的安装和更新基础结构。

他们指定了两种类型的设备：专用本地和漫游。

### <a name="dedicated-on-premises"></a>专用本地

专用本地设备是永远不会离开 Contoso Intranet 且未安装 VPN 客户端的桌面或服务器计算机。 这些本地设备继续使用 Microsoft Endpoint Configuration Manager 及其分发点来安装和更新 Windows 10、Microsoft 365 企业应用版 和 Edge 浏览器。

### <a name="roaming"></a>漫游

漫游设备可以离开 Contoso Intranet，并包括颁发给许多办公室工作人员以及所有远程工作者以及其他组织拥有的设备（如安装了 Contoso VPN 客户端的智能手机和平板电脑）的笔记本电脑。 

由于这些设备可以在任何给定时间连接到 Internet，因此它们使用 Intune 或其他基于云的服务来安装和更新 Windows 10、Microsoft 365 企业应用版 和 Edge。 它们不使用现有的本地 Configuration Manager 分发点。

这意味着漫游设备的一些安装和更新将在漫游设备位于本地并连接到 Intranet 时通过 Internet 完成。 但 Contoso IT 架构师认为，配置简单性比优化 Intranet 带宽到 Internet 更重要，尤其是当大多数远程工作者很少连接到 Intranet 时。

下面是生成的基础结构。

![Contoso 的安装和更新基础结构。](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

安装和更新行为由使设备的计算机帐户成为以下组之一的成员来确定：

- OnPremDevices

  设备上 Configuration Manager 客户端使用分发点进行安装和更新。

- RoamingDevices

  Intune 和设备上的其他设置指定使用 Microsoft 365 网络进行安装和更新。

## <a name="new-onboarding-process"></a>新的载入过程

对于颁发给新工作者或数据中心中新服务器的专用本地设备，当工作者登录时，基于 OnPremDevices 组中设备成员身份的 Configuration Manager 客户端从本地 Configuration Manager 分发点下载并安装 Windows 10、Microsoft 365 企业应用版 和 Edge 的最新更新。 完成后，专用本地设备即可供使用，并使用这些分发点进行持续更新。

对于颁发给新工作者的新远程设备，当工作者登录时，该设备会基于其 RoamingDevices 组的成员身份联系 Intune 云服务和其他服务，并下载并安装 Windows 10、Microsoft 365 企业应用版 和 Edge 的最新更新。 完成后，远程设备即可使用，并使用已安装的 VPN 客户端访问本地资源，并使用 Microsoft 365 网络进行持续更新。

## <a name="next-step"></a>后续步骤

[在组织中设置混合工作的](empower-people-to-work-remotely.md) 基础结构。
