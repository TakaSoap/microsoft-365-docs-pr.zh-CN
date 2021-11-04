---
title: 使用合规性管理器管理改进操作
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: admindeeplinkCOMPLIANCE
description: 了解如何使用合规性分数和合规性管理器提高对个人数据的保护级别。
ms.openlocfilehash: 5a655d504551e42398cdabbcf7a3f651d788c0ad
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786010"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>使用合规性管理器管理改进操作

Microsoft 合规性管理器可帮助你管理与数据隐私法规相关的改进，例如欧盟一般数据保护条例 [ (GDPR) 、 ](/compliance/regulatory/gdpr)加州消费者保护法案 [CCPA ](/compliance/regulatory/ccpa-faq)) 、HIPAA-HITECH (美国医疗保健隐私法案) 和巴西数据保护法案 (LGPD) 。

本文提供有关出于数据隐私目的使用此工具的指南。

> [!NOTE]
> 来自合规性管理器的建议不应解释为合规性保证。 由你根据法规环境评估和验证客户控制措施的有效性。 这些服务受联机服务条款中的 [条款和条件限制](https://go.microsoft.com/fwlink/?linkid=2108910)。 另请参阅[Microsoft 365安全性和合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="getting-started-with-compliance-manager"></a>合规性管理器入门

#### <a name="what-is-compliance-manager"></a>什么是合规性管理器

[合规性管理器](../compliance/compliance-manager.md)是 Microsoft 365 合规中心 中基于工作流的风险评估工具，用于管理与 Microsoft 云服务相关的法规合规性活动。 合规性管理器作为 Microsoft 365 或 Azure Active Directory (Azure AD) 订阅的一部分，可帮助你在 Microsoft 云服务的共享责任模型中管理法规合规性。

**准备使用评估**

合规性管理器提供预建模板，用于构建[](../compliance/compliance-manager-assessments.md)符合数据隐私相关法规（如 GDPR 和 HIPAA/HITECH）的评估。 这些模板具有内置的控制映射，可帮助你采取改进措施，满足法规的要求。 每项评估都提供有关特定于目标服务的每个法规调用的控制措施的信息，这些信息由你管理的控制措施和 Microsoft 管理的控制措施细分。

使用预建模板可帮助你快速开始使用风险评估。 随着你更加熟练地使用合规性管理器，可以通过添加自己的控制措施和改进操作来自定义预建模板，也可以创建自己的自定义评估以满足组织的需求。

查看 [合规性管理器提供的评估](../compliance/compliance-manager-templates-list.md) 模板的完整列表。

**实时合规性分数**

合规性管理器还会提供合规性分数，用于衡量在控制措施中完成建议改进操作的进度。 可以使用此分数来帮助监视进度，并基于操作可降低风险的可能性确定操作优先级。

#### <a name="use-the-compliance-manager-quickstart-guide"></a>使用合规性管理器快速入门指南

合规性 [管理器快速入门](../compliance/compliance-manager-quickstart.md) 指南提供了关键资源的指导步骤和链接，以帮助您使用合规性管理器：

- [首次访问：熟悉合规性管理器](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - 使用合规性管理器仪表板
    - 了解合规性分数
    - Learning改进操作
    - 了解评估和模板
- [加速：配置合规性管理器以管理合规性活动](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - 生成和管理你的第一个评估
    - 执行实施和测试工作以改进操作以完成评估中的控制措施
    - 了解不同操作对合规性分数的影响
- [向上扩展：使用高级功能来满足自定义需求](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - 创建自定义评估以跟踪非Microsoft 365产品
    - 修改现有模板以添加或删除控件
    - 设置改进操作自动化测试

## <a name="how-your-compliance-score-is-calculated"></a>如何计算合规性分数

合规性分数根据 Microsoft 和客户管理的控件实现的组合进行计算。 有关 [详细说明，请参阅](../compliance/compliance-score-calculation.md) 合规性分数计算。

根据控制措施是必需还是随意，以及控制措施是预防型、检测型还是纠正型，为控制措施分配分数值。 这些统一表示未实现它相对于其他控件的风险。

如合规性分数计算文章所介绍，预防性控制措施的分数高于检测分数和纠正分数，强制控制措施的分数高于随意控制措施的分数。

合规性分数管理 UI 不会列出这些参数，也不提供按这些参数进行筛选的能力。 但是，如果从合规性管理器下载关联的模板，生成的数据集会列出这些参数，以用于大多数法规。

对于技术控制措施，一旦成功实施和测试了改进行动，合规性管理器就会自动更新改进行动分数。 其他非技术控制操作（如可操作或与文档相关的操作）需要手动记录为已实现，然后点 &mdash; &mdash; 算在你的分数中。

你还出于其他目的实施某些改进操作，例如，出于数据隐私法规合规性外的其他原因，使用保留标签，以便即使此功能用于其他目的，并且不是有意的合规性措施的一部分，你也将因使用此功能而获得支持。 &mdash; &mdash;

合规性分数应视为跟踪大规模改进的相对度量。 你不应获得完美分数。

## <a name="additional-guidance"></a>其他指南

以下是有关使用合规性管理器帮助你实现数据隐私法规合规性的一些重要提示：

- 每个数据隐私法规都组合了技术控制、文档规范以及操作、过程和报告要求。 所有这些操作都显示在改进操作中。

- 若要将改进操作视图集中在你感兴趣的领域，可以在合规性管理器管理员的"解决方案"选项卡中按操作类型进行筛选。详细了解如何[筛选合规性管理器仪表板视图](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)。

- 合规性管理器中确定的改进措施的相对重要性和优先级应视为更广泛的风险评审的一部分，以及确定组织需要管理的数据隐私风险。

- 即使跨多个法规要求聚合了改进行动，如果选择适用于 GDPR、LGPD、CCPA 和 HIPAA-HITECH 的法规评估模板，例如，合规性管理器中将列出近 400 项改进措施。 为了更好地应对这一长列表，请使用改进操作筛选器结果集更易于管理的列表。

- 类别筛选器提供了一种通过逻辑分组筛选改进操作的方法，此整体解决方案中的跟踪、阻止、保护、保留和调查文章与这些逻辑分组一致。

- 改进操作中列出的某些控制措施可能会被视为与特定法规条款更直接关联，而其他控制措施可能更间接地与法规的体现相关联，并且许多时候只是建议的活动或最佳做法。