---
title: 邮件流仪表板中的热门域邮件流状态见解
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何 &使用安全与合规中心内"邮件流"仪表板中的"热门域邮件流状态"见解，解决与 MX 记录相关的邮件流问题。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1a22589ece98e497c55d61d29256b2480a2f55d3
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63679711"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>安全与合规中心内热门域&状态见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

安全 **与合规中心的**"邮件流"仪表板 [](mail-flow-insights-v2.md)中的"热门域邮件流状态"&[可](https://protection.office.com)为你提供组织的当前邮件流状态。

此见解可帮助您识别和排查遇到邮件 ***流问题的域*** 。 例如，域无法接收外部电子邮件，因为该域已过期或域的 MX 记录不正确。

![安全与合规中心内"邮件流"仪表板中的"&流状态"小组件。](../../media/mfi-top-domain-mail-flow-status-widget.png)

在小 **组件中** 单击"查看详细信息"时 **，将显示"** 域状态"飞出控件，其中显示每个域状态的更多详细信息：

- **域**
- **以前的 MX 记录**
- **当前 MX 记录**
- **电子邮件接收状态**
- 域状态：绿色选中标记表示单击小组件 (时当前 MX 记录) 与记录中的值匹配，并且域在过去两小时内收到电子邮件。

  红色 X 表示 MX 记录已更改，并且域在过去 6 小时内未收到任何电子邮件。 这很可能表示您的域已过期，或者 MX 记录更新不正确。 请与域注册机构或 DNS 托管服务核实，以查看域是否已过期，或者域的 MX 记录不正确。

可以单击" **查看更多** "查看更多域的相同信息。

!["热门域邮件流状态"见解中的"详细信息"飞出。](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。
