---
title: 内部风险管理
description: 了解如何使用 Microsoft 365 中的内幕风险管理帮助最大限度地减少组织中的风险。
keywords: Microsoft 365，内幕风险，风险管理，合规性
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
ms.openlocfilehash: c9b19066b57d40ad33ac8d50ee1bee1f4a828030
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48774045"
---
# <a name="insider-risk-management-in-microsoft-365"></a>Microsoft 365 中的内幕风险管理

内幕风险管理是 Microsoft 365 中的一种合规性解决方案，可帮助您检测、调查和操作组织中的恶意和意外活动，从而帮助最大限度地减少内部风险。 内幕风险策略允许您定义要在组织中识别和检测的风险类型，包括在案例中进行操作以及在需要时向 Microsoft 高级电子数据展示上报案例。 组织中的风险分析师可以快速采取适当的措施，以确保用户符合组织的合规性标准。

观看以下视频，了解内幕风险管理如何帮助您的组织防止、检测和包含风险，同时确定组织的价值、文化和用户体验的优先级：
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>新式风险痛点

管理和最大限度地减少组织中的风险从了解新式工作区中发现的风险类型开始。 某些风险由直接控制之外的外部事件和因素驱动。 其他风险由可以最小化和避免的内部事件和用户活动驱动。 某些示例是由组织中的用户进行的非法、不正当、未授权或不道德行为和操作带来的风险。 这些行为包括用户的各种内部风险：

- 敏感数据泄露和数据外泄
- 违反机密性
- 知识财产 (IP) 失窃
- 防
- 内幕交易
- 法规遵从性冲突

新式工作区中的用户有权在各种各样的平台和服务中创建、管理和共享数据。 在大多数情况下，组织具有有限的资源和工具来识别和缓解组织范围的风险，同时还能满足用户的隐私标准。

内幕风险管理使用全面的服务和第三方指示符帮助您快速确定、会审和操作风险活动。 通过使用 Microsoft 365 和 Microsoft Graph 中的日志，内幕风险管理允许您定义特定策略以标识风险指示器。 通过这些策略，您可以确定危险活动并采取措施来缓解这些风险。

内幕风险管理的中心围绕以下原则：

- **透明度** ：根据隐私设计的体系结构平衡用户隐私和组织风险。
- **可配置** ：基于行业、地理位置和业务组的可配置策略。
- **集成** ：跨 Microsoft 365 合规性解决方案的集成工作流。
- 可 **操作** ：提供有关启用用户通知、数据调查和用户调查的见解。

## <a name="workflow"></a>工作流

内幕风险管理工作流可帮助您确定、调查和采取措施来解决组织中的内部风险。 使用集中式策略模板，跨 Microsoft 365 服务的全面活动信号，以及警报和案例管理工具，您可以使用可操作的见解来快速识别风险行为并对其进行操作。

使用以下工作流确定和解决 Microsoft 365 中的内幕风险管理的内部风险活动和合规性问题：

![内幕风险管理工作流](../media/insider-risk-workflow.png)

### <a name="policies"></a>策略

[内幕风险管理策略](insider-risk-management-policies.md) 是使用预定义的模板和策略条件（定义在组织中检查哪些触发事件和风险指示器）创建的。 这些条件包括如何将风险指示器用于通知、策略中包含的用户、确定优先顺序的服务以及监视时间段。

