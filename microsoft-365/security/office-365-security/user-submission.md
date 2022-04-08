---
title: 用户报告的消息设置
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4b86341434c05f18e1dd264b6fdabef8e36f2d29
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705354"
---
# <a name="user-reported-message-settings"></a>用户报告的消息设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在Microsoft 365具有Exchange Online邮箱的组织中，可以指定邮箱来接收用户报告为恶意或非恶意邮件的邮件。 当用户使用各种报告选项报告邮件时，可以使用此邮箱来截获仅) 发送到自定义邮箱 (邮件，或者接收 (发送到自定义邮箱和 Microsoft) 的邮件副本。 此功能适用于以下消息报告选项：

- [报表消息加载项](enable-the-report-message-add-in.md)
- [报表网络钓鱼加载项](enable-the-report-phish-add-in.md)
- [第三方报告工具](#third-party-reporting-tools)

将用户报告的消息传送到自定义邮箱而不是直接发送到 Microsoft，使管理员能够选择性地使用 [管理员提交](admin-submission.md)向 Microsoft 手动报告邮件。 这些设置以前称为用户提交策略。

  > [!NOTE]
  > 如果[在Outlook na Web中禁](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)用了报告，则在此处启用用户报告的消息将替代该设置，并使用户能够在Outlook na Web中再次报告消息。

## <a name="custom-mailbox-prerequisites"></a>自定义邮箱先决条件

使用以下文章配置必需的先决条件，以便用户报告的消息转到自定义邮箱：

- 通过创建交换邮件流规则来设置垃圾邮件置信度级别，跳过对自定义邮箱的垃圾邮件筛选。 请参阅 [使用 EAC 创建邮件流规则，该规则设置邮件的 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 以将 SCL 设置为 **绕过垃圾邮件筛选**。

- [创建一个反恶意软件策略](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)，其中包括自定义邮箱，其中零小时自动清除 (恶意软件的 ZAP) 已关闭 (**保护设置** 部分 **"为恶意软件启用零小时自动清除**"部分\>) 。

- [创建反垃圾邮件策略](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)，其中包括自定义邮箱，其中禁用用于垃圾邮件的 ZAP 和用于网络钓鱼的 ZAP (**零小时自动清除** 部分\>**"启用零小时自动清除 (ZAP)** 未选择) 。

如果已Pertahanan Microsoft untuk Office 365，还应配置以下设置，以便高级筛选不会影响报告消息的用户：

- [创建保险箱链接策略](set-up-safe-links-policies.md)，其中包括关闭保险箱链接扫描的自定义邮箱 (在"**关闭**) "部分\>**中选择未知潜在恶意 URL 的操作**。

- [创建保险箱附件策略](set-up-safe-attachments-policies.md)，其中包括自定义邮箱，其中保险箱附件扫描 (**保险箱附件未知恶意软件响应** 部分\>**关闭**) 。

验证邮箱是否满足所有适用的先决条件后，可以使用本文中的过程来配置用户提交邮箱。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到 **"用户提交** "页，请使用 <https://security.microsoft.com/userSubmissionsReportMessage>。

- 若要修改用户提交的配置，需要成为以下角色组之一的成员：

  - [Microsoft 365 Defender门户中的权限中的](permissions-microsoft-365-security-center.md)**组织管理****或安全管理员**。

- 需要访问 Exchange Online PowerShell。 如果尝试使用的帐户无法访问 Exchange Online PowerShell，则在指定提交邮箱时将收到如下所示的错误：

  > 在域中指定电子邮件地址

  有关启用或禁用对 Exchange Online PowerShell 的访问的详细信息，请参阅以下主题：

  - [启用或禁用对 Exchange Online PowerShell 的访问](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Exchange Online中的客户端访问规则](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>使用Microsoft 365 Defender门户配置用户提交邮箱

1. 在 Microsoft 365 Defender 门户中<https://security.microsoft.com>，转到策略 **&规则** \> **威胁策略**\>用户在"**其他**"部分 **中报告的消息设置**。 若要直接转到 **"用户提交** "页，请使用 <https://security.microsoft.com/userSubmissionsReportMessage>。

2. 在 **"用户提交**"页上，你所看到的内容取决于 **Microsoft Outlook"报表消息"按钮** 设置是 **"关闭**"还是 **"打开**"：

   - **Microsoft Outlook"报表消息"按钮** \> **：**![](../../media/scc-toggle-on.png)如果使用报表消息加载项、报表网络钓鱼加载项或Outlook na Web中的内置报表，请选择此选项，然后配置以下设置：
     - **将报告的消息发送到**：选择以下选项之一：
       - **Microsoft**： (所有报告的消息都转到 Microsoft) ，则不使用用户提交邮箱。
       - **Microsoft 和我组织的邮箱**：在显示的框中，输入现有Exchange Online邮箱的电子邮件地址。 不允许分发组。 用户提交将转到 Microsoft 进行分析，并转到自定义邮箱供管理员或安全操作团队分析。
       - **我组织的邮箱**：在显示的框中，输入现有Exchange Online邮箱的电子邮件地址。 不允许分发组。 如果希望消息仅转到管理员或安全操作团队进行分析，请使用此选项。 除非管理员自行转发消息，否则消息不会转到 Microsoft。

          > [!IMPORTANT]
          > 美国政府组织 (GCC、GCC高和 DoD) 只能配置 **我的组织的邮箱**。 其他两个选项已禁用。
          >
          > 如果组织配置为仅发送到自定义邮箱，则不会发送报告邮件进行重新扫描，并且用户报告的消息门户中的结果将始终为空。

       无论为 **将报告的消息发送到** 的所选值如何，都可以使用以下设置：

       - **允许用户选择是否要向 Microsoft 报告其消息**
       - **选择可供用户使用的报告选项** 部分：在以下选项中至少选择一个：
         - **在发送消息之前询问我**
         - **始终报告消息**
         - **从不报告消息**

          > [!CAUTION]
          > 如果已使用Outlook na Web邮箱策略[在Outlook na Web中禁用垃圾邮件报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)，但你配置了上述任何设置以向 Microsoft 报告邮件，则用户将能够使用报表邮件加载项或报表网络钓鱼加载项Outlook na Web向 Microsoft 报告邮件。

     保留 **Microsoft Outlook"报表消息"按钮** 设置!["打开](../../media/scc-toggle-on.png)**"** 以允许最终用户从隔离门户报告误报消息。

     - **"用户报告体验"部分**
       - **在报告选项卡之前** ：在 **标题** 和 **消息正文** 框中，输入用户在使用报表消息加载项或报表网络钓鱼加载项报告邮件之前看到的描述性文本。 可以使用变量 %type% 包括提交类型 (垃圾，而不是垃圾、网络钓鱼等) 。
       - **报告选项卡后** ：在 **"标题** 和 **确认"消息** 框中，输入用户使用报表消息加载项或报表网络钓鱼加载项报告邮件后看到的描述性文本。 可以使用变量 %type% 来包含提交类型。
       - **仅当用户报告网络钓鱼时显示**：如果要仅在将电子邮件报告为网络钓鱼时才显示该邮件，请检查此选项。 如果没有，将为任何类型的报表显示选中的消息。

       如页面上所示，如果选择将报告的消息发送到 Microsoft 的选项，也会将以下文本添加到通知中：

          > 电子邮件将按原样提交给 Microsoft 进行分析。 某些电子邮件可能包含个人或敏感信息。

   - **Microsoft Outlook"报表消息"按钮** \> **关闭**![](../../media/scc-toggle-off.png)。：如果使用第三方报表工具而不是报表消息加载项、报表网络钓鱼加载项或Outlook na Web中的内置报表，请选择此选项，然后配置以下设置：
     - 选择 **"使用此自定义邮箱"接收用户报告的提交**。 在显示的框中，输入可接收电子邮件的现有Exchange Online邮箱的电子邮件地址。

   - **隔离报表消息按钮**：如果要让最终用户从隔离区报告消息，请启用此功能。

   完成后，单击" **确认**"。 若要清除这些值，请单击"**还原**"

## <a name="third-party-reporting-tools"></a>第三方报告工具

可以配置第三方邮件报告工具，以便将报告的消息发送到自定义邮箱。 为此，请将 **Microsoft Outlook"报表消息"按钮** 设置设置为 **"关闭**"，并将 **"我的组织"邮箱** 设置为所选Office 365邮箱。

唯一的要求是将原始邮件作为一个包含在内。EML 或 .MSG 附件 (未在发送到自定义邮箱的邮件中压缩)  (不只是将原始邮件转发到自定义邮箱) 。

下一部分介绍了消息格式设置要求。 格式是可选的，但如果它不遵循规定的格式，报告将始终作为网络钓鱼提交。

## <a name="message-submission-format"></a>消息提交格式

若要正确识别原始附加邮件，发送到自定义邮箱的消息需要特定格式。 如果邮件不使用此格式，则原始附加的消息始终标识为网络钓鱼提交。

如果要指定原始附加邮件的报告原因，则发送到自定义邮箱的邮件 (不会修改附件，) 需要从主题 (信封标题) 中的以下前缀之一开始：

- 1|或垃圾：
- 2|或不是垃圾：
- 3|或网络钓鱼：

例如：

`3|This part is ignored by the system` <br>
`Not Junk:This part of the subject is ignored as well`

- 这两条消息都根据主题报告为"不是垃圾邮件"。
- 其余的将被忽略。


不遵循此格式的消息不会在提交门户中正确显示。
