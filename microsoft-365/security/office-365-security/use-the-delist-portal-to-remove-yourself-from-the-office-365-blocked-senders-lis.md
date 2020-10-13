---
title: 将自己从阻止的发件人列表中删除
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您将了解如何使用除名门户将自己从 Microsoft 365 阻止的发件人列表中删除。
ms.openlocfilehash: 637b610d0dd621e6d922d23354aead8e3824ad6a
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445527"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>使用除名门户将自己从阻止的发件人名单中删除

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


当您尝试向其电子邮件地址在 Microsoft 365 中的收件人发送电子邮件时，收到一条错误消息？ 如果您认为不应收到错误消息，可以使用除名门户将自己从阻止的发件人列表中删除。

## <a name="what-is-the-blocked-senders-list"></a>阻止的发件人列表是什么？

Microsoft 使用阻止的发件人名单来防止其客户遭受垃圾邮件、欺诈和网络钓鱼网站的攻击。 您的邮件服务器的 IP 地址（即邮件服务器用于在 Internet 上标识自己的地址）被标记为对 Microsoft 365 的潜在威胁，原因是有多种原因。 当 Microsoft 365 将 IP 地址添加到列表中时，它会阻止 IP 地址和我们通过我们的数据中心提供的任何客户之间的进一步通信。

在您收到包含类似于以下错误的邮件回复时，您就知道自己已被添加到该列表中：

> 550 5.7.606-649 访问被拒绝，禁止发送 IP [_ip 地址_];若要请求从此列表中删除，请访问 https://sender.office.com/ 并按照说明操作。 有关详细信息，请参阅 [Exchange Online 中的电子邮件未送达报告](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)。

其中  _IP address_ 是邮件服务器在其上运行的计算机的 IP 地址。

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>使用除名门户将自己从阻止的发件人列表中删除

1. 在 Web 浏览器中，请转至 [https://sender.office.com](https://sender.office.com)。

2. 按照页面上的说明执行操作。请确保您使用收到错误消息的电子邮件地址，以及错误消息中指定的 IP 地址。每次访问只能输入一个电子邮件地址和一个 IP 地址。

3. Click **Submit**.

    门户会向您提供的电子邮件地址发送电子邮件。 电子邮件的外观如下所示： ![ 通过除名门户提交请求时收到的电子邮件的屏幕截图](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. 单击除名门户发送给您的电子邮件中的确认链接。

    这将使您返回到除名门户。

5. In the delist portal, click **Delist IP**.

    从阻止发件人列表中删除 IP 地址后，来自该 IP 地址的电子邮件将传递给使用 Microsoft 365 的收件人。 因此，请务必确信从该 IP 地址发送的电子邮件不会被滥用或恶意;否则，可能会再次阻止该 IP 地址。

    > [!NOTE]
    > 在删除限制之前，可能需要长达24小时或结果相差很大。

请参阅 [在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md) 和 [EOP 中的出站垃圾邮件保护](outbound-spam-controls.md) 以防止 IP 被阻止。
