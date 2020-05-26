---
title: 隔离的邮件常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 管理员可以在 Exchange Online Protection （EOP）中查看有关隔离邮件的常见问题和解答。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a231e363d5764465547ee1e80cc080c3d7c006c
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351091"
---
# <a name="quarantined-messages-faq"></a>隔离的邮件常见问题解答

本主题提供了有关使用 Exchange Online 中的邮箱的 Microsoft 365 组织的隔离电子邮件、或没有 Exchange Online 邮箱的独立 Exchange Online Protection （EOP）组织的隔离电子邮件的常见问题和解答。

有关反垃圾邮件保护的问题和解答，请参阅[反垃圾邮件保护常见问题解答](anti-spam-protection-faq.md)。

有关反恶意软件保护的问题和解答，请参阅[反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)。

有关反欺骗保护的问题和解答，请参阅[反欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>如何管理为恶意软件隔离的邮件？

只有管理员可以管理隔离的恶意邮件。 有关详细信息，请参阅[以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。

## <a name="how-do-i-quarantine-spam"></a>如何隔离垃圾邮件？

默认情况下，通过垃圾邮件筛选功能分类为垃圾邮件或批量电子邮件的邮件将被传递到用户的邮箱，并移动到 "垃圾邮件" 文件夹。 但您可以创建并配置反垃圾邮件策略以隔离垃圾邮件或批量电子邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>如何向用户授予对隔离的访问权限？

用户必须具有有效的帐户才能访问其自己的隔离邮件。 独立 EOP 要求用户在 EOP 中表示为邮件用户（手动创建或通过目录同步创建）。 有关在独立 EOP 环境中管理用户的详细信息，请参阅[Manage mail users IN EOP](manage-mail-users-in-eop.md)。

## <a name="what-messages-can-end-users-access-in-quarantine"></a>最终用户可以访问隔离中的哪些邮件？

用户可以访问垃圾邮件、批量电子邮件以及（从属于2020年4月）的网络钓鱼邮件。 最终用户无法访问隔离的恶意软件、高可信度的网络钓鱼或因将邮件传递到邮件流规则中**的托管隔离**操作（也称为传输规则）而被隔离的邮件。 有关访问隔离邮件的用户的详细信息，请参阅[以用户的方式查找和释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>邮件在隔离中保存多长时间？

您可以使用反垃圾邮件策略配置在隔离中保存垃圾邮件、网络钓鱼和批量电子邮件的时间长度。 默认值为30天，也是最大值。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)

对于由邮件流规则操作隔离的邮件，会将**邮件传递到托管隔离**，并将邮件保留30天。 您不能配置此持续时间。

时段到期后，邮件将被删除且不可恢复。

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>我是否可以一次释放或报告多个隔离邮件？

在安全 & 合规性中心中，可以一次选择并发布最高100个邮件。

管理员可以使用 Exchange Online PowerShell 或独立 EOP PowerShell 中的[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)和[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlet 来批量查找和释放隔离的邮件，并批量报告误报。

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>搜索隔离邮件时是否支持通配符？ 是否可以搜索特定域的隔离邮件？

安全性 & 合规性中心不支持通配符。 例如，在搜索发件人时，您需要指定完整的电子邮件地址。 不过，您可以在 Exchange Online PowerShell 或独立 EOP PowerShell 中使用通配符。

例如，运行以下命令以查找来自域 contoso.com 中的所有发件人的垃圾邮件隔离邮件：

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

然后，运行以下命令，将这些邮件释放到所有原始收件人：

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

释放邮件后，您将无法再次将其释放。
