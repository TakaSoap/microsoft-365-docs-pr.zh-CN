---
title: 了解内部风险管理
description: 了解如何通过组织中内部风险管理帮助最大程度地减少Microsoft 365。
keywords: Microsoft 365， 内部风险， 风险管理， 合规性
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 30f73f99b60092c854ae7d1ccc2d8eac1e7a49b7
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335838"
---
# <a name="learn-about-insider-risk-management-in-microsoft-365"></a>了解企业内部风险管理Microsoft 365

内部风险管理是 Microsoft 365中的合规性解决方案，通过让你能够检测、调查和处理组织中恶意和无意的活动，帮助最大程度地降低内部风险。 通过内部风险策略，你可以定义在组织中识别和检测的风险类型，包括处理案例以及根据需要将Advanced eDiscovery上报给 Microsoft。 您组织的风险分析师可以快速采取适当的措施，以确保用户符合组织的合规性标准。

观看下面的视频，了解内部风险管理如何有助于组织在确定组织价值、文化及用户体验优先级时预防、检测和包含风险：
<br>
<br>

**内部风险管理解决方案&开发**：
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]
<br>

**内部风险管理工作流**：
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

## <a name="modern-risk-pain-points"></a>新式风险难处

要管理并最大限度地降低组织中的风险，首先要了解现代工作场所中的风险类型。 某些风险由外部事件和无法控制的因素所驱动。 其他风险由可最小化和避免的内部事件和用户活动驱动。 一些示例是组织中用户非法、不当、未经授权或不良行为和操作带来的风险。 这些行为包括来自用户的广泛内部风险：

- 敏感数据的泄露和数据泄漏
- 违反保密规定
- 窃取知识产权 (IP)
- 欺诈
- 内幕交易
- 违反法规遵从性

现代工作场所中的用户可以跨各种平台和服务创建、管理和共享数据。 在大多数情况下，组织具有有限的资源和工具来识别和缓解组织范围内的风险，同时还符合用户隐私标准。

内部风险管理使用全面的服务和第三方指标来帮助你快速识别、会审和操作风险活动。 通过使用 microsoft Microsoft 365 和 Microsoft Graph中的日志，内部风险管理允许你定义特定策略以确定风险指标。 这些策略允许你识别有风险的活动并采取措施缓解这些风险。

内部风险管理以以下原则为中心：

- **透明度：** 通过按设计的隐私体系结构平衡用户隐私与组织风险。
- **可配置**：基于行业、地理和业务组的可配置策略。
- **集成**：跨合规性解决方案Microsoft 365工作流。
- **可操作**：提供见解以启用审阅者通知、数据调查和用户调查。

## <a name="identifying-potential-risks-with-analytics-preview"></a>通过分析功能识别潜在风险 (预览) 

通过预览体验计划风险分析，无需配置任何预览体验计划风险策略，即可对组织中潜在的预览体验成员风险进行评估。 此评估可以帮助组织确定用户风险更高的潜在领域，并可帮助确定可能考虑配置的预览体验计划风险管理策略的类型和范围。 此评估还可以帮助您确定对现有内部风险策略进行其他许可或未来优化的需求。

