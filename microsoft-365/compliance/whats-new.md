---
title: Microsoft 365 合规中心更新信息
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 无论是将新解决方案添加到合规中心、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365都可以帮助您随时了解不断变化的合规性环境。 了解我们本月已经进行了哪些工作。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dd85c6c9875fc6e5cf596a4decffdd4fe97d7c4e
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61940934"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 合规中心更新信息

无论是向[Microsoft 365 合规中心](microsoft-365-compliance-center.md)添加新解决方案、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365 都可以帮助您随时了解不断变化的合规性环境。 查看下面的内容，了解当前Microsoft 365的新增功能。

> [!NOTE]
> 一些合规性功能以不同的速度为客户提供推出。 如果尚未看到功能，请尝试将自己添加到 [定向发布](/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 有兴趣了解其他管理中心中如何工作？ 请查看以下文章：
>
> - [最新功能Microsoft 365 管理中心](/office365/admin/whats-new-in-preview)
> - [SharePoint管理中心的新增功能](/sharepoint/what-s-new-in-admin-center)
> - [Microsoft 365 Defender 的新增功能](../security/defender/whats-new.md)
>
> 请访问Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap)，了解Microsoft 365、即将推出、正在开发、已取消或以前发布的新功能。

## <a name="december-2021"></a>2021 年 12 月

### <a name="compliance-and-service-assurance"></a>合规性和服务保证

- [Azure、Dynamics 365](/compliance/regulatory/gdpr-breach-notification)和 Windows GDPR 泄露通知进行了更新，以阐明客户无需使用付费服务（如 Defender for Cloud）接收安全和隐私通知

### <a name="ediscovery"></a>电子数据展示

