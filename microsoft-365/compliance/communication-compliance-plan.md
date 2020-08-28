---
title: 通信合规性规划
description: 了解有关在组织中使用通信合规性的规划。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 5fde3c6d5fd14bd0e4d108030ffaa8e5aeb5ed5c
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289317"
---
# <a name="plan-for-communication-compliance"></a>通信合规性规划

在组织中开始使用 [通信合规性](communication-compliance.md) 之前，您的信息技术和合规性管理团队应检查重要的规划活动和注意事项。 在以下方面全面了解和规划部署可帮助确保实现和使用通信合规性功能，并与解决方案的最佳做法保持一致。

## <a name="work-with-stakeholders-in-your-organization"></a>与组织中的利益干系人合作

确定组织中相应的利益干系人进行协作，以针对通信合规性警报采取措施。 一些建议的利益干系人（包括在初始规划和端到端 [通信合规性工作流](communication-compliance.md#workflow) 中）是组织中以下区域的人员：

- 信息技术
- 合规性
- 隐私
- 安全性
- 人力资源人员
- 法律

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>规划调查和修正工作流

选择 "专用利益干系人" 以在 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)中的定期节奏上监视和查看警报和事例。 请确保了解如何将用户和利益干系人分配给组织中不同的通信合规性角色组。

根据您想要管理通信策略和通知的方式，您需要为管理员、审阅者和调查人员将用户分配给一个或多个角色组。 您可以选择将用户分配给特定角色组，以管理不同的通信合规性功能集。 或者，您可能决定将所有通信合规性用户分配给通信合规性角色组。 使用单个角色组或多个组以最大限度地满足合规性管理要求。

在配置通信合规性时计划从这些角色组选项中进行选择：

|**角色**|**角色权限**|
|:-----|:-----|
| **通信合规性** | 使用此角色组管理单个组中的组织的通信合规性。 通过添加指定管理员、分析师、调查人员和查看者的所有用户帐户，您可以在单个组中配置通信合规性权限。 此角色组包含所有通信合规性权限角色。 此配置是快速开始使用通信合规性的最简单方法，非常适合不需要为单独的用户组定义单独权限的组织。 |
| **通信合规性管理员** | 使用此角色组最初配置通信合规性和更高版本，以将通信合规性管理员与定义的组隔离。 分配到此角色组的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。 分配到此角色组的用户无法查看邮件通知。 |
| **通信合规性分析师** | 使用此组可将权限分配给将充当通信合规性分析员的用户。 分配到此角色组的用户可以查看将其分配为审阅者的策略、查看邮件元数据 (不是邮件内容) 、升级到其他审阅者或向用户发送通知。 分析师无法解决待处理的警报。 |
| **通信合规调查人员** | 使用此组将权限分配给将充当通信合规性调查人员的用户。 分配到此角色组的用户可以查看邮件元数据和内容、升级到其他审阅者、升级到高级电子数据展示事例、向用户发送通知以及解决警报。 |
| **通信合规性查看器** | 使用此组可为将管理通信报告的用户分配权限。 分配到此角色组的用户可以访问通信合规性主页上的所有报告小部件，并且可以查看所有通信合规性报告。 |

## <a name="plan-for-policies"></a>规划策略

使用 [预定义](communication-compliance-feature-reference.md#policy-templates) 的攻击性语言模板、敏感信息和法规遵从性，创建通信合规性策略是快速且轻松的。 自定义通信合规性策略允许您灵活地检测和调查特定于您的组织和要求的问题。

在规划通信合规性策略时，请考虑以下方面：

- 考虑将组织中的所有用户添加为您的通信合规性策略的范围内。 在某些情况下，将特定用户标识为范围内的各个策略是有用的，但是大多数组织应包括针对骚扰或歧视检测而优化的通信合规性策略中的所有用户。
- 若要简化设置，请考虑为需要查看其通信的用户创建组。 如果使用的是组;您可能需要多个。 例如，如果要扫描两个不同的人员组之间的通信，或者要指定未受监督的组。
- 配置要在100% 查看的通信百分比，以确保策略能够捕获组织中的所有问题的相关问题。
- 您可以扫描 [第三方源](communication-compliance-feature-reference.md#supported-communication-types) 的通信，以获取导入到 Microsoft 365 组织中的邮箱的数据。 若要在这些平台中包括通信审查，需要先将连接器配置为这些服务，然后才能通过通信策略监视邮件会议策略条件。
- 在自定义通信合规性策略中，策略可以支持非英语的监视语言。 使用您选择的语言构建冒犯性词的 [自定义关键字词典](communication-compliance-feature-reference.md#custom-keyword-dictionaries) ，或使用 Microsoft 365 中的 [trainable 分类](classifier-getting-started-with.md) 程序构建您自己的机器学习模型。
- 所有组织都具有不同的通信标准和策略需求。 使用通信合规性 [策略条件](communication-compliance-feature-reference.md#conditional-settings) 监视特定关键字，或使用 [自定义敏感信息类型](create-a-custom-sensitive-information-type.md)监视特定类型的信息。

## <a name="ready-to-get-started"></a>准备好开始了吗？

若要为 Microsoft 365 组织配置通信合规性，请参阅 [configure communication 合规性 For microsoft 365](communication-compliance-configure.md) 或查看 [Contoso 的个案研究](communication-compliance-case-study.md) ，以及如何快速将通信合规性策略配置为在 Microsoft 团队、Exchange Online 和 Yammer 通信中监视是否有攻击性的语言。
