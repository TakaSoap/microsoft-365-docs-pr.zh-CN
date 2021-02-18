---
title: 配置和控制外部电子邮件转发、自动转发、5.7.520 访问被拒绝、禁用外部转发、管理员已禁用外部转发、出站反垃圾邮件策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77f666e5eeceee3f5b324e5b9b6fac721c10e410
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286858"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>在 Microsoft 365 中控制自动外部电子邮件转发

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

作为管理员，您可能有公司要求限制或控制自动将邮件转发到组织外部 (外部收件人) 。 电子邮件转发可能很有用，但也可能由于信息可能泄露而带来安全风险。 攻击者可能会使用此信息攻击组织或合作伙伴。


以下类型的自动转发在 Microsoft 365 中可用：

- 用户可以将 [收件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 配置为自动将邮件转发给外部 (或由于帐户泄露而) 。

- 管理员可以配置邮箱 [转发](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (_也称为 SMTP_ 转发) 自动将邮件转发给外部收件人。 管理员可以选择是直接转发邮件，还是将转发的邮件副本保留到邮箱中。

您可以使用出站垃圾邮件筛选器策略来控制自动转发到外部收件人。 有三种设置可用：

- **自动**：阻止自动外部转发。 邮件的内部自动转发将继续工作。 这是默认设置。
- **On**： 允许且不允许自动外部转发。
- **关闭**：自动外部转发处于禁用状态，并且将导致未送达报告 (也称为 NDR 或退回邮件) 发件人。

有关如何配置这些设置的说明，请参阅在 EOP 中配置出 [站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。

> [!NOTE]
>
> - 禁用自动转发会禁用将 (重定向到外部) 或 (转发) 邮箱转发用户的任何收件箱规则。
>
> - 出站垃圾邮件筛选器策略中的设置不会影响内部用户之间的自动转发邮件。
>
> - 您可以在"自动转发邮件"报告中查看有关自动将邮件转发到外部 [收件人的用户的信息](mfi-auto-forwarded-messages-report.md)。

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>出站垃圾邮件筛选器策略设置如何与其他自动电子邮件转发控件一起工作

作为管理员，您可能已经配置了其他控件以允许或阻止自动电子邮件转发。 例如：

- [允许或](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 阻止自动电子邮件转发到部分或所有外部域的远程域。

- Exchange 邮件流规则 [中的](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 条件和操作 (也称为传输规则) 检测并阻止自动转发给外部收件人的邮件。

远程域设置和邮件流规则独立于出站垃圾邮件筛选器策略中的设置。 例如：

- 允许自动转发远程域，但阻止出站垃圾邮件筛选器策略中的自动转发。 本示例中，自动转发的邮件被阻止。

- 允许在出站垃圾邮件筛选器策略中自动转发，但使用邮件流规则或远程域设置来阻止自动转发的电子邮件。 本示例中，邮件流规则或远程域设置将阻止自动转发的邮件。

此功能独立允许您 (例如) 出站垃圾邮件筛选器策略中允许自动转发，但使用远程域来控制用户可以将邮件转发到的外部域。

## <a name="blocked-email-forwarding-messages"></a>阻止的电子邮件转发邮件

当邮件被检测为自动转发，并且出站垃圾邮件[](configure-the-outbound-spam-policy.md)筛选器策略阻止该活动时，该邮件将返回到包含以下信息的 NDR 中的发件人：

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
