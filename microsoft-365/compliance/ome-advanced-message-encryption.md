---
title: 高级邮件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 08/11/2021
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 高级邮件加密使管理员能够使用受保护的邮件执行更多操作，帮助组织履行合规性义务。
ms.openlocfilehash: 9e0f1933d68ba696e6446b321857eb3f6836f378
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197553"
---
# <a name="advanced-message-encryption"></a>高级邮件加密

Office 365 高级邮件加密[包含在 Microsoft 365 企业版 E5、Office 365 E5、Microsoft 365 E5 (](https://www.microsoft.com/microsoft-365/enterprise/home)非营利组织员工定价) 、Office 365 企业版 E5 (非营利组织员工定价) 和 Office 365 教育版 A5 中。 如果你的组织订阅不包含Office 365 高级邮件加密， 可以使用 Microsoft 365 E3 的 Microsoft 365 E5 合规 SKU 加载项、Microsoft 365 E3 (非营利组织员工定价) 或 Microsoft 365 E3 的 Office 365 高级合规版 SKU 加载项、Microsoft 365 E3 (非营利组织员工定价) 、Office 365 SKU 或 Microsoft 365 E5 Microsoft 365 A3/A5 信息保护和管理 SKU 加载项（适用于 Microsoft 365 A3/E3） 购买。

高级邮件加密可帮助客户履行合规性义务，这些义务要求对外部收件人及其对加密电子邮件的访问进行更灵活的控制。 使用高级邮件加密Office 365，您可以使用自动策略控制在组织外部共享的敏感电子邮件。 您可以配置这些策略以标识敏感信息类型，如 PII、财务或运行状况标识，或者您可以使用关键字来增强保护。 配置策略后，将策略与自定义品牌电子邮件模板配对，然后添加过期日期，以对符合策略的电子邮件进行额外控制。 此外，管理员还可以随时撤销对邮件的访问，以进一步控制通过安全 Web 门户从外部访问的加密电子邮件。

只能撤消和设置发送给外部收件人的电子邮件的到期日期。

## <a name="get-started-with-office-365-advanced-message-encryption"></a>开始Office 365 高级邮件加密

以下文章介绍如何设置和使用高级邮件加密。

你的组织必须拥有一个订阅，其中包含Office 365 高级邮件加密。 有关受支持的订阅的详细信息，请参阅邮件 [策略和合规性服务说明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。

如果尚未设置Office 365 邮件加密，请参阅设置[新的Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

使用高级邮件加密，不限于单个品牌模板。 相反，你可以创建和使用多个品牌模板。 有关信息，[请参阅将组织的品牌添加到加密邮件。](add-your-organization-brand-to-encrypted-messages.md) 使用自定义品牌打造时，外部收件人将收到一封通知电子邮件，其中包含指向 OME 门户的链接。 邮件流规则确定通知电子邮件和 OME 门户使用哪个品牌模板。 这样，安全内容不会发送到组织外部。

只能撤销邮件，并应用过期日期至用户通过门户接收的邮件。 换句话说，应用了自定义品牌模板的电子邮件。 有关详细信息和示例，请参阅 Ensure [all external recipients use the OME Portal to read encrypted mail 中的指南](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)。

[设置由用户加密的电子邮件的Office 365 高级邮件加密。](ome-advanced-expiration.md) 使用自动策略控制在组织外部共享的敏感电子邮件，这些策略通过通过安全 Web 门户过期对加密电子邮件的访问来增强保护。

[撤销由用户加密Office 365 高级邮件加密。](revoke-ome-encrypted-mail.md) 控制在组织外部共享的敏感电子邮件，并通过撤销通过安全 Web 门户对加密电子邮件的访问来增强保护。  
