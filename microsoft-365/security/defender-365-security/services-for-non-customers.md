---
title: 非客户向 Microsoft 365 发送邮件的服务
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 为了维护用户对使用电子邮件的信任，Microsoft 已出台多项帮助保护我们的用户的策略和技术。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056274"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>非客户向 Microsoft 365 发送邮件的服务

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


电子邮件滥用、垃圾邮件和欺诈邮件（网络钓鱼）继续增加整个电子邮件系统的负担。 为帮助保持用户对电子邮件使用的信任，Microsoft 已制定各种策略和技术来帮助保护我们的用户。 然而，Microsoft 知道合法的电子邮件不应受到负面影响。 因此，我们建立了一套服务，通过主动管理发件人的发送信誉，帮助发件人提高向 Microsoft 365 用户传递电子邮件的能力。

本概述提供有关我们为您的组织提供的好处的信息，即使您不是客户。

## <a name="sender-solutions"></a>发件人解决方案

****

|服务|优点|
|---|---|
|此联机帮助内容|提供： <ul><li>与向 EOP 用户传递通信的任何问题的起点。</li><li>包含一个简单的在线指南，其中包含我们的策略和要求。</li><li>Microsoft 所采用垃圾邮件筛选器和身份验证技术的概述。</li><ul>|
|[Microsoft 支持](#microsoft-support)|提供有关传送问题的自助和升级支持。|
|[反垃圾邮件 IP 除名门户](#anti-spam-ip-delist-portal)|一种提交 IP 除名请求的工具。在提交此请求前，发件人有责任确保任何源自可疑 IP 的后续邮件不是滥用的或恶意的。|
|[源自 Exchange Online 的垃圾邮件的滥用和垃圾邮件报告](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|防止从 Exchange Online 发送垃圾邮件和其他不需要的邮件，使 Internet 和邮件系统变得混乱。|
|

## <a name="microsoft-support"></a>Microsoft 支持

Microsoft 为向 Microsoft 365 收件人发送邮件时遇到问题的人提供了多种支持选项。 我们建议您：

- 在您接收到的任何未送达报告中，按照说明执行操作。

- 请查看[向 Office 365 发送故障排除邮件](troubleshooting-mail-sent-to-office-365.md)中非客户遇到的最常见的问题。

- 使用 [Microsoft 365](https://sender.office.com) 除名门户提交将 IP 从阻止的发件人列表中删除的请求。

- 参阅 [Microsoft 社区论坛](https://community.office365.com/f/)。

- 使用另一种方法联系你尝试通过电子邮件发送的客户，让他们联系 Microsoft 支持并代表你打开支持票证。 在某些情况下，出于法律原因，Microsoft 支持必须与拥有被阻止的 IP 空间的发件人直接沟通。 但是，非客户通常无法开立支持票证。

  有关对 Office 365 的 Microsoft 技术支持的详细信息，请参阅 [支持](/office365/servicedescriptions/office-365-platform-service-description/support)。

## <a name="anti-spam-ip-delist-portal"></a>反垃圾邮件 IP 除名门户

这是自助服务门户，可用于将自己从 Microsoft 365 阻止的发件人名单中删除。 如果您尝试向电子邮件地址在 Microsoft 365 中的收件人发送电子邮件，并且认为不应发送电子邮件，请使用此门户。 有关详细信息，请参阅[使用除名门户来将自己从阻止的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>源自 Exchange Online 的垃圾邮件的滥用和垃圾邮件报告

有时，第三方会使用 Microsoft365 发送垃圾邮件，这违反我们的使用条款和策略。 如果您收到来自 Office 365 的任何垃圾邮件，您可以向 Microsoft 报告这些邮件。 有关说明，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。