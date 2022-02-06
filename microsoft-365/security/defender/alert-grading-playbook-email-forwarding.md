---
title: 可疑电子邮件转发活动的警报评分
description: 可疑电子邮件转发活动的警报评分，查看警报并采取建议操作来修正攻击和保护你的网络。
keywords: 事件， 警报， 调查， 分析， 响应， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
  - NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
  - M365-security-compliance
  - m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
  - MOE150
ms.technology: m365d
---
# <a name="alert-grading-for-suspicious-email-forwarding-activity"></a>可疑电子邮件转发活动的警报评分

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

威胁参与者可以将遭到入侵的用户帐户用于多种恶意目的，包括阅读用户收件箱中的电子邮件、将电子邮件转发给外部收件人以及发送网络钓鱼邮件等。 目标用户可能不知道他们的电子邮件正在转发。 这是攻击者在用户帐户遭到入侵时使用的一种非常常见的策略。

可以使用转发规则手动或自动转发电子邮件。 自动转发可以通过多种方式实现，如收件箱规则、Exchange传输规则 (ETR) 和 SMTP 转发。 虽然手动转发需要用户直接操作，但他们可能不知道所有自动转发的电子邮件。 在Microsoft 365，当用户自动将电子邮件转发到潜在恶意电子邮件地址时，将引发警报。

本操作手册可帮助你调查可疑电子邮件转发活动警报，并快速将其评级为真正 (TP) 或误报 (FP) 。 然后，你可以对 TP 警报采取建议操作来修正攻击。

有关 Microsoft Defender for Office 365 和 Microsoft Defender for Cloud Apps 警报评分的概述，请参阅[简介文章](alert-grading-playbooks.md)。

使用此 Playbook 的结果为：

- 你已识别与自动转发的电子邮件相关的警报为恶意 (TP) 或恶意 (FP) 活动。

  如果恶意， [则已停止为](../office-365-security/external-email-forwarding.md) 受影响的邮箱自动转发电子邮件。

- 如果电子邮件已转发到恶意电子邮件地址，你已进行必要的操作。

## <a name="email-forwarding-rules"></a>电子邮件转发规则

电子邮件转发规则允许用户创建规则，将发送到用户邮箱的电子邮件转发到组织内部或外部其他用户的邮箱。 一些电子邮件用户（尤其是具有多个邮箱的电子邮件用户）配置转发规则，将雇主电子邮件移动到其私人电子邮件帐户。 电子邮件转发是一项有用的功能，但也可能由于信息泄露而带来安全风险。 攻击者可能会使用此信息来攻击您的组织或合作伙伴。

### <a name="suspicious-email-forwarding-activity"></a>可疑电子邮件转发活动

攻击者可能会设置电子邮件规则来隐藏受损用户邮箱中的传入电子邮件，以向用户隐藏其恶意活动。 他们还可能在受损的用户邮箱中设置规则，以删除电子邮件、将电子邮件移动到另一个不太明显的文件夹（如 RSS 文件夹）或将电子邮件转发到外部帐户。  

某些规则可能会将所有电子邮件移动到另一个文件夹，并标记为"已读"，而某些规则可能仅移动电子邮件或主题中包含特定关键字的邮件。 例如，收件箱规则可能设置为查找"发票"、"网络钓鱼"、"不答复"、"可疑电子邮件"或"垃圾邮件"等关键字，然后将它们移动到外部电子邮件帐户。 攻击者也可能使用遭到入侵的用户邮箱来分发垃圾邮件、网络钓鱼电子邮件或恶意软件。
 
Microsoft Defender for Office 365可以检测可疑电子邮件转发规则并发出警报，从而让你可以在源中查找和删除隐藏规则。

有关详细信息，请参阅以下博客文章：

