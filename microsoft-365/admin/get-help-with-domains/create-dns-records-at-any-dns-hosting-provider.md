---
title: 添加 DNS 记录以连接你的域
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: 验证域和更新注册机构的帐户中的 DNS 记录，将任何 DNS 托管提供商的域连接到 Microsoft 365。
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
ms.openlocfilehash: ae8dc1c1d2f603e81d2affd723df2be460a873de
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60164808"
---
# <a name="add-dns-records-to-connect-your-domain"></a>添加 DNS 记录以连接你的域

如果是从第三方托管提供商处购买的域，则可以通过更新注册机构帐户中的 DNS 记录将其连接到 Microsoft 365。

执行完以下步骤后，你的域将在向你出售域的主机中保持注册，但 Microsoft 365 可将其用于你的电子邮件地址（如 user@yourdomain.com）和其他服务。

如果你不添加域，组织中的人员将在电子邮件地址中使用 onmicrosoft.com 域，直至你添加为止。 请务必在添加用户前先添加域，以免需要进行两次设置。

如果在下文中找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.yml)。

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>步骤 1：添加 TXT 或 MX 记录以验证你是否拥有相应的域

### <a name="recommended-verify-with-a-txt-record"></a>建议：使用 TXT 记录进行验证

首先，你需要证明自己拥有要添加到 Microsoft 365 的域。

1. 登录到 Microsoft 365 管理中心，然后选择“**全部显示**” > “**设置**” > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">“**域**”</a>。
2. 在新的浏览器标签页或窗口中，登录 DNS 托管提供商网站，然后找到管理 DNS 设置（如“区域文件设置”、“管理域”、“域管理器”和“DNS 管理器”）的位置。
3. 转到提供商的“DNS 管理器”页面，然后将管理中心中指示的 TXT 记录添加到域中。

   添加此记录不会影响现有电子邮件或其他服务，并且可在域连接到 Microsoft 365 后，安全地将其删除。

   示例：

   - TXT 名称：`@`
   - TXT 值：MS=ms########（管理中心的唯一 ID）
   - TTL：`3600`（或提供商的默认值）

4. 保存记录，返回管理中心，然后选择“**验证**”。 对记录更改进行注册通常需要 15 分钟左右，但有时可能需要更长时间。 请稍等片刻并多尝试几次，以便获得所做的更改。

当 Microsof 找到正确的 TXT 记录时，表明域已通过验证。

### <a name="verify-with-an-mx-record"></a>使用 MX 记录进行验证

如果注册机构不支持添加 TXT 记录，可通过添加 MX 记录进行验证。

1. 登录到 Microsoft 365 管理中心，然后选择“**全部显示**” > “**设置**” > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">“**域**”</a>。
2. 在新的浏览器标签页或窗口中，登录 DNS 托管提供商网站，然后找到管理 DNS 设置（如“区域文件设置”、“管理域”、“域管理器”和“DNS 管理器”）的位置。
3. 转到提供商的“DNS 管理器”页面，然后将管理中心中指示的 MX 记录添加到域中。

此 MX 记录的 **优先级** 必须是域的所有现有 MX 记录中最高的。 否则，它可能会干扰发送和接收电子邮件。 域验证完成后，应立即删除此记录。

请确保将字段设置为以下值：

- 记录类型：`MX`
- 优先级：设置为尚未使用的任何大值。
- 主机名：`@`
- 指向地址：从管理中心复制值并将其粘贴到此处。
- TTL：`3600`（或提供商的默认值）

当 Microsof 找到正确的 MX 记录时，表明域已通过验证。

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>步骤 2：添加 DNS 记录以连接 Microsoft 服务

在新的浏览器标签页或窗口中，登录 DNS 托管提供商网站，然后找到管理 DNS 设置（如“区域文件设置”、“管理域”、“域管理器”和“DNS 管理器”）的位置。

根据要启用的服务，你将添加多个不同类型的 DNS 记录。

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>添加针对电子邮件（Outlook、Exchange Online）的 MX 记录

**准备工作：** 如果用户已经拥有使用你的域的电子邮件地址（如 user@yourdomain.com），请先在管理中心中创建其帐户，然后再设置 MX 记录。 这样一来，他们便能够继续接收电子邮件。 更新你的域的 MX 记录时，使用你的域的任何人的所有新电子邮件现在都将发往 Microsoft 365。 你已拥有的任何电子邮件将保留在你当前的电子邮件主机中，除非你决定[将电子邮件和联系人迁移到 Microsoft 365。](../setup/migrate-email-and-contacts-admin.md)

你将从管理中心域设置向导中获取有关 MX 记录的信息。

在托管提供商的网站上，添加一条新的 MX 记录。
请确保将字段设置为以下值：

