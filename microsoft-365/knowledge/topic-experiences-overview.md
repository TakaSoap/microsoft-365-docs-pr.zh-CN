---
title: Microsoft Viva 主题概述
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Viva 主题概述。
ms.openlocfilehash: 91442ba12b3d5df1d9934022751f4bc381cd40e8
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453965"
---
# <a name="microsoft-viva-topics-overview"></a>Microsoft Viva 主题概述 

Viva 主题使用 Microsoft AI 技术、Microsoft 365、Microsoft Graph、搜索和其他组件和服务，从 SharePoint 新式页面和 Microsoft 搜索开始，为用户提供他们日常使用的 Microsoft 365 应用中的知识。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Viva 主题可帮助解决许多公司中的一个关键业务问题 -在用户需要信息时提供相关信息。 例如，新员工需要快速了解大量新信息，在阅读公司信息时会遇到他们不知道的术语。 若要了解详细信息，用户可能需要离开自己正在执行的内容，并花费宝贵的时间搜索详细信息，例如有关术语内容的信息、组织中谁是主题专家，以及可能与术语相关的网站和文档。

Viva 主题使用 AI 自动搜索和 **标识组织中** 的主题。 它编译有关它们的信息，例如简短说明、处理主题的人，以及网站、文件和与主题相关的页面。 知识经理或参与者可以选择根据需要更新主题信息。 这些主题可供用户使用，这意味着对于新闻和页面中新式 SharePoint 网站中显示的主题每个实例，文本将突出显示。 用户可选择选择主题，通过主题详细信息了解有关该主题的详细信息。 还可以在 SharePoint 搜索中查找主题。


## <a name="how-topics-are-displayed-to-users"></a>如何向用户显示主题

当 SharePoint 新闻和页面上的内容中提到主题时，你将看到它突出显示。 可以从突出显示部分打开主题摘要。 打开摘要标题中的主题详细信息。 上述主题可以自动标识，或者已添加到页面，页面作者直接引用了该主题。 

   ![主题要点](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>知识索引

Viva 主题使用 Microsoft AI **技术识别** Microsoft 365 环境中的主题。

主题是组织重要或重要的短语或术语。 它对于组织具有特定的含义，并且具有相关资源，可帮助用户了解它是什么，并查找有关它的信息。 有很多不同类型的主题对组织非常重要。 最初，Microsoft AI 技术侧重于以下类型：
- Project
- 事件
- 组织
- 位置
- 产品
- 创意工作
- 研究领域


当主题被标识且 AI 确定它有足够的信息成为建议的主题时，主题页将显示通过主题索引收集的信息，例如：

- 备用名称和首字母缩写。
- 主题的简短说明。
- 可能熟悉此主题的人。
- 与主题相关的文件、页面和网站。

知识管理员可以选择对租户中所有 SharePoint 网站进行主题爬网，或仅选择特定主题。

请参阅 [主题发现和策展](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)

## <a name="roles"></a>角色

在 Microsoft 365 环境中使用 Viva 主题时，用户将具有以下角色：

- 主题查看者：可以在至少具有读取访问权限的 SharePoint 新式网站和 Microsoft搜索中查看主题突出显示的用户。 他们可以选择主题突出显示以查看主题页面中的主题详细信息。 主题查看者可以提供有关主题对用户有用的反馈。

- 参与者：具有编辑现有主题或创建新主题权限的用户。 知识管理员通过 Microsoft 365 管理中心中的 Viva 主题设置向用户分配参与者权限。 请注意，还可以选择授予所有主题查看者编辑和创建主题的权限，以便每个人都可以参与他们看到的主题。

- 知识经理：在主题生命周期中指导主题的用户。 知识经理使用主题中心中的"管理主题"页确认 AI 建议的主题、删除不再相关的主题，以及编辑现有主题或创建新主题，并且是唯一有权访问它的用户。 知识管理员通过 Microsoft 365 管理中心中的 Viva 主题管理员设置向用户分配知识管理器权限。 

- 知识管理员：知识管理员设置 Viva 主题并通过 Microsoft 365 管理中心中的管理员控件进行管理。 目前，Microsoft 365 全局管理员或 SharePoint 管理员可以充当知识管理员。

有关详细信息 [，请参阅 Viva](topic-experiences-roles.md) 主题角色。

## <a name="topic-management"></a>主题管理

主题管理在组织 **的主题中心的"** 管理主题" **页中完成**。 主题中心是在设置期间创建的，并充当组织的知识中心。 

虽然所有许可用户都可以在主题中心查看他们连接的主题，但只有具有管理主题权限 (知识经理) 才能查看和使用"管理主题"页。

知识经理可以：

- 确认或删除在租户中发现的主题。
- 根据需要手动创建新主题 (例如，如果提供的信息不足，无法通过 AI) 。
- 编辑现有主题页面。</br>

有关详细信息 [，请参阅主题中心中的](manage-topics.md) "管理主题"。  


## <a name="admin-controls"></a>管理控件

Microsoft 365 管理中心中的管理控件允许你管理知识网络。 它们允许 Microsoft 365 全局管理员或 SharePoint 管理员：

- 控制允许组织中哪些用户查看 SharePoint 新式页面或 SharePoint 搜索结果中的主题。
- 控制将爬网哪些 SharePoint 网站以标识主题。
- 排除找到的特定主题。
- 控制哪些用户可以在主题中心管理主题。
- 控制哪些用户可以创建和编辑主题。
- 控制哪些用户可以查看主题。

有关[管理员控件的详细信息，请参阅](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions)分配用户权限、[管理主题可见性](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)和管理主题发现。 [](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery)

## <a name="topic-curation--feedback"></a>主题&反馈

当环境中发生更改时，AI 将持续努力提供改进主题的建议。 

具有编辑或创建主题权限的用户如果要更正或添加其他信息，可以直接对主题页面进行更新。 他们还可以添加 AI 无法识别的新主题。 如果这些手动添加的主题信息足够多，并且 AI 能够识别这种类型的主题，则来自 AI 的其他建议可能会增强这些手动添加的主题 

可能会询问允许其访问以查看其日常工作中的主题的用户是否对主题有用。 系统会查看这些响应，并使用它们改进主题突出显示，并帮助确定主题摘要和主题详细信息中显示的内容。

此外，具有适当权限的用户可以标记与主题相关的项目（如 Yammer 对话）并将其添加到特定主题。 

请参阅 [主题发现和策展](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)


## <a name="see-also"></a>另请参阅

