---
title: 通信合规性规划
description: 了解如何规划在组织中使用通信合规性。
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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: b26d983bf73a968a06566f18c20d4df24b7763a8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179315"
---
# <a name="plan-for-communication-compliance"></a>通信合规性规划

在开始使用 [组织中通信](communication-compliance.md) 合规性之前，信息技术和合规性管理团队应查看重要的规划活动和注意事项。 全面了解和规划以下方面的部署有助于确保实现和使用通信合规性功能顺利进行，并且符合解决方案的最佳实践。

## <a name="work-with-stakeholders-in-your-organization"></a>与组织中的利益干系人合作

确定组织中适当的利益干系人，以便协作以对通信合规性警报采取措施。 一些建议的利益干系人是组织以下领域的人员，他们需要考虑包括在初始[](communication-compliance.md#workflow)规划和端到端通信合规性工作流中：

- 信息技术
- 合规性
- 隐私
- 安全性
- 人力资源
- 法律

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>规划调查和修正工作流

选择专门的利益干系人，以定期在"报告"中监视和[查看Microsoft 365 合规中心。](https://compliance.microsoft.com/) 请务必了解如何将用户和利益干系人分配到组织中不同的通信合规性角色组。

根据希望管理通信策略和警报方式，需要为管理员、审阅者和调查人员将用户分配到一个或多个角色组。 您可以选择将用户分配给特定角色组，以管理不同的通信合规性功能集。 或者，您可以决定将所有通信合规性用户分配给 Communication Compliance 角色组。 使用单个角色组或多个组以最适合合规性管理要求。

在配置通信合规性时，请计划从这些角色组选项中进行选择：

|**角色**|**角色权限**|
|:-----|:-----|
| **通信合规性** | 使用此角色组在单个组中管理组织的通信合规性。 通过添加指定管理员、分析者、调查者和查看者的所有用户账户，可以在单个组中配置通信合规性权限。 此角色组包含所有通信合规性权限角色。 这一配置是通信合规性快速入门的最简单方式，非常适合不需要为单独用户组定义单独权限的组织。 |
| **通信合规性管理员** | 使用此角色组进行通信合规性初始配置，后期可将通信合规性管理员隔离到已定义组中。 分配到此角色组的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。 分配到此角色组的用户无法查看消息警报。 |
| **通信合规性分析者** | 使用此组向执行通信合规性分析者操作的用户分配权限。 分配到此角色组的用户可以查看分配其为审阅者的策略，查看消息元数据（而不是消息内容）、升级到其他审阅者，或向用户发送通知。 分析者不能解决挂起的警报。 |
| **通信合规性调查者** | 使用此组向执行通信合规性调查者操作的用户分配权限。 分配到此角色组的用户可以查看消息元数据和内容、升级到其他审阅者、升级到高级 eDiscovery 案例、向用户发送通知、以及解决警报。 |
| **通信合规性查看者** | 使用此组向管理通信报告的用户分配权限。 分配到此角色组的用户可以访问通信合规性主页上的所有报告小组件，并且可以查看所有通信合规性报告。 |

## <a name="plan-for-policies"></a>规划策略

使用针对冒犯性语言、敏感信息和法规遵从性的[](communication-compliance-feature-reference.md#policy-templates)预定义模板，可快速轻松地创建通信合规性策略。 通过自定义通信合规性策略，可以灵活地检测和调查特定于您的组织和要求的问题。

规划通信合规性策略时，请考虑以下方面：

- 请考虑将组织中所有用户添加为通信合规性策略的作用域内用户。 在某些情况下，将特定用户标识为个别策略的作用域内非常有用，但大多数组织应在针对骚扰或非法检测优化的通信合规性策略中包括所有用户。
- 若要简化设置，请考虑为需要审阅其通信的人创建组。 如果你使用的是组;您可能需要几个。 例如，如果想要监管两个不同组人员之间的通信，或者指定一个不受监管的组，这时候就需要创建若干个组。
- 配置 100% 要审阅的通信百分比，以确保策略捕获组织通信中关注的所有问题。
- 您可以扫描来自[第三方源的通信](communication-compliance-feature-reference.md#supported-communication-types)，以搜索导入到组织中邮箱Microsoft 365的数据。 若要查看这些平台中的通信，需要先配置这些服务的连接器，然后通信策略才能监视满足策略条件的邮件。
- 在自定义通信合规性策略中，策略可以支持监视除英语语言外的语言。 使用你[选择的语言](communication-compliance-feature-reference.md#custom-keyword-dictionaries)生成冒犯性字词的自定义关键字词典，或者使用可训练的分类器在 Microsoft 365[](classifier-get-started-with.md)中构建你自己的机器学习Microsoft 365。
- 所有组织都有不同的通信标准和策略需求。 使用通信合规性策略条件监视特定 [关键字，](communication-compliance-feature-reference.md#conditional-settings) 或监视具有自定义敏感信息 [类型的特定类型的信息](create-a-custom-sensitive-information-type.md)。

## <a name="ready-to-get-started"></a>准备好开始了吗？

若要为 Microsoft 365 组织配置通信合规性，请参阅为[Microsoft 365](communication-compliance-configure.md)配置通信合规性或查看[Contoso](communication-compliance-case-study.md)的案例研究，以及他们如何快速配置通信合规性策略以监视 Microsoft Teams、Exchange Online 和 Yammer 通信中的冒犯性语言。
