---
title: 在中国使用独立 EOP 保护本地邮箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 使用由世纪互联运营的 Office 365 的中国管理员可以了解如何使用独立 Exchange Online Protection (EOP) 来保护其本地邮箱。
ms.openlocfilehash: 9b91abec8d258df2b549cee1d538d2f65d2974ab
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356891"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>在中国使用独立 EOP 保护本地邮箱

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 本文仅适用于由中国世纪互联运营的 Office 365。

即使您计划在本地承载部分或全部邮箱，仍可以使用 Exchange Online Protection (EOP) 保护邮箱。 若要配置连接器，你的帐户必须是全局管理员或 Exchange 公司管理员 (组织管理角色组) 。 有关 Office 365 权限与 Exchange 权限的关系的信息，请参阅 [在由世纪互联运营的 office 365 中分配管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet&preserve-view=true)。 如果所有 Exchange 邮箱都是本地的，请按照以下步骤设置您的 EOP 服务。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>步骤1：使用 Microsoft 365 管理中心添加并验证你的域

1. 在 Microsoft 365 管理中心，导航到 "安装程序" 以将您的域添加到服务中。

2. 按照门户中的步骤将适用的 DNS 记录添加到您的 DNS 托管提供商，以验证域所有权。

> [!TIP]
> [将您的域和用户添加到由世纪互联运营的 office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet&preserve-view=true) 中，并为 [office 365 创建 dns 记录。当您](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet&preserve-view=true) 将您的域添加到服务并配置 dns 时，可以参考这些资源，从而为 office 创建 DNS 记录。

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>步骤2：添加收件人并配置域类型

在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。 执行此操作有几种方法，如[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中所述。 此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。 有关 DBEB 的详细信息，请参阅 [使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步骤 3：使用 EAC 设置邮件流

在能使邮件在 EOP 和你的内部部署邮件服务器间流动的 Set up connectors to route mail between Office 365 and your own email servers (EAC) 中创建连接器。 有关详细说明，请参阅 [在 Office 365 中使用连接器配置邮件流](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

 如何判断此任务生效？

 请参阅 [Test mail flow by 验证 Office 365 连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>步骤 4：允许入站端口 25 SMTP 访问

配置连接器后，请等待 72 小时，允许准备 DNS 记录更新。 遵循此限制，将防火墙或邮件服务器上的入站端口-25 SMTP 流量限制为仅接受来自 EOP 数据中心的邮件，特别是从 [Office 365 的 url 和 ip 地址范围](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints)列出的 ip 地址。 此操作将通过限制可以接收的入站邮件范围，保护内部部署环境。 此外，如果邮件服务器上的设置控制了允许为邮件中继连接的 IP 地址，也要更新这些设置。

> [!TIP]
> 将 SMTP 服务器上的设置配置 60 秒的连接时间。此设置在大多数情况下都可接受，例如，在发送带有很大附件的邮件时允许有些延迟。

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>第5步：确保垃圾邮件已路由到每个用户的 "垃圾邮件" 文件夹

若要确保垃圾邮件 () 垃圾邮件被正确路由到每个用户的 "垃圾邮件" 文件夹，您必须执行以下几个配置步骤。 [配置独立 EOP 将垃圾邮件传递到混合环境中的 "垃圾邮件" 文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)中提供了这些步骤。 如果不想将邮件移动到每个用户的 "垃圾邮件" 文件夹，可以通过编辑反垃圾邮件策略 (也称为 "内容筛选器策略") 选择另一个操作。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>步骤6：使用 Microsoft 365 管理中心将 MX 记录指向 EOP

按照 Office 365 域配置步骤更新你的域的 MX 记录，以便于你的入站电子邮件能够通过 EOP。 有关详细信息，请参阅 [管理 dns 记录时，可以再次引用为 Office 365 创建 dns 记录](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。

如何判断此任务生效？

 请参阅 [Test mail flow by 验证 Office 365 连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。

此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：

- In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.

- 将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。

- 如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>不太常见：包含本地邮箱和云中的混合安装

如果 exchange Online 中有本地 Exchange 邮箱以及 Exchange Online 中的云中的一个或多个邮箱，则可以使用 *混合* 设置。 在混合安装中，诸如忙/闲日历共享和邮件路由等功能在本地和云环境中协同工作。 您可能在将邮箱转换为 Exchange Online 时设置了混合设置。 混合环境的设置与 EOP 独立保护的方式不同。

您可以选择一种混合方案，以充分利用基于云的电子邮件为大多数员工。 您可以执行此操作，同时在本地承载一些邮箱; 请参阅。例如，适用于法律部门。

混合设置可能非常复杂，但具有许多好处。 若要了解有关使用 Exchange 设置混合方案的详细信息，请参阅 [Exchange Server 混合部署](https://docs.microsoft.com/Exchange/exchange-hybrid)。
