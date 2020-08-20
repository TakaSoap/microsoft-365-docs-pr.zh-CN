---
title: 在 Outlook 网页版中报告垃圾和钓鱼电子邮件
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
description: 管理员可以了解 Exchange Online 中 Outlook 网页版中的内置垃圾邮件、非垃圾邮件和 (Outlook Web App) 钓鱼电子邮件报告选项，以及如何为用户禁用这些报告选项。
ms.openlocfilehash: a364afed9bb7e61d5f34ffc0206ede1c5155db65
ms.sourcegitcommit: c692bdc186fb29499816e8bb2addcddef34d23d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818329"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>在 Exchange Online 的 Outlook 网页版中报告垃圾和钓鱼电子邮件

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，你可以使用 Web 上的 Outlook (中内置报告 Outlook Web App) 选项，将误报选项提交误报 (正确的电子邮件被标记为垃圾邮件) 、漏报邮件 (允许) 错误 (正式邮件和网络钓鱼邮件提交到 Exchange Online Protection (EOP) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议您使用安全与合规中心中的&提交门户。 有关详细信息，请参阅["使用管理员提交"将可取的垃圾邮件、网络钓鱼邮件、URL 和文件提交到 Microsoft。](admin-submission.md)

- 管理员可以禁用或启用用户在 Web 上的 Outlook 中向 Microsoft 报告邮件。 有关详细信息，请参阅本主题 [后面"在 Outlook 网页版中禁用或启用](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 垃圾邮件报告"一节。

- 您可以将报告的邮件配置为复制或重定向到您指定的邮箱。 有关详细信息，请参阅 [在 Exchange Online 中指定提交用户收集的垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。

- 有关向 Microsoft 报告消息的详细信息，请参阅"[报告邮件和文件到 Microsoft"。](report-junk-email-messages-to-microsoft.md)

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>在 Outlook 网页版中报告垃圾邮件和钓鱼邮件

1. 对于"收件箱"或"垃圾邮件"之外的任何其他电子邮件文件夹中的邮件，请使用下列两种方法中的任何一种来报告垃圾邮件和网络钓鱼邮件：

   - 选择邮件 **，然后在**工具栏上单击"垃圾邮件"，然后选择"**垃圾邮件"****或"网络钓鱼"。**

     ![从功能区报告垃圾或钓鱼电子邮件](../../media/owa-report-junk.png)

   - Select one or more messages， right-click， and then select **Mark as junk**.

2. 在出现的对话框中，单击"**报告"。** 如果您改变了主想，请单击 **"不报告"。**

   |垃圾邮件|网络钓鱼|
   |:---:|:---:|
   |!["报告为垃圾邮件"对话框](../../media/owa-report-as-junk-dialog.png)|!["报告为网络钓鱼"对话框](../../media/owa-report-as-phishing-dialog.png)|

3. 选定的消息会发送至 Microsoft 进行分析。 若要确认已提交的邮件，请打开您的“已发送邮件”**** 文件夹查看已提交的邮件。

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>从 Web 上的 Outlook 中的"垃圾邮件"文件夹报告非垃圾邮件和网络钓鱼邮件

1. 在"垃圾邮件"文件夹中，请使用以下两种方法之一来报告垃圾邮件误报或网络钓鱼邮件：

   - 选择邮件，然后在**工具栏上单击**"非垃圾邮件"，然后选择 **"非垃圾邮件****"或"网络钓鱼"。**

     ![从功能区报告垃圾或钓鱼电子邮件](../../media/owa-report-not-junk.png)

   - Select one or more messages， right-click， and then select **Mark as not junk**.

2. 在出现的对话框中，阅读信息并单击"报告 **"。** 如果您改变了主想，请单击 **"不报告"。**

   |非垃圾邮件|网络钓鱼|
   |:---:|:---:|
   |![报告为非垃圾邮件对话框](../../media/owa-report-as-not-junk-dialog.png)|!["报告为网络钓鱼"对话框](../../media/owa-report-as-phishing-dialog.png)|

3. 选定的消息会发送至 Microsoft 进行分析。 若要确认已提交的邮件，请打开您的“已发送邮件”**** 文件夹查看已提交的邮件。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>在 Outlook 网页版中禁用或启用垃圾邮件报告

默认情况下，用户可以向 Microsoft 报告垃圾邮件误报、假负和网页邮件，以供在 Web 上的 Outlook 中进行分析。 管理员可以在 Exchange Online PowerShell 中配置 Web 上的 Outlook 邮箱策略，以防止用户向 Microsoft 报告垃圾邮件误报和垃圾邮件误报。 无法禁止用户向 Microsoft 报告网络钓鱼邮件。

### <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 必须先分配有权限，然后才能执行这些过程。 具体来说，你**需要**Exchange Online 中的**收件人策略或邮件收件人**角色，这些角色默认情况下被分配**到"组织管理****"和"收件人**管理"角色组。 有关 Exchange Online 中角色组的详细信息，请参阅 Exchange [Online 中的修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。

- 每个组织都有一个名为 OwaMailboxPolicy-Default 的默认策略，但您可以创建自定义策略。 自定义策略适用于默认策略前的已确定范围的用户。 有关 Web 上的 Outlook 邮箱策略的详细信息，请参阅 [Exchange Online 中的 Outlook 网页版邮箱策略](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。

- 禁用垃圾电子邮件报告不会删除 Web 上 Outlook 中的邮件被标记为垃圾邮件或非垃圾邮件的能力。 选择"垃圾邮件"文件夹中的邮件并单击 **"非垃圾邮件"** \> **Not junk**仍然会将该邮件移回收件箱中。 选择任何其他电子邮件文件夹中的邮件并单击"垃圾邮件 **"** \> **Junk**仍会将该邮件移至垃圾邮件文件夹。 不再提供的选项向 Microsoft 报告邮件。

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>使用 Exchange Online PowerShell 在 Web 上的 Outlook 中禁用或启用垃圾邮件报告

1. 若要查找现有 Outlook 网页版邮箱策略和垃圾邮件报告状态，请运行以下命令：

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. 若要禁用或启用 Web 上的 Outlook 中的垃圾邮件报告，请使用以下语法：

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   本示例禁用默认策略中的垃圾邮件报告。

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   本示例在名为 Contoso Managers 的自定义策略中启用垃圾邮件报告功能。

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

有关语法和参数的详细信息，请参阅[Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy)和[Set-OwaMailboxPolicy。](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已成功启用或禁用 Web 上的 Outlook 中的垃圾邮件报告，请执行以下任一步骤：

- 在 Exchange Online PowerShell 中，运行以下命令并验证 **ReportJunkEmailEnabled** 属性值：

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 在 Outlook 网页版中打开受影响用户的邮箱，在收件箱中选择一封邮件，单击**Junk** \> **"垃圾邮件"，** 然后验证是否显示向 Microsoft 报告该邮件的提示。<sup>\*</sup>

- 在 Web 上的 Outlook中打开受影响用户的邮箱，选择"垃圾邮件"文件夹中的邮件，单击 **"** \> **垃圾邮件"，** 然后确认"将该邮件报告给 Microsoft 的提示"已显示或未显示。<sup>\*</sup>

<sup>\*</sup> 用户可以隐藏该提示以在仍报告邮件时报告邮件。 若要在 Outlook 网页版中检查此设置，请执行下列操作：

1. 单击 **"Web** ![ 上的设置"图标查看 ](../../media/owa-settings-icon.png) \> **所有 Outlook 设置** \> **垃圾邮件**。
2. 在" **报告** "部分中，验证值 **：发送报告前先询问我**。

   ![Web 上的 Outlook 垃圾邮件报告设置](../../media/owa-junk-email-reporting-options.png)
