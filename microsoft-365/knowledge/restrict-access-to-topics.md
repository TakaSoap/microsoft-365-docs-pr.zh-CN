---
title: 限制对主题的访问
description: 如何排除主题以防止它们被发现。
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698816"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>限制对主题体验中主题的访问

在主题体验中，贵组织中的利益干系人可能希望确保未发现特定主题，不会向许可用户公开这些主题。 例如，您可能正在处理您不想公开任何相关信息的项目。 虽然对网站、文件和其他资源的 Office 365 权限将阻止主题体验用户查看主题中的敏感信息，但存在其他安全措施来阻止发现特定主题。

虽然知识管理员控制知识网络设置以防止发现主题，但知识管理员和其他利益干系人需要知道如何完成此操作，以便他们可以协作处理这一问题。

> [!Important] 
> 本文介绍了防止主题通过 AI 标识或在环境中作为附加安全保护措施进行查看的方法。 值得注意的是，在主题体验中，不允许用户查看主题中不允许他们通过 Office 365 权限访问的内容。 即使用户能够查看主题，他们没有查看 Office 365 权限的文件、网站和页面也不可见。 确保正确设置敏感文件的权限应该是你的主要安全保护措施。

## <a name="prevent-topics-from-being-identified"></a>阻止标识主题

知识管理员可以通过阻止在初始索引中发现特定主题来限制对特定主题的访问。 在 Microsoft 365 管理中心的知识库管理员设置中，有两种方法可以这样做。
 
- [选择要从主题发现中排除的 SharePoint](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)网站：可以使用此设置阻止对特定 SharePoint 网站进行主题爬网。
- [按名称排除](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)主题：管理员可以使用此设置阻止按名称发现特定主题。 在知识网络管理员设置中，管理员可以上载要排除在 CSV 文件中的主题列表。 可以排除与主题名称完全匹配或部分匹配的主题。

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>阻止特定用户查看主题

知识管理员还可以 [选择谁可以查看组织的主题](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)。 此设置允许你选择哪些许可用户可以查看所有主题。 例如，在试验环境中，您可能只希望允许一小组用户查看主题。

## <a name="remove-topics-from-being-viewed"></a>从查看中删除主题

知识管理员可以选择 [删除主题](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) ，以便用户无法再看到这些主题。 在 **主题中心的**"管理主题"页上，知识管理员可以选择拒绝特定主题以防止查看这些主题。 可以删除主题，无论主题是否位于建议或已确认的状态。

如果需要，以后可以将已删除的主题添加回可查看的主题。 


## <a name="see-also"></a>另请参阅



  






