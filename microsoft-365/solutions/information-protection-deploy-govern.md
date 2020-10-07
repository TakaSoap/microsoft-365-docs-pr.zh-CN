---
title: 管理受数据隐私法规约束的信息
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
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 365 保留标签和策略来管理 Microsoft 365 环境中的个人数据。
ms.openlocfilehash: c2a933e556213ae4b78db9dc5f903885df969b27
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377041"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>管理受数据隐私法规约束的信息

可以在您的环境中使用信息控制控件，以帮助满足数据隐私合规性需求，包括特定于常规 Data Protection 规章的数字 (GDPR) 、HIPAA-高科技 (美国卫生保健隐私法案) 、加利福尼亚消费者保护法 (CCPA) 和巴西 Data Protection 法案 (LGPD) 。 

这些控件主要分为以下几个解决方案领域：

- 保留策略
- 保留标签
- 记录管理

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>影响信息治理控制的数据隐私条例

下面的示例列出了可能与信息治理控制相关的数据隐私法规：

- GDPR 文章 (13) # B2 2) # B4 a) 
- GDPR 文章 (5) # B2 1) # B4 f) 
- HIPAA-高科技 (45 CFR 164.312 (c) # B3 2) # A5
- HIPAA-高科技 (45 CFR 164.316 (b) # B3 1) # B5 i) # A7
- HIPAA-高科技 (45 CFR 164.316 (b) # B3 1) # B5 ii) # A7
- LGPD 文章46

有关这些管理法规的详细信息，请参阅 [评估数据隐私风险和确定敏感信息文章](information-protection-deploy-assess.md)。

对于信息治理，数据隐私规章通常会调用以下内容：

- 对于存储在 Microsoft 365 中的个人数据，应采用一种技术方案进行保留和删除。
- 如果要存储个人数据，请通知主题将存储数据的时间长度，这是前端 web 系统上现在的标准做法。
- 应保护个人数据，防止使用可验证的方法意外处理、丢失或更改。
- 应记录对个人数据执行的任何操作，并且文档应在指定时间段内保留。

由于数据隐私法规在数据保留和删除方面不是非常特定的，因此需要考虑其他因素，这可能规定了 Microsoft 365 订阅中存储的个人信息的信息治理准则。 下面是一些示例：

- 在5年的不活动后，需要删除或 anonymization 帐户数据的情况下，在该时间点之后对消费者帐户进行老化，要求在存储与通知和其他自动化相关的数据和工作流的系统之间进行业务流程。
- 配置用于保留与 GDPR 相关的策略和过程的规则，这些规则和过程已被取代（与组织的策略和程序的保留计划一致）的三年。
- 维护单独的订阅，以便通过其支持组织与使用者进行通信。 两周后所有的电子邮件通信都将保留并删除，以减少系统中的任何隐私债务堆积。

要回答的主要问题是： 

- 出于有效的业务原因，包含个人数据的信息需要多长时间才能保持，以避免 "永远不应保留" 做法？ 这必须与业务连续性的保留需求平衡。

无论个人信息保留或删除个人信息的法律和商业原因如何，Microsoft 都提供了多种在 Microsoft 365 中实施您的数据管理方案的功能。

## <a name="managing-information-governance-in-microsoft-365"></a>在 Microsoft 365 中管理信息治理

若要开始，请参阅在 Microsoft 365 中 [管理信息](../compliance/manage-information-governance.md) 管理和 [数据保留、删除和销毁](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)。

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>为容器、电子邮件和内容开发数据保留计划

请注意以下几点：

- 若要为定义的信息类型建立数据保留计划，应考虑实施任何保留或删除方案的先决条件。

- 根据大多数组织认为重要的信息类型的数量以及与他们一起提供的相应大型记录保留计划，实现数据保留和记录管理策略需要进行规划。 

- 建立此类型的有效数据管理策略的关键是重点关注需要更正式管理的最高优先级的业务功能和信息类型。 例如法律合同、财务报表和法规遵从性文档。 尽量避免为每种信息类型提供单独的保留计划。 请尽量充分利用常规类别，例如，将常规业务内容的保留计划安排为7年。

- 一旦环境中的个人信息类型更清楚，请为此类型的内容建立保留和删除计划，并调整您的信息体系结构以使此类信息的管理更容易。 例如，使用受控制的访问隔离单独的网站、库或文件夹中的个人信息。

### <a name="retention-policies-and-retention-labels"></a>保留策略和保留标签

使用 [保留策略和保留标签](../compliance/retention.md) 在 Microsoft 365 中保留或删除包含或预期包含个人数据的内容。

### <a name="records-management"></a>记录管理

使用保留标签声明内容 a 记录，以在 Microsoft 365 中为数据实现 [记录管理解决方案](../compliance/records-management.md) 。

对于数据隐私，法律部门收到 (Dsr) 的数据主体请求被声明为记录，可以无限期存储或处理证据，以符合法规活动的保留规范。

