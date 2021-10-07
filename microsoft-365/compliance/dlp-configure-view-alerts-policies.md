---
title: 配置和查看数据丢失防护策略警报
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
description: 了解如何定义和管理数据丢失防护策略的警报。
ms.openlocfilehash: 1692467ac882b563cedd51ad3770312ba883ccd9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194497"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>配置和查看数据丢失防护策略警报

DLP 策略 (数据丢失) 采取保护措施，防止意外共享敏感项目。 对敏感项目采取操作时，可以通过配置 DLP 警报来通知您。 本文演示如何定义与 DLP 策略或 DLP 策略的数据丢失防护 () 策略。 你将看到如何使用新 DLP 警报管理仪表板Microsoft 365 合规中心查看 DLP 策略违反的警报、[事件和](https://compliance.microsoft.com/)关联元数据。

<!-- LEFT OFF HERE-->

## <a name="features"></a>功能

以下功能是以下功能的一部分：

-   **DLP 警报管理仪表板**[：](https://compliance.microsoft.com/)在Microsoft 365 合规中心中，此仪表板显示对以下工作负载强制执行的 DLP 策略的警报：

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   设备
-   **高级警报配置选项**：这些选项是 DLP 策略创作流的一部分。 使用它们创建丰富的警报配置。 你可以根据事件数或泄露数据的大小创建单个事件警报或聚合警报。

## <a name="before-you-begin"></a>准备工作

在开始之前，请确保你具有必要的先决条件：

-   DLP 警报管理仪表板的许可
-   警报配置选项的许可
-   角色

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP 警报管理仪表板的许可

DLP 的所有符合条件的租户Office 365 DLP 警报管理仪表板。 若要开始，你应该有资格使用 Office 365 DLP Exchange Online SharePoint Online 和 OneDrive for Business。 有关 DLP 的许可要求Office 365，请参阅哪些许可证为用户提供从服务中获益[的权利？。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)

使用符合[使用 DLP](endpoint-dlp-learn-about.md)条件Teams [DLP](dlp-microsoft-teams.md)的客户将在 DLP 警报管理仪表板中查看其Teams DLP 策略警报和 DLP 策略警报。

### <a name="licensing-for-alert-configuration-options"></a>警报配置选项的许可

-   **单事件警报** 配置：拥有 E1、F1 或 G1 订阅、E3 或 G3 订阅的组织只能在每次活动发生时触发警报时创建警报策略。
-   **聚合警报配置**：若要根据阈值配置聚合警报策略，必须具有以下配置之一：
    -   E5 或 G5 订阅
    -   包含以下功能之一的 E1、F1 或 G1 订阅或 E3 或 G3 订阅：
        -   Office 365 高级威胁防护（计划 2）
        -   Microsoft 365 E5 合规
        -   Microsoft 365电子数据展示和审核加载项许可证

### <a name="roles"></a>角色

如果要查看 DLP 警报管理仪表板或编辑 DLP 策略中的警报配置选项，您必须是以下角色组之一的成员：

-   合规管理员
-   合规数据管理员
-   安全管理员
-   安全操作员
-   安全信息读取者

若要访问 DLP 警报管理仪表板，您需要管理警报角色和以下角色之一：

-   DLP 合规性管理
-   View-Only DLP 合规性管理

## <a name="alert-configuration-experience"></a>警报配置体验

如果符合聚合警报配置选项的条件[](#licensing-for-alert-configuration-options)，则会看到 DLP 策略创作体验中的以下内联选项。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for aggregated alert configuration options." border="false":::

可以使用这些警报配置选项来配置一个设置，该设置定义 DLP 规则匹配在触发警报之前发生的时间。 通过此配置，您可以设置一个策略，以在活动符合策略条件或超出特定阈值时（基于活动数或根据已过滤数据的量）生成警报。

如果符合单事件警报配置选项[](#licensing-for-alert-configuration-options)的条件，则会看到 DLP 策略创作体验中的以下警报配置选项。 使用此选项可创建每次因用户活动而发生 DLP 规则匹配时都会触发的警报。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for single-event alert configuration options." border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP 警报管理仪表板

使用 DLP 警报管理仪表板：

1.  In the [Microsoft 365 合规中心，](https://www.compliance.microsoft.com)go to **Data Loss Prevention**.

2.  选择" **警报"** 选项卡以查看 DLP 警报仪表板。

    -   选择筛选器以优化警报列表。 选择 **"自定义** 列"列出您想要查看的属性。 还可以选择在任何列中按升序或降序对警报进行排序。
    -   选择警报以查看详细信息：

        :::image type="content" source="../media/alert-details.png" alt-text="显示 DLP 警报管理仪表板上的警报详细信息的屏幕截图。" border="false":::

1.  选择 **"事件"** 选项卡以查看与警报关联的所有事件。 可以选择特定事件以查看其详细信息。
    下表显示了一些事件详细信息。
    
    | 类别          | 属性名                 | 说明                                                                | 适用的事件类型                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*事件详细信息*||
    |      | Id                            | 与事件关联的唯一 ID                                        | 所有事件                               |
    |                   | 位置                      | 检测到事件的工作负荷                                      | 所有事件                               |
    |                   | 活动时间              | 导致 DLP 冲突的用户活动时间                    | 所有事件                               |
    |*影响的实体*||
    |  | 用户                          | 导致 DLP 冲突的用户                                          | 所有事件                               |
    |                   | 主机名称                      | 检测到 DLP 违反情况的机器的主机名              | 设备事件                           |
    |                   | IP 地址                    | 计算机 IP 地址                                                  | 设备事件                           |
    |                   | 文件路径                     | 冲突所涉及的文件的绝对路径                        | SharePoint、OneDrive 和设备事件 |
    |                   | 电子邮件收件人              | 违反 DLP 策略的电子邮件的收件人                       | Exchange事件                          |
    |                   | 电子邮件主题                 | 违反 DLP 策略的电子邮件主题                          | Exchange事件                          |
    |                   | 电子邮件附件             | 电子邮件中违反 DLP 策略的附件的名称         | Exchange事件                          |
    |                   | 网站所有者                    | 网站所有者的名称                                                     | SharePoint 和 OneDrive 事件           |
    |                   | 网站 URL                      | SharePoint 或 OneDrive 的完整 URL                                | SharePoint 和 OneDrive 事件           |
    |                   | 已创建文件                  | 文件创建时间                                                      | SharePoint 和 OneDrive 事件           |
    |                   | 上次修改文件            | 上次修改文件的时间                                  | SharePoint 和 OneDrive 事件           |
    |                   | 文件大小                     | 文件大小                                                           | SharePoint 和 OneDrive 事件           |
    |                   | 文件所有者                    | 文件的所有者                                                          | SharePoint 和 OneDrive 事件           |
    |*策略详细信息*||
    |     | 匹配的 DLP 策略            | 匹配的 DLP 策略的名称                                    | 所有事件                               |
    |                   | 匹配的规则                  | 匹配的 DLP 策略中的 DLP 规则的名称                    | 所有事件                               |
    |                   | 检测到敏感信息类型 | 作为 DLP 策略的一部分检测到的敏感信息类型 | 所有事件                               |
    |                   | Mailbox01 会使用新的数据库重新联机。                 | 作为匹配的 DLP 策略的一部分采取的操作                          | 所有事件                               |
    |                   | 用户过度控制策略          | 用户是否通过策略提示过度控制策略                | 所有事件                               |
    |                   | 替代对齐文本   | 提供以替代策略提示的理由                          | 所有事件                               |
    
1.  选择 **"敏感信息类型"** 选项卡以查看有关内容中检测到的敏感信息类型的详细信息。 详细信息包括可信度和计数。

2.  调查警报后，选择"管理警报"以更改 (**活动**、正在调查、已消除或已解决) 。  您还可以添加注释并将警报分配给您的组织中的某人。

    -   若要查看工作流管理的历史记录，请选择"管理 **日志"。**
    -   对警报执行所需操作后，将警报的状态设置为"已解决 **"。**