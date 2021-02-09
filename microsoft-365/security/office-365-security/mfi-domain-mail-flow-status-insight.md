---
title: 邮件流仪表板中的热门域邮件流状态见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何 &使用安全与合规中心的邮件流仪表板中的"顶级域邮件流状态"见解来排查与 MX 记录相关的邮件流问题。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df0f571d29d72b23e7b2e210b61a4fb1676175aa
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150203"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>安全与合规中心内热门域&状态见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

安全 **与合规** 中心的邮件流仪表板中的"[](mail-flow-insights-v2.md)顶级域邮件流状态 [](https://protection.office.com)&可为你提供组织的当前邮件流状态。

此见解可帮助您识别遇到邮件流问题的域并排除 ***故障*** 。 例如，域无法接收外部电子邮件，因为该域已过期或域的 MX 记录不正确。

![安全与合规中心的邮件流仪表板中的"&流状态"小组件](../../media/mfi-top-domain-mail-flow-status-widget.png)

单击小 **组件** 中的"查看详细信息"时，将显示"域 **状态** "飞出，其中显示每个域状态的更多详细信息：

- **域**
- **以前的 MX 记录**
- **当前 MX 记录**
- **电子邮件接收状态**
- 域状态：绿色选中标记表示单击小组件) 时当前的 MX 记录 (与记录的值匹配，并且域在过去两小时内已收到电子邮件。

  红色 X 表示 MX 记录已更改，并且域在过去 6 小时内未收到任何电子邮件。 这很可能表示你的域已过期，或者 MX 记录更新不正确。 请与域注册机构或 DNS 托管服务联系，以查看域是否已过期，或者域的 MX 记录是否不正确。

可以单击 **"查看更多"** 查看更多域的相同信息。

![顶部域邮件流状态见解中的详细信息飞出](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
