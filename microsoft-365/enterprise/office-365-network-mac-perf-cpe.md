---
title: Microsoft 365网络路由
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/12/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365网络路由
ms.openlocfilehash: 84b16d696c5c99a7f917e8d1dacc6f1f27626f37
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064399"
---
# <a name="microsoft-365-informed-network-routing"></a>Microsoft 365网络路由

智能网络路由是一项功能，可以将各种 Microsoft 365 应用程序与第三方软件定义的网络 (SD-WAN) 解决方案集成，以优化和改进与 Microsoft 服务终结点的网络连接。 优化的 SD-WAN 连接可能会改进用户体验和性能。

## <a name="overview"></a>概述

智能网络路由在 Microsoft 和 SD-WAN 解决方案之间提供双向数据共享通道。 对于您配置的每个办公室位置和 Internet 线路，Microsoft 会定期与 SD-WAN 解决方案共享有关与每个特定 Internet 线路关联的网络流量的选定 Microsoft 365 应用程序体验质量的反馈。 使用此反馈，SD-WAN 解决方案随后可以通过通过备用可用链接Microsoft 365应用程序流量执行智能恢复操作。 

很难持续检测特定 Internet 线路的服务质量下降，如延迟增加或数据包丢失率高。 这些降级可能会对应用程序（如应用程序、Exchange Online、SharePoint、OneDrive 和 Microsoft Teams）的用户体验产生不利影响。 常见症状包括搜索内容Exchange、与 SharePoint 或 OneDrive 文档库交互时传输时间长，或呼叫或会议质量Microsoft Teams。

通知网络路由中的反馈和恢复机制旨在动态地实时检测此类问题，并通知部署的 SD-WAN 解决方案执行自动恢复操作。

数据共享通道还用于定期接收来自 SD-WAN 解决方案的网络级光学数据，包括与设备和连接的电路关联的配置信息和使用情况统计信息。 不收集或存储任何个人信息。 收集的所有信息将聚合到办公室位置和连接的 Internet 线路。 此信息可帮助 Microsoft 更有效地解决报告的有关使用 Microsoft 365 服务和应用程序的问题。

>[!NOTE]
>Microsoft 365网络路由支持 WW 商业云中的租户，但GCC中等、GCC高、DoD、德国或中国云。

## <a name="requirements"></a>要求

### <a name="integrated-sd-wan-solutions"></a>集成 SD-WAN 解决方案

Microsoft 正在与各种合作伙伴合作，以便能够与Microsoft 365网络路由集成。 当前启用的解决方案包括：

| Device Maker | 解决方案名称 | 最低版本 |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>网络拓扑 

通知网络路由当前基于用于向 Microsoft 发送网络流量的公共 IP 地址识别与特定办公地点和 Internet 线路关联的流量。 

如果分支位置没有至少一个提供直接 Internet 访问的网络电路，则通知网络路由可能不会提供显著价值。

### <a name="application-usage"></a>应用程序使用情况

应用程序体验 (通过网络质量指标) 通过特定 Microsoft 客户端应用程序进行收集。 Exchange指标反映 Outlook 客户端的使用情况，以及一些Outlook Web App使用情况。 SharePoint和OneDrive指标反映租户特定终结点SharePoint的使用情况，而不考虑客户端应用程序。 Teams指标反映桌面客户端Teams使用情况。 在评估网络线路的运行状况时，不会考虑其他应用程序流量。

## <a name="enabling-informed-network-routing"></a>启用智能网络路由

启用智能网络路由需要多个步骤，其中一些步骤需要在 SD-WAN 解决方案的配置接口内执行。 有关如何启动在 SD-WAN 解决方案中启用明智网络路由的过程的指导，请咨询您的 SD-WAN 解决方案供应商，然后再继续 Microsoft 365 管理中心。

准备好在服务器中启用通知网络路由Microsoft 365 管理中心，请确保你 **拥有必要的用户** 管理员或 **全局管理员** 权限。

>[!IMPORTANT]
>为了向选定的 SD-WAN 解决方案提供必要的租户级应用程序权限同意以访问通知的网络路由数据共享通道，必须以全局管理员角色执行以下步骤。


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步骤 1：打开 SD-WAN 解决方案配置选项

