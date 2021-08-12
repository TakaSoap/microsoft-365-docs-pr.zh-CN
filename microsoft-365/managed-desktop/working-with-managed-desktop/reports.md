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
ms.openlocfilehash: 8116d5d1caaa24951ad9baf9e291bf3fd850abfbe7ae2402022f8fafcf883673
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53834595"
---
# <a name="work-with-reports"></a>处理报告

Microsoft Endpoint Manager控制台将多个产品的报告汇集到一个位置，帮助你监视和调查 Azure AD 组织（"租户 (配置和设备) 问题。 Microsoft 托管桌面的"报告"菜单中有一个部分，可在其中查找特定于Microsoft 托管桌面注册设备的管理的报告。 此外，你可以在整个 Microsoft Endpoint Manager 多个位置筛选来自其他产品组的报告，以专门包含或排除由 Microsoft 托管桌面 管理的设备。 

## <a name="microsoft-managed-desktop-reports"></a>Microsoft 托管桌面报告
Microsoft 托管桌面提供了几个报告和仪表板，您的组织中的 IT 管理员可以使用这些报表和仪表板了解设备数量的各个方面。可以通过导航到"报告"菜单的"托管 *Microsoft 托管桌面下找到***这些报告Microsoft Endpoint Manager。** 

在 **摘要选项卡** 上，你将找到有关设备更新的快速指标。 选择 **"查看** 任何指标的详细信息"将允许您下载其他信息进行脱机分析，包括指标的基础数据集。

选择"报告 **"** 选项卡时，将看到可用详细报告的说明。 这些报告更为全面，支持在门户中可视化和筛选数据，以及导出基础数据进行脱机分析或分发。 以下报告现在可用：
- 设备 **状态***(预览)* 根据设备活动和使用情况Microsoft 托管桌面服务使用情况。 
- 可以使用 **设备状态***趋势 (预览*) 来监视过去 60 天内你的设备设备状态Microsoft 托管桌面趋势。 趋势可以帮助你将设备状态与其他更改关联，例如新部署。 
- Windows **安全更新 (***预览*) 显示Windows跨设备发布安全更新Microsoft 托管桌面的信息。

> [!NOTE]
> 预览 *(中的)* 我们基于在公共预览期间收到的反馈进行改进，因此可以在有限通知下更改报告。

## <a name="endpoint-analytics"></a>终结点分析
Microsoft 托管桌面现在与[Endpoint Analytics 集成](/mem/analytics/overview)。 这些报告可让你深入了解如何衡量组织的运行方式以及为用户提供的体验质量。 终结点分析位于终结点 **分析的"** 报告 ["Microsoft Endpoint Manager。](https://endpoint.microsoft.com/) 若要透视分数以仅包含由管理的设备Microsoft 托管桌面转到任何报告，请选择"筛选器"下拉列表，然后选择"Microsoft 托管桌面 **设备"。** 

如果在注册期间未自动为 Azure AD ("租户") 配置终结点分析，可以自己执行。 有关详细信息，请参阅终结点 [分析门户中的载入](/mem/analytics/enroll-intune#bkmk_onboard)。 你可以注册所有设备，或者，如果你希望仅包括Microsoft 托管桌面设备，请为"测试"、第一个、"快速"和"广泛"选择现代工作区设备组。 这些报告可能需要不同的权限。 有关详细信息，请参阅 [确保](/mem/analytics/overview#permissions) 正确分配角色的权限。

> [!NOTE]
> 为了更好地尊重隐私用户隐私，必须Microsoft 托管桌面终结点分析的设备使用此筛选器。

## <a name="intune-reports"></a>Intune 报告
Microsoft Intune我们用于代表你管理设备的服务之一。 在某些情况下，使用 Intune 报告专门监视对设备管理Microsoft 托管桌面很有用。 或者你可能希望从用于管理其他设备的报告中排除我们管理的设备。 通过以下报告，你可以筛选功能以包含或排除Microsoft 托管桌面设备。

- [所有设备](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [设备合规性](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [不符合要求的设备](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 自定义Microsoft 托管桌面角色保证仅访问Microsoft 托管桌面报告。 若要访问其他Microsoft Endpoint Manager，如所有 **设备**，请参阅基于角色的访问控制 [和](/mem/intune/fundamentals/role-based-access-control)Microsoft Intune。 

## <a name="microsoft-managed-desktop-inventory-data"></a>Microsoft 托管桌面清单数据

除了其他报告之外，还可以导出有关由设备管理的设备Microsoft 托管桌面。 在 **"设备"** 视图中的"设备"Microsoft Endpoint Manager，使用"导出所有"选项卡 [下载详细的清单报告](device-inventory-report.md)。
