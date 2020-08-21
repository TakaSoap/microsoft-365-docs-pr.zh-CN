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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: 获取有关有关 Exchange Online Protection 与 EOP 和云托管的电子邮件 () 一般问题的解答。
ms.openlocfilehash: 42162ea841f876fc5e958d67fab61dbe4bffe9de
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827757"
---
# <a name="eop-general-faq"></a>EOP 一般常见问题解答

我们在此处回答了有关 Exchange Online Protection 和 EOP 和云 (筛选) 服务的一般常见问题。 有关其他常见问题 (FAQ) 的主题，请转到下列链接：

- [EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.md)

- [委派管理常见问题解答](delegated-administration-faq.md)

- [反垃圾邮件保护常见问题](anti-spam-protection-faq.md)

- [隔离常见问题解答](quarantine-faq.md)

- [反恶意软件保护常见问题](anti-malware-protection-faq-eop.md)

- [邮件跟踪常见问题解答](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>什么是 EOP？

EOP 是云托管的电子邮件筛选服务，用于保护客户不受垃圾邮件和恶恶意软件的攻击和实现自定义策略规则。 EOP 包含在任何包含 Exchange Online 邮箱的 Microsoft 365 订阅中。 EOP 也作为保护本地电子邮件环境的独立产品。

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>如何注册 EOP 试用版或购买 EOP？

在 Exchange Online Protection 主页上注册 EOP 试用版或 [通过 Web 购买](https://products.office.com/exchange/exchange-email-security-spam-protection)EOP。 请注意，试用购买的功能与付费订阅相同，但还包括 [Exchange Enterprise CAL with Services 订阅计划中提供](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) 的其他功能。

## <a name="how-is-eop-priced"></a>EOP 如何定价？

EOP 由用户许可。 有关最新定价信息，请参阅 [Exchange Online Protection 主页](https://products.office.com/exchange/exchange-email-security-spam-protection)。

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>EOP 进入生产需要多长时间？

当您按照设置 EOP 服务中所述的步骤更改 MX [记录时](set-up-your-eop-service.md)，您的邮件将通过 EOP 传递，筛选将立即开始。 MX 记录可能需要 24-48 小时才能通过 DNS 传播。 在此过程中，您可以随时调整保护设置。

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>必须使用 Microsoft 365 的所有功能才能使用 EOP 吗？ 如果我只想使用 EOP 保护该怎样，只保护全部就会怎样？

您可以使用 EOP 保护本地邮箱，无需使用任何其他 Microsoft 365 功能。 这称为独立订阅。 可以在 Exchange Online Protection 服务说明中找到 EOP [功能列表](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>通过 EOP 注册电子邮件筛选时为什么需要 Microsoft 365 租户？

Microsoft 365 是可经 Microsoft 365 租户访问的产品和服务集合的名称。 将 Microsoft 365 租户视为可以向其添加电子邮件筛选许可证的起始点。

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>EOP 是否具有一个通信门户，我可以在其中找到已知问题及预期解决方案？ 新功能怎办？

Microsoft 365 管理中心将包含一部分此类信息。 如果你受服务级别事件影响，则应该会在登录 (Microsoft 365 管理中心后，看到一个通信警报 (通常会) 旁的轮询图标旁。 我们建议你阅读所有项的信息，然后酌情进行处理。

关于新的 EOP 功能 [，Microsoft 365 商业版路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) 在找到有关即将推出的新功能的信息方面是不错的资源。 我们还会在 Microsoft 365 博客网站上发布 [有关新功能的博客](https://www.microsoft.com/microsoft-365/blog/) 文章。

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>该服务是否处理旧版 Exchange (，例如 Exchange Server 2010 沙) 和非 Exchange 环境？

是的，此服务不受服务器限制，可以与任何 SMTP 邮件传输代理一起使用。

## <a name="what-size-organization-can-use-the-service"></a>组织可以使用此服务的规模？

任意大小。 EOP 网络有足够的容量容纳您的增长，无论您的组织增长的速度如何。

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>设置 EOP 需要什么权限？

要配置 EOP，您必须是组织管理角色组配置的 (Exchange 公司管理员) 。

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>如何知道我的数据和私人信息是安全的？

若要了解有关我们确保你的数据和私人信息安全所采取的步骤（包括有关服务级别协议 (SUM) 的详细信息），请转到 [Office 365 信任中心](https://www.microsoft.com/trust-center)。

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>是否有任何限制是我需要注意的，例如邮件大小限制？

是。 有关 EOP 中的限制的详细信息，请参阅 [Exchange Online Protection 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)。

## <a name="does-eop-support-powershell"></a>EOP 是否支持 PowerShell？

是的，可通过 PowerShell 使用完整的 EOP 功能：具有 Exchange Online 邮箱的组织使用 Exchange Online PowerShell;独立 EOP 组织的独立 EOP PowerShell。 有关详细信息，请参阅[Exchange Online PowerShell 和](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)Exchange Online Protection [PowerShell。](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)
