---
title: Microsoft Defender for Office 365
description: 了解最新版本的 Microsoft Defender for Office 365 中提供的新特性和功能。
keywords: Microsoft Defender for Office 365 的新增功能， ga， 通用， 功能， 可用， 新增
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 07/27/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae01a929121488399ac3a016f0b33ae7b28ff96d
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58533611"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本文列出了最新版本的 Microsoft Defender for Office 365。 当前处于预览状态的功能使用预览 (**表示) 。**

观看[此视频](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3)了解更多信息。

> [!TIP]
> 还没有 Microsoft Defender for Office 365？ [联系销售人员以开始试用](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)。

## <a name="august-2021"></a>2021 年 8 月

- [管理员审阅报告的邮件](admin-review-reported-message.md)：管理员现在可以在查看报告的邮件后将模板邮件发送回最终用户。 这可以根据管理员裁定针对你的组织进行自定义。 
=======
## <a name="september-2021"></a>2021 年 9 月

- [隔离策略](quarantine-policies.md)：管理员可以为收件人访问隔离邮件配置精细控制，并自定义最终用户垃圾邮件通知。
  - [管理员体验视频](https://youtu.be/vnar4HowfpY)
  - [最终用户体验视频](https://youtu.be/s-vozLO43rI)
  - 此博客文章介绍隔离体验中即将提供的其他新功能： [简化隔离体验](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience/ba-p/2676388)。

## <a name="august-2021"></a>2021 年 8 月

- [管理员审阅报告的邮件](admin-review-reported-message.md)：管理员现在可以在查看报告的邮件后将模板邮件发送回最终用户。 可以根据管理员裁定为组织自定义模板。
- [租户允许/](manage-tenant-allows.md)阻止列表中的添加允许：如果阻止的邮件作为管理员提交过程的一部分提交，你现在可以将允许条目添加到租户允许/阻止列表。 根据阻止的性质，提交的 URL、文件和/或发件人允许将添加到租户允许/阻止列表。 在大多数情况下，添加 允许为系统提供一些时间，并自然地允许（如果需要）。 在某些情况下，Microsoft 会管理你的允许。

## <a name="july-2021"></a>2021 年 7 月

- [自动调查中的电子邮件分析改进](email-analysis-investigations.md)
- [高级](configure-advanced-delivery.md)传递：引入一项新功能，用于配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到安全操作邮箱。
- [保险箱链接Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams)
- 针对以下方案的新警报策略：遭到入侵的邮箱、表单网络钓鱼、由于替代和舍入 ZAP 而传递的恶意邮件
  - 可疑电子邮件转发活动
  - 用户被限制共享表单和收集响应
  - 表单因潜在的网络钓鱼尝试被阻止
  - 已标记并确认为网络钓鱼的表单
  - [ZAP 的新警报策略](../../compliance/new-defender-alert-policies.md)
- Microsoft Defender for Office 365 警报现已集成到 Microsoft 365 Defender - Microsoft 365 Defender 统一警报队列和[统一警报队列](../defender/investigate-alerts.md)
- [用户](user-tags.md)标记现已集成到 Microsoft Defender 中，用于提供 Office 365 警报体验，包括：Office 365 安全 & 合规性中的警报队列和详细信息，以及将自定义警报策略范围限制到用户标记以创建目标警报策略。 
  - Microsoft Defender for Office 365 计划 2 中Microsoft 365 Defender中心 (统一警报Office 365标记) 

## <a name="june-2021"></a>2021 年 6 月

- 反网络钓鱼策略安全提示第一个联系人策略设置。 当安全提示第一次收到来自发件人的电子邮件或不经常收到发件人的电子邮件时，将显示此通知。 有关此设置以及如何配置它的信息，请参阅以下文章：
  - [第一个联系人安全提示](set-up-anti-phishing-policies.md#first-contact-safety-tip)
  - [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)
  - [在 Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md)

## <a name="aprilmay-2021"></a>2021 年 4 月/5 月

- [电子邮件实体页面](mdo-email-entity-page.md)：电子邮件的统一 360 度视图，包含有关威胁、身份验证和检测、触发详细信息以及全新的电子邮件预览体验的丰富信息。
- [Office 365 API：](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events)更新 EmailEvents (RecordType 28) 添加传递操作、原始和最新的传递位置以及更新的检测详细信息。
- [适用于防御者的威胁Office 365：](/microsoft-365/security/defender/threat-analytics)查看活动威胁参与者、热门技术和攻击面，以及 Microsoft 研究人员针对正在进行的活动进行的广泛报告。

## <a name="februarymarch-2021"></a>2021 年 2 月/3 月

- 警报 ID 集成 (在搜寻体验中使用警报 ID Alert-Explorer导航 [) 搜索](threat-explorer.md)
- 将搜寻体验中记录的导出限制从 9990 提高至 200，000 [](threat-explorer.md)
- 扩展 Explorer (和实时检测) 搜索体验中试用租户的数据保留和搜索限制从之前限制 (7 天) 到 30 [天](threat-explorer.md)
- Explorer (中名为 **模拟** 域和模拟用户的新搜寻透视表和实时) 搜索针对受保护用户或域的模拟攻击。 有关详细信息，请参阅 [详细信息](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains)。  (Microsoft Defender for Office 365 计划 1 或计划 2) 

## <a name="december-2020"></a>2020 年 12 月

- [默认情况下，安全Office 365](secure-by-default.md)
- 自动调查改进：针对手动触发的电子邮件调查的常规警报、将邮箱更改视为单独的实体类别、删除冗余 URL 阻止操作，以及创建出站电子邮件群集以用于用户遭到入侵的调查。

## <a name="november-2020"></a>2020 年 11 月

- Review > Action Center > Remediation from Mail Submission and Action Log (Defender for Office 365 Plan 2 中的) 

## <a name="septemberoctober-2020"></a>2020 年 9 月/10 月

- 当收件人安全提示发件人发送的电子邮件或不经常收到发件人发送的电子邮件时，新建的第一个联系人联系人。 有关此设置以及如何使用 Exchange 邮件流规则配置它 (也称为传输规则) ，[请参阅第一](set-up-anti-phishing-policies.md#first-contact-safety-tip)个联系人安全提示。
- [使用配置分析器检查策略](configuration-analyzer-for-security-policies.md)
- 威胁资源管理器中的扩展功能，包括主要目标用户、传输规则和连接器[ (](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) Defender for Office 365 信息，威胁资源管理器[ (](threat-explorer.md)电子邮件被租户/用户策略)  (Defender for Office 365 计划 2) 
- 在威胁资源管理器中显示 URL[威胁 (恶意软件](threat-explorer.md#threats-in-urls)、网络钓鱼、垃圾邮件或无)  (Defender for Office 365 计划 2) 
- [针对威胁、](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming)其他操作、传递位置和更新时间线视图的搜寻体验威胁资源管理器的改进 (Defender for Office 365 计划 2) 

## <a name="julyaugust-2020"></a>2020 年 7 月/8 月

- [Microsoft](threat-explorer.md#improvements-to-threat-hunting-experience) Defender for (计划 1 或计划 2 Office 365搜寻体验体验) 
- [使用预设安全策略轻松应用推荐设置](preset-security-policies.md)

## <a name="marchapril-2020"></a>2020 年 3 月/4 月

- 现在通常 [可以使用](address-compromised-users-quickly.md) 自动调查和响应功能处理遭到入侵的用户帐户。  (Microsoft Defender for Office 365 计划 2) 

## <a name="januaryfebruary-2020"></a>2020 年 1 月/2 月

- [Microsoft Defender for Office 365 (](campaigns.md)计划 2 Office 365中的市场活动视图) 
- 威胁[资源管理器增强功能](threat-explorer.md)，使安全运营团队能够搜索和筛选多个字段，同时调查[电子邮件](investigate-malicious-email-that-was-delivered.md)： (Microsoft Defender for Office 365 计划 2) 
  - 传递位置和特殊操作
  - 方向 (入站、出站或组织内部) 
  - 高级 NOT 筛选器 (包括不包含、不包含等高级筛选) 
  - 粒度时间筛选器 (天、小时、每小时) 

- " **事件"** 小部件现在是"操作 **中心"小部件** 。  (安全与合规中心查看安全小组件&，请转到威胁管理 \> **审阅**.)  (Microsoft Defender for Office 365 计划 2) 

- [保险箱预览Microsoft 365 (](safe-docs.md)**文档)**

## <a name="december-2019"></a>2019 年 12 月

- [在 Microsoft](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) Defender for (计划 1 或计划 2 Office 365导出 URL 单击数据进行脱机) 

- [使用 Microsoft Defender 中的市场活动视图Office 365 (**预览** 版)  (](campaigns.md) Microsoft Defender for Office 365 计划 2) 

## <a name="november-2019"></a>2019 年 11 月

- [查看 Microsoft](address-compromised-users-quickly.md) Defender for (**计划** 2)  (预览版中新的泄露Office 365和响应) 

## <a name="september-2019"></a>2019 年 9 月

- [使用 Microsoft](automated-investigation-response-office.md) Defender for (计划 2 Office 365的自动调查和响应) 

- [与 Microsoft Defender 集成Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)使用 Office 365 Management Activity API (Defender for Office 365 Plan 2) 

- [查看电子邮件头，并下载](investigate-malicious-email-that-was-delivered.md)Microsoft Defender for (计划 1 Office 365计划 2 电子邮件) 

## <a name="august-2019"></a>2019 年 8 月

- [查看 Microsoft](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) Defender for (计划 1 或Office 365 2 计划的电子邮件时间线) 

## <a name="july-2019"></a>2019 年 7 月

- [检查 Microsoft](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) Defender for (计划 1 或 2 Office 365电子邮件的传递操作和) 

## <a name="june-2019"></a>2019 年 6 月

- [查看网络钓鱼 URL](threat-explorer.md#view-phishing-url-and-click-verdict-data)并单击 Microsoft Defender for (计划 1 Office 365计划 2 中的裁定) 

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender for Office 365 计划 1 和计划 2

你是否知道 Microsoft Defender for Office 365在两个计划中可用？ [详细了解每个计划包括哪些内容](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。

## <a name="see-also"></a>另请参阅

[Microsoft 365路线图](https://www.microsoft.com/microsoft-365/roadmap)

[Microsoft Defender for Office 365 服务说明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
