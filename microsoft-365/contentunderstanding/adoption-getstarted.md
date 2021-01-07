---
title: Microsoft SharePoint 合成器采用：入门
description: 了解如何在组织中使用和实施 SharePoint Syntex，以帮助你解决业务问题。
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 441f28e36ced25b2e5af3f71235995c8b021f779
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771867"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint 合成器采用：入门

将 SharePoint 合成中可用的智能内容服务视为具有三个部分：

- **内容理解：** 创建无代码 AI 模型以对内容进行分类和提取信息，以自动应用元数据进行知识发现和重用。 了解有关内容[了解的内容。](document-understanding-overview.md)
- **内容处理：** 使用 Power Automate 自动捕获、获取和分类内容并简化以内容为中心的流程。 详细了解内容 [处理](form-processing-overview.md)。
- **内容合规性：** 通过与 Microsoft 信息保护的集成来控制和管理内容以提高安全性和治理。

借助新的 AI 服务和功能，可以使用 SharePoint Syntex 将内容理解和分类应用程序直接构建到内容管理流中。 有两种不同的内容理解方式。 使用的模型类型基于文件格式和用例：

| 表单处理 | 文档理解 |
|:-------|:-------|
| 从文档库创建。 | 在内容中心（SharePoint 合成的一部分）中创建。 |
| 在 AI 生成器中创建的模型。 | 在本机界面中创建的模型。 |
| 用于半结构化文件格式。 | 用于非结构化文件格式。 |
| 可设置分类器。 | 带可选提取器可训练的分类器。 |
| 仅限于单个库。 | 可应用于多个库。 |
| 培训 PDF、JPG、PNG 格式，总计 50 MB/500 pp。 | 培训 5-10 个 PDF、Office 或电子邮件文件，包括负面示例。 |

下表介绍了 SharePoint Syntex 的可用性和许可：

