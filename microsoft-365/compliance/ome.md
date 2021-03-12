---
title: 邮件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: 了解如何在组织内外人员之间发送和接收加密电子邮件。
ms.openlocfilehash: 8d1803442428f3061c686afa0b790d3f468abde8
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741323"
---
# <a name="message-encryption"></a>邮件加密

人们经常使用电子邮件来交换敏感信息，例如财务数据、法律合同、机密产品信息、销售报表和预测、患者健康信息或客户和员工信息。因此，邮箱可能会成为一个包含大量潜在敏感信息的存储库，信息泄露可能会成为您组织的严重威胁。

使用 Office 365 邮件加密，组织可以在组织内外人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于 Outlook.com、Yahoo！、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有预期收件人才能查看邮件内容。

## <a name="how-office-365-message-encryption-works"></a>Office 365 邮件加密的工作原理

本文的其余部分适用于新的 OME 功能。

Office 365 邮件加密是一项基于 Microsoft Azure 权限管理 (Azure RMS) 的联机服务，它是 Azure 信息保护的一部分。 此服务包括加密、标识和授权策略，以帮助保护电子邮件的安全。 可以使用权限管理模板、"不要转发"选项和仅[](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)[加密选项加密邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

然后，用户可以使用这些选项加密电子邮件和各种附件。 有关受支持的附件类型的完整列表，请参阅电子邮件的 IRM 简介中的"IRM 策略在附加到邮件时覆盖[的文件类型"。](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)

作为管理员，您还可以定义邮件流规则以应用此保护。 例如，您可以创建一个规则，要求加密发送给特定收件人的所有邮件，或主题行中包含特定词语，并指定收件人不能复制或打印邮件的内容。

与以前版本的 OME 不同，无论您在组织内部还是向 Microsoft 365 之外的收件人发送邮件，新功能都提供统一的发件人体验。 此外，接收发送到 Outlook 2016 或 Outlook 网页版中的 Microsoft 365 帐户的受保护电子邮件的收件人不必执行任何其他操作来查看邮件。 它无缝工作。 使用其他电子邮件客户端和电子邮件服务提供商的收件人也具有改进的体验。 有关信息， [请参阅了解 Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) 中的受保护邮件和如何 [打开受保护的邮件](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)。

有关以前版本的 OME 与新的 OME 功能之间的差异的详细列表，请参阅 [比较 OME 的版本](ome-version-comparison.md)。

当某人发送与加密邮件流规则匹配的电子邮件时，该邮件在发送之前已加密。 所有使用 Outlook 客户端读取邮件的 Microsoft 365 最终用户都会收到针对加密和受权限保护的邮件的本机一流阅读体验，即使他们与发件人不在同一组织中。 支持的 Outlook 客户端包括 Outlook 桌面、Outlook Mac、iOS 和 Android 版 Outlook mobile 以及 Outlook 网页 (以前称为 Outlook Web App) 。

接收发送到其 Outlook.com、Gmail 和 Yahoo 帐户的加密邮件或受权限保护的邮件的收件人将收到包装邮件，将其引导到 OME 门户，他们可在其中使用 Microsoft 帐户、Gmail 或 Yahoo 凭据轻松进行身份验证。

在 Outlook 客户端上读取加密或受权限保护的邮件的最终用户也使用 OME 门户查看他们收到的加密和受权限保护的邮件。

如果受保护邮件的发件人位于 GCC High 中，并且收件人位于 GCC High 外部，包括商业用户、Outlook.com 用户和其他电子邮件提供商（如 Gmail）的用户，收件人将收到包装邮件。 包装邮件将收件人引导到收件人能够阅读和回复邮件的 OME 门户。 否则，如果发件人和收件人都位于 GCC High 环境中，即使他们并不在同一个组织中，则使用 Outlook 客户端读取邮件的收件人将收到加密和受权限保护的邮件的本机一流阅读体验。 有关 GCC High 中不同体验的信息，请参阅 [比较 OME 的版本](ome-version-comparison.md)。

