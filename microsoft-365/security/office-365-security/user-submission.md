---
title: 为用户提交的垃圾邮件和网络钓鱼邮件指定邮箱
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
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.openlocfilehash: 38fa16b5270273813b4549b0c3c9baaa1b05b098
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224549"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>为 Exchange Online 中的垃圾邮件和网络钓鱼邮件的用户提交指定邮箱

在使用 Exchange Online 邮箱的 Microsoft 365 组织中，您可以指定接收用户报告为恶意或非恶意邮件的邮箱。 当用户使用各种报告选项提交邮件时，您可以使用此邮箱来拦截邮件（仅发送到自定义邮箱）或接收邮件副本（发送到自定义邮箱和 Microsoft）。 此功能适用于以下邮件报告选项：

- [报告邮件加载项](enable-the-report-message-add-in.md)

- [Outlook 网页网站中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)（以前称为 "Outlook web App"）

  > [!NOTE]
  > 如果[在 web 上的 Outlook 中禁用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)了报告功能，则在此处启用用户提交将覆盖该设置，并使用户能够在 web 上再次报告 Outlook 中的邮件。

您还可以配置第三方邮件报告工具，以便将邮件转发到您指定的邮箱。

将用户报告的邮件传递到自定义邮箱，而不是直接发送到 Microsoft，使管理员可以有选择性地将邮件报告给 Microsoft，并使用[管理员提交](admin-submission.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 "**用户提交**" 页，请使用 <https://protection.office.com/userSubmissionsReportMessage> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 必须先分配有权限，然后才能执行这些过程。 若要为用户提交配置邮箱，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。 若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>使用安全 & 合规性中心配置用户提交邮箱

1. 在安全 & 合规性中心中，转到 "**威胁管理** \> **策略** \> **用户提交**"。

2. 在出现的 "**用户提交**" 页面中，选择下列选项之一：

   - **为 Outlook 启用 "报告邮件" 功能（推荐）**：如果您在 outlook 网页版中使用报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：

     - **自定义最终用户确认消息**：单击此链接。 在出现的 "**自定义确认消息**" 浮出控件中，配置以下设置：

       - **提交前**：在 "**标题**" 和 "**确认消息**" 框中，输入用户在使用报告邮件外接程序报告邮件之前看到的描述性文本。 您可以使用变量% type% 来包含提交类型（垃圾邮件、非垃圾邮件、网络钓鱼等）。

         如前所述，还会将以下文本添加到通知中：

         > 你的电子邮件将按与 Microsoft 的相同方式提交到 Microsoft 进行分析。 有些电子邮件可能包含个人信息或敏感信息。

       - **提交后**：单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 。 在 "**标题**" 和 "**确认消息**" 框中，输入用户在使用报告邮件外接程序报告邮件后看到的描述性文本。 您可以使用变量% type% 来包括提交类型。

      完成时，请单击“保存”****。 若要清除这些值，请单击 "**用户提交**" 页上的 "**还原**回"。

   - **将报告的邮件发送到**：执行下列任一选择：

     - **Microsoft （推荐）**：不使用用户提交邮箱（所有报告的邮件都转到 Microsoft）。

     - **Microsoft 和自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许使用通讯组。

     - **自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许使用通讯组。

     完成后，请单击 "**确认**"。

     ![将报告的邮件发送到 Microsoft 和自定义邮箱](../../media/user-submission-enable-outlook-report-message.png)

   - **禁用 outlook 的报告邮件功能**：如果您在 outlook 网页版中使用第三方报告工具而不是报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：

     选择 "**使用此自定义邮箱" 可接收用户报告的提交**。 在出现的框中，输入现有邮箱的电子邮件地址，或要创建的邮箱的电子邮件地址。

     完成后，请单击 "**确认**"。

     ![使用第三方工具将报告的邮件发送到自定义邮箱](../../media/user-submission-disable-outlook-report-message.png)
