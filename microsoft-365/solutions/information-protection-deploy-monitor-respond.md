---
title: 监视和响应组织中的数据隐私事件
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 使用审核和通知策略和数据主体请求来监视和响应个人数据事件。
ms.openlocfilehash: 5760bb40eb26e2ff0636ea9604cc7c45b7d0ca63
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695063"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>监视和响应组织中的数据隐私事件

Microsoft 365 功能可帮助您在您的组织中监视、调查数据隐私事件并在 operationalize 相关功能时对其做出响应。 对于上述每种情况，拥有过程、过程和其他文档可能也非常重要，这也是证明合规性的合规性。

具体包括： 

- 审核和警报策略
- 数据主体请求（包括内容搜索和电子数据展示）
- 其他调查工具和报告

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>影响监控和响应工具的使用的数据隐私法规

下面的示例列出了可能与信息治理控制相关的数据隐私法规：

- LGPD 文章46
- LGPD 文章48
- GDPR 文章（5）（1）（f）
- GDPR 文章（15）（1）（e）
- HIPAA-高科技（45 C.F.R。 164.308 （a）（1）（ii）（D））
- HIPAA-高科技（45 C.F.R。 164.308 （a）（6）（ii）
- HIPAA-高科技（45 C.F.R。 164.312 （b））
- CCPA （1798.105 （c））

有关详细信息，请参阅[评估数据隐私风险和标识敏感信息](information-protection-deploy-assess.md)。

通常情况下，数据隐私管理法规要求进行监视和响应：

- 有关与存储、共享和处理个人数据相关的活动的审核、警报和报告
- 能够响应数据主体请求（DSR），在某些情况下，可以执行调查和其他管理措施以遵守此类请求。

您的组织可能还希望出于其他目的（如其他合规性需求或业务原因）执行监视和响应活动。 在整体监控和响应规划、实施和管理的过程中，建立用于数据隐私的监控和响应方案。

为了帮助您开始使用 Microsoft 365 中的监控和响应方案来获取数据隐私法规，本文列出了 Microsoft 365 中的有用功能，以回答以下问题： 

- 对于不同的数据类型和源，可使用哪种日常监控、调查和报告技术？
- 处理数据主体请求（Dsr）和任何补救措施（如 anonymization、密文和删除）将需要哪些机制。

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>安全与合规中心中的审核和警报策略

有关设置审核、高级审核和通知策略的相关文章，请参阅以下文章：

- [统一审核](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [邮箱审核](../compliance/enable-mailbox-auditing.md)
- [高级审核](../compliance/advanced-audit.md)
- [警报策略](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 和 CCPA 的数据主体请求

有关[GDPR 和 CCPA 的数据主体请求](../compliance/gdpr-dsr-office365.md)，请参阅有关在 Microsoft 365 中响应 DSR 的信息。

## <a name="manage-deleted-users-in-microsoft-stream"></a>在 Microsoft Stream 中管理已删除的用户

对于 Microsoft Stream，当从 Azure Active Directory （Azure AD）中删除用户时，如果他们的名称与之前发布的流视频相关联，则他们的电子邮件地址仍将与视频相关联。 请参阅[从 Microsoft Stream 管理已删除的用户](https://docs.microsoft.com/stream/managing-deleted-users)以将其删除。

## <a name="additional-investigative-tools"></a>其他调查工具

以下是在组织中监视、调查和修正与数据隐私相关的事件时可能有用的两个附加工具：

- [内幕风险管理在 microsoft 365 中](../compliance/insider-risk-management.md)，Microsoft 合规性管理中心的一项功能，通过使您能够检测、调查和对组织中的危险活动采取措施来帮助最大限度地减少内部风险。
- Microsoft [365 中的数据调查](../compliance/overview-data-investigations.md)是 Microsoft 合规性管理中心的一项功能，用于在 microsoft 365 中搜索敏感、恶意或放错位置的数据，然后调查执行相应操作以修正事件所发生的情况。
