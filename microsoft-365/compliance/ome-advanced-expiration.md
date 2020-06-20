---
title: 为使用 Office 365 高级邮件加密进行加密的电子邮件设置到期日期
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 使用 Office 365 高级邮件加密通过自定义品牌化模板设置电子邮件的过期日期来扩展电子邮件的安全性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e929ce1d948a83a98cca6fa35a65b80a2fc9ef15
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818685"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>为使用 Office 365 高级邮件加密进行加密的电子邮件设置到期日期

Office 365 高级邮件加密包含在[Microsoft 365 企业版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 e5 （非盈利员工定价）、Office 365 企业版 E5 （非盈利员工定价）和 Office 365 教育版 A5 中。 如果您的组织有一个不包含 Office 365 高级邮件加密的订阅，则可以使用 microsoft 365 E5 兼容性 SKU 附加 Microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Microsoft 365 高级合规性 SKU 外接程序（microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Office 365 Sku 购买它。

您可以使用您的用户发送给使用 OME 门户访问加密电子邮件的外部收件人的电子邮件的邮件过期。 您可以通过使用在 Windows Powershell 中指定过期日期的自定义品牌模板，强制收件人使用 OME 门户查看并回复您的组织发送的加密电子邮件。

作为 O365 全局管理员，当您应用公司品牌以自定义组织的电子邮件的外观时，您还可以为这些电子邮件指定过期时间。 使用 Office 365 高级邮件加密，可以为来自您的组织的加密电子邮件创建多个模板。 使用模板，可以控制收件人访问您的用户发送的邮件的时间长短。

当最终用户收到设置了过期日期的邮件时，用户会看到包装电子邮件中的到期日期。 如果用户尝试打开已过期的邮件，则会在 OME 门户中显示一个错误。

您只能将电子邮件的到期日期设置为外部收件人。

使用 Office 365 高级邮件加密，无论何时应用自定义品牌打造，Office 365 都会将包装应用于与应用该模板的邮件流规则相适应的电子邮件。 此外，如果使用自定义品牌，则只能使用过期时间。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>使用 PowerShell 创建自定义品牌模板以强制邮件过期

1. 使用组织中具有全局管理员权限的帐户[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

2. 运行 Set-omeconfiguration cmdlet。

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

其中：

- `Identity`是自定义模板的名称。

- `ExternalMailExpiryInDays`标识收件人在过期前可保留邮件的天数。 可以使用1到730天之间的任意值。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有关 Office 365 高级邮件加密的详细信息

- [Office 365 高级邮件加密](ome-advanced-message-encryption.md)

- [撤销使用 Office 365 高级邮件加密进行加密的电子邮件](revoke-ome-encrypted-mail.md)

- [邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
