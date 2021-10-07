---
title: 使用报表
description: 各种报告Microsoft 托管桌面
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1fb29ef7555bb3e7ff2024090b3b7cf953a2de10
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213165"
---
# <a name="work-with-reports"></a>使用报表

该Microsoft Endpoint Manager控制台将来自多个产品的报告汇集到一个位置，帮助你监视和调查 Azure AD 组织（"租户 (配置和设备) 问题。 Microsoft 托管桌面的"报告"菜单中有一个部分，可在其中查找特定于Microsoft 托管桌面注册设备的管理的报告。 此外，你可以在整个 Microsoft Endpoint Manager 多个位置筛选来自其他产品组的报告，以明确包括或排除由 Microsoft 托管桌面 管理的设备。 

## <a name="microsoft-managed-desktop-reports"></a>Microsoft 托管桌面报告
Microsoft 托管桌面提供了几个报表和仪表板，您的组织中的 IT 管理员可以使用这些报表和仪表板来了解设备数量的各个方面。可以通过导航到"报告"菜单的"Microsoft 托管桌面"部分下的 *"托管* 设备 **"来查找** Microsoft Endpoint Manager。 

在 **摘要选项卡** 上，你将找到有关设备更新的快速指标。 选择 **"查看** 任何指标的详细信息"将允许您下载其他信息进行脱机分析，包括指标的基础数据集。

选择"报告 **"** 选项卡时，将看到可用详细报告的说明。 这些报告更为全面，支持在门户中可视化和筛选数据，以及导出基础数据进行脱机分析或分发。 以下报告现在可用：
- 预览 [**版** (设备](device-status-report.md)状态) 根据设备活动和使用情况Microsoft 托管桌面服务使用情况。 
- 在 **预览版** 中， (设备 *状态趋势)* 监视过去 60 天内设备状态趋势Microsoft 托管桌面设备。 趋势可以帮助你将设备状态与其他更改（例如，新部署）关联。 
- 预览 [**Windows安全更新 (**](security-updates-report.md)显示) 跨 Windows 设备发布安全更新Microsoft 托管桌面的信息。
- 应用程序 **使用情况报告** 提供有关跨设备应用的典型Microsoft 托管桌面的信息。 对于向此报告提供数据的设备，必须设置为可选诊断数据级别。

## <a name="endpoint-analytics"></a>终结点分析
Microsoft 托管桌面现在与[Endpoint Analytics 集成](/mem/analytics/overview)。 这些报告可让你深入了解如何衡量组织的运行方式以及为用户提供的体验质量。 终结点分析位于终结点 **分析的"** 报告 ["Microsoft Endpoint Manager。](https://endpoint.microsoft.com/) 若要透视分数以仅包含由托管设备Microsoft 托管桌面转到任何报告，请选择"筛选器"下拉列表，然后选择"Microsoft 托管桌面 **设备"。**

如果注册期间未自动为 Azure AD ("租户") 配置终结点分析，可以自己执行。 有关详细信息，请参阅终结点 [分析门户中的载入](/mem/analytics/enroll-intune#bkmk_onboard)。 你可以注册所有设备，或者，如果你希望仅包括Microsoft 托管桌面，请为"测试"、第一个、"快速"和"广泛"选择现代工作区设备组。 这些报告可能需要不同的权限。 有关详细信息，请参阅 [权限](/mem/analytics/overview#permissions) 以确保正确分配了角色。

> [!NOTE]
> 为了更好地尊重用户隐私，必须有 10 Microsoft 托管桌面注册终结点分析的设备使用此筛选器。

## <a name="intune-reports"></a>Intune 报表
Microsoft Intune我们用于代表你管理设备的服务之一。 在某些情况下，使用 Intune 报告专门监视对设备管理Microsoft 托管桌面很有用。 或者你可能希望从用于管理其他设备的报告中排除我们管理的设备。 通过以下报告，你可以筛选功能以包含或排除Microsoft 托管桌面设备。

- [所有设备](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [设备合规性](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [不符合要求的设备](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 自定义Microsoft 托管桌面角色保证仅访问Microsoft 托管桌面报告。 若要访问其他Microsoft Endpoint Manager，如所有 **设备**，请参阅基于角色 [的访问控制和](/mem/intune/fundamentals/role-based-access-control)Microsoft Intune。 

## <a name="microsoft-managed-desktop-inventory-data"></a>Microsoft 托管桌面清单数据

除了其他报告之外，还可以导出有关由设备管理的设备Microsoft 托管桌面。 在 **"设备"** 视图中的"设备"Microsoft Endpoint Manager，使用"导出所有"选项卡 [下载详细的清单报告](device-inventory-report.md)。
