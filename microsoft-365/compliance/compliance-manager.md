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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器可帮助组织简化和自动化风险评估，并建议用于帮助解决风险的建议措施。
ms.openlocfilehash: d7136368a1c9726d1a77a0c99e717b98e1920242
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791799"
---
# <a name="microsoft-compliance-manager"></a>Microsoft 合规性管理器

**本文内容：** 了解什么是合规性管理器、它如何帮助简化合规性并降低风险以及关键组件。

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>新增功能：合规性管理器的正式发行版

合规性管理器现已推出 (GA) 作为 [Microsoft 365 合规性中心](microsoft-365-compliance-center.md)内的端到端合规性管理解决方案。 在此版本中，合规性管理器将从 Microsoft 服务信任门户中先前的位置完成转换。

由于合规性分数的公开预览发展成为集中式工具，具有增强的合规性管理功能和更易于使用的功能。  GA 发行版中引入了一个更大的预建评估集合，可帮助您扩展合规性活动。

**了解有关 GA 版本的详细信息：**
- 我们的 [常见问题](compliance-manager-faq.md) 将更详细地引导您完成发展。
- 阅读 [此博客文章](https://aka.ms/compliancemanager/GAblog)中的 "GA 功能增强"。

观看以下视频，了解合规性管理器如何帮助简化组织管理合规性的方式：
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>什么是合规性管理器

[Microsoft 合规性管理器](https://compliance.microsoft.com/compliancemanager) 是 [microsoft 365 合规性中心](microsoft-365-compliance-center.md) 中的一项功能，可帮助您更轻松、方便地管理组织的合规性要求。 合规性管理器可帮助你在法规遵从性旅程中进行，从获取数据保护风险的清单到管理实施控制的复杂性，保持最新的管理法规和证书，并向审计员报告。

合规性管理器通过提供以下功能帮助简化合规性并降低风险：

- 针对常见行业和区域标准和管理法规的预建评估，或自定义评估以满足您的独特合规性需求 (可用评估取决于您的许可协议; [了解详细](https://go.microsoft.com/fwlink/?linkid=2132371)) 。

- 工作流功能，可帮助您通过单一工具高效地完成风险评估。

- 有关建议的改进措施的详细分步指南，可帮助您遵守与贵组织最相关的标准和法规。 对于由 Microsoft 管理的操作，你将看到 "实施详细信息" 和 "审核结果"。

- 基于风险的符合性分数，可帮助您了解完成改进措施中的进度，以帮助您了解合规性状态。

合规性管理器仪表板显示了你当前的合规性分数，可帮助你查看需要注意的事项，并指导你执行关键改进操作。 下面是合规性管理器仪表板外观的示例：

![合规性管理器-仪表板](../media/compliance-manager-dashboard.png "合规性管理器仪表板")

## <a name="understanding-your-compliance-score"></a>了解合规性分数

合规性管理者奖项您要为符合法规、标准或策略的措施完成改进措施，并将这些点组合到整体合规性分数中。 每个操作对你的分数有不同的影响，具体取决于所涉及的潜在风险。 您的合规性分数可帮助您确定重点关注的操作，以改进您的总体合规性状态。

合规性管理器为你提供了基于 Microsoft 365 数据保护基准的初始分数。 此基准是一组控件，包括用于数据保护和常规数据管理的关键法规和标准。

##### <a name="learn-more"></a>了解详细信息

[了解如何计算合规性分数](compliance-score-calculation.md)。

[了解如何处理改进操作](compliance-manager-improvement-actions.md)。

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>关键元素：控件、评估、模板、改进操作

合规性管理器使用多个数据元素来帮助您管理合规性活动。 在使用合规性管理器分配、测试和监视合规性活动时，对关键元素有一个基本的了解是很有帮助的：控件、评估、模板和改进操作。

### <a name="controls"></a>控件

控件是法规、标准或策略的要求。 它定义了如何评估和管理系统配置、组织过程以及负责满足法规、标准或策略的特定要求的人员。

合规性管理器跟踪以下类型的控件：

1. **Microsoft 托管控件** ： microsoft 云服务的控件，microsoft 负责实现
2. **您的控件** ：有时称为 "客户托管控件"，它们是由您的组织实现和管理的控件
3. **共享控件** ：这些控件是你的组织和 Microsoft 共同负责实施的控制

##### <a name="learn-more"></a>了解详细信息

[监视控件的进度](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)。

[了解合规性管理器如何持续评估控件](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)。

### <a name="assessments"></a>评估

评估是从特定的法规、标准或策略中对控件进行分组。 完成评估中的操作可帮助您满足标准、法规或法律的要求。 例如，您可能有一个评估，在完成其中的所有操作后，可帮助您将 Microsoft 365 设置为符合 ISO 27001 的要求。

评估具有以下几个组件：

- **范围内的服务** ：适用于评估的一组特定的 Microsoft 服务
- **Microsoft 托管控件** ： microsoft 云服务的控件，microsoft 云服务代表你代表你实施
- **您的控件** ：有时称为 "客户托管控件"，它们是由您的组织实现和管理的控件
- **共享控件** ：这些控件是你的组织和 Microsoft 共同负责实施的控制
- **评估成绩** ：显示从评估中的操作（由组织和 Microsoft 管理）获得的可能积分总数的进度

在创建评估时，您需要将其分配给一个组。 您可以按对组织的最逻辑的任何方式配置组。 例如，您可以按审核年、区域、解决方案、组织内的团队或其他某种方式对评估进行分组。 创建组后，您可以对 [合规性管理器仪表板进行筛选](compliance-manager-setup.md#filtering-your-dashboard-view) ，以查看一个或多个组的分数。

##### <a name="learn-more"></a>了解详细信息

[在合规性管理器中构建和管理评估](compliance-manager-assessments.md)。

### <a name="templates"></a>模板

合规性管理器提供可帮助您快速创建评估的模板。 您可以修改这些模板以创建针对您的需求而优化的评估。 您还可以通过创建包含自己的控件和操作的模板来构建自定义评估。 例如，您可能希望模板涵盖内部业务流程控制，或者是我们的150个预构建的评估模板中的一个不包含的区域数据保护标准。

##### <a name="learn-more"></a>了解详细信息

[查看合规性管理器提供的评估模板的列表](compliance-manager-templates-list.md)。

[获取创建和修改用于评估的模板的详细说明](compliance-manager-templates.md)。

### <a name="improvement-actions"></a>改进操作

改进操作可帮助您集中执行合规性活动。 每个改进操作都提供了建议的指南，旨在帮助您与数据保护法规和标准保持一致。 可将改进操作分配给组织中的用户，以执行实施和测试工作。 您还可以在 "改进" 操作中存储文档、注释和记录状态更新。

##### <a name="learn-more"></a>了解详细信息

[使用提高操作来管理合规性工作流](compliance-manager-improvement-actions.md)。

[了解操作对合规性分数的影响](compliance-score-calculation.md#action-types-and-points)。

## <a name="supported-languages"></a>支持的语言

合规性管理器可采用以下语言：

- 英语
- 马来印度尼西亚语
- 马来马来语
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

## <a name="next-steps-set-up-and-customize"></a>后续步骤：设置和自定义

了解如何登录、分配权限和角色、配置设置以及在 [合规性管理器开始](compliance-manager-setup.md)时自定义仪表板视图。

然后，开始自定义合规性管理器，以帮助您遵循与您的组织最重要的行业标准（通过 [设置评估](compliance-manager-assessments.md)）。