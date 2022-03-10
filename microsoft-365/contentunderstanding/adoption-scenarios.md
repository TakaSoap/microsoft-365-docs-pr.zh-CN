---
title: Microsoft SharePoint Syntex 的应用场景和用例
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
ms.localizationpriority: medium
description: 查找有关如何在组织中使用SharePoint Syntex业务方案。
ms.openlocfilehash: fe4f72dc56014e5bc990e5ea39bd019785bd8572
ms.sourcegitcommit: 40f89c46032ea33de25417106f39cbeebef5a049
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2022
ms.locfileid: "63419081"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex 的应用场景和用例

使用以下示例方案可提示有关在组织中如何使用SharePoint Syntex的想法。

- [应用场景：通过表单处理跟踪发票数据](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [方案：通过了解文档来跟踪合同信息](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [应用场景：避免基于记录管理、文档管理和合规性流程SharePoint Syntex](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [方案：捕获以前无法访问的文档的信息](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [方案：改进数据处理以提供见解和分析](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [方案：自动执行订单处理](adoption-scenarios.md#scenario-automate-order-processing)
- [应用场景：简化护照续订流程](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a>应用场景：通过表单处理跟踪发票数据

例如，您可以使用一个使用 SharePoint Syntex 和 Power Automate 功能来跟踪和监视发票的过程。

1. 设置用于存储发票文档的库。
1. 训练模型以识别文档中的字段。
1. 将要跟踪的字段提取到列表中。
1. 设置一个流，以针对特定事件通知您，例如：
    - 将添加一个新的发票。
    - 发票已过期。
    - 发票的金额大于自动审批金额。

![使用发票和 SharePoint Syntex 跟踪Power Automate。](../media/content-understanding/process-invoices-flow.png)

当您自动执行此方案时，您可以：

- 通过自动从发票中提取数据而不是手动提取数据来节省时间和资金。
- 通过使用工作流检查发票并通知您任何问题，减少潜在错误并确保更好的合规性。

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a>方案：通过了解文档来跟踪合同信息

另一个示例是，您可以设置一个流程来识别贵公司与其他公司或个人的合同。 设置一个模型以从这些合同中提取关键信息（如客户端名称、费用、日期或其他重要信息）并作为您可以快速查看的字段将信息添加到库中。 在文档库上应用保留标签，以确保在一段特定时间前无法删除合同，以适当遵守业务法规。

1. 从内容中心开始，为合同创建新的文档理解模型。
1. Upload示例文档，然后运行培训以确定合同文档并查看结果。
1. 培训提取程序以识别合约中的字段，如客户端名称、费用、日期，然后测试提取程序。
1. 模型完成后，将模型应用到可在其中上载合约的库。
1. 将保留标签应用于日期字段，以便合同在库中保留所需时间。

![使用标签和保留标签SharePoint Syntex和监视合同。](../media/content-understanding/process-contracts-flow.png)

当您自动执行此方案时，您可以：

- 通过自动从合同中提取数据而不是手动提取数据来节省时间和资金。
- 通过使用保留标签来确保更好地合规性，以确保适当地保留合同。

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>应用场景：避免基于记录管理、文档管理和合规性流程SharePoint Syntex

降低风险是大多数公司的共同目标。 您可能需要：

- 在整个租户中提供/强制执行信息治理的更好方法。
- 改进文档、电子邮件和视为项目的"记录"的其他形式的通信的分类系统。
- 审核收据、合同等，以确保遵守公司策略。
- 确保项目具有合规性所需的全部文档。

设置一些流程以遵守SharePoint Syntex，以捕获和适当分类、审核和标记需要更好治理的文档和表单。 您可以依赖SharePoint Syntex来自动对内容进行分类，而不是依赖最终用户手动标记，或者依赖合规性团队手动应用管理规则和存档。 您可以启用简化的搜索体验、管理数据卷、应用记录管理和保留策略、确保合规性以及最佳实践存档和清除实践。

当您自动执行此方案时，您感觉安全：

- 合规性得到维持，并且风险已降低。
- 分类和记录管理一致且准确应用。
- 控制内容卷。
- 员工可以轻松在正确的上下文中发现正确的信息。

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>方案：捕获以前无法访问的文档的信息

大多数组织都有法律文档、策略、合同、HR 文档和管理准则的大型存储库。 挖掘这些数据存储以提取有价值的信息，例如：项目、部门、主题、人员、地理区域等。

例如，HR 主管需要快速访问所有 HR 文档，包括简历、HR 策略和其他表单。 他们希望从简历和其他与 HR 相关的文档中快速识别必要信息，而无需手动对文档进行筛选。 他们正在寻找一个解决方案，通过该解决方案，他们可以快速找到所需的信息，而无需手动查看成千上万条简历、HR 策略和其他可能分布于多个网站的文档。

当您自动执行此方案时，您可以：

- 从数字内容中解锁知识。
- 对 HR 策略、简历、销售文档、技术蓝图、帐户计划和提取信息进行分类。
- 快速找到要查找的正确信息或文档。
- 即时访问最新信息。
- 缩短搜索时间。

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a>方案：改进数据处理以提供见解和分析

例如，一家SharePoint Syntex公司可以使用代码从 FDA 文档中提取信息，以回答其领导的问题。 使答案更易于访问可以缩短生成这些答案的时间，并增加数据的可用性以生成更准确的领导问题的答案。

例如，项目经理需要从我领导团队快速提供产品相关问题的解答。 他们需要在一个合并仪表板中查找与查询相关的信息和指标。 他们正在寻找一个解决方案，从产品标签、产品 pamphlet 和其他材料中提取他们需要的信息，并生成一份合并报告，在向领导团队报告时可以使用该报告。

当您自动执行此方案时，您可以：

- 减少生成答案的时间。
- 提高数据的可用性。
- 提供更准确的答案。

## <a name="scenario-automate-order-processing"></a>方案：自动执行订单处理

使用 SharePoint Syntex，您可以缩短手动处理客户订单的时间。 例如，您可以使用 OCR 处理将传真、电子邮件或纸张中的订单上载到 SharePoint，然后从这些订单中提取元数据，以便您可以使用自动化流程完成这些订单。

例如，供应链经理希望减少由手动数据输入导致的错误。 他们希望避免手动检查入站客户订单以及 (、传真或电子邮件) ，以减少进入业务系统的错误。 他们希望一个应用 AI 和机器学习技术的解决方案来验证传入订单信息、提取核心数据并自动推送到其 ERP 系统中，以便实现订单履行与对帐。

自动执行此方案时，可以确保：

- 订单和装运准确度提高。
- 减少与订单或发货错误相关的费用或处罚。
- 发票或付款延迟减少。
- 人员成本降低。

## <a name="scenario-simplify-visa-renewal-process"></a>应用场景：简化护照续订流程

SharePoint Syntex可帮助你自动执行关键合同信息的提醒和续订。 例如，HR 主管需要确保员工的护照是最新的和/或及时续订的。 他们希望为用户提供一个简单直观的更新其 Visa 的过程。 他们需要一个从合同中提取续订日期的解决方案，并自动在员工续订日期接近时发送提醒。

自动执行此方案时，可以确保：

- 不合规级别已降低。
- 减少了手动提醒的数量。
- 针对不合规的罚款数量减少。

## <a name="see-also"></a>另请参阅

[Microsoft SharePoint Syntex采用：入门](adoption-getstarted.md)