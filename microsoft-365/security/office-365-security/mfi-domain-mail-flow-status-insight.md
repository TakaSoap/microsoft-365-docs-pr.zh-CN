---
title: 邮件流仪表板中的主要域邮件流状态洞察力
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的邮件流仪表板中的顶级域邮件流状态洞察力来解决与其电子邮件域中的 MX 记录相关的邮件流问题。
ms.openlocfilehash: d4abc311e96df87894d5f059328f1a16a00190b8
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877500"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>安全 & 合规中心中的主要域邮件流状态洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Security & 合规中心](https://protection.office.com)中的 [邮件流仪表板](mail-flow-insights-v2.md)中的 **顶级域邮件流状态** 洞察力为您的组织的域提供了邮件流的当前状态。 此洞察力可帮助您识别和解决遇到 * *_邮件流受到影响_* 的域的问题 (例如，无法接收外部电子邮件) ，尤其是域过期或包含不正确的 MX 记录的域。

![安全 & 合规性中心的邮件流仪表板中的顶级域流状态构件](../../media/mfi-top-domain-mail-flow-status-widget.png)

当您单击小组件中的 " *查看详细信息* *" 时，将显示一个 **域状态** 弹出控件，其中显示了有关每个域的状态的更多详细信息：

- **域**
- **以前的 MX 记录**
- **当前 MX 记录**
- **电子邮件接收状态**
- **域状态** ：绿色复选标记表示当前的 MX 记录 (您单击小组件时，) 与我们记录的值相匹配，并且在过去的两个小时内，该域已收到电子邮件。

  红色的 X 表示 MX 记录已更改，并且在过去6小时内没有收到任何电子邮件。 这可能表明你的域已过期，或者 MX 记录已被错误更新。 请与你的域注册机构或 DNS 托管服务核实域是否已过期，或者域的 MX 记录是否不正确。

您可以单击 " **查看更多** " 查看更多域的相同信息。

!["详细信息" 浮出在顶级域邮件流状态洞察力](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
