---
title: Microsoft 365 使用情况分析数据模型
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: '了解使用情况分析如何连接到 API 并提供各种服务使用情况的每月Microsoft 365趋势。  '
ms.openlocfilehash: 013fdd75063ad8ad2489ebe43c9091f05f94c14c
ms.sourcegitcommit: 57211e8082a3429017ad33fe0e6bd9af203bb7ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2022
ms.locfileid: "62487271"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Microsoft 365 使用情况分析数据模型

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>数据Microsoft 365使用情况分析表

Microsoft 365使用情况分析连接到公开多维数据模型的 API。 使用情况分析Microsoft 365其数据的 API 来自各种普遍可用的Graph API。 应用程序使用情况Microsoft 365 API 的功能本身并不普遍可用。
  
> [!NOTE]
> 有关详细信息，请参阅使用 [Microsoft Microsoft 365 中的使用率Graph](/graph/api/resources/report)。 
  
此 API 提供有关各种服务使用情况的每月Microsoft 365的信息。 有关 API 返回的确切数据，请参考以下部分中的表。
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>报告 API 返回Microsoft 365表

|**表名**|**表中信息**|**日期范围**|
|:-----|:-----|:-----|
|租户产品使用情况  <br/> |包含启用的活动用户、按月保留的用户、第一次用户和累积活动用户的每月总计。  <br/> |包含滚动的为期 12 个月（包含当月）的每月汇总数据。  <br/> |
|租户产品活动  <br/> |包含每月活动总数和产品中其他活动的活动用户计数。  <br/> 有关在此数据表中返回的产品中的活动的信息，请参阅[活动用户定义](active-user-in-usage-reports.md)。  <br/> |包含滚动的为期 12 个月（包含当月）的每月汇总数据。  <br/> |
|租户 Office 许可证  <br/> |包含分配给用户的 Microsoft Office 订阅数的数据  <br/> |包含滚动的 12 个月（包括当前部分月份）的月份结束状态数据。  <br/> |
|租户邮箱使用情况  <br/> |包含有关用户邮箱、邮箱总数以及存储使用方式的数据。  <br/> |包含滚动的 12 个月（包括当前部分月份）的月份结束状态数据。  <br/> |
|租户客户端使用情况  <br/> |包含有关频繁使用特定客户端/设备连接到 Exchange Online、Skype for Business 和 Yammer 的用户数的数据。  <br/> |包含滚动的为期 12 个月（包含当月）的每月汇总数据。  <br/> |
|租户 SharePoint Online 使用情况  <br/> |包含有关 SharePoint 网站（包括团队网站或组网站）的数据，如网站总数、网站上的文档数、各活动类型的文件数和已用存储。  <br/> |包含滚动的 12 个月（包括当前部分月份）的月份结束状态数据。  <br/> |
|租户 OneDrive for Business 使用情况  <br/> |包含有关 OneDrive 帐户的数据，如帐户数、跨 OneDrive 的文档数、已用存储、各活动类型的文件数。  <br/> |包含滚动的 12 个月（包括当前部分月份）的月份结束状态数据。  <br/> |
|租户Microsoft 365组使用情况  <br/> |包含有关Microsoft 365组使用情况的数据，包括邮箱、SharePoint和Yammer。  <br/> |包含滚动的 12 个月（包括当前部分月份）的月份结束状态数据。  <br/> |
|租户 Office 激活  <br/> |包含有关 Office 订阅激活数、每个设备 (Android/iOS/Mac/PC) 的激活计数、按服务计划（例如，Microsoft 365 企业应用版、Visio、Project）的激活数的数据。  <br/> |包含滚动的 12 个月（包括当前部分月份）的月份结束状态数据。  <br/> |
|用户状态  <br/> |包含有关用户的元数据，包括用户显示名称、分配的产品、位置、部门、职务、公司。 此数据与在上一个完整的月份中分配许可证的用户有关。 每个用户都由用户 ID 唯一表示。  <br/> |此数据有关在刚刚结束的一个月内分配到许可证的用户。  <br/> |
|用户活动  <br/> |包含有关授权用户执行的活动的每用户级别的信息。  <br/> 有关在此数据表中返回的产品中的活动的信息，请参阅[活动用户定义](active-user-in-usage-reports.md)。  <br/> |此数据有关刚刚结束的一个月内在任何服务中执行活动的用户。  <br/> |
   
