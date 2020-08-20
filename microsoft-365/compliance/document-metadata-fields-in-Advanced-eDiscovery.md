---
title: 高级电子数据展示中的文档元数据字段
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文定义了 Microsoft 365 高级电子数据展示案例中审阅集内文档的元数据字段。
ms.openlocfilehash: 69b22155f209f155aa0b311f67f3e69841093003
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814384"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>高级电子数据展示中的文档元数据字段

下表列出了高级电子数据展示中审阅案例中的文档的元数据字段。 此表提供了以下信息：

- **字段名称****和显示字段名称**：元数据字段的名称和在审阅集中查看所选文档的文件元数据时显示的字段名称。 查看文档的文件元数据时，不包括某些元数据字段。 这些字段以星号 (*) 。

- **可搜索的字段名称：** 在运行审阅集查询时可以搜索 [的属性的名称](review-set-search.md)。 空白单元格表示无法在审阅集查询中搜索该字段。

- **导出的字段名称：** 元数据字段的名称，在导出文档时包含该字段。  空白单元格表示导出的元数据中不包含字段。

- **描述：** 元数据字段的说明。

> [!NOTE]
> 审 **阅集** 搜索中的 ["关键字"字段](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) 使用针对 KQL (关键字查询) 。 "可搜索字段 **名称"列中列出的** 字段可以在审 **阅集搜索中的"关键字** "字段中使用，以形出复杂的查询，而无需使用查询生成器。 有关 KQL 的详细信息，请参阅关键字查询 [语言语法参考](https://go.microsoft.com/fwlink/?LinkId=269603)。

|**字段名称和****显示字段名称**|**可搜索的字段名称**|**导出的字段名称**|**说明**|
|:-----|:-----|:-----|:-----|
|附件内容 ID|AttachmentContentId||项目的附件内容 ID。|
|附件名称|AttachmentNames|Attachment_Names|附件名称列表。|
|证销客户端特权得分|AttorneyClientPrivilegeScore||大部分玩家特权模型内容分数。|
|作者|作者|Doc_authors|文档元数据中的作者。|
|BCC|Bcc|Email_bcc|邮件类型的"Bcc"字段。 格式为**DisplayName \<SMTPAddress> **。|
|CC|Cc|Email_cc|邮件类型的"Cc"字段。 格式为**DisplayName \<SMTPAddress> **。|
|合规性标签|ComplianceLabels|Compliance_labels|[应用于](retention.md) Office 365 中的内容的保留标签。|
|复合路径|CompoundPath|Compound_path|描述项目来源的人力读取路径。|
|内容*|内容||提取项的文本。|
|对话正文|对话正文||项目的会话正文。|
|对话主题|对话主题||项目的对话主题。|
|对话 ID|ConversationId|Conversation_ID|邮件中的对话 ID。|
|对话索引||Conversation_index|邮件中的对话索引。|
|对话 Pdf 时间|ConversationPdfTime||对话的 PDF 版本的创建日期。|
|对话兑动采字时间|ConversationRedactionBurnTime||为聊天创建 PDF 版本的对话的日期。|
|创建文档日期|CreatedTime|Doc_date_created|通过文档元数据创建日期。|
|Custodian|Custodian|Custodian|与项目关联的保CNTODIan 的名称。|
|日期|日期|日期|日期是一个依赖于文件类型的计算字段。<br /><br />电子邮件：发送日期<br />电子邮件附件：文档的上次修改日期;如果不可用，则为父级的"发送日期"。<br />嵌入的文档：文档上次修改日期;如果不可用，则为父元素的最后修改日期<br />SPO 文档 (包括新式附件) ：SharePoint 上次修改日期;如果不可用，则文档最后修改日期<br />非 Office 365 文档：上次修改日期<br />会议：会议开始日期<br />语音邮件：发送日期<br />IM：发送日期|
|其他路径|Dedupedcompoundpath|Deduped_compound_path|文档组合路径列表，这些路径与电子邮件 (完全重复，根据内容为：基于内容，文档：基于哈希) 。|
|其他保加大学|DedupedCustodians|Deduped_custodians|基于内容，完全与电子邮件保留 (性的文档列表;的文档，根据哈希) 。|
|其他文件 ID|DedupedFileIds|Deduped_file_IDs|根据内容，具有与电子邮件完全不同 (文件 ID 列表;的文档，根据哈希) 。|
|文档注释|DocComments|Doc_comments|来自文档元数据的评论。|
|文档公司||Doc_company|文档元数据中的公司。|
|DocIndex*|||系列中的索引。 **-1** **或 0** 表示其是根。|
|文档关键字||Doc_keywords|文档元数据中的关键字。|
|修改者的文档||Doc_modified_by|上次从文档元数据修改日期。|
|文档修订||Doc_revision|从文档元数据修订。|
|文档主题||Doc_subject|文档元数据中的主题。|
|文档模板||Doc_template|文档元数据中的模板。|
|基准主题|DominantTheme|Dominant_theme|基准主题计算以供分析。|
|复制子集||Duplicate_subset|完全重复项的组 ID。|
|EmailAction*||Email_action|值为 **None 、** **Reply**或 **Forward**;基于邮件的主题行。|
|电子邮件送达回执||Email_delivery_receipt|在 Internet 头中为送达回执提供的电子邮件地址。|
|Importance|EmailImportance|Email_importance|邮件重要性 **：0** - 低; **1** - 正常; **2** - 高|
|EmailLevel*||Email_level|指示邮件在其所属的电子邮件线程内的级别;附件继承父邮件值。|
|电子邮件 ID||Email_message_ID|邮件中的 Internet 邮件 ID。|
|EmailReadReceipt*||Email_read_receipt|已读回执在 Internet 头中提供的电子邮件地址。|
|电子邮件安全性|EmailSecurity|Email_security|消息的安全设置 **：0** - 无; **1** - 已签名; **2** - 加密; **3** - 已加密并进行签名。|
|电子邮件敏感度|EmailSensitivity|email_sensitivity|消息的敏感度设置 **：0** - 无; **1** 个人; **2** - 专用; **3** - CompanyConfidential。|
|电子邮件集|EmailSet|Email_set|同一电子邮件集中的所有邮件的组 ID。|
|EmailThread*||Email_thread|邮件在电子邮件集中的位置;由从根到当前邮件的根节点 ID，并由句点 (.) 分隔。|
|提取的内容类型||Extracted_content_type|提取的内容类型，其形式为 mime 类型;例如 **，image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|提取的文本中的字符数。|
|家庭相关性分数问题 1*||Family_relevance_score_case_issue_1|系列相关性分数问题 1 从相关性向 1。|
|FamilyDuplicateSet*||Family_duplicate_set|与内容完全相同且与相同 (的系列的数字标识符) 。|
|系列 ID|FamilyId|Family_ID|家庭 ID 将所有项目组合在一起;对于电子邮件，这包括邮件和所有附件;对于文档，这包括文档和所有嵌入的项目。|
|家庭规模||Family_size|系列中的文档数量。|
|文件相关性分数问题 1*||File_relevance_score_case_issue_1|文件相关性分数大小写问题 1。|
|File 类|FileClass|File_class|对于来自 SharePoint 和 OneDrive 的内容： **文档**;对于 Exchange 的内容： **电子邮件** 或 **附件**。|
|文件 ID|FileId|File_ID|在这种情况下，文档标识符具有唯一性。|
|创建文件系统日期||File_system_date_created|从文件系统创建 (日期仅适用于非 Office 365) 。|
|修改文件系统日期||File_system_date_modified|文件系统中的修改日期 (适用于非 Office 365 数据) 。|
|文件类型|FileType||基于文件扩展名的项的文件类型。|
|组 ID| GroupID|  |分组内容的组 ID。|
|有附件|HasAttachment|Email_has_attachment|指示邮件是否有附件。|
|具有 attorney|HasAttorney||**四**个参与者中至少一个参与者在外表时，则为 True;否则为False **。**|
|HasText*||Has_text|指示项目是否包含文本;可能的值为 **True** 和 **False**。|
|不可变 ID||Immutable_ID|此 ID 用于唯一标识审阅集中的文档。 此字段不能用于审阅集搜索中，且 ID 无法用于访问其本机位置的文档。|
|非独占类型|InclusiveType|Inclusive_type|计算得出的非独占类型 **：0** - 不包含 0; 非独占; **1** - 包括这两个值; **2** - 非独占减值; **3** - 以独占副本的格式复制。|
|In Reply To Id||In_reply_to_ID|在对邮件中的 ID 的答复。|
|是否为新式附件| IsModernAttachment|  |此文件是新式附件或链接的文件。|
|来自文档版本 | IsFromDocumentVersion |  |当前文档来自另一文档的不同版本。|
|电子邮件附件 | IsEmailAttachment|  |此项目来自于显示为邮件附件的电子邮件附件。|
|嵌入附件| IsInlineAttachment|  |它以内联方式附加，并显示在邮件正文中。|
|代表|IsRepresentative|Is_representative|每组完全重复项中的一个文档标记为代表。|
|Item 类|ItemClass|Item_class|由 Exchange 服务器提供的项目类;例如 **，IPM。注意**|
|上次修改日期|LastModifiedDate|Doc_date_modified|上次从文档元数据修改日期。|
|加载 ID|LoadId|Load_ID|将项目添加到审阅集的加载集的 ID。|
|位置|位置|位置|指示文档来源位置的字符串。<br /><br />**导入的数据** - 非 Office 365 数据<br />**Teams** - Microsoft Teams<br />**Exchange** - Exchange 邮箱<br />**SharePoint** - SharePoint 网站<br />**OneDrive** - OneDrive 帐户|
|位置名称|LocationName|Location_name|用于标识项目来源的字符串。 对于 Exchange，这将是邮箱的 SMTP 地址;对于 SharePoint 和 OneDrive，网站集的 URL。|
|标记为代表|MarkAsRepresentative||每组完全重复项中的一个文档标记为代表。|
|标记为预标记的事例问题 1*||Marked_as_pre_tagged_Case_issue_1|相关性中标记为预标记的事例问题 1。|
|标记为种子问题 1*||Marked_as_seed_Case_issue_1|相关性中标记为案例问题 1。|
|会议结束日期|MeetingEndDate|Meeting_end_date|会议的会议结束日期。|
|会议开始日期|MeetingStartDate|Meeting_start_date|会议的会议开始日期。|
|邮件类型|MessageKind|Message_kind|要搜索的邮件类型。 可能的值** <br /> <br /> ：联系人 <br /> 文档 <br /> <br /> 电子邮件外部数据 <br /> 传真 <br /> im <br /> 即将会议 <br /> <br /> MicrosoftTeams** (报告中聊天、会议和通话的项目从 Microsoft Teams)  (** <br /> 备注 <br /> <br /> 发表 <br /> 任务 <br /> 语音邮件中的项目**| 
|本机扩展|NativeExtension|Native_extension|项目的本机扩展。|
|本机文件名|NativeFileName|Native_file_name|项目的本机文件名。|
|NativeMD5||Native_MD5|MD5 哈希 (此文件流的 128) 希值。|
|NativeSHA256||Native_SHA_256|SHA256 哈希 (个值的256) 数据流。|
|ND/ET 排序：不包括附件|NdEtSortExclAttach|ND_ET_sort_excl_attach|将电子邮件线程与电子邮件 (和"数据不) ND"组 () 连接。 此字段用于在审阅时进行有效的排序。 **D 作为**前缀添加到 ND 集 **，E**作为前缀添加到 ET 集。|
|ND/ET 排序：包括附件|NdEtSortInclAttach|ND_ET_sort_incl_attach|将电子邮件线程与 ET 连接 (设置) 不断重复的设置 (ND) 集。 此字段用于在审阅时进行有效的排序。 **D 作为**前缀添加到 ND 集 **，E**作为前缀添加到 ET 集。 ET 集中的每个电子邮件项目后跟各自的附件。|
|规范化的相关性分数问题 1||Normalized_relevance_score_case_issue_1|相关性的标准化相关性分数问题 1。|
|O365 作者||O365_authors|从 SharePoint 中作者。|
|创建者的 O365||O365_created_by|由 SharePoint 创建。|
|创建日期||O365_date_created|从 SharePoint 创建日期。|
|修改日期 O365||O365_date_modified|上次修改日期（自 SharePoint）。|
|修改者的 O365||O365_modified_by|由 SharePoint 修改。|
|父 ID|ParentId|Parent_ID|项父项的 ID。|
|ParentNode||Parent_node|电子邮件线程中最接近的电子邮件。|
|父路径|ParentPath|Parent_path|项目直接父级的复合路径。|
|参与者域|ParticipantDomains|Email_participant_domains|邮件参与者的所有域列表。|
|Participants|Participants|Email_participants|邮件的所有参与者列表;例如，发件人、收件人、"收件人"、"收件人"、"收件人"等。|
|透视表 ID|PivotId|Pivot_ID|透视表 ID。|
|具有潜在特权|PotentiallyPrivileged|Potentially_privileged|如果 attorney-client privilege detection model considers the document potentially privileged|
|处理状态|ProcessingStatus|Error_code|将项目添加到审阅集后的处理状态。|
|读取百分比案例问题 1||Read_percent_Case_issue_1|读取相关性的百分比案例问题 1。|
|读取百分点值|ReadPercentile||基于相关性读取文档的百分点值。|
|收件人数||Recipient_count|邮件中的收件人数。|
|收件人域|RecipientDomains|Email_recipient_domains|邮件收件人的所有域列表。|
|收件人|收件人|Email_recipients|邮件"收件人"、"抄送"、" (抄送"和"收件人") 。|
|相关性加载组案例问题 1||Relevance_load_group_case_issue_1|相关性加载组案例问题 1。|
|相关性状态描述案例问题 1||Relevance_status_description_Case_issue_1|相关性相关性的相关性状态描述案例问题 1。|
|相关性标记案例问题 1||Relevance_tag_case_issue_1|相关性的相关性标记案例问题 1。|
|相关性注释||Relevance_comment|相关性的注释字段。|
|相关性分数|RelevanceScore||文档的相关性分数。|
|相关性标记|RelevanceTag||文档的相关性分数。|
|代表性 ID|RepresentativeId||每组完全重复的数字标识符。|
|发件人|发件人|Email_sender|发件人 (邮件) 发件人"字段。 格式为**DisplayName \<SmtpAddress> **。|
|发件人/作者|SenderAuthor||计算字段由项目的发件人或作者所构成。|
|发件人域|SenderDomain|Email_sender_domain|发件人的域。|
|发件箱|发件箱|Email_date_sent|邮件的发送日期。|
|设置顺序：先包含|SetOrderInclusivesFirst|Set_order_inclusives_first|排序字段 - 电子邮件和附件：按时间顺序计算;文档：首先通过降序相似性分数进行透视。|
|SimilarityPercent||Similarity_percent|指示文档与相似的重复集的透视如何。|
|本机文件大小|Size|Native_size|本机项的字节数。|
|主题|主题|Email_subject|邮件主题。|
|主题/标题|SubjectTitle||计算字段中包含项目的主题或标题。|
|用事例问题 1 标记||Tagged_by_Case_issue_1|相关性的将此文档标记为案例问题 1 的用户。|
|标记|标记|标记|应用于审阅集的标记。|
|主题列表|ThemesList|Themes_list|对项目进行分析计算时的主题列表。|
|标题|标题|Doc_title|文档元数据中的标题。|
|To|To|Email_to|邮件类型的字段。 格式为**DisplayName \<SmtpAddress> **|
|在电子邮件集中是唯一的|UniqueInEmailSet||**假** 如果其电子邮件集中存在的附件副本。|
|已修正|WasRemediated|Was_Remediated|**如此** 如果该项已修正，否则为 **假**。|
|Word count|WordCount|Word_count|项目中的单词数。|
|||||

> [!NOTE]
> 若要详细了解在为高级电子数据展示事例收集数据时搜索 Office 365 内容位置时的可搜索属性，请参阅 [关键字查询和内容搜索搜索搜索的搜索条件](keyword-queries-and-search-conditions.md)。
