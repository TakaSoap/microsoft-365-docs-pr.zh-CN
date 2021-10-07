---
title: 运行主题Microsoft Viva试用版
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
ms.localizationpriority: medium
description: 了解如何在组织中计划和运行 Microsoft Viva主题的试用计划。
ms.openlocfilehash: 9e0aff8f2c4ce339af44261becc1b0ebd0a39445
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178715"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a>运行主题Microsoft Viva试用版

本文介绍如何设置和运行试用计划，以将 Viva 主题部署到组织。 本文还推荐了试用版的最佳实践。

## <a name="sign-up-for-a-trial"></a>注册试用版

可从以下来源之一公开提供试用版。 这些试用版为 25 位用户提供 30 天对 Viva 主题的访问权限。

- [Viva 主题产品页](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)

- Microsoft 365 管理中心[](https://admin.microsoft.com)
    1. 登录到 [Microsoft 365 管理中心](https://admin.microsoft.com)。
    2. 转到计费  >  **购买服务**。
    3. 向下滚动到“**加载项**”部分。
    4. 在"**主题体验"** 磁贴上，选择"**详细信息"。**
    5. 选择“**获取免费试用版**”。
    6. 按照其余向导步骤确认试用版。

你必须是全局Microsoft 365或帐单管理员才能激活试用版。

> [!NOTE]
> 只能针对每个租户添加一次公共Microsoft 365试用版。

### <a name="who-should-be-involved-in-a-trial"></a>Who应涉及试用版

|角色|活动|
|---|---|
|Microsoft 365全局管理员或帐单管理员|激活试用版并分配许可证|
|Microsoft 365全局管理员或SharePoint管理员|配置 Viva 主题并创建主题中心|
|业务用户|执行知识管理器、主题参与者和主题使用者角色|

### <a name="before-you-activate-a-trial"></a>激活试用版之前

规划对于有效试用 Viva 主题至关重要。 试用期有限，必须包括主题发现和探索主题质量、管理和最终用户体验。

#### <a name="discovery"></a>发现

在试用期间，主题发现配置有两个高级策略选项：

- 索引所有或大部分联机SharePoint内容。
  - 大型租户最多可能需要两周时间才能完全编制索引。 虽然主题将在这一期间逐步生成，但完全索引可能占用试用期的一半。
  - 对于具有大量数据的租户，此选项可生成大量主题，可能数万个。

- 标识要编制索引SharePoint网站子集。

选择这些策略是在以下两个因素之间取得平衡：

- 具有足够的数据以生成有意义的主题。 Viva 主题中的 AI 经过调整，适用于大型数据集，最好是包含 10，000 多个文档的大型数据集。
- 在试用期内未生成太多主题，因此在可用时段内评估主题非常难以避免。

对于大多数组织，第二个策略可产生最佳结果。

> [!NOTE]
> 由于 AI 需要的文档数量，我们建议你在生产租户上运行 Viva 主题试用版。 这一期间不会影响租户的性能。 只有拥有试用版许可证的用户才能访问 Viva 主题用户体验。

#### <a name="roles"></a>角色

在试用期间，有三个角色必须处于活动状态，如下表所述。

|角色|活动|
|---|---|
|知识经理|控制主题的生命周期阶段;确认并删除主题;充当主题参与者的社区管理员|
|主题参与者|内容主题专家，可以：<br> 查看评估 AI 定义的内容质量的主题<br>使用附加内容来特展发现的主题<br>创建 AI 未发现的其他主题|
|主题使用者|通过页面突出显示和搜索使用主题<br>提供对所展示主题的价值的反馈|

#### <a name="expected-topics"></a>预期主题

记录预期由 AI 生成的主题会很有用，即使这仅基于假设。 为定义子集编制索引时，此任务SharePoint可以轻松地识别其 SMES。

拥有记录的列表将帮助你：

- 查看 AI 生成的主题列表，该列表可能大于预期。
- 了解可能需要手动创建的主题或需要优先处理的主题。

在成功部署或试用 Viva 主题时，始终需要混合使用 AI 定义的主题和人为创建的主题。

## <a name="activate-a-trial"></a>激活试用版

启动试用版时，需要：

- 将许可证分配给相关用户。
- 执行 [Viva 主题](set-up-topic-experiences.md) 的其他设置。

激活试用版后，主题发现过程将开始。

## <a name="during-a-trial"></a>试用期间

该试用期应该用于评估 Viva 主题的以下组件：

- AI 建议的主题和主题内容
- 最终用户体验，在新式页面和SharePoint上显示主题Microsoft 搜索

请考虑以下因素：

- 若要使 Viva 主题提供最大值，主题中的内容需要组合 AI 定义的内容和人工设置的内容。
- 所有用户体验都经过"权限修整" (包括知识经理在"管理主题" **页上的**) 。 只有在用户有权查看用于生成该主题的一些资源时，他们才能看到主题。 这意味着不同的用户可能会在同一主题页面上看到不同的内容。
- 用户可能会看到多个主题在"管理主题"页 **中具有相同的** 名称。 这些主题不一定重复，但可能是由于在数据的多个上下文中使用的单个术语，例如两个不同的项目使用的项目代码名称。

## <a name="after-a-trial"></a>试用后

根据试验结果，您可以决定是否继续生产使用 Viva 主题。

### <a name="proceed-to-production-use"></a>继续生产使用

为了确保服务的连续性，必须购买所需数量的许可证，并将这些许可证分配给用户。 试用期结束时没有完整许可证的试用版用户将无法访问任何 Viva Topics 体验。

### <a name="dont-proceed-to-production-use"></a>不要继续生产使用

如果你在试用后不购买许可证：

- 主题发现将停止。
- 用户将不再看到主题突出显示或卡片。
- 不会删除主题中心，但建议的主题和管理主题体验将不可用。
- 任何 AI 定义的主题都将丢失。
- 主题参与者编辑的主题将保留在主题中心页面库中。 仅手动提供的内容将保留在这些页面上，不会保留任何 AI 建议的内容。

## <a name="see-also"></a>另请参阅

[开始推动采用 Microsoft Viva 主题](topics-adoption-getstarted.md)
