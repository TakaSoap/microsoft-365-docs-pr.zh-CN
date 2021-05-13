---
title: Microsoft 365网络连接位置服务
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365网络连接位置服务
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470444"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365网络连接位置服务

管理Microsoft 365中心现在显示 **Network Insights** 和性能建议，这些建议是实时性能指标，收集自你的 Microsoft 365 租户。 这些指标仅能由租户中的管理用户查看。 组织网络连接是通过网络出口位置到 Internet 按办公室位置设计的。 Microsoft 365客户端连接使用该路由，然后通过 Internet 连接到 Microsoft 服务前端服务器。 标识办公地点是显示这些网络见解的关键。

## <a name="location-in-network-measurements"></a>网络测量中的位置

组织的管理员可以选择将位置包含在此功能所使用的网络度量中。 这允许自动发现每个办公室所在的城市。 位置信息并不精确，并模糊处理为 300m，并按城市分类。 在设备上捕获位置Windows时，设备将在工具托盘中显示"位置使用中"图标。  管理员可能需要通知用户此图标的外观。 通过此处理，该位置将被视为组织办公地点，而不是人员或设备的位置。 可以在这些发现的办公地点城市显示网络见解。 如果希望建议的准确性更高，可以输入特定的办公地点地址。 网络见解将聚合到这些位置。 Office聚合的位置不能超过 300 米。

## <a name="location-in-the-microsoft-365-admin-center"></a>管理中心Microsoft 365位置

在Microsoft 365中心，必应地图控件来显示组织办公地点。 这些控件还显示选定办公地点的网络外围拓扑。 当管理员为办公地点添加特定地址详细信息时，必应地图还用于建议地址，以便更轻松地输入数据。

## <a name="terms-of-use"></a>使用条款

通过网站必应地图（包括地理代码）只能在提供内容的产品内使用。 客户对 Microsoft 365 管理中心位置服务功能（由 必应地图 支持）的使用受 必应地图 End-User _使用条款_ 和 <https://go.microsoft.com/?linkid=9710837> Microsoft [隐私声明的约束](https://go.microsoft.com/fwlink/?LinkID=248686)。

此功能通过 必应地图，也受 **TomTom 支持**。 有关 TomTom 产品和服务的更多信息，请参阅 [https://www.tomtom.com/legal](https://www.tomtom.com/legal) 。

## <a name="related-topics"></a>相关主题

[Microsoft 365 管理中心 (预览) ](office-365-network-mac-perf-overview.md)

[Microsoft 365预览版 (网络性能) ](office-365-network-mac-perf-insights.md)

[Microsoft 365网络评估 (预览) ](office-365-network-mac-perf-score.md)

[Microsoft 365管理中心中Microsoft 365预览 (连接) ](office-365-network-mac-perf-onboarding-tool.md)
