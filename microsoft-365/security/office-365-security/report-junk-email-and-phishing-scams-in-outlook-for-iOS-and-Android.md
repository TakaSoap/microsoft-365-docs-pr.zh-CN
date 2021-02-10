---
title: 在 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和钓鱼电子邮件
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
description: 管理员可以了解 Outlook for iOS 和 Outlook for Android 中的内置垃圾邮件（非垃圾邮件）和网络钓鱼电子邮件报告选项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166815"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>在 Exchange Online 中报告 Outlook for iOS 和 Outlook for Android 中的垃圾邮件和网络钓鱼电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

在使用混合新式身份验证的 Exchange Online 或本地邮箱的 Microsoft 365 组织中，可以使用 Outlook for iOS 和 Outlook for Android 中的内置报告选项向 Exchange Online Protection (EOP) 提交误报 (标记为垃圾邮件) 、漏报 (允许的) 错误电子邮件以及网络钓鱼邮件。 [](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始之前，您需要了解哪些信息

- 如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议你使用安全与合规中心&门户。 有关详细信息，请参阅"使用管理员提交"将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)

- 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。

- 有关向 Microsoft 报告邮件详细信息，请参阅向 [Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

  > [!NOTE]
  > 如果在用户提交策略中禁用了 Outlook 的垃圾邮件报告，垃圾邮件或网络钓鱼邮件将移动到"垃圾邮件"文件夹，并且不会报告给管理员或 Microsoft。

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>在 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和网络钓鱼邮件

对于收件箱中的邮件或其他任何电子邮件文件夹（垃圾邮件除外），请使用以下步骤报告 iOS 和 Android 的垃圾邮件和网络钓鱼邮件：

1. 选择一个或多个邮件。
2. 在右上角点击三个垂直点。 操作菜单将打开。

   ![从操作菜单报告垃圾邮件或钓鱼电子邮件](../../media/Android-report-as-junk-dialog.png)

3. 点击 **"报告垃圾邮件**"，然后选择"**垃圾邮件**"或"**网络钓鱼"。**

   ![报告垃圾邮件或钓鱼电子邮件](../../media/Android-report-junk-or-phishing.png)

4. 在出现的对话框中， **可以选择"报告** "或" **否"。谢谢**。 选择"**否"时**，如果点击"垃圾邮件"，邮件将移动到"垃圾邮件"文件夹，如果点击了网络钓鱼，邮件将移动到"已删除邮件"文件夹。 Select **Report** to also send a copy of the message to Microsoft.

   ![报告垃圾邮件或网络钓鱼电子邮件报告选项](../../media/Android-junk-email-reporting-options.png)

如果改变主意，请在出现的 Toast 通知上选择"撤消"。  邮件仍保留在收件箱文件夹中。

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>从 Outlook for iOS 和 Outlook for Android 中的"垃圾邮件"文件夹报告非垃圾邮件

在"垃圾邮件"文件夹中，使用以下步骤报告垃圾邮件误报：

1. 选择一个或多个邮件。
2. 在右上角点击三个垂直点。 操作菜单将打开。

   ![从操作菜单中报告非垃圾邮件](../../media/Android-not-junk-email.png)

3. 点击 **"非垃圾邮件"。**

将显示一个 Toast 通知，表明电子邮件已移动到收件箱。 如果改变主意，请选择 **Toast** 通知上的"撤消"。 电子邮件仍保留在"垃圾邮件"文件夹中。
