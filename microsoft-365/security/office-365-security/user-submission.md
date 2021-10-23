---
title: 用户报告的邮件设置
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
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0ec5e495e23326c52af37858d596caa3fbead606
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556312"
---
# <a name="user-reported-message-settings"></a>用户报告的邮件设置

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在Microsoft 365邮箱Exchange Online，您可以指定一个邮箱来接收用户报告为恶意或不恶意的邮件。 当用户使用各种报告选项报告邮件时，您可以使用此邮箱截获仅 (发送到自定义邮箱的邮件) 或接收发送到自定义邮箱 (Microsoft) 的邮件的副本。 此功能适用于以下邮件报告选项：

- [报告邮件外接程序](enable-the-report-message-add-in.md)
- [报告网络钓鱼外接程序](enable-the-report-phish-add-in.md)
- [第三方报告工具](#third-party-reporting-tools)

将用户报告的邮件发送到自定义邮箱而不是直接发送给 Microsoft，允许管理员使用管理员提交选择性地将邮件手动 [报告给](admin-submission.md)Microsoft。 这些设置以前称为用户提交策略。

  > [!NOTE]
  > 如果在[邮件中禁用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)了报告Outlook 网页版，则在此处启用用户报告的邮件将替代该设置，并使用户能够重新报告Outlook 网页版邮件。

## <a name="custom-mailbox-prerequisites"></a>自定义邮箱先决条件

使用以下文章配置必备组件，以便用户报告的邮件转到自定义邮箱：

- 通过创建 Exchange 邮件流规则来设置垃圾邮件可信度，跳过自定义邮箱上的垃圾邮件筛选。 请参阅使用 EAC 创建邮件流规则，[该规则将邮件的 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)设置为"绕过 **垃圾邮件筛选"。**

- 创建包含自定义邮箱 [的](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)反恶意软件策略，其中对恶意软件禁用了零时差自动清除 (ZAP) 的 (**保护设置** 部分未选中"启用恶意软件的零时差自动清除") 。 \> 

- [](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)创建一个反垃圾邮件策略，包括自定义邮箱，其中未选择"启用零时差自动清除 ( ( \> **ZAP**) "的自定义邮箱，其中"垃圾邮件的 ZAP"和"适用于网络钓鱼的 ZAP"部分) 。

如果你有 Microsoft Defender for Office 365，则还应配置以下设置，以便我们的高级筛选不会影响报告邮件的用户：

- [Create a 保险箱 Links policy](set-up-safe-links-policies.md) that includes the custom mailbox where 保险箱 Links scanning is turned off (**Select the action for unknown potentially malicious URLs in messages section** \> **Off**) .

