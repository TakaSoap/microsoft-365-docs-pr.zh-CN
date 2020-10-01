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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: 了解如何使用合规性分数和合规性管理器改进个人数据保护级别。
ms.openlocfilehash: b5a112b7614de23af8540346e26dac3b7a4fa1c9
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333476"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>使用合规性管理器管理改进操作

Microsoft 合规性管理器可帮助您管理与数据隐私法规相关的改进，如欧盟 [通用数据保护法规 (GDPR) ](../compliance/gdpr.md)、 [加利福尼亚州消费者保护法 CCPA) ](../compliance/ccpa-faq.md)、HIPAA-高科技 (法案) LGPD (。

本文提供了有关使用此工具进行数据保密的指南。

>[!Note]
>来自合规性管理器的建议不应解释为合规性保证。 根据您的法规环境评估和验证客户控制措施的有效性。 这些服务受 [在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件的制约。 另请参阅 [适用于安全性和合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>合规性管理器入门

#### <a name="what-is-compliance-manager"></a>什么是合规性管理器

[合规性管理器](../compliance/compliance-manager.md) 是 microsoft 365 合规性中心中基于工作流的风险评估工具，用于管理与 Microsoft 云服务相关的法规遵从性活动。 作为 Microsoft 365 或 Azure Active Directory (Azure AD) 订阅的一部分，合规性管理器可帮助您管理 Microsoft 云服务的共享职责模型中的法规遵从性。

**准备好使用评估**

合规性管理器提供了预构建的模板，用于建立与与数据隐私相关的法规（如 GDPR 和 HIPAA/高科技）相适应的 [评估](../compliance/compliance-manager-assessments.md) 。 这些模板具有内置的控件映射，可帮助您采取改进措施来满足该规章的要求。 每个评估提供有关特定于目标服务的每项规章调用的控件信息，由您管理和控制 Microsoft 管理的控件来细分。 

使用预建的模板可帮助您快速开始使用风险评估。 随着您在使用合规性管理器方面更加熟练，可以通过添加自己的控件和改进操作来自定义预建的模板，也可以创建自己的自定义评估以满足组织的需求。

查看合规性管理器提供 [的评估模板的完整列表](../compliance/compliance-manager-templates-list.md) 。

**实时合规性分数**

合规性管理器还提供了合规性分数，用于衡量在控件中完成建议的改进操作的进度。 您可以使用此分数帮助监视进度，并根据其可能降低风险的可能性对操作进行排序。

#### <a name="use-the-compliance-manager-quickstart-guide"></a>使用合规性管理器快速入门指南

[合规性管理器快速入门](../compliance/compliance-manager-quickstart.md)指南提供了渐变步骤和指向关键资源的链接，可帮助您使用合规性管理器：

- [首次访问：熟悉合规性管理器](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - 使用合规性管理器仪表板
    - 了解合规性分数
    - 了解改进操作
    - 了解评估和模板
- [斜向向上刀：配置合规性管理器以管理合规性活动](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - 构建和管理您的首个评估
    - 执行实施和测试有关改进操作的工作以完成评估中的控件
    - 了解不同操作对合规性分数有何影响
- [向上扩展：使用高级功能满足你的自定义需求](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - 创建自定义评估以跟踪非 Microsoft 365 产品
    - 修改现有模板以添加或删除控件
    - 设置对改进操作的自动测试

## <a name="how-your-compliance-score-is-calculated"></a>如何计算合规性分数

您的合规性分数是基于 Microsoft 和客户托管的控制实施的组合计算的。 有关详细说明，请参阅 [合规性分数计算](../compliance/compliance-score-calculation.md) 。

根据控件是强制性的还是自由的，以及是否为预防性、侦探或纠正措施，为控件分配分数值。 这些共同体现了其相对于其他控件的实现风险。

如合规性分数计算文章中所示，预防性控制获得比侦探和纠正措施更高的分数，强制性控制措施比随机控制获得更高的分数。

合规性分数管理 UI 不会列出这些参数，也不能提供对其进行筛选的功能。 但是，如果从合规性管理器下载关联的模板，则生成的数据集将为大多数管理法规列出这些参数。

对于技术控制，合规性管理器会在成功实现并测试操作后自动更新改进操作得分。 其他非技术性控制操作 &mdash; （如可操作或与文档相关的操作） &mdash; 需要手动记录，然后再按磅数计算到您的成绩。

您还需要为其他目的实施某些改进操作，例如， &mdash; 使用保留标签作为数据隐私法规遵从性之外的原因 &mdash; ，这样您就可以获得使用此类功能的信用，即使它用于其他用途，也不是有意的合规性操作的一部分。

应将合规性分数视为跟踪广泛规模改进的相对度量。 您不应争取一个理想的分数。

## <a name="additional-guidance"></a>其他指南

下面是使用合规性管理器帮助您实现数据隐私法规遵从性的一些重要提示：

- 每个数据隐私法规都结合了技术控制、文档规范以及操作、过程和报告要求。 所有这些操作都显示在改进操作中。

- 若要将改进操作视图集中到您感兴趣的领域，可以在合规性管理器管理员的 " **解决方案** " 选项卡中按操作类型进行筛选。了解有关 [筛选合规性管理器仪表板视图](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)的详细信息。

- 应将合规性管理器中标识的改进操作的相对重要性和优先级视为广泛风险评审的一部分以及已确定组织需要管理的数据隐私风险。

- 即使选择了跨多个法规要求的改进操作聚合，如果选择了 GDPR、LGPD、CCPA 和 HIPAA-高科技的法规评估模板，例如，合规性管理器中将列出几乎400的改进操作。 若要更好地解决此较长的列表，请使用改进操作筛选器将结果集减少为更易于管理的列表。

- "类别" 筛选器提供了一种通过逻辑分组来筛选改进操作的方法，此整体解决方案中的跟踪、阻止、保护、保留和调查文章与对应。

- 改进操作中列出的某些控件可能更直接绑定到特定的规章文章，而其他控件可能更直接与法规精神关联，而多次只是建议的活动或最佳做法。