若要了解有关内部风险分析的信息，请参阅预览体验 [成员风险管理设置：分析](insider-risk-management-settings.md#analytics-preview)。

## <a name="get-started-with-recommended-actions-preview"></a>预览版中推荐 (入门) 

无论是首次设置内部风险管理还是开始创建新策略，新的建议操作体验都可以帮助您最了解内部风险管理功能。 [](insider-risk-management-configure.md#recommended-actions-preview) 建议的操作包括设置权限、选择策略指示器、创建策略等。

## <a name="workflow"></a>工作流

内部风险管理工作流可帮助你识别、调查和采取措施来解决组织内部风险。 借助集中的策略模板、Microsoft 365 服务的全面活动信号以及警报和案例管理工具，您可以使用可操作见解快速识别和处理风险行为。

通过 Microsoft 365 中的内部风险管理，按照以下工作流程识别和解决内部风险活动和合规性问题：

![内部风险管理工作流。](../media/insider-risk-workflow.png)

### <a name="policies"></a>策略

[内部风险管理策略](insider-risk-management-policies.md) 是使用预定义模板和策略条件创建的，这些模板和策略条件定义了在组织中检查哪些触发事件和风险指标。 这些条件包括如何对警报使用风险指标、策略中包括哪些用户、优先处理哪些服务以及监视时间段。

可以从以下策略模板中选择以快速开始使用内部风险管理：

- [离职用户窃取数据](insider-risk-management-policies.md#data-theft-by-departing-users)
- [常规数据泄露](insider-risk-management-policies.md#general-data-leaks)
- [优先用户的数据泄露活动(预览)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [心怀不满用户的数据泄露活动(预览)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [安全策略常规违规活动(预览)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [离职用户的安全策略违规活动(预览)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [优先用户的安全策略违规活动(预览)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [心怀不满员工的安全策略违规活动(预览)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

![内部风险管理策略仪表板。](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>警报

警报由与策略条件匹配的风险指示器自动生成，并显示在 [警报仪表板中](insider-risk-management-activities.md#alert-dashboard)。 此仪表盘可以快速预览需要审查的全部警报、随时间变化的开放警报以及组织的警报统计。 将显示所有策略警报，并显示以下信息，以帮助你快速识别需要操作的现有警报和新警报的状态：

- 状态
- Severity
- 检测到的时间
- 情况
- 案例状态

![内部风险管理警报仪表板。](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>会审

需要调查的新用户活动会自动生成分配有需求审阅 *状态的警报。* 审阅者可以快速识别并审阅、评估和分类这些警报。

可以通过打开一个新的案例、将警报分配到一个现有案例，或关闭警报来解决警报。 使用警报筛选器，可以轻松按状态、严重性或检测到的时间快速识别警报。 作为会审过程的一部分，审阅者可以查看策略标识的活动的警报详细信息、查看与策略匹配关联的用户活动、查看警报的严重性以及查看用户配置文件信息。

![内部风险管理会审。](../media/insider-risk-triage.png)

### <a name="investigate"></a>调查

使用用户活动报告快速调查所选用户的所有活动[ (预览) 。 ](insider-risk-management-activities.md#user-activity-reports-preview) 这些报告允许贵组织的研究人员在定义的时段内检查特定用户的活动，而无需将其临时或显式分配给内部风险管理策略。 在检查用户的活动后，调查人员可以以恶意方式消除个别活动，与其他调查人员共享或通过电子邮件发送指向报告的链接，或者选择将用户临时或显式分配给内部风险管理策略。

[为](insider-risk-management-cases.md) 需要更深入地查看和调查活动详细信息以及策略匹配情况的情况的警报创建案例。 **案件仪表盘** 提供了所有活动案件、随时间变化的未结案件以及组织的案件统计的全面视图。 审阅者可以按状态、打开事例的日期和上次更新事例的日期快速筛选事例。

在案件仪表盘选中案件即可打开该案件以进行调查和审查。 此步骤是内部风险管理工作流的核心。 此区域将风险活动、策略条件、警报详细信息和用户详细信息合成为审阅者的集成视图。 此领域的主要调查工具包括：

- **用户活动**：用户活动自动显示在交互式图表中，该图表按时间以及当前或过去的风险活动的风险级别绘制活动。 审阅者可以快速筛选和查看用户的全部风险历史记录，并深入了解特定活动了解更多详细信息。
- **内容资源管理器**：与通知活动关联的所有数据文件和电子邮件都会自动捕获并显示在内容资源管理器中。 审阅者可以按数据源、文件类型、标签、对话以及更多属性筛选和查看文件和消息。
- **案例备注**：审阅者可以在"案例备注"部分提供案例备注。 此列表将所有备注合并到一个中央视图中，并包括审阅者和提交日期的信息。

![内部风险管理调查。](../media/insider-risk-investigate.png)

此外，新的审核 [ (预览 ](insider-risk-management-audit-log.md) 版) 使你可以随时了解对内部风险管理功能采取的操作。 此资源允许独立审阅分配给一个或多个内部风险管理角色组的用户所采取的操作。

### <a name="action"></a>Action

调查案例后，审阅者可以快速采取行动来解决该案例，或与组织的其他风险利益干系人协作。 如果用户意外或无意违反策略条件，可以从您可以为组织自定义的通知模板向用户发送简单的提醒通知。 这些通知可以充当简单的提醒，也可以指示用户刷新培训或指南以帮助防止将来存在风险的行为。 有关详细信息，请参阅 [内部风险管理通知模版](insider-risk-management-notices.md)。

在更严重的情况下，可能需要与组织的其他审阅者或服务共享内部风险管理案例信息。 内部风险管理与其他合规性解决方案Microsoft 365紧密集成，以帮助你解决端到端风险。

- **Advanced eDiscovery：** 通过上报案件进行调查，你可以将案件的数据和管理转移到Advanced eDiscovery Microsoft 365。 高级电子数据展示提供了端到端的工作流程，可用于保存、收集、审查、分析和导出响应组织的内部和外部调查的内容。 它帮助法律团队管理整个法定保留通知工作流。 若要了解有关高级电子数据展示案例的详细信息，请参阅 [Microsoft 365 中的高级电子数据展示概述](overview-ediscovery-20.md)。
- Office 365 管理 API 集成 **(预览版) ：** 内部风险管理支持通过 Office 365 管理 API 将警报信息导出到安全信息和事件管理 (SIEM) 服务。 通过访问平台中最适合组织风险流程的警报信息，可以更灵活地操作风险活动。 若要了解有关使用管理 API 导出Office 365信息的信息，请参阅[导出警报](insider-risk-management-settings.md#export-alerts-preview)。

> [!NOTE]
> 感谢你在预览 ServiceNow 连接器期间提供的反馈和支持。 我们决定在 2020 年 11 月 30 日停止预览 ServiceNow 连接器并停止支持内部风险管理。 我们正在积极评估替代方法，以为客户提供内部风险管理中的 ServiceNow 集成。

## <a name="scenarios"></a>应用场景

内部风险管理可以帮助您在多种常见方案中检测、调查和采取措施来缓解组织内部风险：

### <a name="data-theft-by-departing-users"></a>离职用户窃取数据

当用户离开组织时（无论是由于任一目的还是由于终止而离开组织）时，通常存在公司、客户和用户数据面临风险的合法问题。 用户可能会以为项目数据并非专有数据，或者可能会试图获取公司数据来获取个人利益，并违反公司策略和法律标准。 通过离开用户策略模板使用数据[](insider-risk-management-policies.md#policy-templates)盗窃的内部风险管理策略会自动检测通常与此类盗窃相关的活动。 通过此策略，你将通过离开用户来自动收到与数据盗窃相关的可疑活动的警报，以便你可以采取适当的调查操作。 此策略[Microsoft 365](import-hr-data.md)需要为组织配置 HR 连接器。

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>有意或无意泄露敏感或机密信息

在大多数情况下，用户会尽量正确处理敏感或机密信息。 但有时，用户可能会出错，并且信息会意外共享在组织外部或违反信息保护策略。 In other circumstances， users may intently leak or share sensitive and confidential information with malicious intent and for potential personal gain. 使用下列数据泄露策略模板创建的内部风险管理策略会自动检测通常与共享敏感或机密信息相关的活动：

- [常规数据泄露](insider-risk-management-policies.md#general-data-leaks)
- [优先用户的数据泄露活动(预览)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [心怀不满用户的数据泄露活动(预览)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>预览版中有意或无意 (违反) 

在新式工作场所中管理其设备时，用户通常具有很大程度的控制。 此控件可能包括安装或卸载应用程序的权限，这些应用程序是执行其职责所需的权限，还是临时禁用设备安全功能的功能。 无论此活动是无意的、意外的还是恶意的，此行为都可能会给组织带来风险，并且对于识别和采取行动以最大限度地减少风险非常重要。 为了帮助标识这些有风险的安全活动，以下内部风险管理安全策略违反模板对安全风险指示器进行评分，并使用 Microsoft Defender for Endpoint 警报提供与安全相关的活动的见解：

- [安全策略常规违规活动(预览)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [离职用户的安全策略违规活动(预览)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [优先用户的安全策略违规活动(预览)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [心怀不满员工的安全策略违规活动(预览)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>基于位置、访问级别或风险历史记录的用户策略 (预览) 

您组织的用户可能具有不同的风险级别，具体取决于他们的位置、对敏感信息的访问级别或风险历史记录。 此结构可能包括您组织的管理层领导团队的成员、具有大量数据和网络访问权限的 IT 管理员，或者过去具有风险活动历史记录的用户。 在这些情况下，更仔细的检查和更积极的风险评分对于帮助显示警报以便进行调查和快速操作非常重要。 若要帮助识别这些类型的用户存在风险的活动，可以创建优先级用户组，并基于以下策略模板创建策略：

- [优先用户的安全策略违规活动(预览)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [优先用户的数据泄露活动(预览)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>解除注册的用户对预览 (的行为) 

雇佣者事件可能会以多种与内部风险相关的方式影响用户行为。 这些压力因素可能是性能考核不佳、职位降级或被放在绩效考核计划中的用户。 虽然大多数用户不会恶意响应这些事件，但是这些操作的压力可能会导致某些用户采取在正常情况下通常不会考虑的操作。 为了帮助标识这些类型的有风险的活动，以下内部风险管理策略模板使用 Microsoft 365 HR 连接器，并开始记分风险指示器，这些风险指标与可能在接近雇佣压力事件时发生的行为相关：

- [心怀不满用户的数据泄露活动(预览)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [心怀不满员工的安全策略违规活动(预览)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>准备好开始了吗？

- 请参阅 [规划内部风险管理，](insider-risk-management-plan.md) 了解如何准备在组织中启用内部风险管理策略。
- 请参阅 [内部风险管理设置入门，](insider-risk-management-settings.md) 为内部风险策略配置全局设置。
- 请参阅 [内部风险管理入门，](insider-risk-management-configure.md) 以配置先决条件、创建策略并开始接收警报。
