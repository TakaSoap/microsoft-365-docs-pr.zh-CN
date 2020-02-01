---
title: Office 365 高级邮件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 中的高级邮件加密通过使管理员能够更好地使用受保护的邮件来帮助组织满足其合规性义务。
ms.openlocfilehash: 580803d7b15608ebb0852896cdbd9a43ee5a2ff4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601799"
---
# <a name="office-365-advanced-message-encryption"></a>Office 365 高级邮件加密

Office 365 高级邮件加密包含在[Microsoft 365 企业版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 e5 （非盈利员工定价）、Office 365 企业版 E5 （非盈利员工定价）和 Office 365 教育版 A5 中。 如果您的组织有一个不包含 Office 365 高级邮件加密的订阅，则可以使用 microsoft 365 E5 兼容性 SKU 附加项购买 Microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Office 365 高级适用于 Microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Office 365 Sku 的合规性 SKU 外接程序。

Office 365 中的高级邮件加密帮助客户满足法规遵从性义务，这些要求对外部收件人和其加密电子邮件的访问权限要求更灵活的控制。 使用 Office 365 中的高级邮件加密，可以控制使用自动策略在组织外共享的敏感电子邮件。 您可以配置这些策略以标识敏感信息类型（如 PII、财务或运行状况 Id），也可以使用关键字来增强保护。 配置策略后，您可以使用自定义品牌的电子邮件模板对策略进行配对，然后添加一个到期日期，以对符合该策略的电子邮件进行更多控制。 此外，管理员可以随时撤销对邮件的访问权限，从而进一步控制在外部通过安全 web 门户访问的加密电子邮件。

您只能撤销和设置发送给外部收件人的电子邮件的到期日期。

## <a name="get-started-with-office-365-advanced-message-encryption"></a>开始使用 Office 365 高级邮件加密

以下文章介绍了如何设置和使用高级邮件加密。

您的组织必须具有包含 Office 365 高级邮件加密的订阅。 有关受支持订阅的详细信息，请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。

如果尚未设置 Office 365 邮件加密，请参阅[设置新的 office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

使用高级邮件加密时，您并不局限于单个品牌模板。 相反，您可以创建和使用多个品牌打造模板。 有关信息，请参阅[将组织的品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)。

[为通过 Office 365 高级邮件加密加密的电子邮件设置到期日期](ome-advanced-expiration.md)。 使用自动策略控制在组织外部共享的敏感电子邮件，从而通过将安全 web 门户转到加密电子邮件来实现访问权限，从而增强保护。

[撤消由 Office 365 高级邮件加密加密的电子邮件](revoke-ome-encrypted-mail.md)。 控制在组织外共享的敏感电子邮件，并通过将访问安全的 web 门户转到加密电子邮件来增强保护。  

使用 Office 365 高级邮件加密时，无论您何时应用自定义品牌打造模板，Office 365 都会对适合您应用该模板的邮件流规则的电子邮件应用包装。 您只能撤消邮件并将到期日期应用到用户通过门户接收的邮件。 也就是说，应用了自定义品牌打造模板的电子邮件。 有关详细信息和示例，请参阅[确保所有外部收件人使用 OME 门户阅读加密邮件的指南（仅适用于 Office 365 高级邮件加密）](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only)。
