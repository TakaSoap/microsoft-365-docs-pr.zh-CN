---
title: 监视个人数据泄露
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.localizationpriority: high
search.appverid:
- MET150
description: 了解可用于监视个人数据泄露的三种工具。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba164fde38be1e8eed53b71ab568124140deaac5
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682694"
---
# <a name="monitor-for-leaks-of-personal-data"></a>监视个人数据泄露

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


有许多工具可用于监视个人数据的使用和传输。本主题介绍了三种十分有用的工具。

![用于监视个人数据的使用和传输的工具。](../../media/Monitor-for-leaks-of-personal-data-image1.png)

在此图中：

- 从 Microsoft 365 数据丢失防护报告入手，它们用于监视 SharePoint Online、OneDrive for Business 和传输中的电子邮件内的个人数据。这些报告为监控个人数据提供了最详细的信息。然而，这些报告并未囊括 Office 365 中的所有服务。

- 接下来，使用警报策略和审核日志监视服务中的活动。设置持续监视或搜索审核日志以调查事件。审核日志适用于以下服务：Sway、Power BI、电子数据展示、Dynamics 365、Power Automate、Microsoft Teams、管理员活动、OneDrive for Business、SharePoint Online、传输中的邮件和静态邮箱。Skype 对话属于静态邮箱服务。

- 最后，使用 Microsoft Defender for Cloud Apps 监视其他 SaaS 提供程序中包含敏感数据的文件。即将推出的功能为，通过 Defender for Cloud Apps 跨 Azure 信息保护和 Office 使用敏感信息类型和统一标签。可以设置适用于所有 SaaS 应用或特定应用（如 Box）的策略。Defender for Cloud Apps 不会发现 Exchange Online 中的文件（包括附加到电子邮件的文件）。

## <a name="data-loss-prevention-reports"></a>数据丢失防护报告

创建数据丢失防护 (DLP) 策略后，你需要验证这些策略是否按预期运行，以及是否有助于你保持合规性。借助 Office 365 中的 DLP 报告，可以快速查看 DLP 策略匹配数、替代数或误报数；观察它们随时间推移是呈上升趋势还是下降趋势；以不同的方式筛选报告；以及通过选择图中直线上的点来查看更多详细信息。

可以使用 DLP 报告实现以下目的：

- 重点关注特定的时间段，并了解峰值和发展趋势的原因。
- 发现违反组织的 DLP 策略的业务流程。
- 了解 DLP 策略的任何业务影响。
- 查看用户在通过重写策略或报告误报解析策略提示时提交的理由。
- 通过显示该策略的匹配结果，验证该策略是否遵守特定 DLP 策略。
- 在详细信息窗格中查看与您的 DLP 策略相匹配的含敏感数据的文件列表。

此外，当你在测试模式下运行 DLP 策略时，可以使用 DLP 报告对其进行微调。

DLP 报表位于Microsoft 365 合规中心中。转到 **报表**\>**组织数据** 部分，查找 **DLP 策略匹配**、**DLP 事件**，以及 **DLP 误报和替代** 报告。

有关详细信息，请参阅[查看数据丢失防护报告](../../compliance/view-the-dlp-reports.md)。

