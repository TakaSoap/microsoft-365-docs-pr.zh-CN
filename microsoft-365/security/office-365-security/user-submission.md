---
title: 用户提交策略
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
- m365initiative-defender-office365
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.openlocfilehash: c4792958d1e59cefd8b56c05b5e159f50be80c8b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600477"
---
# <a name="user-submissions-policy"></a>用户提交策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 邮箱的 Microsoft 365 组织中，您可以指定接收用户报告为恶意或非恶意邮件的邮箱。 当用户使用各种报告选项提交邮件时，您可以使用此邮箱来拦截邮件， (仅将邮件发送给自定义邮箱) 或接收 (发送到自定义邮箱和 Microsoft) 的邮件的副本。 此功能适用于以下邮件报告选项：

- [报告邮件加载项](enable-the-report-message-add-in.md)

- [Outlook 网页上的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (以前称为 Outlook web App) 

- [Outlook for iOS 和 Outlook for Android 中的内置报告](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > 如果 [在 web 上的 Outlook 中禁用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)了报告功能，则在此处启用用户提交将覆盖该设置，并使用户能够在 web 上再次报告 Outlook 中的邮件。

您还可以配置第三方邮件报告工具，以便将邮件转发到您指定的邮箱。

将用户报告的邮件传递到自定义邮箱，而不是直接发送到 Microsoft，使管理员可以有选择性地将邮件报告给 Microsoft，并使用 [管理员提交](admin-submission.md)。

## <a name="custom-mailbox-prerequisites"></a>自定义邮箱先决条件

使用以下文章配置需要的必备组件，以使用户报告的邮件转到您的自定义邮箱：

- 通过创建用于设置垃圾邮件可信度级别的 exchange 邮件流规则，跳过自定义邮箱上的垃圾邮件筛选。 请参阅 [使用 EAC 创建邮件流规则，将邮件的 scl](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 设置为将 scl 设置为 **-1**。

- 为自定义邮箱中的恶意软件关闭扫描附件。 使用 "[在 Office 365 ATP 中设置安全附件策略](set-up-atp-safe-attachments-policies.md)" 创建安全附件策略，设置为 "**关闭****安全附件" 未知恶意软件响应**。

- 对自定义邮箱中的邮件禁用 URL 扫描。 使用 " [在 Office 365 ATP 中设置安全链接策略](set-up-atp-safe-links-policies.md) " 创建安全链接策略，设置为 " **关闭** "，以 **选择对邮件中未知的潜在恶意 url 的操作**。

- 创建反恶意软件策略以关闭恶意软件零小时自动清除。 请参阅[使用安全 & 合规性中心创建反恶意软件策略](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，将**恶意软件设置为零小时自动清除** **。**

- 创建垃圾邮件筛选器策略以禁用自定义邮箱中的垃圾邮件和网络钓鱼的零小时自动清除 (ZAP) 。 请参阅[使用安全 & 合规性中心创建反垃圾邮件策略](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，并清除用于垃圾邮件**Zap**和**网络钓鱼 ZAP**的 "**打开**" 复选框。

- 禁用自定义邮箱中的垃圾邮件规则。 使用 [Exchange Online 邮箱上的 "配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md) " 禁用垃圾邮件规则。 禁用后，EOP 无法将邮件移动到 "垃圾邮件" 文件夹，具体取决于垃圾邮件筛选判定操作 **将邮件移动到 "垃圾邮件" 文件夹** 或邮箱中的 "安全列表" 集合。

确认您的邮箱符合所有适用的先决条件后，请 [使用安全 & 合规性中心在本文中配置用户提交邮箱](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) () 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 " **用户提交** " 页，请使用 <https://protection.office.com/userSubmissionsReportMessage> 。

- 若要修改用户提交的配置，您必须是下列角色组之一的成员：

  - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的**组织管理**。

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>使用安全 & 合规性中心配置用户提交邮箱

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **用户提交**"。

2. 在出现的 " **用户提交** " 页面中，选择下列选项之一：

   1. **启用 (建议的 outlook) 的 "报告邮件" 功能 **：如果您在 outlook 网页版中使用报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：

      - **自定义最终用户确认消息**：单击此链接。 在出现的 " **自定义确认消息** " 浮出控件中，配置以下设置：

      - **提交前**：在 " **标题** " 和 " **确认消息** " 框中，输入用户在使用报告邮件外接程序报告邮件之前看到的描述性文本。 您可以使用变量% type% 来包括提交类型 (垃圾邮件、非垃圾邮件、网络钓鱼等 ) 。

        如前所述，如果选择将报告的邮件发送给 Microsoft 的选项，则还会向通知中添加以下文本：

        > 你的电子邮件将按与 Microsoft 的相同方式提交到 Microsoft 进行分析。 有些电子邮件可能包含个人信息或敏感信息。

      - **提交后**：单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 。 在 " **标题** " 和 " **确认消息** " 框中，输入用户在使用报告邮件外接程序报告邮件后看到的描述性文本。 您可以使用变量% type% 来包括提交类型。

      完成时，请单击“保存”****。 若要清除这些值，请单击 "**用户提交**" 页上的 "**还原**回"。

      - **将报告的邮件发送到**：执行下列任一选择：

        - **Microsoft (建议) **：不使用用户提交邮箱 (所有报告的邮件都转到 Microsoft) 。

        - **Microsoft 和自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许使用通讯组。 用户提交将转到 Microsoft 进行分析和自定义邮箱，以供管理员或安全操作团队进行分析。

        - **自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。 不允许使用通讯组。 如果您希望邮件仅转到管理员或安全操作团队进行分析，请使用此选项。 除非管理员自行转发，否则邮件不会转到 Microsoft。

        > [!NOTE]
        > 美国政府组织 (GCC、GCC-H 和 DoD) 只能配置 **自定义邮箱**。 其他两个选项将被禁用。 

      完成后，请单击 " **确认**"。

      > [!CAUTION]
      > 如果您已在 Outlook 网页上使用 Outlook 网页邮箱策略禁用了 " [垃圾邮件报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) "，但您将上述任一设置配置为向 microsoft 报告邮件，则用户可以使用报告邮件加载项在 outlook 网页中向 microsoft 报告邮件。

   - **禁用 outlook 的报告邮件功能**：如果您在 outlook 网页版中使用第三方报告工具而不是报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：

      选择 " **使用此自定义邮箱" 可接收用户报告的提交**。 在出现的框中，输入已在 Office 365 中的现有邮箱的电子邮件地址。 这必须是 Exchange Online 中可接收电子邮件的现有邮箱。

      完成后，请单击 " **确认**"。

## <a name="message-submission-format"></a>邮件提交格式

发送到自定义邮箱的邮件需要遵循特定的提交邮件格式。 提交 (信封标题) 的主题应采用以下格式：

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

其中，SafetyAPIAction 是以下整数值之一：

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
