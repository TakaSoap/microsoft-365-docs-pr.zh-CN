---
title: 审核日志中的详细属性
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: 本文提供导出 Office 365 记录的结果时包含的其他审核日志说明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69a34f4de948bc9533ef2872d94171134e50ffea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927070"
---
# <a name="detailed-properties-in-the-audit-log"></a>审核日志中的详细属性

从安全与合规中心审核日志搜索的结果时，&下载符合搜索条件的所有结果。 为此，在"审核日志 **搜索**"页上选择"导出 \> 结果""**下载所有结果**"。 有关详细信息，请参阅搜索[审核日志。](search-the-audit-log-in-security-and-compliance.md)
  
 导出 审核日志 搜索的所有结果时，统一 审核日志 中的原始数据将复制到下载到本地计算机的逗号分隔值 (CSV) 文件中。 此文件包含名为 **AuditData** 的列中每个审核记录的其他信息。 此列包含记录中多个属性的多值审核日志属性。 此多 **值属性中的每个** 属性：值对用逗号分隔。 
  
下表介绍了根据在多属性 **AuditData** 列中 (发生事件的服务) 中包含的属性。 具有 **此属性列的 Office 365** 服务指示包含此属性 (管理员) 的服务和活动类型。 有关这些属性或本主题中可能未列出的属性的更多详细信息，请参阅 [管理活动 API 架构](/office/office-365-management-api/office-365-management-activity-api-schema)。
  
> [!TIP]
> 您可以使用 Excel 中 Power Query 中的 JSON 转换功能将 **AuditData** 列拆分为多个列，以便每个属性都有自己的列。 这让你能够对一个或多个属性进行排序和筛选。 若要了解如何进行此操作，请参阅导出 [、配置和查看审核日志记录](export-view-audit-log-records.md)。 
  
