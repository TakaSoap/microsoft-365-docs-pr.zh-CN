---
title: '配置和查看 DLP 策略的警报 (预览) '
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 10/15/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解如何定义和管理 DLP 策略的警报。
ms.openlocfilehash: addf46b27575f1a1cc062949aedb7ecdecaf7286
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651447"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>配置和查看 DLP 策略的警报 (预览) 

本文介绍如何定义与您的数据丢失防护 (DLP) 策略相关联的丰富警报策略。 您将了解如何使用 [Microsoft 365 合规性中心](https://compliance.microsoft.com/) 中的新 DLP 警报管理仪表板来查看警报、事件以及 DLP 策略冲突的相关元数据。

## <a name="features"></a>功能

以下功能是此预览的一部分：

-   **DLP 警报管理仪表板**：在 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)中，此仪表板显示对以下工作负荷强制实施的 DLP 策略的警报：

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   设备
-   **高级警报配置选项**：这些选项是 DLP 策略创作流的一部分。 使用它们创建丰富的通知配置。 您可以根据事件数或泄漏数据的大小创建单个事件警报或聚合的警报。

## <a name="before-you-begin"></a>准备工作

在开始之前，请确保您具有必要的先决条件：

-   DLP 警报管理仪表板的许可
-   通知配置选项的许可
-   角色

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP 警报管理仪表板的许可

