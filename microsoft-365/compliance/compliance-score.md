---
title: Microsoft 合规性分数
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
description: Microsoft 合规性分数可帮助组织简化和自动化风险评估，并建议用于帮助解决风险的建议措施。
ms.openlocfilehash: f604f52fd66664aeb1b61fb873cfe40e8f48115c
ms.sourcegitcommit: 544b10cc3abe04a47438085d51c4250c9238f76f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "38685060"
---
# <a name="microsoft-compliance-score-preview"></a>Microsoft 合规性分数（预览）

Microsoft 合规性分数有助于简化管理合规性的方式，并通过用户友好的体验降低合规性风险。 合规性分数现在适用于[Microsoft 365 合规性中心](microsoft-365-compliance-center.md)中的公共预览版。 阅读本文，了解符合性分数、它如何帮助您管理组织的合规性，以及如何开始。

## <a name="what-is-compliance-score"></a>合规性分数是什么

Microsoft 合规性分数是 Microsoft 365 合规性中心中的一项预览功能，可帮助您了解组织的合规性状况。 它将计算基于风险的分数，以衡量您在帮助降低数据保护和法规标准方面的风险的完成操作的进度。

您可以使用合规性分数作为一种工具来跟踪所有风险评估。 它提供了工作流功能，可帮助您通过通用工具高效地执行和完成风险评估。

如果您当前使用[合规性管理器](compliance-manager-overview.md)，您会注意到，合规性分数现在是一个独立的功能，具有更简单、更易于使用用户的设计，可帮助您更轻松地管理合规性。 

主合规性分数页面是自定义仪表板。 它显示了你当前的成绩，可帮助你查看需要注意的事项，并指导你提高成绩的操作。 您的合规性分数仪表板将如下所示：

![合规性分数-仪表板](media/compliance-score-dashboard.png "合规性分数仪表板")

### <a name="simplified-compliance-management"></a>简化了合规性管理

合规性分数通过提供以下功能来帮助简化合规性管理：

- **持续评估**：通过 Microsoft 365 环境自动扫描，以检测和监视系统中数据保护控件的有效性
- **建议的操作**：提供有关如何实现控制以最大化分数的建议和分步指南
-  **内置的控件映射**：通过提供内置的通用控制框架，帮助您及时了解日益发展的合规性环境

