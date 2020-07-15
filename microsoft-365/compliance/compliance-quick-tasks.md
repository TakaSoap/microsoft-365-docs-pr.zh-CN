---
title: Microsoft 365 合规性入门的快速任务
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: 了解可帮助您在 Microsoft 365 中快速开始遵守合规性的任务。
ms.openlocfilehash: a946d4711111089ba6074b2c264b8edd36a01315
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126611"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Microsoft 365 合规性入门的快速任务

如果你不熟悉 Microsoft 365 合规性并想要从哪里开始，本文将提供有关基础知识的指南，并对重要合规性任务进行优先级划分。 本文将帮助您快速开始管理和监控数据、保护信息和最大限度地减少内幕风险。

如果您正在了解如何最佳地管理风险、保护数据以及与新远程员工的法规和标准保持一致，本文也非常有用。 现在，员工以新的方式进行协作和相互连接，这意味着您的现有合规性过程和控件可能需要进行调整。 在您的组织中确定和管理这些新的合规性风险对保护数据和最大限度地减少威胁和风险至关重要。

完成这些基本合规性任务后，请考虑通过实施其他 Microsoft 365 合规性解决方案来扩大组织中的合规性覆盖范围。

## <a name="task-1-configure-compliance-permissions"></a>任务1：配置合规性权限

管理组织中的哪些人能够访问 Microsoft 365 合规性中心以查看内容和执行管理任务，这一点非常重要。 Microsoft 365 提供特定于合规性的管理角色，并使用 Microsoft 365 合规性中心中包含的工具。

首先向组织中的人员分配合规性权限，以便他们可以执行这些任务，并防止未经授权的人员访问其职责之外的区域。 在开始配置和实施 Microsoft 365 附带的合规性解决方案之前，您需要确保已将适当的人员分配给**合规性数据管理员**和**合规性管理员**管理员角色。 你还需要将用户分配到 Azure Active Directory 全局读取器角色，以按合规性分数查看数据。

