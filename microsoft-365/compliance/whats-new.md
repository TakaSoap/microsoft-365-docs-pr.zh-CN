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
description: 无论是将新解决方案添加到合规中心、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365 都可以帮助你随时了解不断变化的合规性环境。 了解我们这个月已经进行了哪些工作。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8723171820bb1c089d34b81f5adb6663ecc9b8af
ms.sourcegitcommit: 27cb4591e08f62ba0a08d6dcf224bf2039034fe5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2021
ms.locfileid: "49883711"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 合规中心更新信息

无论是向 [Microsoft 365](microsoft-365-compliance-center.md)合规中心添加新解决方案、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365 都可以帮助你随时了解不断变化的合规性环境。 查看下面的内容，了解 Microsoft 365 合规性的新增功能。 

> [!NOTE]
> 一些合规性功能以不同速度向我们的客户推出。 如果尚未看到功能，请尝试将自己添加到 [定向发布](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)。


> [!TIP]
> 有兴趣了解其他管理中心中正在做什么？ 请查看以下文章：<br>[Microsoft 365 管理中心中的新增功能](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[SharePoint 管理中心中的新增功能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender 的新增功能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
请访问 [Microsoft 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap) ，了解已启动、即将推出、正在开发、已取消或之前发布的 Microsoft 365 功能。

## <a name="november--december-2020"></a>2020 & 11 月&日
提醒我们通常以预览状态发布新功能和更新的功能，以了解这些功能的使用方式，以便我们可以在发布为通用功能之前进行完善和改进。 在预览版和 (预览版) ，请务必通过打开合规性中心右下角的反馈卡，告诉我们您的想法。

![反馈](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>聚焦：发布 DLP (终结点) 数据丢失防护

[终结点 DLP](endpoint-dlp-learn-about.md) 将 DLP 的活动监视和保护功能扩展到 Windows 10 设备上敏感信息。 在 [设备载入到](dlp-configure-endpoints.md) Microsoft 365 合规中心后，可以设置 DLP 策略来保护这些设备的敏感信息。

### <a name="advanced-ediscovery"></a>高级电子数据展示

为了更加轻松地管理电子数据展示工作流中的加密内容，Microsoft 365 电子数据展示工具现在包含附加到电子邮件并在[](ediscovery-decryption.md)Exchange 中发送的加密文件的解密。 此外，存储在 SharePoint 和 OneDrive 中的加密文档在高级电子数据展示中解密。

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
- [从已标记的文档中删除标签和加密](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document)。 若要从 SharePoint 中的已标记文档删除标签和它强制执行的加密，全局管理员和 SharePoint 管理员可以运行新的 `Unlock-SPOSensitivityLabelEncryptedFile` cmdlet。 即使管理员无权访问站点或文件，或者 Azure 权限管理服务不可用，此 cmdlet 也运行。

## <a name="october-2020"></a>2020 年 10 月

### <a name="advanced-ediscovery"></a>高级电子数据展示

[CJK 语言支持](ediscovery-cjk-support.md)。 高级电子数据展示现在支持双字节字符集语言，统称为 CJK 语言 (包括简体中文、繁体中文、日语和朝鲜语) 。 这些可以在多个高级审阅集方案中使用。

### <a name="sensitivity-labels"></a>敏感度标签

- [标签范围](sensitivity-labels.md#label-scopes)。 创建敏感度标签时，你将看到一个新选项，用于定义标签的范围。 此选项允许你仅为文件和电子邮件、容器和/或 (SharePoint 网站和 Teams) 配置标签。
- [动态内容标记](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。 为敏感度标签配置内容标记时，现在可以将动态变量（如文本字符串和文本字符串）用于页眉、 `${Item.Label}` `${Item.Location}` 页脚或水印。

## <a name="september-2020"></a>2020 年 9 月

### <a name="spotlight-compliance-manager"></a>聚焦：合规性管理器

今年在 Ignite 上宣布，合规性分数重新成为合规性 [管理器](compliance-manager.md)。 此版本完成了从服务信任门户中合规性管理器以前主页的转换，并引入了 Microsoft 365 合规中心中的端到端合规性管理解决方案。

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
- [Power Automate 流](communication-compliance-feature-reference.md#power-automate-flows)。 设置流程以自动执行提醒和用户的任务、在用户触发警报时通知管理员等。
- ["改进分类"修正操作](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)。 包含与可训练分类器匹配的项目的警报可能会从反馈中获益，以帮助最大程度地减少组织中误报。 通过 **"改进** 分类"选项，你可以提供相关通信合规性策略中配置的分类器是否与检测到的项目匹配的反馈。 你甚至可以建议其他分类器与项目关联，以提高未来警报的匹配准确度。

### <a name="data-connectors"></a>数据连接器

- [新的第三方数据连接器](archiving-third-party-data.md#third-party-data-connectors)。 25 个新的数据连接器，包括 14 个来自 Globanet 的连接器和 8 个来自 Telemessage 的连接器。
- [物理保护连接器](import-physical-badging-data.md)。 导入物理密码数据，例如员工的原始物理访问事件或组织密码系统生成的任何物理访问警报。 示例包括建筑物、服务器会议室或数据中心的条目。 内部风险管理解决方案可以使用物理保护数据来帮助保护组织免受组织内部的恶意活动或数据盗窃。

### <a name="insider-risk-management"></a>内部风险管理

- [Microsoft Teams 集成](insider-risk-management-settings.md#microsoft-teams-preview)。 在内部风险设置中启用 Teams 集成后，你可以与 Teams 中其他利益干系人协作，共同执行与单个案例相关的安全共享和存储数据、跟踪和查看分析员和调查人员的响应活动等任务。
- [Power Automate 流](insider-risk-management-settings.md#power-automate-flows-preview)。 设置流程以自动执行事例和用户的重要任务，例如检索用户、警报和案例信息以与利益干系人和其他应用共享、自动执行诸如发布到事例笔记等操作。
- [活动资源管理器](insider-risk-management-alerts.md#activity-explorer-preview)。 在查看警报时可用，活动资源管理器为调查人员和分析师提供了一个全面的分析工具，用于深入查看每个警报。 快速查看检测到的风险活动的日程表，并识别并筛选与警报关联的所有风险活动。

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
> 对于所有功能，如果你至少提供 30 个反馈回复，我们将创建一个可以审阅的分类器经过改进的版本。 如果改进，可以重新发布分类器。

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

- 与 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 集成后，你可以导入和筛选 Microsoft Defender 的终结点警报，以用于根据新的违反安全策略模板创建的策略检测到的活动。 还有一个相关的内部风险[](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)设置，你可以选择根据 Microsoft Defender for Endpoint 警报会审状态将安全警报导入内部风险管理。

    > [!NOTE]
    > 若要利用 Microsoft Defender for Endpoint 集成 (包括新的安全策略违反模板) ，你需要在组织中配置 Microsoft Defender for Endpoint。 你还需要在 Microsoft Defender for Endpoint 中配置高级功能，为内部风险管理集成启用[Microsoft Defender for Endpoint。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- 创建策略时自定义 [指示器阈值](insider-risk-management-policies.md#create-a-new-policy)。
- 设置 [优先级用户组，](insider-risk-management-settings.md#priority-user-groups-preview) 以根据用户的位置、敏感信息访问级别或风险历史记录等因素来定义组织中需要进一步检查其活动的用户。
- 使用 Office 365 管理活动 API 将 [内部](insider-risk-management-settings.md#export-alerts-preview) 风险警报详细信息导出到组织可能用于管理或聚合内部风险数据的其他应用程序。
- 新 [域](insider-risk-management-settings.md#domains-preview) 设置可帮助您定义和控制特定域中活动的风险级别。

**通信合规性**

- 查看 [警报中的消息](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)时，现在可以删除 Microsoft Teams 频道、一对一和群聊中的不恰当的消息。 已删除的消息和内容将替换为策略提示，说明由于敏感内容而将其删除。
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

 (在预览) 新版本 [的 HR](import-hr-data.md) 连接器允许您导入与作业级别更改、绩效考核和性能改进计划相关的数据。 然后，此数据可用于多个 [内部风险策略，](insider-risk-management-policies.md) 以检测相关活动。

### <a name="retention-labels-new-support-for-email"></a>保留标签：电子邮件的新支持

现在可以创建保留 [标签，](retention.md#retention-labels) 以根据邮件的标记时间开始保留电子邮件。 这不适用于日历项目，日历项目将基于项目发送时间进行保留。

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>敏感度标签：新功能和改进

-  (在预览) 为标签配置加密设置时，请查找使用双密钥加密以进一步保护已标记文件和电子邮件[](encryption-sensitivity-labels.md#double-key-encryption)的新选项。
- 创建或删除敏感度标签或创建、编辑或删除标签策略时，更改现在在 1 小时内同步到所有用户、应用和服务。

## <a name="june-2020"></a>2020 年 6 月

### <a name="spotlight-new-data-connectors-hit-preview"></a>聚焦：新的数据连接器命中预览

基于我们的承诺，帮助您将更多第三方源的数据导入到 Microsoft 365 中，我们乐于宣布再发布两个数据连接器的预览版本：

- [一条"一文"消息](archive-bloomberg-message-data.md)。 从 Bloomberg 邮件协作工具导入和存档金融服务电子邮件数据。 在邮箱中存储数据后，可以访问和使用合规性功能（如诉讼保留、内容搜索、就地存档、审核、通信合规性和保留策略）中的数据。
- [ICE 聊天](archive-icechat-data.md)。 从 ICE 聊天协作工具导入和存档金融服务聊天数据。 在邮箱中存储数据后，可以访问和使用合规性功能（如诉讼保留、电子数据展示、存档、审核、通信合规性和保留策略）中的数据。

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>合规性分数&合规性管理器：命中率不断回来

6 月更新包括合规性分数中的新评估深化 [视图](compliance-score.md)。 监视控制进度、直接从合规性分数添加和删除评估等。

想要随时了解合规性分数和合规性管理器的更新？ 为 [合规性分数发行说明添加](compliance-score-release-notes.md) 书签并经常查看。

## <a name="may-2020"></a>2020 年 5 月

### <a name="spotlight-data-classification-is-officially-released"></a>聚焦：数据分类已正式发布

数据分类（又名"[了解数据](data-classification-overview.md)"、 (分析、内容资源管理器和活动资源管理器) 从预览阶段开始，可供所有组织使用。 强大的见解和工具可帮助发现和评估敏感信息和标签 (保留和敏感度) 整个组织的内容中。 查看包含敏感信息或应用了标签的内容、浏览 Microsoft 365 位置中的标签活动、创建自定义敏感信息类型等。

观看视频教程...

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>可训练分类器：修补程序和特性

可能会为可训练分类器带来更多增强功能：

- 基于反馈的修补程序：为自定义分类器设定种子并训练后，不再需要手动输入 SharePoint 网站 URL 和文件夹路径。 现在，可以从网站和文件夹的预填充列表进行选择。
- 新功能：创建敏感度标签并配置 Office 应用的自动标记设置时，现在可以自动应用 (或建议用户将) 标签应用于与可训练分类器匹配的内容。 [了解更多](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>通信合规性：Yammer 支持在此处

Yammer 中的私人消息和公共社区对话在通信合规性策略中受支持。 Yammer 是可选通道，并且必须位于 [本机模式下](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) ，以支持对邮件和附件的扫描。

### <a name="data-loss-prevention-new-sharing-restriction"></a>数据丢失防护：新的共享限制

设置 DLP 策略以保护 SharePoint 或 OneDrive 中的内容时，现在可以配置"限制对内容的访问"操作，以阻止通过"具有链接的任何人"选项访问内容[](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)的人。

### <a name="insider-risk-management-tailor-your-alert-volume"></a>内部风险管理：定制警报量

为内部风险策略检测到的用户活动分配特定的风险分数，该分数反过来确定警报严重性 (低、中、高) 。 默认情况下，Microsoft 365 会生成一定数量的低、中和高严重性警报，但使用新的警报音量设置，可以增大[](insider-risk-management-settings.md#alert-volume)或减小音量以满足你的需求。

### <a name="pst-import-new-region-supported"></a>PST 导入：支持的新区域

现在可以在阿拉伯联合酋长国进行网络上载。

### <a name="sensitivity-labels-new-privacy-option"></a>敏感度标签：新隐私选项

为标签 [配置](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) 网站和组设置时，现在可以将隐私选项设置为"无"-让用户 **选择谁可以访问网站**。 当你希望使用敏感度标签保护容器中的内容，但仍允许用户自行配置隐私设置时，这非常有用。

## <a name="april-2020"></a>2020 年 4 月

### <a name="records-management-overhauland-a-new-addition"></a>记录管理：检查...和新增功能

4 月包括记录管理解决方案的一些关键更新：

- "记录管理"部分现在在合规中心中完全可用。 利用文件计划、保留标签和标签策略、事件和处置的更新用户界面和功能。
- 关于处置，我们还推出 SharePoint[](disposition.md#disposition-of-records)和 OneDrive 中记录的处置证明。 现在可以在已自动处置或处置评审后看到这些位置中的项目列表。

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>敏感度标签：预览自动标记策略

借助自动标记策略，现在可以自动将敏感度标签应用于已保存的 (的 SharePoint 和 OneDrive 文档（又名"数据处于其余状态) 以及已发送或接收的电子邮件 (也称"传输中的电子邮件) 。 由于此标签由服务而不是应用，因此你无需担心用户拥有哪些应用以及版本。

此功能扩展了创建敏感度标签时"Office 应用的自动标记"设置中已包含的现有客户端标签。 若要快速了解这两种自动标记选项之间的差异和好处，请查看 [更新后的文章](apply-sensitivity-label-automatically.md)。

## <a name="march-2020"></a>2020 年 3 月

### <a name="introducing-advanced-audit"></a>高级审核介绍

[Microsoft 365](advanced-audit.md) 中的高级审核引入了新的审核功能，可帮助组织进行取证和合规性调查。 重点包括长期保留审核日志、自定义 审核日志 保留策略、新的 *MailItemsAccessed* 邮箱审核操作，以及引入新的租户级别限制，这为组织提供了其自己的完全分配的带宽配额来访问审核数据。

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>合规性分数&合规性管理器：预览最新增强功能

此预览版的关键更新包括：

- 创建和修改模板的简化过程
- 模板和操作的版本控制通知和控制
- 跨组同步常见操作
- 现在，语言支持扩展到中文 (简体) 、中文 (繁体) 、法语、德语、意大利语、日语、朝鲜语、葡萄牙语 (巴西) 、俄语和西班牙语

详细了解合规性 [分数](compliance-score.md) 和 [合规性管理器](compliance-manager-overview.md)

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>敏感度标签：支持在 SharePoint 和 OneDrive (预览版中标记 Office) 

启用预览允许用户在 Office 网页版中应用敏感度标签。 他们将能够查看功能区上的"敏感度"按钮和状态栏上的已应用标签名称。 此外，如果他们使用桌面应用标记文件，然后在 SharePoint 或 OneDrive 上保存文件，如果标签应用了加密设置，Microsoft 365 现在将能够处理这些文件的内容。 在这些情况下，还将支持共同授权、电子数据展示、数据丢失防护、搜索和其他协作功能。

[了解如何启用预览](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>2020 年 2 月

### <a name="insider-risk-management-is-officially-released"></a>内部风险管理正式发布

请滚动卷...<br>现在，具有以下订阅的组织可以使用内部风险管理：

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (或试用版) 
- 带 Microsoft E5 合规性加载项的 Microsoft 365 企业版 [E3 订阅](https://go.microsoft.com/fwlink/?linkid=2120432)

请注意，自预览版以来，我们进行了一些改进，包括 [新的角色组](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) 和 [解决方案范围的设置](insider-risk-management-configure.md#step-4-configure-insider-risk-settings)。

与始终一样，请在你使用解决方案时留下反馈，以便我们可以继续改进。

### <a name="records-management"></a>记录管理

此新解决方案将所有记录管理功能放在一个保护之下。 要点包括引入 SharePoint 和 OneDrive 的记录版本控制以及记录的处置证明。

![Microsoft 365 合规中心中的"记录管理"页](../media/mcc-records-management-page.png)

[详细了解记录管理](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>解决方案聚焦：Facebook 和 Twitter 的数据连接器

数据连接器 [于上个月发布](#just-launched) ，我们正在寻找有关测试以下连接器的帮助。

- [Facebook 业务页面](archive-facebook-data-with-sample-connector.md)。 将数据从 Facebook 业务页面导入并存档到 Microsoft 365。 对合规性解决方案（如记录管理和电子数据展示）非常有益。
- [Twitter](archive-twitter-data-with-sample-connector.md)。 将数据从 Twitter 导入并存档到 Microsoft 365。 对合规性解决方案（如记录管理和电子数据展示）非常有益。

在设置和验证这些连接器时，请留下反馈，告诉我们哪些功能良好、哪些没有，以及我们可以如何改进体验。

## <a name="january-2020"></a>2020 年 1 月

等待结束。 我们很高兴地宣布，Microsoft 365 合规中心可供所有使用 Microsoft 365、Office 365、企业移动性 + 安全性 (EMS) 和 Windows 10 企业版计划的客户使用。 在安全与合规中心&管理的任何数据或策略在合规中心内可用，因此无需来回跳转。

现在，添加书签并前往浏览用于跨组织管理合规性的一条一 [https://compliance.microsoft.com](https://compliance.microsoft.com) 线商店...或 [阅读本文](microsoft-365-compliance-center.md) ，进一步深入探究。

![Microsoft 365 合规中心主页](../media/mcc-home-ga.png)

我们还在本月发布了新的和更新的解决方案。 下面简单介绍一下要点。

### <a name="now-in-preview"></a>现在预览版

**内部风险管理 (预览)**

我们乐意地宣布，我们的内部风险管理解决方案现已公开预览版。 简而言之，内部风险管理通过提供：

- 匿名控制，有助于确保用户隐私。
- 具有识别内部威胁（如数据泄露）的本机和第三方指示器的智能策略模板。
- 跨 IT、人力资源和法律团队的集成端到端调查工作流。

我们喜欢听到您的想法。 使用解决方案时，请留下反馈，以便我们可以确保在实现常规可用性时满足你的需求。

[了解有关内部风险管理的更多信息](insider-risk-management.md)

### <a name="just-launched"></a>刚启动

**通信合规性**

从预览阶段到完全可用性，通信合规性是我们新的内部风险解决方案集的关键组成部分。 此可靠的解决方案使用工作流来检测、调查和采取不符合组织标准的邮件的修正操作，以帮助最大程度地降低通信风险。

预览期间的客户反馈非常好。 它带来了一些增强功能，包括入门的首次运行体验、调查和修正操作改进等。

[详细了解通信合规性](communication-compliance.md)

![Microsoft 365 合规中心中的通信合规性页面显示欢迎体验的第一张卡片](../media/mcc-communication-compliance-page-with-fre.png)

**数据连接器**

以前与 Office 36 & 5 安全与合规中心的其他"导入"功能共享空间，数据连接器现在在 Microsoft 365 合规中心有自己的主页。 使用新的"数据连接器"页，将组织的人力资源 (HR)  (文件和各种第三方平台（如 Facebook、LinkedIn、Twitter 和 Instant Bloomberg) ）的数据导入和存档到 Microsoft 365 组织的邮箱。 导入后，可在多个合规性解决方案中管理此数据，包括电子数据展示、内部风险管理、通信合规性、审核、保留策略等。

[详细了解数据连接器](archiving-third-party-data.md)

![Microsoft 365 合规中心的数据连接器页面](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>值得注意的更新

**合规性分数和预览版 (新)**

合规性分数团队始终努力帮助你在不断发展的合规性环境之前取得先机，我们合规性分数团队提供了一组新的模板，可帮助你根据最近的法规评估组织的合规性状态，并获取有关如何实施更有效的控制措施的指导。 你将看到用于：

- ISO/IEC 27701：2019
- 加州消费者隐私法案 (CCPA)
- 巴西一般数据保护法 (（巴西）（ (）- LGPD) 
- SOC 1 类型 2 和 SOC 2 类型 2

[了解有关合规性分数模板更多信息](compliance-score.md#templates)