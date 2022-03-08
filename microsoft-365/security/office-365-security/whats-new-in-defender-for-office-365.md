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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 12/03/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ae288b2d7dbaec9f66a501f7177741a5df48d0c
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323943"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于：**

- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本文列出了最新版本的 Microsoft Defender for Office 365。 当前处于预览状态的功能使用预览 (**表示)**。

观看[此视频](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3)了解更多信息。

> [!TIP]
> 还没有 Microsoft Defender for Office 365？ [联系销售人员以开始试用](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)。

有关其他 Microsoft Defender 安全产品的新增功能详细信息，请参阅：

- [Microsoft 365 Defender 的新增功能](../defender/whats-new.md)
- [Microsoft Defender for Endpoint 中的新增功能](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Microsoft Defender 标识的新增功能](/defender-for-identity/whats-new)
- [Microsoft Cloud App Security](/cloud-app-security/release-notes)

## <a name="march-2022"></a>2022 年 3 月

- [简化了 Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/streamlining-the-submissions-experience-in-microsoft-defender/ba-p/3152080) 中的提交体验：引入新的统一且简化的提交过程，使体验更简单。


## <a name="january-2022"></a>2022 年 1 月

- [Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/updated-hunting-and-investigation-experiences-for-microsoft/ba-p/3002015) 更新的搜寻和调查体验：介绍适用于 Office 365 Defender 体验的电子邮件摘要面板，以及威胁资源管理器和实时检测体验更新。


## <a name="october-2021"></a>2021 年 10 月

- [高级传递 DKIM 增强功能](configure-advanced-delivery.md)：增加了对 DKIM 域条目的支持，作为第三方网络钓鱼模拟配置的一部分。
- [默认安全](secure-by-default.md)：扩展默认安全Exchange邮件流规则 (传输规则) 。

## <a name="september-2021"></a>2021 年 9 月

- [改进了 Defender for Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/improving-the-reporting-experience-in-microsoft-defender-for/ba-p/2760898)
- [隔离策略](quarantine-policies.md)：管理员可以为收件人对隔离邮件的访问配置精细控制，并自定义最终用户垃圾邮件通知。
  - [管理员体验视频](https://youtu.be/vnar4HowfpY)
  - [最终用户体验视频](https://youtu.be/s-vozLO43rI)
  - 此博客文章：简化隔离体验中介绍了隔离体验中即将提供 [的其他新功能](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience/ba-p/2676388)。
- 门户重定向默认开始，将用户从安全与合规&重定向到Microsoft 365 Defender<https://security.microsoft.com>。 有关详细信息，请参阅：将帐户[从Office 365安全与合规中心重定向到Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)

## <a name="august-2021"></a>2021 年 8 月

- [管理员查看报告的邮件](admin-review-reported-message.md)：管理员现在可以在查看报告的邮件后将模板邮件发送回最终用户。 可以根据管理员裁定为组织自定义模板。
- [租户允许/](manage-tenant-allows.md)阻止列表中的添加允许：如果阻止的邮件作为管理员提交过程的一部分提交，你现在可以将允许条目添加到租户允许/阻止列表。 根据阻止的性质，提交的 URL、文件和/或发件人允许将添加到租户允许/阻止列表。 在大多数情况下，会添加 允许以向系统提供一些时间，并自然地允许（如果需要）。 在某些情况下，Microsoft 会管理你的允许。

## <a name="july-2021"></a>2021 年 7 月

- [自动调查中的电子邮件分析改进](email-analysis-investigations.md)
- [高级](configure-advanced-delivery.md)传递：引入一项新功能，用于配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到安全操作邮箱。
- [保险箱链接Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams)
- 针对以下方案的新警报策略：遭到入侵的邮箱、表单网络钓鱼、由于替代和舍入 ZAP 而传递的恶意邮件
  - 可疑电子邮件转发活动
  - 用户已被限制共享表单和收集回复
  - 表单因潜在的网络钓鱼尝试已被阻止
  - 表单已被标记并确认为网络钓鱼
  - [ZAP 的新警报策略](../../compliance/new-defender-alert-policies.md)
- Microsoft Defender for Office 365 警报现已集成到 Microsoft 365 Defender - Microsoft 365 Defender 统一警报队列和统一[警报队列](../defender/investigate-alerts.md)
- [用户](user-tags.md)标记现已集成到 Microsoft Defender 中，用于提供 Office 365 警报体验，包括：Office 365 安全 & 合规性中的警报队列和详细信息，以及将自定义警报策略范围限制到用户标记以创建目标警报策略。
  - Microsoft Defender for Microsoft 365 Defender 门户中的统一警报队列中 (Microsoft Defender for Office 365 计划 2) 

## <a name="june-2021"></a>2021 年 6 月

- 反网络钓鱼策略安全提示第一个联系人策略设置。 当安全提示第一次收到发件人发送的电子邮件或不经常收到发件人发送的电子邮件时，将显示此通知。 有关此设置以及如何配置它的信息，请参阅以下文章：
  - [第一个联系人安全提示](set-up-anti-phishing-policies.md#first-contact-safety-tip)
  - [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)
  - [在 Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md)

## <a name="aprilmay-2021"></a>2021 年 4 月/5 月

- [电子邮件实体页面](mdo-email-entity-page.md)：电子邮件的统一 360 度视图，包含有关威胁、身份验证和检测、触发详细信息以及全新的电子邮件预览体验的丰富信息。
- [Office 365 API](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events)：更新 EmailEvents (RecordType 28) 添加传递操作、原始和最新的传递位置以及更新的检测详细信息。
- [适用于防御者的威胁Office 365](/microsoft-365/security/defender/threat-analytics)：查看活动威胁参与者、热门技术和攻击面，以及 Microsoft 研究人员有关正在进行的活动的广泛报告。

## <a name="februarymarch-2021"></a>2021 年 2 月/3 月

- 警报 ID 集成 (在搜寻体验中使用警报 ID Alert-Explorer导航 [) 搜索](threat-explorer.md)
- 将搜寻体验中记录的导出限制从 9990 提高至 200，000 [](threat-explorer.md)
- 扩展 Explorer (和实时检测) 搜索体验中，试用租户的数据保留和搜索限制从以前的限制 (7) 到 30 [天](threat-explorer.md)
- Explorer (中称为 **模拟** 域和模拟用户的新搜寻透视表和实时) 搜索针对受保护的用户或域的模拟攻击。 有关详细信息，请参阅 [详细信息](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains)。  (Microsoft Defender for Office 365 计划 1 或计划 2) 


## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender for Office 365 计划 1 和计划 2

你是否知道 Microsoft Defender for Office 365在两个计划中可用？ [详细了解每个计划包括哪些内容](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。

## <a name="see-also"></a>另请参阅

[Microsoft 365路线图](https://www.microsoft.com/microsoft-365/roadmap)

[Microsoft Defender for Office 365 服务说明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
