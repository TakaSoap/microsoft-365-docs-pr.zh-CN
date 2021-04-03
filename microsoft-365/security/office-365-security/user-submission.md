---
title: 用户提交策略
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d86c79f0f0ab74d1dfbb88e7803f4ee4d691ea73
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501184"
---
# <a name="user-submissions-policy"></a>用户提交策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，可以指定一个邮箱来接收用户报告为恶意或不恶意的邮件。 当用户使用各种报告选项提交邮件时，您可以使用此邮箱拦截仅 (发送到自定义邮箱的邮件) 或接收 (发送到自定义邮箱和 Microsoft) 的邮件的副本。 此功能适用于以下邮件报告选项：

- [报告邮件外接程序](enable-the-report-message-add-in.md)

- [报告网络钓鱼外接程序](enable-the-report-phish-add-in.md)

- [Outlook 网页网页中的](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 内置 (以前称为Outlook Web App) 

- [Outlook for iOS 和 Outlook for Android 中的内置报告](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > 如果在 [Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)网页中禁用了报告功能，则在此处启用用户提交将覆盖该设置，并使用户能够在 Outlook 网页中重新报告邮件。

还可以配置第三方邮件报告工具，将邮件转发到指定的邮箱。

将用户报告的邮件发送到自定义邮箱，而不是直接发送给 Microsoft，使管理员能够使用管理员提交选择性地将邮件手动 [报告给](admin-submission.md)Microsoft。

## <a name="custom-mailbox-prerequisites"></a>自定义邮箱先决条件

使用以下文章配置必备组件，以便用户报告的邮件转到自定义邮箱：

- 通过创建 Exchange 邮件流规则来设置垃圾邮件可信度，跳过自定义邮箱上的垃圾邮件筛选。 请参阅 [使用 EAC 创建将邮件的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 设置为 **-1** 的邮件流规则。

- 关闭自定义邮箱中恶意软件的扫描附件。 使用 [Defender for Office 365](set-up-safe-attachments-policies.md)中的"设置安全附件策略"创建安全附件策略，同时将"安全附件未知恶意软件响应"设置为"关闭 **"。**

- 关闭自定义邮箱中邮件的 URL 扫描。 使用 [Defender for Office 365](set-up-safe-links-policies.md)中的"设置安全链接策略"创建安全链接策略，并设置"关闭"以选择邮件中未知潜在恶意 **URL 的操作**。

- 创建反恶意软件策略以关闭恶意软件零时差自动清除。 请参阅 [使用安全&合规中心创建反恶意软件](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)策略，将 **"恶意软件零时差自动清除**"设置为 **"关闭"。**

- 创建垃圾邮件筛选器策略，以禁用对自定义邮箱中的 (和网络钓鱼) ZAP 邮件进行零时差自动清除。 请参阅 [使用安全&](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 中心创建反垃圾邮件策略并清除 **垃圾邮件** **ZAP** 和钓鱼邮件 **ZAP** 的打开复选框。

- 禁用自定义邮箱中的垃圾邮件规则。 使用 [配置 Exchange Online 邮箱上的垃圾邮件设置禁用](configure-junk-email-settings-on-exo-mailboxes.md) 垃圾邮件规则。 禁用后，EOP 无法根据垃圾邮件筛选裁定操作将邮件移动到"垃圾邮件"文件夹或邮箱的安全列表集合，将邮件移动到"垃圾邮件"文件夹。

在验证邮箱满足所有适用的先决条件后，请使用安全 [&](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) 合规性中心配置本文 (提交邮箱) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到用户 **提交页面，** 请使用 <https://protection.office.com/userSubmissionsReportMessage> 。

- 若要修改用户提交的配置，你需要是以下角色组之一的成员：

  - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
  - **Exchange** Online 中的 [组织管理](/Exchange/permissions-exo/permissions-exo#role-groups)。

- 您需要访问 Exchange Online PowerShell。 如果您尝试使用的帐户无法访问 Exchange Online PowerShell，则指定提交邮箱时将收到如下所示的错误：

  > 在域中指定电子邮件地址

  有关启用或禁用对 Exchange Online PowerShell 的访问权的信息，请参阅下列主题：

  - [启用或禁用对 Exchange Online PowerShell 的访问](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Exchange Online 中的客户端访问规则](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>使用安全&合规中心配置用户提交邮箱

1. 在安全与&中心，转到"**威胁管理** \> **策略**"" \> **用户提交"。**

2. 在出现的 **"用户** 提交"页面中，选择以下选项之一：

      1. **启用 Outlook (** 推荐) 的报告邮件功能：如果使用报告邮件外接程序、报告网络钓鱼外接程序或 Outlook 网页中的内置报告，请选择此选项，然后配置以下设置：

    - **自定义最终用户确认消息：** 单击此链接。 在出现的 **"自定义确认消息** "飞出中，配置以下设置：

        - **提交前**：在"标题"和"确认"消息框中，输入用户在使用报告邮件外接程序或报告网络钓鱼外接程序报告邮件之前看到的描述性文本。 您可以使用变量 %type% 将提交类型 (垃圾邮件、网络钓鱼等) 。

            如前所述，如果您选择将报告的邮件发送给 Microsoft 的选项，则还会将以下文本添加到通知中：

        > 你的电子邮件将像现在一样提交到 Microsoft 进行分析。 某些电子邮件可能包含个人或敏感信息。

        - **提交后**：单击展开 ![ 图标 ](../../media/scc-expand-icon.png) 。 在 **"标题****"** 和"确认"消息框中，输入用户在使用"报告邮件"外接程序或"报告钓鱼邮件"外接程序报告邮件后看到的描述性文本。 可以使用变量 %type% 包含提交类型。

      完成后，单击“保存”。 若要清除这些值，请单击"**用户提交**"页面上的"**还原"。**
    
    - **自定义最终用户报告选项**：单击此链接。 在出现的 **"自定义最终用户报告** 选项"飞出中，输入垃圾邮件报告选项的描述性文本。 
在 **"要显示何时报告邮件的选项"下**，至少选择以下选项之一：
        - **在发送报告之前询问我**
        - **自动发送报告**
        -  **从不发送报告** \
   完成后，单击“保存”。
              - **将报告的邮件发送到**：进行以下选择之一：
              - **Microsoft (推荐) ：** 所有报告的邮件都转到 Microsoft (时，不会使用用户提交) 。
              - **Microsoft 和自定义邮箱：** 在出现的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许通讯组。 用户提交将同时转到 Microsoft 进行分析，并转到自定义邮箱，供管理员或安全运营团队进行分析。
              - **仅自定义邮箱**：在出现的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许通讯组。 如果希望邮件仅转到管理员或安全运营团队进行分析，请使用此选项。 除非管理员自行转发，否则邮件不会发送到 Microsoft。

        > [!NOTE]
        > GCC、GCC-H 和 DoD (的美国政府组织只能) 自定义 **邮箱**。 其他两个选项已禁用。

        > [!NOTE]
        > 如果组织配置为仅发送到自定义邮箱，将不会发送报告的邮件进行重新扫描，并且用户报告的邮件门户中的结果将始终为空。

      完成后，单击"确认 **"。**

      > [!CAUTION]
      > 如果已使用 Web 上的 Outlook 邮箱策略禁用 [Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 网页中的垃圾邮件报告，但配置了以上任一设置以向 Microsoft 报告邮件，则用户将能够使用"报告邮件"外接程序或"报告网络钓鱼"外接程序在 Outlook 网页中向 Microsoft 报告邮件。


    1. **禁用 Outlook** 的"报告邮件"功能：如果您使用第三方报告工具而不是报告邮件外接程序、报告网络钓鱼外接程序或 Outlook 网页中的内置报告，请选择此选项，然后配置以下设置：

          选择 **"使用此自定义邮箱接收用户报告的提交"。** 在出现的框中，输入 Office 365 中已有邮箱的电子邮件地址。 这应该是 Exchange Online 中可以接收电子邮件的现有邮箱。

          完成后，单击"确认 **"。**

## <a name="message-submission-format"></a>邮件提交格式

发送到自定义邮箱的邮件需要遵循特定的提交邮件格式。 提交 (信封标题) 应采用以下格式：

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

其中 SafetyAPIAction 是以下整数值之一：

- 1：垃圾邮件
- 2：非垃圾邮件
- 3：网络钓鱼

在下面的示例中：

- 邮件被报告为网络钓鱼。
- 网络消息 ID 为 49871234-6dc6-43e8-abcd-08d797f20abe。
- 发件人 IP 为 167.220.232.101。
- The From address is test@contoso.com.
- 邮件的主题行是"测试网络钓鱼提交"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

不遵循此格式的邮件将不会在提交门户中正确显示。
