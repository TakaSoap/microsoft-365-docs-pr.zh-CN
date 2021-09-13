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
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 无论是将新解决方案添加到合规中心、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365都可以帮助您随时了解不断变化的合规性环境。 了解我们本月已经进行了哪些工作。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 498d88e2a75a0485043297eebf27c3da014a63b9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59196822"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 合规中心更新信息

无论是向[Microsoft 365 合规中心](microsoft-365-compliance-center.md)添加新解决方案、根据反馈更新现有功能，还是推出最新更新的文档，Microsoft 365都可以帮助您随时了解不断变化的合规性环境。 查看下面的内容，了解当前Microsoft 365的新增功能。

> [!NOTE]
> 一些合规性功能以不同的速度为客户提供推出。 如果尚未看到功能，请尝试将自己添加到 [定向发布](/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 有兴趣了解其他管理中心中如何工作？ 请查看以下文章：
>
> - [最新功能Microsoft 365 管理中心](/office365/admin/whats-new-in-preview)
> - [SharePoint管理中心的新增功能](/sharepoint/what-s-new-in-admin-center)
> - [Microsoft 365 Defender 的新增功能](../security/defender/whats-new.md)
>
> 请访问Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap)，了解Microsoft 365、即将推出、正在开发、已取消或之前发布的新功能。

## <a name="august-2021"></a>2021 年 8 月

