---
title: 修复发件人域见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解安全 & 合规性中心的 "邮件流" 仪表板中的 "修复发件人域的洞察力"。
ms.openlocfilehash: c4cf4a87ad770325ca6ad2f0b87ac8ce52c345c2
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818827"
---
# <a name="fix-sender-domain-insight"></a>修复发件人域见解

Microsoft 365 需要从内部本地电子邮件环境发送到 Microsoft 365 的邮件，以满足特定的安全条件：

- 你已在 Microsoft 365 中创建了一个入站连接器，以通过使用源 IP 地址或证书来验证来自你的本地电子邮件服务器的 SMTP 连接。

- 您已将本地电子邮件服务器配置为通过 Microsoft 365 将电子邮件中继到外部世界。

- 在您的配置中，下列陈述中的一条为真：

  - 发件人的电子邮件域已在您的组织中注册。 有关更多信息，请参阅 在 Office 365 中添加域。

  - 您的内部部署电子邮件服务器配置为使用证书向 Microsoft 365 发送电子邮件，证书包含或与您在 Microsoft 365 中注册的域名完全匹配，并且您已在 Microsoft 365 中使用该域创建了一个基于证书的连接器。 

不符合条件的邮件将不会被组织到组织中，并且可能会被拒绝。

**Fix sender domain**真知灼见显示从本地环境中不符合条件的电子邮件，可帮助您识别本地电子邮件环境中可能受到危害的计算机和用户帐户，并帮助您采取补救措施。

![安全 & 合规性中心的邮件流仪表板中的修补发件人域洞察力](../../media/sender-domain-insight-selected.png)

当您单击 "**查看详细信息**" 时，会转到另一个小部件，其中包含更多详细信息，如下图中所示：

![修复发件人域洞察力中的详细信息小部件](../../media/sender-domain-view-details.png)

你将看到用于将邮件传递到 Office 365 的入站连接器。 您还可以单击 "**查看示例邮件 id** " 以查看从您的本地电子邮件环境中发送的邮件的详细信息。 由于这些邮件是由 Office 365 拒绝的，因此不能使用邮件跟踪，但可以使用示例邮件 id 来跟踪本地电子邮件环境中的邮件。

![查看修补发件人域洞察力中的示例邮件 id](../../media/sender-domain-view-sample-message-ids.png)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他邮件流见解的详细信息，请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
