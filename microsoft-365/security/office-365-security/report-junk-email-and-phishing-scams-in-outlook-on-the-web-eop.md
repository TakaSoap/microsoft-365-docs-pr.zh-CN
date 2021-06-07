---
title: 报告 Web 上Outlook垃圾邮件和钓鱼电子邮件
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online 中 Outlook 网页 (Outlook Web App) 中的内置垃圾邮件报告选项、非垃圾邮件和网络钓鱼电子邮件报告选项，以及如何为用户禁用这些报告选项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788303"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>在电子邮件中报告Outlook网页中的垃圾邮件Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，如果邮箱位于 Exchange Online 或本地邮箱使用混合新式身份验证，可以将[](../../enterprise/hybrid-modern-auth-overview.md)误报 (标记为垃圾邮件) 、漏报 (允许的) 错误电子邮件以及网络钓鱼邮件提交到 Exchange Online Protection (EOP) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

> [!IMPORTANT]
> 对于用户提交，我们建议使用报告邮件外接程序或报告网络钓鱼外接程序。 有关详细信息，请参阅[启用报告邮件或报告钓鱼外接程序](./enable-the-report-message-add-in.md)。我们不建议在应用内使用内置Outlook，因为它不使用用户[提交策略](./user-submission.md)。

- 如果你是拥有多个邮箱Exchange Online管理员，我们建议你使用安全与合规中心&提交门户。 有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)

- 管理员可以禁用或启用用户在 Web 上向 Microsoft 报告Outlook功能。 有关详细信息，请参阅本文稍后介绍的在 web Outlook[中](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)禁用或启用垃圾邮件报告部分。

- 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。

- 有关向 Microsoft 报告邮件的信息，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>禁用或启用 Web 上Outlook垃圾邮件报告

默认情况下，用户可以将垃圾邮件误报、漏报和钓鱼邮件报告给 Microsoft，以便Outlook中进行分析。 管理员可以在 PowerShell Outlook Web 邮箱策略Exchange Online，以防止用户向 Microsoft 报告垃圾邮件误报和垃圾邮件漏报。 无法禁用用户向 Microsoft 报告网络钓鱼邮件的能力。

### <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您需在 Exchange Online权限，然后才能执行本文中的过程。 具体来说，您需要 **收件人策略** 或 **邮件收件人** 角色，这些角色默认分配给组织管理角色组和 **收件人** 管理角色组。 有关角色组中角色组Exchange Online，请参阅 Exchange Online[中的权限](/exchange/permissions-exo/permissions-exo)和修改[角色Exchange Online。](/Exchange/permissions-exo/role-groups#modify-role-groups)

- 每个组织都有一个名为 OwaMailboxPolicy-Default 的默认策略，但您可以创建自定义策略。 自定义策略应用于默认策略之前的范围用户。 有关 Web 邮箱策略Outlook，请参阅 Outlook 中的[Web 邮箱策略Exchange Online。](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- 禁用垃圾邮件报告不会删除在 Web 上的垃圾邮件中将Outlook标记为垃圾邮件的能力。 选择"垃圾邮件"文件夹中的邮件并单击"**非** 垃圾邮件""非垃圾邮件"仍将 \> 该邮件移回收件箱。 选择任何其他电子邮件文件夹中的邮件并单击 **"垃圾邮件**"仍将 \> 该邮件移动到"垃圾邮件"文件夹中。 不再可用的是向 Microsoft 报告邮件的选项。

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>使用 Exchange Online PowerShell 禁用或启用 Web 上Outlook垃圾邮件报告

1. 若要查找现有Outlook Web 邮箱策略和垃圾邮件报告状态，请运行以下命令：

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. 若要在 Web 上的Outlook或启用垃圾邮件报告，请使用以下语法：

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   本示例在默认策略中禁用垃圾邮件报告。

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   此示例在名为 Contoso Managers 的自定义策略中启用垃圾邮件报告。

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

有关语法和参数的详细信息，请参阅[Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy)和[Set-OwaMailboxPolicy。](/powershell/module/exchange/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证您是否已成功启用或禁用 Web 上的Outlook垃圾邮件报告，请执行以下步骤之一：

- 在 Exchange Online PowerShell 中，运行以下命令并验证 **ReportJunkEmailEnabled** 属性值：

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 在 Web 上的 Outlook 中打开受影响的用户的邮箱，选择"收件箱"中的邮件，单击"垃圾邮件"并验证向 Microsoft 报告邮件的 \> 提示是否显示。<sup>\*</sup>

- 在 Web 上的 Outlook 中打开受影响的用户的邮箱，选择"垃圾邮件"文件夹中的邮件，单击"垃圾邮件"并验证向 Microsoft 报告邮件的 \> 提示是否显示。<sup>\*</sup>

<sup>\*</sup> 用户可以隐藏报告邮件的提示，同时仍报告邮件。 若要在 Web Outlook中检查此设置：

1. 单击 ![ 设置Outlook"Web 设置"图标"查看所有Outlook ](../../media/owa-settings-icon.png) \> **设置** \> **垃圾邮件"。**
2. 在" **报告** "部分，验证值： **在发送报告之前询问我**。

   ![Outlook垃圾邮件报告设置](../../media/owa-junk-email-reporting-options.png)
