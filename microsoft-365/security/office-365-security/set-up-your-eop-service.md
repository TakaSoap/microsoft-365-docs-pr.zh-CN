---
title: 设置独立 EOP 服务
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 管理员可以了解如何设置独立 Exchange Online Protection (EOP) 保护本地电子邮件环境。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bbad39475f87be27a83edc0c27e2bbe46f8e39ac
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203896"
---
# <a name="set-up-your-standalone-eop-service"></a>设置独立 EOP 服务

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
-  [独立 Exchange Online Protection](exchange-online-protection-overview.md)

本主题介绍如何设置独立 Exchange Online Protection (EOP) 。 如果您已从 Office 365 域向导登录到这里，则假如您不想使用 Exchange Online Protection，请返回到 Office 365 域向导。 若要详细了解如何配置连接器，请参阅[Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

> [!NOTE]
> 此主题假设你拥有内部部署邮箱，并且想使用 EOP 对其进行保护，这称为独立方案。 如果要使用 Exchange Online 在云中托管所有邮箱，则不必完成本文的所有步骤。 转到比较 [Exchange Online](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) 计划以注册和购买云邮箱。
>
> 如果你想在内部部署和云中分别托管一部分邮箱，这称为混合方案。 这需要更高级的邮件流设置。 [Exchange Server混合部署介绍了](/exchange/exchange-hybrid) 混合邮件流，并提供了指向显示如何设置它的资源的链接。

## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

- 估计完成该任务的时间：1 小时

- 您需在 Exchange Online Protection 中获得权限，然后才能执行本文中的过程。 具体来说，您需要远程域和接受域角色，默认情况下，该角色 (全局管理员组) 组和邮件流 **管理员** 角色组。 有关详细信息，请参阅 [Permissions in standalone EOP](feature-permissions-in-eop.md) 和 [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 如果你还未注册 EOP，请访问 [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) 并选择购买或者试用服务。

- 有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅[Keyboard shortcuts for the Exchange admin center in Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 是否有任何疑问？ 请在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 论坛中寻求帮助。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>步骤 1：使用 Microsoft 365 管理中心添加和验证域

1. 在 [Microsoft 365 管理中心](../../admin/admin-overview/about-the-admin-center.md)中，转到" **设置** "以将域添加到服务。

2. 按照该步骤将适用的 DNS 记录添加到您的 DNS 托管提供程序以验证域所有权。

> [!TIP]
> [将域添加到 Office 365](../../admin/setup/add-domain.md) 和在任何 DNS 托管提供商处为 [Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 创建 DNS 记录是当您将域添加到服务和配置 DNS 时要引用的有用资源。

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>步骤 2：添加收件人，并选择性启用 DBEB

在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。执行此操作有几种方法，如[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中所述。此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。有关 DBEB 的详细信息，请参阅[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步骤 3：使用 EAC 设置邮件流

在能使邮件在 EOP 和你的内部部署邮件服务器间流动的 Set up connectors to route mail between Office 365 and your own email servers (EAC) 中创建连接器。 有关详细说明，请参阅设置 [连接器以在 Microsoft 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)和您自己的电子邮件服务器之间路由邮件。

### <a name="how-do-you-know-this-task-worked"></a>如何判断此任务生效？

检查服务与环境之间的邮件流。 有关详细信息，请参阅通过验证 [Microsoft 365](/exchange/mail-flow-best-practices/test-mail-flow)连接器测试邮件流。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>步骤 4：允许入站端口 25 SMTP 访问

配置连接器后，请等待 72 小时以允许传播 DNS 记录更新。 在此之后，限制防火墙或邮件服务器上的入站端口-25 SMTP 通信，以仅接受来自 EOP 数据中心的邮件，特别是来自 [Exchange Online Protection IP 地址](../../enterprise/urls-and-ip-address-ranges.md)中列出的 IP 地址的邮件。 此操作将通过限制可以接收的入站邮件范围，保护内部部署环境。 此外，如果邮件服务器上的设置控制了允许为邮件中继连接的 IP 地址，也要更新这些设置。

> [!TIP]
> 将 SMTP 服务器上的设置配置 60 秒的连接时间。 此设置在大多数情况下都是可接受的，例如，如果邮件发送了较大的附件，则允许一些延迟。

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>步骤 5：确保垃圾邮件已路由到每个用户的"垃圾邮件"文件夹

为确保垃圾邮件 (垃圾邮件) 正确路由到每个用户的"垃圾邮件"文件夹，必须执行几个配置步骤。 配置独立 EOP 以将垃圾邮件发送到混合环境中垃圾邮件文件夹中 [提供了这些步骤](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

如果您不想将邮件移动到每个用户的"垃圾邮件"文件夹，则通过编辑反垃圾邮件策略可以选择其他操作。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>步骤 6：使用 Microsoft 365 管理中心将 MX 记录指向 EOP

按照域配置步骤更新域的 MX 记录，以便入站电子邮件通过 EOP。 请务必将你的 MX 记录直接指向 EOP 而不是让第三方筛选服务将电子邮件中继到 EOP。 有关详细信息，请再次参阅[为 Office 365 创建 DNS 记录](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。

> [!NOTE]
> 如果必须将 MX 记录指向位于 EOP 前面的另一台服务器或服务，请参阅增强的 [Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)中的连接器筛选。

### <a name="how-do-you-know-this-task-worked"></a>如何判断此任务生效？

此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：

- 检查服务与环境之间的邮件流。 有关详细信息，请参阅通过验证 [Microsoft 365](/exchange/mail-flow-best-practices/test-mail-flow)连接器测试邮件流。

- 将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。

- 如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。

> [!TIP]
> 完成安装后，您无需进行其他操作，EOP 即可删除垃圾邮件和恶意软件。 EOP 会自动删除垃圾邮件和恶意软件。 但是，您可以根据业务需求微调设置。 有关详细信息，请参阅 [Office 365](anti-spam-and-anti-malware-protection.md) 中的反垃圾邮件和反恶意软件保护和 [配置欺骗智能](learn-about-spoof-intelligence.md)。
>
> 现在服务正在运行，我们建议阅读 Best [practices for configuring EOP](best-practices-for-configuring-eop.md)，其中介绍了设置 EOP 后的建议设置和注意事项。