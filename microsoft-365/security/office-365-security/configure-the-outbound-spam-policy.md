---
title: 配置出站垃圾邮件策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。
ms.openlocfilehash: c17772db2a2961cade180a5c1e0403ae8450007f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599559"
---
# <a name="configure-the-outbound-spam-policy"></a>配置出站垃圾邮件策略

如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。 与入站筛选类似，出站垃圾邮件筛选由连接筛选和内容筛选组成，并允许某些特定的控件处理出站邮件。 出站垃圾邮件筛选器策略设置类型：

- 默认：使用默认出站垃圾邮件筛选器策略配置公司范围的出站垃圾邮件筛选器设置。 无法重命名此策略，并且其始终启用。

- 自定义：自定义出站垃圾邮件筛选器策略可以精细并应用于组织中的特定用户、组或域。 自定义策略的优先级始终高于默认策略。 您可以通过更改每个自定义策略的优先级来更改自定义策略的运行顺序;但是，如果用户匹配多个策略，则只有最高优先级（即最接近0的数字）策略适用。

> [!NOTE]
> 有关[Office 365 中的出站垃圾邮件控制](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls)的详细信息。 <br><br> 对出站垃圾邮件策略的更新当前正在滚动，预计更新在10月2019结束后完成。 在这段时间内，某些选项可能不可用。  有关详细信息，请参阅[Office 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?featureid=54125) 

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟

您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限，请参阅 [Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)主题中的“反垃圾邮件”条目。

以下步骤也可以通过远程 PowerShell 执行。 使用[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) cmdlet 可查看您的设置，以及用于编辑出站垃圾邮件策略设置的[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) 。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[使用 Remote PowerShell 连接到 Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

## <a name="use-the-security-and-compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>使用安全与合规中心（SCC）编辑默认的出站垃圾邮件策略

使用以下步骤编辑默认出站垃圾邮件策略：

### <a name="to-configure-the-default-outbound-spam-policy"></a>要配置默认出站垃圾邮件策略

1. 在 SCC 中，导航到 "**威胁管理** \> **策略** \> **反垃圾邮件**"

2. 展开 "**出站垃圾邮件筛选器策略（永不打开）** " 部分，然后单击 "**编辑策略**"。

3. 展开 "**通知**" 部分，选择以下与出站邮件相关的复选框，然后选择 "**添加人员**"，在附带的对话框中添加关联的电子邮件地址或地址。 （如果它们解析为有效的 SMTP 目标，它们可以是通讯组列表）：

   - 将**所有可疑的出站电子邮件的副本发送到以下电子邮件地址或地址**：这些邮件被筛选器标记为垃圾邮件（无论 SCL 分级如何）。 它们未被筛选器拒绝，但是将通过高风险传输工具路由。 用分号分隔多个地址。 请注意，指定的收件人将作为密件抄送 (Bcc) 地址接收邮件（"发件人"和"收件人"字段是原始的发件人和收件人）。

   - **当发件人被阻止发送出站垃圾邮件时，向以下电子邮件地址发送通知**：使用分号分隔多个地址。

   当从特定用户检测到大量垃圾邮件或其他发送异常时，将限制该用户发送电子邮件，并将通知发送到指定的电子邮件地址。

   使用该设置指定的域管理员将收到该用户的出站邮件被阻止的通知。  若要查看此通知的样式，请参阅[发件人被阻止发送出站垃圾邮件时的示例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)。

   > [注释！]还会生成一个系统警报，指示用户已受到限制。  若要了解有关警报以及如何恢复用户的详细信息，请参阅[发送垃圾电子邮件后，从受限用户门户中删除用户](removing-user-from-restricted-users-portal-after-spam.md)。

4. 展开 "**收件人限制**" 部分，指定用户可以向其发送的最大收件人数、内部和外部收件人的每小时收件人数以及每天的最大数量。

    > [注释！]任何输入的最大数量为10000。  有关详细信息，请参阅[Exchange online 中的接收和发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

7. 指定当用户超过指定限制时要执行的**操作**。  可能的操作如下所示：
    * **限制用户在以下日期之前发送邮件**。  一旦超出任何发送限制（内部、外部或每日），将为管理员生成一个警报，并且用户将无法在下一天（基于 UTC 时间）发送任何后续电子邮件。 管理员无法替代此块。

    * **限制用户发送邮件**。  一旦超出任何发送限制（内部、外部或每日），将为管理员生成一个警报，并且在管理员删除此限制之前，用户将无法再发送任何电子邮件。  在这些情况下，将在 "[受限用户" 页](removing-user-from-restricted-users-portal-after-spam.md)上列出用户。  从列表中删除后，将不会在那天再次限制用户。

    * **不执行任何操作/警报**。 一旦超出任何发送限制（内部、外部或每日），将为管理员生成警报，但不会执行任何操作来限制用户。

6. 展开 "**应用**于" 部分，然后创建基于条件的规则，以指定要向其应用此策略的用户、组和域。 可以创建多个唯一性条件。  注意：如果指定了多个条件，则用户必须满足所有条件。  

      * 若要选择用户，请选择 **"发件人为"**。 在随后的对话框中，从用户选取器列表中选择一个或多个公司的发件人，然后单击“添加”。 若要添加列表中没有的发件人，请键入他们的电子邮件地址，并单击“检查姓名”。 完成选择后，单击“确定”返回主屏幕。

      * 若要选择组，请选择 **"发件人是" 的成员**。 然后，在随后出现的对话框中选择或指定组。 单击"确定"返回到主屏幕。

      * 若要选择域，请选择 **"发件人域为"**。 然后，在随后出现的对话框中添加域。 单击"确定"返回到主屏幕。

        可以在规则中创建例外。 例如，可以筛选来自除某个域之外的所有域的邮件。 单击“添加例外”，然后创建例外条件，此过程与创建其他条件的方法类似。

        仅支持启用邮件的安全组将出站垃圾邮件策略应用于组。

7. 单击“保存”****。

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>为一组特定用户创建自定义策略
1. 在 SCC 中，导航到 "**威胁管理** \> **策略** \> **反垃圾邮件**"

2. 单击 "**创建出站策略**" 按钮。

3. 展开 "**通知**" 部分，选择以下与出站邮件相关的复选框，然后选择 "**添加人员**"，在附带的对话框中添加关联的电子邮件地址或地址。

4. 展开 "**收件人限制**" 部分，指定用户可以向其发送的收件人的最大数量、内部和外部收件人的每小时以及每日最大数量。

7. 指定当用户超过指定限制时要执行的**操作**。

6. 展开 "**应用**于" 部分并创建基于条件的规则，以指定要向其应用此策略的用户、组和域。 可以创建多个唯一性条件。  

8. 单击 "**保存**"

## <a name="for-more-information"></a>更多详细信息

[发送垃圾电子邮件后，从受限用户门户删除用户](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[反垃圾邮件保护常见问题](anti-spam-protection-faq.md)
