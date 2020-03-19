---
title: Microsoft 合规性分数更新
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
description: 有关 Microsoft 合规性分数未来更新的详细信息（预览），M365 合规性中心中的一项功能，可帮助简化和自动化风险评估。
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857753"
---
# <a name="microsoft-compliance-score-preview-updates"></a>Microsoft 合规性分数（预览）更新

 本文提供有关[Microsoft 合规性分数](compliance-score.md)和[Microsoft 合规性管理器](compliance-manager-overview.md)未来更新的详细信息。 了解有关其[关系](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)的详细信息。

## <a name="improved-template-creation-and-update-processes"></a>改进的模板创建和更新过程

我们正在简化导入、导出和修改用于评估的模板的过程。 全新体验使你能够更轻松地将自己的评估引入到合规性分数，并使其保持更新。

### <a name="the-current-process"></a>当前进程

有两种方法可以在合规性管理器中创建模板。 您可以复制现有模板，也可以将模板数据从 Excel 电子表格导入到新模板中。 从 "**模板**" 页中，选择 " **+ 添加模板**" 以创建新的模板，方法是输入名称，选择 "维度"，然后上传具有特定格式和架构的 Excel 文件。 或者，您可以选中 "**从现有模板复制**" 框，选择要复制的模板并验证尺寸，如下图所示。 自定义模板需要一个[多步骤过程](working-with-compliance-manager.md#templates)，该过程首先选择创建模板之后的 "**添加自定义控件**"。

![合规性分数-仪表板](../media/compliance-score-template-update-old.png "当前模板复制过程")

### <a name="whats-changing"></a>更改内容

我们正在让你更轻松地创建新模板。 在单步**扩展**过程中，可以将包含操作和控件的电子表格添加到现有的 Microsoft 模板中，以生成自己的自定义版本。 在 "**模板**" 浮出控件窗格中，选择 "**从共用模板创建扩展**" 复选框，如下图中所示。 然后，您将使用一种新的 Excel 格式来添加自定义项，该格式不是当前的复杂格式。 此新进程将替换**现有模板中**的当前副本并**添加自定义控件**函数。

每次通过以下概述的版本控制过程更新最初的评估时，您的自定义评估将继承这些更新并保留您的自定义控件。

此外，我们还使您可以更轻松地修改您自己的现有模板。 您可以导出模板，在同一工作簿中进行更改，然后在保存编辑内容后将其导入。

![合规性分数-仪表板](../media/compliance-score-template-update-new.png "新模板创建过程")

## <a name="versioning-notice-and-control"></a>版本控制通知和控制

您的组织将在下一版本的合规性分数和合规性管理器中接收更新的评估，以帮助您与认证和法规更新保持一致。

今后，只要有更新可用于评估模板或改进操作，警报图标都会通知您更新已准备就绪。 当您单击该图标时，将弹出一个窗口，说明更新并提示您接受。 下面是针对评估的版本控制警报的一个示例：

![合规性分数-版本控制警报](../media/compliance-score-assessment-version.png "评估版本更新警报")

选择警报图标可显示一个弹出窗格，其中介绍了更新并提示您接受：

![合规性分数-版本化飞出](../media/compliance-score-assessment-version-accept.png "评估更新确认窗格")

## <a name="common-actions-will-synch-status-across-groups"></a>常见操作将同步组之间的状态

如果您的组织具有多个评估组，**技术**操作的行为（即影响整个组织的操作）将会发生变化。 跨组的任何重复操作将合并为一个单个操作。 该单个操作将包含重复版本中所有已上载的笔记和证据。 进行此更改后，技术操作将表现为属于同一组时的当前操作。 现在，在一个组或评估中对操作所做的任何更改都将反映在所有实例中。  **实现状态**、**实现 Dat**、**测试状态**和**测试日期** 将反映最新的更新。

## <a name="language-support"></a>语言支持

由于英语：简体中文、中文（繁体）、法语、德语、意大利语、日语、朝鲜语、葡萄牙语（巴西）、俄语和西班牙语，以下语言中现在还提供了合规性分数。