展开以下各部分，查看每个数据表的详细信息。
  
### <a name="data-table---user-state"></a>数据表 - 用户状态

此表为在上一完整月份中分配了许可证的所有用户提供用户级别详细信息。 其数据来自于 Azure Active Directory。
  
|**列名称**|**列说明**|
|:-----|:-----|
|UserId  <br/> |表示用户并启用与数据集内的其他数据表联接的唯一用户 ID。  <br/> |
|Timeframe  <br/> |月份值，此表包含该月份的数据。  <br/> |
|UPN  <br/> |用户主体名称，用于唯一标识用户，使其能够与其他外部数据源联接。  <br/> |
|DisplayName  <br/> |用户的显示名称。  <br/> |
|IDType  <br/> |如果用户是使用 Yammer ID 进行连接的 Yammer 用户，则 ID 类型设置为 1;如果用户使用 Microsoft 365 ID 连接到 Yammer，则设置为 0。  <br/> 值为 1 表示此用户使用其 Yammer ID Yammer而不是其Microsoft 365 ID  <br/> |
|HasLicenseEXO  <br/> |如果为用户分配了许可证，并启用了在当月的最后一天Exchange许可证，则设置为 true。  <br/> |
|HasLicenseODB  <br/> |如果为用户分配了许可证，并启用了在当月的最后一天OneDrive for Business许可证，则设置为 true。  <br/> |
|HasLicenseSPO  <br/> |如果为用户分配了许可证，并启用了在当月最后一SharePoint使用 SharePoint Online，则设置为 true。  <br/> |
|HasLicenseYAM  <br/> |如果为用户分配了许可证并启用了在Yammer最后一天使用许可证，则设置为 true。  <br/> |
|HasLicenseSFB  <br/> |如果为用户分配了许可证，并启用了在当月的最后一天使用 Skype For Business，则设置为 true。  <br/> |
|HasLicenseTeams  <br/> |如果为用户分配了许可证并启用在当月的最后一天Microsoft Teams，则设置为 true。  <br/> |
|Company  <br/> |此用户在 Azure Active Directory 中对应的公司数据。  <br/> |
|Department  <br/> |此用户在 Azure Active Directory 中对应的部门数据。  <br/> |
|LocationCity  <br/> |此用户在 Azure Active Directory 中对应的城市数据。  <br/> |
|LocationCountry  <br/> |此用户在 Azure Active Directory 中对应的国家/地区数据。  <br/> |
|LocationState  <br/> |此用户在 Azure Active Directory 中对应的省/市/自治区数据。  <br/> |
|LocationOffice  <br/> |用户的 Office。  <br/> |
|Title  <br/> |此用户在 Azure Active Directory 中对应的职务数据。  <br/> |
|Deleted  <br/> |如此 如果该用户已被删除Microsoft 365最后一个完整的月份。  <br/> |
|DeletedDate  <br/> |从用户中删除用户的日期Microsoft 365。  <br/> |
|YAM_State  <br/> |用户当前系统中Yammer状态，可以是活动状态、已删除状态或已挂起状态。  <br/> |
|YAM_ActivationDate  <br/> |用户在 Yammer 中进入活动状态的日期。  <br/> |
|YAM_DeletionDate  <br/> |用户在 Yammer 中进入已删除状态的日期。  <br/> |
|YAM_SuspensionDate  <br/> |用户在 Yammer 中进入已挂起状态的日期。  <br/> |
   
### <a name="data-table---user-activity"></a>数据表 - 用户活动

此表包含有关上个月在任何服务中有活动的每个用户的数据。
  
