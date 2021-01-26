---
title: '主题体验角色 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解主题体验中的用户角色。
ms.openlocfilehash: b649ea81d8e5b036e9332e9c87b67a951b5905a7
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975689"
---
# <a name="topic-experiences-roles-preview"></a>主题体验角色 (预览) 

> [!Note] 
> 本文中的内容适用于 Project Cortex 专用预览版。 [了解更多关于 Project Cortex的信息](https://aka.ms/projectcortex)。


在 Microsoft 365 环境中使用主题体验时，你的用户可以担任以下角色：
-   主题查看器
-   主题参与者
-   知识管理器
-   知识管理员

## <a name="topic-viewer"></a>主题查看器

主题查看者是组织中可以查看其 SharePoint 新式网站和 SharePoint 搜索中突出显示的主题的用户。 他们可以选择突出显示的主题，在主题页中查看有关这些主题的更多详细信息。 

若要使主题突出显示及其主题页面对主题查看器可见，用户必须：
-   [由 Microsoft](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) 365 管理员分配主题体验许可证。
-   允许查看主题。 这由 Microsoft 365 管理中心的"主题体验设置"页中的知识管理员完成。


## <a name="topic-contributors"></a>主题参与者

主题参与者是组织中不仅具有主题查看器权限的用户，还可以编辑现有主题或创建新主题。 在手动"选择"主题页中的信息时，它们 (AI 或手动提供的信息) 以确保其质量。

具有主题参与者权限的用户将看到"主题"页上显示的"编辑"按钮，这允许他们更新和发布主题。

主题参与者还可以通过其主题中心网站创建和发布新主题。

若要能够创建和编辑主题，用户必须：

-   [由 Microsoft](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) 365 管理员分配主题体验许可证。
-   [分配创建和编辑主题的权限](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)。 这是由知识管理员在 Microsoft 365 管理中心的"主题体验设置"页中完成。

## <a name="knowledge-managers"></a>知识经理

知识经理是管理组织中主题的用户。  主题管理通过主题中心中的"管理主题"页完成，并且仅对知识管理员可见。

在"管理主题"页中，知识管理员可以执行以下任务：
-   查看所有 AI 建议的主题。
-   查看主题以确认它们有效。
-   删除不希望向用户显示的主题。


此外，知识管理员还可以编辑现有主题或创建新主题。

为了能够管理主题，用户必须：
-   [由 Microsoft](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) 365 管理员分配主题体验许可证。
-   [分配有管理主题) 。](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center) 这是由知识管理员在 Microsoft 365 管理中心的"主题体验设置"页中完成。

对业务有全面了解的用户可以成为知识管理器角色的优秀候选人。 此类人员不仅可能了解主题是否有效，还可能了解公司内与这些主题相关的人员。


## <a name="knowledge-admins"></a>知识管理员

知识管理员是在你的 Microsoft 365 环境中设置和配置主题体验的管理员。 他们还会在设置完成后管理主题体验设置。 知识管理员角色要求你是 Microsoft 365 全局管理员或 SharePoint 管理员，因为设置和管理是在 Microsoft 365 管理中心内完成。
在设置过程中，知识管理员可以配置主题体验以执行以下操作：

-   选择将针对主题对哪些 SharePoint 网站进行爬网。
-   选择哪些许可用户将能够查看主题 (查看者) 。
-   选择要从标识中排除的主题。
-   选择哪些许可用户可以为主题参与者创建和编辑 (主题) 。
-   选择哪些许可用户能够管理知识经理 (主题) 。
-   命名主题中心。

知识管理人员需要能够与组织中所有主题体验利益干系人进行协调，以了解如何配置它。 例如，如果新项目包含敏感信息，则需要通知知识经理，以便他们可以确保 SharePoint 网站没有针对主题进行爬网，或者需要排除特定主题名称。


## <a name="see-also"></a>另请参阅

