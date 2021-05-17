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
description: 中国使用由世纪Office 365的管理员可了解如何使用独立 Exchange Online Protection (EOP) 保护其本地邮箱。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4258d64721fc2042297bb15eaeecafa90dcf4bc1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203865"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>在中国使用独立 EOP 保护本地邮箱

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 本文仅适用于由世纪Office 365中国运营的系列文章。

即使您计划在本地托管部分或所有邮箱，您仍可以使用 EOP Exchange Online Protection (邮箱) 。 若要配置连接器，你的帐户必须是全局管理员Exchange组织管理角色组 (公司管理员) 。 有关这些权限Office 365权限Exchange，请参阅在由世纪Office 365[中分配管理员角色](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet)。 如果所有 Exchange邮箱都位于本地，请按照以下步骤设置 EOP 服务。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>步骤 1：使用Microsoft 365中心添加和验证域

1. 在Microsoft 365管理中心中，导航到"设置"以将域添加到服务。

2. 按照门户中的步骤将适用的 DNS 记录添加到 DNS 托管提供商，以验证域所有权。

> [!TIP]
> 将域和用户添加到由[世纪](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet)Office 365运营的域和在管理 DNS 记录时为 Office 365 创建 DNS 记录是向服务添加域和配置[DNS](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet)时参考的有用资源。

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>步骤 2：添加收件人并配置域类型

在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。 执行此操作有几种方法，如[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中所述。 此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。 有关 DBEB 详细信息，请参阅使用 [基于目录的边缘阻止拒绝发送给无效收件人的邮件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步骤 3：使用 EAC 设置邮件流

在能使邮件在 EOP 和你的内部部署邮件服务器间流动的 Set up connectors to route mail between Office 365 and your own email servers (EAC) 中创建连接器。 有关详细说明，请参阅 Configure [mail flow using connectors in Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

 如何判断此任务生效？

 请参阅[通过验证您的邮件连接器测试Office 365流](/exchange/mail-flow-best-practices/test-mail-flow)。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>步骤 4：允许入站端口 25 SMTP 访问

配置连接器后，请等待 72 小时，允许准备 DNS 记录更新。 然后，将防火墙或邮件服务器的入站端口-25 SMTP 流量限制为仅接受来自 EOP 数据中心的邮件，特别是来自 URL 中列出的 IP 地址和[Office 365。](../../enterprise/managing-office-365-endpoints.md) 此操作将通过限制可以接收的入站邮件范围，保护内部部署环境。 此外，如果邮件服务器上的设置控制了允许为邮件中继连接的 IP 地址，也要更新这些设置。

> [!TIP]
> 将 SMTP 服务器上的设置配置 60 秒的连接时间。此设置在大多数情况下都可接受，例如，在发送带有很大附件的邮件时允许有些延迟。

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>步骤 5：确保垃圾邮件已路由到每个用户的"垃圾邮件"文件夹

为确保垃圾邮件 (垃圾邮件) 正确路由到每个用户的"垃圾邮件"文件夹，必须执行几个配置步骤。 配置独立 EOP 以将垃圾邮件发送到混合环境中垃圾邮件文件夹中 [提供了这些步骤](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 如果您不想将邮件移动到每个用户的"垃圾邮件"文件夹，您可以选择其他操作，通过编辑反垃圾邮件策略 (也称为内容筛选器策略) 。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>步骤 6：使用Microsoft 365中心将 MX 记录指向 EOP

按照 Office 365 域配置步骤更新你的域的 MX 记录，以便于你的入站电子邮件能够通过 EOP。 有关详细信息，可以在管理 DNS 记录时再次引用为Office 365[创建 DNS 记录](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet)。

如何判断此任务生效？

 请参阅[通过验证您的邮件连接器测试Office 365流](/exchange/mail-flow-best-practices/test-mail-flow)。

此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：

- In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.

- 将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。

- 如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>不太常见：具有本地邮箱和云中的邮箱的混合设置

如果Exchange本地邮箱和云中的一个或多个Exchange Online，则具有 *混合* 设置。 在混合设置中，忙/闲日历共享和邮件路由等功能在本地和云环境中协同工作。 在将邮箱转换到邮箱时，您可能具有混合Exchange Online。 混合环境的设置方式与 EOP 独立保护不同。

你可以选择混合方案来利用大多数员工的基于云的电子邮件。 您可以在本地托管一些邮箱时进行此操作;例如，对于法律部门。

混合设置可能很复杂，但有很多好处。 若要了解有关使用混合部署设置混合方案Exchange，请参阅Exchange Server[部署](/Exchange/exchange-hybrid)。