|**列名称**|**列说明**|
|:-----|:-----|
|UserID  <br/> |表示用户并启用与数据集内的其他数据表联接的唯一用户 ID。  <br/> |
|IDType  <br/> |如果用户是使用 Yammer ID 进行连接的 Yammer 用户，则 ID 类型设置为 1;如果用户使用 Microsoft 365 ID 连接到 Yammer，则设置为 0。  <br/> 值为 1 表示此用户使用其 Yammer ID Yammer而不是其Microsoft 365 ID  <br/> |
|Timeframe  <br/> |月份值，此表代表该月份的数据。  <br/> |
|EXO_EmailSent  <br/> |发送的邮件数。  <br/> |
|EXO_EmailReceived  <br/> |接收的邮件数。  <br/> |
|EXO_EmailRead  <br/> |用户执行的电子邮件阅读活动数，可以是阅读已读电子邮件或之前收到的电子邮件多次。  <br/> |
|EXO_AppointmentCreated  <br/> |创建的约会数。  <br/> |
|EXO_MeetingAccepted  <br/> |接受的会议数。  <br/> |
|EXO_MeetingCancelled  <br/> |已取消的会议数。  <br/> |
|EXO_MeetingDeclined  <br/> |拒绝的会议数。  <br/> |
|EXO_MeetingSent  <br/> |发送的会议数。  <br/> |
|ODB_FileViewedModified  <br/> |此用户在任何 OneDrive for Business 上与其进行了交互（如创建、更新、删除、查看或下载）的文件数。  <br/> |
|ODB_FileSynched  <br/> |此用户在任何 OneDrive for Business 上同步的文件数。  <br/> |
|ODB_FileSharedInternally  <br/> |此用户从任何用户内部共享的文件数OneDrive for Business组内可能包含外部用户 (组) 。  <br/> |
|ODB_FileSharedExternally  <br/> |此用户从任何 OneDrive for Business 进行外部共享的文件数。  <br/> |
|ODB_AccessedByOwner  <br/> |用户与之交互的网站数，这些网站驻留在其自己的OneDrive for Business。  <br/> |
|ODB_AccessedByOthers  <br/> |此用户与之交互的网站数，这些网站驻留在另一个用户的OneDrive for Business。  <br/> |
|SPO_GroupFileViewedModified  <br/> |此用户在任何组网站上与之交互的文件数。  <br/> |
|SPO_GroupFileSynched  <br/> |此用户在任何组网站上进行同步的文件数。  <br/> |
|SPO_GroupFileSharedInternally  <br/> |已与组织内部用户或组内用户（可能包含外部用户 (共享的文件) 。  <br/> |
|SPO_GroupFileSharedExternally  <br/> |此用户从任何组网站进行外部共享的文件数。  <br/> |
|SPO_GroupAccessedByOwner  <br/> |用户与之交互的网站数，这些网站位于他们拥有的组网站上。  <br/> |
|SPO_GroupAccessedByOthers  <br/> |用户与之交互的网站数，这些网站驻留在另一个用户拥有的组网站上。  <br/> |
|SPO_OtherFileViewedModified  <br/> |此用户在任何其他网站上与之交互的文件数。  <br/> |
|SPO_OtherFileSynched  <br/> |此用户从任何其他站点同步的文件数。  <br/> |
|SPO_OtherFileSharedInternally  <br/> |此用户从任何其他网站内部共享的文件数，或与组中可能包含外部用户 (组) 。 <br/> |
|SPO_OtherFileSharedExternally  <br/> |此用户从任何其他网站外部共享的文件数。  <br/> |
|SPO_OtherAccessedByOwner  <br/> |用户与之交互的网站数，这些站点位于他们拥有的其他网站上。  <br/> |
|SPO_OtherAccessedByOthers  <br/> |用户与之交互的驻留在另一个用户拥有的另一个网站上的网站数。  <br/> |
|SPO_TeamFileViewedModified  <br/> |与此用户在任何团队网站上进行交互的文件数。  <br/> |
|SPO_TeamFileSynched  <br/> |此用户从任何团队网站进行同步的文件数。  <br/> |
|SPO_TeamFileSharedInternally  <br/> |此用户从任何团队网站内部共享的文件数，或与组中可能包含外部用户 (组) 。  <br/> |
|SPO_TeamFileSharedExternally  <br/> |此用户从任何团队网站进行外部共享的文件数。  <br/> |
|SPO_TeamAccessedByOwner  <br/> |用户与之交互的网站数，这些网站位于他们拥有的团队网站上。  <br/> |
|SPO_TeamAccessedByOthers  <br/> |用户与之交互的网站数，这些网站驻留在另一个用户拥有的团队网站上。  <br/> |
|Teams_ChatMessages  <br/> |发送的聊天消息数。  <br/> |
|Teams_ChannelMessage  <br/> |张贴到频道的消息数。  <br/> |
|Teams_CallParticipate  <br/> |用户参与的呼叫数。  <br/> |
|Teams_MeetingParticipate  <br/> |用户加入的会议数。  <br/> |
|Teams_HasOtherAction  <br/> |如果用户在任务中执行了其他操作，则布尔Microsoft Teams。  <br/> |
|YAM_MessagePost  <br/> |此Yammer发布的消息数。  <br/> |
|YAM_MessageLiked  <br/> |用户Yammer的消息数。  <br/> |
|YAM_MessageRead  <br/> |此Yammer读取的消息数。  <br/> |
|SFB_P2PSummary  <br/> |此用户参与的对等会话数。  <br/> |
|SFB_ConfOrgSummary  <br/> |此用户组织的会议会话数。  <br/> |
|SFB_ConfPartSummary  <br/> |此用户参与的会议会话数。  <br/> |

