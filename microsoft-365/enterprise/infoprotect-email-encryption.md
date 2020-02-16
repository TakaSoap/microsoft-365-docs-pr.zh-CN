---
title: 步骤 6：配置电子邮件加密
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 了解并配置 Office 365 的特权访问管理。
ms.openlocfilehash: d678c109f42901be2413c2b33e362d6796be96b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067172"
---
# <a name="step-6-configure-email-encryption"></a>步骤 6：配置电子邮件加密

*此步骤可选，它适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![第 6 阶段：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Microsoft 365 中有三种类型的电子邮件加密。

|||
|:-------|:-----|
| Office 邮件加密 (OME) | 在组织外部发送的 Exchange Online 电子邮件的加密。 |
| 信息权限管理 (IRM) | 随电子邮件一起携带的加密和权限。 |
| 安全/多用途 Internet 邮件扩展 (S/MIME) | 使用加密和数字签名的电子邮件保护。 |
|||

## <a name="office-365-message-encryption"></a>Office 365 邮件加密

通过 OME，您的组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。 OME 适用于 Outlook.com、Yahoo！、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有预期的收件人可以查看邮件。

![电子邮件的 OME 加密](../media/infoprotect-email-encryption/ome-encryption.png)

您设置用于定义加密条件的传输规则。 当用户发送的邮件与规则匹配时，则自动应用加密。

若要查看加密邮件，收件人可以获取一次性密码，使用 Microsoft 帐户登录，或使用与 Microsoft 365 关联的工作或学校帐户进行登录。 此外，收件人也可发送加密回复。 他们不需要自己的 Microsoft 365 订阅即可查看加密的邮件或发送加密的答复。

有关详细信息，请参阅 [Office 365 邮件加密](https://docs.microsoft.com/Office365/SecurityCompliance/ome)。

## <a name="irm"></a>IRM

Microsoft 365 中的 IRM 可帮助您通过其他加密保护信息，并通过应用智能策略来指定谁有权访问他们可以执行的操作。 对于电子邮件，您可以使用 IRM 进行加密并应用使用限制。 例如，可以指定某些收件人具有管理电子邮件的所有功能，并且某些收件人无法打印或转发电子邮件。 

IRM 策略在 Microsoft 365 中配置，并可应用于 SharePoint Online 和电子邮件中的文档。 受 IRM 保护的电子邮件包含应用的应用的策略设置并与之一起移动。 

![电子邮件的 IRM 保护](../media/infoprotect-email-encryption/irm-protection.png)

当收件人使用包含的策略打开电子邮件时，策略设置将用于解密邮件，并确定收件人可对邮件执行的操作。 

有关详细信息，请参阅 [Exchange Online 中的信息权限管理]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online)。

## <a name="smime"></a>S/MIME

S/MIME 是基于数字证书的基于电子邮件的保护解决方案，使您可以对邮件进行加密和数字签名。 邮件加密有助于确保只有预期收件人可以打开并阅读该邮件。 数字签名可帮助收件人验证发件人的身份，并确定只有发件人可以发送它。

![电子邮件的 S/MIME 保护](../media/infoprotect-email-encryption/smime-protection.png)

S/MIME 可用于向 Microsoft 365 订阅中的其他邮箱或向外部用户发送电子邮件。
通过使用包含用于加密或解密邮件的公钥和私钥的数字证书以及创建和验证数字签名，可以进行邮件加密和数字签名。
若要使用 S/MIME，您必须具有每个收件人的公钥。 收件人维护自己的私钥，它们必须保持安全。 如果私钥受到威胁，您需要获取新的数字证书，并将公钥重新分发给所有潜在的发件人。

有关详细信息，请参阅[邮件签名和加密的 S/MIME](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)。


作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step6)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 7 步](../media/stepnumbers/Step7.png)|[配置 Office 365 Privileged Access Management](infoprotect-configure-privileged-access-management.md)|
