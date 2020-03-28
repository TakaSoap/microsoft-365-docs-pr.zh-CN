---
title: '在 Outlook 网页版中报告垃圾电子邮件和钓鱼行为 '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Office 365 具有 Exchange Online 邮箱的用户可以使用 web 上的 Outlook （Outlook Web App）将垃圾邮件、非垃圾邮件和网络钓鱼邮件提交给 Microsoft 进行分析。
ms.openlocfilehash: c6aba9a701b23be4bbbe508825a55c6438461928
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033675"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a>在 Office 365 中的 Outlook 网页上报告垃圾邮件和网络钓鱼电子邮件

如果你是使用 Exchange Online 邮箱的 Office 365 客户，则可以使用 web 上的 Outlook （以前称为 Outlook Web App）中的内置报告选项来提交误报（好的电子邮件被标记为垃圾邮件）、漏报（允许使用错误的电子邮件）和到 Exchange Online Protection （EOP）的网络钓鱼邮件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，需要知道什么？

- 如果您是使用 Exchange Online 邮箱的 Office 365 组织中的管理员，我们建议您在 Office 365 安全性 & 合规性中心中使用提交门户。 有关详细信息，请参阅[使用管理员提交将可疑的垃圾邮件、网络钓鱼、url 和文件提交给 Microsoft](admin-submission.md)。

- 管理员可以在 Outlook 网页版中禁用或启用用户将邮件报告给 Microsoft 的功能。 有关详细信息，请参阅本主题后面的在[Outlook 网页版中禁用或启用垃圾邮件报告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)一节。

- 有关将邮件报告给 Microsoft 的详细信息，请参阅[在 Office 365 中向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>在 Outlook 网页网络中报告垃圾邮件和网络钓鱼邮件

1. 对于收件箱中的邮件或除垃圾邮件以外的任何其他电子邮件文件夹中的邮件，请使用下列方法之一来报告垃圾邮件和网络钓鱼邮件：

   - 选择邮件，单击工具栏上的 "**垃圾**邮件"，然后选择 "**垃圾**邮件" 或 "**网络钓鱼**"。

     ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/owa-report-junk.png)

   - 选择一个或多个邮件，单击鼠标右键，然后选择 "**标记为垃圾**邮件"。

2. 在出现的对话框中，单击 "**报告**"。 如果你改变主意，请单击 "**不报告**"。

   !["报告为垃圾邮件" 对话框](../../media/owa-report-as-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/owa-report-as-phishing-dialog.png)

3. 选定的邮件将发送给 Microsoft 进行分析。 若要确认已提交的邮件，请打开您的“已发送邮件”**** 文件夹查看已提交的邮件。

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>从 web 上的 Outlook 中的 "垃圾邮件" 文件夹报告非垃圾邮件和网络钓鱼邮件

1. 在 "垃圾邮件" 文件夹中，使用以下任一方法报告垃圾邮件误报或网络钓鱼邮件：

   - 选择邮件，单击工具栏上的 "**非垃圾**邮件"，然后选择 "**不垃圾**邮件" 或 "**网络钓鱼**"。

     ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/owa-report-not-junk.png)

   - 选择一个或多个邮件，单击鼠标右键，然后选择 "**标记为非垃圾**邮件"。

2. 在出现的对话框中，阅读信息，然后单击 "**报告**"。 如果你改变主意，请单击 "**不报告**"。

   !["报告为非垃圾邮件" 对话框](../../media/owa-report-as-not-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/owa-report-as-phishing-dialog.png)

3. 选定的邮件将发送给 Microsoft 进行分析。 若要确认已提交的邮件，请打开您的“已发送邮件”**** 文件夹查看已提交的邮件。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>在 web 上的 Outlook 中禁用或启用垃圾电子邮件报告

默认情况下，用户可以在 web 上的 Outlook 中将垃圾邮件误报、漏报和网络钓鱼邮件报告给 Microsoft 进行分析。 管理员可以使用 Exchange Online 中的 web 邮箱策略上的 Outlook 来禁用或启用此功能，但只能在 Exchange Online PowerShell 中使用。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

- 必须先分配有权限，然后才能执行这些过程。 特别是，您需要 Exchange Online 中的**收件人策略**或**邮件收件人**角色，默认情况下，这些角色分配给**组织管理**角色组和**收件人管理**角色组。 有关 Exchange Online 中的角色组的详细信息，请参阅[Modify role groups In Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。

- 每个组织都有一个名为 "Set-owamailboxpolicy" 的默认策略-默认值，但您可以创建自定义策略。 在默认策略之前，自定义策略将应用于作用域内的用户。 有关 Outlook 网页版邮箱策略的详细信息，请参阅[Exchange Online 中的 "outlook on web 邮箱策略"](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。

1. 若要在 web 邮箱策略和 "垃圾邮件报告" 状态中查找您的现有 Outlook，请运行以下命令：

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. 若要在 web 上的 Outlook 中禁用或启用垃圾邮件报告，请使用以下语法：

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   本示例禁用默认策略中的垃圾邮件报告。

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   本示例在名为 Contoso 经理的自定义策略中启用了垃圾邮件报告。

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

有关语法和参数的详细信息，请参阅[set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)和[set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)。

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证您是否已成功启用或禁用 web 上的 Outlook 中的垃圾邮件报告功能，请执行以下任一步骤：

- 在 Exchange Online PowerShell 中，运行以下命令并验证**ReportJunkEmailEnabled**属性值：

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 在 Outlook 网页版中打开受影响用户的邮箱，并验证用于报告垃圾邮件、非垃圾邮件和网络钓鱼邮件的选项是否可用。 请注意，用户仍可以将邮件标记为垃圾邮件、网络钓鱼邮件和非垃圾邮件，但用户无法将其报告给 Microsoft。
