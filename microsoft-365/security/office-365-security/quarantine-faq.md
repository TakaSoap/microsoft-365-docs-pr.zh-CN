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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以查看有关 Exchange Online Protection 中的隔离邮件的常见问题和解答， (EOP) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 342f6b7f27c99352c4e5906799ce463b658e0c87
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203856"
---
# <a name="quarantined-messages-faq"></a>隔离邮件常见问题解答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本主题提供有关在 Exchange Online 中拥有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的隔离电子邮件的常见问题和解答。

有关反垃圾邮件保护的问题和解答，请参阅 [反垃圾邮件保护常见问题解答](anti-spam-protection-faq.md)。

有关反恶意软件保护的问题和解答，请参阅 [反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)。

有关反欺骗保护的问题和解答，请参阅 [反欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>如何管理因恶意软件隔离的邮件？

只有管理员才能管理因恶意软件隔离的邮件。 有关详细信息，请参阅 [以管理员角色管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。

## <a name="how-do-i-quarantine-spam"></a>如何隔离垃圾邮件？

默认情况下，被垃圾邮件筛选分类为垃圾邮件或批量电子邮件的邮件将传递到用户的邮箱，并移动到"垃圾邮件"文件夹。 不过，您可以创建和配置反垃圾邮件策略，以隔离垃圾邮件或批量电子邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>如何授予用户对隔离的访问权限？

用户必须具有有效的帐户，以访问隔离中自己的邮件。 独立 EOP 要求在 EOP 中将用户表示为邮件用户 (通过目录同步邮箱手动创建或) 。 有关在独立 EOP 环境中管理用户的信息，请参阅 [在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。

## <a name="what-messages-can-end-users-access-in-quarantine"></a>最终用户可以在隔离中访问哪些邮件？

自 2020 年 4 (，用户可以访问垃圾邮件、批量) 电子邮件和邮件。这些邮件是收件人。 最终用户无法访问隔离的恶意软件、高可信度网络钓鱼或因邮件流规则中的"将邮件传递至托管隔离"操作而隔离 (也称为传输规则) 。 有关访问隔离邮件的用户详细信息，请参阅以用户模式查找并 [释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>邮件在隔离区中保留多久？

您可以使用反垃圾邮件策略配置垃圾邮件、网络钓鱼和批量电子邮件在隔离区中保留多久。 默认值为 30 天，也是最大值。 有关详细信息，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)

对于由邮件流规则操作 **"** 将邮件发送到托管隔离邮箱"隔离的邮件，这些邮件在隔离中保留 30 天。 无法配置此持续时间。

时间段过期后，邮件将被删除且不可恢复。

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>能否一次释放或报告多个隔离邮件？

在安全&合规中心，一次最多可以选择并释放 100 条消息。

管理员可以使用 Exchange Online PowerShell 或独立 EOP PowerShell 中的 [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) 和 [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) cmdlet 批量查找并释放隔离邮件，并批量报告误报。

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>搜索隔离邮件时是否支持通配符？ 能否搜索特定域的隔离邮件？

安全与合规中心不支持&通配符。 例如，在搜索发件人时，需要指定完整的电子邮件地址。 但是，您可以在 Exchange Online PowerShell 或独立 EOP PowerShell 中使用通配符。

例如，将以下 PowerShell 代码复制到记事本，将文件另存为 .ps1，位置便于您查找 (例如，C:\Data\QuarantineRelease.ps1) 。

然后，在连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 或 [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)后，运行以下命令以运行脚本：

```powershell
& C:\Data\QuarantineRelease.ps1
```

该脚本执行以下操作：

- 查找从 fabrikam 域中所有发件人隔离为垃圾邮件的未发布邮件。 最大结果数为 50，000， (50 页（包含 1000 个结果) ）。
- 将结果保存到 CSV 文件。
- 将匹配的隔离邮件释放给所有原始收件人。

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

释放邮件后，无法再次释放它。