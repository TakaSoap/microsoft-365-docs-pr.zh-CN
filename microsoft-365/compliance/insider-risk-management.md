---
title: 了解内部风险管理
description: 了解如何在 Microsoft 365 中通过内部风险管理帮助最大程度地降低组织风险。
keywords: Microsoft 365， 内部风险， 风险管理， 合规性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: ceb35fa9e89a5393500cecb82e52f44852e47b6f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094663"
---
# <a name="learn-about-insider-risk-management-in-microsoft-365"></a>了解 Microsoft 365 中的内部风险管理

内部风险管理是 Microsoft 365 中的合规性解决方案，通过让你能够检测、调查和处理组织中恶意和无意的活动，帮助将内部风险降至最低。 内部风险策略允许你定义在组织中识别和检测的风险类型，包括根据需要对事例采取行动，以及将事例上报给 Microsoft 高级电子数据展示。 您组织的风险分析员可以快速采取适当的措施，以确保用户符合组织的合规性标准。

观看下面的视频，了解内部风险管理如何在确定组织价值、文化及用户体验优先级时帮助组织预防、检测和包含风险：
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>新式风险要点

在组织中管理和最小化风险从了解现代工作场所中发现的风险类型开始。 某些风险由外部事件和无法控制的因素所驱动。 其他风险由可最小化和避免的内部事件和用户活动驱动。 一些示例是组织中用户非法、不当、未经授权或不当行为和操作带来的风险。 这些行为包括来自用户的广泛内部风险：

- 敏感数据泄露和数据泄漏
- 保密性冲突
- 知识产权 (IP) 盗窃
- 欺诈
- 内部交易
- 违反法规

新式工作场所中的用户可以跨各种平台和服务创建、管理和共享数据。 在大多数情况下，组织具有有限的资源和工具来识别和缓解组织范围内的风险，同时还符合用户隐私标准。

内部风险管理使用全面的服务和第三方指标，帮助你快速识别、分类和操作风险活动。 通过使用 Microsoft 365 和 Microsoft Graph 中的日志，内部风险管理允许你定义特定策略以标识风险指标。 通过这些策略，您可以识别有风险的活动并采取措施来缓解这些风险。

内部风险管理以以下原则为中心：

- **透明度：** 平衡用户隐私与组织风险与按设计的隐私体系结构。
- **可配置**：基于行业、地理和业务组的可配置策略。
- **集成**：跨 Microsoft 365 合规性解决方案的集成工作流。
- **可操作**：提供见解以启用用户通知、数据调查和用户调查。

## <a name="workflow"></a>工作流

内部风险管理工作流可帮助您识别、调查和采取措施来解决组织内部风险。 借助重点策略模板、Microsoft 365 服务的全面活动信号以及警报和案例管理工具，您可以使用可操作见解快速识别和处理有风险的行为。

在 Microsoft 365 中识别和解决内部风险活动和内部风险管理的合规性问题使用以下工作流：

![内部风险管理工作流](../media/insider-risk-workflow.png)

### <a name="policies"></a>策略

[内部风险管理策略是](insider-risk-management-policies.md) 使用预定义模板和策略条件创建的，这些模板和策略条件定义了在组织中检查哪些触发事件和风险指标。 这些条件包括如何对警报使用风险指标、策略中包括哪些用户、确定服务优先级以及监视时间段。

可以从以下[策略模板]中选择以快速开始使用内部风险管理：