- [创建一保险箱](set-up-safe-attachments-policies.md)附件策略，其中包括自定义邮箱，其中保险箱附件扫描已关闭 **(保险箱附件未知恶意软件** 响应"部分关闭 \> ) 。

验证邮箱满足所有适用的先决条件后，可以使用本文中的过程配置用户提交邮箱。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com/> 打开 Microsoft 365 Defender 门户。 若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission> 。

- 若要修改用户提交的配置，你需要是以下角色组之一的成员：

  - **组织管理****或安全管理员**，在 Microsoft 365 Defender [门户中](permissions-microsoft-365-security-center.md)。

- 您需要访问 Exchange Online PowerShell。 如果您尝试使用的帐户无法访问 Exchange Online PowerShell，则当您指定提交邮箱时，将收到如下所示的错误：

  > 在域中指定电子邮件地址

  有关启用或禁用对 PowerShell Exchange Online访问的信息，请参阅下列主题：

  - [启用或禁用对 Exchange Online PowerShell 的访问](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [客户端访问规则Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>使用Microsoft 365 Defender门户配置用户提交邮箱

1. 在Microsoft 365 Defender门户中，转到"策略&**规则** \> **""威胁策略**""其他用户提交"中的"用户 \>  \> **报告的邮件设置"。**

2. 在"**用户提交"** 页上，你看到的内容由"Microsoft Outlook **报告消息**"按钮设置是"关闭"还是"**开"确定**：

   - **Microsoft Outlook"报告消息"按钮** \>**打开** ![打开。：如果使用报告邮件外接程序、报告网络钓鱼外接程序或 Outlook 网页版 中的内置报告，请选择此选项，然后配置 ](../../media/scc-toggle-on.png) 以下设置：
     - **将报告的邮件发送到**：选择下列选项之一：
       - **Microsoft：** 所有报告的邮件都转到 Microsoft (时，不会使用用户提交) 。
       - **Microsoft 和我的组织的** 邮箱：在出现的框中，输入现有邮箱Exchange Online地址。 不允许通讯组。 用户提交将同时转到 Microsoft 进行分析，并转到自定义邮箱，供管理员或安全运营团队进行分析。
       - **我的组织的邮箱**：在出现的框中，输入现有邮箱Exchange Online电子邮件地址。 不允许通讯组。 如果希望邮件仅转到管理员或安全运营团队进行分析，请使用此选项。 除非管理员自行转发，否则邮件不会发送到 Microsoft。

          > [!IMPORTANT]
          > 美国政府组织 (GCC、GCC High 和 DoD) 只能配置我的 **组织的邮箱**。 其他两个选项已禁用。
          >
          > 如果组织配置为仅发送到自定义邮箱，将不会发送报告的邮件进行重新扫描，并且用户报告的邮件门户中的结果将始终为空。

       无论你为"将报告的邮件 **发送到"** 选择的值如何，以下设置都可用：

       - **让用户选择是否要向 Microsoft 报告其邮件**
       - **选择可供用户使用的报告选项部分** ：至少选择以下选项之一：
         - **发送邮件前询问我**
         - **始终报告邮件**
         - **从不报告邮件**

          > [!CAUTION]
          > 如果已使用 Outlook 网页版 邮箱策略禁用[Outlook 网页版](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)中的垃圾邮件报告，但配置了之前的任何设置以向 Microsoft 报告邮件，则用户将能够使用报告邮件外接程序或报告网络钓鱼外接程序向 Outlook 网页版 中的 Microsoft 报告邮件。

     将 **"Microsoft Outlook报告邮件**"按钮设置保持打开状态，以允许最终用户从隔离门户报告 ![ ](../../media/scc-toggle-on.png) 误报邮件。

     - **用户报告体验部分**
       - **"报告** 前"选项卡：在"标题"和"邮件"正文框中，输入用户在使用"报告邮件"外接程序或"报告网络钓鱼"外接程序报告邮件之前看到的描述性文本。 您可以使用变量 %type% 将提交类型 (垃圾邮件、网络钓鱼等) 。
       - **"报告** 后"选项卡：在"标题"和"确认"消息框中，输入用户在使用"报告邮件"外接程序或"报告钓鱼邮件"外接程序报告邮件后看到的描述性文本。 可以使用变量 %type% 包含提交类型。
       -  **仅在用户报告网络钓鱼** 时显示：如果希望仅在电子邮件报告为网络钓鱼时显示邮件，请选中此选项。 如果没有，则针对任何类型的报告显示已检查的邮件。

       如页面上所示，如果您选择将报告的邮件发送给 Microsoft 的选项，还会将以下文本添加到通知中：

          > 你的电子邮件将像现在一样提交到 Microsoft 进行分析。 某些电子邮件可能包含个人或敏感信息。

   - **Microsoft Outlook"报告消息"按钮** \>**关闭** ![切换为关闭：如果使用第三方报告工具而不是报告邮件外接程序、报告网络钓鱼外接程序或 Outlook 网页版 中的内置报告，请选择此选项，然后配置 ](../../media/scc-toggle-off.png) 以下设置：
     - 选择 **"使用此自定义邮箱接收用户报告的提交"。** 在出现的框中，输入可以接收电子邮件Exchange Online邮箱的电子邮件地址。

   - **Microsoft Outlook报告邮件** 按钮：如果希望最终用户报告隔离邮件，请启用此功能。

   完成后，单击"确认 **"。** 若要清除这些值，请单击"还原 **"**

## <a name="third-party-reporting-tools"></a>第三方报告工具

可以将第三方邮件报告工具配置为将报告的邮件发送到自定义邮箱。 为此，你可以将"Microsoft Outlook **报告邮件**"按钮设置设置为 **"** 关闭"，将"我的组织的邮箱"设置为Office 365邮箱。

唯一的要求是原始邮件作为 包含。EML 或 。MSG (未) 发送到自定义邮箱的邮件中的附件 (不要只将原始邮件转发到自定义邮箱) 。

下一节将介绍邮件格式要求。 格式是可选的，但如果它不符合规定格式，报告将始终作为网络钓鱼提交。

## <a name="message-submission-format"></a>邮件提交格式

若要正确标识原始附加的邮件，发送到自定义邮箱的邮件需要特定格式。 如果邮件不使用此格式，则原始附加的邮件始终标识为网络钓鱼提交。

如果要指定原始附加邮件的报告原因，则发送到自定义邮箱 (的邮件不修改附件) 需要在"主题 (信封标题") 中以下列前缀之一开头：

- 1|或垃圾邮件：
- 2|或非垃圾邮件
- 3|或网络钓鱼

例如：

`3|This part is ignored by the system` <br>
`Not Junk:This part of the subject is ignored as well`

- 这两条消息都根据主题报告为"非垃圾邮件"。
- 其余部分将被忽略。


不遵循此格式的邮件将不会在提交门户中正确显示。
