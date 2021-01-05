---
title: Microsoft 365 通知网络路由
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/22/2020
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
ms.openlocfilehash: 367f83684a4a200e3ddd630e1412c756d7093da1
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749547"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 通知网络路由 (预览) 

智能网络路由是一项功能，可以将各种 Microsoft 365 应用程序与第三方软件定义的网络 (SD-WAN) 解决方案集成，以优化和改进与 Microsoft 服务终结点的网络连接。 优化的 SD-WAN 连接可能会改进用户体验和性能。

>[!IMPORTANT]
>Microsoft 365 通知网络路由当前处于预览状态。 有关此预览的详细信息，包括接收协助的指南，请参阅 [Microsoft 365 通知网络路由公共预览版](https://go.microsoft.com/fwlink/?linkid=2151565)。

## <a name="overview"></a>概述

智能网络路由在 Microsoft 和 SD-WAN 解决方案之间提供双向数据共享通道。 对于您配置的每个办公室位置和 Internet 电路，Microsoft 会定期与 SD-WAN 解决方案共享与每个特定 Internet 电路关联的选定 Microsoft 365 应用程序体验质量的反馈。 然后，SD-WAN 解决方案可以使用此反馈通过备用可用链接路由 Microsoft 365 应用程序流量，以执行智能恢复操作。 

很难持续检测特定 Internet 电路路径中的服务质量下降，如延迟增加或数据包丢失率高。 这些降级可能会对 Exchange Online、SharePoint、OneDrive 和 Microsoft Teams 等应用程序的用户体验产生不利影响。 常见症状包括 Exchange 内容的搜索缓慢、与 SharePoint 或 OneDrive 文档库交互时传输时间长，或者 Microsoft Teams 中的通话或会议质量差。

网络通知路由中的反馈和恢复机制旨在以近实时方式动态检测此类问题，并通知部署的 SD-WAN 解决方案执行自动恢复操作。

数据共享通道还用于定期接收来自 SD-WAN 解决方案的网络级光学数据，包括与设备和连接的电路关联的配置信息和使用情况统计信息。 不会收集或存储任何个人信息。 所有收集的信息将聚合到办公室位置和连接的 Internet 线路。 此信息可帮助 Microsoft 更有效地解决使用 Microsoft 365 服务和应用程序时报告的问题。

>[!NOTE]
>Microsoft 365 通知网络路由支持 WW 商业云中的租户，但不包括 GCC 中等、GCC 高、DoD、德国或中国云。

## <a name="requirements"></a>要求

### <a name="integrated-sd-wan-solutions"></a>集成 SD-WAN 解决方案

Microsoft 正在与各种合作伙伴合作，以便能够与 Microsoft 365 通知网络路由集成。 当前启用的解决方案包括：

| Device Maker | 解决方案名称 | 最低版本 |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>网络拓扑 

通知网络路由当前基于用于向 Microsoft 发送网络流量的公共 IP 地址，标识与特定办公地点和 Internet 电路关联的流量。 

如果分支位置没有至少一个提供直接 Internet 访问的网络电路，则网络通知路由可能不会提供显著价值。

### <a name="application-usage"></a>应用程序使用情况

应用程序体验 (通过网络质量指标反映) 是在运行 Windows、Teams、SharePoint 和 OneDrive 的设备上使用 Microsoft Outlook 收集的。 在评估网络电路的运行状况时，不会考虑其他应用程序流量。

## <a name="enabling-informed-network-routing"></a>启用智能网络路由

启用智能网络路由需要多个步骤，其中一些步骤需要在 SD-WAN 解决方案的配置接口内执行。 有关如何在 Microsoft 365 管理中心中继续配置之前启动在 SD-WAN 解决方案内启用网络通知路由的过程的指导，请咨询您的 SD-WAN 解决方案供应商。

准备好在 Microsoft 365 管理中心启用通知网络路由后，请确保你拥有必要的全局管理员权限。

>[!IMPORTANT]
>为了为所选 SD-WAN 解决方案提供必要的租户级应用程序权限同意，以访问通知的网络路由数据共享通道，必须以全局管理员角色执行以下步骤。


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步骤 1：打开 SD-WAN 解决方案配置选项

在 [Microsoft 365 管理](https://admin.microsoft.com/)中心 **，选择>** 导航窗格中的"运行状况"和"网络连接"。

管理中心的这一部分为组织提供了聚合的网络连接指标，并提供了有关如何提高连接性的指导。 有关管理中心内提供的这些功能的其他信息， [请参阅 Microsoft 365 ](office-365-network-mac-perf-overview.md) 管理中心 (预览) 中的网络连接。

Select **Settings > SD-WAN solution** to open the informed network routing configuration pane. "设置"下显示的其他选项适用于管理中心中的一般网络连接指南，不需要这些选项来启用智能网络路由。

在配置窗格中，选择"将 **SD-WAN 解决方案 (预览) 。**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>步骤 2：选择 SD-WAN 解决方案和数据存储位置

在下拉框中，选择已部署的 SD-WAN 解决方案以及要存储与网络通知路由关联的数据的位置。 有关 [其他信息，](#data-storage) 请参阅数据存储部分。

选择“**下一步**”。

### <a name="step-3-accept-terms-for-sharing-of-data"></a>步骤 3：接受数据共享条款

仔细阅读并确认提供的与在 Microsoft 和所选 SD-WAN 解决方案之间共享数据相关的条款，然后选中指示的复选框。

选择“**下一步**”。

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>步骤 4：向 SD-WAN 解决方案授予权限

此步骤将启动 Azure Active Directory 权限授予请求 (Azure AD) 。 将请求你授予租户级别权限，以允许所选 SD-WAN 解决方案访问与租户关联的通知网络路由数据存储和服务运行状况信息。 此操作需要全局管理员角色权限。

选择 **"授予对此应用程序的权限"** 链接并按照 Azure AD 请求操作。

完成权限授予后，选择"下一 **步"。**

### <a name="step-5-confirm-your-configuration-settings"></a>步骤 5：确认配置设置

为租户启用网络通知路由的最后一步是显示你提供的设置的确认页面。 

现在为租户启用了通知网络路由。

选择 **"** 完成"，然后关闭 SD-WAN 解决方案配置窗格。

## <a name="configuring-network-informed-routing"></a>配置网络通知路由

您将对 SD-WAN 解决方案中的明智网络路由执行大部分配置，例如配置在正常情况下如何路由流量，以及检测到问题时应该使用的备用路径。 有关这些配置步骤的详细信息，请咨询您的 SD-WAN 解决方案提供商。

必须在 Microsoft 365 管理中心中配置每个办公室位置，以便通知的网络路由可以正确识别与提供这些位置连接的网络电路相关的流量。

Office 位置可以自动检测为 Microsoft 正在进行的网络遥测集合的一部分。 因此，某些位置可能会预先填充到租户的管理中心中。 

如果这些位置准确，则只需为每个所需位置启用通知网络路由功能，并配置 Internet 线路及其公用 IP 地址。 

如果自动检测的位置不准确，或者租户中没有预填充的位置，您必须手动添加或编辑位置，以反映组织的准确拓扑。

### <a name="updating-locations"></a>更新位置

可在"位置"选项卡下找到 **租户的位置。** 可以直接在列表中编辑位置，或者使用 CSV 文件更新位置。

确保要启用通知网络路由的每个办公室位置都存在于此列表中。

>[!NOTE]
>收集的示例 **和其他** 评估相关信息的位置列表中的列与通知网络路由功能不相关。

### <a name="enabling-a-location-for-informed-network-routing"></a>为智能网络路由启用位置

1. 在 **"位置"** 列表中，从快速操作菜单中选择"编辑"以打开位置配置窗格。

2. 选择 **"在此位置使用 Microsoft 365 通知网络路由"。**

3. 在此办公室位置部分，将提供 Internet 连接的所有网络电路添加到"出口 IP 地址"范围中的 **此办公室** 位置。 确保每个电路与代表网络流量的唯一公用 IP 地址子网关联。

4. 选择“**保存**”以保存所做的更改。

## <a name="disabling-network-informed-routing"></a>禁用网络通知路由

通过重置 SD-WAN 解决方案设置，可能会为整个租户禁用通知网络路由功能。 虽然这将停止 Microsoft 365 内的所有数据处理，但还应在管理中心内禁用网络通知路由。

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步骤 1：打开 SD-WAN 解决方案配置选项

在 [Microsoft 365 管理](https://admin.microsoft.com/) 中心> **左侧** 导航窗格中选择"运行状况"和"网络连接"。

Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.

配置窗格显示当前配置的 SD-WAN 解决方案的摘要。

### <a name="step-2-reset-your-configuration"></a>步骤 2：重置配置

在配置窗格中，选择 **"重置 SD-WAN 解决方案设置"。**

现在已重置设置，并且已禁用通知网络路由。 你可按照启用通知网络路由 [中的步骤随时重新启用它](#enabling-informed-network-routing)。

## <a name="data-storage"></a>数据存储

Microsoft 与 SD-WAN 解决方案提供商之间交换的数据存储在初始启用网络通知路由期间所选的数据存储位置。 数据存储位置选项表示包含存储数据的 Microsoft Azure 区域的地理区域。

>[!NOTE]
>在预览阶段，唯一可用的数据存储位置是 **北美**。 在通知网络路由的一般可用之前，其他数据存储位置将可用。

数据将在此位置保留最多 30 天。 禁用后，将在此 30 天保留时段内删除所有剩余数据。

## <a name="related-topics"></a>相关主题

[Microsoft 365 管理中心中的网络连接 (预览) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 网络连接位置服务 (预览) ](office-365-network-mac-location-services.md)
