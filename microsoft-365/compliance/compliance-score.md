---
title: Microsoft 合规性分数（预览）
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性分数（预览版）可帮助组织简化和自动化风险评估，并建议用于帮助解决风险的建议措施。
ms.openlocfilehash: 0cb8bd0b5aa39be2a9a6e706afa21bb7dc53eadb
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016135"
---
# <a name="microsoft-compliance-score-preview"></a>Microsoft 合规性分数（预览）

**本文内容：** 了解符合性分数是什么，它如何帮助简化管理法规遵从性的方式，以及如何为你的组织进行设置。

**新增功能：** 2020年6月发布的版本包含用于创建和管理评估的新功能，以及查看合规性分数内的控制措施。 访问[合规性分数发行说明](compliance-score-release-notes.md)，查看合规性分数的公开预览版中的新增功能。

## <a name="what-is-compliance-score"></a>合规性分数是什么

[Microsoft 合规性分数](https://compliance.microsoft.com/compliancescore)是[microsoft 365 合规性中心](microsoft-365-compliance-center.md)中的一项预览功能，可帮助您了解组织的合规性状况。 它将计算基于风险的分数，以衡量您在帮助降低数据保护和法规标准方面的风险的完成操作的进度。

您可以使用合规性分数作为一种工具来跟踪所有风险评估。 它提供了工作流功能，可帮助您通过通用工具高效完成风险评估。

[合规性管理器](compliance-manager-overview.md)用户将注意到，合规性分数现在是一项独立功能，具有更简单、更易于使用用户的设计，可帮助组织更轻松地管理合规性。

主合规性分数页面是自定义仪表板。 它显示了你当前的成绩，可帮助你查看需要注意的事项，并指导你提高成绩的操作。 您的合规性分数仪表板将如下所示：

![合规性分数-仪表板](../media/compliance-score-dashboard.png "合规性分数仪表板")

### <a name="simplified-compliance-management"></a>简化了合规性管理

合规性分数通过提供以下功能来帮助简化合规性管理：

- **持续评估**：通过 Microsoft 365 环境自动扫描，以检测和监视系统中数据保护控件的有效性
- **建议的操作**：提供有关如何实现控制以最大化分数的建议和分步指南
-  **内置的控件映射**：通过提供内置的通用控制框架，帮助您及时了解日益发展的合规性环境

> [!IMPORTANT]
> 合规性分数和合规性管理器中提供的建议不应解释为合规性保证。 根据您的法规环境评估和验证客户控制措施的有效性。 这些服务当前处于预览阶段，并遵循[在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件。 另请参阅[适用于安全性和合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="relationship-to-compliance-manager"></a>与合规性管理器的关系

将合规性分数视为合规性管理器的简化体验。 虽然这两个功能与集成的工具不同时存在，但遵从性分数可使您更轻松地监控整体合规性状况并采取措施来改进。

合规性分数与合规性管理器共享相同的后端。 您在一个工具中执行的任何操作都将在另一个工具中呈现。

在公共预览过程中，评估和模板管理的一些功能仍在合规性管理器中。 我们建议你在合规性分数中开始所有合规性管理活动。 当你转到合规性管理器处理的函数时，我们将指导你。

#### <a name="learn-more"></a>了解详细信息

[了解合规性分数与合规性管理器之间的关系](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)。

## <a name="understanding-your-score"></a>了解你的成绩

合规性分数奖项您需要完成的操作，以遵守法规、标准或策略。 每个操作对你的分数有不同的影响，具体取决于所涉及的潜在风险。 你的分数可帮助优先考虑要关注的操作，以改进你的总体合规性状况。

合规性分数为你提供了基于 Microsoft 365 数据保护基准的初始分数。  此基准是一组控件，包括用于数据保护和常规数据管理的关键法规和标准。 此基线主要从 NIST CSF （美国国家标准和技术协会 Cybersecurity Framework）和 ISO （国际标准化组织）以及 FedRAMP （联邦风险和授权管理计划）和 GDPR （欧盟的常规数据保护法规）中提取元素。

数据保护基准评估用于在配置任何其他评估之前计算您的初始分数。 首次访问时，合规性分数已从 Microsoft 365 解决方案中收集信号。 你将快速了解你的组织是如何相对于关键数据保护标准和管理法规执行的，并查看建议采取的改进措施。

由于每个组织都有特定的需求，因此合规性分数取决于您设置和管理您自己的评估以更好地缓解风险。 例如，如果您的组织属于金融服务行业，您可能需要添加 FFIEC 评估。 如果您的组织属于医疗保健行业，则可以添加 HIPAA/高科技评估。

#### <a name="learn-more"></a>了解详细信息

[了解如何计算和持续监控合规性分数](compliance-score-methodology.md)。

[在合规性分数中创建和管理评估](compliance-score-assessments.md)。

## <a name="key-components-controls-assessments-templates-improvement-actions"></a>关键组件：控件、评估、模板、改进操作

合规性分数使用多个组件来帮助您管理合规性活动。 在使用合规性分数分配、测试和监视合规性活动时，有必要对关键组件有一个基本的了解：控件、评估、模板和改进操作。

### <a name="controls"></a>控件

控件是法规、标准或策略的要求。 它定义了如何评估和管理系统配置、组织过程以及负责满足法规、标准或策略的特定要求的人员。

合规性分数跟踪两种类型的控件：

1. **Microsoft 托管控件**： microsoft 云服务的控件，microsoft 负责实现
2. **您的控件**：有时称为 "客户控件"，它们是由您的组织实现和管理的控件

#### <a name="learn-more"></a>了解详细信息

[监视控件的进度](compliance-score-assessments.md#monitor-assessment-progress-and-controls)。

### <a name="assessments"></a>评估

评估是从特定的法规、标准或策略中对控件进行分组。 完成评估中的操作可帮助您满足标准、法规或法律的要求。 例如，您可以进行一项评估，在完成其中的所有操作后，会将 Microsoft 365 设置为符合 ISO 27001 要求的行为。

评估具有以下几个组件：

- **范围内的服务**：适用于评估的一组特定的 Microsoft 服务
- **Microsoft 托管控件**： microsoft 实现和测试的控件
- **您的控件**：您管理的控件
- **评估分数**：在该评估中完成改进操作所实现的分数百分比

在创建评估时，您需要将其分配给一个**组**。 您可以按对组织的最逻辑的任何方式配置组。 例如，您可以按年、合规性标准、服务、组织内的团队或其他方式对评估进行分组。 创建组后，您可以[筛选合规性分数仪表板](compliance-score-setup.md#filtering-your-dashboard-view)，以查看一个或多个组的分数。

#### <a name="learn-more"></a>了解详细信息

[在合规性分数中创建和管理评估](compliance-score-assessments.md)。

### <a name="templates"></a>模板

合规性分数提供可供你快速创建评估的模板。 您可以修改这些模板以创建针对您的需求而优化的评估。 您还可以通过使用自己的控件和操作来开发自己的模板来创建自定义评估。 例如，您可能希望模板涵盖内部业务流程控制或一个我们的模板未涵盖的区域数据保护标准。

通过创建您自己的模板，不仅可以跟踪 Microsoft 云评估，还可以跟踪组织范围内的任何其他风险评估。

#### <a name="learn-more"></a>了解详细信息

[查看适用于构建评估的合规性分数中的模板](compliance-score-templates.md)。

[获取有关创建和修改模板合规性管理器的详细说明](working-with-compliance-manager.md#templates)。

### <a name="improvement-actions"></a>改进操作

改进的操作将对合规性活动进行集中。 每个改进操作都提供了详细的实施指导，可帮助您与数据保护法规和标准保持一致。 可将操作分配给组织中的用户，以执行实施和测试工作。 您还可以在 "改进" 操作中存储文档、注释和记录状态更新。

#### <a name="learn-more"></a>了解详细信息

[使用提高操作来管理合规性工作流](compliance-score-improvement-actions.md)。

## <a name="next-steps-set-up-and-customize"></a>后续步骤：设置和自定义

了解如何登录、设置权限和角色、配置安全分数更新以及在[合规性分数设置](compliance-score-setup.md)时对仪表板视图进行个性化设置。

然后，通过[设置评估](compliance-score-assessments.md)开始为你的组织自定义合规性分数。