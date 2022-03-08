---
title: 将你的域连接到 Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何使用 Microsoft 365 验证域和创建 DNS 记录。
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: 3aa43cd798c26dde8eb064754ae3fb74bd520c29
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312497"
---
# <a name="connect-your-domain-to-microsoft-365"></a>将你的域连接到 Microsoft 365

> [!NOTE]
> 如果你不添加域，组织中的人员将在电子邮件地址中使用 onmicrosoft.com 域，直至你添加为止。 请务必在添加用户前先添加域，以免需要进行两次设置。

如果在下文中找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.yml)。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft

你将从管理中心域设置向导中获取有关 MX 记录的信息。

在托管提供商的网站上，添加一条新的 MX 记录。
请确保将字段设置为以下值：

- 记录类型：`MX`
- 优先级：设置为可用的最高值，通常为 `0`。
- 主机名：`@`
- 指向地址：从管理中心复制值并将其粘贴到此处。
- TTL：`3600`（或提供商的默认值）

保存记录，然后删除任何其他 MX 记录。

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>添加 CNAME 记录以将用户连接到其邮箱

你将从管理中心域设置向导中获取有关 CNAME 记录的信息。

在托管提供商的网站上，添加以下 CNAME 记录。 请确保将每个服务的字段设置为以下值：

- 记录类型：`CNAME (Alias)`
- 主机：将从管理中心复制的值粘贴在此处。
- 指向地址：从管理中心复制值并将其粘贴到此处。
- TTL：`3600`（或提供商的默认值）

## <a name="add-a-txt-record-to-help-prevent-spam"></a>添加 TXT 记录以帮助防止垃圾邮件

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

最后，请返回管理中心域设置向导以完成设置。
