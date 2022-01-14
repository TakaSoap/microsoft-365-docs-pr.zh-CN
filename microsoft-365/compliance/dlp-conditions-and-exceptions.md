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
description: 了解 dlp 策略条件和例外
ms.openlocfilehash: 7c57d3f1f4e6c05cf5fe346440d59e7c5f9daac2
ms.sourcegitcommit: f563b4229760fa099703296d1ad2c1f0264f1647
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2022
ms.locfileid: "62041038"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>DLP 策略条件、异常和操作

DLP 策略中的条件和例外可标识策略应用于的敏感项目。 操作定义因满足例外条件而发生的情况。

- 条件定义要包含内容
- 异常定义要排除哪些内容。
- 操作定义因满足条件或例外而发生的情况

大多数条件和例外都有一个支持一个或多个值的属性。 例如，如果 DLP 策略应用于Exchange，则"**发件人是"** 条件需要邮件的发件人。 一些条件有两个属性。 例如，“**邮件头包含以下任何词语**”条件需要一个属性来指定邮件头字段，需要第二个属性来指定要在头字段中查找的文本。 某些条件或例外没有任何属性。 例如 **，"附件受密码保护"** 条件只是查找邮件中受密码保护的附件。

操作通常需要其他属性。 例如，当 DLP 策略规则重定向邮件时，需要指定邮件重定向到何处。
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>DLP 策略的条件和例外

以下各节中的表介绍了 DLP 中可用的条件和例外。

