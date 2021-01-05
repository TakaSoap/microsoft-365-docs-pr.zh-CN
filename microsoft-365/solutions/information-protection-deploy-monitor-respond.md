---
title: 监视和响应组织中数据隐私事件
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用审核和警报策略和数据主体请求来监视和响应个人数据事件。
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749583"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>监视和响应组织中数据隐私事件

Microsoft 365 功能可用于帮助你在操作相关功能时监视、调查和响应组织中数据隐私事件。 拥有每个流程、过程和其他文档对证明监管机构的合规性也很重要。

具体包括： 

- 审核和警报策略
- 数据主体请求 (包括内容搜索和电子数据展示) 
- 其他调查工具和报告

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>影响监视和响应工具使用的数据隐私法规

下面是可能与信息治理控制相关的数据隐私法规的示例列表：

- LGPD 文章 46
- LGPD 文章 48
- GDPR 文章 (5)  (1)  (f) 
- GDPR (15)  (1)  (e) 
- HIPAA-HITECH (45 C.F.R. 164.308 ()  (1)  (ii)  (D) ) 
- HIPAA-HITECH (45 C.F.R. 164.308 ()  (6)  (ii) 
- HIPAA-HITECH (45 C.F.R. 164.312 (b) ) 
- CCPA (1798.105 (c) ) 

有关详细信息，请参阅"[评估数据隐私风险并识别敏感信息"。](information-protection-deploy-assess.md)

数据隐私法规通常要求进行以下监视和响应：

- 审核、警报和报告与个人数据的存储、共享和处理相关的活动
- 能够响应 DSR (数据主体) 在某些情况下，执行调查和其他管理措施以遵守此类请求。

您的组织可能还希望出于其他目的（如其他合规性需求或出于业务原因）执行监视和响应活动。 为数据隐私建立监控和响应方案应作为整体监视和响应规划、实施和管理的一部分完成。

为了帮助你开始使用 Microsoft 365 中针对数据隐私法规的监视和响应方案，本文列出了 Microsoft 365 中用于回答以下问题的有用功能： 

- 对于不同的数据类型和来源，可以使用哪类日常监视、调查和报告技术？
- 需要哪些机制来处理 DSR 请求 (DSR) 任何修正操作（如匿名化、修订和删除）。

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>安全与合规中心中的审核和警报策略

请参阅以下文章以设置审核、高级审核和警报策略：

- [统一审核](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [邮箱审核](../compliance/enable-mailbox-auditing.md)
- [高级审核](../compliance/advanced-audit.md)
- [警报策略](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>针对 GDPR 和 CCPA 的数据主体请求

有关在 Microsoft 365 中响应 DSR 的信息，请参阅 GDPR 和 [CCPA](../compliance/gdpr-dsr-office365.md) 的数据主体请求。

## <a name="manage-deleted-users-in-microsoft-stream"></a>在 Microsoft Stream 中管理已删除的用户

对于 Microsoft Stream，从 Azure Active Directory (Azure AD) 中删除用户时，如果用户姓名与之前发布 Stream 视频相关联，则其电子邮件地址仍与该视频相关联。 请参阅 ["管理 Microsoft Stream 中删除](https://docs.microsoft.com/stream/managing-deleted-users) 的已删除用户"。

## <a name="insider-risk-management-as-an-investigative-tool"></a>内部风险管理作为调查工具

[Microsoft 365](../compliance/insider-risk-management.md) 中的内部风险管理是 Microsoft 合规性管理中心的一项功能，通过让你能够检测、调查和对组织中存在风险的活动采取行动，可帮助你最大程度地降低内部风险。
