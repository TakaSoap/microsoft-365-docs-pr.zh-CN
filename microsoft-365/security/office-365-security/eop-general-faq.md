---
title: EOP 一般常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: 获取有关 Exchange Online Protection 和 EOP (云托管电子邮件筛选服务) 常见问题的解答。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04246b7c0a241c672328febd1584a56aa11becf2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916954"
---
# <a name="eop-general-faq"></a>EOP 一般常见问题解答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
-  [独立 Exchange Online Protection](exchange-online-protection-overview.md)

我们在此处回答了有关 Exchange Online Protection (EOP) 云托管的电子邮件筛选服务的最常见常见问题。 有关其他常见问题 (FAQ) 的主题，请转到下列链接：

- [EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.md)

- [委派管理常见问题解答](delegated-administration-faq.md)

- [反垃圾邮件保护常见问题](anti-spam-protection-faq.md)

- [隔离常见问题解答](quarantine-faq.md)

- [反恶意软件保护常见问题](anti-malware-protection-faq-eop.md)

- [邮件跟踪常见问题解答](/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>什么是 EOP？

EOP 是云托管的电子邮件筛选服务，用于保护客户免受垃圾邮件和恶意软件的攻击，并实施自定义策略规则。 EOP 包含在包含 Exchange Online 邮箱的任何 Microsoft 365 订阅中。 EOP 也作为独立产品/服务提供，以帮助保护本地电子邮件环境。

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>如何注册 EOP 试用版或购买 EOP？

在 Exchange Online Protection 主页上注册 EOP 试用版或通过 Web[购买 EOP。](https://products.office.com/exchange/exchange-email-security-spam-protection) 请注意，试用版购买的功能与付费订阅的功能相同，但还包括 [Exchange Enterprise CAL with Services](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) 订阅计划提供的其他功能。

## <a name="how-is-eop-priced"></a>EOP 如何定价？

EOP 由用户授权。 有关最新定价信息，请参阅 [Exchange Online Protection 主页](https://products.office.com/exchange/exchange-email-security-spam-protection)。

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>将 EOP 投入生产需要多久？

根据设置 EOP 服务 中概述的步骤更改 MX 记录，并且邮件通过 [EOP](set-up-your-eop-service.md)流动时，筛选将立即开始。 MX 记录可能需要 24-48 小时才能通过 DNS 传播。 在此过程中，你随时都可以微调保护设置。

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>我是否必须使用 Microsoft 365 的所有功能来使用 EOP？ 如果只需要 EOP 保护，这一切如何？

可以使用 EOP 保护本地邮箱，而无需使用 Microsoft 365 的其他任何功能。 这称为独立订阅。 可以在 Exchange Online Protection 服务说明 中找到 [EOP 功能列表](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>通过 EOP 注册电子邮件筛选时，为什么需要 Microsoft 365 租户？

Microsoft 365 是一组产品和服务的名称，可以通过 Microsoft 365 租户访问这些产品和服务。 将 Microsoft 365 租户视为可以添加电子邮件筛选许可证的起点。

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>EOP 是否具有可在其中了解已知问题和预期解决方案的通信门户？ 新功能如何？

Microsoft 365 管理中心将包含一些此信息。 如果受服务级别事件影响，应看到通信警报 (登录 Microsoft 365 管理中心后) 通常附带一个铃声图标。 我们建议你阅读所有项的信息，然后酌情进行处理。

关于新的 EOP 功能 [，Microsoft 365 商业](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) 版路线图是一个很好的资源，用于查找有关即将推出的新功能的信息。 我们还将在 [Microsoft 365](https://www.microsoft.com/microsoft-365/blog/) 博客网站上发布有关新功能的博客文章。

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>该服务是否与旧版 Exchange 版本（如 (2010 Exchange Server和非 Exchange) 一起运行？

是，该服务与服务器无关，可用于任何 SMTP 邮件传输代理。

## <a name="what-size-organization-can-use-the-service"></a>组织可以使用该服务的大小？

任意大小。 无论组织增长多快，EOP 网络都有足够的容量来容纳增长。

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>设置 EOP 需要什么权限？

若要配置 EOP，您必须是全局管理员或组织管理角色组 (Exchange 公司) 。

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>如何知道数据和私人信息是安全的？

若要了解有关我们为确保数据和私人信息的安全而执行的步骤（包括有关服务级别协议 (SLA) 的信息）的信息，请转到 [Office 365](https://www.microsoft.com/trust-center)信任中心。

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>我是否应注意任何限制，例如邮件大小限制？

是。 有关 EOP 中限制的信息，请参阅[Exchange Online Protection Limits。](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="does-eop-support-powershell"></a>EOP 是否支持 PowerShell？

是，可通过 PowerShell 使用完整的 EOP 功能：Exchange Online PowerShell，适用于具有 Exchange Online 邮箱的组织;独立 EOP 组织的 EOP PowerShell。 有关详细信息，请参阅[Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)和[Exchange Online Protection PowerShell。](/powershell/exchange/exchange-online-protection-powershell)