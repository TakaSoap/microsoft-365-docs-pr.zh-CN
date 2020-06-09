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
ms.openlocfilehash: 0f3c7f160e26b8befcbbe8096c07e9eb6fecb533
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613428"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>为 Exchange Online 中的垃圾邮件和网络钓鱼邮件的用户提交指定邮箱

在使用 Exchange Online 邮箱的 Microsoft 365 组织中，您可以指定接收用户报告为恶意或非恶意邮件的邮箱。 当用户使用各种报告选项提交邮件时，您可以使用此邮箱来拦截邮件（仅发送到自定义邮箱）或接收邮件副本（发送到自定义邮箱和 Microsoft）。 此功能适用于以下邮件报告选项：

- [报告邮件加载项](enable-the-report-message-add-in.md)

- [Outlook 网页网站中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)（以前称为 "Outlook web App"）

  > [!NOTE]
  > 如果[在 web 上的 Outlook 中禁用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)了报告功能，则在此处启用用户提交将覆盖该设置，并使用户能够在 web 上再次报告 Outlook 中的邮件。

您还可以配置第三方邮件报告工具，以便将邮件转发到您指定的邮箱。

将用户报告的邮件传递到自定义邮箱，而不是直接发送到 Microsoft，使管理员可以有选择性地将邮件报告给 Microsoft，并使用[管理员提交](admin-submission.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 "**用户提交**" 页，请使用 <https://protection.office.com/userSubmissionsReportMessage> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 必须先分配有权限，然后才能执行这些过程。 若要为用户提交配置邮箱，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。 若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>使用安全 & 合规性中心配置用户提交邮箱

1. 在安全 & 合规性中心中，转到 "**威胁管理** \> **策略** \> **用户提交**"。

2. 在出现的 "**用户提交**" 页面中，选择下列选项之一：

   a. **为 Outlook 启用 "报告邮件" 功能（推荐）**：如果您在 outlook 网页版中使用报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：

      - **自定义最终用户确认消息**：单击此链接。 在出现的 "**自定义确认消息**" 浮出控件中，配置以下设置：

      - **提交前**：在 "**标题**" 和 "**确认消息**" 框中，输入用户在使用报告邮件外接程序报告邮件之前看到的描述性文本。 您可以使用变量% type% 来包含提交类型（垃圾邮件、非垃圾邮件、网络钓鱼等）。

        如前所述，如果选择将报告的邮件发送给 Microsoft 的选项，则还会向通知中添加以下文本：

        > 你的电子邮件将按与 Microsoft 的相同方式提交到 Microsoft 进行分析。 有些电子邮件可能包含个人信息或敏感信息。

      - **提交后**：单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 。 在 "**标题**" 和 "**确认消息**" 框中，输入用户在使用报告邮件外接程序报告邮件后看到的描述性文本。 您可以使用变量% type% 来包括提交类型。

      完成时，请单击“保存”****。 若要清除这些值，请单击 "**用户提交**" 页上的 "**还原**回"。

      - **将报告的邮件发送到**：执行下列任一选择：

        - **Microsoft （推荐）**：不使用用户提交邮箱（所有报告的邮件都转到 Microsoft）。

        - **Microsoft 和自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许使用通讯组。 用户提交将转到 Microsoft 进行分析和自定义邮箱，以供管理员或安全操作团队进行分析。

        - **自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许使用通讯组。 如果您希望邮件仅转到管理员或安全操作团队进行分析，请使用此选项。 除非管理员自行转发，否则邮件不会转到 Microsoft。

        > [!NOTE]
        > 美国政府组织（GCC、GCC-H 和 DoD）只能配置**自定义邮箱**。 其他两个选项将被禁用。 

      完成后，请单击 "**确认**"。

      > [!CAUTION]
      > 如果您已在 Outlook 网页上使用 Outlook 网页邮箱策略禁用了 "[垃圾邮件报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)"，但您将上述任一设置配置为向 microsoft 报告邮件，则用户可以使用报告邮件加载项在 outlook 网页中向 microsoft 报告邮件。

   - **禁用 outlook 的报告邮件功能**：如果您在 outlook 网页版中使用第三方报告工具而不是报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：

      选择 "**使用此自定义邮箱" 可接收用户报告的提交**。 在出现的框中，输入已在 Office 365 中的现有邮箱的电子邮件地址。 这必须是 Exchange Online 中可接收电子邮件的现有邮箱。

      完成后，请单击 "**确认**"。

## <a name="message-submission-format"></a>邮件提交格式

发送到自定义邮箱的邮件需要遵循特定的提交邮件格式。 提交的主题（信封标题）应采用以下格式：

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

是 SafetyAPIAction 是以下整数值之一：

- 1：垃圾邮件
- 2： NotJunk
- 3：网络钓鱼

在下面的示例中：

- 将邮件报告为网络钓鱼。
- 网络邮件 ID 为49871234-6dc6-43e8-abcd-08d797f20abe。
- 发件人 IP 为167.220.232.101。
- "发件人" 地址为 test@contoso.com。
- 邮件的主题行是 "测试网络钓鱼提交"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

不遵循此格式的邮件在提交门户中不会正确显示。