> [!NOTE]
> Teams_HasOtherAction用户被视为活动用户，但组织的聊天消息、一对一呼叫、频道消息、会议总数和会议值为零。
   
### <a name="data-table---tenant-product-usage"></a>数据表 - 租户产品使用情况

此表提供每月的采用数据，这些数据针对每个产品的启用、活跃、返回和首次使用Microsoft 365。 这些Microsoft 365值表示任一产品中的活动使用情况。
  
|**列名称**|**列说明**|
|:-----|:-----|
|Product  <br/> |产品名称，已汇总该产品的使用情况信息。 Microsoft 365列中的值表示任何产品中的活动  <br/> |
|Timeframe  <br/> |月份值。对于过去 12 个月（包括当月），每个产品每月对应一行。  <br/> |
|EnabledUsers  <br/> |允许将产品用于时间范围值的用户数，如果用户在一个月的某一部分处于启用状态，则仍计入该用户。  <br/> |
|ActiveUsers  <br/> |为时间范围值在产品中执行有意活动的用户数。  <br/> 如果某一用户在某一特定月份内在产品中执行了某一关键活动，则将该用户计为该月该产品的活动用户。 **租户产品活动** 表中列出了各项关键活动。  <br/> |
|CumulativeActiveUsers  <br/> |允许使用产品，且自在新使用情况系统中启用数据收集起在截至时间范围月份前至少使用了一次产品的用户数。  <br/> |
|MoMReturningUsers  <br/> |在时间范围月份内处于活动状态，且在上个月中也处于活动状态的用户数。  <br/> |
|FirstTimeUsers  <br/> |自在新使用情况系统中启用数据收集起在时间范围内首次处于活动状态的用户数。  <br/> 如果自在此新报告系统中启用数据收集起，首次检测到某一用户的活动，该用户将被视为某一特定月份中首次使用的用户。 一旦计为第一次用户，即使此用户的活动存在较大的间隙，他们绝不会再次被计为第一次用户  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>数据表 - 租户产品活动

此表每月提供活动总数和产品中其他活动的活动用户计数。
  
|**列名称**|**列说明**|
|:-----|:-----|
|Timeframe  <br/> |月份值。对于过去 12 个月（包括当月），每个产品每月对应一行。  <br/> |
|Product  <br/> |可用使用情况数据Microsoft 365产品的名称。  <br/> |
|活动  <br/> |产品中用于展示积极使用产品的活动的名称。  <br/> |
|ActivityCount  <br/> |这是所有活动用户在产品中执行的每个活动的操作总数。  <br/> **注意：** 对于 SharePoint Online 和 OneDrive for Business 活动，此值表示用户与之交互的不同文档数。  <br/> |
|ActiveUserCount  <br/> |在产品中执行活动的用户数。  <br/> |
|TotalDurationInMinute  <br/> |所有活动用户在适当 Skype for Business 活动中使用音频或视频会话的持续分钟数。  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>数据表 - 租户邮箱使用情况

此表包含拥有用户邮箱Exchange Online所有许可用户的摘要数据。 它包含跨所有用户邮箱的月末状态。 此表中的数据不能跨多个月份进行累加。 此表中的最新月份的数据表示最新状态。
  
