---
title: 高级电子数据展示中的文档元数据字段
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文定义审阅集内文档的元数据字段，例如Advanced eDiscovery文档Microsoft 365。
ms.openlocfilehash: 0dd0c11360a1e815c950e6e01448d95a79a8e266
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177539"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>高级电子数据展示中的文档元数据字段

下表列出了审阅集内文档的元数据字段，其中一种情况Advanced eDiscovery。 该表提供以下信息：

- **字段名称和****显示字段名称**：元数据字段的名称以及查看审阅集内选定文档的文件元数据时显示的字段名称。 查看文档的文件元数据时，不包含某些元数据字段。 这些字段用星号* (突出显示) 。

- **可搜索字段名称：** 运行审阅集查询时可以搜索 [的属性的名称](review-set-search.md)。 空单元格表示无法搜索审阅集查询中的字段。

- **导出的字段名称：** 导出文档时包含的元数据字段的名称。  空单元格表示字段不包含在导出的元数据中。

- **说明：** 元数据字段的说明。

> [!NOTE]
> 审阅 **集搜索** 中的关键字 [字段使用](./review-set-search.md) 关键字查询语言 (KQL) 。 "可搜索字段名称"列中列出的字段可在审阅集搜索的 **"** 关键字"字段中使用，以形成复杂的查询，而无需使用查询生成器。 有关 KQL 详细信息，请参阅 [关键字查询语言语法参考](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。

<br>

****

|字段名和显示字段名|可搜索字段名称|导出的字段名称|说明|
|---|---|---|---|
|附件内容 ID|AttachmentContentId||项目的附件内容 ID。|
|律师客户特权分数|AttorneyClientPrivilegeScore||律师-客户特权模型内容分数。|
|作者|作者|Doc_authors|从文档元数据创作。|
|BCC|Bcc|Email_bcc|邮件类型的"Bcc"字段。 格式为 **DisplayName \<SMTPAddress\>**。|
|CC|Cc|Email_cc|邮件类型的"抄送"字段。 格式为 **DisplayName \<SMTPAddress\>**。|
|合规性标签|ComplianceLabels|Compliance_labels|[应用于网站](retention.md)中内容的保留Office 365。|
|复合路径|CompoundPath|Compound_path|描述项目源的可读路径。|
|内容*|内容||已提取项目的文本。|
|对话正文|ConversationBody||项目的对话正文。|
|对话 ID|ConversationId|Conversation_ID|邮件的对话 ID。 对于Teams一对一和群组聊天，同一对话内的所有转录文件及其系列项目共享同一对话 ID。 有关详细信息，请参阅 Advanced eDiscovery[中的内容的工作流Microsoft Teams。](teams-workflow-in-advanced-ediscovery.md)|
|对话索引||Conversation_index|邮件的对话索引。|
|对话名称||ConversationName|频道中频道Teams。 名称的格式取决于通道的类型： <br>Teams频道聊天和私人频道聊天：\<Name of team, name of channel\> <br>Teams一对一和群聊：所有聊天参与者的显示名称和电子邮件地址<br>Yammer社区：Community名称 + 帖子的前 120 个字符<br>Yammer私有：发件人姓名和电子邮件地址 + 邮件的前 120 个字符|
|对话 Pdf 时间|ConversationPdfTime||创建对话的 PDF 版本的日期。|
|对话修订消耗时间|ConversationRedactionBurnTime||为聊天创建对话的 PDF 版本的日期。|
|对话主题|ConversationTopic||项目的对话主题。|
|对话类型|ConversationType|ConversationType|聊天对话的类型。 值为： <br> Teams 1：1 和群聊及Yammer对话：**分组** 针对<br>Teams频道和专用频道：**频道**|
|包含已编辑邮件|ContainsEditedMessage|ContainsEditedMessage|指示聊天脚本Teams脚本是否包含已编辑的消息
|||Converted_file_path|转换后的导出文件的路径。 对于内部 Microsoft，请使用 。|
|Custodian|Custodian|Custodian|与项目关联的保管人的名称。|
|日期|日期|日期|Date 是依赖于文件类型的计算字段。<p>电子邮件：发送日期<br>电子邮件附件：文档的上次修改日期;如果不可用，则说明父级的发送日期<br>嵌入文档：文档的上次修改日期;如果不可用，则父项的上次修改日期<br>SPO 文档 (包括新式) ：SharePoint上次修改日期;如果不可用，则文档上次修改日期<br>非Office 365文档：上次修改日期<br>会议：会议开始日期<br>VoiceMail：发送日期<br>IM：发送日期<br>Teams：发送日期|
|文档注释|DocComments|Doc_comments|文档元数据中的注释。|
|文档公司||Doc_company|文档元数据中的公司。|
|创建文档的日期|CreatedTime|Doc_date_created|从文档元数据创建日期。|
|DocIndex*|||系列中的索引。 **-1** 或 **0** 表示它是根。|
|文档关键字||Doc_keywords|文档元数据中的关键字。|
|修改者的文档||Doc_modified_by|文档元数据的上次修改日期。|
|文档修订|Doc_Version|Doc_Version|文档元数据的修订。|
|文档主题||Doc_subject|文档元数据中的主题。|
|文档模板||Doc_template|文档元数据中的模板。|
|DocLastSavedBy||Doc_last_saved_by|上次保存文档的用户的名称。|
|基准主题|DominantTheme|Dominant_theme|计算用于分析的基准主题。|
|重复子集||Duplicate_subset|完全重复项的组 ID。|
|EmailAction*||Email_action|值为 **None、Reply** 或 **Forward;** 基于邮件的主题行。|
|请求的电子邮件传递回执||Email_delivery_receipt|Internet 邮件头中提供的电子邮件地址，用于送达回执。|
|重要性|EmailImportance|Email_importance|邮件的重要性 **：0** - 低; **1** - 正常; **2** - 高|
|忽略处理错误|ErrorIgnored|Error_Ignored|错误已忽略且未修正。|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|电子邮件的完整电子邮件头集|
|EmailLevel*||Email_level|指示邮件所属电子邮件线程中的邮件级别;attachments 继承其父邮件的值。|
|电子邮件 ID||Email_message_ID|邮件中的 Internet 邮件 ID。|
|EmailReadReceiptRequested||Email_read_receipt|在 Internet 标头中为已读回执提供的电子邮件地址。|
|电子邮件安全性|EmailSecurity|Email_security|邮件的安全策略设置 **：0** - 无; **1** - 已签名; **2** - 加密; **3** - 加密和签名。|
|电子邮件敏感度|EmailSensitivity|email_sensitivity|邮件的敏感度设置 **：0** - 无; **1** 个人; **2** - 专用; **3** - CompanyConfidential。|
|电子邮件集|EmailSet|Email_set|同一电子邮件集内所有邮件的组 ID。|
|EmailThread*||Email_thread|邮件在电子邮件集内的位置;由从根到当前邮件的节点 ID 组成，并按句点 (.) 。|
|||Export_native_path|导出文件的路径。|
|提取的内容类型||Native_type|以 mime 类型形式提取的内容类型;例如 **，image/jpeg**|
|||Extracted_text_path|导出中提取的文本文件的路径。|
|ExtractedTextLength*||Extracted_text_length|提取的文本中的字符数。|
|FamilyDuplicateSet*||Family_duplicate_set|彼此完全相同的系列的数字标识符 (内容以及所有相同的) 。|
|家庭 ID|FamilyId|Family_ID|将附件和从电子邮件中提取的项目及其父项进行分组和聊天。 这包括聊天或电子邮件以及所有附件和提取的项目。|
|系列大小||Family_size|家庭中的文档数。|
|文件类|FileClass|File_class|For content from SharePoint and OneDrive： **Document**. <br>For content from Exchange： **Email** or **Attachment**. <br>For content from Teams or Yammer： **Conversations**.|
|文件 ID|FileId|File_ID|文档标识符在大小写中是唯一的。|
|创建文件系统日期||File_system_date_created|文件系统数据的创建 (仅适用于非Office 365数据) 。|
|修改文件系统日期||File_system_date_modified|文件系统文件的修改 (仅适用于非Office 365数据) 。|
|文件类型|FileType||基于文件扩展名的项目的文件类型。|
|组 ID|GroupId|Group_ID|将电子邮件和文档的所有项目分组在一起。 对于电子邮件，这包括邮件以及所有附件和提取的项目。 对于文档，这包括文档和任何嵌入项目。|
|具有附件|EmailHasAttachment|Email_has_attachment|指示邮件是否包含附件。|
|有律师|HasAttorney||**如此** 当在律师列表中找到至少一个参与者;否则，值为 **False**。|
|HasText*||Has_text|指示项目是否具有文本;可能的值是 **True** 和 **False**。|
|不可变 ID||Immutable_ID|此 ID 用于唯一标识审阅集内的文档。 此字段不能用于审阅集搜索，并且 Id 不能用于访问位于其本机位置的文档。|
|非独占类型|InclusiveType|Inclusive_type|计算用于分析的非独占类型 **：0** - 非非独占类型; **1** - 非独占; **2** - 非独占减号; **3** - 包含副本。|
|In Reply To Id||In_reply_to_ID|回复邮件中的 ID。|
|InputFileExtension||Original_file_extension|文件的原始文件扩展名。|
|InputFileID||Input_file_ID|审阅集内顶级项目的文件 ID。 对于附件，此 ID 将是父级的 ID。 这可用于将系列分组在一起。|
|新式附件|IsModernAttachment||此文件是新式附件或链接文件。|
|来自文档版本|IsFromDocumentVersion||当前文档来自另一个文档的不同版本。|
|是电子邮件附件|IsEmailAttachment||此项目来自电子邮件附件，该附件显示为邮件的附加项目。|
|内联附件|IsInlineAttachment||这是内联附加的，显示在邮件正文中。|
|代表|IsRepresentative|Is_representative|每组精确重复项中的一个文档标记为具有代表性。|
|Item 类|ItemClass|Item_class|Exchange 服务器提供的项目类;例如 **，IPM。注意**|
|上次修改日期|LastModifiedDate|Doc_date_modified|文档元数据中的上次修改日期。|
|加载 ID|LoadId|Load_ID|将项目添加到审阅集的负载集的 ID。|
|位置|位置|位置|指示文档来源位置类型的字符串。<p>**导入的数据**- 非Office 365数据<br>**Teams** - Microsoft Teams<br>**Exchange** - Exchange邮箱<br>**SharePoint** - SharePoint网站<br>**OneDrive** - OneDrive帐户|
|位置名称|LocationName|Location_name|标识项目源的字符串。 对于 Exchange，这将是邮箱的 SMTP 地址;表示SharePoint和OneDrive，即网站集的 URL。|
|||Marked_as_pivot|此文件是一组几乎重复的数据透视表。|
|标记为具有代表性|MarkAsRepresentative||将每组精确重复项中的一个文档标记为代表。|
|会议结束日期|MeetingEndDate|Meeting_end_date|会议的会议结束日期。|
|会议开始日期|MeetingStartDate|Meeting_start_date|会议的会议开始日期。|
|邮件类型|MessageKind|Message_kind|要搜索的邮件类型。 可能的值 **<p> <br> ：contacts docs <br> email <br> externaldata <br> faxs im meetings <br> <br> <br> <br> microsoftteams** (returns items from chats， meetings， and calls in Microsoft Teams) **<br> notes <br> posts <br> rssfeeds <br> tasks <br> voicemail**|
|新式附件父 ID||ModernAttachment_ParentId|文档的父级的不可变 ID。|
|本机扩展|NativeExtension|Native_extension|项的本机扩展。|
|本机文件名|NativeFileName|Native_file_name|项的本机文件名。|
|NativeMD5||Native_MD5|MD5 哈希 (文件流) 128 位哈希值。|
|NativeSHA256||Native_SHA_256|SHA256 哈希 (文件流中的 256) 哈希值。|
|ND/ET 排序：排除附件|NdEtSortExclAttach|ND_ET_sort_excl_attach|连接电子邮件线程连接 ET () 设置和近 (ND) 集。 此字段用于在审阅时进行有效的排序。 D 的前缀为 ND 集 **，E** 为 ET 集前缀。|
|ND/ET 排序：包括附件|NdEtSortInclAttach|ND_ET_sort_incl_attach|连接电子邮件线程 (ET) 设置和近 (ND) 集。 此字段用于在审阅时进行有效的排序。 D 的前缀为 ND 集 **，E** 为 ET 集前缀。 ET 集合中的每个电子邮件项目后跟相应的附件。|
|近重复集||ND_set|与透视文档类似的项目共享相同的ND_set。|
|O365 作者||O365_authors|创作自SharePoint。|
|O365 创建者||O365_created_by|由 SharePoint。|
|O365 创建日期||O365_date_created|创建日期SharePoint。|
|O365 修改日期||O365_date_modified|上次修改日期（SharePoint）。|
|修改者 O365||O365_modified_by|修改者SharePoint。|
|其他保管人|DedupedCustodians|Deduped_custodians|与电子邮件完全相同的文档保管人 (，基于内容;基于哈希值对文档) 。|
|其他文件 ID|DedupedFileIds|Deduped_file_IDs|与电子邮件完全相同的文档的文件 (列表（基于内容）;基于哈希值对文档) 。|
|其他路径|Dedupedcompoundpath|Deduped_compound_path|与电子邮件完全相同的文档的复合路径列表 (：基于内容、文档：基于哈希) 。|
|父 ID|ParentId|Parent_ID|项的父级的 ID。|
|ParentNode||Parent_node|电子邮件线程中最接近的前一封电子邮件。|
|参与者域|ParticipantDomains|Email_participant_domains|邮件参与者的所有域的列表。|
|参与者|参与者|Email_participants|邮件的所有参与者列表;例如，发件人、收件人、抄送、密件抄送。|
|透视表 ID|PivotId|Pivot_ID|透视表的 ID。|
|潜在的特权|PotentiallyPrivileged|Potentially_privileged|如此 如果律师-客户特权检测模型认为文档可能特权|
|处理状态|ProcessingStatus|Error_code|将项目添加到审阅集后的处理状态。|
|读取百分点值|ReadPercentile||基于相关性读取文档的百分点值。|
|接收时间|接收时间|Email_date_received|以 UTC 格式接收电子邮件的日期和时间。|
|收件人计数||Recipient_count|邮件中的收件人数。|
|收件人域|RecipientDomains|Email_recipient_domains|邮件收件人的所有域的列表。|
|收件人|收件人|Email_recipients|邮件的所有收件人列表 (收件人、抄送、密件抄送) 。|
|||Redacted_file_path|导出中修订替换文件的路径。|
|||Redacted_text_path|导出中修订的文本文件替换的路径。 对于内部 Microsoft，请使用 。|
|相关性标记案例问题 1||Relevance_tag_case_issue_1|相关性标记案例问题 1 来自相关性。|
|相关性分数|RelevanceScore||基于相关性的文档的相关性分数。|
|相关性标记|RelevanceTag||基于相关性的文档的相关性分数。|
|代表 ID|RepresentativeId||每组精确重复项的数字标识符。|
|||Row_number|加载文件中项的行号。|
|发件人|发件人|Email_sender|邮件 (发件人) "字段。 格式为 **DisplayName \<SmtpAddress>**。|
|发件人/作者|SenderAuthor||计算字段，由项目的发件人或作者组成。|
|发件人域|SenderDomain|Email_sender_domain|发件人的域。|
|发件箱|发件箱|Email_date_sent|邮件的发送日期。<br>聊天：脚本的开始日期|
|设置顺序：先包含|SetOrderInclusivesFirst|Set_order_inclusives_first|排序字段 - 电子邮件和附件：按时间顺序排序;documents： pivot first then by descending similarity score.|
|设置 ID||Set_ID|同一电子邮件线程 (ND_set) 相似内容的文档或电子邮件 (Email_set) 共享相同的Set_ID。|
|SimilarityPercent||Similarity_percent|指示文档与近重复集的透视表的相似性。|
|本机文件大小|Size|Native_size|本机项的字节数。|
|主题|主题|Email_subject|邮件的主题。|
|主题/标题|SubjectTitle||计算字段，由项目的主题或标题组成。|
|标记|标记|标记|在审阅集内应用的标记。|
|Teams频道名称|TeamsChannel|Channel_Name|频道中频道Microsoft Teams。|
|主题列表|ThemesList|Themes_list|为分析计算的主题列表。|
|标题|标题|Doc_title|文档元数据中的标题。 文档元数据中的标题。 对于Teams和Yammer，这是 ConversationName 属性的值。|
|到|到|Email_to|邮件类型的收件人字段。 Format 为 **DisplayName \<SmtpAddress>**|
|在电子邮件集内是唯一的|UniqueInEmailSet||**假** 如果电子邮件集的附件副本。|
|版本组 ID||Version_Group_Id|将同一文档的不同版本分组在一起。|
|已修正|WasRemediated|Was_Remediated|**如此** 如果该项已修正，否则 **为 假**。|
|Word count|WordCount|Word_count|项中的字数。|
|||||

> [!NOTE]
> 有关在收集 Advanced eDiscovery 案例的数据时Office 365搜索内容位置时可搜索属性Advanced eDiscovery请参阅关键字查询和内容搜索[的搜索条件](keyword-queries-and-search-conditions.md)。
