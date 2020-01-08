---
title: 在 Exchange Online 中修复错误代码为 5.7.7 xx 的电子邮件传递问题
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 了解如何在 Exchange Online 中修复错误代码为 5.7.7 xx 的电子邮件问题（阻止发送邮件的租户）。
ms.openlocfilehash: cbfff7fc0905206a0302f7e1a458718637d934b7
ms.sourcegitcommit: 8ac1b6586678035050fc422e6fb503fa478be397
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962301"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>在 Exchange Online 中修复错误代码为 5.7.7 xx 的电子邮件传递问题

本主题介绍在未送达报告（也称为 "NDR"、"退回邮件"、"传递状态通知" 或 "DSN"）中看到状态代码 550 5.7.7 xx 时可以执行的操作。 当你的租户受到限制以单向方式发送电子邮件时，你将看到此自动通知。 这些错误代码通常将为705或750。

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705：租户已超出阈值限制：需要了解的内容

一旦您的用户（统称为 "组织"），通过该服务发送一定数量的可疑电子邮件，则在解决问题之前，可以阻止所有用户发送任何电子邮件。 这通常是泄露（最常见的）或发送过多的批量邮件的结果。 用户将收到一 NDR，其中指出：

`550 5.7.705 Access denied, tenant has exceeded threshold`

在极少数情况下，如果您的订阅已过期，也可能会发生这种情况。 服务同步新订阅信息所需的时间（通常不超过一天），但在这种情况下，可能会阻止您的组织同时发送电子邮件。 避免这种情况的最佳方式是确保你的订阅不会过期。

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750：未注册的域电子邮件限制：您需要了解的内容

Office 365 允许租户通过 Exchange Online Protection （EOP）中继某些邮件。 例如：

- Office 365 邮箱接收来自外部发件人的电子邮件。 邮件转发是在 Office 365 邮箱上配置的，因此邮件将返回到用户的外部电子邮件地址。 此方案在教育环境中最常见，即学生希望使用其个人电子邮件帐户查看学校相关的邮件。

- 具有通过 EOP 发送传出邮件的本地电子邮件服务器的混合 envrionments。

### <a name="problems-with-unregistered-domains"></a>未注册域的问题

问题是，在本地电子邮件服务器受到威胁时，会通过 EOP 中继大量垃圾邮件。 在几乎所有情况下，连接器都设置正确，但电子邮件是从未注册（也称为未设置）的域发送的。 Office 365 允许未注册的域中有合理的电子邮件量，但您应配置用于将电子邮件作为接受域发送的每个域。

一旦受到威胁，租户将被阻止为未注册的域发送出站电子邮件。 用户将收到一 NDR，其中指出：

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a>如何取消阻止租户以便再次发送

如果您的租户被阻止发送电子邮件，则需要执行以下几项操作：

1. 验证是否已注册所有电子邮件域。 有关详细信息，请参阅[将域添加到 Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain)和[在 Exchange Online 中管理接受的域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

2. 查找异常[连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。 恶意参与者通常会在 Office 365 组织中创建新的入站连接器以发送垃圾邮件。 若要查看现有连接器，请参阅[验证 Office 365 中的连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)。

3. 按照对[Office 365 中的受损电子邮件帐户的响应](responding-to-a-compromised-email-account.md)中所述，检查是否存在已损坏的用户。

4. 为 Office 365 组织中的所有管理员[启用 MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) 。

5. 锁定你的本地电子邮件服务器并验证其是否未受到威胁。

   > [!TIP]
   > 这里有许多因素，尤其是在使用第三方服务器时。 无论如何，您都需要验证所有传出电子邮件现在是否合法。

6. 致电 Microsoft 支持部门，让你的租户不再被阻止，以从未注册的域中再次发送。 错误代码很有帮助，但您需要证明您的环境已受到保护，并且无法发送垃圾邮件。 若要打开支持案例，请参阅[联系支持人员以获取商业产品-管理员帮助](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。

## <a name="for-more-information"></a>有关详细信息

[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)

[Exchange Online 服务说明的 "发送限制" 部分中的批量邮件指南](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[Office 365 中的电子邮件未送达报告](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[配置邮箱的电子邮件转发](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[如何设置多功能设备或应用程序以使用 Office 365 发送电子邮件](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

[在 Exchange Online 中管理接受的域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
