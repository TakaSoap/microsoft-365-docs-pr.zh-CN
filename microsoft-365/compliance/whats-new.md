---
title: Microsoft 365 合规中心更新信息
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 无论是向合规中心添加新解决方案、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365 都可以帮助你随时了解不断变化的合规性环境。 了解我们这个月已经进行了哪些工作。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4fcc0c9317ed0f302c03ba4bda0b536b57889660
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066815"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 合规中心更新信息

无论是向 [Microsoft 365](microsoft-365-compliance-center.md)合规中心添加新解决方案、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365 都可以帮助你随时了解不断变化的合规性环境。 查看下面的内容，了解 Microsoft 365 合规性的新增功能。

> [!NOTE]
> 一些合规性功能以不同速度向我们的客户推出。 如果尚未看到功能，请尝试将自己添加到 [定向发布](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 有兴趣了解其他管理中心中正在做什么？ 请查看以下文章：<br>[Microsoft 365 管理中心中的新增功能](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[SharePoint 管理中心中的新增功能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender 的新增功能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
请访问 [Microsoft 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap) ，了解已启动、即将推出、正在开发、已取消或之前发布的 Microsoft 365 功能。

## <a name="december-2020"></a>2020 年 12 月

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>聚焦：内部风险解决方案的新内容

Microsoft 365 合规性内容团队努力创建"内容解决方案"文档，以提升合规性功能如何一起用于帮助实现合规性目标。

首先，将内部风险解决方案（通信合规性、内部风险管理、信息屏障和特权访问管理）紧密结合的内容。 下面将看一看你将找到的：

- [内部风险解决方案的新登录页面](insider-risk-solution-overview.md)。 包括解决方案可帮助缓解的风险、许可要求、部署顺序、体系结构图示、培训资源等的详细信息。
- 每个内部风险解决方案的新概述文章。 帮助您了解、规划、部署和管理每个解决方案的文章指南和链接：
  - [通信合规性](communication-compliance-solution-overview.md)
  - [内部风险管理](insider-risk-management-solution-overview.md)
  - [信息屏障](information-barriers-solution-overview.md)
  - [Privileged Access Management](privileged-access-management-solution-overview.md)
  
即将推出更多内容解决方案文档！

### <a name="advanced-ediscovery"></a>高级电子数据展示

改进了工作流[和功能，用于](add-custodians-to-case.md)向高级电子数据展示案例[](non-custodial-data-sources.md)添加保管人和非监管数据源。

### <a name="data-connectors"></a>数据连接器

[发布了四个新的 Globanet 连接器](archiving-third-party-data.md#third-party-data-connectors)：Redtail Speak、Salesforce Chatter、ServiceNow 和 Yieldbroker。

### <a name="encryption"></a>加密

介绍 [租户级别的 Microsoft 365 客户密钥](customer-key-tenant-level.md)。 使用提供的密钥，可以在 DEP (创建) 策略并将其分配给租户。 DEP 对租户中这些工作负载的数据进行加密：

- Teams 聊天 (一对一聊天、群聊、会议聊天和频道对话) 
- Teams 媒体 (图像、代码段、视频、wiki 图像) 
- Teams 存储中存储的 Teams 通话和会议录像
- Teams 聊天通知
- Cortana 的 Teams 聊天建议
- Teams 状态消息
- Exchange Online 的用户和信号信息

### <a name="records-management"></a>记录管理

记录 [管理管理员角色组现在](get-started-with-records-management.md#permissions-required-for-records-management) 授予所有记录管理功能（包括处置评审）的权限。

### <a name="sensitivity-labels"></a>敏感度标签

- [自动标记 Azure Azure (预览) 。 ](https://docs.microsoft.com/en-us/azure/purview/create-sensitivity-label) 现在，你可以创建敏感度标签并自动将敏感度标签应用到 Azure Azure 中的资产，如 Azure Blob 存储中的文件和 Azure 中SQL Server。
- [要求用户向项目应用标签](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents)。 这一新选项也称为"强制标签"，要求用户根据特定方案选择和应用敏感度标签。

## <a name="november-2020"></a>2020 年 11 月
提醒我们通常以预览状态发布新功能和更新的功能，以了解这些功能的使用方式，以便我们可以在发布为通用功能之前进行完善和改进。 在预览版和 (预览版) ，请务必通过打开合规性中心右下角的反馈卡，告诉我们您的想法。

![反馈](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>聚焦：发布 DLP (终结点) 数据丢失防护

[终结点 DLP](endpoint-dlp-learn-about.md) 将 DLP 的活动监视和保护功能扩展到 Windows 10 设备上敏感信息。 在 [设备载入到](dlp-configure-endpoints.md) Microsoft 365 合规中心后，可以设置 DLP 策略来保护这些设备的敏感信息。

### <a name="advanced-ediscovery"></a>高级电子数据展示

为了更轻松地管理电子数据展示工作流中的加密内容，Microsoft 365 电子数据展示工具现在包含附加到电子邮件并在 Exchange[](ediscovery-decryption.md)中发送的加密文件的解密。 此外，存储在 SharePoint 和 OneDrive 中的加密文档在高级电子数据展示中解密。

### <a name="compliance-manager"></a>合规性管理器

- [支持 Microsoft 365 政府版订阅](compliance-manager.md)。 合规性管理器现在可供美国政府社区 (GCC) 中等和高客户使用。
- [适用于合规性管理器的 Microsoft 合规性配置分析器](compliance-manager-mcca.md)。 新的基于 PowerShell 的工具，通过扫描组织的当前配置，并针对 Microsoft 365 建议的最佳方案验证它们，帮助你开始使用合规性管理器。
- [新模板](compliance-manager-templates-list.md)。 添加了 56 个新模板，使合规性管理器模板总数超过 230 个。

### <a name="data-connectors"></a>数据连接器

[预览版中的五个新的 Globanet 连接器](archiving-third-party-data.md#third-party-data-connectors)。 新连接器包括 Reuters Dealing、Reuters FX、CellTrust、XIP、generic MS SQL Database 数据。

### <a name="retention-labels-disposition-review"></a>保留标签 (处置评审) 

若要在处置评审期间查看项目，用户现在必须是内容资源管理器内容查看器和 [内容资源管理器列表查看器角色组的成员](disposition.md#permissions-for-disposition)。 尽管需要审阅项目，但完成处置评审不需要这些角色组。

### <a name="sensitivity-labels"></a>敏感度标签

- [ (预览) SharePoint 网站的外部共享设置](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings)。 创建将用于组和网站的标签时，你将看到一个选项，用于控制已应用标签的 SharePoint 网站的外部共享。 可以指定允许任何人、新来宾和现有来宾、仅现有来宾或仅组织用户共享。 应用标签后，标签设置将替换 [在 SharePoint](https://docs.microsoft.com/sharepoint/change-external-sharing-site)管理中心配置的任何外部共享设置。
- [从已标记的文档中删除标签和加密](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document)。 若要从 SharePoint 中已标记的文档中删除标签及其强制加密，全局管理员和 SharePoint 管理员可以运行新的 `Unlock-SPOSensitivityLabelEncryptedFile` cmdlet。 即使管理员无权访问站点或文件，或者 Azure 权限管理服务不可用，此 cmdlet 也运行。

## <a name="october-2020"></a>2020 年 10 月

### <a name="advanced-ediscovery"></a>高级电子数据展示

[CJK 语言支持](ediscovery-cjk-support.md)。 高级电子数据展示现在支持双字节字符集语言，统称为 CJK 语言 (包括简体中文、繁体中文、日语和朝鲜语) 。 这些可在多个高级审阅集方案中使用。

### <a name="sensitivity-labels"></a>敏感度标签

- [标签范围](sensitivity-labels.md#label-scopes)。 创建敏感度标签时，你将看到一个新选项，用于定义标签的范围。 此选项允许你仅为文件和电子邮件、容器和/或 (SharePoint 网站和 Teams) 配置标签。
- [动态内容标记](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。 为敏感度标签配置内容标记时，现在可以将动态变量（如文本字符串和文本字符串）用于页眉、 `${Item.Label}` `${Item.Location}` 页脚或水印。

## <a name="september-2020"></a>2020 年 9 月

### <a name="spotlight-compliance-manager"></a>聚焦：合规性管理器

今年在 Ignite 上宣布，合规性分数重新成为 [合规性管理器](compliance-manager.md)。 此版本完成了从服务信任门户中合规性管理器以前主页的转换，并引入了 Microsoft 365 合规中心中的端到端合规性管理解决方案。

观看下面的视频，了解合规性管理器如何有助于简化组织管理合规性的情况。
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>高级审核

- 新的 10 年审核日志保留期可帮助支持长时间运行的调查，并响应法规、法律和内部义务。
- [三个新的关键事件](advanced-audit.md#access-to-crucial-events-for-investigations)。 以下新事件可帮助您调查可能的泄露并确定泄露范围：Send、SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint。

### <a name="communication-compliance"></a>通信合规性

- [更新的角色组](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)。 通信合规性角色组现在与可用于内部风险管理解决方案的角色组结构相匹配。
- [报表仪表板](communication-compliance-feature-reference.md#reports-preview)。 查看所有通信合规性报告的中央位置。 "报告"小组件提供对通信合规性活动状态进行总体评估最常用的见解的快速视图。
- [Power Automate 流](communication-compliance-feature-reference.md#power-automate-flows)。 设置流以自动执行提醒和用户的任务、在用户触发警报时通知管理员等。
- ["改进分类"修正操作](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)。 包含与可训练分类器匹配的项目的警报可能会从反馈中获益，以帮助最大程度地减少组织中误报。 通过 **"改进** 分类"选项，你可以提供相关通信合规性策略中配置的分类器是否与检测到的项目匹配的反馈。 你甚至可以建议其他分类器与项目关联，以提高未来警报的匹配准确度。

### <a name="data-connectors"></a>数据连接器

- [新的第三方数据连接器](archiving-third-party-data.md#third-party-data-connectors)。 25 个新的数据连接器，包括 14 个来自 Globanet 的连接器和 8 个来自 Telemessage 的连接器。
- [物理保护连接器](import-physical-badging-data.md)。 导入物理密码数据，例如员工的原始物理访问事件或组织密码系统生成的任何物理访问警报。 示例包括建筑物、服务器会议室或数据中心的条目。 内部风险管理解决方案可以使用物理保护数据来帮助保护组织免受组织内部的恶意活动或数据盗窃。

### <a name="insider-risk-management"></a>内部风险管理

- [Microsoft Teams 集成](insider-risk-management-settings.md#microsoft-teams-preview)。 在内部风险设置中启用 Teams 集成后，你可以与 Teams 中其他利益干系人协作，共同执行与单个案例相关的安全共享和存储数据、跟踪和查看分析员和调查人员的响应活动等任务。
- [Power Automate 流](insider-risk-management-settings.md#power-automate-flows-preview)。 设置流程以自动执行事例和用户的重要任务，例如检索要与利益干系人和其他应用共享的用户、警报和事例信息，自动执行诸如发布到事例笔记等操作。
- [活动资源管理器](insider-risk-management-alerts.md#activity-explorer-preview)。 查看警报时可用，活动资源管理器为调查人员和分析师提供了一个全面的分析工具，用于深入查看每个警报。 快速查看检测到的风险活动的日程表，并识别并筛选与警报关联的所有风险活动。

### <a name="retention-policies-and-retention-labels"></a>保留策略和保留标签

- [支持 Yammer](retention-policies-yammer.md)。 现在，您可以使用保留策略来保留和删除 Yammer 社区消息和私人消息。
- [将标签应用于 Teams 会议录制](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings)。 创建自动标记策略时，使用关键字查询编辑器来标识存储在用户的 OneDrive 帐户或 SharePoint 中的 Teams 会议录制。

### <a name="records-management"></a>记录管理

[支持法规记录](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record)。 将标签分类为法规记录会增加对应用标签的内容的限制，并限制标签本身的可用管理操作。 例如，应用于内容后，任何人（甚至全局管理员）都不得删除标签。 [详细了解](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) 允许和阻止哪些操作用于法规记录。

### <a name="sensitivity-labels"></a>敏感度标签

[支持美国政府客户](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。 现在，仅 Azure 信息保护统一标签客户端和扫描程序支持 GCC、GCC High 和 DoD 客户敏感度标签。

### <a name="trainable-classifiers"></a>可训练的分类器

新的分类和反馈功能可帮助提高所有自定义分类器以及一些预先训练的分类器的准确性并最大限度地减少误报匹配。 通过此流，你可以提供有关项目是否匹配特定分类器的反馈，建议其他分类器与项目关联，以及分类分类器以优化和提高匹配准确度。

此新功能包含在以下功能中：

> [!NOTE]
> 对于所有功能，如果至少提供 30 个反馈回复，我们将创建该分类器经过重新检查的版本，你可以查看该分类器。 如果改进，可以重新发布分类器。

- [可训练分类器](classifier-learn-about.md#retraining-classifiers)。 若要提高已发布分类器的准确性，您可以提供有关检测到的项目是否与分类器匹配的反馈。
- [通信合规性](classifier-how-to-retrain-comms-compliance.md)。 新的 **"改进分类** 修正"操作可使你提供反馈，了解通信合规性警报中的项目是否与通信合规性策略中配置的分类器匹配。
- [内容资源管理器](classifier-how-to-retrain-content-explorer.md)。 如果将保留自动标记策略设置为自动将标签应用于与可训练分类器匹配的电子邮件，可以使用内容资源管理器查看标记的项目并提供项目是否与分类器匹配的反馈。

## <a name="august-2020"></a>2020 年 8 月

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>聚焦：内部风险和通信合规性更新

多个新增和改进的功能在本月公开预览版中可用：

**内部风险管理**

- 查看我们的六 [个新策略模板](insider-risk-management-policies.md#policy-templates)：
    - 按优先级用户的数据泄露
    - 解除限制的用户泄露数据
    - 一般安全策略违反
    - 离开用户违反安全策略
    - 优先级用户违反安全策略
    - 解除限制的用户违反安全策略

- 与 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 集成后，你可以导入和筛选 Microsoft Defender 的终结点警报，以用于根据新的违反安全策略模板创建的策略检测到的活动。 此外，还有相关的内部风险[](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)设置，你可以选择根据 Microsoft Defender for Endpoint 警报会审状态将安全警报导入内部风险管理。

    > [!NOTE]
    > 若要利用 Microsoft Defender for Endpoint 集成 (包括新的安全策略违反模板) ，你需要在组织中配置 Microsoft Defender for Endpoint。 你还需要在 Microsoft Defender for Endpoint 中配置高级功能，为内部风险管理集成启用[Microsoft Defender for Endpoint。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- 创建策略时自定义 [指示器阈值](insider-risk-management-policies.md#create-a-new-policy)。
- 设置 [优先级用户组，](insider-risk-management-settings.md#priority-user-groups-preview) 以根据用户的位置、敏感信息访问级别或风险历史记录等因素来定义组织中需要进一步检查其活动的用户。
- 使用 Office 365 管理活动 API 将 [内部](insider-risk-management-settings.md#export-alerts-preview) 风险警报详细信息导出到组织可能用于管理或聚合内部风险数据的其他应用程序。
- 新 [域](insider-risk-management-settings.md#domains-preview) 设置可帮助您定义和控制特定域中活动的风险级别。

**通信合规性**

- 查看 [警报中的消息](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)时，现在可以删除 Microsoft Teams 频道、一对一和群聊中的不恰当的消息。 已删除的邮件和内容将替换为策略提示，说明由于敏感内容而将其删除。
- 新的 [通信 (](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) 角色也将包含在) 年 9 月发布的新通信合规性角色组中。
- 新的通信合规性设置体验，包括隐私[和](communication-compliance-feature-reference.md#privacy)[通知模板的设置](communication-compliance-feature-reference.md#notice-templates)。
- 新的 [分类器](communication-compliance-feature-reference.md#classifiers) 可帮助检测成人、手部和手部图像。
- 查看警报中的邮件时显示的新"检测到[](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details)的模式"通知可使你了解用户重复发生相同行为的实例。

### <a name="sensitivity-labels"></a>敏感度标签

- 对于美国政府（GCC、GCC-H 和 GCC-HC）租户，目前仅支持其Azure信息保护统一标签客户端和扫描仪的敏感性标签。 更多详细信息，请参阅[Azure 信息保护高级政府服务说明](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。
- 现在， [可以使用安全&合规中心 PowerShell](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) 创建和配置在标签管理中心看到的所有设置。 这意味着，除了将 PowerShell 用于标签管理中心中不可用的设置之外，你现在还可以完全编写敏感度标签和敏感度标签策略的创建和维护脚本。

### <a name="records-management-content-overhaul"></a>记录管理：内容检查

涉及部署步骤、将内容标记为记录和记录版本控制的新文档：

- [开始进行记录管理](get-started-with-records-management.md)
- [使用保留标签声明记录](declare-records.md)
- [使用记录版本控制来更新存储在 SharePoint 或 OneDrive 中的记录](record-versioning.md)

### <a name="retention-labels--policies"></a>保留标签&策略

现在记录与保留相关的管理员活动，并可在审核日志。 如需完整的列表，请参阅[保留策略和保留标签活动](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。

### <a name="advanced-ediscovery"></a>高级电子数据展示

- 将 [集合添加到审阅集](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)时，现在可以包括新式附件 (也称为"云附件") SharePoint 文档版本。
- 新的 [直接下载导出体验](export-documents-from-review-set.md)，无需使用 Azure 存储资源管理器下载案例内容。

## <a name="july-2020"></a>2020 年 7 月

### <a name="spotlight-on-help-docs"></a>聚焦帮助文档

为了帮助您了解用于保护和管理组织的敏感数据的合规性解决方案，我们创建了两个新的登录页面，概述了解决方案如何协同工作以实现这些目标，包括指向相关文档的链接，以便您可以进一步深入研究。

[Microsoft 365 中的 Microsoft 信息保护](information-protection.md)<br>
[Microsoft 365 中的 Microsoft 信息治理](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>高级电子数据展示：将非安全数据源添加到事例

将数据添加到案例，而无需将其与保管人 (称为非) 。 [](non-custodial-data-sources.md) 如果需要保留此非安全数据，可以使用我们新的高级索引功能来这样做。

### <a name="data-connectors-hr-connector-enhancements"></a>数据连接器：HR 连接器增强功能

 (预览) 新版本 [的 HR](import-hr-data.md) 连接器允许您导入与作业级别更改、绩效考核和性能改进计划相关的数据。 然后，此数据可在多个内部风险策略 [中用于](insider-risk-management-policies.md) 检测相关活动。

### <a name="retention-labels-new-support-for-email"></a>保留标签：电子邮件的新支持

现在可以创建保留 [标签，](retention.md#retention-labels) 以根据邮件的标记时间开始保留电子邮件。 这不适用于日历项目，日历项目将基于项目发送时间进行保留。

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>敏感度标签：新功能和改进

-  (在预览) 配置标签的加密设置时，查找使用双密钥加密以进一步保护已标记文件和电子邮件的新[](encryption-sensitivity-labels.md#double-key-encryption)选项。
- 创建或删除敏感度标签或创建、编辑或删除标签策略时，更改现在在 1 小时内同步到所有用户、应用和服务。
