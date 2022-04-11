---
title: DLP 策略条件、异常和操作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: ''
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
recommendations: false
description: 了解 dlp 策略条件和异常
ms.openlocfilehash: f4a3521d0e5aab73cc16d97e0aea9c5830d9ddec
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64762048"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>DLP 策略条件、异常和操作

DLP 策略中的条件和异常可识别应用策略的敏感项。 操作定义因满足异常条件而发生的情况。

- 条件定义要包含的内容
- 异常定义要排除的内容。
- 操作定义因满足条件或异常而发生的情况

大多数条件和异常都有一个属性支持一个或多个值。 例如，如果 DLP 策略应用于Exchange电子邮件，**则发件人** 的条件需要邮件的发件人。 一些条件有两个属性。 例如，“**邮件头包含以下任何词语**”条件需要一个属性来指定邮件头字段，需要第二个属性来指定要在头字段中查找的文本。 某些条件或例外没有任何属性。 例如， **附件是受密码保护** 的条件，只需在受密码保护的消息中查找附件。

操作通常需要其他属性。 例如，当 DLP 策略规则重定向消息时，需要指定将消息重定向到的位置。
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>DLP 策略的条件和异常

以下部分中的表描述了 DLP 中可用的条件和异常。

- [发件人](#senders)
- [收件人](#recipients)
- [邮件主题或正文](#message-subject-or-body)
- [附件](#attachments)
- [邮件头](#message-headers)
- [邮件属性](#message-properties)

### <a name="senders"></a>发件人

如果将发件人地址用作条件或例外，则查找值的实际字段因配置的发件人地址位置而异。 默认情况下，DLP 规则使用标头地址作为发件人地址。

![显示信封 (P1) 地址和标头 (P2) 地址之间的差异的电子邮件标头的图像](../media/dlp-conditions-exceptions-meetinginvite-callouts.png)

在租户级别，可以配置要跨所有规则使用的发件人地址位置，除非被单个规则重写。 若要设置租户 DLP 策略配置以跨所有规则从信封评估发件人地址，可以运行以下命令：

```PowerShell
Set-PolicyConfig -SenderAddressLocation Envelope
```

若要在 DLP 规则级别配置发件人地址位置，参数为 *SenderAddressLocation*。 可用值有：

- **标头**：仅检查消息标头中的发件人 (例如 **“发****件人”、“发件人**”或“**回复到**”字段) 。 此值为默认值。

- **信封**：仅检查邮件信封中的发件人 (SMTP 传输中使用的 **MAIL FROM** 值，该值通常存储在 **“返回路径** ”字段) 中。

- **头或信封** (`HeaderOrEnvelope`) 在邮件标头和邮件信封中检查发件人。

|DLP 中的条件或异常|Microsoft 365 PowerShell 中的条件/异常参数|属性类型|description|
|---|---|---|---|
|发件人为|条件： *从* <br/><br/> 异常： *ExceptIfFrom*|Addresses|由组织中的指定邮箱、邮件用户、邮件联系人或Microsoft 365组发送的消息。|
|发件人为以下组的成员 |*FromMemberOf* <br/><br/> *ExceptIfFromMemberOf*|Addresses|由指定通讯组、启用邮件的安全组或Microsoft 365组的成员发送的消息。|
|发件人 IP 地址为|条件： *SenderIPRanges*<br/><br/> 异常： *ExceptIfSenderIPRanges*|IPAddressRanges|发件人的 IP 地址匹配指定的 IP 地址或位于指定的 IP 地址范围内的邮件。|
|发件人地址包含单词|condition： *FromAddressContainsWords* <br/><br/> 异常： *ExceptIfFromAddressContainsWords*|Words|发件人电子邮件地址中包含指定词语的邮件。|
|发件人地址与模式匹配|条件： *FromAddressMatchesPatterns* <br/><br/> 异常： *ExceptFromAddressMatchesPatterns*|模式|发件人的电子邮件地址包含匹配指定正则表达式的文本模式的邮件。|
|发件人域为|条件： *SenderDomainIs* <br/><br/> 异常： *ExceptIfSenderDomainIs*|DomainName|发件人的电子邮件地址域与指定值匹配的邮件。 如果需要查找 *包含* 指定域 (的发件人域，例如，域的任何子域) ，请使用 **发件人地址与** *FromAddressMatchesPatterns* () 条件匹配，并使用语法“domaincom$”\.指定域\.。|
|发件人范围|条件： *FromScope* <br/><br/> 异常： *ExceptIfFromScope*|UserScopeFrom|由内部或外部发件人发送的消息。|
|发件人的指定属性包括以下任何词语|condition： *SenderADAttributeContainsWords* <br/><br/> 异常： *ExceptIfSenderADAttributeContainsWords*|首要属性： `ADAttribute` <br/><br/> 第二个属性： `Words`|发件人的指定的 Active Directory 属性包含任意的指定词语的邮件。|
|发件人的指定属性匹配这些文本模式|condition： *SenderADAttributeMatchesPatterns* <br/><br/> 异常： *ExceptIfSenderADAttributeMatchesPatterns*|首要属性： `ADAttribute` <br/><br/> 第二个属性： `Patterns`|发件人的指定的 Active Directory 属性包含与指定正则表达式匹配的文本模式的邮件|

### <a name="recipients"></a>收件人

|DLP 中的条件或异常|Microsoft 365 PowerShell 中的条件/异常参数|属性类型|description|
|---|---|---|---|
|收件人为|条件： *SentTo* <br/><br/> 异常： *ExceptIfSentTo*|Addresses|其中一个收件人是组织中的指定邮箱、邮件用户或邮件联系人的消息。 收件人可以位于邮件的 **To**、 **Cc** 或 **Bcc** 字段中。|
|收件人域为|条件： *RecipientDomainIs* <br/><br/> 异常： *ExceptIfRecipientDomainIs*|DomainName|收件人电子邮件地址的域与指定值匹配的消息。|
|收件人地址包含字词|condition： *AnyOfRecipientAddressContainsWords* <br/><br/> exception： *ExceptIfAnyOfRecipientAddressContainsWords*|Words|收件人电子邮件地址中包含指定词语的邮件。 <br/><br/>**注意**：此条件不考虑发送到收件人代理地址的邮件。它只匹配发送到收件人主电子邮件地址的邮件。|
|收件人地址与模式匹配|condition： *AnyOfRecipientAddressMatchesPatterns* <br/><br/> exception： *ExceptIfAnyOfRecipientAddressMatchesPatterns*|模式|收件人的电子邮件地址包含匹配指定正则表达式的文本模式的邮件。 <br/><br/> **注意**：此条件不考虑发送到收件人代理地址的邮件。它只匹配发送到收件人主电子邮件地址的邮件。|
|发送到成员|条件： *SentToMemberOf* <br/><br/> 异常： *ExceptIfSentToMemberOf*|Addresses|包含作为指定通讯组、启用邮件的安全组或Microsoft 365组成员的收件人的消息。 该组可以位于消息的 **To**、 **Cc** 或 **Bcc** 字段中。|
|收件人的指定属性包括以下任何词语 |*RecipientADAttributeContainsWords* <br/><br/> *ExceptIfRecipientADAttributeContainsWords*|首要属性： `ADAttribute` <br/><br/> 第二个属性： `Words`|收件人的指定的 Active Directory 属性包含任意的指定词语的邮件。 <br/><br/> 请注意， **国家/地区** 属性需要两个字母的国家/地区代码值 (例如，德国的 DE) 。|
|收件人的指定属性匹配这些文本模式 |*RecipientADAttributeMatchesPatterns* <br/><br/> *ExceptIfRecipientADAttributeMatchesPatterns*|首要属性： `ADAttribute` <br/><br/> 第二个属性： `Patterns`|收件人的指定的 Active Directory 属性包含与指定正则表达式匹配的文本模式的邮件。|

### <a name="message-subject-or-body"></a>邮件主题或正文

|DLP 中的条件或异常|Microsoft 365 PowerShell 中的条件/异常参数|属性类型|description|
|---|---|---|---|
|主题包含单词或短语|condition： *SubjectContainsWords* <br/><br/> 异常： *ExceptIf SubjectContainsWords*|Words|在" Subject "字段中包含指定词语的邮件。|
|主题与模式匹配|条件： *SubjectMatchesPatterns* <br/><br/> 异常： *ExceptIf SubjectMatchesPatterns*|模式|主题字段包含与指定正则表达式匹配的文本模式的消息。|
|内容包含|条件： *ContentContainsSensitiveInformation* <br/><br/> exception *ExceptIfContentContainsSensitiveInformation*|SensitiveInformationTypes|包含数据丢失防护定义的敏感信息的消息或文档 (DLP) 策略。|
|主题或正文匹配模式|条件： *SubjectOrBodyMatchesPatterns* <br/><br/> 异常： *ExceptIfSubjectOrBodyMatchesPatterns*|模式|主题字段或消息正文包含与指定正则表达式匹配的文本模式的消息。|
|主题或正文包含单词|condition： *SubjectOrBodyContainsWords* <br/><br/> 异常： *ExceptIfSubjectOrBodyContainsWords*|Words|主题字段或消息正文中具有指定字词的消息|

### <a name="attachments"></a>附件

|DLP 中的条件或异常|Microsoft 365 PowerShell 中的条件/异常参数|属性类型|description|
|---|---|---|---|
|附件受密码保护|条件： *DocumentIsPasswordProtected* <br/><br/> 异常： *ExceptIfDocumentIsPasswordProtected*|无|附件受密码保护的邮件（因而无法扫描）。 密码检测仅适用于Office文档、.zip文件和 .7z 文件。|
|附件的文件扩展名为|条件： *ContentExtensionMatchesWords* <br/><br/> 异常： *ExceptIfContentExtensionMatchesWords*|Words|附件的文件扩展名匹配任意指定词语的邮件。|
|无法扫描任何电子邮件附件的内容|条件： *DocumentIsUnsupported* <br/><br/>异常： *ExceptIf DocumentIsUnsupported*|不适用|未由Exchange Online本机识别附件的消息。|
|任何电子邮件附件的内容均未完成扫描|条件： *ProcessingLimitExceeded* <br/><br/> 异常： *ExceptIfProcessingLimitExceeded*|无|规则引擎无法完成附件扫描的邮件。可以使用此条件创建规则，以协同工作来标识并处理无法完全扫描内容的邮件。|
|文档名称包含单词|条件： *DocumentNameMatchesWords* <br/><br/> exception： *ExceptIfDocumentNameMatchesWords*|Words|附件的文件名与任何指定字词匹配的消息。|
|文档名称与模式匹配|条件： *DocumentNameMatchesPatterns* <br/><br/> 异常： *ExceptIfDocumentNameMatchesPatterns*|模式|附件的文件名包含匹配指定正则表达式的文本模式的邮件。|
|文档属性为|条件： *ContentPropertyContainsWords* <br/><br/> 异常： *ExceptIfContentPropertyContainsWords*|Words|附件的文件扩展名与任何指定字词匹配的消息或文档。|
|文档大小等于或大于|条件： *DocumentSizeOver* <br/><br/> 异常： *ExceptIfDocumentSizeOver*|Size|任何附件大于或等于指定值的邮件。|
|任何附件内容包含这些词语中的任何一个|条件： *DocumentContainsWords* <br/><br/> 异常： *ExceptIfDocumentContainsWords*|`Words`|附件包含指定词语的邮件。|
|任何附件内容都与这些文本模式匹配|条件： *DocumentMatchesPatterns* <br/><br/> exception： *ExceptIfDocumentMatchesPatterns*|`Patterns`|附件包含匹配指定正则表达式的文本模式的邮件。|

### <a name="message-headers"></a>邮件头

|DLP 中的条件或异常|Microsoft 365 PowerShell 中的条件/异常参数|属性类型|说明|
|---|---|---|---|
|标头包含单词或短语|condition： *HeaderContainsWords* <br/><br/> 异常： *ExceptIfHeaderContainsWords*|哈希表|包含指定标头字段的消息以及该标头字段的值包含指定的单词。|
|标题与模式匹配|condition： *HeaderMatchesPatterns* <br/><br/> 异常： *ExceptIfHeaderMatchesPatterns*|哈希表|包含指定标头字段的消息以及该标头字段的值包含指定的正则表达式。|

### <a name="message-properties"></a>邮件属性

|DLP 中的条件或异常|Microsoft 365 PowerShell 中的条件/异常参数|属性类型|description|
|---|---|---|---|
|重要性|condition： *WithImportance* <br/><br/> exception： *ExceptIfWithImportance*|重要性|标记有指定重要性级别的消息。|
|内容字符集包含单词|条件： *ContentCharacterSetContainsWords* <br/><br/> *ExceptIfContentCharacterSetContainsWords*|CharacterSets|具有任意指定字符集名称的邮件。|
|已重写发件人|condition： *HasSenderOverride* <br/><br/> 异常： *ExceptIfHasSenderOverride*|无|发件人已选择覆盖数据丢失防护 (DLP) 策略的邮件。 有关 DLP 策略的详细信息，请 [参阅有关数据丢失防护的了解](./dlp-learn-about-dlp.md)|
|消息类型匹配|条件： *MessageTypeMatches* <br/><br/> 异常： *ExceptIfMessageTypeMatches*|MessageType|指定类型的邮件。 **注意**：可用消息类型为自动回复、自动转发、加密 (S/MIME) 、日历、权限控制 (权限管理) 、Voicemail、Signed、Read receipt 和审批请求。 |
|邮件大小大于或等于|条件： *MessageSizeOver* <br/><br/> 异常： *ExceptIfMessageSizeOver*|`Size`|总大小（邮件和附件）大于或等于指定值的邮件。 **注意**：在确定邮件流规则之前将对邮箱的邮件大小限制进行评估。 对于邮箱而言过大的邮件将被拒绝，然后此条件的规则才能对该邮件采取措施。|

## <a name="actions-for-dlp-policies"></a>DLP 策略的操作

下表描述了 DLP 中可用的操作。

|DLP 中的操作|Microsoft 365 PowerShell 中的操作参数|属性类型|description|
|---|---|---|---|
|设置标头|SetHeader|第一个属性： *标头名称* <br/><br/> 第二个属性： *标头值*|SetHeader 参数指定 DLP 规则的操作，该规则在消息标头中添加或修改标头字段和值。 此参数使用语法“HeaderName：HeaderValue”。 可以指定多个标头名称和值对，用逗号分隔|
|删除标头|RemoveHeader|首要属性：*MessageHeaderField*<br/><br/> 次要属性：*String*|RemoveHeader 参数指定 DLP 规则的操作，该操作从消息标头中删除标头字段。 此参数使用语法“HeaderName”或“HeaderName：HeaderValue”。可以指定多个标头名称或标头名称以及用逗号分隔的值对|
|将消息重定向到特定用户|*RedirectMessageTo*|Addresses|将电子邮件重定向到指定的收件人。邮件不会传递给原始收件人，也不会向发件人或原始收件人发送通知。|
|将要批准的消息转发给发件人的经理|适度|第一个属性： *ModerateMessageByManager*<br/><br/> 第二个属性： *布尔值*|Moderate 参数指定 DLP 规则的操作，该操作将电子邮件发送给审查器。 此参数使用语法：@{ModerateMessageByManager = <$true $false> \|;|
|将要批准的消息转发给特定审批者|适度|第一个属性： *ModerateMessageByUser*<br/><br/>次要属性：*Addresses*|Moderate 参数指定 DLP 规则的操作，该操作将电子邮件发送给审查器。 此参数使用语法：@{ ModerateMessageByUser = @ (“emailaddress1”，“emailaddress2”,...“emailaddressN”) }|
|添加收件人|AddRecipients|第一个属性： *字段*<br/><br/>次要属性：*Addresses*|将一个或多个收件人添加到邮件的 To/Cc/Bcc 字段。 此参数使用语法：@{<AddToRecipients \<CopyTo \| BlindCopyTo\> = “emailaddress”}|
|将发件人的经理添加为收件人|AddRecipients|第一个属性： *AddedManagerAction*<br/><br/>第二个属性： *字段*|将发件人的经理添加到邮件中作为指定收件人类型 (To、Cc、Bcc)，或在不通知发件人或收件人的情况下将邮件重定向到发件人的经理。 此操作仅在发件人的 Manager 属性于 Active Directory 中定义时适用。 此参数使用语法：@{AddManagerAsRecipientType = “\<To \| Cc \| Bcc\>”}|
Prepend 主题|PrependSubject|String|将指定的文本添加到邮件" Subject "字段的开头。考虑使用空格或冒号 (:) 作为指定文本的最后一个字符以区别于原始的主题文本。  <br/><br/>若要防止将同一字符串添加到主题 (中已包含文本的消息中，请) 答复，请将“主题包含单词”添加 (ExceptIfSubjectContainsWords) 规则例外。|
|应用 HTML 免责声明|ApplyHtmlDisclaimer|第一个属性： *文本*<br/><br/>第二个属性： *位置*<br/><br/>第三个属性： *回退操作*|将指定的 HTML 免责声明应用于消息的所需位置。<br/><br/>此参数使用语法： @{ Text = " " Location = \<Append \| Prepend\>;FallbackAction = \<Wrap \| Ignore \| Reject\> }|
|删除Office 365消息加密和权限保护|RemoveRMSTemplate|不适用|删除在电子邮件上应用的Office 365加密|
|将消息传递到托管隔离区 |*Quarantine*|无| 此操作目前以 **公共预览版提供**。 在此阶段，DLP 策略隔离的电子邮件将显示为 ExchangeTransportRule 的策略类型。<br/><br/> 将消息传递到 EOP 中的隔离区。 有关详细信息，请参阅 [EOP 中的隔离电子邮件](/microsoft-365/security/office-365-security/quarantine-email-messages)。|

<!--|Modify Subject|ModifySubject|PswsHashTable | Remove text from the subject line that matches a specific pattern and replace it with different text. See the example below. You can: <br/><br/>- **Replace** all matches in the subject with the replacement text <br/><br/>- **Append** to remove all matches in the subject and inserts the replacement text at the end of the subject. <br/><br/>- **Prepend** to remove all matches and inserts the replacement text at the beginning of the subject. See ModifySubject parameter in, /powershell/module/exchange/new-dlpcompliancerule|-->
