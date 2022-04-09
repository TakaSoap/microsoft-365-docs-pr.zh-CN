---
title: Defender for Office 365的安全操作指南
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 用于 SecOps 人员管理Microsoft Defender for Office 365的规范性 playbook。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01c857d96fe461c91c459704f4572191f37ef016
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747349"
---
# <a name="microsoft-defender-for-office-365-security-operations-guide"></a>Microsoft Defender for Office 365安全操作指南

本文概述了在组织中成功运行Microsoft Defender for Office 365的要求和任务。 这些任务有助于确保安全运营中心 (SOC) 提供高质量、可靠的方法来保护、检测和响应与电子邮件和协作相关的安全威胁。

本指南的其余部分介绍 SecOps 人员所需的活动。 活动分为规范性每日、每周、每月和临时任务。

本指南的配套文章概述了如何在[Microsoft 365 Defender门户的“事件”页上管理来自Defender for Office 365的事件和警报](mdo-sec-ops-manage-incidents-and-alerts.md)。

[Microsoft 365 Defender安全操作指南](/microsoft-365/security/defender/integrate-microsoft-365-defender-secops)包含可用于规划和开发的其他信息。

## <a name="daily-activities"></a>每日活动

### <a name="monitor-the-microsoft-365-defender-incidents-queue"></a>监视Microsoft 365 Defender事件队列

 (的Microsoft 365 Defender门户中的<https://security.microsoft.com/incidents-queue>“**事件**”页也称为 _“事件”队列_) 允许你在Defender for Office 365中管理和监视来自以下源的事件：

- [警报](../../compliance/alert-policies.md#default-alert-policies)。
- [AIR)  (自动调查和响应 ](automated-investigation-response-office.md)。

有关事件队列的详细信息，请参阅[Microsoft 365 Defender中的优先级事件](../defender/incident-queue.md)。

用于监视事件队列的会审计划应对事件使用以下优先顺序：

1. **检测到潜在的恶意 URL 单击**。
2. **限制用户发送电子邮件**。
3. **检测到可疑的电子邮件发送模式**。
4. **用户报告为恶意软件或网络钓鱼的电子邮件**， **多个用户将电子邮件报告为恶意软件或网络钓鱼**。
5. **发送后删除了包含恶意文件的电子邮件**、 **传递后删除了包含恶意 URL 的电子邮件**，以及 **传递后从市场活动中删除的电子邮件**。
6. **由于 ETR 替代而交付的网络钓鱼**， **由于用户的“垃圾邮件”文件夹被禁用而交付了网络钓鱼**， **并且由于 IP 允许策略而交付了网络钓鱼**
7. **恶意软件未被打碎，因为 ZAP 已禁** 用， **而网络钓鱼不会因为 ZAP 被禁用而被打碎**。

下表介绍了事件队列管理和责任人角色：

|活动|Cadence|说明|Persona|
|---|---|---|---|
|事件队列 <https://security.microsoft.com/incidents-queue>中的会审事件。|每天|验证来自Defender for Office 365的所有 **中****高** 严重性事件是否经过会审。|安全运营团队|
|调查事件并采取响应操作。|每天|调查所有事件，并主动采取建议或手动响应操作。|安全运营团队|
|解决事件。|每天|如果事件已得到修正，请解决该事件。 解决该事件可解析所有链接的相关活动警报。|安全运营团队|
|对事件进行分类。|每天|将事件分类为 true 或 false。 对于真实警报，请指定威胁类型。 此分类可帮助安全团队查看威胁模式并保护组织免受威胁。|安全运营团队|

### <a name="manage-false-positive-and-false-negative-detections"></a>管理误报和误报检测

在Defender for Office 365中，你将 (标记为坏) 和假负的邮件管理误报 (错误邮件允许在以下位置) ：

- [提交门户 (管理员提交) ](admin-submission.md)。
- [租户允许/阻止列表](tenant-allow-block-list.md)
- [威胁资源管理器](threat-explorer.md)

有关详细信息，请参阅本文后面的 [“管理误报和误报检测”](#manage-false-positive-and-false-negative-detections) 部分。

下表介绍了误报和假负管理以及责任人角色：

|活动|Cadence|说明|Persona|
|---|---|---|---|
|向 Microsoft <https://security.microsoft.com/reportsubmission>提交误报和误报。|每天|通过报告错误的电子邮件、URL 和文件检测向 Microsoft 提供信号。|安全运营团队|
|分析管理员提交详细信息。|每天|了解向 Microsoft 提交的下列因素： <ul><li>是什么导致了误报的误报。</li><li>提交时Defender for Office 365配置的状态。</li><li>是否需要更改Defender for Office 365配置。</li></ul>|安全运营团队 <br/><br/> 安全管理|
|在租户允许/阻止列表 <https://security.microsoft.com/tenantAllowBlockList>中添加块条目。|每天|使用租户允许/阻止列表根据需要为假负 URL、文件或发件人检测添加块条目。|安全运营团队|
|从隔离区释放误报。|每天|在收件人确认消息被错误地隔离后，可以释放或批准用户的发布请求。 <br/><br/> 若要控制用户可以对其自己的隔离消息执行哪些操作 (包括发布或请求发布) ，请参阅 [隔离策略](quarantine-policies.md)。|安全运营团队 <br/><br/> 消息传递团队|

### <a name="review-phishing-and-malware-campaigns-that-resulted-in-delivered-mail"></a>查看导致发送邮件的网络钓鱼和恶意软件活动

|活动|Cadence|说明|Persona|
|---|---|---|---|
|查看电子邮件活动。|每天|查看针对组织<https://security.microsoft.com/campaigns>[的电子邮件活动](campaigns.md)。 重点关注导致将消息传递给收件人的市场活动。 <br/><br/> 从用户邮箱中存在的市场活动中删除邮件。 仅当活动包含尚未通过事件、 [零小时自动清除 (ZAP) ](zero-hour-auto-purge.md)或手动修正来修正的电子邮件时，才需要执行此操作。|安全运营团队|

## <a name="weekly-activities"></a>每周活动

### <a name="review-email-detection-trends-in-defender-for-office-365-reports"></a>查看Defender for Office 365报表中的电子邮件检测趋势

在Defender for Office 365中，可以使用以下报告查看组织中的电子邮件检测趋势：

- [邮件流状态报告](view-mail-flow-reports.md#mailflow-status-report)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)

|活动|Cadence|说明|Persona|
|---|---|---|---|
|在以下处查看电子邮件检测报告： <ul><li><https://security.microsoft.com/reports/TPSAggregateReportATP></li><li><https://security.microsoft.com/mailflowStatusReport?viewid=type></li></ul>|每周|查看与好电子邮件相比的恶意软件、网络钓鱼和垃圾邮件的电子邮件检测趋势。 通过一段时间内的观察，可以查看威胁模式并确定是否需要调整Defender for Office 365策略。|安全管理 <br/><br/> 安全运营团队|

### <a name="track-and-respond-to-emerging-threats-using-threat-analytics"></a>使用威胁分析跟踪和响应新出现的威胁

使用 [威胁分析](/microsoft-365/security/defender-endpoint/threat-analytics) 来查看活动的趋势威胁。

|活动|Cadence|说明|Persona|
|---|---|---|---|
|查看威胁分析 <https://security.microsoft.com/threatanalytics3>中的威胁。|每周|威胁分析提供详细分析，包括以下项： <ul><li>IOC。</li><li>搜寻有关活动威胁行动者及其活动的查询。</li><li>流行和新的攻击技术。</li><li>严重漏洞。</li><li>常见的攻击面。</li><li>普遍存在的恶意软件。</li></ul>|安全运营团队 <br/><br/> 威胁搜寻团队|

### <a name="review-top-targeted-users-for-malware-and-phishing"></a>查看目标最高的恶意软件和网络钓鱼用户

使用威胁资源管理器中的 **[“目标最强用户](threat-explorer.md#top-targeted-users)** ”选项卡来发现或确认恶意软件和网络钓鱼电子邮件的首要目标用户。

|活动|Cadence|说明|Persona|
|---|---|---|---|
|在“威胁资源管理器<https://security.microsoft.com/threatexplorer>”中查看 **“目标最高的用户**”选项卡。|每周|使用这些信息确定是否需要调整这些用户的策略或保护。 将受影响的用户添加到 [Priority 帐户](/microsoft-365/admin/setup/priority-accounts) 以获得以下优势： <ul><li>事件影响事件时的其他可见性。</li><li>为执行邮件流模式量身定制的启发式 (优先级帐户保护) 。</li><li>[优先级帐户报告的电子邮件问题](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</li></ul>|安全管理 <br/><br/> 安全运营团队|

### <a name="review-top-malware-and-phishing-campaigns-that-target-your-organization"></a>查看面向组织的顶级恶意软件和网络钓鱼活动

活动视图显示针对组织的恶意软件和网络钓鱼攻击。 有关详细信息，请参阅[Microsoft Defender for Office 365中的市场活动视图](campaigns.md)。

|活动|Cadence|说明|Persona|
|---|---|---|---|
|使用 **市场活动视图**<https://security.microsoft.com/campaigns>查看影响你的恶意软件和网络钓鱼攻击。|每周|了解攻击和技术，以及Defender for Office 365能够识别和阻止哪些内容。 <br/><br/> 使用市场活动视图中的 **下载威胁报告** 获取有关活动的详细信息。|安全运营团队|

## <a name="ad-hoc-activities"></a>临时活动

### <a name="manual-investigation-and-removal-of-email"></a>手动调查和删除电子邮件

|活动|Cadence|说明|Persona|
|---|---|---|---|
|根据用户请求调查和删除威胁资源管理器 <https://security.microsoft.com/threatexplorer> 中的不良电子邮件。|临时|使用威胁资源管理器中的 **触发器调查** 操作对过去 30 天内的任何电子邮件启动自动调查和响应 playbook。 手动触发调查可集中节省时间和精力，包括： <ul><li>根调查。</li><li>识别和关联威胁的步骤。</li><li>用于缓解这些威胁的建议操作。</li></ul> <br/> 有关详细信息，请参阅示 [例：用户报告的网络钓鱼消息启动调查 playbook](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) <br/><br/> 或者，可以使用威胁资源管理器 [手动调查](investigate-malicious-email-that-was-delivered.md) 具有强大搜索和筛选功能的电子邮件，并直接从同一位置 [执行手动响应操作](remediate-malicious-email-delivered-office-365.md) 。 可用的手动操作： <ul><li>移动到收件箱</li><li>移动到垃圾邮件</li><li>移动到已删除的项</li><li>软删除</li><li>硬删除。</li></ul>|安全运营团队|

### <a name="proactively-hunt-for-threats"></a>主动搜寻威胁

|活动|Cadence|说明|Persona|
|---|---|---|---|
|在以下情况下定期主动搜寻威胁： <ul><li><https://security.microsoft.com/threatexplorer></li><li><https://security.microsoft.com/v2/advanced-hunting></li></ul>.|临时|使用 [威胁资源管理器](threat-explorer.md) 和 [高级搜寻](../defender-endpoint/advanced-hunting-overview.md)搜索威胁。|安全运营团队 <br/><br/> 威胁搜寻团队|
|共享搜寻查询。|临时|在安全团队中积极共享常用的有用查询，以便更快地进行手动威胁搜寻和修正。 <br/><br/> 在[高级搜寻中](/microsoft-365/security/defender/advanced-hunting-shared-queries)使用[威胁跟踪器](threat-trackers.md)和共享查询。|安全运营团队 <br/><br/> 威胁搜寻团队|
|Create custom detection rules at <https://security.microsoft.com/custom_detection>.|临时|[创建自定义检测规则](../defender/advanced-hunting-overview.md#get-started-with-advanced-hunting)，根据提前搜寻中的Defender for Office 365数据主动监视事件、模式和威胁。 检测规则包含基于匹配条件生成警报的高级搜寻查询。|安全运营团队 <br/><br/> 威胁搜寻团队|

### <a name="review-defender-for-office-365-policy-configurations"></a>查看Defender for Office 365策略配置

|活动|Cadence|说明|Persona|
|---|---|---|---|
|查看Defender for Office 365策略<https://security.microsoft.com/configurationAnalyzer>的配置。|临时 <br/><br/> 每月|使用[配置分析器](configuration-analyzer-for-security-policies.md)将现有策略设置与[建议的标准或严格值](recommended-settings-for-eop-and-office365.md)Defender for Office 365进行比较。 配置分析器可识别意外或恶意更改，从而降低组织的安全状况。 <br/><br/> 或 yu 可以使用基于 PowerShell 的 [ORCA 工具](https://aka.ms/getorca)。|安全管理 <br/><br/> 消息传递团队|
|查看Defender for Office 365中的检测替代<https://security.microsoft.com/reports/TPSMessageOverrideReportATP>|临时 <br/><br/> 每月|在 **威胁防护状态报告中**，使用 [“按系统查看”数据重写\>“按原因”视图的明细](view-email-security-reports.md#view-data-by-system-override-and-chart-breakdown-by-reason)，查看检测到为网络钓鱼但因策略或用户替代设置而发送的电子邮件。 <br/><br/> 积极调查、删除或微调重写，以避免发送确定为恶意的电子邮件。|安全管理 <br/><br/> 消息传递团队|

### <a name="review-spoof-and-impersonation-detections"></a>查看欺骗和模拟检测

|活动|Cadence|说明|Persona|
|---|---|---|---|
|查看 **欺骗智能见解** 和 **模拟检测见解** <ul><li><<https://security.microsoft.com/spoofintelligence>></li><li><https://security.microsoft.com/impersonationinsight></li></ul>.|临时 <br/><br/> 每月|使用 [欺骗智能见解](learn-about-spoof-intelligence.md) 和 [模拟见解](impersonation-insight.md) 来调整欺骗和模拟检测的筛选。|安全管理 <br/><br/> 消息传递团队|

### <a name="review-priority-account-membership"></a>查看优先级帐户成员身份

|活动|Cadence|说明|Persona|
|---|---|---|---|
|查看定义为优先级帐户 <https://security.microsoft.com/securitysettings/userTags>的人员。|临时|通过组织更改使 [优先级帐户](/microsoft-365/admin/setup/priority-accounts) 的成员身份保持最新状态，以便为这些用户获得以下优势： <ul><li>在报表中提高可见性。</li><li>在事件和警报中进行筛选。</li><li>为执行邮件流模式量身定制的启发式 (优先级帐户保护) 。</li></ul> <br/> 使用自定义 [用户标记](user-tags.md) 供其他用户获取： <ul><li>在报表中提高可见性。</li><li>在事件和警报中进行筛选。</li></ul>|安全运营团队|

## <a name="appendix"></a>附录

### <a name="learn-about-microsoft-defender-for-office-365-tools-and-processes"></a>了解Microsoft Defender for Office 365工具和流程

安全操作和响应团队成员需要将Defender for Office 365工具和功能集成到现有的调查和响应流程中。 有关新工具和功能的Learning可能需要一些时间，但它是载入过程的关键部分。 SecOps 和电子邮件安全团队成员了解Defender for Office 365的最简单方法是使用作为忍者训练内容一部分的培训内容<https://aka.ms/mdoninja>。

内容针对不同知识级别进行结构化 (基础知识、中级和高级) ，每个级别包含多个模块。

Microsoft Defender for Office 365 [YouTube 频道](https://www.youtube.com/playlist?list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf)中也提供了特定任务的简短视频。

### <a name="permissions-for-defender-for-office-365-activities-and-tasks"></a>Defender for Office 365活动和任务的权限

在 Microsoft 365 Defender 门户和 PowerShell 中管理Defender for Office 365的权限基于基于角色的访问控制 (RBAC) 权限模型。 RBAC 与大多数Microsoft 365服务使用的权限模型相同。 有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

> [!NOTE]
> Privileged Identity Management (Azure AD中的 PIM) 也是向 SecOps 人员分配所需权限的一种方式。 有关详细信息，请参阅 [Privileged Identity Management (PIM) 以及为何将其用于Microsoft Defender for Office 365](use-privileged-identity-management-in-defender-for-office-365.md)。

以下权限 (角色和角色组) 在Defender for Office 365中可用，可用于向安全团队成员授予访问权限：

- **Azure AD角色**：为 _所有_ Microsoft 365服务（包括Defender for Office 365）分配权限的集中式角色。 可以在Microsoft 365 Defender门户中查看Azure AD角色和分配的用户，但不能直接在其中管理它们。 相反，你管理Azure AD角色和成员<https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/RolesAndAdministrators>。 安全团队使用的最常见角色包括：
  - **安全管理员**
  - **安全操作员**
  - **安全信息读取者**

- **电子邮件&协作角色**：授予特定于Microsoft Defender for Office 365权限的角色和角色组。 以下角色在Azure AD中不可用，但对安全团队来说可能很重要：

  - **预览** 角色：将此角色分配给需要预览或下载电子邮件作为调查活动的一部分的团队成员。 允许用户使用[电子邮件实体页](mdo-email-entity-page.md#email-preview-for-cloud-mailboxes)在云邮箱中[预览和下载](investigate-malicious-email-that-was-delivered.md#preview-role-permissions)电子邮件。

    默认情况下，此角色仅分配给以下角色组：

    - 数据调查员
    - 电子数据展示管理员

    若要将此角色分配到新的或现有的角色组，[请参阅Microsoft 365 Defender门户中的“修改电子邮件”&协作角色成员身份](permissions-microsoft-365-security-center.md#modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal)。

  - **搜索和清除** 角色：根据 AIR 建议批准删除恶意消息，或在搜寻体验（如威胁资源管理器）中对消息执行手动操作。

    默认情况下，此角色仅分配给以下角色组：

    - 数据调查员
    - 组织管理

    若要将此角色分配到新的或现有的角色组，[请参阅Microsoft 365 Defender门户中的“修改电子邮件”&协作角色成员身份](permissions-microsoft-365-security-center.md#modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal)。

  - **租户 AllowBlockList Manager**：管理 [租户允许/阻止列表中的允许和阻止](tenant-allow-block-list.md)条目。 阻止 URL、文件 (使用文件哈希) 或发件人是调查已传递的恶意电子邮件时要采取的有用响应操作。

    默认情况下，此角色仅分配给 **安全操作员** 角色组。 但是， **安全管理员** 和 **组织管理** 角色组的成员也可以管理租户允许/阻止列表中的条目。

### <a name="siemsoar-integration"></a>SIEM/SOAR 集成

Defender for Office 365通过一组编程 API 公开其大部分数据。 这些 API 可帮助你自动化工作流并充分利用Defender for Office 365功能。 数据通过[Microsoft 365 Defender API](/microsoft-365/security/defender/api-overview) 提供，可用于将Defender for Office 365集成到现有的 SIEM/SOAR 解决方案中。

- [事件 API](/microsoft-365/security/defender/api-incident)：Defender for Office 365警报和自动调查是Microsoft 365 Defender中事件的活动部分。 安全团队可以通过将整个攻击范围和所有受影响的资产分组在一起，专注于关键事项。

- [事件流式处理 API](/microsoft-365/security/defender/streaming-api)：允许将实时事件和警报传送到单个数据流中。 支持的Defender for Office 365事件类型包括：
  - [EmailEvents](/microsoft-365/security/defender/advanced-hunting-emailevents-table)
  - [EmailUrlInfo](/microsoft-365/security/defender/advanced-hunting-emailurlinfo-table)
  - [EmailAttachmentInfo](/microsoft-365/security/defender/advanced-hunting-emailattachmentinfo-table)
  - [EmailPostDeliveryEvents](/microsoft-365/security/defender/advanced-hunting-emailpostdeliveryevents-table)

  这些事件包含处理所有电子邮件 (的数据，包括过去 30 天内) 的组织内消息。

- [高级搜寻 API](/microsoft-365/security/defender/api-advanced-hunting)：允许跨产品威胁搜寻。

- [威胁评估 API](/graph/api/resources/threatassessment-api-overview)：可用于直接向 Microsoft 报告垃圾邮件、网络钓鱼 URL 或恶意软件附件。

若要将Defender for Office 365事件和原始数据连接到 Microsoft Sentinel，可以使用 [Microsoft 365 Defender (M365D) 连接器](/azure/sentinel/connect-microsoft-365-defender?tabs=MDO)

可以使用此简单的“Hello World”示例测试对 Microsoft Defender API 的 API 访问：[Microsoft 365 Defender REST API 的Hello World](/microsoft-365/security/defender/api-hello-world)。

有关 SIEM 工具集成的详细信息，请参阅[将 SIEM 工具与Microsoft 365 Defender集成](/microsoft-365/security/defender/configure-siem-defender)。

## <a name="address-false-positives-and-false-negatives-in-defender-for-office-365"></a>解决Defender for Office 365中的误报和误报

用户提交和管理员提交电子邮件是机器学习检测系统的关键正强化信号。 提交可帮助我们查看、会审、快速了解和缓解攻击。 主动报告误报和误报是一项重要活动，可在检测过程中发生错误时向Defender for Office 365提供反馈。

组织有多个用于配置用户提交的选项。 根据配置，当用户向 Microsoft 提交误报或误报时，安全团队可能会更积极地参与：

- 当 [用户报告的消息设置](user-submission.md) 配置了以下任一设置时，用户提交将发送到 Microsoft 进行分析：
  - 将报告的消息发送到：Microsoft。
  - 将报告的消息发送到：Microsoft 和我组织的邮箱。

  当操作团队发现用户未报告的误报或误报时，安全团队成员应执行加载临时 [管理员提交](admin-submission.md) 。

- 当用户报告的消息配置为仅将邮件发送到组织的邮箱时，安全团队应主动通过管理员提交向 Microsoft 发送用户报告的误报和误报。

每当用户将消息报告为网络钓鱼时，Defender for Office 365就会生成警报，并且警报将触发 AIR playbook。 事件逻辑会尽可能将此信息关联到其他警报和事件。 这种信息整合有助于安全团队会审、调查和响应用户报告的电子邮件。

用户提交和管理员提交由 Microsoft 的提交管道处理，该管道遵循紧密集成的过程。 此过程包括：

- 噪。
- 自动会审。
- 由安全分析师和基于人工协作的基于机器学习的解决方案进行分级。

有关详细信息，请参阅[Defender for Office 365中的报告电子邮件 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/reporting-an-email-in-microsoft-defender-for-office-365/ba-p/2870231)。

安全团队成员可以在以下位置从Microsoft 365 Defender门户<https://security.microsoft.com>中的多个位置进行提交：

- [管理员提交](admin-submission.md)：使用提交门户向 Microsoft 提交可疑垃圾邮件、网络钓鱼、URL 和文件。
- 使用以下消息操作之一直接从威胁资源管理器：
  - 报表干净
  - 报表网络钓鱼
  - 报告恶意软件
  - 报告垃圾邮件

  最多可以选择 10 条消息来执行批量提交。 以这种方式创建的管理员提交在提交门户中也可见。

为了短期缓解误报，安全团队可以直接管理[租户允许/阻止列表](tenant-allow-block-list.md)中文件、URL 和发件人的[阻止条目](manage-tenant-blocks.md)。

为了短期缓解误报，安全团队无法直接管理租户允许/阻止列表中的 [允许条目](manage-tenant-allows.md) 。 相反，他们需要使用 [管理员提交](admin-submission.md) 和 **允许消息，如此** 选项。

在[Defender for Office 365隔离保存](manage-quarantined-messages-and-files.md)潜在的危险或不需要的消息和文件。 安全团队可以查看、发布和删除所有用户的所有类型的隔离消息。 此功能使安全团队能够在隔离误报消息或文件时有效响应。

## <a name="integrate-third-party-reporting-tools-with-defender-for-office-365-user-submission"></a>将第三方报告工具与Defender for Office 365用户提交集成

如果你的组织使用允许用户在内部报告可疑电子邮件的第三方报告工具，则可以将该工具与Defender for Office 365的用户提交功能集成。 此集成为安全团队提供以下优势：

- 与 Defender for Office 365 的 AIR 功能集成。
- 简化会审。
- 减少调查和响应时间。

指定在Microsoft 365 Defender门户<https://security.microsoft.com/userSubmissionsReportMessage>的 **“用户提交**”页上发送用户报告邮件的自定义邮箱。 有关详细信息，请参阅 [用户报告的消息设置](user-submission.md)。

> [!NOTE]
>
> - 自定义邮箱是一个Exchange Online邮箱。
> - 第三方报告工具必须包含原始报告消息作为未压缩的消息。EML 或 .发送到自定义邮箱的邮件中的 MSG 附件 (不只是将原始邮件转发到自定义邮箱) 。
> - 自定义邮箱需要特定的先决条件才能发送潜在的错误邮件。 有关详细信息，请参阅 [自定义邮箱先决条件](user-submission.md#custom-mailbox-prerequisites)。

当用户报告的电子邮件到达自定义邮箱时，Defender for Office 365会自动生成 **用户报告为恶意软件或网络钓鱼的名为“电子邮件**”的警报。 此警报将启动 [AIR playbook](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)。 playbook 执行一系列自动调查步骤：

- 收集有关指定电子邮件的数据。
- 收集有关与该电子邮件相关的威胁和实体的数据。 实体可以包括文件、URL 和收件人。
- 根据调查结果为 SecOps 团队提供建议的操作。

**用户报告为恶意软件或网络钓鱼** 警报、自动调查及其建议操作的电子邮件会自动与Microsoft 365 Defender中的事件相关联。 这种关联进一步简化了安全团队的会审和响应过程。 如果多个用户报告相同或类似的消息，则所有用户和消息都与同一事件相关联。

与其他Microsoft 365 Defender产品中的警报和调查相比，Defender for Office 365中的警报和调查数据会自动进行比较：

- Microsoft Defender for Endpoint
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

如果发现关系，系统会创建一个事件，以使整个攻击可见。