您可以从以下 [策略模板中进行选择，以便快速开始使用 "内幕风险管理"：

- [通过去声用户窃取数据](insider-risk-management-policies.md#data-theft-by-departing-users)
- [常规数据泄露](insider-risk-management-policies.md#general-data-leaks)
- [按优先级用户 (预览的数据泄露) ](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [因不满用户 (预览而进行的数据泄露) ](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [ (预览的常规安全策略冲突) ](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [通过 (preview 中的去声用户进行安全策略违反) ](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [按优先级用户 (预览的安全策略冲突) ](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [因不满用户 (预览) 而违反安全策略的情况 ](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)
- [电子邮件中的冒犯性语言](insider-risk-management-policies.md#offensive-language-in-email)

![内幕风险管理策略仪表板](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>警报

警报由符合策略条件并显示在 " [通知" 仪表板](insider-risk-management-alerts.md)中的风险指示器自动生成。 通过此仪表板，可以快速查看需要查看的所有警报、一段时间内打开的警报以及组织的警报统计信息。 将显示所有策略警报，其中包含以下信息，可帮助您快速识别现有通知的状态和需要采取操作的新警报：

- 状态
- Severity
- 检测时间
- 情况
- 案例状态

![内幕风险管理警报仪表板](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>诊断

需要调查的新用户活动将自动生成为其分配了 *需求审阅* 状态的警报。 审阅者可以快速确定和审阅、评估和会审这些警报。

通过打开新事例、将警报分配给现有事例或消除警报来解决警报。 使用警报筛选器，可以轻松地根据状态、严重性或时间来识别警报。 作为会审过程的一部分，审阅者可以查看策略标识的活动的警报详细信息、查看与策略匹配相关的用户活动、查看警报的严重性并查看用户配置文件信息。

![内幕风险管理会审](../media/insider-risk-triage.png)

### <a name="investigate"></a>调查

为需要对策略匹配的活动详细信息和环境进行更深层次审阅和调查的警报创建[案例](insider-risk-management-cases.md)。 **事例仪表板** 提供了所有活动案例的详细视图、一段时间内的开放事例以及贵组织的案例统计信息。 审阅者可以按状态、打开案例的日期以及上次更新事例的日期来快速筛选案例。

在事例仪表板上选择一个事例将打开调查和审阅的案例。 这一步是内幕风险管理工作流的核心。 此区域是将风险活动、策略条件、警报详细信息和用户详细信息合成到审阅者的集成视图中的。 此区域中的主要调查工具是：

- **用户活动** ：用户活动将自动显示在交互式图表中，该图表按时间和当前或过去风险活动的风险级别绘制活动。 审阅者可以快速筛选和查看用户的整个风险历史记录，并深入了解具体活动以了解详细信息。
- **内容资源管理器** ：自动捕获与警报活动相关联的所有数据文件和电子邮件，并将其显示在内容资源管理器中。 审阅者可以按数据源、文件类型、标记、对话以及其他许多属性来筛选和查看文件和邮件。
- **案例备注** ：审阅者可以在 "事例注释" 部分中为事例提供注释。 此列表合并了一个中心视图中的所有笔记，并包含审阅者和提交的日期信息。

![内幕风险管理调查](../media/insider-risk-investigate.png)

### <a name="action"></a>操作

在调查事例之后，审阅者可以快速处理案例或与组织中的其他风险承担者进行协作。 如果用户无意或无意中违反了策略条件，则可以向用户发送一个简单的提醒通知，以供您为组织自定义的通知模板。 这些通知可用作简单的提醒，也可指导用户进行复习培训或指导，以帮助防止将来出现风险的行为。 有关详细信息，请参阅 [内幕风险管理通知模板](insider-risk-management-notices.md)。

在更严重的情况下，您可能需要与组织中的其他审阅者或服务共享内幕风险管理案例信息。 内幕风险管理与其他 Microsoft 365 合规性解决方案紧密集成，可帮助您实现端到端风险解决方案。

- **高级电子数据展示** ：升级案例以进行调查，以便在 Microsoft 365 中将案例的数据和管理转移到高级电子数据展示。 高级电子数据展示提供了端到端工作流，以保留、收集、查看、分析和导出对组织内部和外部调查做出响应的内容。 它允许法律团队管理整个法律封存通知工作流。 若要了解有关高级电子数据展示事例的详细信息，请参阅 [Microsoft 365 中的高级电子数据展示概述](overview-ediscovery-20.md)。
- **Servicenow (preview)** ： ServiceNow 是一个流行的云计算平台，可帮助组织管理企业运营的数字工作流。 内幕风险管理支持与您的 ServiceNow 服务共享案例警报，并允许您创建与各个内幕风险案例相关的事件和更改请求。 若要了解有关使用 ServiceNow 共享警报信息的详细信息，请参阅 [与 Servicenow 共享事例](insider-risk-management-cases.md#share-the-case)。
- **Office 365 管理 api 集成 (预览)** ：内幕风险管理支持通过 Office 365 管理 api 将警报信息导出到安全信息和事件管理 (SIEM) 服务。 在最适合组织风险流程的平台中访问警报信息，可以在操作风险活动方面提供更大的灵活性。 若要了解有关使用 Office 365 管理 Api 导出通知信息的详细信息，请参阅 [导出警报](insider-risk-management-settings.md#export-alerts-preview)。

>[!NOTE]
>ServiceNow preview 将于 30 2020 年11月结束，并且不会继续。 感谢你的反馈和支持，同时确定后续步骤。

## <a name="scenarios"></a>方案

内幕风险管理可帮助您在以下几个常见方案中检测、调查和采取措施来缓解组织中的内部风险：

### <a name="data-theft-by-departing-users"></a>通过去声用户窃取数据

当用户离开组织（自愿或作为终止的结果）时，通常会对公司、客户和用户数据存在风险带来合法的关注。 用户可能 innocently 假定项目数据并非专有数据，或者可能被引诱采用公司数据进行个人收益，并违反公司政策和法律标准。 [通过脱离用户](insider-risk-management-policies.md#policy-templates)策略模板使用数据失窃的内幕风险管理策略可自动检测通常与此类型的盗窃相关联的活动。 通过此策略，您将自动收到警报，以了解与盗窃用户的数据被盗相关的可疑活动，以便您可以采取适当的调查操作。 为您的组织配置 [Microsoft 365 HR 连接器](import-hr-data.md) 是此策略模板所必需的。

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>敏感或机密信息的有意或无意泄露

在大多数情况下，用户可以尝试更好地处理敏感或机密信息。 但偶尔用户可能会导致错误和信息在您的组织外部被意外共享或违反您的信息保护策略。 在其他情况下，用户可能会有意泄露或共享敏感和机密信息，以实现恶意目的和潜在的个人收益。 使用以下数据泄露策略模板创建的内幕风险管理策略将自动检测通常与共享敏感信息或机密信息相关的活动：

- [常规数据泄露](insider-risk-management-policies.md#general-data-leaks)
- [按优先级用户 (预览的数据泄露) ](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [因不满用户 (预览而进行的数据泄露) ](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

### <a name="offensive-behavior-that-violates-corporate-policies"></a>违反公司政策的冒犯行为

用户到用户的通信通常是意外或恶意违反公司策略的来源。 这些冲突可能包括用户之间的冒犯性语言、威胁和骚扰。 此类型的活动可为敌意的工作环境，并会对用户和更大的组织产生法律行为。 内幕风险管理使用新的内置 Microsoft 365 分类器和 [电子邮件](insider-risk-management-policies.md#offensive-language-in-email) 策略模板中的冒犯性语言来帮助最大限度地减少这些风险。 此策略模板可帮助您快速配置和启用策略，以自动检测和提醒您组织中的这种行为。

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a> (预览) 的有意或无意的安全策略冲突

在新式的工作区中管理其设备时，用户通常会有很大程度的控制。 这可能包括安装或卸载应用程序所需的应用程序的权限，或者临时禁用设备安全功能的功能。 无论此活动是意外的、意外的还是恶意的，此行为可能会给组织带来风险，并且很重要的是确定和采取最大限度地进行最小化。 为了帮助标识这些危险安全活动，以下内幕风险管理安全策略冲突模板会对安全风险指标进行评分，并使用 Microsoft Defender 高级威胁防护 (ATP) 警报来提供与安全相关的活动的见解：

- [ (预览的常规安全策略冲突) ](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [通过 (preview 中的去声用户进行安全策略违反) ](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [按优先级用户 (预览的安全策略冲突) ](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [因不满用户 (预览) 而违反安全策略的情况 ](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>基于位置、访问级别或风险历史记录的用户的策略 (预览) 

组织中的用户可能具有不同的风险级别，具体取决于其位置、敏感信息的访问级别或风险历史记录。 这可能包括组织的管理层领导团队的成员、拥有大量数据和网络访问权限的 IT 管理员，或历史活动较旧的用户。 在这些情况下，更仔细地检查和更高的风险评分对帮助介绍调查和快速操作的提醒非常重要。 为了帮助确定这些类型的用户的危险活动，您可以创建优先级用户组并从以下策略模板创建策略：

- [按优先级用户 (预览的安全策略冲突) ](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [按优先级用户 (预览的数据泄露) ](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>由不满意的用户 (预览的操作和行为) 

雇用强调事件可能会影响用户行为，与内幕风险相关的几种方式。 这些 stressors 可能是不好的性能审核、职位降级或用户正在进行性能评审计划。 尽管大多数用户不会对这些事件进行恶意响应，但这些操作的压力可能会导致某些用户在正常情况下采取通常不会考虑的操作。 为了帮助标识这些类型的危险活动，以下内幕风险管理策略模板使用 Microsoft 365 HR 连接器，并开始计分风险指标，与可能发生的与就业 stressor 事件有关的行为相关：

- [因不满用户 (预览而进行的数据泄露) ](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [因不满用户 (预览) 而违反安全策略的情况 ](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>准备好开始了吗？

- 有关如何准备在组织中启用内幕风险管理策略的说明，请参阅 [Plan for 内幕风险管理](insider-risk-management-plan.md) 。
- 请参阅 [开始使用内幕风险管理设置](insider-risk-management-settings.md) 配置内幕风险策略的全局设置。
- 请参阅 " [内幕风险管理入门](insider-risk-management-configure.md) "，配置先决条件、创建策略并开始接收通知。
