---
title: Office 365 中的管理员提交，O365 报送，Office 365 垃圾邮件问题，O365 false 负数，提交在 office 365 中的网络钓鱼，提交电子邮件以便进行扫描，在 Office 365 中提交可疑电子邮件，扫描邮件，让 Microsoft 扫描网络钓鱼，使用 microsoft 扫描进行垃圾邮件，提交电子邮件、提交电子邮件、dodgy 电子邮件、不正确的主角邮件、可疑、不受信任的邮件、向 microsoft 报告网络钓鱼电子邮件、将网络邮件报告给 microsoft、向 microsoft 报告欺诈电子邮件、将电子邮件报告给 microsoft、将电子邮件报告给 microsoft、垃圾邮件收件箱 office 365 中的电子邮件，病毒在电子邮件 office 365 中
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
ms.collection:
- M365-security-compliance
description: 了解如何将可疑电子邮件、可疑的网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、Url 和文件从 Office 365 租户提交到 Microsoft 进行扫描。
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033610"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>使用管理员提交将可疑的垃圾邮件、网络钓鱼诈骗、Url 和文件提交给 Microsoft

如果您是在 Exchange Online 中拥有邮箱的 Office 365 组织中的管理员，则可以使用 Office 365 安全 & 合规性中心中的提交门户将电子邮件、Url 和附件提交到 Microsoft 进行扫描。

当您提交电子邮件时，您将获得可能允许传入的电子邮件进入租户的任何策略的信息，以及对邮件中的任何 Url 和附件的检查。 可能允许邮件的策略包括单个用户的安全发件人列表和租户级策略，如 Exchange 邮件流规则（也称为传输规则）。

有关向 Microsoft 提交电子邮件、Url 和附件的其他方法，请参阅 

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到**提交**页面，请<https://protection.office.com/reportsubmission>使用。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要连接到独立的 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 必须先分配有权限，然后才能执行这些过程。 若要添加、修改和删除反垃圾邮件策略，您必须是 "**组织管理**"、"**安全管理员**" 或 "**安全读者**" 角色组的成员。 若要详细了解安全与合规中心内的角色组，请参阅 [Office 365 安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

- 有关用户如何向 Microsoft 提交邮件和文件的详细信息，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>如何将可疑内容定向到 Microsoft for Office 365 扫描

若要将内容提交给 Microsoft，请单击 "提交" 页面左上角的 "**新建提交**" 按钮。 将显示页面右侧的浮出控件，其中包含用于提交电子邮件、URL 或文件的选项。

### <a name="submit-a-questionable-email-to-microsoft"></a>将可疑电子邮件提交给 Microsoft

![电子邮件提交示例](../../media/submission-flyout-email.PNG)

1. 若要提交电子邮件，请选择 "**电子邮件**"，并指定电子邮件**网络邮件 ID**或上载电子邮件文件。

2. 指定您想要运行策略检查的收件人。 策略检查将确定电子邮件是否因用户或租户级别策略而绕过扫描。

3. 指定是否应阻止电子邮件。 如果应阻止该电子邮件，请指定是否应将其阻止为垃圾邮件、网络钓鱼或恶意软件。 如果您不确定可能的类型，请使用您的最佳判断。

   - 如果由于提交策略而绕过筛选器，你将看到有关该策略的信息。

   - 如果筛选器由于一个或多个策略而被绕过，扫描将在几分钟内完成。 您将通过单击状态链接来查看有关提交的其他信息。 这包括策略检查结果和重新扫描判定结果。 注意这不会再次通过 Office 365 ATP 完全筛选堆栈运行电子邮件，但会根据邮件、URL 或文件的某些属性运行部分重新扫描。

4. 单击 "**提交**" 按钮。

### <a name="send-a-suspect-url-to-microsoft"></a>向 Microsoft 发送可疑 URL

![电子邮件提交示例](../../media/submission-url-flyout.png)

1. 若要提交 URL，请从浮出控件中选择**url** 。 键入完整 URL，包括协议（**https://**）。

   如果您选择了 "**应该已经过筛选**"，请指定 URL 是否为网络钓鱼或恶意软件。

2. 单击 "**提交**" 按钮。

### <a name="submit-a-suspected-file-to-microsoft"></a>将可疑文件提交给 Microsoft

![电子邮件提交示例](../../media/submission-file-flyout.PNG)

1. 若要提交文件，请从浮出控件中选择**文件**，并上载要扫描的文件。

2. 单击 "**提交**" 按钮。