In the [Microsoft 365 管理中心](https://admin.microsoft.com/)， select **Health > Network connectivity** in the left-hand navigation pane.

管理中心的这一部分为组织提供了聚合的网络连接指标，并指导如何提高连接性。 有关[管理中心内Microsoft 365 管理](office-365-network-mac-perf-overview.md)功能的其他信息，请参阅 Microsoft 365 管理 中心中的网络连接。

选择 **设置 > SD-WAN 解决方案"** 以打开通知网络路由配置窗格。 设置下显示的其他选项适用于管理中心中的一般网络连接指南，不需要这些选项来启用明智的网络路由。

在配置窗格中，选择 **"添加 SD-WAN 解决方案"。**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>步骤 2：选择 SD-WAN 解决方案和数据存储位置

在下拉框中，选择已部署的 SD-WAN 解决方案以及要存储与通知网络路由关联的数据的位置。 有关 [其他信息，](#data-storage) 请参阅数据存储部分。

选择 **下一步**。

### <a name="step-3-accept-terms-for-sharing-of-data"></a>步骤 3：接受数据共享条款

仔细阅读并确认提供的与在 Microsoft 和所选 SD-WAN 解决方案之间共享数据相关的条款，然后选中指示的复选框。

选择 **下一步**。

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>步骤 4：向 SD-WAN 解决方案授予权限

此步骤将启动向用户授予权限Azure Active Directory (Azure AD) 。 将请求你授予租户级别权限，以允许所选 SD-WAN 解决方案访问与租户关联的通知网络路由数据存储和服务运行状况信息。 此操作需要 **Azure AD DC 管理员或****全局管理员** 角色权限。

选择"**向此应用程序授予权限"** 链接，然后按照Azure AD操作。

完成权限授予后，选择"下一 **步"。**

### <a name="step-5-confirm-your-configuration-settings"></a>步骤 5：确认配置设置

为租户启用通知网络路由的最后一步是显示你提供的设置的确认页面。 

现在已为租户启用智能网络路由。

选择 **"** 完成"，然后关闭 SD-WAN 解决方案配置窗格。

## <a name="configuring-informed-network-routing"></a>配置智能网络路由

您将对 SD-WAN 解决方案中的明智网络路由执行大部分配置，例如配置在正常情况下应该如何路由流量，以及检测到问题时应该使用的备用路径。 有关这些配置步骤的详细信息，请咨询您的 SD-WAN 解决方案提供商。

每个办公室位置都必须在服务器配置Microsoft 365 管理中心以便通知网络路由可以正确识别与提供这些位置连接的网络电路相关的流量。

Office位置可能会自动检测为 Microsoft 正在进行的网络遥测集合的一部分。 因此，某些位置可能会预先填充在租户的管理中心中。 

如果这些位置准确，则只需为每个所需位置启用通知网络路由功能，并配置 Internet 线路及其公用 IP 地址。 

如果自动检测的位置不准确，或者租户中没有预填充的位置，必须手动添加或编辑位置，以反映组织的准确拓扑。

### <a name="updating-locations"></a>更新位置

可以在"位置"选项卡下找到 **租户的位置。** 可以直接在列表中编辑位置，也可以使用 CSV 文件更新位置。

确保要启用通知网络路由的每个办公室位置都位于此列表中。

>[!NOTE]
>收集的示例 **和其他** 与评估有关的信息的"位置"列表中的列与通知网络路由功能不相关。

### <a name="enabling-a-location-for-informed-network-routing"></a>为智能网络路由启用位置

1. 在"**位置"列表中**，从快速操作菜单中选择"编辑"以打开位置配置窗格。

2. 在此 **位置Microsoft 365使用通知网络路由**。

3. 将提供 Internet 连接的所有网络电路添加到此办公地点部分Egress **IP 地址范围** 中。 确保每个电路与代表网络流量的唯一公用 IP 地址子网关联。

4. 选择“**保存**”以保存所做的更改。

## <a name="disabling-informed-network-routing"></a>禁用通知网络路由

通过重置 SD-WAN 解决方案设置，可能会为整个租户禁用通知网络路由功能。 虽然这将停止对管理中心内的所有Microsoft 365，但还应禁用管理中心内的通知网络路由。

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>步骤 1：打开 SD-WAN 解决方案配置选项

In the [Microsoft 365 管理中心](https://admin.microsoft.com/)select **Health > Network connectivity** in the left-hand navigation pane.

选择 **设置 > SD-WAN 解决方案"** 以打开通知网络路由配置窗格。

配置窗格显示当前配置的 SD-WAN 解决方案的摘要。

### <a name="step-2-reset-your-configuration"></a>步骤 2：重置配置

在配置窗格中，选择"**重置 SD-WAN 解决方案设置"。**

您的设置现已重置，并且已禁用通知网络路由。 可以按照启用通知网络路由 中的步骤随时 [重新启用它](#enabling-informed-network-routing)。

## <a name="data-storage"></a>数据存储

在 Microsoft 与 SD-WAN 解决方案提供商之间交换的数据存储在初始启用通知网络路由期间所选的数据存储位置。 数据存储位置选项表示包含存储Microsoft Azure区域的地理区域。

数据将在此位置保留最多 30 天。 禁用后，将在此 30 天的保留时段内删除所有剩余数据。

此位置的数据与选定的 SD-WAN 解决方案进行交换，配置的 SD-WAN 解决方案的位置可能不在同一区域。 客户应与客户的 SD-WAN 解决方案提供商合作，在生产部署之前评估任何数据存储位置要求。

## <a name="related-topics"></a>相关主题

[网络连接Microsoft 365 管理中心](office-365-network-mac-perf-overview.md)

[Microsoft 365网络连接位置服务](office-365-network-mac-location-services.md)
