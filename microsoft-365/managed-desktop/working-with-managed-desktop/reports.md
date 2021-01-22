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
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921346"
---
# <a name="work-with-reports"></a>处理报告

Microsoft 托管桌面提供了多个报表和仪表板，你的组织中 IT 管理员可以使用这些报表和仪表板来了解设备数量的各个方面。你将在两个位置找到报告 [：Microsoft Endpoint Manager](https://endpoint.microsoft.com) 和 Microsoft [365 管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager 中的报告

Microsoft Endpoint Manager 控制台将多个产品的报告汇集到一个位置，帮助你监视和调查 Azure AD 组织 ("租户") 和设备的问题。 Microsoft 托管桌面在主菜单中的"报告"下有一部分，您可以在其中找到特定于 Microsoft 托管桌面对已注册设备的管理的报告。

这些报告包括：
- **托管设备**  > **功能更新**：此视图显示整个 Microsoft 托管桌面设备中的功能更新的总体状态。
- **托管设备**  > **Office 更新**：此视图显示 Microsoft 托管桌面设备中的 Office 更新的总体状态。

此外，可以在 Microsoft Endpoint Manager 中的多个位置筛选来自其他产品组的报表，以专门包含或排除由 Microsoft 托管桌面管理的设备。 这些报告集成了此筛选功能：

- [所有设备](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [设备合规性](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [不符合要求的设备](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 自定义 Microsoft 托管桌面角色保证仅访问 Microsoft 托管桌面报告。 若要访问 Microsoft Endpoint Manager 的其他部分（如所有设备），请参阅[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)中的基于角色的访问控制。 

## <a name="reports-in-microsoft-365-admin-center"></a>Microsoft 365 管理中心中的报告

可以通过打开 Microsoft [365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)管理中心，然后导航到"报表"并选择 **"Microsoft** 托管桌面"来查找 Microsoft 托管桌面见解报告。 也可以按照从主页 **上的 Microsoft** 托管桌面选项卡上的 Microsoft Endpoint Manager 直接链接到 [这些报告](https://endpoint.microsoft.com)。 

这些报告包括： 

- [使用情况见解](usage-insights.md) - 此视图提供 Microsoft 托管桌面设备的使用指标。
- [可靠性见解](reliability-insights.md) - 此视图为您提供托管设备的运行状况摘要。
- [电池见解](battery-insights.md) - 此视图显示有关应用中的能耗和环境中设备预计电池使用时间的信息。
- [Windows 安全更新见解](security-update-insights.md) - 此视图显示有关 Microsoft 托管桌面设备安全更新状态的信息。

 ## <a name="inventory-data"></a>清单数据

除了其他报告外，还可以导出有关由 Microsoft 托管桌面管理的设备的信息。 在Microsoft Endpoint Manager的"设备"区域中的"设备"视图中，使用"导出所有 **"选项卡**[下载详细的清单报告](device-inventory-report.md)。
