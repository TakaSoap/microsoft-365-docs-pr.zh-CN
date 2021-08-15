---
title: 限制对主题中主题Microsoft Viva访问
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
ms.openlocfilehash: e0fc8d2bce8de471049f36194696fd5600b05476ccceb362a448d7ba79be45d7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53854671"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>限制对主题中主题Microsoft Viva访问

在Microsoft Viva中，您组织的利益干系人可能希望确保不会发现特定主题，并且不会向许可用户公开这些主题。 例如，您可能正在处理一个您不想公开任何相关信息的项目。 虽然Office 365、文件和其他资源的权限将阻止主题体验用户查看主题中的敏感信息，但还有一些额外的安全措施可防止发现特定主题。

知识管理员控制设置以防止主题被发现，而知识管理员和其他利益干系人需要知道如何操作，以便他们可以协作工作。

> [!Important] 
> 本文介绍了防止主题通过 AI 标识或在你的环境中视为其他安全保护措施的方法。 需要注意的是，在 Viva 主题中，不允许用户查看主题中不允许他们通过特定权限访问Office 365内容。 即使用户能够查看主题、其文件、网站和页面，他们Office 365查看权限将不可见。 确保正确设置敏感文件的权限应该是主要的安全保护措施。

## <a name="prevent-topics-from-being-identified"></a>阻止标识主题

知识管理员可通过阻止在初始索引中发现特定主题来限制对特定主题的访问。 有两种方法可以执行此任务，这两种方法均在"Viva 主题"管理设置中Microsoft 365 管理中心。
 
- [Select SharePoint sites to exclude from topic discovery](./topic-experiences-discovery.md#select-sharepoint-topic-sources)： You can use this setting to prevent specific SharePoint sites from being crawled for topics.
- [按名称排除主题](./topic-experiences-discovery.md#exclude-topics-by-name)：管理员可以使用此设置防止按名称发现特定主题。 在 Viva 主题管理员设置中，管理员可以上载要排除在 CSV 文件中的主题列表。 可以排除与主题名称完全匹配或部分匹配的主题。

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>阻止特定用户查看主题

知识管理员还可以 [选择谁可以查看组织的主题](./topic-experiences-knowledge-rules.md)。 此设置允许你选择哪些许可用户可以查看所有主题。 例如，在试验环境中，您可能只希望允许一小组用户查看主题。

## <a name="remove-topics-from-being-viewed"></a>从查看中删除主题

知识管理人员可以选择 [删除主题](./manage-topics.md) ，以便用户不再可以看到它们。 在主题 **中心的**"管理主题"页上，知识管理人员可以选择拒绝特定主题以防止查看这些主题。 可以删除主题，而不管主题是否位于建议或已确认状态。

如果需要，稍后可以将已删除的主题添加回可查看的主题。 


## <a name="see-also"></a>另请参阅



