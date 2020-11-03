---
title: 'DLP 策略条件和例外 (预览) '
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解 dlp 策略条件和例外
ms.openlocfilehash: 2ce49b15bdb13035a37f6895b4b8865b55a62f78
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841466"
---
# <a name="dlp-policy-conditions-and-exceptions-preview"></a>DLP 策略条件和例外 (预览) 

DLP 策略中的条件和例外标识策略所应用于的敏感项目。 条件定义要包括的内容和例外定义要排除的内容。 对于每个条件，都存在一个对应的例外，并且它们使用完全相同的语法。

 大多数条件和异常都有一个支持一个或多个值的属性。 例如，如果将 DLP 策略应用于 Exchange 电子邮件，则 **"发件人是"** 条件需要邮件的发件人。 一些条件有两个属性。 例如，“ **邮件头包含以下任何词语** ”条件需要一个属性来指定邮件头字段，需要第二个属性来指定要在头字段中查找的文本。 有些条件或例外项没有任何属性。 例如， **附件是受密码保护的** 条件只是在受密码保护的邮件中查找附件。

## <a name="conditions-and-exceptions-for-dlp-policies"></a>DLP 策略的条件和例外

以下各节中的表介绍了 DLP 中可用的条件和例外。

- [发件人](#senders)
- [收件人](#recipients)
- [邮件主题或正文](#message-subject-or-body)
- [附件](#attachments)
- [邮件头](#message-headers)
- [邮件属性](#message-properties)

## <a name="senders"></a>Senders


|**DLP 中的条件或例外**  |**Microsoft 365 PowerShell 中的条件/异常参数** |**属性类型**  |**说明**|
|---------|---------|---------|---------|
|发件人为 |条件： *从* <br/> 异常： *ExceptIfFrom*      |Addresses |     由组织中的指定邮箱、邮件用户、邮件联系人或 Microsoft 365 组发送的邮件。|
|发件人 IP 地址为     |条件： *SenderIPRanges*<br/> 异常： *ExceptIfSenderIPRanges*         |  IPAddressRanges       | 发件人的 IP 地址匹配指定的 IP 地址或位于指定的 IP 地址范围内的邮件。       |
|发件人地址包含单词   | 条件： *FromAddressContainsWords* <br/> 异常： *ExceptIfFromAddressContainsWords*        |   Words      |   发件人电子邮件地址中包含指定词语的邮件。|
| 发件人地址匹配模式    | 条件： *FromAddressMatchesPatterns* <br/> 异常： *ExceptFromAddressMatchesPatterns*       |      模式   |  发件人的电子邮件地址包含匹配指定正则表达式的文本模式的邮件。  |
|发件人域为  |  条件： *SenderDomainIs* <br/> 异常： *ExceptIfSenderDomainIs*       |称         |     发件人的电子邮件地址域与指定值匹配的邮件。 如果您需要查找 *包含* 指定域的发件人域 (例如，域) 的任何子域，请使用 **发件人地址匹配** ( *FromAddressMatchesPatterns* ) 条件，并使用语法： ' \. domain \. com $ ' 指定域。    |

## <a name="recipients"></a>收件人

|**DLP 中的条件或例外**| **Microsoft 365 PowerShell 中的条件/异常参数** |    **属性类型** | **说明**|
|---------|---------|---------|---------|
|收件人为|  条件： *SentTo* <br/> 异常： *ExceptIfSentTo* | Addresses | 其中一个收件人是组织中指定的邮箱、邮件用户或邮件联系人的邮件。 收件人可以在邮件的 " **收件人** "、 **"抄送** " 或 **"密件抄送** " 字段中。|
|收件人域为|   条件： *RecipientDomainIs* <br/> 异常： *ExceptIfRecipientDomainIs* |   称 |    发件人的电子邮件地址域与指定值匹配的邮件。|
|收件人地址包含单词|  条件： *RecipientAddressContainsWords* <br/> 异常： *ExceptIfRecipientAddressContainsWords*|    Words|  收件人电子邮件地址中包含指定词语的邮件。 <br/>**注意** ：此条件不考虑发送到收件人代理地址的邮件。它只匹配发送到收件人主电子邮件地址的邮件。|
|收件人地址匹配模式| 条件： *RecipientAddressMatchesPatterns* <br/> 异常： *ExceptIfRecipientAddressMatchesPatterns*|   模式    |收件人的电子邮件地址包含匹配指定正则表达式的文本模式的邮件。 <br/> **注意** ：此条件不考虑发送到收件人代理地址的邮件。它只匹配发送到收件人主电子邮件地址的邮件。|
|发送给的成员| 条件： *SentToMemberOf* <br/> 异常： *ExceptIfSentToMemberOf*|  Addresses|  包含指定通讯组成员、已启用邮件的安全组或 Microsoft 365 组的收件人的邮件。 该组可以位于邮件的 " **收件人** "、 **"抄送** " 或 **"密件抄送** " 字段中。|

## <a name="message-subject-or-body"></a>邮件主题或正文

|**DLP 中的条件或例外** | **Microsoft 365 PowerShell 中的条件/异常参数** |**属性类型**| **说明**|
|---------|---------|---------|---------|
|主题包含字词或短语| 条件： *SubjectContainsWords* <br/> 异常： *ExceptIf SubjectContainsWords*| Words   |在" Subject "字段中包含指定词语的邮件。|
|主题匹配模式|条件： *SubjectMatchesPatterns* <br/> 异常： *ExceptIf SubjectMatchesPatterns*|模式   |"Subject" 字段包含匹配指定正则表达式的文本模式的邮件。|
|内容包含|  条件： *ContentContainsSensitiveInformation* <br/> 异常 *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  包含由数据丢失防护 (DLP) 策略定义的敏感信息的邮件或文档。|


## <a name="attachments"></a>Attachments

|**DLP 中的条件或例外**| **Microsoft 365 PowerShell 中的条件/异常参数**| **属性类型**   |**说明**|
|---------|---------|---------|---------|
|附件受密码保护|条件： *DocumentIsPasswordProtected* <br/> 异常： *ExceptIfDocumentIsPasswordProtected*|无| 附件受密码保护的邮件（因而无法扫描）。 密码检测仅适用于 Office 文档和 .zip 文件。|
|附件的文件扩展名为|条件： *ContentExtensionMatchesWords* <br/> 异常： *ExceptIfContentExtensionMatchesWords*|  Words   |附件的文件扩展名匹配任意指定词语的邮件。|
|无法扫描任何电子邮件附件的内容|条件： *DocumentIsUnsupported* <br/>异常： *ExceptIf DocumentIsUnsupported*|   不适用|    Exchange Online 本身不会识别其附件的邮件。|
|任何电子邮件附件的内容未完成扫描|   条件： *ProcessingLimitExceeded* <br/> 异常： *ExceptIfProcessingLimitExceeded*|    无 |规则引擎无法完成附件扫描的邮件。可以使用此条件创建规则，以协同工作来标识并处理无法完全扫描内容的邮件。|
|文档名称包含单词|条件： *DocumentNameMatchesWords* <br/> 异常： *ExceptIfDocumentNameMatchesWords* |Words  |附件的文件名匹配任何指定单词的邮件。|
|文档名称匹配模式|条件： *DocumentNameMatchesPatterns* <br/> 异常： *ExceptIfDocumentNameMatchesPatterns*|    模式    |附件的文件名包含匹配指定正则表达式的文本模式的邮件。|
|文档属性为|条件： *ContentPropertyContainsWords* <br/> 异常： *ExceptIfContentPropertyContainsWords* |Words| 附件的文件扩展名与任何指定词语相匹配的邮件或文档。|
|文档大小等于或大于| 条件： *DocumentSizeOver* <br/> 异常： *ExceptIfDocumentSizeOver*|    Size    |任何附件大于或等于指定值的邮件。|

## <a name="message-headers"></a>邮件头

|**DLP 中的条件或例外**| **Microsoft 365 PowerShell 中的条件/异常参数**| **属性类型**|  **说明**|
|---------|---------|---------|---------|
|标头包含字词或短语|条件： *HeaderContainsWords* <br/> 异常： *ExceptIfHeaderContainsWords*|  哈希表  |包含指定的标头字段的消息和该标头字段的值包含指定的单词。|
|标头匹配模式|   条件： *HeaderMatchesPatterns* <br/> 异常： *ExceptIfHeaderMatchesPatterns*|    哈希表  |包含指定的标头字段的消息，并且该标头字段的值包含指定的正则表达式。|

## <a name="message-properties"></a>邮件属性

|**DLP 中的条件或例外**| **Microsoft 365 PowerShell 中的条件/异常参数**| **属性类型**   |**说明**|
|---------|---------|---------|---------|
|邮件大小超过|条件： *MessageSizeOver* <br/> 异常： *ExceptIfMessageSizeOver*| Size    |总大小（邮件和附件）大于或等于指定值的邮件。 <br/>**注意** ：在确定邮件流规则之前将对邮箱的邮件大小限制进行评估。对于邮箱而言过大的邮件将被拒绝，然后此条件的规则才能对该邮件采取措施。|

