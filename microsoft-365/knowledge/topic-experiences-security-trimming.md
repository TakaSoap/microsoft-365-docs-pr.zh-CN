---
title: '主题体验安全修整 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 如何使用安全性查看主题的概述。
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698814"
---
# <a name="topic-experiences-security-trimming-preview"></a>主题体验安全修整 (预览) 

> [!Note] 
> 本文中的内容适用于 Project Cortex 专用预览版。 [了解更多关于 Project Cortex的信息](https://aka.ms/projectcortex)。

主题体验用户将无法查看其现有 Office 365 权限阻止他们查看的主题信息。 用户在主题页面上看到的所有内容 (例如，SharePoint 网站、文档) 文件将是他们已允许查看的信息。 主题体验不会更改任何现有权限。

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>为什么两个用户对同一主题可能有不同的视图

通过 AI 或手动选择创建主题时，该主题可以包含主题说明、替代名称、与主题关联的人员，以及与该主题相关的网站、页面和文件。 在主题页面上查看此信息时，查看同一主题的两个用户可能看不到相同的信息。
  
例如，当用户 1 查看 Neptune 主题页面时，他们可能会看到该页面。

![用户 1 的 Neptune 主题](../media/knowledge-management/user2-topic-view.png) </br> 

但是，当用户 2 查看同一 Neptune 主题页时，她的视图与用户 1 不同。  用户 2 能够在主题页的"固定文件和页面"部分查看 *DG-2000 产品* 概述文件，该文件不会为用户 1 显示。  

![用户 2 的 Neptune 主题](../media/knowledge-management/user1-topic-view.png) </br> 

用户在同一主题上可能看到的内容的不同之处在于，用户可能没有查看相关站点或文件的 Office 365 权限。  主题体验会遵守对主题中的项目设置的权限，并且无法更改对它们的访问权限。 在我们的示例中，用户 1 无法查看 Neptune 主题页中的 *DG-2000 产品* 概述文件，因为用户 1 没有查看该文件的 Office 365 权限。

如果用户无法查看主题中的足够信息，因此该主题将不可用。 在此实例中，用户不会看到突出显示的主题。 但是，对主题中的详细信息具有访问权限的其他用户将能够看到该主题。


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>知识管理员和主题参与者的主题权限

分配了管理主题的权限的用户（知识管理员）只能查看他们有权在主题内查看的信息。

同样，具有创建和编辑主题权限的用户（主题参与者）将只能查看他们有权在主题内查看的信息。 


## <a name="ai-versus-manually-curated-topic-information"></a>AI 与手动选择的主题信息

主题可以包含 AI 生成的信息以及主题参与者或知识管理员添加或编辑的信息。

 - AI 添加的主题中的信息仅对有权访问源内容的人可见。
 - 主题参与者或知识管理员手动添加或编辑的信息对可以看到该主题的每个人可见。

下表介绍基于用户权限在给定主题中可以看到哪些用户（主题查看者、参与者和知识管理员）。

|主题项|用户可以看到哪些内容|
|:---------|:------------------|
|主题名称|用户可以在主题中心查看所有主题的主题名称。 如果某些主题与用户的相关性较低，则这些主题可能不可见。|
|主题说明|AI 生成的说明仅对具有源内容权限的用户可见。 手动输入或编辑的说明对所有用户都可见。|
|人员|固定人员对所有用户可见。 建议的用户仅对具有源内容权限的用户可见。|
|文件|文件仅对具有源内容权限的用户可见。|
|页面|只有对源内容具有权限的用户才能看到页面。|
|网站|网站仅对具有源内容权限的用户可见。|




## <a name="see-also"></a>另请参阅

