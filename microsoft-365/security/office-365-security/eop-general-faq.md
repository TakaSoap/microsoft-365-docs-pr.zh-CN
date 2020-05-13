---
title: EOP 一般常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: 获取有关 Exchange Online Protection （EOP）云托管的电子邮件筛选服务的最常见一般问题的答案。
ms.openlocfilehash: 02aa7175e95cf706ed13268035953400af2485a7
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206658"
---
# <a name="eop-general-faq"></a>EOP 一般常见问题解答

在这里，我们将回答有关 Exchange Online Protection （EOP）云托管的电子邮件筛选服务的最常见的一般问题。 有关其他常见问题 (FAQ) 的主题，请转到下列链接：

- [EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.md)

- [委派管理常见问题解答](delegated-administration-faq.md)

- [反垃圾邮件保护常见问题](anti-spam-protection-faq.md)

- [隔离常见问题解答](quarantine-faq.md)

- [反恶意软件保护常见问题](anti-malware-protection-faq-eop.md)

- [邮件跟踪常见问题解答](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>什么是 EOP？

EOP 是一种云托管的电子邮件筛选服务，可用于保护客户免受垃圾邮件和恶意软件的攻击，并实现自定义策略规则。 EOP 包含在任何包含 Exchange Online 邮箱的 Microsoft 365 订阅中。 EOP 也可以作为一种独立的产品提供，以帮助保护本地电子邮件环境。

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>如何注册 EOP 试用版或购买 EOP？

通过 web 在[Exchange Online Protection 主页](https://products.office.com/exchange/exchange-email-security-spam-protection)上注册 EOP 试用版或购买 EOP。 请注意，试用版的功能与付费订阅的功能相同，但还包括[Exchange ENTERPRISE CAL With service](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)订阅计划提供的附加功能。

## <a name="how-is-eop-priced"></a>EOP 如何定价？

EOP 由用户授予许可。 有关最新定价信息，请参阅[Exchange Online Protection 主页](https://products.office.com/exchange/exchange-email-security-spam-protection)。

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>将 EOP 投入生产需要多长时间？

更改 MX 记录时，根据[设置 EOP 服务](set-up-your-eop-service.md)中概述的步骤，以及通过 EOP 的邮件流，筛选将立即开始。 MX 记录可能需要长达24-48 小时才能通过 DNS 传播。 在此过程中，你可以随时微调保护设置。

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>是否必须使用 Microsoft 365 的所有功能才能使用 EOP？ 如果我只想实现 EOP 保护，这是什么？

您可以使用 EOP 来保护您的内部部署邮箱，而无需使用 Microsoft 365 的其他任何功能。 这称为独立订阅。 可以在[Exchange Online Protection 服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)中找到 EOP 功能的列表。

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>在通过 EOP 注册电子邮件筛选时，为什么需要 Microsoft 365 租户？

Microsoft 365 是可通过 Microsoft 365 租户访问的产品和服务集合提供的名称。 请将 Microsoft 365 租户视为您可以为电子邮件筛选添加许可证的起始点。

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>EOP 是否有一个通信门户，我可以在其中找到已知问题和预期解决办法？ 新功能是什么？

Microsoft 365 管理中心将包含此信息中的一些信息。 如果您受到服务级别事件的影响，则在登录到 Microsoft 365 管理中心后，您应该会看到一条通信警报（通常伴随响铃图标）。 我们建议你阅读所有项的信息，然后酌情进行处理。

关于新的 EOP 功能， [Microsoft 365 for business 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)是找出有关即将推出的新功能的信息的一个很有用的资源。 我们还将向[Microsoft 365 博客](https://www.microsoft.com/microsoft-365/blog/)网站发布有关新功能的博客文章。

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>该服务是否适用于旧版 Exchange 版本（例如 Exchange Server 2010）和非 Exchange 环境？

是的，该服务是服务器不可知的，可用于任何 SMTP 邮件传输代理。

## <a name="what-size-organization-can-use-the-service"></a>组织可以使用服务的规模是多少？

任意大小。 EOP 网络具有足够的容量来满足您的增长需求，而不考虑组织的增长速度。

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>设置 EOP 需要什么权限？

为了配置 EOP，您必须是全局管理员或 Exchange 公司管理员（组织管理角色组）。

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>如何知道我的数据和隐私信息是安全的？

若要详细了解我们为确保数据和隐私信息的安全性（包括有关服务级别协议（Sla）的信息）所采取的步骤，请转到[Office 365 信任中心](https://www.microsoft.com/trust-center)。

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>是否有应注意的任何限制，例如邮件大小限制？

是的。 有关 EOP 中的限制的详细信息，请参阅[Exchange Online Protection 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)。

## <a name="does-eop-support-powershell"></a>EOP 是否支持 PowerShell？

是的，完整的 EOP 功能可通过 PowerShell： Exchange Online PowerShell 提供，适用于具有 Exchange Online 邮箱的组织;独立的 EOP PowerShell 用于独立的 EOP 组织。 有关详细信息，请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)和[Exchange online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)。