|**属性**|**说明**|**具有此属性的 Microsoft 365 服务**|
|:-----|:-----|:-----|
|Actor|执行该操作的用户或服务帐户。|Azure Active Directory|
|AddOnName|在团队中添加、删除或更新的加载项的名称。 Microsoft Teams 中的加载项类型为自动程序、连接器或选项卡。|Microsoft Teams|
|AddOnType|在团队中添加、删除或更新的加载项的类型。 以下值指示加载项的类型。  <br/> **1** - 指示自动程序。<br/> **2** - 指示连接器。<br/> **3** - 指示选项卡。|Microsoft Teams|
|AzureActiveDirectoryEventType|Azure Active Directory 事件的类型。 下列值指示事件的类型。  <br/> **0** - 指示帐户登录事件。<br/> **1** - 指示 Azure 应用程序安全事件。|Azure Active Directory|
|ChannelGuid|Microsoft Teams 频道的 ID。 频道所在的团队由 **TeamName** 和 **TeamGuid** 属性标识。|Microsoft Teams|
|ChannelName|Microsoft Teams 频道的名称。 频道所在的团队由 **TeamName** 和 **TeamGuid** 属性标识。|Microsoft Teams|
|Client|客户端设备、设备操作系统和用于登录事件的设备浏览器 (，例如 Nokia Lumia 920;Windows Phone 8;IE Mobile 11) 。|Azure Active Directory|
|ClientInfoString|有关用于执行此操作的电子邮件客户端的信息，例如浏览器版本、Outlook 版本和移动设备信息|Exchange (邮箱活动) |
|ClientIP|记录活动时使用的设备的 IP 地址。 IP 地址显示为 IPv4 或 IPv6 地址格式。<br/><br/> 对于某些服务，此属性中显示的值可能是代表用户调用服务的受信任应用程序（例如，Web 应用上的 Office）的 IP 地址，而不是执行活动的人员使用的设备的 IP 地址。 <br/><br/>此外，对于管理员活动 (或由系统帐户) 针对 Azure Active Directory 相关事件执行的活动，不会记录 IP 地址，并且 ClientIP 属性的值为 `null` 。 |Azure Active Directory、Exchange、SharePoint|
|CreationTime|用户执行活动时的协调世界时 (UTC) 日期和时间。|全部|
|DestinationFileExtension|复制或移动的文件的文件扩展名。 此属性只对 FileCopied 和 FileMoved 用户活动显示。|SharePoint|
|DestinationFileName|复制或移动文件的名称。 此属性只对 FileCopied 和 FileMoved 操作显示。|SharePoint|
|DestinationRelativeUrl|在其中复制或移动文件的目标文件夹的 URL。 SiteURL、DestinationRelativeURL和 **DestinationFileName** 属性的值的组合与 ObjectID 属性的值相同，ObjectID 属性的值是所复制文件的完整路径名。  此属性只对 FileCopied 和 FileMoved 用户活动显示。|SharePoint|
|EventSource|识别在 SharePoint 中发生的事件。 可能的值是 **SharePoint** 和 **ObjectModel**。|SharePoint|
|ExternalAccess|对于 Exchange 管理员活动，指定 cmdlet 是由您组织的用户、Microsoft 数据中心人员或数据中心服务帐户运行，还是由委派管理员运行。 值 **False** 表示 cmdlet 由组织中的某人运行。 值 **True** 表示 cmdlet 由数据中心人员、数据中心服务帐户或委托的管理员运行。  <br/> 对于 Exchange 邮箱活动，指定邮箱是否由组织外部用户访问。|Exchange|
|ExtendedProperties|Azure Active Directory 事件的扩展属性。|Azure Active Directory|
|ID|报告条目的 ID。 ID 唯一标识报告条目。|全部|
|InternalLogonType|仅供内部使用。|Exchange (邮箱活动) |
|ItemType|访问或修改的对象类型。 可能的值包括File、Folder、Web、Site、Tenant 和 **DocumentLibrary**。    |SharePoint|
|LoginStatus|标识可能发生的登录失败。|Azure Active Directory|
|LogonType|邮箱访问的类型。 下列值指示访问邮箱的用户的类型。  <br/><br/> **0** - 指示邮箱所有者。<br/> **1** - 指示管理员。<br/> **2** - 指示代理人。 <br/>**3** - 指示 Microsoft 数据中心中的传输服务。<br/> **4** - 指示 Microsoft 数据中心中的服务帐户。 <br/>**6** - 指示委派的管理员。|Exchange (邮箱活动) |
|MailboxGuid|访问邮箱的 Exchange GUID。|Exchange (邮箱活动) |
|MailboxOwnerUPN|拥有已访问邮箱的人员的电子邮件地址。|Exchange (邮箱活动) |
|成员|列出已从团队中添加或删除的用户。 以下值表示分配给用户的角色类型。  <br/><br/> **1** - 指示所有者角色。<br/> **2** - 表示“成员”角色。<br/> **3** - 表示“来宾”角色。 <br/><br/>成员属性还包括组织的名称和成员的电子邮件地址。|Microsoft Teams|
|ModifiedProperties (Name、NewValue、OldValue) |属性包含在管理员事件中，例如将用户添加为网站或网站集管理组的成员。 属性包括修改 (例如，Site Admin 组) 修改的属性的新值 (例如已添加为网站管理员的用户和已修改对象的上一个值。|所有 (管理员活动) |
|ObjectId|对于 Exchange 管理员审核日志，通过 cmdlet 修改的对象的名称。  <br/> 对于 SharePoint 活动，用户访问的文件或文件夹的完整 URL 路径名称。  <br/> 对于 Azure AD 活动，为已修改的用户帐户的名称。|全部|
|Operation|用户或管理员活动的名称。 此属性的值对应于在"活动"下拉列表 **中** 选定的值。 如果 **选择了"显示所有活动** 的结果"，则报告中将包含所有服务的所有用户和管理员活动的条目。 有关记录在 office 365 中的操作/活动审核日志，请参阅在 Office  365 中搜索 审核日志 中的["已审核的活动"选项卡](search-the-audit-log-in-security-and-compliance.md)。  <br/> 对于 Exchange 管理员活动，此属性标识已运行的 cmdlet 名称。|全部|
|OrganizationId|组织的 GUID。|全部|
|路径|访问的邮件所在的邮箱文件夹的名称。 此属性还标识创建邮件或将邮件复制/移动到的文件夹。|Exchange (邮箱活动) |
|参数|对于 Exchange 管理员活动，与 Operation 属性中标识的 cmdlet 一同使用的所有参数的名称和值。|Exchange (管理员活动) |
|RecordType|记录指示的操作类型。 此属性指示触发该操作的服务或功能。 有关记录类型及其对应的 ENUM 值列表 (这是审核记录中的 **RecordType** 属性) ，请参阅审核 [日志记录类型](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)。| 
|ResultStatus|指示在 Operation **(中指定的** 操作) 是否成功。  <br/> 对于 Exchange 管理员活动，值为 **True** (成功) **False** (失败) 。|全部  <br/>|
|SecurityComplianceCenterEventType|指示活动是安全中心&事件。 所有安全&合规中心活动的此属性的值为 **0。**|安全与合规中心|
|SharingType|分配给共享资源的用户的共享权限的类型。 此用户在 **UserSharedWith** 属性中标识。|SharePoint|
|Site|用户访问的文件或文件夹所在网站的 GUID。|SharePoint|
|SiteUrl|用户访问的文件或文件夹所在网站的 URL。|SharePoint|
|SourceFileExtension|用户访问的文件的文件扩展名。 如果访问对象是一个文件夹，则此属性为空。|SharePoint|
|SourceFileName|用户访问的文件或文件夹名称。|SharePoint|
|SourceRelativeUrl|包含用户访问文件的文件夹的 URL。 **SiteURL、SourceRelativeURL** 和 **SourceFileName** 属性的值的组合与 ObjectID 属性的值相同 **，ObjectID** 属性的值是用户访问的文件的完整路径名。|SharePoint|
|主题|访问的邮件的主题行。|Exchange (邮箱活动) |
|TabType| 在团队中添加、删除或更新的选项卡类型。 此属性的可能值为：  <br/><br/> **Excel 固定** - Excel 选项卡。  <br/> **扩展** - 所有第一方和第三方应用;如课堂计划、VSTS 和窗体。  <br/> **备注** - OneNote 选项卡。  <br/> **Pdfpin** - PDF 选项卡。  <br/> **Powerbi** - Power BI 选项卡。  <br/> **Powerpointpin** - PowerPoint 选项卡。  <br/> **Sharepointfiles** - SharePoint 选项卡。  <br/> **网页** - 固定的网站选项卡。  <br/> **Wiki 选项卡** - Wiki 选项卡。  <br/> **Wordpin** - Word 选项卡。|Microsoft Teams|
|Target|在 Operation 属性 **(标识的用户**) 操作。 例如，如果将来宾用户添加到 SharePoint 或 Microsoft 团队，则此属性中将列出该用户。|Azure Active Directory|
|TeamGuid|Microsoft Teams 中团队的 ID。|Microsoft Teams|
|TeamName|Microsoft Teams 中的团队名称。|Microsoft Teams|
|UserAgent|有关用户浏览器的信息。 此信息由浏览器提供。|SharePoint|
|UserDomain|有关执行该操作的用户或 () 租户组织的标识信息。|Azure Active Directory|
|UserID|执行该操作的用户 (**Operation** 属性) 记录的记录。 审核由系统帐户执行的活动记录 (例如 SHAREPOINT\system 或 NT AUTHORITY\SYSTEM) 也包含在审核日志。 UserId 属性的另一个常见值是 app@sharepoint。 这表明执行活动的“用户”是在 SharePoint 中拥有必要权限的应用程序，代表用户、管理员或服务执行组织范围内操作（例如，搜索 SharePoint 网站或 OneDrive 帐户）。 有关详细信息，请参阅[审核记录中的 app\@sharepoint 用户](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records)。 |全部|
|UserKey|UserID 属性中标识的用户的备用 **ID。** 例如，对于用户在 SharePoint 中执行的 (PUID) 填充此属性。 对于系统帐户执行的其他服务和事件，此属性也可能指定与 **UserID** 属性相同的值。|全部|
|UserSharedWith|与之共享资源的用户。 如果 Operation 属性的值为 **SharingSet** **，则包含** 此属性。 此用户也列在报表的 **"共享** 对象"列中。|SharePoint|
|UserType|执行操作的用户类型。 以下值指示用户类型。 <br/> <br/> **0** - 常规用户。 <br/>**2** - Microsoft 365 组织的管理员。<sup>1</sup> <br/>**3** - Microsoft 数据中心管理员或数据中心系统帐户。 <br/>**4** - 系统帐户。 <br/>**5** - 应用程序。 <br/>**6** - 服务主体。<br/>**7** - 自定义策略。<br/>**8** - 系统策略。|全部|
|版本|指示由记录的 Operation (标识的活动) 版本号。 |全部|
|Workload|发生活动的 Microsoft 365 服务。|全部|
||||

> [!NOTE]
><sup>1</sup> 对于与 Azure Active Directory 相关的事件，管理员的值不在审核记录中使用。 管理员执行的活动的审核记录将指示常规用户 (例如 **UserType： 0**) 执行了活动。 **UserID** 属性将标识 (常规用户或) 管理员的用户。<br/>

当您在查看特定事件的详细信息时单击 **"详细信息"** 时，也会显示上述属性。
  
![单击“详细信息”，查看审核日志事件记录的详细属性](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)