|**列名称**|**列说明**|
|:-----|:-----|
|TotalMailboxes  <br/> |订阅的用户邮箱Microsoft 365数量。  <br/> |
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

此表提供有关用户用于连接到 Exchange Online、Skype for Business 和 Yammer 的每月汇总数据。 此表中的客户端尚未使用 SharePoint Online 和 OneDrive for Business 数据。
  
|**列名称**|**列说明**|
|:-----|:-----|
|Product  <br/> |客户端使用情况数据Microsoft 365产品的名称。  <br/> |
|ClientId  <br/> |用于连接到产品的每个设备的名称。  <br/> |
|UserCount  <br/> |针对每个产品使用每个客户端的用户数。  <br/> |
|Timeframe  <br/> |月份值  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>数据表 - 租户 SharePoint Online 使用情况

此表包含有关 SharePoint Online 网站的使用情况或活动的逐月汇总数据。 这仅包含团队网站和组网站。 SharePoint Online 网站的结束状态在此列中表示，例如，如果用户创建了 5 个文档，并使用了 10 MB 的总存储，然后删除了一些文件，并添加了更多文件，以便文件在当月结束时总共七个使用 5 MB 存储， 此表中表示的值是月份结束状态。 此表处于隐藏状态，以避免汇总时重复计数，并用作创建两个引用表的源。
  
|**列名称**|**列说明**|
|:-----|:-----|
|SiteType  <br/> |网站类型值（任意/团队/组）（任意表示这两种网站类型均可）。  <br/> |
|TotalSites  <br/> |在时间范围结束时存在的网站数。  <br/> |
|DocumentCount  <br/> |在时间范围结束时存在于网站上的文档总数。  <br/> |
|Diplansed  <br/> |在时间范围结束时，所有网站的已用存储总计。  <br/> |
|ActivityType  <br/> |记录文件活动的各种类型（任何/活动文件/共享 EXT/INT 的文件/同步的文件）的网站数。  <br/> 表示已执行的任何文件活动。  <br/> |
|SitesWithOwnerActivities  <br/> |活动网站数，其中网站所有者在其自己的网站上执行特定文件活动。 可以从 PowerShell 命令 **get-sposite 获取网站所有者**。 这是负责网站的人。   <br/> |
|SitesWithNonOwnerActivities  <br/> |该月汇总的活动网站数，其中除网站所有者之外的用户在网站上执行特定文件活动。 可以从 PowerShell 命令 **get-sposite 获取网站所有者**。 这是负责网站的人。 <br/> |
|ActivityTotalSites  <br/> |记录时间范围内的任何活动的网站数。如果某一网站在时间范围早期具有活动，但在时间范围结束时被删除，仍会将其计入该时间范围内活动网站。  <br/> |
|Timeframe  <br/> |此列包含日期值。用作日历表的多对一关系。  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>数据表 - 租户OneDrive使用情况

此表提供有关 OneDrive 帐户的数据，如帐户数、跨 OneDrive 帐户的文档数、使用的存储、各活动类型的文件数。 此外，此表中还展示了 OneDrive for Business 帐户的月末状态。 例如，如果用户创建了一个使用 10 MB 存储的五个文档，然后删除了一些文档并添加了更多文件，以便当月结束时他们拥有七个使用 5 MB 存储的文件，则当月结束值在此表中表示为当月结束时。
  
|**列名称**|**列说明**|
|:-----|:-----|
|SiteType  <br/> |值为"OneDrive"。  <br/> |
|TotalSites  <br/> |在时间范围结束时存在的 OneDrive for Business 帐户数。  <br/> |
|DocumentCount  <br/> |在时间范围结束时，所有 OneDrive for Business 帐户中存在的文档总数  <br/> |
|Diplansed  <br/> |在时间范围结束时，所有OneDrive帐户使用的总存储。  <br/> |
|ActivityType  <br/> |记录文件活动的各种类型（任何/活动文件/共享 EXT/INT 的文件/同步的文件）的帐户数。  <br/> 任何表示执行任何文件活动  <br/> |
|SitesWithOwnerActivities  <br/> |活动 OneDrive for Business 帐户数，其中帐户所有者在其自己的帐户上执行特定文件活动。  <br/> |
|SitesWithNonOwnerActivities  <br/> |OneDrive for Business 帐户计数，其中文件活动由除帐户所有者之外的用户执行。  <br/> |
|ActivityTotalSites  <br/> |在时间范围内记录任何活动的 OneDrive for Business 帐户数。如果某一 OneDrive for Business 帐户在时间范围早期具有活动，但在时间范围结束时被删除，仍会将其计入该时间范围的活动 OneDrive for Business 帐户。  <br/> |
|Timeframe  <br/> |此列包含日期值。用作日历表的多对一关系。  <br/> |
|Content Date  <br/> |如果时间范围显示当前月，则此值表示数据可供使用的当前月的最后一天。  <br/> 如果时间范围显示上个月，则此值表示上个月的最后一天。  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>数据表 - 租户Microsoft 365组使用情况