有关可以使用 OME 加密的邮件和附件的大小限制详细信息，请参阅 [Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Office 365 高级邮件加密在 OME 上的工作方式

Office 365 高级邮件加密允许你创建多个品牌模板，以便可以微调对收件人邮件的控制，并创建自定义品牌打造体验以支持不同的组织结构。

Microsoft 365 中的高级邮件加密可帮助你履行要求更灵活地控制外部收件人对加密电子邮件的访问的合规性义务。 通过 Office 365 中的高级邮件加密，作为管理员，您可以使用自动策略控制在组织外部共享的敏感电子邮件，这些策略可检测敏感信息类型 (例如 PII、财务或运行状况) 或关键字，通过使通过安全 Web 门户过期对加密电子邮件的访问来增强保护。 作为管理员，你可以随时撤销对电子邮件的访问，进一步控制通过 Microsoft 365 Web 门户访问的加密电子邮件。

邮件吊销和过期仅适用于用户发送给组织外部收件人的电子邮件。 此外，收件人必须通过 Web 门户访问电子邮件。 若要确保收件人使用门户接收电子邮件，请设置应用包装的自定义品牌模板。 然后，在邮件流规则中应用品牌模板。 有关高级邮件加密的信息，请参阅 [Office 365 高级邮件加密](ome-advanced-message-encryption.md)。

## <a name="defining-rules-for-office-365-message-encryption"></a>定义 Office 365 邮件加密的规则

为 Office 365 邮件加密启用新功能的一种方式是让 Exchange Online 和 Exchange Online Protection 管理员定义邮件流规则。 这些规则确定应在哪些条件下加密电子邮件。 为规则设置加密操作时，任何匹配规则条件的邮件在发送之前都将被加密。

邮件流规则非常灵活，可让你组合条件，以便可以在单个规则中满足特定安全要求。 例如，您可以创建一个规则，对包含特定关键字且发送给外部收件人的所有邮件进行加密。 Office 365 邮件加密的新功能还加密来自加密电子邮件收件人的答复。

若要详细了解如何创建邮件流规则以利用新的 OME 功能，请参阅 Define Rules [for Office 365 Message Encryption。](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-the-new-ome-capabilities"></a>开始使用新的 OME 功能

如果你已准备好在组织中开始使用新的 OME 功能，请参阅设置 [新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>发送、查看和回复加密电子邮件

使用 Office 365 邮件加密，用户可以从 Outlook 和 Outlook 网页版发送加密电子邮件。 此外，管理员可以在 Microsoft 365 中设置邮件流规则，以根据关键字匹配或其他条件自动加密电子邮件。

组织中加密邮件的收件人将能够在任何版本的 Outlook（包括 Outlook for PC、Outlook for Mac、Outlook 网页版、Outlook for iOS 和 Outlook for Android）中无缝读取这些邮件。 在其他电子邮件客户端上接收加密邮件的用户可以在 OME 门户中查看邮件。

有关如何发送和查看加密邮件的详细指南，请看一下这些文章。

|阅读本文...|如果是...|
|:-----|:-----|
|[了解 Office 365 中的受保护邮件](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|希望了解有关加密邮件如何工作以及可以使用哪些选项的详细信息的最终用户。|
|[如何打开受保护的邮件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|想要阅读发送给您的受保护邮件的最终用户。 本文包含有关从不同电子邮件帐户（包括 Microsoft 365 外部的帐户，如 gmail 和 Yahoo！ 帐户。|
|[在 Outlook 中发送、查看和回复加密邮件](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|想要从 Outlook 发送、查看或回复加密邮件的最终用户。 即使您不是组织的成员，您仍会收到 Outlook 中发送给您的加密邮件的通知。 阅读本文，了解如何查看和回复从 Office 365 发送的加密邮件。|
|[发送经过数字签名或加密的邮件](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|希望使用 Outlook for Mac 发送、查看或回复加密邮件的最终用户。 本文还介绍了使用除 OME 外的其他加密方法，如 S/MIME。|
|[在 Android 设备上查看加密邮件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|收到使用 Android 设备上的 Office 365 邮件加密进行加密的邮件的最终用户，可以使用免费的 OME 查看器应用查看邮件并发送加密回复。 本文介绍如何。|
|[在 iPhone 或 iPad 上查看加密邮件](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|收到使用 iPhone 或 iPad 上的 Office 365 邮件加密进行加密的邮件的最终用户，可以使用免费的 OME 查看器应用查看邮件并发送加密回复。 本文介绍如何。|
||
