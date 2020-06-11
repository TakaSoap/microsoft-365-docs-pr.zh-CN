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
- M365solutions
ms.custom: ''
description: 使用 Microsoft 365 保留标签和策略来管理 Microsoft 365 环境中的个人数据。
ms.openlocfilehash: 4c65eafa167d7224c4022d5634ce089952fada19
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695157"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>管理受数据隐私法规约束的信息

可以在您的环境中使用信息控制控件，以帮助满足数据隐私合规性需求，其中包括特定于常规数据保护法规（GDPR）、HIPAA-高科技（美国卫生保健隐私法案）、加利福尼亚州消费者保护法（CCPA）和巴西数据保护法案（LGPD）的数字。 

这些控件主要分为以下几个解决方案领域：

- 保留策略
- 保留标签
- 记录管理

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>影响信息治理控制的数据隐私条例

下面的示例列出了可能与信息治理控制相关的数据隐私法规：

- GDPR 文章（13）（2）（a）
- GDPR 文章（5）（1）（f）
- HIPAA-高科技（45 CFR 164.312 （c）（2））
- HIPAA-高科技（45 CFR 164.316 （b）（1）（i））
- HIPAA-高科技（45 CFR 164.316 （b）（1）（ii））
- LGPD 文章46

有关这些管理法规的详细信息，请参阅[评估数据隐私风险和确定敏感信息文章](information-protection-deploy-assess.md)。

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

若要开始，请参阅在 Microsoft 365 中[管理信息](../compliance/manage-information-governance.md)管理和[数据保留、删除和销毁](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)。

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>为容器、电子邮件和内容开发数据保留计划

请注意以下几点：

- 若要为定义的信息类型建立数据保留计划，应考虑实施任何保留或删除方案的先决条件。

- 根据大多数组织认为重要的信息类型的数量以及与他们一起提供的相应大型记录保留计划，实现数据保留和记录管理策略需要进行规划。 

- 建立此类型的有效数据管理策略的关键是重点关注需要更正式管理的最高优先级的业务功能和信息类型。 例如法律合同、财务报表和法规遵从性文档。 尽量避免为每种信息类型提供单独的保留计划。 请尽量充分利用常规类别，例如，将常规业务内容的保留计划安排为7年。

- 一旦环境中的个人信息类型更清楚，请为此类型的内容建立保留和删除计划，并调整您的信息体系结构以使此类信息的管理更容易。 例如，使用受控制的访问隔离单独的网站、库或文件夹中的个人信息。

### <a name="retention-policies"></a>保留策略

为自动应用的网站中的内容创建和部署[保留策略](../compliance/retention-policies.md)。

若要获取包含或预期包含个人数据的网站的数据隐私，请指定保留或删除规则以满足组织标准。

### <a name="retention-labels"></a>保留标签

创建和部署内容和电子邮件的[保留标签](../compliance/labels.md)。

若要获取包含或预期包含个人数据的网站、库、文件夹和电子邮件的数据隐私，请指定自动保留或删除规则以满足组织标准。

### <a name="records-management"></a>记录管理

创建和部署基于记录保留计划和文件计划的记录管理的保留标签。

对于数据隐私，法律部门收到的数据主体请求（Dsr）声明为记录并无限期存储，以遵守法规活动保留规范。

有关详细信息，请参阅以下资源： 

- [记录管理](../compliance/records-management.md)
- [文件计划管理器](../compliance/file-plan-manager.md)
- [基于事件的记录管理保留](../compliance/automate-event-driven-retention.md)
- [内容的处置](../compliance/disposition-reviews.md)
