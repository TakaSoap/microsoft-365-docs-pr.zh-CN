---
title: 处理报告
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bfd8305d23e0e6d761c629ee3048c6204f702d37
ms.sourcegitcommit: 98146c67a1d99db5510fa130340d3b7be8d81b21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "49585324"
---
# <a name="work-with-reports"></a>处理报告

Microsoft 托管桌面提供了多个报告和仪表板，贵组织中的 IT 管理员可以使用它来了解设备填充的各个方面。你可以在两个位置找到报告：在 [Microsoft 终结点管理器](https://endpoint.microsoft.com) 和 [microsoft 365 管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)中。 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft 终结点管理器中的报告

Microsoft 终结点管理器控制台将多个产品的报告汇集到一个位置，以帮助您监视和调查 Azure AD 组织 ( "租户" ) 配置和设备的问题。 Microsoft 托管桌面的主菜单中有一个 " **报告** " 部分，您可以在其中查找特定于 Microsoft 托管桌面管理的已注册设备的报告。

此外，在 Microsoft 终结点管理器的多个位置，您可以从其他产品组筛选报告，以专门包含或排除由 Microsoft 托管桌面管理的设备。 这些报告集成了此筛选功能：

- **所有设备**
- **设备合规性**
- **不符合设备**

> [!NOTE]
> 自定义 Microsoft 托管桌面角色可保证仅访问 Microsoft 托管桌面报告。 若要访问 Microsoft 终结点管理器（如 **所有设备**）的其他部分，请参阅 [基于角色的访问控制与 microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。 

## <a name="reports-in-microsoft-365-admin-center"></a>Microsoft 365 管理中心中的报告

您可以通过打开 [microsoft 365 管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)，导航到 " **报表** " 并选择 " **microsoft 托管桌面**" 来查找 microsoft 托管的桌面洞察力报告。 您还可以在主页 [Microsoft 终结点管理器](https://endpoint.microsoft.com)上的 " **Microsoft 托管桌面**" 选项卡上跟踪这些报告的直接链接。 

这些报告包括： 

- [Usage insights](usage-insights.md) -此视图提供 Microsoft 托管桌面设备的使用指标。
- [可靠性见解](reliability-insights.md) -此视图为你提供托管设备的运行状况摘要。
- [电池洞察力](battery-insights.md) -此视图显示有关您的环境中的设备的应用和计划电池寿命的信息。
- [Windows 安全更新见解](security-update-insights.md) -此视图显示有关 Microsoft 托管桌面设备的安全更新状态的信息。

 ## <a name="inventory-data"></a>清单数据

除了其他报告之外，您还可以导出由 Microsoft 托管桌面管理的设备的相关信息。 在 Microsoft 终结点管理器的 "**设备**" 区域的 "**设备**" 视图中，使用 "**全部导出**" 选项卡 [下载详细的清单报告](device-inventory-report.md)。