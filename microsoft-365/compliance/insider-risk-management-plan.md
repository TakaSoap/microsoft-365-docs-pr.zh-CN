---
title: 内部风险管理计划
description: 了解如何在组织中规划使用内部风险管理策略。
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
ms.collection: m365-security-compliance
ms.openlocfilehash: f2581c4756a57926ab4a4539be8c383b0479e567
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126621"
---
# <a name="plan-for-insider-risk-management"></a>内部风险管理计划

在组织中开始使用 [内部](insider-risk-management.md) 风险管理之前，信息技术和合规性管理团队应检查重要的规划活动和注意事项。 全面了解和规划以下方面的部署将有助于确保内部风险管理功能的实现和使用顺利进行，并与解决方案的最佳实践保持一致。

## <a name="work-with-stakeholders-in-your-organization"></a>与组织中的利益干系人合作

确定组织中适当的利益干系人，以协作对内部风险管理警报和案例采取行动。 在初始计划和端到端内部风险管理工作流中要考虑的一些建议利益干系人[](insider-risk-management.md#workflow)来自组织的以下领域：

- 信息技术
- 合规性
- 隐私
- 安全性
- 人力资源
- 法律

## <a name="determine-any-regional-compliance-requirements"></a>确定任何区域合规性要求

不同的地理和组织区域可能有与组织的其他区域不同的合规性和隐私要求。 与这些领域的利益干系人合作，确保他们了解内部风险管理中的合规性和隐私控制，以及如何在组织的不同区域使用这些控制措施。 在某些情况下，合规性和隐私要求可能需要根据用户的情况或针对该领域的法规或策略要求，指定或限制某些利益干系人进行调查和案件的策略。

如果您要求特定利益干系人参与涉及特定区域、角色或部门用户的情况调查，您可能需要实施单独的 (，即使针对不同地区和用户的相同) 内部风险管理策略。 [](insider-risk-management-policies.md) 通过此配置，适当的利益干系人可以更轻松地对与角色和地区相关的案例进行会审和管理。 此外，你可能要考虑为调查者和审阅者使用与用户语言相同的区域创建流程和策略，以帮助简化内部风险管理警报和案例的上报过程。

## <a name="plan-for-the-review-and-investigation-workflow"></a>规划审阅和调查工作流

选择专门的利益干系人，定期在 [Microsoft 365](https://compliance.microsoft.com/)合规中心中监视和查看警报和案例。 请务必了解如何将不同的利益干系人分配给内部风险管理中提供的不同角色组。

根据合规性管理团队的结构，你可以将用户分配到特定角色组来管理不同的内部风险管理功能集。 配置内部风险管理时，从以下角色组选项中进行选择：

| **角色组** | **角色权限** |
| :---- | :---------------- |
| **内部风险管理** | 使用此角色组管理单个组中组织的内部风险管理。 通过为指定的管理员、分析师和调查人员添加所有用户帐户，可以在单个组中配置内部风险管理权限。 此角色组包含所有内部风险管理权限角色。 此配置是快速开始使用内部风险管理的最简单方法，非常适合不需要为单独的用户组定义单独权限的组织。|
| **内部风险管理管理员** | 使用此角色组最初配置内部风险管理，稍后再将内部风险管理员隔离到定义的组中。  此角色组的用户可以创建、读取、更新和删除内部风险管理策略、全局设置和角色组分配。 |
| **预览体验计划风险管理分析员** | 使用此组向将充当内部风险案例分析员的用户分配权限。 此角色组的用户可以访问所有内部风险管理警报、案例和通知模板。 他们无法访问内部风险内容资源管理器。 |
| **预览体验计划风险管理调查员** | 使用此组向将充当内部风险数据调查者的用户分配权限。 此角色组的用户可以访问所有内部风险管理警报、案例、通知模板和适用于所有情况的内容资源管理器。 |

## <a name="understand-requirements-and-dependencies"></a>了解要求和依赖关系

根据计划实施内部风险管理策略的方法，你需要拥有正确的 Microsoft 365 许可订阅，并了解和规划某些解决方案先决条件。

**许可：** 内部风险管理作为 Microsoft 365 许可订阅广泛选择的一部分提供。 有关详细信息，请参阅 [内部风险管理入门](insider-risk-management-configure.md#subscriptions-and-licensing) 文章。

如果你没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试内部风险管理，可以将[Microsoft 365](/office365/admin/try-or-buy-microsoft-365)添加到现有订阅或注册[](https://www.microsoft.com/microsoft-365/enterprise)Microsoft 365 企业版 E5 试用版。

**策略模板要求：** 根据选择的策略模板，在组织中配置内部风险管理之前，您需要了解和规划以下要求：

- 通过 **离开用户** 模板使用数据盗窃时，必须配置 Microsoft 365 HR 连接器，以定期导入组织中用户的离职日期和终止日期信息。 有关 [为组织配置](import-hr-data.md) Microsoft 365 HR 连接器的分步指南，请参阅"使用 HR 连接器导入数据"一文。
- 使用数据泄露模板时，必须至少配置一个数据丢失防护 (DLP) 策略，以定义组织中敏感信息并接收针对高严重性 DLP 策略警报的内部风险警报。 有关 [为组织](create-test-tune-dlp-policy.md) 配置 DLP 策略的分步指南，请参阅"创建、测试和调整 DLP 策略"一文。
- 使用 **安全策略违反** 模板时，必须在 Defender 安全中心中为内部风险管理集成启用 Microsoft Defender for Endpoint，以导入安全违反警报。 请参阅 [Microsoft Defender 中的](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) "配置高级功能"一文，了解启用 Defender for Endpoint 与内部风险管理集成的分步指南。
- 使用 **Disgruntled** 用户模板时，必须配置 Microsoft 365 HR 连接器，以定期导入组织中用户的绩效或降级状态信息。 有关 [为组织配置](import-hr-data.md) Microsoft 365 HR 连接器的分步指南，请参阅"使用 HR 连接器导入数据"一文。

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>在生产环境中对一小组用户进行测试

在生产环境中广泛启用解决方案之前，您可以考虑使用一小组生产用户测试策略，同时在组织中进行必要的合规性、隐私和法律审查。 在测试环境中评估内部风险管理需要生成模拟用户操作和其他信号，以创建用于会审和案件处理的警报。 对于大多数组织来说，此方法不可行，因此首选在生产环境中对一小组用户测试内部风险管理。

在此测试期间，在策略设置中保持匿名化功能，以匿名处理内部风险管理控制台中的用户显示名称，以维护工具中的隐私。 此设置有助于保护具有策略匹配项的用户的隐私，并且有助于在针对内部风险警报的数据调查和分析审查中提高对象性。

如果在配置内部风险管理策略后未立即看到任何警报，这可能意味着尚未达到最低风险阈值。 检查策略是否触发并正常工作的一个好方法就是查看用户是否位于"用户"页上 **的策略范围内。**

## <a name="resources-for-stakeholders"></a>利益干系人的资源

与组织中管理和修正工作流中包含的利益干系人共享内部风险管理文档：

- [创建和管理内部风险策略](insider-risk-management-policies.md)
- [调查内部风险警报](insider-risk-management-alerts.md)
- [对内部风险案例采取措施](insider-risk-management-cases.md)
- [使用内部风险内容资源管理器查看案例数据](insider-risk-management-content-explorer.md)
- [创建内部风险通知模板](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>准备好开始了吗？

准备好为组织配置内部风险管理了吗？ 查看以下文章：

- [开始使用内部风险管理设置来](insider-risk-management-settings.md) 配置全局策略设置。
- [开始内部风险管理，](insider-risk-management-configure.md) 以配置先决条件、创建策略并开始接收警报。
