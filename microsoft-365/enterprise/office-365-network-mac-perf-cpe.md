---
title: Microsoft 365 通知网络路由
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 通知网络路由
ms.openlocfilehash: 40b4345ca80c5e90a07583b83b82368d4a35535a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611432"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 通知网络路由 (预览) 

已通知网络路由是一项功能，可将各种 Microsoft 365 应用程序集成到第三方软件定义的网络 (SD WAN) 解决方案中，以优化和改进与 Microsoft 服务终结点的网络连接。 优化的 SD WAN 连接可能会导致用户体验和性能提高。

>[!IMPORTANT]
>Microsoft 365 通知网络路由当前处于预览状态。 有关此预览的详细信息，包括接收帮助的指南，请参阅 [Microsoft 365 通知网络路由公共预览版](https://go.microsoft.com/fwlink/?linkid=2151565)。

## <a name="overview"></a>概述

已通知网络路由在 Microsoft 与您的 SD WAN 解决方案之间提供双向数据共享通道。 对于您配置的每个办公室位置和 Internet 电路，Microsoft 会定期与在所选 Microsoft 365 应用程序体验的质量上，与每个特定 Internet 电路相关联的网络流量与 SD WAN 解决方案共享反馈。 通过此反馈，SD WAN 解决方案可以通过使用可替换的可用链接来路由 Microsoft 365 应用程序流量，从而执行智能恢复操作。 

特定 Internet 电路（如增加的延迟或高数据包丢失）的路径中的服务质量降低很难连续检测。 这些降低可能会对 Exchange Online、SharePoint、OneDrive 和 Microsoft 团队等应用程序的用户体验产生不利的损害。 常见症状包括对 Exchange 内容的搜索速度较慢、在与 SharePoint 或 OneDrive 文档库交互或 Microsoft 团队中的通话或会议质量较差时的传输时间较高。

网络中的反馈和恢复机制通知路由旨在实时动态检测此类问题，并通知部署的 SD WAN 解决方案执行自动恢复操作。

数据共享通道还可用于定期接收 SD WAN 解决方案中的网络级光学数据，包括与设备和附加电路相关联的配置信息和使用情况统计信息。 不会收集或存储任何个人信息。 所有收集的信息都聚合到办公室位置和连接的 Internet 电路中。 此信息可以帮助 Microsoft 更高效地解决使用 Microsoft 365 服务和应用程序时报告的问题。

>[!NOTE]
>Microsoft 365 通知网络路由支持 WW 商业云中的租户，但不支持 GCC 中级、GCC 高、DoD、德国或中国云。

## <a name="requirements"></a>Requirements

### <a name="integrated-sd-wan-solutions"></a>集成的 SD 广域网解决方案

Microsoft 正在与各种合作伙伴合作，以实现与 Microsoft 365 的网络路由的集成。 当前启用的解决方案包括以下各项：

| 设备生成器 | 解决方案名称 | 最低版本 |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>网络拓扑 

已通知网络路由当前根据用于向 Microsoft 发送网络流量的公用 IP 地址来标识与特定办公室位置和 Internet 电路相关联的流量。 

如果没有至少一条网络电路在分支机构提供直接 Internet 访问，则网络通知路由可能不会提供显著价值。

### <a name="application-usage"></a>应用程序使用

通过在运行 Windows、团队、SharePoint 和 OneDrive 的设备上使用 Microsoft Outlook，在网络质量指标) 中反映的应用程序体验数据 (。 评估网络电路的运行状况时不会考虑其他应用程序通信。

## <a name="enabling-informed-network-routing"></a>启用通知的网络路由

启用通知网络路由需要多个步骤，其中一些步骤将需要在您的 SD WAN 解决方案的配置界面中执行。 请咨询您的 SD WAN 解决方案供应商，以获取有关如何启动在 SD WAN 解决方案内启用网络通知路由的过程的指南，然后再继续使用 Microsoft 365 管理中心中的配置。

准备好在 Microsoft 365 管理中心中启用已通知的网络路由后，请确保您具有必要的全局管理员权限。

>[!IMPORTANT]
>为了提供所需的租户级应用程序权限，为所选的 SD WAN 解决方案访问已通知的网络路由数据共享频道，必须以全局管理员身份执行以下步骤。


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步骤1：打开 SD-WAN 解决方案配置选项

在 [Microsoft 365 管理中心](https://admin.microsoft.com/)，在左侧导航窗格中选择 " **运行状况 > 网络连接** "。

本管理中心的这一部分为您的组织提供聚合网络连接指标，并提供有关如何提高连接性的指导。 有关管理员中心中提供的这些功能的其他信息，请参阅 [Microsoft 365 管理中心中的网络连接 (预览) ](office-365-network-mac-perf-overview.md) 。

选择 " **设置" > "SD WAN 解决方案** " 以打开 "已通知的网络路由配置" 窗格。 " **设置** " 下显示的其他选项适用于 "管理中心" 中的常规网络连接指南，无需启用通知网络路由。

在 "配置" 窗格中，选择 " **添加您的 SD-WAN 解决方案 (预览)**"。

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>步骤2：选择您的 SD WAN 解决方案和数据存储位置

在下拉框中，选择已部署的 SD WAN 解决方案，以及希望将与网络通知路由相关联的数据存储到的位置。 有关其他信息，请参阅 " [数据存储](#data-storage) " 部分。

选择“下一步”。

### <a name="step-3-accept-terms-for-sharing-of-data"></a>步骤3：接受数据共享的条款

仔细阅读并确认与在 Microsoft 和所选的 SD WAN 解决方案之间共享数据相关联的提供的术语，然后选择指示的复选框。

选择“下一步”。

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>步骤4：授予对 SD WAN 解决方案的权限

此步骤将启动 Azure Active Directory (Azure AD) 的权限授予请求。 你将被请求授予租户级权限，这些权限允许你所选的 SD WAN 解决方案访问已通知的网络路由数据存储和与你的租户关联的服务运行状况信息。 此操作需要全局管理员角色权限。

选择 " **授予对此应用程序的权限** " 链接并遵循 Azure AD 请求。

完成权限授予后，选择 " **下一步**"。

### <a name="step-5-confirm-your-configuration-settings"></a>步骤5：确认配置设置

为租户启用网络通知的路由的最后一步是显示你提供的设置的确认页。 

现已为你的租户启用通知网络路由。

选择 " **完成** "，然后关闭 "SD-WAN 解决方案配置" 窗格。

## <a name="configuring-network-informed-routing"></a>配置网络通知路由

您将在您的 SD WAN 解决方案中对已通知的网络路由执行大量配置，例如在正常情况下配置流量应如何路由以及在检测到问题时应使用的备用路径。 有关这些配置步骤的详细信息，请参阅 SD WAN 解决方案提供商。

每个办公室位置必须在 Microsoft 365 管理中心中进行配置，以便有通知的网络路由能够正确识别与网络电路相关联的通信，从而实现这些位置的连接。

在 Microsoft 正在进行的网络遥测集合中，可能会自动检测到办公室位置。 因此，某些位置可能在你的租户的管理中心内预先填充。 

如果这些位置是准确的，则只需为每个所需位置启用已通知的网络路由功能，并配置 Internet 线路及其公共 IP 地址。 

如果自动检测到的位置不准确，或者在租户中没有预先填充的位置，则必须手动添加或编辑位置，以反映组织的准确拓扑。

### <a name="updating-locations"></a>更新位置

可以在 " **位置** " 选项卡下找到租户的位置。位置可以直接在列表中编辑或使用 CSV 文件进行更新。

确保在此列表中存在要在其上启用通知网络路由的每个办公室位置。

>[!NOTE]
>收集的样本和其他与评估相关的信息的 **位置** 列表中的列与通知的网络路由功能无关。

### <a name="enabling-a-location-for-informed-network-routing"></a>为已通知的网络路由启用位置

1. 在 " **位置** " 列表中，从 "快速操作" 菜单中选择 " **编辑** " 以打开 "位置配置" 窗格。

2. 选择 " **在此位置使用 Microsoft 365 通知网络路由**"。

3. 在此 "办公室位置" 部分的 " **传出 IP 地址范围** " 中，添加所有提供到此办公室位置的 Internet 连接的网络电路。 确保每个电路都与代表网络流量的唯一公共 IP 地址子网相关联。

4. 选择“**保存**”以保存所做的更改。

## <a name="disabling-network-informed-routing"></a>禁用网络通知路由

通过重置您的 SD-WAN 解决方案设置，可能会对整个租户禁用已通知的网络路由功能。 虽然这会在 Microsoft 365 中停止对数据的所有处理，但您还应禁用管理中心内的网络通知路由。

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步骤1：打开 SD-WAN 解决方案配置选项

在 [Microsoft 365 管理中心](https://admin.microsoft.com/) 中，在左侧导航窗格中选择 " **运行状况 > 网络连接** "。

选择 " **设置" > "SD WAN 解决方案** " 以打开 "已通知的网络路由配置" 窗格。

配置窗格显示当前配置的 SD WAN 解决方案的摘要。

### <a name="step-2-reset-your-configuration"></a>步骤2：重置配置

在 "配置" 窗格中，选择 " **重置您的 SD-WAN 解决方案设置**"。

你的设置现在已重置并通知网络路由已禁用。 您可以随时重新启用它，方法是按照 [启用通知的网络路由](#enabling-informed-network-routing)中的步骤操作。

## <a name="data-storage"></a>数据存储

在 Microsoft 和 SD WAN 解决方案提供商之间交换的数据存储在最初启用网络通知路由的过程中所选的数据存储位置。 数据存储位置选项表示包含存储数据的 Microsoft Azure 区域的地理区域。

>[!NOTE]
>在预览阶段，仅适用 **于北美的** 数据存储位置。 在有通知的网络路由的常规可用性之前，其他数据存储位置将变为可用状态。

数据在此位置保留最长30天。 在禁用此功能时，将在此30天保留时段内删除所有剩余数据。

## <a name="related-topics"></a>相关主题

[Microsoft 365 管理中心中的网络连接 (预览版) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 网络连接位置服务 (预览) ](office-365-network-mac-location-services.md)
