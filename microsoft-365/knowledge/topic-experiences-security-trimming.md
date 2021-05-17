---
title: Microsoft Viva 主题安全修整
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: 如何使用安全性查看主题的概述。
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939619"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Microsoft Viva 主题安全修整 

Viva 主题用户无法查看主题中他们现有的Office 365权限阻止他们查看的信息。 用户在主题页面上看到的所有内容 (例如，SharePoint网站、文档) 文件将是他们已被允许查看的信息。 Viva 主题不更改任何现有权限。

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>为什么两个用户对同一主题可能有不同的视图

当通过 AI 或手动选择创建主题时，它可以包含主题描述、替代名称、与主题关联的人员，以及与该主题相关的网站、页面和文件。 在主题页面上查看此信息时，查看同一主题的两个用户可能看不到相同的信息。
  
例如，当用户 1 查看 Neptune 主题页面时，他们可能会看到主题页面的此视图。

![用户 1 的 Neptune 主题](../media/knowledge-management/user2-topic-view.png) </br> 

但是，当用户 2 查看同一 Neptune 主题页时，其视图与用户 1 不同。  用户 2 可以在主题页面的"固定的文件和页面"部分查看 *DG-2000 产品* 概述文件，该文件不会为用户 1 显示。  

![用户 2 的 Neptune 主题](../media/knowledge-management/user1-topic-view.png) </br> 

用户在同一主题上看到的内容的不同之处在于，用户可能Office 365查看相关站点或文件的权限。  Viva 主题遵守对主题中的项目设置的权限，并且无法更改对它们的访问权限。 在我们的示例中，用户 1 无法查看 Neptune 的主题页中的 *DG-2000 产品* 概述文件，因为用户 1 Office 365查看该文件的权限。

如果用户无法查看主题中的足够信息，因此该主题将不可用。 发生这种情况时，用户将看不到突出显示的主题。 另一个拥有主题中更多信息的权限的用户将能够查看该主题。


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>知识经理和主题参与者的主题权限

分配了主题管理权限的用户（知识管理员）只能查看他们有权在主题内查看的信息。

同样，具有创建和编辑主题权限的用户（主题参与者）将只能查看他们有权在主题内查看的信息。 


## <a name="ai-versus-manually-curated-topic-information"></a>AI 与手动选择的主题信息

主题可以包含 AI 生成的信息以及由主题参与者或知识管理员添加或编辑的信息。

 - AI 添加的主题中的信息仅对有权访问源内容的人可见。
 - 主题参与者或知识经理手动添加或编辑的主题说明和人员信息对可以看到该主题的每个人可见。
 - 文件、页面和网站仅对具有源内容权限的用户可见，无论是手动添加还是由 AI 添加。

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

