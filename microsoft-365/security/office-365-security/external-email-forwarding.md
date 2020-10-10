---
title: 配置和控制外部电子邮件转发、自动转发、5.7.520 访问被拒绝、禁用外部转发、管理员已禁用外部转发、出站反垃圾邮件策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: c0a3849d330b508630eb60c7ee24cd8b498a32b8
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417233"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>在 Office 365 中配置外部电子邮件转发

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


外部转发由 *出站反垃圾邮件策略* 控制，并根据配置的设置范围限定给用户。 当前支持3个设置：

- **自动** –这是由系统控制的：它允许出站垃圾邮件筛选功能来控制自动外部电子邮件转发。 这是默认设置。

- **启用** –允许和不限制自动外部转发。

- **关** -自动外部转发已禁用，并将导致向最终用户 (NDR) 的未送达报告。

有关如何配置这些设置的详细信息，请参阅 [配置 EOP 中的出站垃圾邮件筛选](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) 。

> [!NOTE]
> 禁用自动转发也将禁用将邮件重定向到外部地址的收件箱规则。

## <a name="controlling-external-email-forwarding"></a>控制外部电子邮件转发

作为组织的管理员，你可能需要对公司要求进行限制或控制能够在组织外部使用收件箱规则或 SMTP 转发自动转发电子邮件的用户。 电子邮件转发可能是一项非常有用的功能，但也可以通过可能泄露的信息带来风险，即使是向攻击者提供的信息可以被利用来攻击组织或其合作伙伴也是如此。

Office 365 不允许通过 "收件箱" 规则或 "邮箱" 配置自动进行外部转发，这将提供安全的默认策略。 但是，管理员可以为组织中的所有用户或部分用户修改这些设置。 内部用户之间的转发邮件不受此类修改的影响。

> [!NOTE]
> 在 Office 365 中禁用自动转发外部地址的过程分阶段进行，详细信息通过 [消息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) 发布进行通信。 若要帮助管理员准备这些更改，请提前修改策略以确保用户不会中断他们的用户。

有关使用自动转发的用户的详细信息，可以在 [自动转发的邮件报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true)中找到组织中 (收件箱规则或 SMTP 转发) 。

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a>此策略如何与其他自动转发控件一起使用

作为管理员，您可能已有其他类型的控件，例如阻止在 [远程域](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 中进行自动转发和使用 Exchange 传输规则 (ETR) 。 这两个控件都独立于此特定功能，例如，如果您允许对远程域进行自动转发，但通过出站垃圾邮件策略阻止自动转发，则会导致自动转发的邮件被阻止。 同样，如果您在出站垃圾邮件策略中允许自动转发，但在 ETR 或远程域中将其阻止，则这两个控件中的任何一个都将阻止该邮件。 例如，这使您可以在出站垃圾邮件策略中允许自动转发，并利用远程域来控制用户可以自动转发邮件的域。


## <a name="the-blocked-email-forwarding-message"></a>阻止的电子邮件转发邮件

当检测到邮件自动转发且组织策略 *阻止* 活动的 **未送达报告 (NDR) ** 将生成回最终用户。 报告将指示邮件未送达。 NDR 将具有以下格式： 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
