---
title: 隔离邮件常见问题解答
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
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 管理员可以在 Exchange Online Protection 邮箱中查看有关隔离邮件的常见问题 (解) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 896a83d4a09e8d0fcafeb6885cf2c63b6d8bb045
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826785"
---
# <a name="quarantined-messages-faq"></a>隔离邮件常见问题解答

本主题提供了有关 Exchange Online 中邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的隔离电子邮件的常见问题和解答。

有关反垃圾邮件保护的问题和解答，请参阅"[反垃圾邮件保护常见问题解答"。](anti-spam-protection-faq.md)

有关反恶意软件保护的问题和解答，请参阅"[反恶意软件保护常见问题解答"。](anti-malware-protection-faq-eop.md)

有关反欺骗保护的问题和解答，请参阅反 [欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>如何管理被恶意软件隔离的邮件？

只有管理员可以管理被隔离的恶意软件邮件。 有关详细信息，请参阅 [以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。

## <a name="how-do-i-quarantine-spam"></a>如何隔离垃圾邮件？

默认情况下，按垃圾邮件筛选分类为垃圾邮件或批量电子邮件的邮件会传递到用户邮箱，并移动到"垃圾邮件"文件夹。 但是，您可以创建和配置反垃圾邮件策略来代封垃圾邮件或批量电子邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>如何授予用户访问隔离权限？

用户必须拥有有效帐户才能访问其自己的隔离邮件。 独立 EOP 要求用户在 EOP 中表示为邮件用户 (通过目录同步工具手动创建或) 。 有关在独立 EOP 环境中管理用户的详细信息，请参阅"在[EOP 中管理邮件用户"。](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>最终用户可以访问哪些隔离邮件？

从 2020 年 4 月起，用户在 (月起可以访问) 视为收件人的垃圾邮件、批量邮件和联系人联系人。 最终用户无法访问隔离的恶意软件、高可信度钓鱼或由于将邮件传递到邮件流规则 (也称为传输规则) 中托管隔离操作而被隔离的邮件。 **Deliver the message to the hosted quarantine** 有关访问隔离邮件的用户的详细信息，请参阅以用户 [身份查找并释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>邮件会在隔离邮箱中保留多长时间？

您可以通过使用反垃圾邮件策略配置垃圾邮件、网络钓鱼和批量电子邮件在隔离邮箱中的保留时间。 默认值为 30 天，也是最大值。 有关详细信息，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)

对于被邮件流规则隔离的邮件， **操作 向托管隔离邮箱传递**邮件，邮件会在隔离区中保留 30 天。 您无法配置此持续时间。

此时间段到期后，将删除邮件且不可恢复。

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>我可以一次释放或报告多个被隔离的邮件吗？

在安全与&中心内，一次最多可以选择并发布 100 个邮件。

管理员可以在 Exchange Online PowerShell 中使用 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) 和 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets，从批量查找并释放隔离邮件并批量报告误报。

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>搜索隔离的邮件时是否支持通配符？ 能否搜索特定域的隔离邮件？

安全与合规中心不支持通&通配符。 例如，搜索发件人时，需要指定完整的电子邮件地址。 但是，可以在 Exchange Online PowerShell 中使用通配符或独立 EOP PowerShell。

例如，运行以下命令，以查找来自域身份验证中所有发件人的垃圾邮件contoso.com：

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

然后，运行以下命令将这些邮件释放给所有原始收件人：

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

释放邮件后，则无法重新释放邮件。
