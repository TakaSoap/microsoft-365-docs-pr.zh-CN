---
title: Microsoft 合规性管理器发行说明
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
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: c988a727bc48a5b27146168a66a0831c9b57b216
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806685"
---
# <a name="release-notes-for-compliance-manager-preview"></a>合规性管理器的发行说明（预览）

合规性管理器的公共预览版为您提供早期访问即将推出的功能和更新。

您可以使用[服务信任门户](https://servicetrust.microsoft.com)上的更新的[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)工具来跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。

## <a name="whats-new-in-compliance-manager-preview"></a>合规性管理器中的新增功能（预览）

- **基于角色的对合规性管理器的访问：** 已删除默认的**来宾访问**角色。 为使用户能够访问合规性管理器，全局管理员必须为[每个用户分配一个权限](compliance-manager-overview.md#permissions)。

- **更新的合规性分数**：合规性分数现在包括 Microsoft 管理的操作的分数。 因此，你的分数将增加。

- **Actions 项：** 操作项现在是单个项目，并且许多包含来自 Microsoft 安全分数图形 API 的遥测集合。 在可能的情况下，技术操作建议现在有指向 Office 365 服务中适用配置页面的链接。

- **租户管理：** 用于管理合规性管理器中的新数据元素的新界面（预览）：
    - **维：** 查看、添加和自定义模板、评估和操作项的元数据，以允许您为筛选器创建自定义透视。
    - **所有者：** 为每个即席项目指定一个所有者。
    - **客户操作：** 管理合规性管理器（预览版）中包含的操作项的完整列表，并启用/禁用与安全得分集成的操作项的安全分数监视。

## <a name="known-issues-in-compliance-manager-preview"></a>合规性管理器中的已知问题（预览）

以下各节介绍了即将在即将发布的合规性管理器中解决的已知问题。

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

### <a name="microsoft-managed-controls"></a>Microsoft 托管控件

- Microsoft 托管控件的测试日期不会显示在 UI 中，即使在评估中也不会如此。 若要查看测试日期信息，必须导出该评估。

### <a name="customization"></a>自定义

- 通过添加自定义控件，可以向现有控件系列添加新控件，但不允许您添加新的控件系列。
- 此版本不支持链接操作项，也不能向评估添加操作项或控件。
- 如果创建自定义操作，则不能对其进行编辑或将其删除。

### <a name="control-families-not-shown-in-assessments"></a>控制系列未在评估中显示

- 导入模板时，基于该模板的所有评估都会反映属于该模板的所有控制系列。 但是，如果向模板中添加新的控制系列，则任何现有评估都不会反映这些更改。 仅由更新后的模板创建的新评估将反映所做的更改。

### <a name="templates"></a>模板

- 创建模板时，您必须包括**产品**和**证书**的维度，以确保您的模板在合规性分数中显示。
- 存档的模板是可编辑的，不应是可编辑的。
- 锁定的模板允许在不应进行评估时创建评估。 锁定模板旨在防止它用于创建评估。

### <a name="export"></a>导出

- 将模板状态设置为 "已**导入**" 或 "**待审批**" 时，模板导出到 JSON 失败。

### <a name="supported-browsers"></a>支持的浏览器

- Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。
- 在刷新浏览器之前，可能会出现更新数据未显示的实例。
- Microsoft Edge 的预览版本不受支持，但没有已知问题。
- 不支持 Internet Explorer。

### <a name="session-timeout"></a>会话超时

- 会话超时时，可能会出现 "发生错误" 错误。 若要解决此问题，请转到[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)，然后重新登录。
 
### <a name="language-support"></a>语言支持

- 并非所有网页都支持所有语言。 如果本地语言不受支持，请在美国英语中查看。