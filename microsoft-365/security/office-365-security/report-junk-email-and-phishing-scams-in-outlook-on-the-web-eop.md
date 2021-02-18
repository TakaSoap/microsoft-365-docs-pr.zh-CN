---
title: 在 Outlook 网页中报告垃圾邮件和网络钓鱼电子邮件
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
description: 管理员可以了解 Exchange Online 中的 Outlook 网页版 (Outlook Web App) 中的内置垃圾邮件、非垃圾邮件和网络钓鱼电子邮件报告选项，以及如何为用户禁用这些报告选项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0bd2da9b774b3557ebb820102ba86c17ebe44c69
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289217"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>在 Exchange Online 的 Outlook 网页版中报告垃圾邮件和网络钓鱼电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，可以使用 Outlook 网页版中的内置报告选项 (以前称为 Outlook Web App) 将误报 (邮件标记为垃圾邮件) 、漏报 (允许的) 和钓鱼邮件提交到 Exchange Online Protection (EOP) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议您使用安全与合规中心&门户。 有关详细信息，请参阅使用管理员提交将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)

- 管理员可以禁用或启用用户在 Outlook 网页中向 Microsoft 报告邮件的能力。 有关详细信息，请参阅本文稍后介绍的 ["在 Outlook 网页](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 版中禁用或启用垃圾邮件报告"部分。

- 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅 [用户提交策略](user-submission.md)。

- 有关向 Microsoft 报告邮件详细信息，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>报告 Outlook 网页中的垃圾邮件和网络钓鱼邮件

1. 对于收件箱或其他任何电子邮件文件夹中的邮件（垃圾邮件除外），请使用以下任一方法来报告垃圾邮件和网络钓鱼邮件：

   - 选择邮件 **，单击工具栏** 上的"垃圾邮件"，然后选择"**垃圾邮件**"或"网络钓鱼 **"。**

     ![从功能区报告垃圾邮件或网络钓鱼电子邮件](../../media/owa-report-junk.png)

   - 选择一个或多个邮件，右键单击，然后选择 **"标记为垃圾邮件"。**

2. 在出现的对话框中，单击"报告 **"。** 如果改变主意，请单击"**不报告"。**

   |垃圾邮件|网络钓鱼|
   |:---:|:---:|
   |![报告为垃圾邮件对话框](../../media/owa-report-as-junk-dialog.png)|![报告为网络钓鱼对话框](../../media/owa-report-as-phishing-dialog.png)|

3. 选定的邮件将发送给 Microsoft 进行分析。 若要确认已提交的邮件，请打开您的“已发送邮件”文件夹查看已提交的邮件。

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>从 Outlook 网页中的"垃圾邮件"文件夹报告非垃圾邮件和网络钓鱼邮件

1. 在"垃圾邮件"文件夹中，使用以下任一方法来报告垃圾邮件误报或网络钓鱼邮件：

   - 选择邮件，单击工具栏 **上的"非** 垃圾邮件"，然后选择"**非垃圾邮件**"或"网络钓鱼 **"。**

     ![从功能区报告非垃圾邮件或钓鱼电子邮件](../../media/owa-report-not-junk.png)

   - 选择一个或多个邮件，右键单击，然后选择 **"标记为非垃圾邮件"。**

2. 在出现的对话框中，读取信息并单击"报告 **"。** 如果改变主意，请单击"**不报告"。**

   |非垃圾邮件|网络钓鱼|
   |:---:|:---:|
   |![报告为非垃圾邮件对话框](../../media/owa-report-as-not-junk-dialog.png)|![报告为网络钓鱼对话框](../../media/owa-report-as-phishing-dialog.png)|

3. 选定的邮件将发送给 Microsoft 进行分析。 若要确认已提交的邮件，请打开您的“已发送邮件”文件夹查看已提交的邮件。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>在 Outlook 网页中禁用或启用垃圾邮件报告

默认情况下，用户可以向 Microsoft 报告垃圾邮件误报、漏报邮件和网络钓鱼邮件，以在 Outlook 网页中进行分析。 管理员可以在 Exchange Online PowerShell 中配置 Outlook 网页版邮箱策略，以防止用户向 Microsoft 报告垃圾邮件误报和垃圾邮件漏报。 无法禁用用户向 Microsoft 报告网络钓鱼邮件的能力。

### <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 您需要在 Exchange Online 中分配权限，然后才能执行本文中的过程。 具体来说，您需要 **收件人策略** 或 **邮件收件人** 角色，这些角色默认分配给组织管理和 **收件人管理** 角色组。 有关 Exchange Online 中的角色组详细信息，请参阅 [Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 中的权限和修改 Exchange [Online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。

- 每个组织都有一个名为 OwaMailboxPolicy-Default 的默认策略，但您可以创建自定义策略。 自定义策略应用于默认策略之前的范围用户。 有关 Outlook 网页版邮箱策略详细信息，请参阅 [Exchange Online 中的 Outlook 网页版邮箱策略](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。

- 禁用垃圾邮件报告不会删除在 Web 上的 Outlook 中将邮件标记为垃圾邮件或不垃圾邮件的能力。 选择"垃圾邮件"文件夹中的邮件并单击 **"非** 垃圾邮件"仍将邮件 \> 移回收件箱。 选择任何其他电子邮件文件夹中的邮件并单击 **"垃圾邮件**"仍将 \> 邮件移动到"垃圾邮件"文件夹中。 不再可用的是向 Microsoft 报告邮件的选项。

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>使用 Exchange Online PowerShell 禁用或启用 Outlook 网页版中的垃圾邮件报告

1. 若要查找现有 Outlook 网页邮件邮箱策略和垃圾邮件报告状态，请运行以下命令：

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. 若要禁用或启用 Outlook 网页中的垃圾邮件报告，请使用以下语法：

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

有关语法和参数的详细信息，请参阅[Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy)和[Set-OwaMailboxPolicy。](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证您是否已成功启用或禁用 Outlook 网页中的垃圾邮件报告，请使用下列任一步骤：

- 在 Exchange Online PowerShell 中，运行以下命令并验证 **ReportJunkEmailEnabled** 属性值：

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 在 Outlook 网页中打开受影响的用户的邮箱，在收件箱中选择一封邮件，单击"垃圾邮件"并验证向 Microsoft 报告邮件的 \> 提示是否显示。<sup>\*</sup>

- 在 Outlook 网页中打开受影响的用户的邮箱，在"垃圾邮件"文件夹中选择一封邮件，单击"垃圾邮件"并验证向 Microsoft 报告邮件的 \> 提示是否显示。<sup>\*</sup>

<sup>\*</sup> 用户可以隐藏提示以报告邮件，同时仍报告邮件。 若要在 Outlook 网页中检查此设置，请：

1. 单击 **"Web** ![ 上的设置 Outlook 设置"图标 ](../../media/owa-settings-icon.png) \> **"查看所有 Outlook 设置** \> **垃圾邮件"。**
2. 在 **"报告** "部分，验证值 **：在发送报告之前询问我**。

   ![Outlook 网页垃圾邮件报告设置](../../media/owa-junk-email-reporting-options.png)
