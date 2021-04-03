---
title: 限制对 Microsoft Viva 主题中主题的访问
description: 如何排除主题以防止它们被发现。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500879"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>限制对 Microsoft Viva 主题中主题的访问

在 Microsoft Viva 中，贵组织中的利益干系人可能希望确保不会发现特定主题，并且不会向许可用户公开这些主题。 例如，您可能正在处理一个您不想公开任何相关信息的项目。 虽然对网站、文件和其他资源的 Office 365 权限将阻止主题体验用户查看主题中的敏感信息，但还有一些额外的安全措施可防止发现特定主题。

知识管理员控制设置以防止主题被发现，而知识管理员和其他利益干系人需要知道如何操作，以便他们可以协作工作。

> [!Important] 
> 本文介绍了防止主题通过 AI 标识或在你的环境中视为其他安全保护措施的方法。 需要注意的是，在 Viva 主题中，不允许用户查看主题中不允许他们通过 Office 365 权限访问的内容。 即使用户能够查看主题，他们无权查看其 Office 365 的文件、网站和页面也将不可见。 确保正确设置敏感文件的权限应该是主要的安全保护措施。

## <a name="prevent-topics-from-being-identified"></a>阻止标识主题

知识管理员可通过阻止在初始索引中发现特定主题来限制对特定主题的访问。 在 Microsoft 365 管理中心的 Viva 主题管理员设置中，有两种方法可以执行此任务。
 
- [选择要从主题发现中排除的 SharePoint](./topic-experiences-discovery.md#select-sharepoint-topic-sources)网站：可以使用此设置阻止对主题的特定 SharePoint 网站进行爬网。
- [按名称排除主题](./topic-experiences-discovery.md#exclude-topics-by-name)：管理员可以使用此设置防止按名称发现特定主题。 在 Viva 主题管理员设置中，管理员可以上载要排除在 CSV 文件中的主题列表。 可以排除与主题名称完全匹配或部分匹配的主题。

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>阻止特定用户查看主题

知识管理员还可以 [选择谁可以查看组织的主题](./topic-experiences-knowledge-rules.md)。 此设置允许你选择哪些许可用户可以查看所有主题。 例如，在试验环境中，您可能只希望允许一小组用户查看主题。

## <a name="remove-topics-from-being-viewed"></a>从查看中删除主题

知识管理人员可以选择 [删除主题](./manage-topics.md) ，以便用户不再可以看到它们。 在主题 **中心的**"管理主题"页上，知识管理人员可以选择拒绝特定主题以防止查看这些主题。 可以删除主题，而不管主题是否位于建议或已确认状态。

如果需要，稍后可以将已删除的主题添加回可查看的主题。 


## <a name="see-also"></a>另请参阅



