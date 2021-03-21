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
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928420"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>监视和响应组织中数据隐私事件

Microsoft 365 功能可用于帮助你在操作相关功能时监视、调查和响应贵组织的数据隐私事件。 为每项流程、过程和其他文档提供过程、过程和其他文档可能也很重要，以证明对监管机构的遵从性。

具体包括： 

- 审核和警报策略
- 数据主体请求 (包括内容搜索和电子数据展示) 
- 其他调查工具和报告

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>影响监视和响应工具使用的数据隐私法规

下面是可能与信息治理控制相关的数据隐私法规示例列表：

- LGPD 文章 46
- LGPD 文章 48
- GDPR 文章 (5)  (1)  (f) 
- GDPR 文章 (15)  (1)  (e) 
- HIPAA-HITECH (45 C.F.R. 164.308 ()  (1)  (ii)  (D) ) 
- HIPAA-HITECH (45 C.F.R. 164.308 (6)  (6)  (ii) 
- HIPAA-HITECH (45 C.F.R. 164.312 (b) ) 
- CCPA (1798.105 (c) ) 

有关详细信息，请参阅评估 [数据隐私风险并识别敏感信息](information-protection-deploy-assess.md)。

数据隐私法规通常要求对以下内容进行监视和响应：

- 与个人数据的存储、共享和处理相关的活动的审核、警报和报告
- 响应 DSR 数据主体请求 (DSR) 在某些情况下，执行调查和其他管理措施以遵守此类请求。

您的组织可能还希望出于其他目的（如其他合规性需求或出于业务原因）执行监视和响应活动。 应制定数据隐私的监视和响应方案，作为整体监视和响应规划、实施和管理的一部分。

为了帮助你开始使用 Microsoft 365 中针对数据隐私法规的监视和响应方案，本文列出了 Microsoft 365 中用于回答如下问题的有用功能： 

- 对于不同的数据类型和源，提供了哪类日常监视、调查和报告技术？
- 需要哪些机制来处理 DSR 请求 (DSR) 任何修正操作（如匿名化、修订和删除）。

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>安全与合规中心中的审核和警报策略

请参阅以下文章，了解设置审核、高级审核和警报策略：

- [统一审核](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [邮箱审核](../compliance/enable-mailbox-auditing.md)
- [高级审核](../compliance/advanced-audit.md)
- [警报策略](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>针对 GDPR 和 CCPA 的数据主体请求

有关在 Microsoft 365 中响应 DSR 的信息，请参阅 GDPR 的数据主体请求和[CCPA。](/compliance/regulatory/gdpr-dsr-Office365)

## <a name="manage-deleted-users-in-microsoft-stream"></a>在 Microsoft Stream 中管理已删除的用户

对于 Microsoft Stream，从 Azure Active Directory (Azure AD) 中删除用户时，如果用户姓名与该时间点之前发布 Stream 视频相关联，则他们的电子邮件地址仍与该视频相关联。 请参阅 [从 Microsoft Stream 管理已删除的用户](/stream/managing-deleted-users) 以将其删除。

## <a name="insider-risk-management-as-an-investigative-tool"></a>内部风险管理作为调查工具

[Microsoft 365](../compliance/insider-risk-management.md) 中的内部风险管理是 Microsoft 合规性管理中心的一项功能，可帮助你通过检测、调查和操作组织中存在风险的活动来最大程度地降低内部风险。