- [发件人](#senders)
- [收件人](#recipients)
- [邮件主题或正文](#message-subject-or-body)
- [附件](#attachments)
- [邮件头](#message-headers)
- [邮件属性](#message-properties)

### <a name="senders"></a>Senders

如果使用发件人地址作为条件或例外，则查找值的实际字段因使用的规则类型而异。 对于基于 DLP 的规则，信封地址用作发件人地址。 例如Exchange邮件头地址用作发件人地址。
<!-- REMOVE COMMENTS ON 1/20/2022
> [!NOTE]
> Starting January 20, 2022, the default sender address location will be moved to the Header address along with the availability of the -SenderAddressLocation parameter to configure desired behavior at a DLP rule level.

![image](https://user-images.githubusercontent.com/53205984/145942298-6b435ba6-d146-44fe-a1c5-58babeaf8d7a.png)

At the tenant level, you can configure a sender address location to be used across all rules, unless overridden by a single rule. To revert tenant DLP policy configuration to evaluate the sender address from the Envelope across all rules, you can run the following command:

```PowerShell
Set-PolicyConfig –SenderAddressLocation Envelope
```

To configure the sender address location at a DLP rule level, the parameter is _SenderAddressLocation_. The available values are:

- **Header**: Only examine senders in the message headers (for example, the **From**, **Sender**, or **Reply-To** fields). This is the default value.

- **Envelope**: Only examine senders from the message envelope (the **MAIL FROM** value that was used in the SMTP transmission, which is typically stored in the **Return-Path** field).

- **Header or envelope** (`HeaderOrEnvelope`) Examine senders in the message header and the message envelope.
<br>
-->

|DLP 中的条件或例外|powerShell 中的条件/Microsoft 365参数|属性类型|description|
|---|---|---|---|
|发件人为|condition： *From* <br/> exception： *ExceptIfFrom*|Addresses|由组织中指定的邮箱、邮件用户、邮件联系人或Microsoft 365组发送的邮件。|
|发件人为以下组的成员 |_FromMemberOf_ <br/> _ExceptIfFromMemberOf_|Addresses|由指定通讯组、已启用邮件的安全组或通讯组的成员Microsoft 365的邮件。|
|发件人 IP 地址为|condition： *SenderIPRanges*<br/> 例外 *：ExceptIfSenderIPRanges*|IPAddressRanges|发件人的 IP 地址匹配指定的 IP 地址或位于指定的 IP 地址范围内的邮件。|
|发件人地址包含词语|condition： *FromAddressContainsWords* <br/> exception： *ExceptIfFromAddressContainsWords*|Words|发件人电子邮件地址中包含指定词语的邮件。|
|发件人地址与模式匹配|condition： *FromAddressMatchesPatterns* <br/> exception： *ExceptFromAddressMatchesPatterns*|模式|发件人的电子邮件地址包含匹配指定正则表达式的文本模式的邮件。|
|发件人域为|condition： *SenderDomainIs* <br/> 例外 *：ExceptIfSenderDomainIs*|DomainName|发件人的电子邮件地址域与指定值匹配的邮件。 如果需要查找包含指定域 (例如域) 的任何子域的发件人域，请使用与 **(** *FromAddressMatchesPatterns*) 条件匹配的发件人地址，并使用语法"' \. domain \. com$"指定域。|
|发件人作用域|condition： *FromScope* <br/> exception： *ExceptIfFromScope*|UserScopeFrom|由内部或外部发件人发送的邮件。|
|发件人的指定属性包括以下任何词语|condition： *SenderADAttributeContainsWords* <br/> 例外 *：ExceptIfSenderADAttributeContainsWords*|首要属性： `ADAttribute` <p> 第二个属性： `Words`|发件人的指定的 Active Directory 属性包含任意的指定词语的邮件。|
|发件人的指定属性匹配这些文本模式|condition： *SenderADAttributeMatchesPatterns* <br/> 例外 *：ExceptIfSenderADAttributeMatchesPatterns*|首要属性： `ADAttribute` <p> 第二个属性： `Patterns`|发件人的指定的 Active Directory 属性包含与指定正则表达式匹配的文本模式的邮件|
|

### <a name="recipients"></a>收件人

<br>

****

|DLP 中的条件或例外|powerShell 中的条件/Microsoft 365参数|属性类型|说明|
|---|---|---|---|
|收件人为|condition： *SentTo* <br/> exception： *ExceptIfSentTo*|Addresses|其中一个收件人是组织中指定的邮箱、邮件用户或邮件联系人的邮件。 收件人可以在邮件的"**收件人****"、"抄** 送"**或"密件** 抄送"字段中。|
|收件人域为|condition： *RecipientDomainIs* <br/> exception： *ExceptIfRecipientDomainIs*|DomainName|收件人电子邮件地址的域与指定值匹配的邮件。|
|收件人地址包含字词|condition： *AnyOfRecipientAddressContainsWords* <br/> exception： *ExceptIfAnyOfRecipientAddressContainsWords*|Words|收件人电子邮件地址中包含指定词语的邮件。 <br/>**注意**：此条件不考虑发送到收件人代理地址的邮件。它只匹配发送到收件人主电子邮件地址的邮件。|
|收件人地址与模式匹配|condition： *AnyOfRecipientAddressMatchesPatterns* <br/> exception： *ExceptIfAnyOfRecipientAddressMatchesPatterns*|模式|收件人的电子邮件地址包含匹配指定正则表达式的文本模式的邮件。 <br/> **注意**：此条件不考虑发送到收件人代理地址的邮件。它只匹配发送到收件人主电子邮件地址的邮件。|
|发送到的|condition： *SentToMemberOf* <br/> exception： *ExceptIfSentToMemberOf*|Addresses|包含收件人的邮件，这些收件人是指定通讯组、已启用邮件的安全组或Microsoft 365组。 组可以在邮件的"**收件人****"、"** 抄送"**或"密** 件抄送"字段中。|
|收件人的指定属性包括以下任何词语 |_RecipientADAttributeContainsWords_ <br/> _ExceptIfRecipientADAttributeContainsWords_|首要属性： `ADAttribute` <p> 第二个属性： `Words`|收件人的指定的 Active Directory 属性包含任意的指定词语的邮件。 <p> 请注意 **，Country** 属性需要两个字母的国家/地区代码值 (，例如，DE 表示德国) 。|
|收件人的指定属性匹配这些文本模式 |_RecipientADAttributeMatchesPatterns_ <br/> _ExceptIfRecipientADAttributeMatchesPatterns_|首要属性： `ADAttribute` <p> 第二个属性： `Patterns`|收件人的指定的 Active Directory 属性包含与指定正则表达式匹配的文本模式的邮件。|
|

### <a name="message-subject-or-body"></a>邮件主题或正文

<br>

****

|DLP 中的条件或例外|powerShell 中的条件/Microsoft 365参数|属性类型|description|
|---|---|---|---|
|主题包含字词或短语|condition： *SubjectContainsWords* <br/> exception： *ExceptIf SubjectContainsWords*|Words|在" Subject "字段中包含指定词语的邮件。|
|主题与模式匹配|condition： *SubjectMatchesPatterns* <br/> exception： *ExceptIf SubjectMatchesPatterns*|模式|Subject 字段包含匹配指定正则表达式的文本模式的邮件。|
|内容包含|condition： *ContentContainsSensitiveInformation* <br/> exception *ExceptIfContentContainsSensitiveInformation*|SensitiveInformationTypes|包含由 DLP 策略中的数据丢失防护定义的敏感信息 () 文档。|
|主题或正文匹配模式|condition： *SubjectOrBodyMatchesPatterns* <br/> exception： *ExceptIfSubjectOrBodyMatchesPatterns*|模式|主题字段或邮件正文包含匹配指定正则表达式的文本模式的邮件。|
|主题或正文包含字词|condition： *SubjectOrBodyContainsWords* <br/> exception： *ExceptIfSubjectOrBodyContainsWords*|Words|主题字段或邮件正文中具有指定词语的邮件|
|

### <a name="attachments"></a>附件

<br>

****

|DLP 中的条件或例外|powerShell 中的条件/Microsoft 365参数|属性类型|description|
|---|---|---|---|
|附件受密码保护|condition： *DocumentIsPasswordProtected* <br/> exception： *ExceptIfDocumentIsPasswordProtected*|无|附件受密码保护的邮件（因而无法扫描）。 密码检测仅适用于Office文件.zip .7z 文件。|
|附件的文件扩展名为|condition： *ContentExtensionMatchesWords* <br/> 例外 *：ExceptIfContentExtensionMatchesWords*|Words|附件的文件扩展名匹配任意指定词语的邮件。|
|无法扫描任何电子邮件附件的内容|condition： *DocumentIsUnsupported* <br/>exception： *ExceptIf DocumentIsUnsupported*|不适用|附件在本机无法被用户识别Exchange Online。|
|任何电子邮件附件的内容未完成扫描|condition： *ProcessingLimitExceeded* <br/> 例外 *：ExceptIfProcessingLimitExceeded*|无|规则引擎无法完成附件扫描的邮件。可以使用此条件创建规则，以协同工作来标识并处理无法完全扫描内容的邮件。|
|文档名称包含单词|condition： *DocumentNameMatchesWords* <br/> exception： *ExceptIfDocumentNameMatchesWords*|Words|附件的文件名与任意指定词语匹配的邮件。|
|文档名称与模式匹配|condition： *DocumentNameMatchesPatterns* <br/> exception： *ExceptIfDocumentNameMatchesPatterns*|模式|附件的文件名包含匹配指定正则表达式的文本模式的邮件。|
|文档属性为|condition： *ContentPropertyContainsWords* <br/> 例外 *：ExceptIfContentPropertyContainsWords*|Words|附件的文件扩展名与任意指定词语匹配的邮件或文档。|
|文档大小等于或大于|condition： *DocumentSizeOver* <br/> exception： *ExceptIfDocumentSizeOver*|Size|任何附件大于或等于指定值的邮件。|
|任何附件内容包含这些词语中的任何一个|condition： *DocumentContainsWords* <br/> exception： *ExceptIfDocumentContainsWords*|`Words`|附件包含指定词语的邮件。|
|任何附件内容与这些文本模式匹配|condition： *DocumentMatchesPatterns* <br/> exception： *ExceptIfDocumentMatchesPatterns*|`Patterns`|附件包含匹配指定正则表达式的文本模式的邮件。|
|

### <a name="message-headers"></a>邮件头

<br>

****

|DLP 中的条件或例外|powerShell 中的条件/Microsoft 365参数|属性类型|description|
|---|---|---|---|
|标头包含单词或短语|condition： *HeaderContainsWords* <br/> exception： *ExceptIfHeaderContainsWords*|哈希表|包含指定头字段的邮件，以及该头字段的值包含指定的单词。|
|标题与模式匹配|condition： *HeaderMatchesPatterns* <br/> exception： *ExceptIfHeaderMatchesPatterns*|哈希表|包含指定标头字段以及该头字段的值的邮件包含指定的正则表达式。|

### <a name="message-properties"></a>邮件属性

<br>

****

|DLP 中的条件或例外|powerShell 中的条件/Microsoft 365参数|属性类型|description|
|---|---|---|---|
|重要性|condition： *WithImportance* <br/> exception： *ExceptIfWithImportance*|Importance|使用指定的重要性级别标记的邮件。|
|内容字符集包含单词|condition： *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*|CharacterSets|具有任意指定字符集名称的邮件。|
|具有发件人替代|condition： *HasSenderOverride* <br/> 例外 *：ExceptIfHasSenderOverride*|无|发件人已选择覆盖数据丢失防护 (DLP) 策略的邮件。 有关 DLP 策略详细信息，请参阅 [了解数据丢失防护](./dlp-learn-about-dlp.md)|
|邮件类型匹配|condition： *MessageTypeMatches* <br/> exception： *ExceptIfMessageTypeMatches*|MessageType|指定类型的邮件。|
|邮件大小大于或等于|condition： *MessageSizeOver* <br/> exception： *ExceptIfMessageSizeOver*|`Size`|总大小（邮件和附件）大于或等于指定值的邮件。 **注意**：在确定邮件流规则之前将对邮箱的邮件大小限制进行评估。 对于邮箱而言过大的邮件将被拒绝，然后此条件的规则才能对该邮件采取措施。|
|

## <a name="actions-for-dlp-policies"></a>DLP 策略的操作

此表介绍 DLP 中可用的操作。

<br>

****

|DLP 中的操作|Microsoft 365 PowerShell 中的操作参数|属性类型|description|
|---|---|---|---|
|设置标头|SetHeader|第一个属性 *：Header Name* </br> 第二个属性 *：Header 值*|SetHeader 参数指定 DLP 规则在邮件头中添加或修改头字段和值的操作。 此参数使用语法"HeaderName：HeaderValue"。 可以指定用逗号分隔的多个标头名称和值对|
|删除标头|RemoveHeader|首要属性：*MessageHeaderField*</br> 次要属性：*String*|RemoveHeader 参数指定 DLP 规则从邮件头中删除头字段的操作。 此参数使用语法"HeaderName"或"HeaderName：HeaderValue"。可以指定多个标头名称或标头名称以及用逗号分隔的值对|
|将邮件重定向到特定用户|*RedirectMessageTo*|Addresses|将电子邮件重定向到指定的收件人。邮件不会传递给原始收件人，也不会向发件人或原始收件人发送通知。|
|将邮件转发给发件人的经理进行审批|适度|第一个属性 *：ModerateMessageByManager*</br> 第二个属性 *：Boolean*|Moderate 参数指定向审查方发送电子邮件的 DLP 规则的操作。 此参数使用语法 @{ModerateMessageByManager = <$true \| $false>;|
|将邮件转发给特定审批者进行审批|适度|第一个属性 *：ModerateMessageByUser*</br>次要属性：*Addresses*|Moderate 参数指定向审查方发送电子邮件的 DLP 规则的操作。 此参数使用语法：@{ ModerateMessageByUser = @ ("emailaddress1"，"emailaddress2",..."emailaddressN") }|
|添加收件人|AddRecipients|第一个属性 *：Field*</br>次要属性：*Addresses*|将一个或多个收件人添加到邮件的"收件人/抄送/密件抄送"字段中。 此参数使用语法 ：@{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|将发件人的经理添加为收件人|AddRecipients|第一个属性 *：AddedManagerAction*</br>Second 属性 *：Field*|将发件人的经理添加到邮件中作为指定收件人类型 (To、Cc、Bcc)，或在不通知发件人或收件人的情况下将邮件重定向到发件人的经理。 此操作仅在发件人的 Manager 属性于 Active Directory 中定义时适用。 此参数使用语法：@{AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|
Prepend subject|PrependSubject|String|将指定的文本添加到邮件" Subject "字段的开头。考虑使用空格或冒号 (:) 作为指定文本的最后一个字符以区别于原始的主题文本。  </br>若要防止将同一字符串添加到主题 (中已包含文本的邮件（例如，答复) ），请向规则添加"主题包含单词" (ExceptIfSubjectContainsWords) 例外。|
|修改主题|ModifySubject|PswsHashTable | 从与特定模式匹配的主题行中删除文本，并将其替换为不同的文本。 请参阅下面的示例。 可以执行下列操作： </br>- **将** 主题中所有匹配项替换为替换文本 </br>- **追加** 以删除主题中所有匹配项，并将替换文本插入到主题的末尾。 </br>- **在删除** 所有匹配项之前，在主题开头插入替换文本。|
|应用 HTML 免责声明|ApplyHtmlDisclaimer|第一个属性 *：Text*</br>Second 属性 *：Location*</br>第三个属性 *：回退操作*|将指定的 HTML 免责声明应用于邮件的所需位置。</br>此参数使用语法：@{ Text = " " ;Location = <\| Append Prepend>;FallbackAction = <\| Wrap Ignore Reject> \| }|
|删除Office 365 邮件加密和权限保护|RemoveRMSTemplate|不适用|删除Office 365应用于电子邮件的加密|
|