- 记录类型：`MX`
- 优先级：设置为可用的最高值，通常为 `0`。
- 主机名：`@`
- 指向地址：从管理中心复制值并将其粘贴到此处。
- TTL：`3600`（或提供商的默认值）

保存记录，然后删除任何其他 MX 记录。

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>添加 CNAME 记录以连接其他服务（Teams、Exchange Online、AAD 和 MDM）

你将从管理中心域设置向导中获取有关 CNAME 记录的信息。

在托管提供商的网站上，为要连接的每个服务添加 CNAME 记录。
请确保将每个服务的字段设置为以下值：

- 记录类型：`CNAME (Alias)`
- 主机：将从管理中心复制的值粘贴在此处。
- 指向地址：从管理中心复制值并将其粘贴到此处。
- TTL：`3600`（或提供商的默认值）

### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>添加或编辑 SPF TXT 记录，以防出现垃圾邮件（Outlook、Exchange Online）

**准备工作：** 如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。 相反，可以在托管提供商网站上将所需的 Microsoft 365 值添加到当前记录，这样就拥有同时包含两组值的 *单个* SPF 记录。

在托管提供商的网站上，编辑现有 SPF 记录或创建 SPF 记录。
请确保将字段设置为以下值：

- 记录类型：`TXT (Text)`
- 主机：`@`
- TXT 值：`v=spf1 include:spf.protection.outlook.com -all`
- TTL：`3600`（或提供商的默认值）

保存记录。

使用以下任一 [SPF 验证工具](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)验证 SPF 记录。

SPF 旨在帮助防骗，但有些骗术是 SPF 所无法防范的。 为了防范这些骗术，在设置 SPF 后，还应为 Microsoft 365 设置 DKIM 和 DMARC。

若要开始进行设置，请参阅[使用 DKIM 验证从 Microsoft 365 中的域发送的出站电子邮件](../../security/office-365-security/use-dkim-to-validate-outbound-email.md)和[使用 DMARC 验证 Microsoft 365 中的电子邮件](../../security/office-365-security/use-dmarc-to-validate-email.md)。

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>为通信服务（Teams、Skype for Business）添加 SRV 记录

在托管提供商的网站上，为要连接的每个服务添加 SRV 记录。
请确保将每个服务的字段设置为以下值：

- 记录类型：`SRV (Service)`
- 名称：`@`
- 目标：从管理中心复制值并将其粘贴到此处。
- 协议：从管理中心复制值并将其粘贴到此处。
- 服务：从管理中心复制值并将其粘贴到此处。
- 优先级：`100`
- 权重：`1`
- 端口：从管理中心复制值并将其粘贴到此处。
- TTL：`3600`（或提供商的默认值）

保存记录。

#### <a name="srv-record-field-restrictions-and-workarounds"></a>SRV 记录字段限制和解决方法

某些托管提供商会对 SRV 记录中的字段值施加限制。 下面是应对这些限制的一些常见解决方法。

##### <a name="name"></a>名称

如果托管提供商不允许将此字段设置为 **@**，请将其留空。 *仅* 当托管提供商为“服务”和“协议”值提供了单独的字段时，才能使用此方法。 否则，请查看下面的“服务和协议”说明。

##### <a name="service-and-protocol"></a>服务和协议

如果托管提供商没有为 SRV 记录提供这些字段，则必须在记录的“**名称**”字段中指定“**服务**”和“**协议**”值。 （注意：根据你所选择的托管提供商，“**名称**”字段可能会有其他称呼，如：“**主机**”、“**主机名**”或“**子域**”。）若要添加这些值，可创建一个字符串，并用圆点分隔这些值。

例如：`_sip._tls`

##### <a name="priority-weight-and-port"></a>优先级、权重和端口

如果托管提供商没有为 SRV 记录提供这些字段，则必须在记录的“**目标**”字段中指定它们的值。 （注意：根据你所选择的托管提供商，“**目标**”字段可能会有其他称呼，如：“**内容**”、“**IP 地址**”或“**目标主机**”。）

若要添加这些值，请创建一个字符串，并用空格分隔这些值且 *有时以圆点结尾*（如果你不确定，请与你的提供商进行核实）。值必须采用此顺序包含：优先级、权重、端口、目标。

- 示例 1：`100 1 443 sipdir.online.lync.com.`
- 示例 2：`100 1 443 sipdir.online.lync.com`

## <a name="related-content"></a>相关内容

[更改名称服务器以使用任意域注册机构设置 Microsoft 365](change-nameservers-at-any-domain-registrar.md)（文章）\
[查找并修复添加域或 DNS 记录之后出现的问题](find-and-fix-issues.md)（文章）\
[管理域](/admin)（链接页）
