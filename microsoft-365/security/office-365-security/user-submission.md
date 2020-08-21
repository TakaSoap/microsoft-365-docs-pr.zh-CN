---
title: 指定用于提交邮件和网络钓鱼邮件的用户的邮箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.openlocfilehash: 76264801820b6a41ee744a8adcc3b3b48a8e9479
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826737"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>在 Exchange Online 中指定提交邮件和网络钓鱼邮件的邮箱

在使用 Exchange Online 邮箱的 Microsoft 365 组织中，你可以指定一个邮箱，以接收用户报告为恶意的邮件或非恶意邮件。 当用户使用不同的报告选项提交邮件时，可以使用此邮箱截获 (发送到自定义邮箱) 邮件) 或接收 (发送到自定义邮箱和 Microsoft) 的邮件的副本。 此功能使用以下邮件报告选项：

- [报告消息加载项](enable-the-report-message-add-in.md)

- [Outlook 网页版中的内置报告或](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (以前称为"精简Outlook Web App) 

- Outlook for iOS 和 Outlook for Android 中的内置报告

  > [!NOTE]
  > 如果在 Outlook 网页 [版中禁用了报告，](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)则在此处启用用户提交将覆盖该设置，并允许用户再次报告 Outlook 网页版中的邮件。

也可以配置第三方邮件报告工具，将邮件转发到您所指定的邮箱。

将用户报告的邮件发送到自定义邮箱而不是直接发送到 Microsoft，你的管理员可以通过管理员提交选择性地将邮件手动报告 [给](admin-submission.md)Microsoft。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到用户 **提交页面，** 请使用 <https://protection.office.com/userSubmissionsReportMessage> 。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 要修改用户提交的配置，您需要是以下角色组之一的成员：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 若要对用户提交进行只读访问，您需要是下列角色组之一的成员：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>使用安全与&合规中心配置用户提交邮箱

1. 在"安全与&中心"中，转到 **"威胁** \> **管理** \> **策略"用户提交**。

2. 在 **显示的用户提交** 页面中，选择以下选项之一：

   a. **为 Outlook (推荐) 启用报告邮件功能 **：如果使用 Outlook 网页版中的"报告邮件"加载项或内置报告，然后配置以下设置，请选择此选项：

      - **自定义最终用户确认消息：单击**此链接。 在显示 **的"自定义** 确认"消息浮出控件中，配置以下设置：

      - **提交之前**：在**标题****和确认消息**框中，输入用户在使用报告邮件加载项报告邮件之前看到的描述性文本。 你可以使用可变 %type% 包含提交类型 (、垃圾邮件、网络钓鱼或) 。

        如前一说明，如果您选择一个将报告的邮件发送到 Microsoft 的选项，则还会在通知中添加以下文本：

        > 你的电子邮件将会被你并不仅助 Microsoft 提交以供分析。 某些电子邮件可能包含个人或敏感信息。

      - **提交后：** 单击" ![ 展开"图标 ](../../media/scc-expand-icon.png) 。 在 **"标题****"和"确认**"消息框中，输入用户在使用报告邮件加载项报告邮件后看到的描述性文本。 你可以使用变量 %type% 来包含提交类型。

      完成时，请单击“保存”****。 若要清除这些值，请在 **"用户**提交"**页上单击"恢复"。**

      - **将报告的邮件发送到：** 选择下列邮件之一：

        - **Microsoft (推) ： **所有报告的邮件都不会 (提交邮箱将复制到 Microsoft) 。

        - **Microsoft 和自定义邮箱**：在出现的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许通讯组。 用户提交将转到 Microsoft 进行分析，并且会转到自定义邮箱供管理员或安全操作团队分析。

        - **自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许通讯组。 如果希望邮件仅发送给管理员或安全运营团队进行分析，请使用此选项。 除非管理员自己转发消息，否则不会转到 Microsoft。

        > [!NOTE]
        > 美国政府版组织 (GCC、GCC-H 和 DoD) 仅可以配置 **自定义邮箱**。 其他两个选项已禁用。 

      完成后，请单击"确认 **"。**

      > [!CAUTION]
      > 如果已 [使用 Web 上的 Outlook 邮箱](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 策略禁用了 Outlook 网页版中的垃圾邮件报告，但若配置了向 Microsoft 报告邮件的任意一个设置，用户可以使用"报告邮件"加载项在 Web 上的 Outlook 中向 Microsoft 报告邮件。

   - **为 Outlook 禁用"报告邮件"功能**：如果使用第三方报告工具而不是 Web 上的"报告邮件"加载项或内置报告，请选择此选项，然后配置以下设置：

      选择 **"使用此自定义邮箱"接收用户报告的提交**。 在出现的框中，输入已经存在于 Office 365 中的现有邮箱的电子邮件地址。 这必须是 Exchange Online 中可接收电子邮件的现有邮箱。

      完成后，单击"确认 **"。**

## <a name="message-submission-format"></a>邮件提交格式

发送到自定义邮箱的邮件需要遵循特定的提交邮件格式。 提交 (的使用) 的主题方式应为以下格式：

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

SafetyAPIAction 是以下整数值之一：

- 1：垃圾邮件
- 2：非垃圾邮件
- 3：网络钓鱼邮件

在以下示例中：

- 邮件正报告为钓鱼邮件。
- 网络消息 ID 为 49871234-6dc6-43e8-abcd-08d797f20abe。
- 发件人 IP 为 167.220.232.101。
- 发件人地址为 test@contoso.com。
- 邮件的主题行是"测试网络钓鱼邮件"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

未遵循此格式的邮件将无法在提交门户中正常显示。