### <a name="app-governance"></a>应用治理
- [警报见解的扩展条目](app-governance-anomaly-detection-alerts.md#collection-alerts)。 添加了新条目来描述应用管理中现在可用的其他警报见解。

### <a name="communication-compliance"></a>通信合规性
- [通信合规性功能参考](communication-compliance-feature-reference.md)新增了对专用聊天和频道中的新式Teams功能支持。

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
- [](apply-sensitivity-label-automatically.md#recent-enhancements-for-auto-labeling-policies)自动标记策略的增强功能，这些策略包括网站和策略支持的数量更高、支持所有 OneDrive 和 SharePoint 网站以及选择可用的 SharePoint 网站（而不必按 URL 输入每个站点）以及模拟改进。
- 在应用中自动标记Office敏感度标签设置现在支持精确数据匹配[ (EDM) 。 ](apply-sensitivity-label-automatically.md#custom-sensitive-information-types-with-exact-data-match)
- 默认标签现在扩展到预览Power BI ([预览) 。 ](/power-bi/admin/service-security-sensitivity-label-default-label-policy)
- 活动资源管理器Outlook 网页版图面的审核事件[](data-classification-activity-explorer-available-events.md)现已全面推出，这意味着内置标签的用户活动现在可用于所有平台Office应用。
- 支持[](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)的功能表具有 Windows 的新脚注以阐明最低版本适用于当前频道，并提供了一条提示，以便更轻松地将省略前导零的旧版本与较新版本进行比较。

## <a name="july-2021"></a>2021 年 7 月

### <a name="advanced-ediscovery"></a>高级电子数据展示

- [Advanced eDiscovery使用大Microsoft Teams](teams-workflow-in-advanced-ediscovery.md)中的内容创建工作流添加了一个端到端工作流，用于管理 Teams Advanced eDiscovery 中的内容;包括有关新对话脚本功能的预览的详细信息。
- [使用大Advanced eDiscovery](advanced-ediscovery-large-cases.md)添加了新大案例格式的预览，该预览扩展了审阅集和事例限制，并支持 Teams 和 Yammer 对话的对话脚本。

### <a name="app-governance"></a>应用治理

- MCAS [Microsoft Cloud App Security (](app-governance-manage-app-governance.md)管理) 已进入公共预览阶段。 应用管理可监视 M365 租户中基于 OAUth 的应用，并针对可能表示恶意软件或权限级别不当的活动生成警报。

### <a name="compliance-offerings"></a>合规性产品/服务

- [合规性产品](/compliance/regulatory/offering-home) /服务更改侧重于适用的服务范围和更新，以便与 [适用法规的 Azure](/azure/compliance) 产品/服务更加一致。

### <a name="compliance--service-assurance"></a>合规性&服务保证

- [服务保证](/compliance/) (更新;每季度查看内容更新，获取认证和适用性) 
    - 云背景检查
    - 员工转移&终止
    - 治理
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

- [了解Microsoft 365终结点数据丢失防护](endpoint-dlp-learn-about.md)添加了有关设备始终审核文件活动的更新指导。
- [开始使用针对](dlp-on-premises-scanner-get-started.md) GA 版本更新的数据丢失防护本地扫描程序。
- [了解针对 GA Microsoft 365更新](dlp-on-premises-scanner-learn.md)的数据丢失防护本地扫描程序。
- [使用Microsoft 365 GA](dlp-on-premises-scanner-use.md)版本更新的数据丢失防护本地扫描程序。
- [对针对](dlp-use-policies-non-microsoft-cloud-apps.md) GA 版本和 MIP-MCAS 集成更新的非 Microsoft 云应用使用数据丢失防护策略。

### <a name="insider-risk-management"></a>内部风险管理

- [调查内部风险管理活动](insider-risk-management-activities.md) 为新的用户活动报告和新的消除多个警报预览功能添加了内容更新。
- [开始使用内部风险管理设置添加了](insider-risk-management-settings.md) 新 RBAC 功能的内容更新，以选择优先用户组预览功能的审阅者。

### <a name="privacy-management"></a>隐私管理

- Microsoft [隐私管理](privacy-management.md) 已进入公共预览阶段。 隐私管理可帮助你的组织了解和管理Microsoft 365环境中的个人数据、修正潜在的隐私风险以及履行主体权利请求。

### <a name="retention-and-records-management"></a>保留和记录管理
- 预览版[：Teams](create-retention-policies.md#retention-policy-for-teams-locations)保留策略现在支持私人频道作为Teams或编辑保留策略时的新频道位置
- 导入 [文件计划的说明](file-plan-manager.md#import-retention-labels-into-your-file-plan) 已更新，以包含每个条目的法规记录和依赖关系

### <a name="sensitive-information-types"></a>敏感信息类型

添加了以下页面：

- [自定义敏感信息类型筛选器参考](sit-custom-sit-filters.md)
- [使用 PowerShell 修改自定义敏感信息类型](sit-modify-a-custom-sensitive-information-type-in-powershell.md)
- [使用 PowerShell 删除自定义敏感信息类型](sit-remove-a-custom-sensitive-information-type-in-powershell.md)

### <a name="sensitivity-labels"></a>敏感度标签
- 可训练分类器现在通常 (GA) ，用于 Office for [Windows](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)和 Web (Office Online) 
- 强制标记现在扩展到预览Power BI ([中) ](/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy)
- 对于 [使用敏感度标签加密]( sensitivity-labels-coauthoring.md)的文件共同创作：推出对将敏感度标签用作条件和电子邮件未加密附件的 DLP 策略的支持
- 适用于 Outlook 的审核事件现在适用于 macOS、iOS 和 Android，并且适用于 Outlook 网页版

## <a name="june-2021"></a>2021 年 6 月

### <a name="customer-key"></a>客户密钥

- [使用客户密钥加密 (](customer-key-overview.md)客户密钥租户级别 DEP 现在加密 Microsoft 信息保护.) 

### <a name="data-connectors"></a>数据连接器

- 我们已与 [17a-4 LLC](archiving-third-party-data.md#17a-4-data-connectors) 合作发布了 17 个新的数据连接器，与 [CellTrust](archiving-third-party-data.md#celltrust-data-connectors)合作发布了一个新连接器。 我们还发布了其他数据连接器，这些连接器与[具有合作关系的具有合作关系的"百](archiving-third-party-data.md#veritas-data-connectors)米"和["TeleMessage"。](archiving-third-party-data.md#telemessage-data-connectors) 到目前为止，共有 65 个可用的数据连接器可用于将第三方数据导入和存档到Microsoft 365。

### <a name="ediscovery"></a>电子数据展示

- [使用新的](review-set-search.md) UX 格式 (查询和筛选审阅集内容，以筛选和搜索审阅集内容的新) 
- [使用新标记功能和](tagging-documents.md)UX Advanced eDiscovery (审阅集内的文档标记文档，以便更快、更轻松地标记审阅集内的文档;包括使用查询和筛选器根据项目标记项目来快速查找或排除审阅集项的新功能) 
- [为电子数据展示](set-up-compliance-boundaries.md)调查设置合规性 (Microsoft 已取消联系 MS 支持以请求将合规性属性同步到OneDrive的要求;现在，使用邮箱搜索权限筛选器强制实施邮箱搜索权限OneDrive) 

### <a name="sensitivity-labels"></a>敏感度标签

- 敏感度标签策略向导现在支持Outlook标签[](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling)和强制标签的特定选项，作为比 (仍受支持的) PowerShell 高级设置更简单的配置。
- 现已[推出 Word、Excel](sensitivity-labels-office-apps.md#dynamic-markings-with-variables )和 PowerPoint web 版
- 对于[自动标记策略](apply-sensitivity-label-automatically.md)Exchange，如果标签配置为加密，则不应用该加密。 此外Exchange自动标记策略，现在可以配置例外和以下新条件：主题、收件人地址或发件人地址匹配模式;收件人地址包含词语;sender domain is， recipient is a member of;sender 是。
- 将敏感度标签与团队、组和网站一同使用时，可以将 Set-SPOTenant 与 BlockSendLabelMismatchEmail 参数一同使用，以防止在记录审核事件检测到文档敏感度不匹配时自动生成的电子邮件。  有关详细信息，请参阅审核 [敏感度标签活动](sensitivity-labels-teams-groups-sites.md#auditing-sensitivity-label-activities )。
- 现在 [，敏感度](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) 标签的身份验证上下文设置已完全推出预览版。 此外，此配置现在受 Microsoft Teams。
- 为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签后，现在可以在 Office 网页版 中打开由服务原则名称 (（如 Microsoft Cloud App Security) ）标记和加密然后上传到 SharePoint 和[OneDrive 的文件](sensitivity-labels-sharepoint-onedrive-files.md)。
- [](sensitivity-labels-coauthoring.md)使用版本 2105 时，共同创作和自动保存不再局限于测试租户，现在支持在生产中：6 月 18 日针对 Windows，版本 16.50+ for macOS。 请注意，此功能仍不受 iOS 和 Android 支持，仍保持预览状态。

## <a name="may-2021"></a>2021 年 5 月

### <a name="data-loss-prevention"></a>数据丢失防护

- 规划数据丢失 [防护策略的新](dlp-overview-plan-for-dlp.md) 指南。

### <a name="retention-and-records-management"></a>保留和记录管理

- 如果从 SharePoint 或 OneDrive 帐户发布保留策略，则无需再等待 30 天的宽限期，然后才能删除站点或帐户。 客户提出的一个热门请求，此更改现已针对所有租户完成。
- 在预览版 **中**，多阶段处置评审：管理员现在可以为保留标签添加最多五个连续的 [](disposition.md)处置评审阶段，审阅者可以将其他用户添加到其处置评审阶段。 你还可以自定义电子邮件通知和提醒。

### <a name="sensitive-information-types"></a>敏感信息类型

- 新增了可帮助您修改 [关键字词典的信息](sit-modify-keyword-dictionary.md)。

### <a name="sensitivity-labels"></a>敏感度标签

- 在预览版中，当您为组和网站配置敏感度标签时，身份验证[上下文的新设置现在可用](sensitivity-labels-teams-groups-sites.md)。 此选项与 Azure AD 条件访问策略结合使用，以在用户访问应用了标签SharePoint网站时强制实施更严格的条件。 在配置此设置 [之前，请务必](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) 先阅读依赖项和限制。
- [仅针对 Exchange](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)配置的自动标记策略现在支持敏感度标签，这些标签使用"允许用户分配不要转发"或"Encrypt-Only权限"来应用加密。
- [强制标记现在](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents)适用于所有平台Office应用。

## <a name="april-2021"></a>2021 年 4 月

### <a name="advanced-ediscovery"></a>高级电子数据展示

- [中Advanced eDiscovery。](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set) 组织现在可以在一次从审阅集导出项目时导出多达 500 万个项目或 500 MB（以较小者为准）。

### <a name="data-classification"></a>数据分类

- [活动资源管理器中可用的标记活动](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>数据连接器

- [设置连接器以在 Oracle 数据上存档 Cisco Jabber](/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [设置连接器以在 PostgreSQL 数据上存档 Cisco Jabber](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>数据丢失防护

- 数据丢失防护 [策略提示的新主题参考](/microsoft-365/compliance/dlp-policy-tips-reference)。
- 了解数据丢失 [防护的新主题](/microsoft-365/compliance/dlp-learn-about-dlp)。
- 数据丢失防护警报 [仪表板入门的新主题](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)。

### <a name="retention-policies-and-retention-label-policies"></a>保留策略和保留标签策略

- "Microsoft 365 组"位置现在支持将保留设置仅应用于 Microsoft 365 邮箱，或仅将 [Set-RetentionCompliancePolicy PowerShell](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet 与 Applications 参数一同应用于连接的 SharePoint *站点*。

### <a name="sensitivity-labels"></a>敏感度标签

Outlook版本和更新：

- [默认标签和强制标签的不同](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) 设置现在支持内置标签。 以前，仅 AIP 统一标记客户端支持这些设置。
- [](encryption-sensitivity-labels.md#let-users-assign-permissions) macOS、iOS 和 Android 现在支持仅加密。
- [强制标记](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) 将推出到其余平台。
- [所有客户端都支持](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)使用所有变量的动态Outlook标记。

## <a name="march-2021"></a>2021 年 3 月

下面是对 3 月Microsoft 365合规性解决方案和内容的一些更改。

### <a name="advanced-ediscovery"></a>高级电子数据展示

- **Advanced eDiscovery集合** 现在支持 [新的集合工具和工作流](/microsoft-365/compliance/collections-overview)。 其他新主题包括[创建草稿集合](/microsoft-365/compliance/create-draft-collection)、[将草稿集合提交到审阅集](/microsoft-365/compliance/commit-draft-collection)[以及集合统计信息和报告](/microsoft-365/compliance/collection-statistics-reports)。
- **将审阅** 集内的文档 [导出到Azure 存储](/microsoft-365/compliance/download-export-jobs)帐户。
- **用于预测编码模块Advanced eDiscovery。** 首先 [查看替换停用](/microsoft-365/compliance/predictive-coding-overview) 的相关性模块的新预测编码功能。

### <a name="data-classification"></a>数据分类

- **数据分类资源管理器**。 [数据](/microsoft-365/compliance/data-classification-activity-explorer) 分类资源管理器入门。

### <a name="data-connectors"></a>数据连接器

- **私钥 。** 对私钥的支持已添加到 Bloomberg [邮件](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) 数据 [、ICE 聊天](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) 数据和 [Instant Bloomberg](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys) 数据连接器。

### <a name="data-loss-prevention"></a>数据丢失防护

- **Microsoft Teams支持**。 数据丢失防护支持扩展到[Microsoft Teams](/microsoft-365/compliance/dlp-teams-default-policy)。
- **Microsoft 合规性扩展**。 Microsoft 合规性 [扩展入门](/microsoft-365/compliance/dlp-chrome-get-started)。

### <a name="encryption"></a>加密

- **客户密钥Microsoft 365。** [租户级别的客户密钥](/microsoft-365/compliance/customer-key-tenant-level)Microsoft 365公共预览版 (客户) 。
- **双密钥加密**。 了解有关在文档[和文档中](/microsoft-365/compliance/double-key-encryption)启用对已标记和受保护SharePoint OneDrive for Business。

### <a name="insider-risk-management"></a>内部风险管理

以下内部风险管理功能更新于 3 月发布公开预览版：

- 用于创建内部风险策略之前识别风险的新分析功能
- 新的风险活动序列检测支持和管理
- 新的累积 exfiltration 检测支持
- 新的应用内策略运行状况报告和建议支持
- 新的审核日志功能和报告
- 策略创建向导的增强功能
- 内容资源管理器更新
- 新用户管理过程/支持 (策略策略中添加/删除) 
- 新的 AAD 集成支持 (离开的用户策略支持) 
- 更新了 REGEX 策略 (域) 
- 策略模板增强功能和改进

更新或添加了以下主题以支持这些新功能：

- [了解内部风险管理](/microsoft-365/compliance/insider-risk-management)
- [内部风险管理计划](/microsoft-365/compliance/insider-risk-management-plan)
- [内部风险管理设置入门](/microsoft-365/compliance/insider-risk-management-settings)
- [内部风险管理入门](/microsoft-365/compliance/insider-risk-management-configure)
- [创建和管理内部风险策略](/microsoft-365/compliance/insider-risk-management-policies)
- [调查内部风险警报](/microsoft-365/compliance/insider-risk-management-alerts)
- [对内部风险案例采取措施](/microsoft-365/compliance/insider-risk-management-cases)
- [与内部风险审核日志一起查看活动](/microsoft-365/compliance/insider-risk-management-audit-log)
- [使用内部风险内容资源管理器查看数据](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [使用用户仪表板管理工作流](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>记录管理

- **文件计划改进**。 文件计划 [更新将](file-plan-manager.md) 删除或改进以前的导入长度限制。
- **删除记录的保留标签**。 预览版本支持删除 [将项目标记为记录的](create-apply-retention-labels.md#deleting-retention-labels) 保留标签。

### <a name="sensitive-information-types"></a>敏感信息类型

在下列主题中添加或更新了内容：

- [自定义敏感信息类型入门](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [了解敏感信息类型](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [使用基于精确数据匹配的分类创建自定义敏感信息类型](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [创建精确数据匹配活动通知](/microsoft-365/compliance/sit-edm-notifications-activities)
- [敏感信息类型实体定义](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [使用 PowerShell 创建自定义敏感信息类型](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [创建关键字字典](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>敏感度标签

- **DoD 支持**。 支持具有 DoD 环境的美国政府租户。
- **仅对加密Outlook。** 选择"允许用户分配Outlook时，Encrypt-Only加密选项[现在包括加密选项](encryption-sensitivity-labels.md#let-users-assign-permissions)。
- **强制在应用中Office标签**。 更新[了](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client)在安装 Azure 信息保护统一标签客户端Office应用中强制执行内置标签的指南。
