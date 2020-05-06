---
title: 内部风险管理计划
description: 了解如何规划在组织中使用内幕风险管理策略。
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
ms.collection: m365-security-compliance
ms.openlocfilehash: 2b2abd68d767f169ea8e20fc349e6314cc6400d5
ms.sourcegitcommit: e55e4747d3b838baacab8985aefc24aac245c431
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44043396"
---
# <a name="plan-for-insider-risk-management"></a>内部风险管理计划

在您的组织中开始使用[内幕风险管理](insider-risk-management.md)之前，您的信息技术和合规性管理团队应检查重要的规划活动和注意事项。 在以下方面全面了解和规划部署可帮助确保您的内部风险管理功能的实施和使用与解决方案的最佳实践保持一致。

## <a name="work-with-stakeholders-in-your-organization"></a>与组织中的利益干系人合作

确定组织中的相应利益干系人进行协作，以对内幕风险管理警报和案例采取措施。 一些建议的利益干系人（包括在初始规划中）和端到端的[内幕风险管理工作流](insider-risk-management.md#workflow)是组织中以下几个方面的人员：

- 信息技术
- 合规性
- 隐私
- 安全性
- 人力资源人员
- 法律

## <a name="determine-any-regional-compliance-requirements"></a>确定任何区域合规性要求

不同的地理位置和组织区域可能具有与您的组织的其他区域明显不同的合规性和隐私要求。 与这些领域的利益干系人合作，以确保他们了解内幕风险管理中的合规性和隐私控制，以及如何在组织的不同区域中使用它们。 在某些情况下，合规性和隐私要求可能需要策略来根据用户或管理部门的案例或策略要求来指定或限制某些利益干系人的调查和案例。

如果您有特定利益干系人需要涉及特定区域、角色或部门中的员工的案例调查，您可能需要实现针对不同地区和人口的独立（即使相同）[内幕风险管理策略](insider-risk-management-policies.md)。 这将使右侧的利益干系人更轻松地会审和管理与其角色和区域相关的案例。 此外，您可能还需要考虑为一些区域创建流程和策略，在这些区域中，调查人员和审阅者与用户说出的语言相同，有助于简化内幕风险管理警报和案例的升级过程。

## <a name="plan-for-the-review-and-investigation-workflow"></a>规划评审和调查工作流

选择 "专用利益干系人" 以在[Microsoft 365 合规性中心](https://compliance.microsoft.com/)中的定期节奏上监视和查看警报和事例。 请确保了解如何将不同的利益干系人分配给内幕风险管理中可用的不同角色组。

根据合规性管理团队的结构，您可以选择将用户分配给特定角色组，以管理不同的内幕风险管理功能集。 配置内幕风险管理时从这些角色组选项中进行选择：

| **角色组** | **角色权限** |
| :---- | :---------------- |
| **内幕风险管理** | 使用此角色组可在单个组中管理组织的内幕风险管理。 通过添加指定管理员、分析师和调查人员的所有用户帐户，您可以在单个组中配置内幕风险管理权限。 此角色组包含所有内幕风险管理权限角色。 此配置是快速开始使用 "内幕风险管理" 的最简单方法，非常适合于不需要为单独的用户组定义单独权限的组织。|
| **内幕风险管理管理员** | 使用此角色组最初配置内幕风险管理和更高版本，以便将内幕风险管理员与定义的组分离。  此角色组中的用户可以创建、读取、更新和删除内幕风险管理策略、全局设置和角色组分配。 |
| **内幕风险管理分析师** | 使用此组可将权限分配给将充当内幕风险案例分析人员的用户。 此角色组中的用户可以访问所有内幕风险管理警报、案例和通知模板。 他们无法访问内幕风险内容浏览器。 |
| **内幕风险管理调查人员** | 使用此组可将权限分配给将充当内部人员风险数据调查人员的用户。 在所有情况下，此角色组中的用户都可以访问所有内幕风险管理警报、案例、通知模板和内容资源管理器。 |

## <a name="understand-requirements-and-dependencies"></a>了解要求和依赖项

根据您计划实施内幕风险管理策略的方式，您需要拥有适当的 Microsoft 365 许可订阅，并了解并规划一些解决方案先决条件。

**许可：** 内幕风险管理可作为 Microsoft 365 许可订阅的广泛选择的一部分提供。 有关详细信息，请参阅[内幕风险管理](insider-risk-management-configure.md#before-you-begin)文章入门。

如果您没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试使用内幕风险管理，则可以[将 microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)到现有订阅或注册 Microsoft 365 企业版 e5 的[试用版](https://www.microsoft.com/microsoft-365/enterprise)。

**策略模板要求：** 根据策略模板，可能需要在组织中配置内幕风险管理之前了解和规划这些要求：

- 使用 "终止**员工数据失窃**" 模板时，您必须配置 MICROSOFT 365 HR 连接器以定期为组织中的员工导入辞职和终止日期信息。 有关为您的组织配置 Microsoft 365 HR 连接器的分步指南，请参阅[Import data WITH HR Connector](import-hr-data.md)主题。
- 使用**数据泄漏**模板时，必须配置至少一个数据丢失防护（DLP）策略以定义组织中的敏感信息，并为高严重性的 DLP 策略警报接收内幕风险警报。 有关为您的组织配置 DLP 策略的分步指南，请参阅[创建、测试和调整 dlp 策略](create-test-tune-dlp-policy.md)主题。

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>在生产环境中与一小组用户进行测试

在生产环境中广泛启用解决方案之前，您可以考虑在组织中进行必要的符合性、隐私和法律审查的情况下，使用一小组生产用户测试策略。 在测试环境中评估内幕风险管理将需要生成模拟用户操作和其他信号，以创建用于会审和处理的案例警报。 通常情况下，这对于大多数组织来说并不可行，因此在生产环境中使用一小组用户测试内幕风险管理通常是首选的。

在此测试过程中，将 anonymization 功能保留在策略设置中，以便在 "内幕风险管理" 控制台中 pseudonymize 用户显示名称，以维护工具中的隐私。 这有助于保护具有策略匹配的用户的隐私，并有助于促进 objectivity 在数据调查和分析审查中对内幕风险警报进行的调查。

如果配置 "内幕风险管理策略" 后未立即看到任何警报，这可能意味着尚未满足最低风险阈值。 检查策略是否已被触发并按预期工作的良好方法是查看用户是否在 "**用户**" 页上的策略范围。

## <a name="resources-for-stakeholders"></a>利益干系人的资源

与您的组织中包含在管理和修正工作流中的利益干系人共享内幕风险管理文档：

- [创建和管理内部风险策略](insider-risk-management-policies.md)
- [调查内部风险警报](insider-risk-management-alerts.md)
- [对内部风险案例采取措施](insider-risk-management-cases.md)
- [使用内幕风险内容浏览器查看事例数据](insider-risk-management-content-explorer.md)
- [创建内部风险通知模板](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>准备好开始了吗？

准备好为你的组织配置内幕风险管理吗？ 请参阅 "[内幕风险管理入门](insider-risk-management-configure.md)"，配置先决条件、创建策略并开始接收通知。
