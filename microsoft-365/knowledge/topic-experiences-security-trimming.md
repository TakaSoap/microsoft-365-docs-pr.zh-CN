---
title: 安全修整Microsoft Viva主题
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ms.localizationpriority: medium
description: 了解如何使用安全性查看 Viva 主题中的主题。
ms.openlocfilehash: babf5cf6179df18bdf9f2cc1d68e5a6ed4b6b772
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214017"
---
# <a name="security-trimming-in-microsoft-viva-topics"></a>安全修整Microsoft Viva主题

Viva 主题用户无法查看主题中他们现有的Office 365权限阻止他们查看的信息。 用户在主题页上看到的所有内容（例如 SharePoint 网站、文档、文件）都将是已允许其查看的信息。 Viva Topics 不更改任何现有权限。

## <a name="why-two-users-might-have-different-views-of-the-same-topic"></a>为什么两个用户对同一主题可能有不同的视图

通过 AI 或手动策展创建主题时，可包含主题说明、替代名称、与主题关联的人员，以及与主题相关的网站、页面和文件。 在主题页面上查看此信息时，查看同一主题的两个用户可能看不到相同的信息。
  
例如，当用户 1 查看 Neptune 主题页面时，他们可能会看到该主题页面的此视图。

![用户 1 的 Neptune 主题。](../media/knowledge-management/user2-topic-view.png) </br> 

但是，当用户 2 查看同一 Neptune 主题页时，其视图与用户 1 不同。  用户 2 可以在主题页面的"固定的文件和页面"部分查看 *DG-2000 产品* 概述文件，该文件不会为用户 1 显示。  

![用户 2 的 Neptune 主题。](../media/knowledge-management/user1-topic-view.png) </br> 

用户可以在同一主题上看到的内容的区别在于，用户可能Office 365查看相关站点或文件的权限。  Viva 主题遵守对主题中的项目设置的权限，并且无法更改对它们的访问权限。 在我们的示例中，用户 1 无法查看 Neptune 的主题页中的 *DG-2000 产品* 概述文件，因为用户 1 Office 365查看该文件的权限。

如果用户无法查看主题中的足够信息，因此该主题将不可用。 发生这种情况时，用户将看不到突出显示的主题。 对主题中有用的详细信息具有权限的其他用户则将能够看到该主题。


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>知识经理和主题参与者的主题权限

分配了主题管理权限的用户（知识管理员）只能查看他们有权在主题内查看的信息。

同样，具有创建和编辑主题权限的用户（主题参与者）将只能查看他们有权在主题内查看的信息。 


## <a name="ai-versus-manually-curated-topic-information"></a>AI 与手动策展的主题信息

主题可以包含 AI 生成的信息以及由主题参与者或知识管理员添加或编辑的信息。

 - 主题中由 AI 添加的信息仅对具有对该源内容访问权限的人员可见。
 - 主题参与者或知识经理手动添加或编辑的主题说明和人员信息对可以看到该主题的每个人可见。
 - 文件、页面和网站仅对有权查看源内容的用户可见，无论是手动添加还是由 AI 添加。

下表介绍了哪些用户（主题查看者、参与者和知识管理员）可以基于其权限在给定主题中查看。

|主题项|用户可以看到的内容|
|:---------|:------------------|
|主题名称|用户可以在主题中心查看主题的主题名称。 如果用户对源内容没有权限或与用户相关性较低，则某些主题可能不可见。|
|主题描述|AI 生成的描述仅对具有源内容权限的用户可见。 手动输入或编辑的描述对所有用户可见。|
|人员|固定的人员对所有用户可见。 建议的人员仅对具有源内容权限的用户可见。|
|文件|文件仅对具有源内容权限的用户可见。|
|页面|页面仅对具有源内容权限的用户可见。|
|网站|网站仅对具有源内容权限的用户可见。|




## <a name="see-also"></a>另请参阅

