---
title: 规划通信合规性
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
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045845"
---
# <a name="plan-for-communication-compliance"></a>规划通信合规性

在组织中开始使用[通信合规性](communication-compliance.md)之前，您的信息技术和合规性管理团队应检查重要的规划活动和注意事项。 在以下方面全面了解和规划部署可帮助确保实现和使用通信合规性功能，并与解决方案的最佳做法保持一致。

## <a name="work-with-stakeholders-in-your-organization"></a>与组织中的利益干系人合作

确定组织中相应的利益干系人进行协作，以针对通信合规性警报采取措施。 一些建议的利益干系人（包括在初始规划和端到端[通信合规性工作流](communication-compliance.md#workflow)中）是组织中以下区域的人员：

- 信息技术
- 合规性
- 隐私
- 安全性
- 人力资源人员
- 法律

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>规划调查和修正工作流

选择 "专用审阅者" 以在[Microsoft 365 合规性中心](https://compliance.microsoft.com/)中的定期节奏上监视和查看警报。 请记住，您需要[创建新的角色组](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)，以启用具有**监管审核管理员**、**案例管理**、**合规性管理员**和**审阅**角色的审阅者的权限，以使用策略匹配来调查和修正邮件。

## <a name="plan-for-policies"></a>规划策略

使用[预定义](communication-compliance-feature-reference.md#policy-templates)的攻击性语言模板、敏感信息和法规遵从性，创建通信合规性策略是快速且轻松的。 自定义通信合规性策略允许您灵活地检测和调查特定于您的组织和要求的问题。

在规划通信合规性策略时，请考虑以下事项：

- 考虑将组织中的所有用户添加为您的通信合规性策略的范围内。 在某些情况下，将特定用户标识为范围内的各个策略是有用的，但是大多数组织应包括针对骚扰或歧视检测而优化的通信合规性策略中的所有用户。
- 若要简化设置，请考虑为需要查看其通信的用户创建组。 如果使用的是组;您可能需要多个。 例如，如果要扫描两个不同的人员组之间的通信，或者要指定未受监督的组。
- 配置要在100% 查看的通信百分比，以确保策略能够捕获组织中的所有问题的相关问题。
- 您可以扫描[第三方源](communication-compliance-feature-reference.md#supported-communication-types)的通信，以获取导入到 Microsoft 365 组织中的邮箱的数据。 若要在这些平台中包括通信审查，需要先将连接器配置为这些服务，然后才能通过通信策略监视邮件会议策略条件。
- 在自定义通信合规性策略中，策略可以支持非英语的监视语言。 使用您选择的语言构建冒犯性词的[自定义关键字词典](communication-compliance-feature-reference.md#custom-keyword-dictionaries)，或使用 Microsoft 365 中的[trainable 分类](classifier-getting-started-with.md)程序构建您自己的机器学习模型。
- 所有组织都具有不同的通信标准和策略需求。 使用通信合规性[策略条件](communication-compliance-feature-reference.md#conditional-settings)监视特定关键字，或使用[自定义敏感信息类型](create-a-custom-sensitive-information-type.md)监视特定类型的信息。

## <a name="ready-to-get-started"></a>准备好开始了吗？

若要为 Microsoft 365 组织配置通信合规性，请参阅[configure communication 合规性 For microsoft 365](communication-compliance-configure.md)或查看[Contoso 的个案研究](communication-compliance-case-study.md)，以及如何快速将通信合规性策略配置为在 Microsoft 团队、Exchange Online 和 Yammer 通信中监视是否有攻击性的语言。