- [商业电子邮件泄露](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/business-email-uncompromised-part-one/ba-p/2159900)
- [业务电子邮件泄露幕后：使用跨域威胁数据中断大型 BEC 活动](https://www.microsoft.com/security/blog/2021/06/14/behind-the-scenes-of-business-email-compromise-using-cross-domain-threat-data-to-disrupt-a-large-bec-infrastructure/)


## <a name="alert-details"></a>警报详细信息

To review the Suspicious Email Forwarding Activity alert， open the **Alerts** page to see the **Activity list** section. 下面是一个示例。
 
:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png" alt-text="与警报相关的活动列表" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png":::

选择 **"**  活动"以查看边栏中该活动的详细信息。 下面是一个示例。
 
:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png" alt-text="活动的详细信息" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png":::

" **原因** "字段包含与此警报相关的以下信息。

- FT () 转发类型为以下类型之一：

    -  Exchange传输规则 (ETR) ：使用和Exchange传输规则转发 

    -  SMTP：使用邮箱转发转发

    -  InboxRule：使用收件箱规则转发

- 邮件跟踪 ID (MTI) ：这是触发此 (转发) 的 NetworkMessageId 标识符。 NetworkMessageId 是组织中电子邮件的唯一标识符。
- 转发 (F#：转发此电子邮件的用户。
- 可疑收件人列表 (SRL) ：此电子邮件中视为可疑的收件人列表。
- 收件人 (RL) ：此电子邮件中所有收件人的列表。

## <a name="investigation-workflow"></a>调查工作流

调查此警报时，必须确定：

- 用户帐户及其邮箱是否受到威胁？
- 活动是否恶意？

### <a name="is-the-user-account-and-its-mailbox-compromised"></a>用户帐户及其邮箱是否受到威胁？

通过查看发件人的过去行为和最近活动，您应该能够确定是否认为用户帐户遭到入侵。 可以在用户门户中查看从用户页面Microsoft 365 Defender的详细信息。 

您还可以分析受影响的邮箱的以下其他活动：

- 使用威胁资源管理器了解电子邮件相关威胁

    - 观察发件人发送的最近发送的电子邮件中有多少被检测为网络钓鱼、垃圾邮件或恶意软件。

    - 观察发送的电子邮件中有多少包含敏感信息。 

- 在安全门户中评估有Microsoft Azure行为。
- 检查用户设备上是否有恶意活动。

### <a name="are-the-activities-malicious"></a>活动是否恶意？

调查电子邮件转发活动。 例如，检查电子邮件的类型、此电子邮件的收件人或转发电子邮件的方式。 

有关详细信息，请参阅以下文章：

- [自动转发的邮件见解](/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)
- [新用户转发电子邮件见解](/microsoft-365/security/office-365-security/mfi-new-users-forwarding-email)
- [响应被盗用的电子邮件帐户](/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)
- [在 Outlook 中报告误报和漏报](/microsoft-365/security/office-365-security/report-false-positives-and-false-negatives)

下面是用于标识可疑电子邮件转发活动的工作流。

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png" alt-text="电子邮件转发的警报调查工作流" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png":::

可以使用威胁资源管理器或高级搜寻查询调查电子邮件转发警报，基于 Microsoft 365 Defender 门户中的可用性。 你可以选择根据需要遵循整个过程或过程的一部分。

## <a name="using-threat-explorer"></a>使用威胁资源管理器

威胁资源管理器为电子邮件相关威胁提供交互式调查体验，以确定此活动是否可疑。 可以使用警报信息中的以下指示器：

- SRL/RL：使用 SRL (") " (") ""可疑收件人列表"来查找以下详细信息：
 
    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png" alt-text="收件人列表示例" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png":::

    - Who是否将电子邮件转发给这些收件人？

    - 已转发给这些收件人的电子邮件数？

    - 电子邮件转发给这些收件人的频率如何？
 

- MTI：使用邮件跟踪 ID/网络消息 ID 查找以下详细信息：

    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png" alt-text="网络消息 ID 示例" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png":::

    - 此电子邮件提供哪些其他详细信息？ 例如：subject、return path 和 timestamp。

    - 此电子邮件的来源是什么？ 是否有类似的电子邮件？

    - 此电子邮件是否包含任何 URL？ URL 是否指向任何敏感数据？

    - 电子邮件是否包含任何附件？ 附件是否包含敏感信息？

    - 对电子邮件采取的操作是什么？ 是否已删除、标记为已读或已移动到其他文件夹？

    - 是否有与此电子邮件相关的威胁？ 此电子邮件是否属于任何市场活动？

根据这些问题的解答，你应该能够确定电子邮件是恶意电子邮件还是恶意电子邮件。

## <a name="advanced-hunting-queries"></a>高级搜寻查询

若要 [使用高级搜寻](advanced-hunting-overview.md) 查询来收集与警报有关的信息并确定活动是否可疑，请确保你有权访问下表：

- EmailEvents - 包含与电子邮件流有关的信息。

- EmailUrlInfo - 包含与电子邮件中的 URL 有关的信息。

- CloudAppEvents -包含审核日志活动列表。

- IdentityLogonEvents - 包含所有用户的登录信息。

>[!Note]
>某些参数对于您的组织或网络是唯一的。 根据每个查询中的说明填写这些特定参数。
>

运行此查询，查找其他哪些人通过 SRL/RL (转发) 。

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| distinct SenderDisplayName, SenderFromAddress, SenderObjectId
```

运行此查询，了解转发给这些收件人的电子邮件数。

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress
```

运行此查询可了解电子邮件转发给这些收件人的频率。

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress, bin(Timestamp, 1d)
```

运行此查询，查明电子邮件是否包含任何 URL。
 
```kusto
let mti='{MTI}'; //Replace {MTI} with MTI from alert
EmailUrlInfo
| where NetworkMessageId == mti
```

运行此查询，查明电子邮件是否包含任何附件。

   ```kusto
   let mti='{MTI}'; //Replace {MTI} with MTI from alert
   EmailAttachmentInfo
   | where NetworkMessageId == mti
   ```

运行此查询，了解转发 (发件人) 是否创建了任何新规则。

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with display name of Forwarder
let action_types = pack_array(
    "New-InboxRule", 
    "UpdateInboxRules", 
    "Set-InboxRule", 
    "Set-Mailbox",    
    "New-TransportRule",
    "Set-TransportRule");
CloudAppEvents
| where AccountDisplayName == sender
| where ActionType in (action_types)
```

运行此查询，了解此用户是否有异常登录事件。 例如：未知 IP、新应用程序、不常见的国家/地区、多个 LogonFailed 事件。

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with email of the Forwarder IdentityLogonEvents
| where AccountUpn == sender
```

### <a name="investigating-forwarding-rules"></a>调查转发规则

您还可以根据警报管理中心中 FT (类型的规则类型，使用 Exchange 管理中心查找可疑转发) 。

- ETR 

  Exchange规则"部分 **列出了传输规则**。 验证所有规则是否都如预期一样。

- SMTP

  您可以通过选择发件人的邮箱"管理邮件流"设置"**\>\>电子邮件转发编辑"来查看邮箱转发\>规则**。

- InboxRule

  使用电子邮件客户端配置收件箱规则。 您可以使用 [Get-InboxRule](/powershell/module/exchange/get-inboxrule) PowerShell cmdlet 列出用户创建的收件箱规则。

### <a name="additional-investigation"></a>其他调查

除了到目前为止发现的证据，您还可以确定是否正在创建新的转发规则。 调查与规则关联的 IP 地址。 确保该 IP 地址不是异常 IP 地址，并且与用户执行的常规活动一致。

## <a name="recommended-actions"></a>建议的操作

确定关联的活动使此警报为"真正"后，请对警报进行分类，并执行以下操作进行修正：

1. 禁用并删除收件箱转发规则。
2. 对于 InboxRule 转发类型，重置用户帐户凭据。
3. 对于 SMTP 或 ETR 转发类型，调查创建警报的用户帐户的活动。

    - 调查任何其他可疑的管理员活动。

    - 重置用户帐户的凭据。

4. 检查来自受影响帐户、IP 地址和可疑发件人的其他活动。

## <a name="see-also"></a>另请参阅

- [警报评分概述](alert-grading-playbooks.md)
- [可疑的收件箱转发规则](alert-grading-playbook-inbox-forwarding-rules.md)
- [可疑的收件箱操作规则](alert-grading-playbook-inbox-manipulation-rules.md)
- [调查警报](investigate-alerts.md)
