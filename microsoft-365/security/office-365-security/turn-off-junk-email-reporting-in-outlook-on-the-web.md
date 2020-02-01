---
title: 关闭 Outlook 网页版中的垃圾邮件报告
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: 作为 Office 365 管理员，您可以关闭用户将电子邮件报告为垃圾邮件的功能。
ms.openlocfilehash: 0bca03786d0335c24e48340e588510f09d6f6a7e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598119"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>关闭 Outlook 网页版中的垃圾邮件报告

您可以使用 web 上的 Outlook （以前称为 "Outlook Web App"）垃圾邮件报告选项，将垃圾邮件、网络钓鱼邮件和非垃圾邮件发送给 Microsoft 进行分析，如在[outlook 网页版中报告垃圾电子邮件和网络钓鱼诈骗](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中所述。 如果不想使用这些选项，管理员可以通过[set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) cmdlet 将其关闭。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

- 估计完成时间：5 分钟

- 您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限，请参阅[Exchange Online 权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)中的 "Outlook on the web 邮箱策略" 条目。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>关闭对 Microsoft 的垃圾邮件、网络钓鱼和非垃圾邮件报告
<a name="sectionSection1"> </a>

首先，运行以下命令以获取您的可用 Outlook 在 web 邮箱策略上的名称：

```
Get-OwaMailboxPolicy | Format-Table Name
```

接下来，使用以下语法在 web 上的 Outlook 中对 Microsoft 启用或禁用垃圾邮件和非垃圾邮件报告：

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

本示例将关闭默认 Outlook web app 邮箱策略中的报告功能：

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

有关语法和参数的详细信息，请参阅[set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)和[set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)。

## <a name="how-do-you-know-this-worked"></a>您如何知道这有效？
<a name="sectionSection2"> </a>

运行**set-owamailboxpolicy**以检查参数值，然后在 web 上为受影响的用户（已对其应用 outlook 网页邮箱策略）打开 Outlook，并验证报告垃圾邮件、网络钓鱼邮件和非垃圾邮件的选项是否不可用。 您仍可以将邮件标记为垃圾邮件、网络钓鱼邮件，而不能将其报告为垃圾邮件。