| 表单处理 | 文档理解 |
|:-------|:-------|
| 表单处理依赖于 Power Platform。 <br>有关 Power Platform 和 AI Builder 的全局可用性的信息，请参阅 [Power Platform 可用性](https://dynamics.microsoft.com/geographic-availability/)。 | 可在所有区域使用。 |
| 使用 AI Builder 信用额度。<br>可以批量购买 1M 的信用额度。<br>购买 300 多个 SharePoint 合成器许可证时，将包含 100 万个信用额度。<br>1M 信用将允许处理 2000 个文件页。 | 模型在所有拉丁字母语言中均可用。 除了英语之外，还有德语、瑞典语、法语、西班牙语、意大利语和葡萄牙语。 |
| 针对默认公共数据服务环境进行设置。 | 没有容量限制。 |

有关 AI Builder 信用额度和单位详细信息，请参阅 [AI Builder 许可](https://docs.microsoft.com/ai-builder/administer-licensing)。

SharePoint Syntex 与 Microsoft 365 合规性功能集成，如：

- 根据文档期限或外部事件定义记录策略的保留标签。
- 设置 DLP、加密、共享和条件访问策略的敏感度标签。

用户可以应用标签，也可以由 SharePoint 合成 AI 模型自动应用标签。 分析和文件计划提供标签使用和策略的扩展管理。

## <a name="identify-pilot-business-scenarios-to-optimize"></a>确定要优化的试点业务方案

若要准备在组织中使用 SharePoint 合成，首先需要了解它很有用的方案。 原因有助于确定需要哪种模型，以及如何根据模型的应用位置构建组织。 下面是一些文档理解方案，可帮助您的组织：

- 内容处理：处理合同、工作说明和其他类似表单的文档。 输入表单，训练模型以了解和映射字段，然后运行表单以自动收集数据。 有关详细信息，请参阅 [表单处理概述](form-processing-overview.md)。
- 发票分析：从发票提取相关详细信息，并确保它们符合策略或正在适当处理。

考虑 SharePoint Syntex 可帮助组织的方法：

- 自动化业务流程
- 提高搜索准确度
- 管理合规性风险

### <a name="form-processing-scenario-example"></a>表单处理方案示例

例如，您可以使用 SharePoint 合成和 Power Automate 功能设置一个过程来跟踪和监视发票。

1. 设置用于存储发票文档的库。
1. 训练模型以识别文档中的字段。
1. 将要跟踪的字段提取到列表中。
1. 设置流以针对特定事件通知您，例如：
    - 将添加一个新的发票。
    - 发票已过期。
    - 发票用于大于自动审批金额的金额。

![使用 SharePoint 合成和 Power Automate 跟踪和监视发票](../media/content-understanding/process-invoices-flow.png)

当您自动执行此方案时，您可以：

- 通过自动从发票中提取数据而不是手动提取数据来节省时间和资金。
- 通过使用工作流对发票采取行动并通知您任何问题，减少潜在错误并确保更好的合规性。

### <a name="document-understanding-scenario-example"></a>文档理解方案示例

另一个示例是，您可以设置一个流程来识别贵公司与其他公司或个人的合同。 您可以设置一个模型，以从这些合同中提取关键信息（如客户端名称、费用、日期或其他重要信息）并将其添加到库中作为字段，以便您可以快速查看。 还可以对文档库应用保留标签，以确保在一段特定时间之前无法删除合同，以适当遵守业务法规。

1. 从内容中心开始，为合同创建新的文档理解模型。
1. 上载示例文档，查看正面和负面示例，然后运行培训以确定合同文档并查看结果。
1. 培训提取程序以识别合同中的字段，如客户端名称、费用、日期，然后测试提取程序。
1. 模型完成后，将模型应用到可在其中上载合同库。
1. 将保留标签应用于日期字段，以便合同在库中保留组织需要合同的时间长度。

![使用 SharePoint 合成和保留标签跟踪和监视合同](../media/content-understanding/process-contracts-flow.png)

当您自动执行此方案时，您可以：

- 通过自动从合同中提取数据而不是手动提取数据来节省时间和资金。
- 通过使用保留标签来确保更好的合规性，以确保适当地保留合同。

### <a name="tips-for-identifying-scenarios"></a>用于标识方案的提示

在考虑要考虑哪些业务方案时，请询问自己以下问题：

- 它是否解决了一个实际问题？
- 它将被广泛使用还是具有广泛的影响？
- 是否可获取？
- 能否衡量成功？

根据影响和易于实现确定方案优先级。 使初始焦点区域具有更高的影响，这些应用场景也可以轻松实现。 取消难以实现的影响较低的方案的优先级。

## <a name="identify-roles--responsibilities"></a>确定角色&职责

确定贵组织中谁将构建和管理模型？ 可能涉及以下角色：

| SharePoint/知识管理员 | Power Platform 管理员 | 知识管理器 | 模型所有者 |
|:-------|:-------|:-------|:-------|
| AAD 角色| ADD 角色 | AAD 角色 | 支持者 |
| 配置表单处理 | 配置用于表单处理的常见数据服务环境 | 收集用例 | 收集业务用例 |
| 管理内容中心和权限| 购买和分配 AIB 信用 | 建立最佳做法并查看模型分析 | 创建和应用模型 |

知识管理器、业务流程所有者和内容模型所有者在组织中创建示例模型并推广采用。
可能涉及的其他人：合规性管理员、分类管理员。

他们将在哪里生成和应用模型？ 是否有可以增强的现有流程或存储库？

- 表单处理：确定哪些网站将获取表单处理操作。
- 文档了解：您可以为不同的业务区域创建多个内容中心。

## <a name="strategic-positioning"></a>战略定位

与利益干系人合作，确保他们符合使用 SharePoint 合成器的策略。 研究并提供以下资源来帮助进行此定位：

- 业务结果：
  - 潜在财务结果
  - 潜在的灵活性结果
  - 业务结果模板
- 利益干系人/Exec 发起人购买/调整
  - 业务案例平台
  - 财务模型
  - 公司准备情况 - 文化

## <a name="identify-stakeholders"></a>确定利益干系人

确定项目的利益干系人。

|Role |Responsibilities |Department |
|:-------|:-------|:--------|
| 执行发起 ()    | 向公司传达高级愿景和价值   |  管理层领导   |
| 项目主管 ()  | 监督整个启动执行和推出过程 | 项目管理 |
| 知识管理员| 创建和管理内容中心 | IT 或其他部门|
| 内容管理员和模型所有者| 收集用例并创建和应用模型 | 任何部门|
| 支持者 | 帮助宣传和管理投诉处理 | 任何部门 (员工)  |
| 租户管理员 | 配置租户级设置 | IT 部门|
| Power Platform 管理员| 配置常见数据服务环境 | IT 部门|

> [!Note]
> 尽管我们建议在整个推出过程中完成其中每个角色，但你可能会发现，你无需所有角色都开始使用你确定的解决方案。

## <a name="readiness-checklist"></a>准备情况清单

若要准备好实现 SharePoint 合成，需要：

![内容理解的准备情况](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. 规划结束状态
    - 文档理解模型是方法，而不是结尾。
    - 通过以下方式规划利用提取的元数据的价值：
      - 搜索
      - 筛选和查看格式
      - 合规性
      - 自动化
2. 标识
    - 了解现有信息体系结构和内容管理功能的使用。
    - 任何现有内容类型是否适合模型？
    - 元数据将改进哪些现有进程？
3. 设计
    - 设计信息体系结构、托管元数据和内容类型的方法
    - 设计定义、创建、管理过程。

## <a name="engage-your-organization"></a>参与你的组织

1. 确定持有者、确认方案并制定项目计划。
1. 配置设置并应用许可证。
1. 开始认知和培训 – 招募冠军。
1. 分步推出。  
1. 收集反馈并循环。
1. 随着使用情况增长，根据需要规划任何 AI Builder 信用。