> [!IMPORTANT] 
> 合规性分数不表示对任何特定标准或法规的组织合规性的绝对衡量。 它表示您已采用的控制程度，可降低个人数据和个人隐私的风险。 不应将合规性分数和合规性管理器中的建议解释为合规性保证。 此服务目前处于预览阶段，并受[在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件的制约。

## <a name="relationship-to-compliance-manager"></a>与合规性管理器的关系

将合规性分数视为合规性管理器的简化版本。 虽然这两个功能与集成的工具不同时存在，但遵从性分数可使您更轻松地监控整体合规性状况并采取措施来改进。

合规性分数与合规性管理器共享相同的后端，因此合规性管理器中可能已具有的任何数据将在合规性分数中显示。

在公共预览版中，某些功能仅保留在合规性管理器中，例如管理评估和创建模板。 我们建议你在合规性分数中开始所有合规性管理活动。 当您转到合规性管理器处理的函数时，系统将指导您使用该工具。 出于此原因，本文档中的一些文档将向您提供合规性管理器主题。

了解有关[合规性分数发行说明](compliance-score-release-notes.md)中合规性分数和合规性管理器之间关系的详细信息。

## <a name="understanding-your-score"></a>了解你的成绩

合规性分数为您提供了基于 Microsoft 365 数据保护基准的现成分数，这是一组包含常见行业法规和标准的控件。 虽然这一分数是评估合规性状况的一个很好的起点，但一旦添加了与贵组织更相关的评估，合规性分数就会变得更加强大。

例如，如果您的组织属于金融服务行业，您可能需要添加 FFIEC 评估。 如果您的组织属于医疗保健行业，则可以添加 HIPAA/高科技评估。 了解如何[在合规性管理器中添加评估](working-with-compliance-manager.md#assessments)。

了解有关[如何计算和持续监控合规性分数](compliance-score-methodology.md)的详细信息。


## <a name="key-components-controls-assessments-templates-groups"></a>关键组件：控件、评估、模板、组

合规性分数使用多个组件来帮助您管理合规性活动。 在使用合规性分数分配、测试和监视合规性活动时，有必要对这些关键组件有一个基本的了解。 此图显示了它们之间的关系：

![合规性管理器版本3中的关系](media/compliance-manager-relationships.png "合规性分数组件")

### <a name="controls"></a>控件

控件定义评估和管理系统配置、组织过程和人员责任的方式，以满足法规、标准或内部策略的特定要求。

合规性分数跟踪两种类型的控件：

1. **Microsoft 托管控件**：这些是 microsoft 云服务的控件，microsoft 负责实现
2. **客户管理的控件**：这些控件由您的组织管理，您负责实施
 
### <a name="assessments"></a>评估

评估是对为您的组织启动计分过程的模板的评估。 评估组满足标准、法规或法律要求所必需的操作。 例如，您可以进行一项评估，在完成所有操作后，将 Office 365 设置为符合 ISO 27001 要求的行为。

默认情况下，合规性分数为您的组织提供基于 Microsoft 365 数据保护基准的评估，这是降低数据保护和合规性风险的建议（[了解详细信息](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)）。

评估包括以下几个组件：

- **范围内的服务**：适用于评估的一组特定的 Microsoft 服务
- **Microsoft 托管控件**： microsoft 实现和测试的控件
- **客户管理的控件**：您管理的控件
- **评估成绩**：完成该评估中的操作所实现的分数百分比

> [!NOTE]
> 合规性分数显示你的评估以及它们对你的总体成绩的影响。 但是，在公开预览过程中，你将转到合规性管理器来管理评估。

查看[合规性管理器中使用评估](working-with-compliance-manager.md#assessments)的详细说明。

### <a name="templates"></a>模板

合规性分数提供了预配置的评估模板。 合规性分数还允许您创建自己的评估模板以满足您的需求。 例如，您可以为业务流程控制创建一个模板，或为不包含在某个预先配置的模板中的区域数据保护或合规性标准的模板。  通过创建您自己的模板，您可以创建自定义评估，以确保合规性分数不仅跟踪 Microsoft 云评估，还跟踪组织范围内的任何其他风险评估。

您可以通过复制现有模板或从 Excel 文件中导入控件信息来创建新模板。 查看[在合规性管理器中创建模板](working-with-compliance-manager.md#templates)的详细说明。

预配置的合规性分数模板包括：

1. [ISO 27001：2013](https://go.microsoft.com/fwlink/?linkid=2109073)
2. [ISO 27018：2014](https://go.microsoft.com/fwlink/?linkid=2109074)
3. [NIST 800-53 修订版4](https://go.microsoft.com/fwlink/?linkid=2109075)
4. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
5. [NIST Cybersecurity Framework （CSF）](https://go.microsoft.com/fwlink/?linkid=2108868)
6. [云安全联盟（CSA）云控制矩阵（CCM）3.0。1](https://go.microsoft.com/fwlink/?linkid=2109076)
8. [联邦金融机构检查委员会（FFIEC）信息安全手册](https://go.microsoft.com/fwlink/?linkid=2109077) 
8. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / 高[科技](https://go.microsoft.com/fwlink/?linkid=2109079)
9. [FedRAMP 中等](https://go.microsoft.com/fwlink/?linkid=2108869)
10. [欧洲联合 GDPR](https://go.microsoft.com/fwlink/?linkid=2108870)
11. [加利福尼亚消费者隐私法案（CCPA）-预览](https://go.microsoft.com/fwlink/?linkid=2108871)
12. [Microsoft 365 数据保护基准](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)

> [!NOTE]
> 在公共预览过程中，转到合规性管理器以创建和管理模板。

### <a name="groups"></a>组

组允许您按符合您的逻辑方式组织评估。 例如，您可以选择按年、合规性标准、服务、组织内的团队或其他方式对评估进行分组。 

当同一个组中的两个不同评估共享客户管理的操作时，一个评估中的操作的实施详细信息、测试和状态自动同步到组中任何其他评估中的相同操作。 这将统一分配给整个组的已分配改进操作，并减少重复工作。

了解如何[在合规性管理器中创建组](working-with-compliance-manager.md#groups)。

## <a name="next-step"></a>后续步骤

登录、设置权限，并了解[合规性分数设置](compliance-score-setup.md)中的合规性分数仪表板。
