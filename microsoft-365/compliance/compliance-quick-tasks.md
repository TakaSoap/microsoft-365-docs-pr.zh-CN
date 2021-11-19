---
title: Microsoft 365 合规性入门快速任务
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365initiative-compliance
ms.custom: admindeeplinkDEFENDER
ms.localizationpriority: medium
description: 了解将帮助您快速开始使用 Microsoft 365 中Microsoft 365。
ms.openlocfilehash: 621bcbdbbe38be4cbda79e5cf6afcc9846f87e0d
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111035"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Microsoft 365 合规性入门快速任务

如果你是第一次了解Microsoft 365并想知道从何处开始，本文将提供有关基本要求的指导，并优先执行重要的合规性任务。 本文将帮助你快速开始管理和监视数据、保护信息以及将内部风险最小化。

如果你正在找出如何以最佳方式管理风险、保护数据并符合新远程员工的法规和标准，本文也很有用。 员工现在以新方式相互协作和联系，这意味着你现有的合规性流程和控制措施可能需要进行调整。 在组织中识别和管理这些新合规性风险对于保护数据并最大限度地减少威胁和风险至关重要。

完成这些基本合规性任务后，请考虑通过实施额外的合规性解决方案来扩大Microsoft 365范围。

## <a name="task-1-configure-compliance-permissions"></a>任务 1：配置合规性权限

管理组织中哪些人员有权访问 Microsoft 365 合规中心查看内容和执行管理任务非常重要。 Microsoft 365提供特定于合规性和使用应用程序中包含的工具的管理Microsoft 365 合规中心。

首先，向组织人员分配合规性权限，以便他们可以执行这些任务，并防止未经授权的人员访问其职责之外的区域。 在开始配置和实施合规性解决方案之前，需要确保向合规性数据管理员和合规性管理员管理员角色分配适当的人员Microsoft 365。  你还需要将用户分配给全局Azure Active Directory查看合规性管理器数据。

