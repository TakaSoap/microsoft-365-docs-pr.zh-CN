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
- m365initiative-defender-office365
description: 管理员可以查看有关 Exchange Online Protection 和 EOP (隔离邮件的常见问题和) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddb5847706aef3d2c3b8ea8cd9a96fd65a9b3d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794408"
---
# <a name="quarantined-messages-faq"></a>隔离邮件常见问题解答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


本主题提供有关在 Exchange Online 中具有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的隔离电子邮件的常见问题和解答。

有关反垃圾邮件保护的问题和解答，请参阅 [反垃圾邮件保护常见问题解答](anti-spam-protection-faq.md)。

有关反恶意软件保护的问题和解答，请参阅 [反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)。

有关反欺骗保护的问题和解答，请参阅 [反欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>如何管理因恶意软件隔离的邮件？

只有管理员才能管理因恶意软件隔离的邮件。 有关详细信息，请参阅以管理员角色 [管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。

## <a name="how-do-i-quarantine-spam"></a>如何隔离垃圾邮件？

默认情况下，通过垃圾邮件筛选被分类为垃圾邮件或批量电子邮件的邮件将传递到用户的邮箱，并移动到"垃圾邮件"文件夹。 但是，您可以创建和配置反垃圾邮件策略来隔离垃圾邮件或批量电子邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>如何授予用户对隔离的访问权限？

用户必须具有有效的帐户，以访问自己的隔离邮件。 独立 EOP 要求在 EOP 中将用户表示为邮件用户 (通过目录同步邮箱手动创建或) 。 有关在独立 EOP 环境中管理用户的信息，请参阅["在 EOP 中管理邮件用户"。](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>最终用户可以在隔离中访问哪些邮件？

自 2020 年 4 (，用户可以访问垃圾邮件、批量) 电子邮件和邮件，包括收件人的网络钓鱼邮件。 最终用户无法访问隔离的恶意软件、高可信度网络钓鱼或因邮件流规则（也称为传输规则 (传输规则）中的托管隔离操作而隔离) 。 有关用户访问隔离邮件详细信息，请参阅"查找隔离邮件并作为用户[释放"。](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>邮件在隔离区中保留多久？

您可以使用反垃圾邮件策略配置垃圾邮件、网络钓鱼和批量电子邮件在隔离区中的保留时间。 默认值为 30 天，也是最大值。 有关详细信息，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)

对于由邮件流规则操作 **"** 将邮件发送到托管隔离邮箱"隔离的邮件，这些邮件在隔离中保留 30 天。 无法配置此持续时间。

在时间段过期后，邮件将被删除且不可恢复。

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>我能否一次释放或报告多个隔离邮件？

在安全&合规中心，一次可以选择并释放最多 100 条消息。

管理员可以使用 Exchange Online PowerShell 或独立 EOP PowerShell 中的 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) 和 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlet 批量查找并释放隔离邮件，并批量报告误报。

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>搜索隔离邮件时是否支持通配符？ 我能否搜索特定域的隔离邮件？

安全与合规中心不支持通配符&通配符。 例如，在搜索发件人时，需要指定完整电子邮件地址。 但是，您可以在 Exchange Online PowerShell 或独立 EOP PowerShell 中使用通配符。

例如，运行以下命令以查找来自域中所有发件人的垃圾邮件隔离contoso.com：

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

然后，运行以下命令以将这些邮件释放给所有原始收件人：

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

释放邮件后，你无法再次释放它。
