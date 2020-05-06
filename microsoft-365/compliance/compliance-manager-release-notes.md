---
title: Microsoft 合规性管理器发行说明
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
ms.custom:
- seo-marvel-mar2020
description: 查看发行说明，其中包含有关在 Microsoft 合规性管理器中的新功能和已知问题（要在即将推出的版本中解决）的信息。
ms.openlocfilehash: fb462939ef1b1bf0c6f7f4552359d50645b528f3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033702"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a>Microsoft 合规性管理器（预览）发行说明

合规性管理器的公共预览版为您提供早期访问即将推出的功能和更新。 此页面包含有关当前版本的新功能、改进功能和已知问题的更新。

您可以使用[服务信任门户](https://servicetrust.microsoft.com)上的[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)工具来跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。

## <a name="improved-template-creation-and-update-process"></a>改进的模板创建和更新过程

我们已经更新了导入、导出和修改用于评估的模板的过程。 全新的简化体验使您能够更轻松地将自己的评估引入工作流并将其更新。

### <a name="the-old-process"></a>旧进程

在合规性管理器中创建模板的方法有两种。 您可以复制现有模板，或将模板数据从 Excel 电子表格导入到新模板中。 在 "**模板**" 页上，选择 " **+ 添加模板**" 以创建新模板，方法是输入名称，选择 "维度"，然后上传具有特定格式和架构的 Excel 文件。 或者，您可以选中 "**从现有模板复制**" 框，选择要复制的模板，然后验证维度。 设计自定义模板需要一个多步骤过程，该过程是在创建模板后选择 "**添加自定义控件**" 开始执行的。

### <a name="the-new-process"></a>新进程

我们使您能够更轻松地创建新模板。 在单步**扩展**过程中，可以将包含操作和控件的电子表格添加到现有的 Microsoft 模板中，以生成自己的自定义版本。 在合规性管理器的 "**模板**" 页上，选择 " **+ 添加模板**"。 在 "**模板**" 浮出控件窗格中，选中 "**从全局模板创建扩展**" 复选框。 您可以使用比以前更复杂的新 Excel 格式添加自定义项。 此新进程将替换**现有模板中**的前一副本并**添加自定义控件**函数。

每次通过以下概述的版本控制过程更新最初的评估时，您的自定义评估将继承这些更新并保留您的自定义控件。

此外，还可以更轻松地修改您自己的现有模板。 您可以导出模板，在同一工作簿中进行更改，然后在保存编辑内容后将其导入。

查看有关使用此新过程[创建模板](working-with-compliance-manager.md#templates)的详细说明。

## <a name="versioning-notice-and-control"></a>版本控制通知和控制

您的组织在2020年4月发布的合规性管理器中收到更新的评估，以帮助您与认证和法规更新保持一致。 向前发展，我们将为你提供一个清楚的方法，以便你了解并接受通过**版本控制警报**的所有未来更新。

只要有更新可用于评估模板或改进操作，警报图标都会通知您更新已准备就绪。 当您单击该图标时，将弹出一个窗口，说明更新并提示您接受。 选择警报图标可显示一个弹出窗格，该窗口说明更新并提示您接受。 了解有关[接受评估更新](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates)的详细信息。

## <a name="common-actions-will-synch-status-across-groups"></a>常见操作将同步组之间的状态

如果您的组织具有多个评估组，**技术**操作（即影响整个组织的操作）的行为已发生更改。 跨组的任何重复操作都已合并到一个单一操作中。 该单个操作包含所有已上载的笔记和来自重复版本的证据。 进行此更改后，技术操作现在的行为与它们属于同一组时的行为相同。 现在，在一个组或评估中对操作所做的任何更改都将反映在所有实例中。 **实现状态**、**实现日期**、**测试状态**和**测试日期**将反映最新的更新。

## <a name="language-support"></a>语言支持

合规性管理器现已提供以下语言版本，除了英语：简体中文、中文（繁体）、法语、德语、意大利语、日语、朝鲜语、葡萄牙语（巴西）、俄语和西班牙语。

## <a name="known-issues-in-compliance-manager-preview"></a>合规性管理器中的已知问题（预览）

以下部分介绍了当前版本的合规性管理器中的已知问题。

### <a name="dimension-values"></a>维度值

由于数据迁移在2020年4月的版本中，一些组织可能会在其评估和模板中看到**产品**或**证书**值 "custom"。 如果 "**产品**" 或 "**证书**" 字段为空，则会自动插入此值，并且不会对数据工作流产生影响。

### <a name="compliance-score"></a>合规性分数

- 对于标记为**不在范围**内的措施项，分配给该措施项的分数不会从合规性分数计算中排除。 标记为**不在范围内的**操作项不会增加合规性分数。

### <a name="secure-score"></a>安全功能分数

- 安全分数结果不适用于某些 Microsoft 365 和 Office 365 订阅中的某些操作项。 在这些情况下，**无法检测到**安全分数结果。
- 有时，不完成相应策略和操作项目的安全分数结果。
- 对于新租户，将自动打开所有操作的安全得分更新。 全局管理员可以将 "安全分数连续更新" 开关设置为 "关闭"，这将关闭所有操作的更新。
  - **注意**：当组织首次部署 Microsoft 365 或 Office 365 时，将需要大约7天的时间来完全收集数据，并将其划分到你的成绩中。 在这段时间内，将安全分数连续更新开关设置为**Off**并手动设置要**实现**的操作，则会将该操作计为成绩。 在最初的七天之后，将安全分数连续更新打开将启用从该点继续进行监视。
- 如果启用了安全分数更新，尽管操作的测试日期不会更新以反映监控情况，但这些操作将积极受到安全分数的监控。
- 在创建新的评估时，分数将自动包含 Microsoft 托管的控制得分和安全得分集成。
- 安全分数集成不支持的任何操作都可以手动实现。 手动实现将考虑该操作的组的分数。

### <a name="export"></a>导出

- 将模板状态设置为 "已**导入**" 或 "**待审批**" 时，模板导出到 JSON 失败。

### <a name="supported-browsers"></a>支持的浏览器

- Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。
- 在刷新浏览器之前，可能会出现更新数据未显示的实例。
- Microsoft Edge 的预览版本不受支持，但没有已知问题。
- 不支持 Internet Explorer。

### <a name="session-timeout"></a>会话超时

- 会话超时时，可能会出现 "发生错误" 错误。 若要解决此问题，请转到[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)，然后重新登录。
