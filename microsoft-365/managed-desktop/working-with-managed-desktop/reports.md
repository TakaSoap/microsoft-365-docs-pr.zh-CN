---
title: 处理报告
description: 各种报告Microsoft 托管桌面
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771881"
---
# <a name="work-with-reports"></a>处理报告

Microsoft 托管桌面提供了几个报告和仪表板，您的组织中的 IT 管理员可以使用这些报表和仪表板了解设备数量的各个方面。 

## <a name="reports-in-microsoft-endpoint-manager"></a>报告Microsoft Endpoint Manager

Microsoft Endpoint Manager控制台将多个产品的报告汇集到一个位置，帮助你监视和调查 Azure AD 组织（"租户 (配置和设备) 问题。 Microsoft 托管桌面在主菜单中的"报告"下有一个部分，你可以找到特定于Microsoft 托管桌面注册设备的管理的报告。

这些报告包括：
- **托管设备**  > **功能更新**：此视图显示跨设备更新功能Microsoft 托管桌面状态。
- **托管设备**  > **Office更新**： 此视图显示跨 Office 设备更新Microsoft 托管桌面状态。

此外，你可以在整个 Microsoft Endpoint Manager 多个位置筛选来自其他产品组的报告，以专门包含或排除由 Microsoft 托管桌面 管理的设备。 这些报告集成了此筛选功能：

- [所有设备](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [设备合规性](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [不符合要求的设备](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 自定义Microsoft 托管桌面角色保证仅访问Microsoft 托管桌面报告。 若要访问其他Microsoft Endpoint Manager，如所有 **设备**，请参阅基于角色的访问控制 [和](/mem/intune/fundamentals/role-based-access-control)Microsoft Intune。 

## <a name="endpoint-analytics"></a>终结点分析
Microsoft 托管桌面现在与[Endpoint Analytics 集成](/mem/analytics/overview)。 这些报告可让你深入了解如何衡量组织的运行方式以及为用户提供的体验质量。 终结点分析位于终结点 **分析的"** 报告 ["Microsoft Endpoint Manager。](https://endpoint.microsoft.com/) 若要透视分数以仅包含由管理的设备Microsoft 托管桌面转到任何报告，请选择"筛选器"下拉列表，然后选择"Microsoft 托管桌面 **设备"。** 

如果在注册期间未自动为 Azure AD ("租户") 配置终结点分析，可以自己执行。 有关详细信息，请参阅终结点 [分析门户中的载入](/mem/analytics/enroll-intune#bkmk_onboard)。 你可以注册所有设备，或者如果你希望仅包括Microsoft 托管桌面，请为"测试"、第一个、"快速"和"广泛"选择现代工作区设备组。 这些报告可能需要不同的权限。 有关详细信息，请参阅 [确保](/mem/analytics/overview#permissions) 正确分配角色的权限。

> [!NOTE]
> 为了更好地尊重隐私用户隐私，必须Microsoft 托管桌面终结点分析的设备使用此筛选器。

 ## <a name="inventory-data"></a>清单数据

除了其他报告之外，还可以导出有关由设备管理的设备Microsoft 托管桌面。 在 **"设备"** 视图中的"设备"Microsoft Endpoint Manager，使用"导出所有"选项卡 [下载详细的清单报告](device-inventory-report.md)。
