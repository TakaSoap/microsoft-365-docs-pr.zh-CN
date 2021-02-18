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
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290629"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>安全与合规中心中的自动&见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

安全 **与** 合规中心的"邮件流"仪表板 [](mail-flow-insights-v2.md)中的"自动转发邮件 [](https://protection.office.com)"见解&显示有关从组织自动转发给外部域中收件人的邮件的信息。

![安全与合规中心中的"自动转发&小组件](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>自动转发的邮件详细信息

单击小组件中的邮件数时，将显示一个显示有关自动转发邮件的详细信息的飞出窗格：

- **通过转发方法自动转发邮件**：

  - **按邮件流规则**
  - **按收件箱规则**
  - **通过 SMTP 转发**：此方法指示管理员可以在邮箱上配置的自动转发，如配置邮箱的电子邮件 [转发中所述](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)。
  - 指向转发 [报告的链接，](view-mail-flow-reports.md#forwarding-report) 了解更多详细信息。

- **按域和用户自动转发的邮件**：

  - **转发到的前 5 个域**
  - **上个星期 (新域)**
  - **前 5 位转发用户**
  - **上周 (新用户)**
  - 指向转发 [修改报告的链接，](mfi-new-users-forwarding-email.md#forwarding-modifications-report) 了解更多详细信息。

![安全与合规中心中"自动转发的邮件"报告&飞出](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>见解

基于报告数据生成两个见解：

- [转发电子邮件的新用户](mfi-new-users-forwarding-email.md)
- [正在转发电子邮件的新域](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
