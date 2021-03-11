---
title: Microsoft 365 通知网络路由
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
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
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717596"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 通知网络路由 (预览) 

通知网络路由是一项功能，可以将各种 Microsoft 365 应用程序与第三方软件定义的网络 (SD-WAN) 解决方案集成，以优化和改进与 Microsoft 服务终结点的网络连接。 优化的 SD-WAN 连接可能会改善用户体验和性能。

>[!IMPORTANT]
>Microsoft 365 通知网络路由当前处于预览状态。 有关此预览的详细信息，包括接收协助的指导，请参阅 [Microsoft 365 通知网络路由公共预览版](https://go.microsoft.com/fwlink/?linkid=2151565)。

## <a name="overview"></a>概述

通知网络路由在 Microsoft 和 SD-WAN 解决方案之间提供双向数据共享通道。 对于您配置的每个办公室位置和 Internet 线路，Microsoft 会定期与 SD-WAN 解决方案共享有关与每个特定 Internet 电路关联的网络流量的选定 Microsoft 365 应用程序体验质量的反馈。 使用此反馈，SD-WAN 解决方案随后可以通过通过备用可用链接路由 Microsoft 365 应用程序流量来采取智能恢复操作。 

很难持续检测特定 Internet 电路路径中的服务质量下降，例如延迟增加或数据包丢失率高。 这些降级可能会对 Exchange Online、SharePoint、OneDrive 和 Microsoft Teams 等应用程序的用户体验产生不利影响。 常见症状包括 Exchange 内容搜索缓慢、与 SharePoint 或 OneDrive 文档库交互时传输时间长，或者 Microsoft Teams 中的通话或会议质量差。

网络通知路由中的反馈和恢复机制旨在以近实时方式动态检测此类问题，并通知部署的 SD-WAN 解决方案采取自动恢复操作。

数据共享通道还用于定期从 SD-WAN 解决方案接收网络级别的光学数据，包括与设备和连接电路关联的配置信息和使用情况统计信息。 不收集或存储任何个人信息。 所有收集的信息将聚合到办公室位置和连接的 Internet 电路。 此信息可帮助 Microsoft 更有效地解决使用 Microsoft 365 服务和应用程序时报告的问题。

>[!NOTE]
>Microsoft 365 通知网络路由支持 WW 商业云中的租户，但不支持 GCC 中等、GCC 高、DoD、Germany 或中国云中的租户。

## <a name="requirements"></a>要求

### <a name="integrated-sd-wan-solutions"></a>集成的 SD-WAN 解决方案

Microsoft 正在与各种合作伙伴合作，以实现与 Microsoft 365 通知网络路由的集成。 当前启用的解决方案包括：

| Device Maker | 解决方案名称 | 最低版本 |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>网络拓扑 

通知网络路由当前根据用于向 Microsoft 发送网络流量的公共 IP 地址标识与特定办公室位置和 Internet 电路关联的流量。 

如果分支位置没有至少一个提供直接 Internet 访问的网络电路，则网络通知路由可能不会提供显著价值。

### <a name="application-usage"></a>应用程序使用情况

应用程序体验 (通过网络质量指标) 通过特定 Microsoft 客户端应用程序收集。 Exchange 指标反映 Outlook 客户端的使用情况以及一些Outlook Web App使用情况。 SharePoint 和 OneDrive 指标反映特定于租户的 SharePoint 终结点的使用情况，而不考虑客户端应用程序。 Teams 指标反映 Teams 桌面客户端的使用情况。 在评估网络电路的运行状况时，不会考虑其他应用程序流量。

## <a name="enabling-informed-network-routing"></a>启用通知网络路由

启用智能网络路由需要多个步骤，其中一些步骤需要在 SD-WAN 解决方案的配置接口内执行。 有关如何启动在 SD-WAN 解决方案中启用网络通知路由过程的指导，请咨询 SD-WAN 解决方案供应商，然后再在 Microsoft 365 管理中心继续配置。

准备好在 Microsoft 365 管理中心启用通知网络路由后，请确保你拥有必要的全局管理员权限。

>[!IMPORTANT]
>为了向选定的 SD-WAN 解决方案提供必要的租户级应用程序权限同意，以访问通知的网络路由数据共享通道，必须以全局管理员角色执行以下步骤。


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步骤 1：打开 SD-WAN 解决方案配置选项

在 [Microsoft 365 管理中心](https://admin.microsoft.com/)， **选择>导航** 窗格中的"运行状况"和"网络连接"。

管理中心的这一部分为组织提供聚合的网络连接指标，以及如何改进连接的指导。 请参阅 [Microsoft 365 ](office-365-network-mac-perf-overview.md) 管理中心 (预览) 中的网络连接，了解管理中心内提供的这些功能的其他信息。

Select **Settings > SD-WAN solution** to open the informed network routing configuration pane. "设置"下显示的其他选项适用于管理中心中的一般网络连接指南，不需要启用通知网络路由。

在配置窗格中，选择"将 **SD-WAN 解决方案 (预览) 。**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>步骤 2：选择 SD-WAN 解决方案和数据存储位置

在下拉列表中，选择已部署的 SD-WAN 解决方案以及要存储与网络通知路由关联的数据的位置。 有关 [其他信息，](#data-storage) 请参阅数据存储部分。

选择“**下一步**”。

### <a name="step-3-accept-terms-for-sharing-of-data"></a>步骤 3：接受数据共享条款

仔细阅读并确认提供的与 Microsoft 和所选 SD-WAN 解决方案之间共享数据相关的条款，然后选择指示的复选框。

选择“**下一步**”。

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>步骤 4：向 SD-WAN 解决方案授予权限

此步骤将启动 Azure Active Directory 和 Azure AD (的权限) 。 将请求授予租户级别权限，以允许所选 SD-WAN 解决方案访问与租户关联的通知网络路由数据存储和服务运行状况信息。 此操作需要全局管理员角色权限。

选择 **此应用程序链接的"授予** 权限"，然后遵循 Azure AD 请求。

完成权限授予后，选择"下一 **步"。**

### <a name="step-5-confirm-your-configuration-settings"></a>步骤 5：确认配置设置

为租户启用网络通知路由的最后一步是显示你提供的设置的确认页面。 

现在为租户启用了通知网络路由。

选择 **"** 完成"，然后关闭 SD-WAN 解决方案配置窗格。

## <a name="configuring-network-informed-routing"></a>配置网络通知路由

您将在 SD-WAN 解决方案中为通知网络路由执行大部分配置，例如配置在正常情况下应该如何路由流量，以及检测到问题时应该使用的备用路径。 有关这些配置步骤的详细信息，请咨询您的 SD-WAN 解决方案提供商。

必须在 Microsoft 365 管理中心中配置每个办公室位置，以便智能网络路由可以正确标识与提供这些位置连接的网络电路相关的流量。

Office 位置可能会自动检测为 Microsoft 正在进行的网络遥测集合的一部分。 因此，某些位置可能会预先填充在租户的管理中心中。 

如果这些位置准确，则只需为每个所需位置启用通知网络路由功能，并配置 Internet 线路及其公用 IP 地址。 

如果自动检测的位置不准确，或者租户中没有预填充的位置，您必须手动添加或编辑位置以反映组织的准确拓扑。

### <a name="updating-locations"></a>更新位置

可以在"位置"选项卡下找到 **租户的位置。** 可以直接在列表中编辑位置，或者使用 CSV 文件更新位置。

确保要启用通知网络路由的每个办公室位置都位于此列表中。

>[!NOTE]
>收集的示例 **和其他** 评估相关信息的位置列表中的列与通知网络路由功能不相关。

### <a name="enabling-a-location-for-informed-network-routing"></a>为智能网络路由启用位置

1. 在 **"位置"** 列表中，从快速操作菜单中选择"编辑"以打开位置配置窗格。

2. 选择 **在此位置使用 Microsoft 365 通知网络路由**。

3. 在此办公室位置部分"出口 IP 地址范围"中添加提供 Internet 连接的所有网络电路到此 **办公室** 位置。 确保每个电路与表示网络流量的唯一公用 IP 地址子网关联。

4. 选择“**保存**”以保存所做的更改。

## <a name="disabling-network-informed-routing"></a>禁用网络通知路由

通过重置 SD-WAN 解决方案设置，可能会为整个租户禁用通知网络路由功能。 虽然这将停止 Microsoft 365 内的所有数据处理，但还应在管理中心内禁用网络通知路由。

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步骤 1：打开 SD-WAN 解决方案配置选项

在 [Microsoft 365 管理](https://admin.microsoft.com/) 中心，> **导航** 窗格中选择"运行状况"和"网络连接"。

Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.

配置窗格显示当前配置的 SD-WAN 解决方案的摘要。

### <a name="step-2-reset-your-configuration"></a>步骤 2：重置配置

在配置窗格中，选择"**重置 SD-WAN 解决方案设置"。**

现在，已重置设置，并且已禁用通知网络路由。 可以通过按照启用通知网络路由 [中的步骤随时重新启用它](#enabling-informed-network-routing)。

## <a name="data-storage"></a>数据存储

Microsoft 与 SD-WAN 解决方案提供商之间交换的数据存储在初始启用网络通知路由期间所选的数据存储位置。 数据存储位置选项表示包含存储数据的 Microsoft Azure 区域的地理区域。

>[!NOTE]
>在预览阶段，唯一可用的数据存储位置是 **北美**。 在通知网络路由的一般可用之前，其他数据存储位置将变为可用位置。

数据将在此位置保留最多 30 天。 禁用后，将在此 30 天保留时段内删除所有剩余数据。

## <a name="related-topics"></a>相关主题

[Microsoft 365 管理中心中的网络连接 (预览) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 网络连接位置服务 (预览) ](office-365-network-mac-location-services.md)
