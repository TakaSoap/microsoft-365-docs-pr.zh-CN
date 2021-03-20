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
description: 无论是将新解决方案添加到合规中心、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365 都可以帮助你随时了解不断变化的合规性环境。 了解我们本月已经进行了哪些工作。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed29ad5186972f56609a596d88a48c7c460f295f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905854"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 合规中心更新信息

无论是将新解决方案添加到 Microsoft [365](microsoft-365-compliance-center.md)合规中心、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365 都可以帮助你随时了解不断变化的合规性环境。 查看下面的内容，了解 Microsoft 365 合规性的新增功能。

> [!NOTE]
> 一些合规性功能以不同的速度为客户提供推出。 如果尚未看到功能，请尝试将自己添加到 [定向发布](/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 有兴趣了解其他管理中心中如何工作？ 请查看以下文章：<br>[Microsoft 365 管理中心的新增功能](/office365/admin/whats-new-in-preview)<br>[SharePoint 管理中心的新增功能](/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender 的新增功能](../security/mtp/whats-new.md)<br><br>
请访问 [Microsoft 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap) ，了解已启动、即将推出、正在开发、已取消或之前发布的 Microsoft 365 功能。

## <a name="january-2021"></a>2021 年 1 月

### <a name="support-for-card-content-in-teams"></a>支持 Teams 中的卡片内容

以下 Microsoft 365 合规性解决方案现在支持检测[](/microsoftteams/platform/task-modules-and-cards/what-are-cards)通过 Teams 消息中的应用生成的卡内容：

- **核心和高级电子数据展示**。 现在可以将卡片内容[置于保留](create-ediscovery-holds.md#preserve-card-content)状态或包含在搜索 ([](/microsoftteams/ediscovery-investigation#search-for-card-content)内容搜索以及) 。
- **审核**。 卡片活动现在[记录到审核日志。](/microsoftteams/audit-log-events#teams-activities)
- **保留策略**。 现在可以使用保留策略 [来保留和删除卡片内容](retention-policies-teams.md#whats-included-for-retention-and-deletion)。

### <a name="information-governance-and-records-management"></a>信息管理和记录管理

[用于解决](retention-regulatory-requirements.md#new-zealand-public-records-act) 使用信息管理和记录管理以帮助履行新西兰公共记录法案的合规性义务的新评估。

### <a name="sensitivity-labels"></a>敏感度标签

- 现在，GCC 和 GCC-H (支持敏感度标签) 。
- macOS [的新](sensitivity-labels-office-apps.md) 自动标记支持。

## <a name="december-2020"></a>2020 年 12 月

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>聚焦：内部风险解决方案的新内容

Microsoft 365 合规性内容团队努力创建"内容解决方案"文档，以提升如何一起使用合规性功能来帮助实现合规性目标。

首先，将内部风险解决方案（通信合规性、内部风险管理、信息屏障和特权访问管理）紧密结合的内容。 以下是您将找到的一个速览：

- [内部风险解决方案的新登陆页面](insider-risk-solution-overview.md)。 包括有关解决方案可以帮助缓解的风险的详细信息、许可要求、部署顺序、体系结构图示、培训资源等。
- 每个内部风险解决方案的新概述文章。 帮助您了解、规划、部署和管理每个解决方案的文章指南和链接：
  - [通信合规性](communication-compliance-solution-overview.md)
  - [内部风险管理](insider-risk-management-solution-overview.md)
  - [信息屏障](information-barriers-solution-overview.md)
  - [Privileged Access Management](privileged-access-management-solution-overview.md)
  
即将推出更多内容解决方案文档！

### <a name="advanced-ediscovery"></a>高级电子数据展示

改进了工作流和功能，用于[向](add-custodians-to-case.md)高级电子数据展示案例[](non-custodial-data-sources.md)添加保管人和非托管数据源。

### <a name="data-connectors"></a>数据连接器

[发布了四个新的 Globanet 连接器](archiving-third-party-data.md#third-party-data-connectors)：Redtail Speak、Salesforce Chatter、ServiceNow 和 Yieldbroker。

### <a name="encryption"></a>加密

介绍 [租户级别的 Microsoft 365 客户密钥](customer-key-tenant-level.md)。 使用你提供的密钥，可以在 DEP (创建) 策略并将其分配给租户。 DEP 为以下工作负载加密租户内的数据：

- Teams 聊天消息 (一对一聊天、群聊、会议聊天和频道对话) 
- Teams 媒体消息 (图像、代码段、视频、wiki 图像) 
- Teams 存储中存储的 Teams 通话和会议录像
- Teams 聊天通知
- Cortana 的 Teams 聊天建议
- Teams 状态消息
- Exchange Online 的用户和信号信息

### <a name="records-management"></a>记录管理

记录 [管理管理员角色组](get-started-with-records-management.md#permissions-required-for-records-management) 现在授予所有记录管理功能（包括处置评审）的权限。

### <a name="sensitivity-labels"></a>敏感度标签

- [自动标记 Azure Azure (预览版) 。 ](/azure/purview/create-sensitivity-label) 现在，你可以创建敏感度标签，并自动将敏感度标签应用到 Azure Azure 中的资产，如 Azure Blob 存储中的文件和 Azure 中SQL Server。
- [要求用户向项目应用标签](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents)。 这一新选项也称为"强制标签"，它要求用户根据特定方案选择和应用敏感度标签。

## <a name="november-2020"></a>2020 年 11 月
只需提醒一下，我们通常以预览状态发布新功能和更新功能，以了解这些功能的使用方式，以便我们可以在发布通用功能之前进行完善和改进。 在预览阶段， (及) ，请务必通过打开合规性中心右下角的反馈卡告诉我们您的想法。

![反馈](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>聚焦：已发布 DLP (终结点) 数据丢失防护

[终结点 DLP](endpoint-dlp-learn-about.md) 将 DLP 的活动监视和保护功能扩展到 Windows 10 设备的敏感信息。 将设备 [载入](dlp-configure-endpoints.md) 到 Microsoft 365 合规中心后，可以设置 DLP 策略来保护这些设备的敏感信息。

### <a name="advanced-ediscovery"></a>高级电子数据展示

为了更加轻松地管理电子数据展示工作流中的加密内容，Microsoft 365 电子数据展示工具现在合并加密文件的解密，[](ediscovery-decryption.md)这些文件附加到电子邮件并在 Exchange 中发送。 此外，存储在 SharePoint 和 OneDrive 中的加密文档在高级电子数据展示中解密。

### <a name="compliance-manager"></a>合规性管理器

- [支持 Microsoft 365 政府版订阅](compliance-manager.md)。 合规性管理器现在可供美国政府社区 (GCC) 中等和高级客户使用。
- [适用于合规性管理器的 Microsoft 合规性配置分析器](compliance-manager-mcca.md)。 新的基于 PowerShell 的工具，通过扫描组织的当前配置并针对 Microsoft 365 建议的最佳方案验证它们，帮助你开始使用合规性管理器。
- [新模板](compliance-manager-templates-list.md)。 添加了 56 个新模板，使合规性管理器模板总数超过 230 个。

### <a name="data-connectors"></a>数据连接器

[预览版中五个新的 Globanet 连接器](archiving-third-party-data.md#third-party-data-connectors)。 新连接器包括 Reuters Dealing、Reuters FX、CellTrust、XIP、通用 MS SQL Database 数据。

### <a name="retention-labels-disposition-review"></a>保留标签 (处置评审) 

若要在处置评审期间查看项目，用户现在必须是内容资源管理器内容查看器和内容 [资源管理器列表查看器角色组的成员](disposition.md#permissions-for-disposition)。 尽管需要审阅项目，但完成处置评审不需要这些角色组。

### <a name="sensitivity-labels"></a>敏感度标签

- [ (预览) SharePoint 网站的外部共享设置](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings)。 创建将用于组和网站的标签时，你将看到一个选项，用于控制已应用标签的 SharePoint 网站的外部共享。 你可以指定允许任何人、新来宾和现有来宾、仅现有来宾或仅组织中用户共享。 应用标签后，标签设置将替换在 SharePoint 管理中心 中配置的任何外部 [共享设置](/sharepoint/change-external-sharing-site)。
- [从已标记的文档中删除标签和加密](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document)。 若要从 SharePoint 中的已标记文档删除标签和强制执行的加密，全局管理员和 SharePoint 管理员可以运行新 `Unlock-SPOSensitivityLabelEncryptedFile` cmdlet。 即使管理员无权访问站点或文件，或者 Azure 权限管理服务不可用，此 cmdlet 也运行。

## <a name="october-2020"></a>2020 年 10 月

### <a name="advanced-ediscovery"></a>高级电子数据展示

[CJK 语言支持](ediscovery-cjk-support.md)。 高级电子数据展示现在支持双字节字符集语言，统称为 CJK 语言 (包括简体中文、繁体中文、日语和朝鲜语) 。 这些可以在多个高级审阅集方案中使用。

### <a name="sensitivity-labels"></a>敏感度标签

- [标签范围](sensitivity-labels.md#label-scopes)。 创建敏感度标签时，你将看到定义标签范围的新选项。 此选项允许你仅为文件和电子邮件、容器（如 SharePoint (和/或 Teams) 配置标签。
- [动态内容标记](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。 为敏感度标签配置内容标记时，现在可以将动态变量（如 和 ）用于页眉、页脚或水印 `${Item.Label}` `${Item.Location}` 的文本字符串中。

## <a name="september-2020"></a>2020 年 9 月

### <a name="spotlight-compliance-manager"></a>聚焦：合规性管理器

今年在 Ignite 上宣布，合规性分数重新成为合规性 [管理器](compliance-manager.md)。 此版本完成了从服务信任门户中合规性管理器以前的主页的转换，并引入了 Microsoft 365 合规中心中的端到端合规性管理解决方案。

观看下面的视频，了解合规性管理器如何有助于简化组织管理合规性的情况。
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>高级审核

- 新的 10 年审核日志保留期有助于支持长时间运行的调查，并响应法规、法律和内部义务。
- [三个新的关键事件](advanced-audit.md#access-to-crucial-events-for-investigations)。 以下新事件可帮助您调查可能的泄露并确定泄露范围：Send、SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint。

### <a name="communication-compliance"></a>通信合规性

- [更新了角色组](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)。 通信合规性角色组现在与可用于内部风险管理解决方案的角色组结构相匹配。
- [报表仪表板](communication-compliance-feature-reference.md#reports)。 查看所有通信合规性报告的中央位置。 报告小组件提供对通信合规性活动状态进行总体评估最常用的见解的快速视图。
- [Power Automate 流](communication-compliance-feature-reference.md#power-automate-flows)。 设置流程以自动执行警报和用户的任务、在用户触发警报时通知管理员等。
- ["改进分类"修正操作](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)。 包含与可训练分类器匹配的项目的警报可能会从反馈中获益，以帮助最大程度地减少组织中误报。 通过 **"改进** 分类"选项，你可以提供反馈，指示检测到的项目是否与相关通信合规性策略中配置的分类器匹配。 你甚至可以建议其他分类器与项目关联，以提高将来警报的匹配准确度。

### <a name="data-connectors"></a>数据连接器

- [新的第三方数据连接器](archiving-third-party-data.md#third-party-data-connectors)。 25 个新的数据连接器，包括 14 个来自 Globanet 的连接器和 8 个来自 Telemessage 的连接器。
- [物理保护连接器](import-physical-badging-data.md)。 导入物理密码数据，例如员工的原始物理访问事件或由组织的密码系统生成的任何物理访问警报。 示例包括建筑物、服务器会议室或数据中心的条目。 内部风险管理解决方案可以使用物理保护数据来帮助保护组织免受组织内部恶意活动或数据盗窃的攻击。

### <a name="insider-risk-management"></a>内部风险管理

- [Microsoft Teams 集成](insider-risk-management-settings.md#microsoft-teams-preview)。 在内部风险设置中启用 Teams 集成后，你可以与 Teams 中其他利益干系人就安全共享和存储与个别案例相关的数据、跟踪和查看来自分析员和调查人员的响应活动等任务进行协调和协作。
- [Power Automate 流](insider-risk-management-settings.md#power-automate-flows-preview)。 设置流程以自动执行事例和用户的重要任务，例如检索要与利益干系人和其他应用共享的用户、警报和事例信息、自动执行诸如发布到事例笔记等操作。
- [活动资源管理器](insider-risk-management-alerts.md#activity-explorer-preview)。 查看警报时可用，活动资源管理器为研究人员和分析师提供了一个全面的分析工具，可用于深入查看每个警报。 快速查看检测到的风险活动的日程表，并识别并筛选与警报关联的所有风险活动。

### <a name="retention-policies-and-retention-labels"></a>保留策略和保留标签

- [支持 Yammer](retention-policies-yammer.md)。 现在，您可以使用保留策略来保留和删除 Yammer 社区消息和私人消息。
- [将标签应用于 Teams 会议录制](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings)。 创建自动标记策略时，使用关键字查询编辑器来标识存储在用户的 OneDrive 帐户或 SharePoint 中的 Teams 会议录像。

### <a name="records-management"></a>记录管理

[支持法规记录](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record)。 将标签分类为法规记录会增大对应用标签的内容的限制，并限制标签本身的可用管理操作。 例如，应用于内容后，任何人（甚至全局管理员）都不得删除标签。 [详细了解](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) 允许和阻止哪些操作用于法规记录。

### <a name="sensitivity-labels"></a>敏感度标签

[支持美国政府客户](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。 现在 GCC、GCC High 和 DoD 客户支持敏感度标签，仅适用于 Azure 信息保护统一标签客户端和扫描程序。

### <a name="trainable-classifiers"></a>可训练的分类器

新的分类和反馈功能可帮助提高准确性，并最大程度减少所有自定义分类器以及一些预先训练的分类器误报匹配。 通过此流，你可以提供有关项目是否与特定分类器匹配的反馈、建议其他分类器与项目关联以及分类分类器以优化和提高匹配准确度。

此新功能包含在以下功能中：

> [!NOTE]
> 对于所有功能，如果你至少提供 30 个反馈回复，我们将创建该分类器经过重新检查的版本，你可以查看该分类器。 如果改进，可以重新发布分类器。

- [可训练分类器](classifier-learn-about.md#retraining-classifiers)。 若要提高已发布分类器的准确性，您可以提供有关检测到的项目是否与分类器匹配的反馈。
- [通信合规性](classifier-how-to-retrain-comms-compliance.md)。 新的 **改进分类** 修正操作可使你提供通信合规性警报中的项目是否与通信合规性策略中配置的分类器匹配的反馈。
- [内容资源管理器](classifier-how-to-retrain-content-explorer.md)。 如果将保留自动标记策略设置为自动将标签应用于与可训练分类器匹配的电子邮件，可以使用内容资源管理器查看标记的项目并提供这些项目是否与分类器匹配的反馈。

## <a name="august-2020"></a>2020 年 8 月

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>聚焦：内部风险和通信合规性更新

多个新增和改进的功能在本月公开预览版中可用：

**内部风险管理**

- 查看我们的六 [个新策略模板](insider-risk-management-policies.md#policy-templates)：
    - 按优先级用户的数据泄露
    - 解除限制的用户泄露数据
    - 常规安全策略违反
    - 离开用户违反安全策略
    - 优先级用户违反安全策略
    - 解除限制的用户违反安全策略

- 与 [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 集成后，你可以导入和筛选 Microsoft Defender for Endpoint 警报，以用于根据新的违反安全策略模板创建的策略所检测到的活动。 还有一个相关的 [内部](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) 风险设置，你可以选择根据 Microsoft Defender for Endpoint 警报会审状态将安全警报导入内部风险管理。

    > [!NOTE]
    > 若要利用适用于终结点集成的 Microsoft Defender (包括新的安全策略违反模板) ，你需要在你的组织中配置 Microsoft Defender for Endpoint。 你还需要在 Microsoft Defender for Endpoint 中配置高级功能，为内部风险管理集成启用[Microsoft Defender for Endpoint。](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- 创建策略时 [自定义指示器阈值](insider-risk-management-policies.md#create-a-new-policy)。
- 设置 [优先级用户组，](insider-risk-management-settings.md#priority-user-groups-preview) 以根据用户的位置、对敏感信息的访问级别或风险历史记录等因素定义组织中需要进一步检查其活动的用户。
- 使用 Office 365 管理活动 API 将 [内部](insider-risk-management-settings.md#export-alerts-preview) 风险警报详细信息导出到组织可能用于管理或聚合内部风险数据的其他应用程序。
- 新 [域](insider-risk-management-settings.md#domains-preview) 设置可帮助您定义和控制特定域中活动的风险级别。

**通信合规性**

- 查看 [警报中的消息时](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)，现在可以删除 Microsoft Teams 频道、一对一和群聊中的不恰当的消息。 已删除的消息和内容将替换为说明由于敏感内容而删除的策略提示。
- 这些 [角色 (](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) 通信角色也包含在) 年 9 月发布的新通信合规性角色组中。
- 新的通信合规性设置体验，包括隐私 [和](communication-compliance-feature-reference.md#privacy) 通知 [模板的设置](communication-compliance-feature-reference.md#notice-templates)。
- 新的 [分类器](communication-compliance-feature-reference.md#classifiers) ，可帮助检测成人、手部和手部图像。
- 在查看警报中的邮件时显示的新"[](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details)检测到模式"通知可使你了解用户重复出现相同行为的实例。

### <a name="sensitivity-labels"></a>敏感度标签

- 对于美国政府（GCC、GCC-H 和 GCC-HC）租户，目前仅支持其Azure信息保护统一标签客户端和扫描仪的敏感性标签。 更多详细信息，请参阅[Azure 信息保护高级政府服务说明](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。
- 现在， [可以使用安全&中心 PowerShell](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) 创建和配置在标签管理中心内看到的所有设置。 这意味着，除了将 PowerShell 用于标签管理中心中不可用的设置之外，你现在还可以完全编写敏感度标签和敏感度标签策略的创建和维护脚本。

### <a name="records-management-content-overhaul"></a>记录管理：内容检查

涉及部署步骤、将内容标记为记录以及记录版本控制的新文档：

- [开始进行记录管理](get-started-with-records-management.md)
- [使用保留标签声明记录](declare-records.md)
- [使用记录版本控制来更新存储在 SharePoint 或 OneDrive 中的记录](record-versioning.md)

### <a name="retention-labels--policies"></a>保留标签&策略

现在已记录与保留相关的管理员活动，并可在审核日志。 如需完整的列表，请参阅[保留策略和保留标签活动](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。

### <a name="advanced-ediscovery"></a>高级电子数据展示

- 向 [审阅集添加](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)集合时，现在可以包括新式附件 (也称为"云附件") SharePoint 文档版本。
- 全新 [直接下载导出体验](export-documents-from-review-set.md)，无需使用 Azure 存储资源管理器下载案例内容。