此表提供有关如何在Microsoft 365组使用的数据。
  
****

|**列名称**|**列说明**|
|:-----|:-----|
|TimeFrame  <br/> |月份值。对于过去 12 个月（包括当月），每个产品每月对应一行。  <br/> |
|GroupType  <br/> |专用 (/公用/任意组) 。  <br/> |
|TotalGroups  <br/> |每个组类型中的组数。  <br/> |
|ActiveGroups  <br/> |活动组的数量。  <br/> |
|MBX_TotalGroups  <br/> |邮箱组数。  <br/> |
|MBX_ActiveGroups  <br/> |活动邮箱组的数量。  <br/> |
|MBX_TotalActivities  <br/> |邮箱活动数。  <br/> |
|MBX_TotalItems  <br/> |邮箱项目数。  <br/> |
|MBX_StorageUsed  <br/> |使用的邮箱存储数量。  <br/> |
|SPO_TotalGroups  <br/> |组SharePoint数。  <br/> |
|SPO_ActiveGroups  <br/> |活动组SharePoint数。  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |具有SharePoint的活动的组数。  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |具有SharePoint活动的活动组数。  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |内部SharePoint共享活动的组数，或具有可能包含外部用户 (的组) 。  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |具有SharePoint活动的组数。  <br/> |
|SPO_TotalActivities  <br/> |活动SharePoint数。  <br/> |
|SPO_FileAccessedActivities  <br/> |文件SharePoint的活动数。  <br/> |
|SPO_FileSyncedActivities  <br/> |文件SharePoint活动的数量。  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |内部SharePoint共享活动，或与可能包含外部成员 (组共享) 。  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |外部SharePoint共享的文件数。  <br/> |
|SPO_TotalFiles  <br/> |文件SharePoint数。  <br/> |
|SPO_ActiveFiles  <br/> |活动文件SharePoint数。  <br/> |
|SPO_StorageUsed  <br/> |使用的SharePoint的数量。  <br/> |
|YAM_TotalGroups  <br/> |组Yammer数。  <br/> |
|YAM_ActiveGroups  <br/> |活动组Yammer数。  <br/> |
|YAM_LikedActiveGroups  <br/> |具有Yammer的活动的组数。  <br/> |
|YAM_PostedActiveGroups  <br/> |具有Yammer的活动的组数。  <br/> |
|YAM_ReadActiveGroups  <br/> |具有Yammer的组数。  <br/> |
|YAM_TotalActivities  <br/> |活动Yammer数。  <br/> |
|YAM_LikedActivities  <br/> |喜欢的活动Yammer个数。  <br/> |
|YAM_PostedActivties  <br/> |帖子Yammer数。  <br/> |
|YAM_ReadActivites  <br/> |读取Yammer数。  <br/> |

### <a name="data-table---tenant-office-licenses"></a>数据表 - 租户Office许可证

此表提供有关用户的许可证分配的按月摘要数据。 
  
|**列名称**|**列说明**|
|:-----|:-----|
|LicenseName  <br/> |许可证的名称。  <br/> |
|AssignedCount  <br/> |分配的许可证数。  <br/> |
|Timeframe  <br/> |月份值。  <br/> |

### <a name="data-table---tenant-office-activation"></a>数据表 - 租户 Office 激活

该表提供有关跨服务计划Office订阅激活数的数据，例如Microsoft 365 应用版企业版、Visio Project。 此外，它还提供了有关每个设备 (Android/iOS/Mac/PC) 的激活次数的数据。
  
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
