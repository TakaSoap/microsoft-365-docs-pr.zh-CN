---
title: Microsoft 合规性管理器
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器可帮助组织简化和自动化风险评估，并建议采取建议操作来帮助应对风险。
ms.openlocfilehash: 289d82e8bc5f404589b263a2b6dec499d9e3b7e2
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317663"
---
# <a name="microsoft-compliance-manager"></a>Microsoft 合规性管理器

**本文内容：** 了解什么是合规性管理器，它如何有助于简化合规性和降低风险及其关键组件。

## <a name="what-is-compliance-manager"></a>什么是合规性管理器？

[Microsoft 合规性管理器](https://compliance.microsoft.com/compliancemanager)是 Microsoft 365 合规中心一项功能<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank"></a>，可帮助您更加轻松和方便地管理组织的合规性要求。 合规性管理器可以帮助你完成合规性之旅，从清查数据保护风险到管理实现控制的复杂性、及时了解最新法规和认证、以及向审核员报告。

观看下面的视频，了解合规性管理器如何有助于简化组织管理合规性的情况：
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

合规性管理器通过提供：

- 针对常见行业和区域标准和法规的预建评估，或为满足唯一合规性需求而 (评估取决于许可协议; [了解) ](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) 。

- 工作流功能通过单一工具帮助你有效完成风险评估。

- 有关建议改进操作的详细分步指南，可帮助您遵守与组织最相关的标准和法规。 对于由 Microsoft 管理的操作，你将看到实现详细信息和审核结果。

- 基于风险的合规性分数，通过衡量完成改进操作的进度，帮助你了解合规性状态。

合规性管理器仪表板显示当前的合规性分数，帮助你查看需要关注的问题，并指导你执行关键改进操作。 下面是合规性管理器仪表板外观的示例：

![合规性管理器 - 仪表板。](../media/compliance-manager-dashboard.png "合规性管理器仪表板")

## <a name="understanding-your-compliance-score"></a>了解合规性分数

合规性管理器会奖励你完成为遵守法规、标准或策略而采取的改进措施，并且将这些分数组合到一个总体合规性分数中。 每项操作对分数的影响各不相同，具体取决于所涉及的潜在风险。 合规性分数可帮助确定重点操作优先级，以改善整体合规性状态。

合规性管理器根据数据保护基线提供Microsoft 365分数。 此基线是一组控制措施，其中包括数据保护和一般数据管理的关键法规和标准。

##### <a name="learn-more"></a>了解详细信息

[了解如何计算合规性分数](compliance-score-calculation.md)。

[了解如何使用改进操作](compliance-manager-improvement-actions.md)。

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>关键要素：控制措施、评估、模板、改进操作

合规性管理器使用多个数据元素来帮助管理合规性活动。 使用合规性管理器分配、测试和监视合规性活动时，对关键要素有基本的了解会有所帮助：控制、评估、模板和改进操作。

### <a name="controls"></a>控件

控件是法规、标准或策略的要求。 它定义了如何评估和管理系统配置、组织流程以及负责满足法规、标准或策略的特定要求的人员。

合规性管理器跟踪以下类型的控件：

1. **Microsoft 管理的** 控制措施：Microsoft 负责实现 Microsoft 云服务的控制措施
2. **你的** 控件：有时称为客户管理的控制措施，这些控件是由你的组织实现和管理的控件
3. **共享** 控件：这些是您的组织和 Microsoft 共同负责实现的控制

##### <a name="learn-more"></a>了解详细信息

[监视控件的进度](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)。

[了解合规性管理器如何持续评估控制措施](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)。

### <a name="assessments"></a>评估

评估是按特定法规、标准或策略对控制措施进行分组。 完成评估内的操作可以帮助你满足标准、法规或法律的要求。 例如，您可能有一项评估，其中的所有操作完成后，有助于使 Microsoft 365 设置符合 ISO 27001 要求。

评估包括几个组件：

- **适用范围服务**：适用于评估的特定 Microsoft 服务集
- **Microsoft 管理的** 控制措施：Microsoft 代表你实现 Microsoft 云服务的控制措施
- **你的** 控件：有时称为客户管理的控制措施，这些控件是由你的组织实现和管理的控件
- **共享** 控件：这些是您的组织和 Microsoft 共同负责实现的控制
- **评估分数**：显示你在从由你的组织和 Microsoft 管理的评估内的操作获得可能的总分数方面的进度

创建评估时，需要将其分配给组。 您可以使用对组织最符合逻辑的任何方式配置组。 例如，你可以按审核年份、区域、解决方案、贵组织中团队或其他某种方式对评估进行分组。 创建组后，可以 [筛选合规性管理器](compliance-manager-setup.md#filtering-your-dashboard-view) 仪表板，以便按一个或多个组查看分数。

##### <a name="learn-more"></a>了解详细信息

[在合规性管理器中生成和管理评估](compliance-manager-assessments.md)。

### <a name="templates"></a>模板

合规性管理器提供了模板，可帮助你快速创建评估。 你可以修改这些模板，以创建已针对你的需求优化的评估。 您还可以通过使用自己的控件和操作创建模板来构建自定义评估。 例如，你可能希望模板涵盖内部 业务流程 控件，或我们的 325 多个预建评估模板之一未涵盖的区域数据保护标准。

##### <a name="learn-more"></a>了解详细信息

[查看合规性管理器提供的评估模板列表](compliance-manager-templates-list.md)。

[获取有关创建和修改评估模板的详细说明](compliance-manager-templates.md)。

### <a name="improvement-actions"></a>改进操作

改进操作有助于集中您的合规性活动。 每项改进操作都提供建议指导，旨在帮助您遵守数据保护法规和标准。 可以将改进操作分配给贵组织的用户，以执行实施和测试工作。 您还可以在改进操作中存储文档、备注和记录状态更新。

##### <a name="learn-more"></a>了解详细信息

[使用改进操作来管理合规性工作流](compliance-manager-improvement-actions.md)。

[了解操作如何影响合规性分数](compliance-score-calculation.md#action-types-and-points)。

## <a name="supported-languages"></a>支持的语言

合规性管理器提供以下语言版本：

- 英语
- 印度尼西亚语
- 马来语
- 中文（简体）
- 中文（繁体）
- 捷克语
- 丹麦语
- 荷兰语
- 芬兰语
- 法语
- 德语
- 希伯来语
- 匈牙利语
- 意大利语
- 日语
- 朝鲜语
- 挪威语
- 波兰语
- 葡萄牙语（巴西）
- 俄语
- 西班牙语
- 瑞典语
- 泰语
- 土耳其语

## <a name="next-steps-set-up-and-customize"></a>下一步：设置和自定义

若要了解如何登录、分配权限和角色、配置设置以及个性化仪表板视图，可了解合规性 [管理器入门](compliance-manager-setup.md)。

然后开始自定义合规性管理器，通过设置评估来帮助你遵守对组织最重要的 [行业标准](compliance-manager-assessments.md)。

为了帮助你遵守数据隐私法规，我们设计了一个工作流来指导你完成端到端流程，以在 Microsoft 365 中计划和实现功能，包括使用合规性管理器。 有关详细信息，请参阅[使用 Microsoft 365 为数据隐私法规部署信息保护](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy)。 
