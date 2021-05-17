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
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917678"
---
# <a name="work-with-reports"></a>处理报告

Microsoft 托管桌面提供了几个报告和仪表板，您的组织中的 IT 管理员可以使用这些报表和仪表板了解设备数量的各个方面。你将在两个位置找到报告：在 Microsoft Endpoint Manager[和](https://endpoint.microsoft.com)Microsoft 365[管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)中。 

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

## <a name="reports-in-microsoft-365-admin-center"></a>管理中心Microsoft 365报告

可以通过打开Microsoft 托管桌面管理中心，然后导航Microsoft 365报告并选择"报告[](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)"，Microsoft 托管桌面。  您还可以从主页上的"主页"选项卡 **Microsoft 托管桌面这些报告的直接**[Microsoft Endpoint Manager。](https://endpoint.microsoft.com) 

这些报告包括： 

- [使用情况见解](usage-insights.md)- 此视图为设备Microsoft 托管桌面指标。
- [可靠性见解](reliability-insights.md) - 此视图提供托管设备的运行状况摘要。
- [电池见解](battery-insights.md) - 此视图显示有关应用能耗和环境中设备预计电池使用时间的信息。
- [Windows安全更新见解](security-update-insights.md)- 此视图显示有关你的设备安全更新Microsoft 托管桌面的信息。

 ## <a name="inventory-data"></a>清单数据

除了其他报告之外，还可以导出有关由设备管理的设备Microsoft 托管桌面。 在 **"设备"** 视图中的"设备"Microsoft Endpoint Manager，使用"导出所有"选项卡 [下载详细的清单报告](device-inventory-report.md)。