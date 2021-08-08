---
title: 管理受数据隐私条例约束的信息
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
description: 使用Microsoft 365保留标签和策略来管理你的Microsoft 365中的个人数据。
ms.openlocfilehash: 06d3c19918d7e2963bffbb0f663971bbbbb209891f62ee9c83ebcc59b74e16d1
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53843871"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>管理受数据隐私条例约束的信息

可以在环境中使用信息治理控制来帮助满足数据隐私合规性需求，包括特定于一般数据保护条例 (GDPR) 、HIPAA-HITECH (美国医疗保健隐私法案) 、加州消费者保护法案 (CCPA) 和巴西数据保护法案 (LGPD) 等。 

这些控件主要属于以下解决方案区域：

- 保留策略
- 保留标签
- 记录管理

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>影响信息治理控制的数据隐私法规

下面是可能与信息治理控制相关的数据隐私法规示例列表：

- GDPR 文章 (2)  (2)  (13) 
- GDPR 文章 (5)  (1)  (f) 
- HIPAA-HITECH (45 CFR 164.312 (c)  (2) ) 
- HIPAA-HITECH (45 CFR 164.316 (b)  (1)  (i) ) 
- HIPAA-HITECH (45 CFR 164.316 (b)  (1)  (ii) ) 
- LGPD 文章 46

有关这些法规详细信息，请参阅评估数据 [隐私风险并识别敏感信息文章](information-protection-deploy-assess.md)。

对于信息治理，数据隐私法规通常要求：

- 您应该采用用于保留和删除存储在数据存储区中的个人数据的技术Microsoft 365。
- 如果要存储个人数据，请告知主体数据将存储多久，这是现在前端 Web 系统上的标准做法。
- 应该防止个人数据使用可验证的方法意外处理、丢失或更改。
- 对个人数据执行的任何操作都应进行记录，并且该文档应保留指定的期限。

由于数据隐私法规在数据保留和删除方面并不十分具体，因此需要考虑其他因素，这些因素可能规定存储在你的 Microsoft 365 订阅中的个人信息的治理准则。 下面是一些示例：

- 在 5 年不活动后对使用者帐户进行注销，并且要求在此后删除或匿名处理帐户数据，这要求系统在存储数据与与通知和其他自动化相关的工作流之间协调工作。
- 配置与 GDPR 相关的策略和过程在被取代后保留三年的规则，这符合组织的策略和程序的保留计划。
- 维护单独的订阅，以通过其支持组织与消费者进行通信。 所有电子邮件通信在两周后保留和删除，以减少系统内的任何隐私债务增加。

要回答的一个关键问题是： 

- 出于有效的业务原因，包含个人数据的信息需要保留多久，以避免"永久保留"做法？ 这必须与业务连续性的保留需求相平衡。

无论保留或删除个人信息的法律和业务原因如何，Microsoft 都会提供许多功能，以在 Microsoft 365 中实施数据管理方案。

## <a name="managing-information-governance-in-microsoft-365"></a>管理信息治理Microsoft 365

首先，请参阅管理[信息治理](../compliance/manage-information-governance.md)和数据保留、删除和销毁[Microsoft 365。](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>制定容器、电子邮件和内容的数据保留计划

请注意以下几点：

- 为定义的信息类型建立数据保留计划应被视为实施任何保留或删除方案的先决条件。

- 鉴于大多数组织认为重要的信息类型以及相应的大型记录保留计划，实施数据保留和记录管理策略需要进行规划。 

- 建立此类型的有效数据管理策略的关键是重点关注需要更正式的管理的最高优先级业务功能和信息类型。 示例包括法律合同、财务报表和监管合规性文档。 尝试避免对每种信息类型使用单独的保留计划。 尽量利用常规类别，例如，常规业务内容的保留计划为 7 年。

- 在更好地了解环境中的个人信息类型后，为此类内容制定保留和删除计划，并调整信息体系结构，以便更轻松地管理此类信息。 例如，将个人信息隔离在具有受控访问权限的单独网站、库或文件夹中。

### <a name="retention-policies-and-retention-labels"></a>保留策略和保留标签

使用[保留策略和保留标签](../compliance/retention.md)保留或删除Microsoft 365或预期包含个人数据的内容。

### <a name="records-management"></a>记录管理

使用声明内容记录的保留标签，为记录中数据[](../compliance/records-management.md)实现Microsoft 365。

对于数据隐私， (部门收到的) DSR 的数据主体请求将被声明为记录，并可以无限期存储或经过证明处理，以遵守法规活动保留规范。