- [Advanced eDiscovery中的内容](teams-workflow-in-advanced-ediscovery.md#reference-guide)创建工作流 - Microsoft Teams新的可下载快速参考指南更新，用于管理Teams内容Advanced eDiscovery

### <a name="information-governance"></a>信息管理政策

- [在合规中心启用](enable-archive-mailboxes.md#run-diagnostics-on-archive-mailboxes) 存档邮箱 - 新增了有关存档邮箱的新诊断工具的部分
- [使用网络上载将组织的 PST](use-network-upload-to-import-pst-files.md#step-2-upload-your-pst-files-to-microsoft-365)文件导入到 Microsoft 365 - PST 导入现在支持 AzCopy v10
- [还原非活动邮箱](restore-an-inactive-mailbox.md) - 修订了通过先将非活动邮箱的 LegacyExchangeDN 添加到目标邮箱来还原非活动邮箱的过程

### <a name="information-protection"></a>信息保护

- [部署 MIP 解决方案](information-protection-solution.md)- 新的分步指南，适用于正在寻找在 MIP 部署中部署Microsoft 信息保护 (指南) 

### <a name="retention-and-records-management"></a>保留和记录管理

- 保留策略 [生效需要的时间的新指南](create-retention-policies.md#how-long-it-takes-for-retention-policies-to-take-effect)
- 推出的新租户设置：记录管理设置，用于阻止编辑标记为记录和锁定的已标记 SharePoint 项的属性，以及防止用户解锁标记为记录的项的其他设置

### <a name="sensitivity-labels"></a>敏感度标签

- 强制标签和默认标签Power BI通用标签 (通用) 

## <a name="november-2021"></a>2021 年 11 月

### <a name="compliance-manager"></a>合规性管理器

可以在 Microsoft 合规性管理器的新增功能中 [查看新内容更新](compliance-manager-whats-new.md)。

### <a name="device-onboarding"></a>设备载入

添加了以下文章以用于设备载入：

- [将 macOS 设备载入 Microsoft 365 概述（预览版）](device-onboarding-macos-overview.md)
- [使用 Intune 将 macOS 设备载入和卸载到 Microsoft 365 合规性解决方案（预览版）](device-onboarding-offboarding-macos-intune.md)
- [使用适用于 Microsoft Defender for Endpoint 客户的 Intune 将 macOS 设备载入和卸载到合规性解决方案（预览版）](device-onboarding-offboarding-macos-intune-mde.md)
- [使用 JAMF Pro 将 macOS 设备载入和卸载到 Microsoft 365 合规性解决方案（预览版）](device-onboarding-offboarding-macos-jamfpro.md)
- [使用适用于 Microsoft Defender for Endpoint 客户的 JAMF Pro 将 macOS 设备载入和卸载到合规性解决方案（预览版）](device-onboarding-offboarding-macos-jamfpro-mde.md)

### <a name="ediscovery"></a>电子数据展示

- [在将新大小写格式Advanced eDiscovery](advanced-ediscovery-new-case-format.md)正式发布并重命名为"大案例格式"后，使用新大小写格式

### <a name="retention-and-records-management"></a>保留和记录管理
- 推出：用于控制用户是否可以删除SharePoint和OneDrive标记项目的新记录管理设置。 以前，如果 SharePoint 中允许此操作，则配置为保留内容且未将项目标记为记录的保留标签会阻止用户删除 SharePoint 中的OneDrive。 有关详细信息，请参阅保留如何[适用于SharePoint和OneDrive。](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive)

### <a name="sensitive-information-types"></a>敏感信息类型

新增了以下文章：

- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md)
- [基于精确数据匹配的敏感信息类型入门](sit-get-started-exact-data-match-based-sits-overview.md)
- [为基于精确数据匹配的敏感信息类型导出源数据](sit-get-started-exact-data-match-export-data.md)
- [为基于精确数据匹配的敏感信息类型创建架构](sit-get-started-exact-data-match-create-schema.md)
- [为基于精确数据匹配的敏感信息类型哈希并上传敏感信息源表](sit-get-started-exact-data-match-hash-upload.md)
- [创建基于精确数据匹配的敏感信息类型/规则包](sit-get-started-exact-data-match-create-rule-package.md)
- [测试基于精确数据匹配的敏感信息类型](sit-get-started-exact-data-match-test.md)
- [管理精确数据匹配架构](sit-use-exact-data-manage-schema.md)
- [刷新敏感信息源表文件](sit-use-exact-data-refresh-data.md)

### <a name="sensitivity-labels"></a>敏感度标签
- Azure Azure 标签的范围 [名称现在](/azure/purview/create-sensitivity-label) 为"架构化数据资产"。

## <a name="october-2021"></a>2021 年 10 月

### <a name="app-governance"></a>应用治理

- [适用于云应用的 Defender 的应用管理加载项已发布到正式发布](/cloud-app-security/app-governance-manage-app-governance)。 应用管理文档已移至加入 Defender for Cloud Apps 文档。

### <a name="compliance--service-assurance"></a>合规性&服务保证

- [服务保证](/compliance) - 每季度查看内容更新，以验证数据中心) 认证和适用性声明
  - 数据中心体系结构和基础结构
  - 数据中心业务连续性和灾难恢复
  - 数据中心环境安全措施
  - 数据中心物理访问安全性
  - Microsoft 365 SDL 合规性计划
  - Microsoft 365 服务工程师访问控制
  - MS 云风险评估指南

### <a name="data-loss-prevention"></a>数据丢失防护

- [了解数据丢失防护已](endpoint-dlp-learn-about.md) 针对 macOS 支持和高级分类进行更新;更新了用于创建自定义 DLP 策略以审核所有受支持的文件类型的活动。
- [终结点数据丢失防护Microsoft 365](endpoint-dlp-getting-started.md) macOS 支持和高级分类的终结点数据丢失防护入门。
- [已针对](endpoint-dlp-using.md) macOS 支持和高级分类更新了使用终结点数据丢失防护。
- [数据丢失防护策略提示参考](dlp-policy-tips-reference.md) 已针对 macOS 支持和高级分类进行了更新。
- [将 macOS 设备载入Microsoft 365 (预览](device-onboarding-macos-overview.md)) 针对 macOS 支持和高级分类进行了更新。
- 添加了以下用于载入设备的新页面：
  - [使用 Intune 将 macOS 设备载入和卸载到 Microsoft 365 合规性解决方案（预览版）](device-onboarding-offboarding-macos-intune.md)
  - [使用适用于 Microsoft Defender for Endpoint 客户的 Intune 将 macOS 设备载入和卸载到合规性解决方案（预览版）](device-onboarding-offboarding-macos-intune-mde.md)
  - [使用 JAMF Pro 将 macOS 设备载入和卸载到 Microsoft 365 合规性解决方案（预览版）](device-onboarding-offboarding-macos-jamfpro.md)
  - [使用适用于 Microsoft Defender for Endpoint 客户的 JAMF Pro 将 macOS 设备载入和卸载到合规性解决方案（预览版）](device-onboarding-offboarding-macos-jamfpro-mde.md)

### <a name="ediscovery"></a>电子数据展示

- 在[Advanced eDiscovery](advanced-ediscovery-cloud-attachments.md)中收集云附件除了收集云附件的最新版本之外，还可以收集电子邮件或 Teams 聊天对话中共享的版本;通过自动将保留标签自动应用于云附件的新功能，可以收集共享版本。
- 在[Advanced eDiscovery](advanced-ediscovery-historical-versions.md)中设置历史版本新功能，此功能对存储在 SharePoint 网站上的所有文档版本进行索引以用于搜索;这意味着搜索结果中将返回包含与集合查询匹配的内容的文档版本。

### <a name="encryption"></a>加密

- [对一对一呼叫](/microsoftteams/teams-end-to-end-encryption)使用端到端加密Microsoft Teams公共 (预览) 公共预览的新内容。

### <a name="information-governance"></a>信息管理政策

- [设置连接器以导入一个将管理中心 EHR](import-epic-data.md) 审核数据导入新连接器，可让你从"电子医疗保健记录系统"导入数据，以支持新的常规患者数据滥用方案，用于内部风险管理。
- [通过设置连接器](import-healthcare-data.md) 以导入医疗保健 EHR 审核数据新连接器，你可以从电子医疗保健记录系统导入数据，以支持针对内部风险管理的新一般患者数据滥用方案。

### <a name="retention-and-records-management"></a>保留和记录管理
- [自适应策略范围](retention.md#adaptive-or-static-policy-scopes-for-retention) 在预览版中发布，用于保留策略和保留标签策略。
- 你现在可以 [基于敏感度标签自动应用保留标签](apply-retention-labels-automatically.md#identify-files-and-emails-that-have-a-sensitivity-label)。
- 文件计划具有新的 [导入过程](file-plan-manager.md#import-retention-labels-into-your-file-plan)。
- [保留策略和保留](retention-settings.md)标签策略的常见设置：有关在保留策略和保留标签策略中配置自适应范围和其他设置的详细信息的新文章。

### <a name="sensitive-information-types"></a>敏感信息类型

- [了解命名实体 (预览) ](named-entities-learn.md) 命名实体的新内容。
- [使用数据丢失防护策略中的命名实体， (使用 ](named-entities-use.md)) 实体时预览新内容。

### <a name="sensitivity-labels"></a>敏感度标签

- [向符合条件的客户推出](mip-easy-trials.md) 默认标签和默认策略。

## <a name="september-2021"></a>2021 年 9 月

### <a name="app-governance"></a>应用治理

- [简化的应用治理入门信息已更改](app-governance-get-started.md) 工作流，并新增了指向公共预览版注册的链接
- [添加了新的检测警报定义](app-governance-anomaly-detection-alerts.md#app-made-high-volume-of-importance-mail-read-and-created-inbox-rule) (更新;添加了集合警报集合的新) 

### <a name="auditing"></a>审核

- [打开或关闭审核](turn-audit-log-search-on-or-off.md)新增了如何审核组织中审核状态更改的部分;这意味着审核记录在审核打开或关闭时进行记录;你可以搜索Exchange管理员审核日志这些审核记录

### <a name="communication-compliance"></a>通信合规性

- [SIEM 解决方案通信合规性指南](communication-compliance-siem.md) ，用于与 SIEM 解决方案和 SIEM 解决方案) 

### <a name="compliance-offerings"></a>合规性产品/服务

- [MTCS (多层云) ](/compliance/regulatory/offering-mtcs-singapore) Dynamics 365 覆盖范围的新加坡标准更新
- [支付卡行业 (PCI) ](/compliance/regulatory/offering-pci-dss)Data Security Standard (DSS) Online SharePoint更新
- [美国第 508 节](/compliance/regulatory/offering-section-508-vpats) 新的客户端软件指南
- [Web 内容辅助功能指南](/compliance/regulatory/offering-wcag-2-1) 新的客户端软件指南

### <a name="compliance--service-assurance"></a>合规性&服务保证

- [服务保证](/compliance/) 季度检查内容更新的认证和适用性声明
  - 数据承载设备破坏
  - DDOS 攻击

### <a name="data-connectors"></a>数据连接器

- [从](archiving-third-party-data.md#data-connectors-in-the-us-government-cloud)CellTrust 和 17a-4 LLC Microsoft 365数据连接器中存档第三方数据现在在美国政府云中的 GCC 组织中可用
- [设置连接器以存档 YouTube 数据](archive-youtube-data.md) 为公共预览版中的此功能提供了新的指南。

### <a name="ediscovery"></a>电子数据展示

- 使用[KQL](ediscovery-kql-editor.md)编辑器构建搜索查询公共预览，这是在内容搜索、核心电子数据展示和 Advanced eDiscovery 中创建搜索查询的一种新方式;KQL 编辑器为受支持的可搜索属性和条件提供自动完成，并显示标准属性和条件的支持值列表;KQL 编辑器还提供了错误检测和针对搜索查询中潜在错误的修复建议

### <a name="information-barriers"></a>信息屏障

- [针对信息屏障模式](information-barriers-policies.md#step-6-information-barriers-modes) 的信息屏障新预览功能入门
- [信息屏障Microsoft Teams](/microsoftteams/information-barriers-in-teams)信息屏障模式的新预览功能
- [信息屏障OneDrive](/onedrive/information-barriers)信息屏障模式的新预览功能
- [针对信息屏障模式SharePoint](/sharepoint/information-barriers)联机新预览功能的信息障碍

### <a name="insider-risk-management"></a>内部风险管理

- [开始使用内部风险管理新](insider-risk-management-configure.md#recommended-actions-preview) 预览功能，了解入门建议操作
- [调查内部风险活动新的](insider-risk-management-activities.md#get-help-managing-your-insider-risk-alert-queue) "获取有关管理内部风险警报队列的帮助"指导部分
- [内部风险管理设置入门 新的](insider-risk-management-settings.md#admin-notifications) 管理员通知设置预览功能

### <a name="retention-and-records-management"></a>保留和记录管理
- [多阶段处置评审](disposition.md) 现已在 GA (中) ，并提供了 [新的审核事件](search-the-audit-log-in-security-and-compliance.md#disposition-review-activities)。 多阶段处置评审允许你为保留标签指定最多五个连续的处置评审阶段，审阅者可以将其他用户添加到其处置评审阶段。 你还可以自定义电子邮件通知和提醒。
- 有关保留策略[Teams频道现已](create-retention-policies.md#retention-policy-for-teams-locations)在 GA (中) 。

### <a name="sensitivity-labels"></a>敏感度标签
- [](sensitivity-labels-coauthoring.md)共同创作和自动保存现已从当前频道或每月 Enterprise 频道) 和 macOS (最低版本 16.51) 中针对 Windows (最低版本 2107 提供 (GA) 。
- 推出适用于Office内置标签的应用：默认标签设置现在支持现有文档和新文档。 这种行为更改提供了与 Azure 信息保护统一标记客户端同等的功能。 有关每个应用的推出和最低版本的详细信息，请参阅 word、Excel 和 PowerPoint 的 [功能表](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint)。
- 容器标签现在 [使用 PowerShell 高级设置支持默认共享链接设置](sensitivity-labels-teams-groups-sites.md#configure-settings-for-the-default-sharing-link-for-a-site-by-using-powershell-advanced-settings)。
- [列出内置标签的最低](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)受支持版本的功能表现在具有当前频道、每月 Enterprise 频道和 Semi-Annual Enterprise 频道的版本。

## <a name="august-2021"></a>2021 年 8 月

### <a name="app-governance"></a>应用治理
- [警报见解的扩展条目](app-governance-anomaly-detection-alerts.md#collection-alerts)。 添加了新条目来描述应用管理中现在可用的其他警报见解。

### <a name="communication-compliance"></a>通信合规性
- [通信合规性通道](communication-compliance-channels.md)新增了对私人聊天和频道中的新式附件扫描Teams预览功能支持。

### <a name="compliance--service-assurance"></a>合规性&服务保证

- [服务保证](/compliance/) 已更新，每季度查看认证和适用性声明的内容更新：
  - 体系结构
  - 审核日志记录
  - 加密和密钥管理
  - 标识和访问管理
  - Microsoft 365访问管理
  - 网络安全性
  - 隐私
  - 弹性和连续性
  - 风险管理
  - 安全开发和运营
  - 安全监视
  - 供应商管理
  - 漏洞管理

### <a name="data-loss-prevention"></a>数据丢失防护

- [数据丢失防护策略参考](dlp-policy-reference.md)。 添加了一个新的策略参考页，可帮助你创建策略。

### <a name="insider-risk-management"></a>内部风险管理
- [了解并配置内部风险管理浏览器信号检测](insider-risk-management-browser-support.md)。 用于配置 Edge 和 Chrome 浏览器的浏览器信号检测的预览功能。

### <a name="retention-and-records-management"></a>保留和记录管理
- [用于确定何时保留](retention-flowchart.md) 或永久删除项目以补充保留原则的概念和示例的流程图。

### <a name="sensitivity-labels"></a>敏感度标签
- [](apply-sensitivity-label-automatically.md)自动标记策略的增强功能，包括网站和策略支持的数量更高、支持所有 OneDrive 和 SharePoint 网站以及选择可用的 SharePoint 网站（而不必按 URL 输入每个站点）以及模拟改进。
- 在应用中自动标记Office敏感度标签设置现在支持精确数据匹配[ (EDM) 。 ](apply-sensitivity-label-automatically.md#custom-sensitive-information-types-with-exact-data-match)
- 默认标签现在扩展到预览Power BI ([预览) 。 ](/power-bi/admin/service-security-sensitivity-label-default-label-policy)
- 活动资源管理器Outlook 网页版应用的审核事件现已全面推出[](data-classification-activity-explorer-available-events.md)，这意味着内置标签的用户活动现在可用于所有平台Office应用。
- 支持[](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)的功能表新增了 Windows 的脚注，以阐明最低版本适用于当前频道，并提供了一条提示，以便更轻松地比较省略前导零的旧版本与较新版本。

## <a name="july-2021"></a>2021 年 7 月

### <a name="advanced-ediscovery"></a>高级电子数据展示

- [Advanced eDiscovery工作流中](teams-workflow-in-advanced-ediscovery.md)的内容Microsoft Teams添加了用于管理 Advanced eDiscovery 中 Teams 内容的端到端工作流;包括有关新对话脚本功能的预览的详细信息。
- [使用新案例格式Advanced eDiscovery](advanced-ediscovery-new-case-format.md)添加了新案例格式的预览，该预览扩展了审阅集和案例限制，并支持 Teams 和 Yammer 对话的对话脚本。

### <a name="app-governance"></a>应用治理

- MCAS [Microsoft Cloud App Security (](app-governance-manage-app-governance.md)管理) 已进入公共预览阶段。 应用管理可监视 M365 租户中基于 OAUth 的应用，并针对可能表示恶意软件或权限级别不当的活动生成警报。

### <a name="compliance-offerings"></a>合规性产品/服务

- [合规性产品](/compliance/regulatory/offering-home) /服务更改侧重于适用的服务范围和更新，以便与 [适用法规的 Azure](/azure/compliance) 产品/服务更加一致。

### <a name="compliance--service-assurance"></a>合规性&服务保证

- [服务保证](/compliance/) (更新;每季度查看内容更新，获取认证和适用性) 
    - 云背景检查
    - 员工转移&终止
    - 管控
    - 人力资源
    - 事件管理
    - 岗前调查
    - 安全事件管理 (SIM 卡) 
    - SIM – 抑制、抑制和恢复
    - SIM – 检测&分析
    - SIM – 事件后报告
    - SIM – 准备
    - 租户隔离

### <a name="data-classification"></a>数据分类

- [了解数据分类](data-classification-overview.md)。 针对 GA 发布的可训练分类器进行了更新。

### <a name="data-loss-prevention"></a>数据丢失防护

- [了解终结点Microsoft 365](endpoint-dlp-learn-about.md)数据丢失防护新增了有关设备始终审核文件活动的更新指导。
- [开始使用针对](dlp-on-premises-scanner-get-started.md) GA 版本更新的数据丢失防护本地扫描程序。
- [了解针对 GA Microsoft 365更新](dlp-on-premises-scanner-learn.md)的数据丢失防护本地扫描程序。
- [使用Microsoft 365 GA](dlp-on-premises-scanner-use.md)版本更新的数据丢失防护本地扫描程序。
- [对针对](dlp-use-policies-non-microsoft-cloud-apps.md) GA 版本和 MIP-MCAS 集成更新的非 Microsoft 云应用使用数据丢失防护策略。

### <a name="insider-risk-management"></a>内部风险管理

- [调查内部风险管理活动](insider-risk-management-activities.md) 为新的用户活动报告和新的消除多个警报预览功能添加了内容更新。
- [开始使用内部风险管理设置添加了](insider-risk-management-settings.md) 新 RBAC 功能的内容更新，以选择优先用户组预览功能的审阅者。

### <a name="privacy-management"></a>隐私管理

- Microsoft [隐私管理](/privacy/solutions/privacymanagement/privacy-management) 已进入公共预览阶段。 隐私管理可帮助你的组织了解和管理你的Microsoft 365、修正潜在的隐私风险以及履行主体权利请求。

### <a name="retention-and-records-management"></a>保留和记录管理
- 预览版[：Teams](create-retention-policies.md#retention-policy-for-teams-locations)保留策略现在支持私人频道作为Teams或编辑保留策略时的新频道位置
- 导入 [文件计划的说明](file-plan-manager.md#import-retention-labels-into-your-file-plan) 已更新，以包含每个条目的法规记录和依赖关系

### <a name="sensitive-information-types"></a>敏感信息类型

添加了以下页面：

- [自定义敏感信息类型筛选器参考](sit-custom-sit-filters.md)
- [使用 PowerShell 修改自定义敏感信息类型](sit-modify-a-custom-sensitive-information-type-in-powershell.md)
- [使用 PowerShell 删除自定义敏感信息类型](sit-remove-a-custom-sensitive-information-type-in-powershell.md)

### <a name="sensitivity-labels"></a>敏感度标签
- 可训练分类器现已在 GA () 中普遍可用，可用于 Office [Windows](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)应用和 (Office Online) 
- 强制标签现在扩展到预览Power BI ([中) ](/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy)
- 对于 [使用敏感度标签加密]( sensitivity-labels-coauthoring.md)的文件共同创作：推出对将敏感度标签用作条件和电子邮件未加密附件的 DLP 策略的支持
- 适用于 Outlook 的审核事件现在适用于 macOS、iOS 和 Android，并且适用于 Outlook 网页版
