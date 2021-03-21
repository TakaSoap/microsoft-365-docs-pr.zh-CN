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
description: 使用 Office 365 高级邮件加密通过自定义品牌模板设置电子邮件的到期日期来扩展电子邮件安全性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927782"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>为使用 Office 365 高级邮件加密进行加密的电子邮件设置到期日期

Office 365 高级邮件加密包含在 [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/home)企业版 E5、Office 365 E5、Microsoft 365 E5 (非营利组织员工定价) 、Office 365 企业版 E5 (非营利组织版员工定价) 和 Office 365 教育版 A5 中。 如果您的组织订阅不包含 Office 365 高级邮件加密， 可以使用 Microsoft 365 E3 的 Microsoft 365 E5 合规性 SKU 加载项、Microsoft 365 E3 (非营利组织员工定价) 或适用于 Microsoft 365 E3、Microsoft 365 E3 (非营利组织版员工定价) 或 Office 365 SKU 的 Office 365 高级合规性 SKU 加载项购买它。

可以在用户发送给使用 OME 门户访问加密电子邮件的外部收件人的电子邮件上使用邮件过期。 您强制收件人使用 OME 门户查看和回复由组织发送的加密电子邮件，具体使用自定义品牌模板指定 Windows PowerShell 中的到期日期。

作为 Office 365 全局管理员，当你应用公司品牌自定义组织电子邮件的外观时，还可以指定这些电子邮件的过期时间。 通过 Office 365 高级邮件加密，你可以为源自组织的加密电子邮件创建多个模板。 使用模板，您可以控制收件人有权访问用户发送的邮件的多久。

当最终用户收到设置了过期日期的邮件时，用户将看到包装电子邮件中的到期日期。 如果用户尝试打开过期的邮件，OME 门户中将显示错误。

只能为发送给外部收件人的电子邮件设置到期日期。

借助 Office 365 高级邮件加密，无论何时应用自定义品牌，Office 365 都向符合模板所应用的邮件流规则的电子邮件应用包装。 此外，只有当使用自定义品牌时，才能使用过期。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>使用 PowerShell 创建自定义品牌模板以强制邮件过期

1. [使用在组织中](/powershell/exchange/connect-to-exchange-online-powershell) 具有全局管理员权限的帐户连接到 Exchange Online PowerShell。

2. 运行 New-OMEConfiguration cmdlet。

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

其中：

- `Identity` 是自定义模板的名称。

- `ExternalMailExpiryInDays` 标识收件人在邮件过期之前可以保留邮件的天数。 可以使用 1 到 730 天之间的任意值。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有关 Office 365 高级邮件加密的信息

- [Office 365 高级邮件加密](ome-advanced-message-encryption.md)

- [撤销使用 Office 365 高级邮件加密进行加密的电子邮件](revoke-ome-encrypted-mail.md)

- [邮件策略和合规性服务说明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)