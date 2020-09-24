---
title: 自动转发的邮件见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的自动转发的邮件报告。
ms.openlocfilehash: d4b772e6392e0af22e6bed475970f637ed03dcb1
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245943"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>自动转发的邮件在安全 & 合规中心中的洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在安全 & 合规性中心的[邮件流仪表板](mail-flow-insights-v2.md)中，**自动转发的邮件**可在[安全合规性中心](https://protection.office.com)显示有关自动从您的组织转发给外部域中的收件人的邮件的信息。

![Security & 合规中心中的自动转发的邮件小部件](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>自动转发的邮件详细信息

当您单击小组件中的邮件数量时，将显示一个弹出窗口，其中显示有关自动转发邮件的详细信息：

- **通过转发方法自动转发的邮件**：

  - **按邮件流规则**
  - **按收件箱规则**
  - **通过 SMTP 转发**：这是管理员可以在邮箱上配置的自动转发，如 [配置邮箱的电子邮件转发](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)中所述。
  - 有关更多详细信息，请 [转到转发报告](view-mail-flow-reports.md#forwarding-report) 的链接。

- **按域和用户自动转发的邮件**：

  - **转发到的前5个域**
  - **上周 (新域) **
  - **前5个转发用户**
  - **上周 (新用户) **
  - 有关更多详细信息，请 [转到转发修改报告](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 的链接。

![安全 & 合规中心中的自动转发的邮件的详细信息弹出报告](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>见解

根据报告数据生成两个见解：

- [新用户转发电子邮件](mfi-new-users-forwarding-email.md)
- [转发的新域电子邮件](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