- [离开用户的数据盗窃](insider-risk-management-policies.md#data-theft-by-departing-users)
- [常规数据泄露](insider-risk-management-policies.md#general-data-leaks)
- [按优先级用户的数据泄露 (预览) ](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [在预览版中，由 (用户泄露) ](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [预览版中的 (违反) ](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [离开用户以使用预览版 (违反) ](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [预览版中优先级用户违反 (违反) ](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [取消注册的用户在预览版中违反 (违反) ](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

![内部风险管理策略仪表板](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>警报

警报由符合策略条件的风险指示器自动生成，并显示在 [警报仪表板中](insider-risk-management-alerts.md)。 此仪表板可快速查看需要审阅的所有警报、打开一段时间的警报以及组织的警报统计信息。 将显示所有策略警报以及以下信息，以帮助你快速识别现有警报和需要操作的新警报的状态：

- 状态
- Severity
- 检测到的时间
- 情况
- 案例状态

![内部风险管理警报仪表板](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>会审

需要调查的新用户活动会自动生成分配有 *需求审阅状态的* 警报。 审阅者可以快速识别和审阅、评估和分类这些警报。

通过打开新案例、将警报分配给现有案例或消除警报来解决警报。 使用警报筛选器，可以轻松按状态、严重性或检测到的时间快速识别警报。 作为会审过程的一部分，审阅者可以查看策略所标识的活动的警报详细信息、查看与策略匹配关联的用户活动、查看警报的严重性以及查看用户配置文件信息。

![内部风险管理会审](../media/insider-risk-triage.png)

### <a name="investigate"></a>调查

[为](insider-risk-management-cases.md) 警报创建案例，这些警报需要更深入地查看和调查活动详细信息以及策略匹配的情况。 案例 **仪表板** 提供组织的所有活动案例、一段时间的打开案例和事例统计信息的全视图。 审阅者可以按状态、案例的打开日期和上次更新事例的日期快速筛选事例。

在案例仪表板上选择案例将打开该案例进行调查和审阅。 此步骤是内部风险管理工作流的核心。 在此区域中，风险活动、策略条件、警报详细信息和用户详细信息将合成为审阅者的集成视图。 此区域中的主要调查工具包括：

- **用户活动**：用户活动自动显示在交互式图表中，该图表按时间以及当前或过去的风险活动的风险级别绘制活动。 审阅者可以快速筛选和查看用户的全部风险历史记录，并深入了解特定活动，了解更多详细信息。
- **内容资源管理器**：与警报活动关联的所有数据文件和电子邮件都会自动捕获并显示在内容资源管理器中。 审阅者可以按数据源、文件类型、标记、对话等属性筛选和查看文件和消息。
- **案例备注**：审阅者可以在"案例注释"部分提供案例备注。 此列表将所有备注合并在一个中央视图中，并包括审阅者和提交日期的信息。

![内部风险管理调查](../media/insider-risk-investigate.png)

### <a name="action"></a>操作

调查案例后，审阅者可以快速解决问题或与组织的其他风险利益干系人协作。 如果用户意外或无意违反策略条件，可以从您可以为组织自定义的通知模板向用户发送简单的提醒通知。 这些通知可以充当简单的提醒，也可以指示用户刷新培训或指导，以帮助防止未来存在风险的行为。 有关详细信息，请参阅 [内部风险管理通知模板](insider-risk-management-notices.md)。

在更严重的情况下，您可能需要与组织的其他审阅者或服务共享内部风险管理案例信息。 内部风险管理与其他 Microsoft 365 合规性解决方案紧密集成，可帮助你解决端到端风险。

- **高级电子数据展示**：升级案例进行调查后，你可以将案例的数据和管理转移到 Microsoft 365 中的高级电子数据展示。 高级电子数据展示提供了端到端工作流，用于保留、收集、审阅、分析和导出对组织内部和外部调查做出响应的内容。 它允许法律团队管理整个法定保留通知工作流。 若要详细了解高级电子数据展示事例，请参阅 Microsoft [365](overview-ediscovery-20.md)中的高级电子数据展示概述。
- **ServiceNow (预览**) ：ServiceNow 是一个受欢迎的云计算平台，可帮助组织管理用于企业运营的数字工作流。 内部风险管理支持与 ServiceNow 服务共享案例警报，并允许您创建与单个内部风险案例相关的事件和更改请求。 若要了解有关与 ServiceNow 共享警报信息的信息，请参阅["与 ServiceNow 共享案例"。](insider-risk-management-cases.md#share-the-case)
- **Office 365** 管理 API 集成 (预览版) ：内部风险管理支持通过 Office 365 管理 API 将警报信息导出到安全信息和事件管理 (SIEM) 服务。 通过访问平台中最适合组织风险流程的警报信息，可以更灵活地操作风险活动。 若要了解有关使用 Office 365 管理 API 导出警报信息的信息，请参阅"[导出警报"。](insider-risk-management-settings.md#export-alerts-preview)

>[!NOTE]
>感谢你在 ServiceNow 连接器预览期间提供的反馈和支持。 我们决定在 2020 年 11 月 30 日终止 ServiceNow 连接器的预览版并停止对内部风险管理的支持。 我们正在积极评估替代方法，以为客户提供内部风险管理中的 ServiceNow 集成。

## <a name="scenarios"></a>应用场景

在几种常见方案中，内部风险管理可以帮助您检测、调查和采取措施来缓解组织内部风险：

### <a name="data-theft-by-departing-users"></a>离开用户的数据盗窃

当用户主动离开组织或因终止而离开组织时，通常存在公司、客户和用户数据面临风险的合法问题。 用户可能会以为项目数据并非专有数据，或者可能试图获取公司数据以获得个人利益，从而违反公司策略和法律标准。 通过离开用户策略模板使用数据[](insider-risk-management-policies.md#policy-templates)盗窃的内部风险管理策略会自动检测通常与此类盗窃相关的活动。 通过此策略，你将通过离开用户来自动收到与数据盗窃相关的可疑活动的警报，以便你可以采取适当的调查操作。 此策略模板需要为组织配置 [Microsoft 365 HR](import-hr-data.md) 连接器。

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>有意或无意泄露敏感或机密信息

在大多数情况下，用户会尽量正确处理敏感信息或机密信息。 但有时，用户可能会出错，信息可能会意外在组织外部共享或违反信息保护策略。 In other circumstances， users may intently leak or share sensitive and confidential information with malicious intent and for potential personal gain. 使用下列数据泄露策略模板创建的内部风险管理策略会自动检测通常与共享敏感或机密信息相关的活动：

- [常规数据泄露](insider-risk-management-policies.md#general-data-leaks)
- [按优先级用户的数据泄露 (预览) ](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [在预览版中，由 (用户泄露) ](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>预览版中有意或无意 (违反) 

在新式工作场所中管理其设备时，用户通常具有很大程度的控制。 这可能包括安装或卸载执行其职责所需的应用程序的权限或临时禁用设备安全功能的功能。 无论此活动是无意的、意外的还是恶意的，此行为都可能会给组织带来风险，并且对于识别并采取行动以最大限度地减少风险非常重要。 为了帮助标识这些有风险的安全活动，以下内部风险管理安全策略违反模板对安全风险指示器进行评分，并使用 Microsoft Defender for Endpoint 警报提供与安全相关的活动的见解：

- [预览版中的 (违反) ](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [离开用户以使用预览版 (违反) ](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [预览版中优先级用户违反 (违反) ](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [取消注册的用户在预览版中违反 (违反) ](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>基于位置、访问级别或风险历史记录的用户策略 (预览) 

您组织中用户可能具有不同的风险级别，具体取决于他们的位置、敏感信息的访问级别或风险历史记录。 这可能包括组织的执行领导团队成员、具有大量数据和网络访问权限的 IT 管理员，或者过去具有风险活动历史记录的用户。 在这些情况下，更仔细的检查和更积极的风险评分对于帮助显示警报以便进行调查和快速操作非常重要。 为了帮助识别这些类型的用户的风险活动，您可以创建优先级用户组，然后从以下策略模板创建策略：

- [预览版中优先级用户违反 (违反) ](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [按优先级用户的数据泄露 (预览) ](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>从预览体验中取消注册的用户 (行为) 

雇佣关系事件可以通过几种与内部风险相关的方式影响用户行为。 这些压力因素可能是性能考核不佳、职位降级或用户被放在绩效考核计划中。 虽然大多数用户不会恶意响应这些事件，但是这些操作所承受的压力可能会导致某些用户采取他们在正常情况下通常不会考虑的操作。 为了帮助标识这些类型的风险活动，以下内部风险管理策略模板使用 Microsoft 365 HR 连接器，并开始对可能发生在雇佣压力因素事件附近的行为进行评分风险指标：

- [在预览版中，由 (用户泄露) ](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [取消注册的用户在预览版中违反 (违反) ](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>准备好开始了吗？

- 请参阅 [规划内部风险管理，](insider-risk-management-plan.md) 了解如何准备在组织中启用内部风险管理策略。
- 请参阅 [内部风险管理设置入门，](insider-risk-management-settings.md) 为内部风险策略配置全局设置。
- 请参阅 [内部风险管理入门，](insider-risk-management-configure.md) 以配置先决条件、创建策略并开始接收警报。