![显示 DLP 策略匹配项的报告。](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="audit-log-and-alert-policies"></a>审核日志和警报策略

审核日志包含来自 Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory、Microsoft Teams、Power BI、Sway 和其他服务的事件。

Microsoft 365 Defender 门户和 Microsoft 365 合规中心提供两种对审核日志的监视和报告:

- 设置警报策略、查看警报和监视趋势 — 使用 Microsoft 365 Defender 门户和 Microsoft 365 合规中心中的警报策略和警报仪表板工具。
- 直接搜索审核日志：搜索指定日期范围内的所有事件。也可以根据特定条件（如执行操作的用户、操作或目标对象）筛选结果。

信息安全和合规性团队可以使用这些工具主动审核由最终用户和管理员在服务中执行的活动。可以配置自动警报，以在特定网站集上发生某些活动时（例如从已知包含 GDPR 相关信息的网站共享内容时）发送电子邮件通知。通过此操作，这些团队可以跟进用户，以确保遵守企业安全策略或提供其他培训。

信息安全团队还可以搜索审核日志来调查可疑的数据泄露并确定泄露的根本原因和程度。此内置功能有助于遵守 GDPR 条款 33 和 34 的规定，其中要求在特定时间段内向 GDPR 监管机构和数据泄露的数据主体自身提供通知。通常的建议是，仅将审核日志条目在服务内保留 90 天，但许多组织都要求将这些日志保留更长的时间。

有些解决方案可以通过 Microsoft 管理活动 API 来订阅统一审核日志，而且可以按需存储日志条目并提供高级仪表板和警报。例如：[Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365)。

有关警报策略和搜索审核日志的更多信息：

- [Microsoft 365 中的警报策略](../../compliance/alert-policies.md)
- [在 Office 365 中搜索用户和管理员活动的审核日志](../../compliance/search-the-audit-log-in-security-and-compliance.md)（介绍）
- [启用或禁用审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)
- [搜索审核日志](../../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (cmdlet)
- [审核日志中的详细属性](../../compliance/detailed-properties-in-the-office-365-audit-log.md)

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps 可帮助你跨网络发现使用中的其他 SaaS 应用、发送到这些应用以及从这些应用发送的敏感数据。

Microsoft Defender for Cloud Apps 是一项可为云应用提供深层可见性、精细控制和增强型威胁防护的综合服务。可以在你的网络（从所有设备）中识别出超过 15,000 个云应用程序，并提供风险评分以及持续的风险评估和分析。无需代理：从你的防火墙和代理收集信息，从而为你提供有关云使用情况和影子 IT 的完整可见性和上下文。

为了更好地了解云环境，Defender for Cloud Apps 调查功能可让你深入了解批准的应用和托管的应用的所有活动、文件和帐户。你可以获得文件级别的详细信息，并发现数据在云应用中的传输位置。

例如，下图说明了有助于符合 GDPR 的两个 Defender for Cloud Apps 策略。

![示例 Microsoft Defender for Cloud Apps 策略。](../../media/Monitor-for-leaks-of-personal-data-image3.png)

如果选择的文件包含预定义的 PII 属性或自定义表达式，并且从选择的 SaaS 应用组织外部共享，那么第一个策略发出警报。

第二个策略会阻止将文件下载到任何非托管设备。选择要查找的文件内的属性以及需要对其应用策略的 SaaS 应用。

Defender for Cloud Apps 即将推出以下属性类型：

- 敏感信息类型
- Microsoft 365 和 Azure 信息保护中的统一标签

### <a name="defender-for-cloud-apps-dashboard"></a>Defender for Cloud Apps 仪表板

如果尚未开始使用 Defender for Cloud Apps，请首先启动它。如果要访问 Defender for Cloud Apps，请转到：<https://portal.cloudappsecurity.com>。

> [!NOTE]
> 开始使用 Defender for Cloud Apps 时或在分配标签前，请务必启用“自动扫描文件中是否有 Azure 信息保护分类标签”（位于“常规”设置中）。设置后，Defender for Cloud Apps 在对现有文件进行修改前将不会再次扫描现有文件。

![显示有关警报信息的仪表板。](../../media/Monitor-for-leaks-of-personal-data-image4.png)

详细信息：

- [部署 Microsoft Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security)
- [有关 Microsoft Defender for Cloud Apps 的详细信息](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [使用 Microsoft Defender for Cloud Apps 代理阻止下载敏感信息](/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a>用于检测个人数据共享的示例文件和活动策略

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a>检测包含 PII 的文件共享 — 信用卡卡号

从批准的云应用共享包含信用卡卡号的文件时发出警报。

|控件|设置|
|---|---|
|策略类型|文件策略|
|策略模板|无模板|
|策略严重性|高|
|类别|DLP|
|筛选设置|访问级别 = 公共 (Internet)，公共，外部 <p> 应用 = \<select apps\>（如果想要将监视限制为特定 SaaS 应用，请使用此设置）|
|应用对象|所有文件、所有的所有者|
|内容检查|包括匹配当前表达式的文件：所有国家/地区：法国：信用卡卡号 <p> 无需相关上下文：未选中（此设置将匹配关键字和正则表达式） <p> 包括具有至少 1 个匹配项的文件 <p> 取消屏蔽冲突的最后 4 个字符：已选中|
|警报|为每个匹配文件创建警报：已选中 <p> 每日警报限制：1000 <p> 选择一个警报作为电子邮件：已选中 <p> 收件人：infosec@contoso.com|
|治理|Microsoft OneDrive for Business <p> 设为专用：选中“删除外部用户” <p> 所有其他设置：未选中 <p> Microsoft SharePoint Online <p> 设为专用：选中“删除外部用户” <p> 所有其他设置：未选中|

类似策略：

- 检测包含 PII 的文件共享 — 电子邮件地址
- 检测包含 PII 的文件共享 — 护照编号

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a>检测 Box 或 OneDrive for Business 中的客户或 HR 数据

当标记为“客户数据”或“HR 数据”的文件上传至 OneDrive for Business 或 Box 时发出警报。

注意：

- Box 监视要求使用 API 连接器 SDK 配置连接器。
- 此策略需要当前为个人预览版的功能。

|控件|设置|
|---|---|
|策略类型|活动策略|
|策略模板|无模板|
|策略严重性|高|
|类别|共享控制|
|作用对象|单个活动|
|筛选设置|活动类型 = 上传文件 <p> 应用 = Microsoft OneDrive for Business 和 Box <p> 分类标签（目前为个人预览版）：Azure 信息保护 = 客户数据、人力资源—薪资数据、人力资源—员工数据|
|警报|创建警报：已选中 <p> 每日警报限制：1000 <p> 选择一个警报作为电子邮件：已选中 <p> 收件人：infosec@contoso.com|
|治理|所有应用 <p> 隔离用户：选中 <p> 所有其他设置：未选中 <p> Office 365 <p> 隔离用户：选中 <p> 所有其他设置：未选中|

类似策略：

- 检测大量下载客户数据或 HR 数据的情况 — 如果检测到单个用户在较短的一段时间内下载了大量包含客户数据或 HR 数据的文件，则发出警报。
- 检测共享客户和 HR 数据的情况 — 共享包含客户或 HR 数据的文件时发出警报。
