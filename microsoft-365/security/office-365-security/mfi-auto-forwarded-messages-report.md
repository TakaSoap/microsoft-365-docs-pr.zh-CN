---
title: 自动转发的邮件见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: 管理员可以在安全与合规中心的邮件流仪表板中了解自动转发&报告。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c892400152df15adb3dfeb0c747ed7fae034d3d6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029938"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>安全与合规中心中的自动转发&见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


安全 &**与** 合规中心的邮件流仪表板 [](mail-flow-insights-v2.md)中的"自动转发邮件"见解显示有关从组织自动转发给外部域中 [收件人](https://protection.office.com)的邮件的信息。

![安全与合规中心中的"自动转发&小组件](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>自动转发的邮件详细信息

单击小组件中的消息数时，将显示一个显示有关自动转发邮件的详细信息的飞出窗格：

- **通过转发方法自动转发邮件**：

  - **按邮件流规则**
  - **按收件箱规则**
  - **通过 SMTP 转发**：此方法指示管理员可在邮箱上配置的自动转发，如"为邮箱配置电子邮件 [转发"中所述](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。
  - 指向转发 [报告的链接，](view-mail-flow-reports.md#forwarding-report) 了解更多详细信息。

- **按域和用户自动转发的邮件**：

  - **转发到的前 5 个域**
  - **上个星期 (新域)**
  - **前 5 个转发用户**
  - **上周 (新用户)**
  - 有关更多详细信息， [请参阅转发修改](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 报告的链接。

![安全与合规中心内自动转发的邮件报告&飞出](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>见解

基于报告数据生成两个见解：

- [新用户转发电子邮件](mfi-new-users-forwarding-email.md)
- [正在转发电子邮件的新域](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