有关配置权限以及将用户分配到管理员角色的分步指导，请参阅[安全性 & 合规性中心中的权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

## <a name="task-2-know-your-state-of-compliance"></a>任务2：了解合规性状态

如果你不知道你的位置，则很难知道要转到的位置。 满足合规性需求包括了解当前风险级别以及这些不断变化的时间可能需要哪些更新。 无论您的组织是对合规性要求的新，还是具有控制行业的标准和法规的经验丰富的经验，为提高合规性，最好的一个最佳做法是了解您的组织的地位。

[Microsoft 合规性分数](compliance-score.md)可帮助您了解组织的合规性状况，并突出显示可能需要改进的领域。 合规性分数使用集中式仪表板计算基于风险的分数，衡量您在完成操作方面的进展，以帮助降低数据保护和法规标准的风险。 您还可以使用合规性分数作为一种工具来跟踪您的所有风险评估。 它提供了工作流功能，可帮助您通过通用工具高效完成风险评估。

有关开始使用合规性分数的分步指南，请参阅[设置合规性分数](compliance-score-setup.md)。

>[!IMPORTANT]
>大多数组织的安全性和合规性紧密集成。 您的组织必须解决基本安全、威胁防护和标识和访问管理方面的问题，以帮助提供纵深防御的安全性和合规性方法，这一点非常重要。
>
>请检查 Microsoft 365 安全中心中的[microsoft 365 安全分数](../security/mtp/microsoft-secure-score.md)，并完成以下文章中概述的任务：
>
> - [安全路线图-前30天、90天及以上的首要优先级](../security/office-365-security/security-roadmap.md)
> - [用于安全团队的前12个任务以支持在家中工作](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>任务3：为您的组织启用审核

现在，您已确定组织的当前状态以及谁可以管理合规性功能，下一步是确保您有数据进行合规性调查，并在您的组织中生成网络和用户活动报告。 启用审核也是本文后面所述的合规性解决方案的重要先决条件。

审核日志提供的见解是帮助满足合规性要求的重要工具，可帮助您管理和监视需要改进的合规性区域。 必须先启用审核日志记录，然后才能记录活动，以及在搜索审核日志之前。 如果启用此设置，组织中的用户和管理员活动将记录在审核日志中，并保留90天，且最多为一年，具体取决于分配给用户的许可证。

有关启用审核的分步说明，请参阅[打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>任务4：创建策略以向你通知潜在合规性问题

Microsoft 提供了几种内置的警报策略，可帮助确定管理权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。 默认情况下，这些策略处于打开状态，但您可能需要配置自定义警报，以帮助管理特定于您的组织的合规性要求。

使用 "通知策略" 和 "通知仪表板工具" 创建自定义通知策略，并查看用户执行符合策略条件的活动时生成的警报。 一些示例可能是使用警报策略来跟踪影响组织中的合规性要求、权限和数据丢失事件的用户和管理活动。

有关创建自定义警报策略的分步指南，请参阅[安全与合规中心中的警报策略](alert-policies.md)。

## <a name="task-5-configure-just-in-time-access-for-your-administrators"></a>任务5：为管理员配置实时访问

某些用户对敏感信息或关键网络配置设置的持续访问是受到危害的帐户或内部威胁活动的潜在路径。 [特权访问管理](privileged-access-management-overview.md)通过限制对敏感数据的访问或对关键配置设置的访问，帮助保护组织不受破坏并帮助满足合规性最佳做法。 为需要提升权限的任务实现实时访问规则，而不是具有持续访问权限的管理员。 在 Microsoft 365 中启用 "特权访问管理" 使组织能够以零为依据的权限运行，并提供了抵御受影响的管理访问漏洞的防御层。

有关配置特权访问管理的分步指南，请参阅[特权访问管理入门](privileged-access-management-configuration.md)。 有关权限访问管理许可的信息，请参阅[适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#privileged-access-management-in-office-365)。

## <a name="task-6-classify-and-protect-sensitive-data"></a>任务6：对敏感数据进行分类和保护

To get their work done, people in your organization collaborate with others both inside and outside the organization. This means that content no longer stays behind a firewall—it can roam everywhere, across devices, apps, and services. And when it roams, you want it to do so in a secure, protected way that meets your organization's business and compliance policies.

[灵敏度标签](sensitivity-labels.md)允许您对组织的数据进行分类和保护，同时确保用户工作效率和协作能力不阻止。 使用敏感度标签强制实施加密和使用限制应用视觉标记，并保护跨平台和设备、内部部署和云中的信息。

有关配置和使用敏感度标签的分步指南，请参阅[敏感度标签入门](get-started-with-sensitivity-labels.md)。 有关区分大小的标签许可信息，请参阅[适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

## <a name="task-7-configure-a-retention-policy"></a>任务7：配置保留策略

[保留策略](retention.md)使您能够主动决定是保留内容、删除内容还是两者都保留，然后在指定的保留期结束时删除内容。 您可能需要执行这些操作以遵守行业法规和内部策略，以及在发生诉讼或违反安全漏洞时降低风险。

当内容符合保留策略时，用户可以继续编辑和处理内容，就好像没有任何更改。 内容将保留在其原始位置。 但是，如果有人编辑或删除了保留策略遵守的内容，则原始内容的副本会保存到一个安全位置，在该位置保存该内容的保留策略生效。

您可以快速为 Microsoft 365 环境中的多个位置设置保留策略： Exchange 邮件和公用文件夹、SharePoint 网站、OneDrive 帐户和 Microsoft 365 组。 称为 "组织范围内的保留策略"，对该策略可以包含的邮箱数或站点数没有限制。 但是，如果您需要获得更具体的信息，可以通过为特定位置配置保留策略，然后包含或排除网站或用户来执行此操作。

有关配置保留策略的分步指南，请参阅[创建和配置保留策略](create-retention-policies.md)。 有关记录管理许可的信息，请参阅[适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management)。

## <a name="task-8-configure-sensitive-information-and-offensive-language-policies"></a>任务8：配置敏感信息和冒犯性语言策略

保护敏感信息并检测和操作工作区骚扰事件是遵守内部策略和标准的重要部分。 Microsoft 365 中的[通信合规性](communication-compliance-feature-reference.md)帮助你快速检测、捕获和采取补救措施进行电子邮件和 Microsoft 团队通信，从而帮助最大限度地降低这些风险。 其中包括不恰当的通信，其中包含与组织内部和外部的敏感信息共享的猥亵、威胁以及骚扰和通信。

预定义的*冒犯性语言和反骚扰*策略模板允许您扫描内部和外部通信以实现策略匹配，以便指定的审阅者可以对其进行检查。 审阅者可以在组织中调查扫描的电子邮件、Microsoft 团队、Yammer 或第三方通信，并采取适当的补救措施以确保它们符合组织的标准。

预定义的*敏感信息*策略模板可帮助您快速创建一个策略来扫描电子邮件和 Microsoft 工作组通信，其中包含定义的敏感信息类型或关键字，以帮助确保重要数据不会与不应访问的用户共享。 这些活动可能包括有关内幕交易或其他 collusion 活动的未经授权的机密项目或特定于行业的规则的通信。

有关规划和配置通信合规性的分步指南，请参阅[plan for communication 合规性](communication-compliance-plan.md)并[开始进行通信合规性](communication-compliance-configure.md)。 有关通信合规性许可的信息，请参阅[适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)。

## <a name="next-steps"></a>后续步骤

至此，已为组织配置合规性管理基础知识，请考虑 Microsoft 365 中的以下合规性解决方案，以帮助保护敏感信息，并检测和操作其他内幕风险。

### <a name="configure-retention-labels"></a>配置保留标签

虽然保留策略适用于容器级别和 SharePoint 网站和 Exchange 邮箱等位置，但[保留标签](retention.md#retention-labels)允许对保留和删除策略进行更具体的设定。 例如，在文档或电子邮件级别，最终用户除了可由管理员自动应用之外，还可以手动应用。 您还可以将保留标签应用于 SharePoint 中的文档库、文件夹或文档集，以便存储在该位置的所有文档都继承默认保留标签。

此外，保留标签支持[记录管理](records-management.md)以将内容标记为记录。 在此情况下，无法更改或删除标签，也不能编辑或删除内容。 为了帮助组织遵守法规要求，可能需要这些限制。

有关创建和发布保留标签的分步指南，请参阅以下指南：
- [创建保留标签并在应用程序中应用](create-apply-retention-labels.md)
- [将保留标签自动应用于内容](apply-retention-labels-automatically.md)

有关记录管理许可的信息，请参阅[适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management)。

### <a name="identify-and-define-sensitive-information-types"></a>标识和定义敏感信息类型

根据组织数据中的信息中包含的模式定义敏感信息类型。 使用[内置的敏感信息类型](what-the-sensitive-information-types-look-for.md)可帮助确定和保护信用卡号码、银行帐号和护照号码等。 或创建您自己的特定于您的组织的[自定义敏感度信息类型](custom-sensitive-info-types.md)。

有关定义自定义敏感信息类型的分步指导，请参阅[在安全 & 合规性中心中创建自定义敏感信息类型](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type)。

### <a name="prevent-data-loss"></a>防止数据丢失

[数据丢失防护（DLP）策略](data-loss-prevention-policies.md)允许您识别、监视和自动保护 Microsoft 365 组织内的敏感信息。 使用 DLP 策略可识别 Microsoft 服务中的敏感信息，防止意外共享敏感信息，并帮助用户了解如何在不中断其工作流的情况下保持合规性。

有关配置 DLP 策略的分步指南，请参阅[DLP 策略建议](get-started-with-dlp-policy-recommendations.md)入门和[开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)。 有关数据丢失管理许可的信息，请参阅[适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。

### <a name="detect-and-act-on-insider-risks"></a>检测内幕风险并对其执行操作

员工越来越多地能够跨各种各样的平台和服务创建、管理和共享数据。 在大多数情况下，组织具有有限的资源和工具来确定和缓解组织范围的风险，同时满足合规性要求和员工隐私标准。 这些风险可能包括通过在意外 oversharing 或恶意意向的情况中，使员工和数据泄露外部信息泄露的数据被盗。

Microsoft 365 中的[内幕风险管理](insider-risk-management-policies.md)使用全面的服务和第三方指示器来帮助您快速识别、会审和操作有风险的用户活动。 通过使用 Microsoft 365 和 Microsoft Graph 中的日志，内幕风险管理允许您定义特定策略以确定风险指示器，并采取措施来缓解这些风险。

有关规划和配置内幕风险管理策略的分步指南，请参阅[plan for 内幕](insider-risk-management-plan.md)风险管理和[内幕风险管理入门](insider-risk-management-configure.md)。 有关内幕风险管理许可的信息，请参阅[适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)。
