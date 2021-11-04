---
title: 数据丢失防护警报仪表板入门
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: 开始定义和管理数据丢失防护策略的警报。
ms.openlocfilehash: 442929df84508d99ee9ae3d88bc2297e293ecc73
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747338"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>数据丢失防护警报仪表板入门

DLP 策略 (数据丢失) 采取保护措施，防止意外共享敏感项目。 对敏感项目采取操作时，可以通过配置 DLP 警报来通知您。 本文演示如何定义与 DLP 策略或 DLP 策略的数据丢失防护 (警报) 策略。 你将看到如何使用仪表板中的[DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)警报管理Microsoft 365 合规中心查看 DLP 策略违反的<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">警报</a>、事件和关联元数据。

如果您是 DLP 警报的新增用户，则应该查看了解数据丢失防护 [警报仪表板](dlp-alerts-dashboard-learn.md)

## <a name="before-you-begin"></a>准备工作

在开始之前，请确保你具有必要的先决条件：

-   DLP 警报管理仪表板的许可
-   警报配置选项的许可
-   角色

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP 警报管理仪表板的许可

DLP 的所有符合条件的租户Office 365 DLP 警报管理仪表板。 若要开始，你应该有资格使用 Office 365 DLP Exchange Online SharePoint Online 和 OneDrive for Business。 有关 DLP 的许可要求Office 365，请参阅哪些许可证为用户提供从服务中获益[的权利？。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)

使用符合[使用 DLP](endpoint-dlp-learn-about.md)条件Teams [DLP](dlp-microsoft-teams.md)的客户将在 DLP 警报管理仪表板中查看其Teams DLP 策略警报和 DLP 策略警报。

内容 **预览** 功能仅适用于以下许可证：

- Microsoft 365 (E5)
- Office 365 (E5)
- 高级合规性 (E5) 加载项
- Microsoft 365 E5/A5 信息保护和治理
- Microsoft 365 E5/A5 合规

### <a name="licensing-for-alert-configuration-options"></a>警报配置选项的许可

**单事件警报** 配置：拥有 E1、F1 或 G1 订阅、E3 或 G3 订阅的组织只能在每次活动发生时触发警报时创建警报策略。

**聚合警报配置**：若要根据阈值配置聚合警报策略，您必须以下许可配置之一：

- E5 或 G5 订阅
- 包含以下功能之一的 E1、F1 或 G1 订阅或 E3 或 G3 订阅：
    - Office 365 高级威胁防护（计划 2）
    - Microsoft 365 E5 合规
    - Microsoft 365电子数据展示和审核加载项许可证

### <a name="roles"></a>角色


如果要查看 DLP 警报管理仪表板或编辑 DLP 策略中的警报配置选项，您必须是以下角色组之一的成员：

- 合规管理员
- 合规数据管理员
- 安全管理员
- 安全操作员
- 安全信息读取者

若要访问 DLP 警报管理仪表板，您需要：

- 管理警报

以及以下两个角色之一：

- DLP 合规性管理
- View-Only DLP 合规性管理

若要访问内容预览功能和匹配敏感内容和上下文功能，你必须是以下组的成员：

- 内容资源管理器内容查看器角色组

已预分配数据分类内容查看器角色。

## <a name="dlp-alert-configuration"></a>DLP 警报配置

若要了解如何在 DLP 策略中配置警报，请参阅从数据丢失防护[开始。](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)

### <a name="aggregate-event-alert-configuration"></a>聚合事件警报配置

如果您的组织已获得 [聚合警报配置](#licensing-for-alert-configuration-options)选项的许可，则当您创建或编辑 DLP 策略时，将看到这些选项。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for aggregated alert configuration options." border="false":::

通过此配置，您可以设置一个策略，以在活动符合策略条件或超出特定阈值时（基于活动数或根据已过滤数据的量）生成警报。

### <a name="single-event-alert-configuration"></a>单个事件警报配置

如果您的组织已获得单事件 [警报](#licensing-for-alert-configuration-options)配置选项的许可，则创建或编辑 DLP 策略时将看到这些选项。 使用此选项可创建每次发生 DLP 规则匹配时都会触发的警报。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for single-event alert configuration options." border="false":::

## <a name="investigate-a-dlp-alert"></a>调查 DLP 警报

使用 DLP 警报管理仪表板：

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心，</a>go to **Data Loss Prevention**.
2. 选择" **警报"** 选项卡以查看 DLP 警报仪表板。
3. 选择警报以查看详细信息：

:::image type="content" source="../media/alert-details.png" alt-text="显示 DLP 警报管理仪表板上的警报详细信息的屏幕截图。" border="false":::

4. 选择 **"事件"** 选项卡以查看与警报关联的所有事件。 可以选择特定事件以查看其详细信息。 有关一些可用事件详细信息的列表，请参阅了解数据丢失防护 [警报仪表板](dlp-alerts-dashboard-learn.md)。
5. 选择 **"** 详细信息"打开 **警报** 的"概述"页。 概述页提供了摘要：
    1. 发生的情况
    1. 谁执行了导致策略匹配的操作
    1. 有关匹配策略的信息等 

6. 选择 **"事件"** 选项卡以访问：
    1. 涉及的内容
    1. 匹配的敏感信息类型
    1. metadata

7. 选择 **"敏感信息类型"** 选项卡以查看有关内容中检测到的敏感信息类型的详细信息。 详细信息包括可信度、计数和与敏感信息类型匹配的内容。

8. 调查警报后，返回到"概述"选项卡，可在其中管理会审和管理警报处置并添加注释。

- 若要查看工作流管理的历史记录，请选择"管理 **日志"。**
- 对警报执行所需操作后，将警报的状态设置为"已解决 **"。**

## <a name="see-also"></a>另请参阅

- [了解数据丢失防护警报和警报仪表板](dlp-alerts-dashboard-learn.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
