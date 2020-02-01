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
description: 本文在 Microsoft 365 中的高级电子数据展示案例中的审阅集中定义文档的元数据字段。
ms.openlocfilehash: 399e89a577db68e0c31eceef921ef2ab1172352a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595187"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>高级电子数据展示中的文档元数据字段

下表列出了高级电子数据展示中的审阅集内的文档的元数据字段。 该表提供以下信息：

- **字段名称**和**显示字段名称：** 元数据字段的名称，以及在审阅集中查看所选文档的文件元数据时显示的字段的名称。 请注意，在查看文档的文件元数据时，不会包含一些元数据字段。 这些字段突出显示时带有星号（*）。

- 可**搜索字段名称：** 运行[审阅集查询](review-set-search.md)时可搜索的属性的名称。 空白单元格表示无法在审阅集查询中搜索该字段。

-  **导出的域名称：** 导出文档时包含的元数据字段的名称。  空白单元格表示该字段不包含在导出的元数据中。

- **说明：** 元数据字段的说明。

|**字段名称**和**显示字段名称**|**可搜索字段名称**|**导出的域名称**|**说明**|
|:-----|:-----|:-----|:-----|
|附件内容 Id|AttachmentContentId||项目的附件内容 Id。|
|附件名称|AttachmentNames|Attachment_Names|附件的名称列表。|
|律师客户端权限分数|AttorneyClientPrivilegeScore||律师-客户端权限模型内容分数。|
|作者|作者|Doc_authors|来自文档元数据的作者。|
|BCC|Bcc|Email_bcc|邮件类型的 "密件抄送" 字段。 格式为**DisplayName \<SMTPAddress>**。|
|CC|Cc|Email_cc|邮件类型的 "抄送" 字段。 格式为**DisplayName \<SMTPAddress>**。|
|合规性标签|ComplianceLabels|Compliance_labels|将[保留标签](labels.md)应用于 Office 365 中的内容。|
|复合路径|CompoundPath|Compound_path|描述项目来源的可读路径。|
|内容|内容||提取的项的文本。|
|对话正文|对话正文||项目的对话正文。|
|对话主题|对话主题||项目的对话主题。|
|会话 ID|ConversationId|Conversation_ID|邮件中的会话 Id。|
|会话索引||Conversation_index|邮件中的会话索引。|
|对话 Pdf 时间|ConversationPdfTime||创建的 PDF 版本的会话的日期。|
|对话密文刻录时间|ConversationRedactionBurnTime||为聊天创建会话的 PDF 版本的日期。|
|文档创建日期|CreatedTime|Doc_date_created|从文档元数据创建日期。|
|Custodian|Custodian|Custodian|与项目关联的保管人的名称。|
|日期|日期|日期|Date 是一个根据文件类型的计算字段。<br /><br />电子邮件：发送日期<br />电子邮件附件：文档的上次修改日期; 如果不可用，则为父级的发送日期<br />嵌入文档：文档的上次修改日期;如果不可用，则为父级的上次修改日期<br />SPO 文档（包括新式附件）： SharePoint 上次修改日期;如果不可用，则文档的上次修改日期<br />非 Office 365 文档：上次修改日期<br />会议：会议开始日期<br />语音邮件：发送日期<br />IM：发送日期|
|其他路径|Dedupedcompoundpath|Deduped_compound_path|完全重复的文档的复合路径列表（电子邮件：基于内容、文档：基于哈希）。|
|其他保管人|DedupedCustodians|Deduped_custodians|完全重复的文档的保管人列表（基于内容的电子邮件，基于内容的电子邮件; 基于哈希的文档）。|
|其他文件 Id|DedupedFileIds|Deduped_file_IDs|完全重复的文档的文件 Id 列表（基于内容的电子邮件，基于内容的电子邮件; 基于哈希的文档）。|
|文档注释|DocComments|Doc_comments|文档元数据中的注释。|
|文档公司||Doc_company|文档元数据中的公司。|
|DocIndex*|||系列中的索引。 **-1**或**0**表示它是根。|
|文档关键字||Doc_keywords|文档元数据中的关键字。|
|修改的文档||Doc_modified_by|从文档元数据中的上次修改日期。|
|文档修订||Doc_revision|文档元数据中的修订。|
|文档主题||Doc_subject|来自文档元数据的主题。|
|文档模板||Doc_template|文档元数据中的模板。|
|主要主题|DominantTheme|Dominant_theme|为分析而计算的主要主题。|
|重复子集||Duplicate_subset|完全副本的组 ID。|
|EmailAction*||Email_action|值为 "**无**"、"**答复**" 或 "**转发**";根据邮件的主题行。|
|电子邮件送达回执||Email_delivery_receipt|送达回执的 Internet 邮件头中提供的电子邮件地址。|
|Importance|EmailImportance|Email_importance|邮件的重要性： **0** -低;**1** -普通;**2** -高|
|EmailLevel*||Email_level|指示邮件在其所属的电子邮件线程中的级别;附件继承其父邮件的值。|
|电子邮件 Id||Email_message_ID|邮件中的 Internet 邮件 Id。|
|EmailReadReceipt*||Email_read_receipt|Internet 标头中提供的用于已读回执的电子邮件地址。|
|电子邮件安全性|EmailSecurity|Email_security|邮件的安全设置： **0** -无;**1** -签名;**2** -已加密;**3** -加密和签名。|
|电子邮件敏感度|EmailSensitivity|email_sensitivity|邮件的敏感度设置： **0** -无;**1**个人;**2** -专用;**3** -CompanyConfidential。|
|电子邮件集|EmailSet|Email_set|同一电子邮件集中所有邮件的组 ID。|
|EmailThread*||Email_thread|邮件在电子邮件集中的位置;由从根到当前邮件的节点 Id 组成;，以句点分隔。|
|提取的内容类型||Extracted_content_type|提取的内容类型，格式为 mime 类型;例如， **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|提取的文本中的字符数。|
|系列相关性分数事例问题 1 *||Family_relevance_score_case_issue_1|系列相关性分数事例问题1的相关性。|
|FamilyDuplicateSet*||Family_duplicate_set|与每个其他项完全相同的系列的数字标识符（相同内容和所有附件）。|
|系列 ID|FamilyId|Family_ID|系列 Id 将所有项目组合在一起;对于电子邮件，这包括邮件和所有附件;对于文档，这包括文档和任何嵌入项。|
|系列大小||Family_size|系列中的文档数。|
|文件相关性分数事例问题 1 *||File_relevance_score_case_issue_1|来自相关性的文件相关性分数事例问题1。|
|File 类|FileClass|File_class|对于 SharePoint 和 OneDrive 中的内容：**文档**;对于 "Exchange：**电子邮件**" 或 "**附件**" 中的内容。|
|文件 ID|FileId|File_ID|大小写中唯一的文档标识符。|
|文件系统创建日期||File_system_date_created|从文件系统创建的日期（仅适用于非 Office 365 数据）。|
|修改了文件系统日期||File_system_date_modified|从文件系统修改的日期（仅适用于非 Office 365 数据）。|
|文件类型|FileType||项目的文件类型（基于文件扩展名）。|
|有附件|HasAttachment|Email_has_attachment|指示邮件是否包含附件。|
|拥有律师|HasAttorney||如果在律师列表中至少找到一个参与者，则**为 True** ; 否则为 false。否则，该值为**False**。|
|HasText||Has_text|指示项目是否有文本;可能的值为**True**和**False**。|
|不可变 ID|ImmutableId|Immutable_ID|存储在 Office 365 中的不可变 Id。|
|包含类型|InclusiveType|Inclusive_type|为分析计算的非独占类型： **0** -不包含;**1** -包含;**2**个包含项减号;**3**个包含副本。|
|答复 Id 中||In_reply_to_ID|邮件中的 "回复 Id"。|
|代表|IsRepresentative|Is_representative|每组精确副本中的一个文档被标记为代表。|
|Item 类|ItemClass|Item_class|由 exchange server 提供的 Item 类;例如， **IPM。注释**|
|上次修改日期|LastModifiedDate|Doc_date_modified|文档元数据中的上次修改日期。|
|加载 ID|LoadId|Load_ID|将项目添加到评审集的负载集的 Id。|
|位置|位置|位置|表示文档来源的位置的类型的字符串。<br /><br />**导入的数据**-非 Office 365 数据<br />**团队**-Microsoft 团队<br />**Exchange** -exchange 邮箱<br />**Sharepoint** -sharepoint 网站<br />**Onedrive** -onedrive 帐户|
|位置名称|LocationName|Location_name|标识项的源的字符串。 对于 exchange，这将是邮箱的 SMTP 地址;对于 SharePoint 和 OneDrive，是网站集的 URL。|
|标记为代表|MarkAsRepresentative||每组精确的重复项中的一个文档被标记为代表。|
|标记为前置标记事例问题 1 *||Marked_as_pre_tagged_Case_issue_1|标记为 "预先标记的案例问题 1" 与 "相关性"。|
|标记为 "种子情况问题 1 *"||Marked_as_seed_Case_issue_1|从相关性中标记为 "种子事例问题 1"。|
|会议结束日期|MeetingEndDate|Meeting_end_date|会议的会议结束日期。|
|会议开始日期|MeetingStartDate|Meeting_start_date|会议的会议开始日期。|
|邮件类型|MessageKind|Message_kind|要搜索的邮件的类型。 可能的值** <br /> <br />： <br />联系人<br />文档<br />电子<br />邮件<br />externaldata <br />传真<br />im <br />日记会议 microsoftteams** （返回 Microsoft 团队中的聊天、会议和呼叫中的项目） ** <br />备注<br />帖子<br />rssfeeds <br />任务<br />语音邮件**| 
|本机扩展|NativeExtension|Native_extension|项目的本机扩展。|
|本机文件名|NativeFileName|Native_file_name|项目的本机文件名。|
|NativeMD5||Native_MD5|文件流的 MD5 哈希值。|
|ND/ET 排序：排除附件|NdEtSortExclAttach|ND_ET_sort_excl_attach|将电子邮件集和 ND 的串联设置为在审阅时有效排序;将**D**添加为 ND 集的前缀，并将**E**添加到电子邮件集。|
|ND/ET 排序：包括附件|NdEtSortInclAttach|ND_ET_sort_incl_attach|将电子邮件集和 ND 的串联设置为在审阅时有效排序;将**D**添加为 ND 集的前缀，并将**E**添加到电子邮件集。 电子邮件集内的每封电子邮件后面都有相应的附件。|
|标准化相关性分数事例问题1||Normalized_relevance_score_case_issue_1|来自相关性的标准化相关性分数事例问题1。|
|O365 作者||O365_authors|来自 SharePoint 的作者。|
|O365 创建者||O365_created_by|由 SharePoint 创建。|
|O365 创建日期||O365_date_created|从 SharePoint 创建日期。|
|O365 修改日期||O365_date_modified|SharePoint 中的上次修改日期。|
|O365 修改者||O365_modified_by|由 SharePoint 修改。|
|父 ID|ParentId|Parent_ID|项目的父级的 Id。|
|ParentNode||Parent_node|电子邮件线索中最近的最前面的电子邮件。|
|父路径|ParentPath|Parent_path|项目的直接父级的复合路径。|
|参与者域|ParticipantDomains|Email_participant_domains|邮件参与者的所有域的列表。|
|Participants|Participants|Email_participants|邮件的所有参与者的列表;例如，"发件人"、"抄送"、"密件抄送"。|
|透视 ID|PivotId|Pivot_ID|Pivot 的 ID。|
|可能的特权|PotentiallyPrivileged|Potentially_privileged|如此如果律师-客户端特权检测模型认为该文档有可能具有特权|
|处理状态|ProcessingStatus|Error_code|将项目添加到审阅集后的处理状态。|
|已读百分比案例问题1||Read_percent_Case_issue_1|从相关性中读出问题1的百分比事例。|
|读取百分点|ReadPercentile||根据相关性读取文档的百分点值。|
|收件人计数||Recipient_count|邮件中的收件人数。|
|收件人域|RecipientDomains|Email_recipient_domains|邮件的收件人的所有域的列表。|
|收件人|收件人|Email_recipients|邮件的所有收件人的列表（"收件人"、"抄送"、"密件抄送"）。|
|相关性加载组案例问题1||Relevance_load_group_case_issue_1|相关性加载组案例问题1的相关性。|
|相关性状态描述案例问题1||Relevance_status_description_Case_issue_1|相关性状态描述问题1的相关性。|
|相关性标记事例问题1||Relevance_tag_case_issue_1|相关性标记问题1与相关性相关。|
|相关性注释||Relevance_comment|来自相关性的注释字段。|
|相关性分数|RelevanceScore||基于相关性的文档的相关性分数。|
|相关性标记|RelevanceTag||基于相关性的文档的相关性分数。|
|代表 ID|RepresentativeId||每个精确副本集的数字标识符。|
|发件人|发件人|Email_sender|邮件类型的发件人（发件人）域。 格式为**DisplayName \<SmtpAddress>**。|
|发件人/作者|SenderAuthor||由项目的发件人或作者组成的计算字段。|
|发件人域|SenderDomain|Email_sender_domain|发件人的域。|
|发件箱|发件箱|Email_date_sent|邮件的发送日期。|
|设置顺序：首次包含|SetOrderInclusivesFirst|Set_order_inclusives_first|排序字段-电子邮件和附件：按时间顺序排列;文档：先透视，再按降序对相似性得分。|
|SimilarityPercent||Similarity_percent|指示文档与邻近的重复集的透视方式的相似之处。|
|本机文件大小|大小|Native_size|本机项的字节数。|
|Subject|Subject|Email_subject|邮件的主题。|
|主题/职务|SubjectTitle||由项目的主题或标题组成的计算字段。|
|标记的案例问题1||Tagged_by_Case_issue_1|将此文档标记为相关问题1的用户。|
|标签|标签|标签|在审阅集中应用的标记。|
|主题列表|ThemesList|Themes_list|为分析而计算的主题列表。|
|标题|标题|Doc_title|文档元数据中的标题。|
|To|To|Email_to|邮件类型的 "To" 字段。 Format 为**DisplayName\<SmtpAddress>**|
|电子邮件集中的唯一|UniqueInEmailSet||**假**如果电子邮件集中存在附件的副本。|
|已修正|WasRemediated|Was_Remediated|如果项目已修正，**则为 True** ，否则为**False**。|
|Word count|WordCount|Word_count|项目中的单词数。|
|||||

> [!NOTE]
> 有关在为高级电子数据展示事例收集数据时搜索 Office 365 内容位置时可搜索属性的详细信息，请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。