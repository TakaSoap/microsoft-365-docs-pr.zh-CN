---
title: 邮件流仪表板中的顶级域邮件流状态见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可了解如何使用安全 & 合规中心"邮件流"仪表板中的"首要域邮件流"状态见解，来解决与其电子邮件域中的 MX 记录相关的邮件流问题。
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827011"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>安全与合规中心内的顶级域邮件流 &状态见解

安全 & **合规** 中心内邮件流仪表板的 [顶级域](mail-flow-insights-v2.md) 邮件流状态见解可从邮件流邮件流为你提供组织域的当前状态。 该见解可帮助您标识遇到邮件流影响问题 (例如，无法接收外部电子邮件) （尤其***mail flow impacting***是域过期或具有不正确 MX 记录的域）的域，并对这些域进行故障排除。

![安全与合规中心内"邮件流"仪表板中的顶&"&示例](../../media/mfi-top-domain-mail-flow-status-widget.png)

在单击小 **部件中** 的详细信息时，会显示 **一个"域** 状态"浮出控件，显示每个域状态的更多详细信息：

- **域**
- **Previous MX Record**
- **Current MX 记录**
- **电子邮件接收状态**
- **域状态**：绿色复选标记指示在小部件) 上单击时的当前 MX 记录 (与我们记录上提供的值相匹配，且域已在过去两小时内收到电子邮件。

  红色 X 表示 MX 记录已更改，且过去 6 小时内域未收到任何电子邮件。 这可能表示您的域已过期或 MX 记录更新不正确。 请与您的域注册机构或 DNS 托管服务一起检查，以确定域是否已过期，或域的 MX 记录是否正确。

您可以单击" **查看更多** "查看多个域的相同信息。

!["顶级域"邮件流状态见解中的详细信息浮出控件](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。