Office 365 DLP 的所有符合条件的租户都可以访问新的 DLP 警报管理仪表板。 若要开始，你应该有适用于 Exchange Online、SharePoint Online 和 OneDrive for business 的 Office 365 DLP。 有关 Office 365 DLP 的许可要求的详细信息，请参阅 [哪些许可证为用户提供了从服务中受益的权限？](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。

参与 [终结点 dlp](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) 公共预览版或符合 [团队 dlp](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) 条件的客户将看到 dlp 警报管理仪表板中的终结点 Dlp 策略警报和团队 dlp 策略警报。

### <a name="licensing-for-alert-configuration-options"></a>通知配置选项的许可

-   **单事件警报配置**：具有 E1、F1 或 G1 订阅或 E3 或 G3 订阅的组织只能创建警报策略，在每次发生活动时都会触发警报。
-   **聚合的警报配置**：若要根据阈值配置聚合警报策略，您必须具有以下两种配置之一：
    -   E5 或 G5 订阅
    -   一个 E1、F1 或 G1 订阅或 E3 或 G3 订阅，其中包含以下功能之一：
        -   Office 365 高级威胁防护（计划 2）
        -   Microsoft 365 E5 合规
        -   Microsoft 365 电子数据展示和审核附加许可证

### <a name="roles"></a>角色

如果要查看 DLP 警报管理仪表板或编辑 DLP 策略中的警报配置选项，您必须是下列角色组之一的成员：

-   合规性管理员
-   合规性数据管理员
-   安全管理员
-   安全操作员
-   安全读取者

若要访问 DLP 警报管理仪表板，您需要 "管理警报" 角色和以下任一角色：

-   DLP 合规性管理
-   View-Only DLP 合规性管理

## <a name="alert-configuration-experience"></a>警报配置体验

如果你符合 [聚合警报配置选项](#licensing-for-alert-configuration-options)的条件，则会在 DLP 策略创作体验中直接看到以下选项。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="屏幕截图显示适用于符合聚合的警报配置选项的用户的事件报告选项。" border="false":::

您可以使用这些通知配置选项配置定义在触发警报之前 DLP 规则匹配频率的设置。 此配置使您可以设置一个策略，以便在每次活动符合策略条件或超出特定阈值时生成警报，具体取决于活动数量或基于泄露数据量。

如果你有资格进行 [单一事件警报配置选项](#licensing-for-alert-configuration-options)，则会在 DLP 策略创作体验中看到以下警报配置选项。 使用此选项可创建一个警报，该警报在每次因用户活动而发生 DLP 规则匹配时引发。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="屏幕截图显示适用于符合聚合的警报配置选项的用户的事件报告选项。" border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP 警报管理仪表板

使用 DLP 警报管理仪表板的步骤：

1.  在 [Microsoft 365 合规性中心](https://www.compliance.microsoft.com)中，转到 " **数据丢失防护**"。

2.  选择 " **通知** " 选项卡以查看 "DLP 警报" 仪表板。

    -   选择 "筛选器" 以优化警报列表。 选择 " **自定义列** " 以列出您想要查看的属性。 您还可以选择按升序或降序顺序对任何列中的警报进行排序。
    -   选择一个警报以查看详细信息：

        :::image type="content" source="../media/alert-details.png" alt-text="屏幕截图显示适用于符合聚合的警报配置选项的用户的事件报告选项。" border="false":::

1.  选择 " **事件** " 选项卡以查看与警报关联的所有事件。 您可以选择特定事件以查看其详细信息。
    下表显示了一些事件详细信息。
    
    | 类别          | 属性名                 | 说明                                                                | 适用的事件类型                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*事件详情*||
    |      | Id                            | 与事件关联的唯一 ID                                        | 所有事件                               |
    |                   | 位置                      | 检测到事件的工作负荷                                      | 所有事件                               |
    |                   | 活动时间              | 导致 DLP 冲突的用户活动的时间                    | 所有事件                               |
    |*受影响实体*||
    |  | 用户                          | 导致 DLP 冲突的用户                                          | 所有事件                               |
    |                   | 主机名称                      | 检测到 DLP 冲突的计算机的主机名              | 设备事件                           |
    |                   | IP 地址                    | 计算机的 IP 地址                                                  | 设备事件                           |
    |                   | 文件路径                     | 冲突中涉及的文件的绝对路径                        | SharePoint、OneDrive 和设备事件 |
    |                   | 电子邮件收件人              | 与 DLP 策略冲突的电子邮件的收件人                       | Exchange 事件                          |
    |                   | 电子邮件主题                 | 与 DLP 策略相冲突的电子邮件的主题                          | Exchange 事件                          |
    |                   | 电子邮件附件             | 电子邮件中违反 DLP 策略的附件的名称         | Exchange 事件                          |
    |                   | 网站所有者                    | 网站所有者的名称                                                     | SharePoint 和 OneDrive 事件           |
    |                   | 网站 URL                      | SharePoint 或 OneDrive 网站的完整 URL                                | SharePoint 和 OneDrive 事件           |
    |                   | 已创建文件                  | 创建文件的时间                                                      | SharePoint 和 OneDrive 事件           |
    |                   | 上次修改的文件            | 上次修改文件的时间                                  | SharePoint 和 OneDrive 事件           |
    |                   | 文件大小                     | 文件的大小                                                           | SharePoint 和 OneDrive 事件           |
    |                   | 文件所有者                    | 文件的所有者                                                          | SharePoint 和 OneDrive 事件           |
    |*策略详细信息*||
    |     | 与策略匹配的 DLP 策略            | 与之匹配的 DLP 策略的名称                                    | 所有事件                               |
    |                   | 规则匹配                  | DLP 策略中匹配的 DLP 规则的名称                    | 所有事件                               |
    |                   | 检测到敏感信息类型 | 作为 DLP 策略的一部分检测到的敏感信息类型 | 所有事件                               |
    |                   | Mailbox01 会使用新的数据库重新联机。                 | 作为匹配的 DLP 策略的一部分执行的操作                          | 所有事件                               |
    |                   | 用户 overrode 策略          | 用户是否通过策略提示 overrode 策略                | 所有事件                               |
    |                   | 替代对齐文本   | 为替代策略提示而提供的理由                          | 所有事件                               |
    
1.  选择 " **敏感信息类型** " 选项卡，以查看有关在内容中检测到的敏感信息类型的详细信息。 详细信息包括可信度和计数。

2.  调查通知后，选择 " **管理通知** " 以更改 **活动**、 **调查**、 **消除**或 **解决** 的) 状态 (状态。 您还可以添加注释，并将该通知分配给组织中的某个人。

    -   若要查看工作流管理的历史记录，请选择 " **管理日志**"。
    -   对通知执行所需的操作后，将警报的状态设置为 " **已解决**"。
