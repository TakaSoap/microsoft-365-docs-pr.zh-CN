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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 59e2c938c70dd8e3060fd85d084acbe8f79856ad
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806622"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>在 Microsoft 365 中控制自动外部电子邮件转发

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

作为管理员，您可能有公司要求限制或控制自动转发的邮件给外部收件人 (组织外部的收件人) 。 电子邮件转发可能非常有用，但是可能会因信息泄露而带来安全风险。 攻击者可使用此信息来攻击您的组织或合作伙伴。

Microsoft 365 中提供了以下类型的自动转发：

- 用户可以配置 [收件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) ，以便将邮件有意转发给外部发件人 (或作为受到威胁的帐户) 的结果。

- 管理员可以配置 [邮箱转发](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (也称为 _SMTP 转发_ ) ，以自动将邮件转发给外部收件人。

您可以使用出站垃圾邮件筛选器策略来控制自动转发到外部收件人。 有三个可用的设置：

- **自动** ：阻止自动外部转发。 邮件的内部自动转发将继续有效。 这是默认设置。

- **启用** ：允许和不限制自动外部转发。

- **Off** ：禁用自动外部转发，并将导致未送达报告 (也称为 "NDR" 或 "退回邮件") 发件人。

有关如何配置这些设置的说明，请参阅 [在 EOP 中配置出站垃圾邮件筛选](configure-the-outbound-spam-policy.md)。

> [!NOTE]
> 
> - 禁用自动转发将禁用用户) 或邮箱转发 (admins) 将邮件重定向到外部地址 (的任何收件箱规则。
> 
> - 内部用户之间的邮件自动转发不受出站垃圾邮件筛选器策略中的设置的影响。
> 
> - 您可以查看在 [自动转发的邮件报告](mfi-auto-forwarded-messages-report.md)中自动将邮件转发给外部收件人的用户的相关信息。

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>出站垃圾邮件筛选器策略设置如何与其他自动电子邮件转发控件一起使用

作为管理员，您可能已将其他控件配置为允许或阻止自动电子邮件转发。 例如：

- 允许或阻止自动将电子邮件转发到部分或全部外部域的[远程域](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains)。

- Exchange [邮件流规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 中的条件和操作 (也称为传输规则) ，用于检测并阻止将自动转发的邮件发送给外部收件人。

远程域设置和邮件流规则与出站垃圾邮件筛选器策略中的设置无关。 例如：

- 您允许远程域的自动转发，但在出站垃圾邮件筛选器策略中阻止自动转发。 在此示例中，将阻止自动转发的邮件。

- 您可以在出站垃圾邮件筛选器策略中允许自动转发，但使用邮件流规则或远程域设置阻止自动转发的电子邮件。 在此示例中，邮件流规则或远程域设置将阻止自动转发的邮件。

通过此功能，您可以 (例如，) 允许在出站垃圾邮件筛选器策略中自动转发，但使用远程域控制用户可以将邮件转发到的外部域。

## <a name="the-blocked-email-forwarding-message"></a>阻止的电子邮件转发邮件

当检测到邮件自动转发且组织策略 *阻止* 该活动时，会将该邮件以 NDR 的形式返回给发件人，其中包含以下信息：

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