有关配置权限和将人员分配给管理员角色的分步指南，请参阅安全与合规中心& [权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

## <a name="task-2-know-your-state-of-compliance"></a>任务 2：了解合规性状态

如果您不知道您在哪里，则很难知道在哪里。 满足合规性需求包括了解当前风险级别以及在这些不断变化的时间可能需要哪些更新。 无论你的组织是了解合规性要求还是对管理你的行业的标准和法规有丰富经验，改进合规性可以做的最好的一件事就是了解你的组织在什么位置。

[Microsoft 合规性管理器](compliance-manager.md) 可帮助你了解组织的合规性状态，并突出显示可能需要改进的领域。 合规性管理器使用集中式仪表板计算基于风险的分数，以衡量完成有助于降低数据保护和监管标准风险的操作的进度。 您还可以使用合规性管理器作为工具来跟踪所有风险评估。 它提供帮助你通过通用工具有效完成风险评估的工作流功能。

有关合规性管理器的分步指南，请参阅合规性管理器 [入门](compliance-manager-setup.md)。

> [!IMPORTANT]
> 大多数组织都紧密集成了安全性和合规性。 组织解决基本安全、威胁防护、标识和访问管理方面的问题非常重要，这有助于提供针对安全性和合规性的深层防御方法。
>
> 在[Microsoft 365门户](../security/defender/microsoft-secure-score.md)中检查Microsoft 365 Defender安全分数，<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"></a>并完成以下文章中概述的任务：
>
> - [安全路线图 - 前 30 天、前 90 天及以后的首要任务](../security/office-365-security/security-roadmap.md)
> - [支持在家工作的安全团队的 12 大任务](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>任务 3：为组织启用审核

现在，你已确定组织的当前状态以及谁可以管理合规性功能，下一步是确保你拥有数据以执行合规性调查并生成组织中网络和用户活动的报告。 启用审核也是本文稍后介绍的合规性解决方案的重要先决条件。

Insights提供审核日志是一个有价值的工具，有助于将合规性要求与可帮助您管理和监视需要改进的合规性区域的解决方案相匹配。 审核日志记录必须先启用，然后才能记录活动，然后才能搜索审核日志。 启用后，组织的用户和管理员活动将记录在 审核日志 中，并保留 90 天，最多保留一年，具体取决于分配给用户的许可证。

有关启用审核的逐步操作说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>任务 4：创建策略以提醒您潜在的合规性问题

Microsoft 提供了几个内置警报策略，可帮助识别管理员权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。 这些策略默认启用，但可能需要配置自定义警报以帮助管理特定于组织的合规性要求。

使用警报策略和警报仪表板工具创建自定义警报策略，并查看当用户执行符合策略条件的活动时生成的警报。 一些示例可能是使用警报策略跟踪影响组织中合规性要求、权限和数据丢失事件的用户和管理员活动。

有关创建自定义警报策略的分步指南，请参阅安全与合规中心中的警报 [策略](alert-policies.md)。

## <a name="task-5-classify-and-protect-sensitive-data"></a>任务 5：分类和保护敏感数据

组织内人员需要与组织内外的其他人员协作，才能完成工作。也就是说，内容不再一直停留在防火墙后面，而是可跨设备、应用和服务到处漫游。你希望内容的漫游方式不仅安全、受保护，还符合组织的业务和合规性策略。

[敏感度标签](sensitivity-labels.md) 可让你对组织的数据进行分类和保护，同时确保用户工作效率及其协作能力不受阻碍。 使用敏感度标签强制实施加密和使用限制，应用视觉标记，并保护跨平台和设备、本地和云的信息。

有关配置和使用敏感度标签的分步指南，请参阅敏感度 [标签入门](get-started-with-sensitivity-labels.md)。 有关敏感度标签许可信息，请参阅Microsoft 365安全[与合规&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

## <a name="task-6-configure-a-retention-policy"></a>任务 6：配置保留策略

保留 [策略](retention.md) 允许你主动决定是保留内容还是删除内容，或同时保留内容，然后在指定的保留期结束时删除内容。 可能需要这些操作来遵守行业法规和内部策略，并降低诉讼或安全漏洞的风险。

当内容受保留策略影响时，用户可以继续编辑和操作内容，就像没有任何变化一样。 内容将就地保留在其原始位置。 但是，如果有人编辑或删除受保留策略限制的内容，原始内容的副本将保存到保留该内容的安全位置，同时该内容的保留策略生效。

您可以快速为 Microsoft 365 环境中的多个位置（如 Exchange 邮件、SharePoint 网站、OneDrive 帐户和 Microsoft 365 组）设置保留策略。 此策略可自动包含的邮箱或网站数没有限制。 但是，如果需要更具选择性，可以通过为特定位置配置保留策略并包括或排除网站或用户来这样做。

有关配置保留策略的分步指南，请参阅创建 [和配置保留策略](create-retention-policies.md)。 如果你刚开始在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>任务 7：配置敏感信息和冒犯性语言策略

保护敏感信息以及检测和处理工作场所骚扰事件是遵守内部策略和标准的重要组成部分。 [电子邮件中的](communication-compliance.md)Microsoft 365合规性可帮助您快速检测、捕获电子邮件和邮件通信并执行修正操作，从而Microsoft Teams风险。 其中包括包含亵亵、威胁、骚扰和在组织内外共享敏感信息的不当通信。

预定义的 *冒犯性* 语言和反冒犯性策略模板允许你扫描内部和外部通信中的策略匹配项，以便指定的审阅者可以检查这些匹配。 审阅者可以调查组织中扫描的电子邮件、Microsoft Teams、Yammer 或第三方通信，并采取适当的补救措施以确保他们符合组织标准。

预定义的敏感信息策略模板可帮助您快速创建策略，以扫描包含已定义的敏感信息类型或关键字的电子邮件和 Microsoft Teams 通信，以帮助确保重要数据不会与不应具有访问权限的人共享。 这些活动可能包括有关机密项目的未经授权的通信，或有关内部交易或其他合作活动的行业特定规则。

有关计划和配置通信合规性的分步指南，请参阅规划通信合规性和[](communication-compliance-plan.md)[通信合规性入门](communication-compliance-configure.md)。 有关通信合规性许可信息，请参阅[Microsoft 365安全与合规&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)。

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>任务 8：查看敏感项目发生了什么

敏感度标签、敏感信息类型、保留标签和策略以及可训练分类器可用于对 Exchange、SharePoint 和 OneDrive 中的敏感项目进行分类和标记，如前面的任务所见。 快速任务旅程中的最后一步是查看哪些项目已标记，以及用户正在针对这些敏感项目采取的操作。 [内容资源管理器](data-classification-content-explorer.md)[和活动资源管理器](data-classification-activity-explorer.md)提供此可见性。

### <a name="content-explorer"></a>内容资源管理器
 内容资源管理器允许您以本机格式查看已分类为敏感信息类型或属于可训练分类器特定分类的所有项目，以及应用了敏感度或保留标签的所有项目。

有关使用内容资源管理器的分步指南，请参阅了解数据 [-](data-classification-overview.md)数据分类概述和内容 [资源管理器入门](data-classification-content-explorer.md)。

### <a name="activity-explorer"></a>活动资源管理器
活动资源管理器可帮助你监视已分类和已标记敏感项正在完成的工作，包括：
- SharePoint
- Exchange
- OneDrive

有 30 多种不同筛选器可供使用，其中有：

- 日期范围
- 活动类型
- 位置
- 用户
- 敏感度标签
- 保留标签
- 文件路径
- DLP 策略

有关使用活动资源管理器的分步指南，请参阅活动 [资源管理器入门](data-classification-activity-explorer.md)。

## <a name="next-steps"></a>后续步骤

现在，你已为组织配置了合规性管理的基础知识，请考虑 Microsoft 365 中的以下合规性解决方案，以帮助你保护敏感信息，检测并处理其他内部风险。

### <a name="configure-retention-labels"></a>配置保留标签

虽然保留策略在容器级别应用于 SharePoint 站点和 Exchange 邮箱等位置，但保留标签允许更具体的保留[](retention.md#retention-labels)和删除策略目标。 例如，在文档或电子邮件级别，除了管理员自动应用外，最终用户还可以手动应用。 您还可以将保留标签应用于 SharePoint 中的文档库、文件夹或文档集，以便存储在该位置的所有文档继承默认保留标签。

此外，保留标签还 [支持记录管理](records-management.md) 以将内容标记为记录。 发生这种情况时，标签对可能帮助组织遵守法规要求的内容设置其他限制。

有关创建和发布保留标签的分步指南，请参阅以下指南：
- [创建保留标签并在应用中应用它们](create-apply-retention-labels.md)
- [自动向内容应用保留标签](apply-retention-labels-automatically.md)

若要开始使用记录管理，请参阅记录 [管理入门](get-started-with-records-management.md)。

### <a name="identify-and-define-sensitive-information-types"></a>标识和定义敏感信息类型

根据组织数据中信息中包含的模式定义敏感信息类型。 使用 [内置敏感信息类型](./sensitive-information-type-entity-definitions.md) 有助于识别和保护信用卡号、银行帐号、护照号等。 或创建自己的 [特定于您的组织的自定义](create-a-custom-sensitive-information-type.md) 敏感度信息类型。

有关定义自定义敏感信息类型的分步指南，请参阅在安全与合规中心内& [敏感信息类型](./create-a-custom-sensitive-information-type.md)。

### <a name="prevent-data-loss"></a>防止数据丢失

[通过 DLP (策略) ](dlp-learn-about-dlp.md)数据丢失防护，您可以识别、监视和自动保护组织中Microsoft 365敏感信息。 使用 DLP 策略可标识整个 Microsoft 服务 中的敏感项目，防止意外共享敏感项目，并帮助用户了解如何保持合规性而不会中断其工作流。

有关配置 DLP 策略的分步指南，请 [创建](create-test-tune-dlp-policy.md)、测试和调整 DLP 策略。 有关数据丢失管理许可信息，请参阅Microsoft 365[安全与合规&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。

### <a name="detect-and-act-on-insider-risks"></a>检测内部风险并采取行动

越来越多的员工拥有创建、管理和共享各种平台和服务的数据的访问权。 在大多数情况下，组织具有有限的资源和工具来识别和缓解组织范围内的风险，同时还满足合规性要求和员工隐私标准。 这些风险可能包括因员工离职而窃取数据，以及因意外泄露或恶意意图而泄露组织外部信息。

[Microsoft 365中的](insider-risk-management-policies.md)内部风险管理使用整个服务和第三方指示器来帮助你快速识别、会审和操作有风险的用户活动。 通过使用来自Microsoft 365和Microsoft Graph的日志，内部风险管理允许你定义特定策略来识别风险指示器并采取措施来缓解这些风险。

有关计划和配置内部风险管理策略的分步指南，请参阅规划内部风险管理和内部[](insider-risk-management-plan.md)[风险管理入门](insider-risk-management-configure.md)。 有关内部风险管理许可信息，请参阅Microsoft 365安全[与合规&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)。
