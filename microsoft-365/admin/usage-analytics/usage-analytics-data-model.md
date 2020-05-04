---
title: Microsoft 365 使用情况分析数据模型
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: '了解使用情况分析如何连接到 API，并提供各种 Microsoft 365 服务的每月使用趋势。  '
ms.openlocfilehash: 2c39edd66bda19233a67c4623044ffc9e0e8046d
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011767"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 使用情况分析数据模型

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Microsoft 365 使用率分析表的数据

Microsoft 365 使用情况分析连接到公开多维数据模型的 API。 这些 API 处于预览状态，并可在 `https://reports.office.com/pbi/v1.0/\<tenantid\>` 进行访问（将 \<tenant id\> 替换为租户 GUID）。 
  
> [!NOTE]
> 有关详细信息，请参阅[在 Microsoft Graph 中使用 microsoft 365 使用率报告](https://go.microsoft.com/fwlink/p/?linkid=864336)。 
  
此 API 提供了有关各种 Microsoft 365 服务的每月使用趋势的信息。 有关 API 返回的确切数据，请参考以下部分中的表。
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Microsoft 365 报告 API 返回的数据表

|**表名**|**表中信息**|**日期范围**|
|:-----|:-----|:-----|
|租户产品使用情况  <br/> |包含已启用的活动用户、逐月保留的用户、首次使用的用户和累积活动用户的每月总计。  <br/> |包含滚动的为期 12 个月（包含当月）的每月汇总数据。  <br/> |
|租户产品活动  <br/> |包含活动以及产品中各种活动的活动用户计数的每月总计。  <br/> 有关在此数据表中返回的产品中的活动的信息，请参阅[活动用户定义](active-user-in-usage-reports.md)。  <br/> |包含滚动的为期 12 个月（包含当月）的每月汇总数据。  <br/> |
|租户 Office 许可证  <br/> |包含分配给用户的 Microsoft Office 订阅数的数据  <br/> |包含滚动的为期 12 个月（包含当月）的月末状态数据。  <br/> |
|租户邮箱使用情况  <br/> |包含有关用户邮箱的数据，即邮箱数总计和存储使用情况。  <br/> |包含滚动的为期 12 个月（包含当月）的月末状态数据。  <br/> |
|租户客户端使用情况  <br/> |包含有关频繁使用特定客户端/设备连接到 Exchange Online、Skype for Business 和 Yammer 的用户数的数据。  <br/> |包含滚动的为期 12 个月（包含当月）的每月汇总数据。  <br/> |
|租户 SharePoint Online 使用情况  <br/> |包含有关 SharePoint 网站（包括团队网站或组网站）的数据，如网站总数、网站上的文档数、各活动类型的文件数和已用存储。  <br/> |包含滚动的为期 12 个月（包含当月）的月末状态数据。  <br/> |
|租户 OneDrive for Business 使用情况  <br/> |包含有关 OneDrive 帐户的数据，如帐户数、跨 OneDrive 的文档数、已用存储、各活动类型的文件数。  <br/> |包含滚动的为期 12 个月（包含当月）的月末状态数据。  <br/> |
|租户 Microsoft 365 组使用情况  <br/> |包含有关 Microsoft 365 组用途（包括邮箱、SharePoint 和 Yammer）的数据。  <br/> |包含滚动的为期 12 个月（包含当月）的月末状态数据。  <br/> |
|租户 Office 激活  <br/> |包含有关 Office 订阅激活次数、每个设备的激活计数（Android/iOS/Mac/电脑）、按服务计划激活的数据（例如，Microsoft 365 Apps for enterprise、Visio、Project）的数据。  <br/> |包含滚动的为期 12 个月（包含当月）的月末状态数据。  <br/> |
|用户状态  <br/> |包含有关用户的元数据，包括用户显示名称、分配的产品、位置、部门、职务、公司。此数据有关在刚刚结束的一个月内分配到许可证的用户。每个用户都以唯一的用户 ID 表示。  <br/> |此数据有关在刚刚结束的一个月内分配到许可证的用户。  <br/> |
|用户活动  <br/> |包含有关授权用户执行的活动的每用户级别的信息。  <br/> 有关在此数据表中返回的产品中的活动的信息，请参阅[活动用户定义](active-user-in-usage-reports.md)。  <br/> |此数据有关刚刚结束的一个月内在任何服务中执行活动的用户。  <br/> |
   
展开以下各部分，查看每个数据表的详细信息。
  
### <a name="data-table---user-state"></a>数据表 - 用户状态

下表提供了在刚刚结束的一个月内分配到许可证的所有用户的用户级别详细信息。其数据来自于 Azure Active Directory。
  
|**列名称**|**列说明**|
|:-----|:-----|
|UserID  <br/> |代表某一用户的唯一用户 ID，通过它可与数据集内的其他数据表联接。  <br/> |
|Timeframe  <br/> |月份值，此表包含该月份的数据。  <br/> |
|UPN  <br/> |用户主体名称，用于唯一标识用户，使其能够与其他外部数据源联接。  <br/> |
|DisplayName  <br/> |用户的显示名称。  <br/> |
|IDType  <br/> |如果用户是 Yammer 用户（通过使用其 Yammer ID 连接），则 Id 类型设置为 1; 如果用户使用 Microsoft 365 ID 连接到 Yammer，则设置为0。  <br/> 值为1表示此用户使用其 Yammer id 连接到 Yammer，而不是使用其 Microsoft 365 id 连接到 Yammer  <br/> |
|HasLicenseEXO  <br/> |如果用户分配有许可证，并且能够使用 Exchange，则设置为 true。  <br/> |
|HasLicenseODB  <br/> |如果用户分配有许可证，并且能够使用 OneDrive for Business，则设置为 true。  <br/> |
|HasLicenseSPO  <br/> |如果用户分配有许可证，并且能够使用 SharePoint Online，则设置为 true。  <br/> |
|HasLicenseYAM  <br/> |如果用户分配有许可证，并且能够使用 Yammer，则设置为 true。  <br/> |
|HasLicenseSFB  <br/> |如果用户分配有许可证，并且能够使用 Skype For Business，则设置为 true。  <br/> |
|HasLicenseTeams  <br/> |如果向用户分配许可证并启用以使用 Microsoft 团队，则设置为 true。  <br/> |
|Company  <br/> |此用户在 Azure Active Directory 中对应的公司数据。  <br/> |
|Department  <br/> |此用户在 Azure Active Directory 中对应的部门数据。  <br/> |
|LocationCity  <br/> |此用户在 Azure Active Directory 中对应的城市数据。  <br/> |
|LocationCountry  <br/> |此用户在 Azure Active Directory 中对应的国家/地区数据。  <br/> |
|LocationState  <br/> |此用户在 Azure Active Directory 中对应的省/市/自治区数据。  <br/> |
|LocationOffice  <br/> |用户的 Office。  <br/> |
|Title  <br/> |此用户在 Azure Active Directory 中对应的职务数据。  <br/> |
|Deleted  <br/> |如此如果用户已从最近完成的一个月的 Microsoft 365 中删除。  <br/> |
|DeletedDate  <br/> |从 Microsoft 365 中删除用户的日期。  <br/> |
|YAM_State  <br/> |Yammer 系统中的用户状态，可为活动、已删除或已挂起。  <br/> |
|YAM_ActivationDate  <br/> |用户在 Yammer 中进入活动状态的日期。  <br/> |
|YAM_DeletionDate  <br/> |用户在 Yammer 中进入已删除状态的日期。  <br/> |
|YAM_SuspensionDate  <br/> |用户在 Yammer 中进入已挂起状态的日期。  <br/> |
   
### <a name="data-table---user-activity"></a>数据表 - 用户活动

此表包含有关上个月在任何服务中有活动的每个用户的数据。
  
|**列名称**|**列说明**|
|:-----|:-----|
|UserID  <br/> |代表某一用户的唯一用户 ID，通过它可与数据集内的其他数据表联接。  <br/> |
|IDType  <br/> |如果用户是 Yammer 用户（通过使用其 Yammer ID 连接），则 Id 类型设置为 1; 如果用户使用 Microsoft 365 ID 连接到 Yammer，则设置为0。  <br/> 值为1表示此用户使用其 Yammer id 连接到 Yammer，而不是使用其 Microsoft 365 id 连接到 Yammer  <br/> |
|Timeframe  <br/> |月份值，此表代表该月份的数据。  <br/> |
|EXO_EmailSent  <br/> |发送的邮件数。  <br/> |
|EXO_EmailReceived  <br/> |接收的邮件数。  <br/> |
|EXO_EmailRead  <br/> |用户执行的电子邮件阅读活动数，阅读已读电子邮件或以前接收的电子邮件记为多次。  <br/> |
|EXO_AppointmentCreated  <br/> |已创建的约会数。  <br/> |
|EXO_MeetingAccepted  <br/> |接受的会议数。  <br/> |
|EXO_MeetingCancelled  <br/> |取消的会议数。  <br/> |
|EXO_MeetingDeclined  <br/> |拒绝的会议数。  <br/> |
|EXO_MeetingSent  <br/> |已发送的会议数。  <br/> |
|ODB_FileViewedModified  <br/> |此用户在任何 OneDrive for Business 上与其进行了交互（如创建、更新、删除、查看或下载）的文件数。  <br/> |
|ODB_FileSynched  <br/> |此用户在任何 OneDrive for Business 上同步的文件数。  <br/> |
|ODB_FileSharedInternally  <br/> |此用户从任何 OneDrive for Business 或组中的用户（可能包含外部用户）内部共享的文件数。  <br/> |
|ODB_FileSharedExternally  <br/> |此用户从任何 OneDrive for Business 进行外部共享的文件数。  <br/> |
|ODB_AccessByOwner  <br/> |用户与之交互且位于其自己的 OneDrive for Business 上的文件数。  <br/> |
|ODB_AccessOthers  <br/> |用户与之交互且位于其他用户的 OneDrive for Business 上的文件数。  <br/> |
|SPO_GroupFileViewedModified  <br/> |此用户在任何组网站上进行交互的文件数。  <br/> |
|SPO_GroupFileSynched  <br/> |此用户在任何组网站上进行同步的文件数。  <br/> |
|SPO_GroupFileSharedInternally  <br/> |与组织中的用户或组中的用户共享的文件的计数（可能包含外部用户）。  <br/> |
|SPO_GroupFileSharedExternally  <br/> |此用户从任何组网站进行外部共享的文件数。  <br/> |
|SPO_GroupAccessByOwner  <br/> |用户与之交互且位于该用户所拥有的组网站上的文件数。  <br/> |
|SPO_GroupAccessByOthers  <br/> |用户与之交互且位于其他用户所拥有的组网站上的文件数。  <br/> |
|SPO_OtherFileViewedModified  <br/> |此用户在任何其他网站上进行交互的文件数。  <br/> |
|SPO_OtherFileSynched  <br/> |此用户从任何其他网站同步的文件数。  <br/> |
|SPO_OtherFileSharedInternally  <br/> |此用户从任何其他网站或组中的用户（可能包含外部用户）内部共享的文件数。 <br/> |
|SPO_OtherFileSharedExternally  <br/> |此用户从其他任何网站进行外部共享的文件数。  <br/> |
|SPO_OtherAccessedByOwner  <br/> |用户与之交互且驻留在其拥有的其他网站上的网站数。  <br/> |
|SPO_OtherAccessedByOthers  <br/> |用户与之交互且位于其他用户所拥有的其他网站上的网站数。  <br/> |
|SPO_TeamFileViewedModified  <br/> |与此用户在任何团队网站上进行交互的文件数。  <br/> |
|SPO_TeamFileSynched  <br/> |此用户从任何团队网站进行同步的文件数。  <br/> |
|SPO_TeamFileSharedInternally  <br/> |此用户从任何团队网站或组中的用户（可能包含外部用户）内部共享的文件数。  <br/> |
|SPO_TeamFileSharedExternally  <br/> |此用户从任何团队网站进行外部共享的文件数。  <br/> |
|SPO_TeamAccessByOwner  <br/> |用户与之交互且位于该用户所拥有的团队网站上的文件数。  <br/> |
|SPO_TeamAccessByOthers  <br/> |用户与之交互且位于其他用户所拥有的团队网站上的文件数。  <br/> |
|Teams_ChatMessages  <br/> |已发送的聊天邮件数。  <br/> |
|Teams_ChannelMessage  <br/> |发布到频道的邮件数。  <br/> |
|Teams_CallParticipate  <br/> |用户参与的呼叫数。  <br/> |
|Teams_MeetingParticipate  <br/> |用户加入的会议数。  <br/> |
|Teams_HasOtherAction  <br/> |如果用户在 Microsoft 团队中执行其他操作，则为布尔值。  <br/> |
|YAM_MessagePost  <br/> |此用户发布的 Yammer 消息数。  <br/> |
|YAM_MessageLiked  <br/> |此用户点赞的 Yammer 消息数。  <br/> |
|YAM_MessageRead  <br/> |此用户阅读的 Yammer 消息数。  <br/> |
|SFB_P2PSummary  <br/> |此用户参与的对等会话数。  <br/> |
|SFB_ConfOrgSummary  <br/> |此用户组织的会议会话数。  <br/> |
|SFB_ConfPartSummary  <br/> |此用户参与的会议会话数。  <br/> |
   
### <a name="data-table---tenant-product-usage"></a>数据表 - 租户产品使用情况

此表提供了每个月在 Microsoft 365 中每个产品的启用、活动、返回和首次用户的采用情况数据。 Microsoft 365 值表示任一产品中的活动使用率。
  
|**列名称**|**列说明**|
|:-----|:-----|
|Product  <br/> |产品名称，已汇总该产品的使用情况信息。 "产品" 列中的 Microsoft 365 值表示跨任何产品的活动  <br/> |
|Timeframe  <br/> |月份值。对于过去 12 个月（包括当月），每个产品每月对应一行。  <br/> |
|EnabledUsers  <br/> |在时间范围值内允许使用产品的用户数，在一个月的部分时间允许使用的用户也将计算在内。  <br/> |
|ActiveUsers  <br/> |在时间范围值内在产品中执行有意活动的用户数。  <br/> 如果某一用户在某一特定月份内在产品中执行了某一关键活动，则将该用户计为该月该产品的活动用户。 **租户产品活动** 表中列出了各项关键活动。  <br/> |
|CumulativeActiveUsers  <br/> |允许使用产品，且自在新使用情况系统中启用数据收集起在截至时间范围月份前至少使用了一次产品的用户数。  <br/> |
|MoMReturningUsers  <br/> |在时间范围月份内处于活动状态，且在上个月中也处于活动状态的用户数。  <br/> |
|FirstTimeUsers  <br/> |自在新使用情况系统中启用数据收集起在时间范围内首次处于活动状态的用户数。  <br/> 如果自在此新报告系统中启用数据收集起，首次检测到某一用户的活动，该用户将被视为某一特定月份中首次使用的用户。 作为首次用户计数，即使此用户的活动中有很大的缺口，也不会再作为首次用户计数  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>数据表 - 租户产品活动

此表提供活动以及产品中各种活动的活动用户计数的每月总计。
  
|**列名称**|**列说明**|
|:-----|:-----|
|Timeframe  <br/> |月份值。对于过去 12 个月（包括当月），每个产品每月对应一行。  <br/> |
|Product  <br/> |Microsoft 365 中可用使用率数据的产品的名称。  <br/> |
|活动  <br/> |产品中用于展示积极使用产品的活动的名称。  <br/> |
|ActivityCount  <br/> |这是所有活动用户在产品中执行的每个活动的操作总数。  <br/> **注意：** 对于 SharePoint Online 和 OneDrive for Business 活动，此值表示用户与之交互的不同文档数。  <br/> |
|ActiveUserCount  <br/> |在产品中执行活动的用户数。  <br/> |
|TotalDurationInMinute  <br/> |所有活动用户在适当 Skype for Business 活动中使用音频或视频会话的持续分钟数。  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>数据表 - 租户邮箱使用情况

此表包含跨所有具有用户邮箱的已授权 Exchange Online 用户的汇总数据。它包含跨所有用户邮箱的月末状态。此表中的数据不能跨多个月份进行累加。此表中的最新月份的数据表示最新状态。
  
|**列名称**|**列说明**|
|:-----|:-----|
|TotalMailboxes  <br/> |Microsoft 365 订阅的用户邮箱数。  <br/> |
|IssueWarningQuota  <br/> |跨所有用户邮箱发出警告的总配额。  <br/> |
|ProhibitSendQuota  <br/> |跨所有用户邮箱禁止发送的总配额。  <br/> |
|ProhibitSendReceiveQuota  <br/> |跨所有用户邮箱禁止发送接收配额的总配额。  <br/> |
|TotalItemBytes  <br/> |跨所有用户邮箱使用的、以字节为单位的存储量。  <br/> |
|MailboxesNoWarning  <br/> |低于存储警告限制的用户邮箱数。  <br/> |
|MailboxesIssueWarning  <br/> |针对存储配额发出警告的用户邮箱数。  <br/> |
|MailboxesExceedSendQuota  <br/> |已超出发送配额的用户邮箱数。  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |已超出发送/接收配额的用户邮箱数。  <br/> |
|DeletedMailboxes  <br/> |在时间范围内删除的用户邮箱数。  <br/> |
|Timeframe  <br/> |月份值。  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>数据表 - 租户客户端使用情况

下表提供了有关用户用于连接到 Exchange Online、Skype for Business 和 Yammer 的客户端的逐月汇总数据。此表中的客户端尚未使用 SharePoint Online 和 OneDrive for Business 数据。
  
|**列名称**|**列说明**|
|:-----|:-----|
|产品  <br/> |Microsoft 365 中提供了客户端使用情况数据的产品的名称。  <br/> |
|ClientId  <br/> |用于连接到产品的每个设备的名称。  <br/> |
|UserCount  <br/> |针对每个产品使用每个客户端的用户数。  <br/> |
|Timeframe  <br/> |月份值  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>数据表 - 租户 SharePoint Online 使用情况

此表包含有关 SharePoint Online 网站的使用情况或活动的逐月汇总数据。这仅包含团队网站和组网站。此列中展示了 SharePoint Online 网站的月末状态，例如，如果用户创建了 5 个文档并总共使用了 10 MB 存储，然后删除一些文件并添加更多文件，以便在月末文件的状态总共为 7 并使用了 5 MB 存储，则此表中展示的值即为月末状态。此表处于隐藏状态，以避免汇总时重复计数，并用作创建两个引用表的源。
  
|**列名称**|**列说明**|
|:-----|:-----|
|SiteType  <br/> |网站类型值（任意/团队/组）（任意表示这两种网站类型均可）。  <br/> |
|TotalSites  <br/> |在时间范围结束时存在的网站数。  <br/> |
|DocumentCount  <br/> |在时间范围结束时存在于网站上的文档总数。  <br/> |
|Diplansed  <br/> |在时间范围结束时，所有网站的已用存储总计。  <br/> |
|ActivityType  <br/> |记录文件活动的各种类型（任何/活动文件/共享 EXT/INT 的文件/同步的文件）的网站数。  <br/> 任何表示执行任何文件活动。  <br/> |
|SitesWithOwnerActivities  <br/> |活动网站数，其中网站所有者在其自己的网站上执行特定文件活动。  <br/> |
|SitesWithNonOwnerActivities  <br/> |该月汇总的活动网站数，其中除网站所有者之外的用户在网站上执行特定文件活动。  <br/> |
|ActivityTotalSites  <br/> |记录时间范围内的任何活动的网站数。如果某一网站在时间范围早期具有活动，但在时间范围结束时被删除，仍会将其计入该时间范围内活动网站。  <br/> |
|Timeframe  <br/> |此列包含日期值。用作日历表的多对一关系。  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>数据表-租户 OneDrive 使用情况

此表提供有关 OneDrive 帐户的数据，如帐户数、跨 OneDrive 帐户的文档数、使用的存储、各活动类型的文件数。此外，此表中还展示了 OneDrive for Business 帐户的月末状态。例如，如果用户使用 10 MB 存储创建了 5 个文档，然后删除一些文档并添加更多文件，以便在月末具有 7 个文件，这些文件使用了 5 MB 存储，则月末将在此表中展示月末值。
  
|**列名称**|**列说明**|
|:-----|:-----|
|SiteType  <br/> |值为"OneDrive"。  <br/> |
|TotalSites  <br/> |在时间范围结束时存在的 OneDrive for Business 帐户数。  <br/> |
|DocumentCount  <br/> |在时间范围结束时，所有 OneDrive for Business 帐户中存在的文档总数  <br/> |
|Diplansed  <br/> |在时间范围结束时，所有 OneDrive 帐户的已用存储总计。  <br/> |
|ActivityType  <br/> |记录文件活动的各种类型（任何/活动文件/共享 EXT/INT 的文件/同步的文件）的帐户数。  <br/> 任何表示执行任何文件活动  <br/> |
|SitesWithOwnerActivities  <br/> |活动 OneDrive for Business 帐户数，其中帐户所有者在其自己的帐户上执行特定文件活动。  <br/> |
|SitesWithNonOwnerActivities  <br/> |OneDrive for Business 帐户计数，其中文件活动由除帐户所有者之外的用户执行。  <br/> |
|ActivityTotalSites  <br/> |在时间范围内记录任何活动的 OneDrive for Business 帐户数。如果某一 OneDrive for Business 帐户在时间范围早期具有活动，但在时间范围结束时被删除，仍会将其计入该时间范围的活动 OneDrive for Business 帐户。  <br/> |
|Timeframe  <br/> |此列包含日期值。用作日历表的多对一关系。  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>数据表-租户 Microsoft 365 组使用情况

此表提供有关如何在组织中使用 Microsoft 365 组的数据。
  
****

|**列名称**|**列说明**|
|:-----|:-----|
|时间  <br/> |月份值。 对于过去 12 个月（包括当月），每个产品每月对应一行。  <br/> |
|GroupType  <br/> |组的类型（private/public/any）。  <br/> |
|TotalGroups  <br/> |每个组类型中的组数。  <br/> |
|ActiveGroups  <br/> |活动组的数量。  <br/> |
|MBX_TotalGroups  <br/> |邮箱组的数量。  <br/> |
|MBX_ActiveGroups  <br/> |活动邮箱组的数量。  <br/> |
|MBX_TotalActivities  <br/> |邮箱活动的数量。  <br/> |
|MBX_TotalItems  <br/> |邮箱项目数。  <br/> |
|MBX_StorageUsed  <br/> |使用的邮箱存储的数量。  <br/> |
|SPO_TotalGroups  <br/> |SharePoint 组的数量。  <br/> |
|SPO_ActiveGroups  <br/> |活动 SharePoint 组的数量。  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |具有文件访问活动的 SharePoint 组的数量。  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |包含文件同步活动的 SharePoint 组的数量。  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |包含内部共享活动或与组（可能包含外部用户）的 SharePoint 组的数量。  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |共享外部活动的 SharePoint 组的数量。  <br/> |
|SPO_TotalActivities  <br/> |SharePoint 活动的数量。  <br/> |
|SPO_FileAccessedActivities  <br/> |SharePoint 文件访问的活动的数量。  <br/> |
|SPO_FileSyncedActivities  <br/> |SharePoint 文件同步活动的数量。  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |内部或与组（可能包含外部成员）的 SharePoint 文件共享活动的数量。  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |SharePoint 文件共享外部活动的数量。  <br/> |
|SPO_TotalFiles  <br/> |SharePoint 文件数。  <br/> |
|SPO_ActiveFiles  <br/> |活动 SharePoint 文件的数量。  <br/> |
|SPO_StorageUsed  <br/> |使用的 SharePoint 存储量。  <br/> |
|YAM_TotalGroups  <br/> |Yammer 组的数量。  <br/> |
|YAM_ActiveGroups  <br/> |活动 Yammer 组的数量。  <br/> |
|YAM_LikedActiveGroups  <br/> |具有类似活动的 Yammer 组的数量。  <br/> |
|YAM_PostedActiveGroups  <br/> |包含 post 活动的 Yammer 组的数量。  <br/> |
|YAM_ReadActiveGroups  <br/> |具有读取活动的 Yammer 组的数量。  <br/> |
|YAM_TotalActivities  <br/> |Yammer 活动的数量。  <br/> |
|YAM_LikedActivities  <br/> |类似活动的 Yammer 数。  <br/> |
|YAM_PostedActivties  <br/> |Yammer 发布活动的数量。  <br/> |
|YAM_ReadActivites  <br/> |Yammer 读取活动的次数。  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>数据表 - 租户 Office 激活

该表提供了有关跨服务计划的 Office 订阅激活次数的数据，例如，Microsoft 365 Apps for 企业、Visio、Project。 此外，它还提供了有关每个设备 (Android/iOS/Mac/PC) 的激活次数的数据。
  
|**列名称**|**列说明**|
|:-----|:-----|
|ServicePlanName  <br/> |服务计划名称值列表和通过设备进行的激活次数，如以下列所示。  <br/> |
|TotalEnabled  <br/> |在时间范围结束时，允许使用每个服务计划的用户数（按服务计划名称排列）。  <br/> |
|TotalActivatedUsers  <br/> |在时间范围结束时，激活每个服务计划的用户数。  <br/> |
|AndroidCount  <br/> |在时间范围结束时，Android 设备上每个服务计划的激活次数。  <br/> |
|iOSCount  <br/> |在时间范围结束时，iOS 设备上每个服务计划的激活次数。  <br/> |
|MacCount  <br/> |在时间范围结束时，MAC 设备上每个服务计划的激活次数。  <br/> |
|PcCount  <br/> |在时间范围结束时，PC 设备上每个服务计划的激活次数。  <br/> |
|WinRtCount  <br/> |在时间范围结束时，Windows Mobile 设备上每个服务计划的激活次数。  <br/> |
|Timeframe  <br/> |此列包含日期值。用作日历表的多对一关系。  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   

