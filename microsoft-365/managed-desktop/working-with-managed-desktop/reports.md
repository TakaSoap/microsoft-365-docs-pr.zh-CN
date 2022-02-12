---
title: 处理报告
description: 各种报告Microsoft 托管桌面
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: f37a02c8cda29f48f926125f353d5e75410d9ab5
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765488"
---
# <a name="work-with-reports"></a>处理报告

Microsoft Endpoint Manager控制台将多个产品的报告汇集到一个位置，以帮助你监视和调查 Azure AD 组织 ("租户") 配置和设备的问题。

Microsoft 托管桌面"报告"菜单中的一个部分，可在其中查找特定于注册Microsoft 托管桌面管理的报告。 在整个产品组的多个Microsoft Endpoint Manager，您可以筛选来自其他产品组的报告。 你可以包括或排除由设备管理的设备Microsoft 托管桌面。

## <a name="microsoft-managed-desktop-reports"></a>Microsoft 托管桌面报告

Microsoft 托管桌面提供了多个报表和仪表板。 贵组织中 IT 管理员可使用这些报告和仪表板了解设备总体的各个方面。 In Microsoft Endpoint Manager， navigate to the Reports section， under Microsoft 托管桌面， select Managed devices.

在 **摘要选项卡** 中，你将找到有关设备更新的快速指标。 选择 **"查看** 任何指标的详细信息"以下载其他信息进行脱机分析，包括指标的基础数据集。

选择"报告 **"** 选项卡时，将看到可用详细报告的说明。 这些报告更加全面，并支持门户中的数据可视化和筛选。 还可以导出基础数据进行脱机分析或分发。 以下报告现在可用：

| 报告 | 说明 |
| ------ | ------ |
| [**预览版** (](device-status-report.md)*设备状态*)  | 此报表显示你根据设备Microsoft 托管桌面使用情况使用服务。 |
| **预览版 (***设备状态*)  | 这将监视过去 60 天内你的设备在设备Microsoft 托管桌面趋势。 趋势可以帮助你将设备状态与其他更改关联，例如新部署。 |
| [**Windows预览版中** (](security-updates-report.md)*安全更新)* | 此报表显示Windows设备中发布安全更新Microsoft 托管桌面更新。 |
| [**应用程序使用情况** 报告](app-usage-report.md) | 此报告提供有关跨设备应用的典型Microsoft 托管桌面的信息。 对于向此报告提供数据的设备，必须设置为可选诊断数据级别。 |
| **预览版 (***服务指标)* | 此报告提供每月关键指标Microsoft 托管桌面简单明了的摘要。 |

## <a name="endpoint-analytics"></a>终结点分析

Microsoft 托管桌面现在与 [Endpoint Analytics 集成](/mem/analytics/overview)。 这些报告可让你深入了解如何衡量组织的运行方式以及为用户提供的体验质量。 可以在"终结点分析"菜单的"**报告"菜单中** 找到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)。 若要透视分数以仅包含由 Microsoft 托管桌面 管理的设备，请转到任何报告，选择"筛选器"下拉列表，然后选择"Microsoft 托管桌面 **设备"**。

如果在注册期间未自动为 Azure AD组织 (") "租户"配置终结点分析，可以自己执行。 有关详细信息，请参阅终结点 [分析门户中的载入](/mem/analytics/enroll-intune#bkmk_onboard)。 你可以注册所有设备，或者，如果你希望仅包括 Microsoft 托管桌面设备，请为"测试"、第一个、"快速"和"广泛"选择现代工作区设备组。 这些报告可能需要不同的权限。 有关详细信息，请参阅 [权限](/mem/analytics/overview#permissions) 以确保正确分配了角色。

> [!NOTE]
> 为了更好地尊重用户隐私，必须有 10 Microsoft 托管桌面终结点分析注册的设备使用此筛选器。

## <a name="intune-reports"></a>Intune 报表

Microsoft Intune我们用于代表你管理设备的服务之一。

在某些情况下，使用 Intune 报告专门监视对设备管理Microsoft 托管桌面很有用。 你可以从用于管理其他设备的报告中排除我们管理的设备。 通过以下报告，你可以筛选功能以包含或排除Microsoft 托管桌面设备。

- [所有设备](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [设备合规性](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [不合规的设备](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 自定义Microsoft 托管桌面角色保证仅访问Microsoft 托管桌面报告。 若要访问其他Microsoft Endpoint Manager（如所有设备）**的信息**，请参阅基于角色 [的](/mem/intune/fundamentals/role-based-access-control)访问控制和Microsoft Intune。

## <a name="microsoft-managed-desktop-inventory-data"></a>Microsoft 托管桌面清单数据

除了其他报告之外，还可以导出有关由设备管理的设备Microsoft 托管桌面。 In Microsoft Endpoint Manager， navigate to the **Devices** section， under Microsoft 托管桌面， select **Devices** and use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).
