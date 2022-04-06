---
title: 开始推动采用 Microsoft SharePoint Syntex
description: 了解如何在组织中使用和实施SharePoint Syntex，以帮助简化业务流程。
ms.author: chucked
author: chuckedmonson
manager: pamgreen
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
ms.openlocfilehash: 40af6061029785705d262f3b8c5134531e76885f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467634"
---
# <a name="get-started-driving-adoption-of-microsoft-sharepoint-syntex"></a>开始推动采用 Microsoft SharePoint Syntex

将企业提供的智能内容服务SharePoint Syntex三个部分：

- **内容了解：** 创建无代码 AI 模型以对内容进行分类和提取信息，以自动应用元数据进行知识发现和重用。 详细了解内容 [理解](document-understanding-overview.md)。
- **内容处理：** 自动捕获、获取和分类内容，并简化使用 Power Automate 以内容为中心的Power Automate。 详细了解内容 [处理](form-processing-overview.md)。
- **内容合规性：** 控制和管理内容，以改进安全性和管理，并集成Microsoft 信息保护。

借助新的 AI 服务和功能，你可以直接将内容理解和分类应用构建到内容管理流中，SharePoint Syntex。 有两种不同的内容理解方式。 使用的模型类型基于文件格式和用例。

| 表单处理 | 文档理解 |
|:-------|:-------|
| 从文档库创建。 | 在内容中心内创建，属于SharePoint Syntex。 |
| 在 AI 生成器中创建的模型。 | 在本机接口中创建的模型。 |
| 用于半结构化文件格式。 | 用于非结构化文件格式。 |
| 可设置的分类器。 | 带可选提取器、可训练分类器。 |
| 仅限于单个库。 | 可应用于多个库。 |
| 培训 PDF、JPG、PNG 格式，总计 50 MB/500 pp。 | 培训 5-10 个 PDF、Office 或电子邮件文件，包括反面例子。 |

有关功能的更完整比较，请参阅文档理解 [与表单处理模型的区别](difference-between-document-understanding-and-form-processing-model.md)。

## <a name="identify-pilot-business-scenarios-to-optimize"></a>确定要优化的试点业务方案

若要准备在SharePoint Syntex中使用应用程序，首先需要了解它非常有用的方案。 "原因"可帮助确定需要哪种模型，以及如何根据将应用模型的地方来构建组织。 下面是一些文档理解可帮助您的组织的方案：

- **内容处理：** 处理合同、工作声明和其他类似表单的文档。 输入表单，训练模型以了解和映射字段，然后运行表单以自动收集数据。 有关详细信息，请参阅表单 [处理概述](form-processing-overview.md)。
- **发票分析：** 从发票中拉出相关详细信息，并确保它们符合策略或正在适当处理。

考虑一下SharePoint Syntex组织的方式：

- 自动化业务流程
- 提高搜索准确度
- 管理合规性风险

在思考要考虑哪些业务方案时，请询问自己以下问题：

- 它是否解决了真正的问题？
- 它将被广泛使用还是具有广泛的影响？
- 它是否可获取？
- 能否衡量成功？

根据影响和实现方便性确定方案优先级。 使初始的重点关注区域具有更高的影响，并且可以轻松实现这些方案。 取消难以实现的影响较低的方案的优先级。

使用[示例方案和用例来](adoption-scenarios.md)提示有关如何在组织中使用SharePoint Syntex的想法。

## <a name="identify-roles--responsibilities"></a>确定角色&职责

确定贵组织中将构建和管理模型的人。 可能会涉及以下角色。

| SharePoint/知识管理员 | Power 平台管理员 | 知识经理 | 模型所有者 |
|:-------|:-------|:-------|:-------|
| AAD角色| AAD角色 | AAD角色 | 支持者 |
| 配置表单处理 | 配置 Dataverse 环境以用于表单处理 | 收集用例 | 收集业务用例 |
| 管理内容中心和权限| 购买和分配 AIB 信用额度 | 建立最佳做法并查看模型分析 | 创建和应用模型 |

知识经理、业务流程所有者和内容模型所有者在组织中创建示例模型和采用者。
可能涉及的其他人：合规性管理员、分类管理员。

他们将在哪里生成和应用模型？ 是否有可以增强的现有流程或存储库？

- 表单处理：确定哪些网站将获取表单处理操作。
- 文档了解：您可以为不同的业务区域创建多个内容中心。

## <a name="strategic-positioning"></a>战略定位

与利益干系人合作，确保他们符合使用 SharePoint Syntex。 研究和提供以下资源来帮助实现此定位：

- 业务成果：
  - 潜在的财务结果
  - 潜在的灵活性结果
  - 业务结果模板
- 利益干系人/Exec 发起人购买/调整
  - 业务案例平台
  - 财务模型
  - 公司准备情况 - 文化

## <a name="identify-stakeholders"></a>确定利益干系人

确定你的项目的利益干系人。

|角色 |责任 |部门 |
|:-------|:-------|:--------|
| 执行发起 ()    | 向公司传达高级别愿景和价值   |  行政领导   |
| Project潜在客户 ()  | 监督整个启动执行和推广流程 | 项目管理 |
| 知识管理员| 创建和管理内容中心 | IT 或其他部门|
| 内容管理者和模型所有者| 收集用例并创建和应用模型 | 任何部门|
| 支持者 | 帮助宣传和管理异议处理 | 任何部门（员工） |
| 租户管理员 | 配置租户级别设置 | IT 部门|
| Power 平台管理员| 配置 Dataverse 环境 | IT 部门|

> [!NOTE]
> 尽管我们建议在部署过程中完成其中每个角色，但你可能会发现，你无需全部开始使用你确定的解决方案。

## <a name="readiness-checklist"></a>准备情况清单

若要准备好实现SharePoint Syntex，您需要：

![内容理解的准备情况。](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. 规划结束状态
    - 文档理解模型是方法，而不是结尾。
    - 规划利用提取的元数据的价值，包括：
      - 搜索
      - 筛选和查看格式
      - 合规性
      - 自动化
2. 标识
    - 了解现有信息体系结构和内容管理功能的使用。
    - 任何现有内容类型是否适合模型？
    - 元数据将改进哪些现有进程？
3. 设计
    - 设计信息体系结构、托管元数据和内容类型的方法。
    - 设计定义、创建、管理过程。

## <a name="engage-your-organization"></a>参与你的组织

1. 确定持有者、确认方案以及制定项目计划。
1. 配置设置并应用许可证。
1. 开始认知和培训 – 招募冠军。
1. 分步推出。  
1. 收集反馈并循环。
1. 随着使用情况的扩大，可根据需要规划任何 AI 生成器信用额度。

## <a name="see-also"></a>另请参阅

[SharePoint Syntex 的应用场景和用例](adoption-scenarios.md)

[使用 Microsoft 365 解决方案管理合同](solution-manage-contracts-in-microsoft-365.md)
