---
title: 在审核日志中使用共享审核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 管理员可以了解如何在组织中使用共享审核Microsoft 365 审核日志标识与组织外部的用户共享的资源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff05b655617608332b4b838e07a6af55e8b4d010
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193167"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>在审核日志中使用共享审核

共享是 SharePoint Online 和 OneDrive for Business中的一项关键活动，在组织中广泛使用。 管理员可以使用共享审核功能审核日志确定如何在组织中使用共享。 
  
## <a name="the-sharepoint-sharing-schema"></a>SharePoint共享架构

共享事件 (不包括与共享策略和共享链接) 相关的事件，主要方式与文件和文件夹相关的事件不同：一个用户正在执行对其他用户有影响的操作。 例如，当资源用户 A 向用户 B 授予对文件的访问权限时。 本示例中，用户 A 是  *操作用户，*  用户 B 是  *目标用户*。 在SharePoint文件架构中，操作用户的操作仅影响文件本身。 当用户 A 打开文件时 **，FileAccessed** 事件所需的唯一信息是操作用户。 为了消除此差异，有一个单独的架构，称为"共享 *SharePoint，* 用于捕获有关共享事件的信息。 这将确保管理员能够查看共享资源的用户和共享资源的用户。 
  
共享架构在审核记录中提供两个与共享事件相关的其他字段： 
  
- **TargetUserOrGroupType：** 标识目标用户或组是成员、来宾、SharePointGroup、SecurityGroup 还是合作伙伴。

- **TargetUserOrGroupName：** 存储上一示例中与用户 B (共享资源的目标用户或组的 UPN 或) 。 

这两个字段以及 审核日志 架构中的其他属性（如 User、Operation 和 Date）可以完整描述哪个用户与谁共享了哪个资源以及何时 *共享*。 
  
还有一个对共享情景非常重要的架构属性。 当您导出审核日志时，导出的 CSV 文件的 **AuditData** 列将存储有关共享事件的信息。 例如，当用户与其他用户共享网站时，这是通过将目标用户添加到用户组SharePoint实现。 **AuditData** 列捕获此信息以向管理员提供上下文。 有关如何分析 **AuditData** 列中的信息的说明，请参阅步骤 [2。](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log)

## <a name="sharepoint-sharing-events"></a>SharePoint共享事件

共享的定义如下：当 (用户希望与) 用户共享资源时 (*用户* 共享) 。 与与外部用户共享资源相关的审核记录 (组织外部且在组织的 Azure Active Directory) 中没有来宾帐户的用户由以下事件标识，这些事件记录在 审核日志：

- **SharingInvitationCreated：** 您组织的用户尝试与外部用户 (网站) 共享资源。 这导致向目标用户发送外部共享邀请。 此时，不授予对资源的访问权限。

- **SharingInvitationAccepted：** 外部用户已接受操作用户发送的共享邀请，现在可以访问资源。

- **AnonymousLinkCreated：** 为资源 (匿名链接) "任何人"链接。 由于可创建并复制匿名链接，因此可以合理假定任何具有匿名链接的文档已与目标用户共享。

- **AnonymousLinkUsed：** 如名称所示，使用匿名链接访问资源时将记录此事件。 

- **SecureLinkCreated：** 用户已创建"特定人员链接"，以与特定人员共享资源。 此目标用户可能是组织外部的用户。 与资源共享的人在 **AddedToSecureLink** 事件的审核记录中标识。 这两个事件的时间戳几乎完全相同。

- **AddedToSecureLink：** 用户已添加到特定人员链接。 使用 **此事件中的 TargetUserOrGroupName** 字段可标识添加到相应特定人员链接的用户。 此目标用户可能是组织外部的用户。

## <a name="sharing-auditing-work-flow"></a>共享审核工作流程
  
当用户 (代理用户) 想要与其他用户共享资源 (目标用户) 、SharePoint (或 OneDrive for Business) 将首先检查目标用户的电子邮件地址是否已与组织目录中的用户帐户关联。 如果目标用户位于目录 (并且具有相应的来宾用户帐户) ，SharePoint执行以下操作：
  
-  通过将目标用户添加到相应的组，立即向目标用户分配访问资源SharePoint，并记录 **AddedToGroup** 事件。 
    
- 向目标用户的电子邮件地址发送共享通知。
    
- 记录 **SharingSet** 事件。 此事件在搜索工具的活动选取器中的"共享和访问请求活动"下具有友好名称"共享文件、文件夹审核日志网站"。 请参阅步骤 [1 中的屏幕截图](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)。 
    
如果目标用户的用户帐户不在目录中，则SharePoint执行以下操作： 
    
   - 根据资源的共享方法，记录以下事件之一：
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (仅在共享资源是网站集时记录此事件) 
    
   - 当目标用户通过单击邀请) 中的链接接受发送给 (的共享邀请时，SharePoint 将记录 **SharingInvitationAccepted** 事件并分配目标用户访问资源的权限。 如果向目标用户发送匿名链接，则目标用户使用该链接访问资源后，将记录 **AnonymousLinkUsed** 事件。 对于安全链接，当外部用户使用链接访问资源时，将记录 **FileAccessed** 事件。

还会记录有关目标用户的其他信息，例如邀请的目标用户标识以及接受邀请的用户。 在某些情况下，这些用户 (电子邮件地址) 可能会有所不同。 

## <a name="how-to-identify-resources-shared-with-external-users"></a>如何标识与外部用户共享的资源

管理员的一个常见要求是创建已与组织外部的用户共享的所有资源的列表。 通过使用共享审核Office 365，管理员可以生成此列表。 方法如下：
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>步骤 1：搜索共享事件，将结果导出到 CSV 文件

第一步是搜索审核日志共享事件。 有关详细信息， (包括搜索) 所需的权限审核日志， [请参阅搜索](search-the-audit-log-in-security-and-compliance.md)审核日志。
  
1. 转到 <https://compliance.microsoft.com>。

2. 使用工作或学校帐户进行登录。

3. 在 Microsoft 365 合规中心的左窗格中，单击“**审核**”。

    将显示“**审核**”页。

4. 在 **"活动**" **下，单击"共享和访问请求活动** "以搜索与共享相关的事件。 

    ![在"活动"下，选择"共享和访问请求活动"。](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5. 选择日期和时间范围以查找该时段内发生的共享事件。 

6. 单击 **"** 搜索"运行搜索。 

7. 运行完搜索并显示结果后，单击"**导出** 结果 \> **下载所有结果"。**

    选择导出选项后，窗口底部会显示一条消息，提示您打开或保存 CSV 文件。

8. 单击 **"** \> **另存为** "，将 CSV 文件保存到本地计算机上的文件夹中。 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>步骤 2：使用 PowerQuery 编辑器格式化导出审核日志

下一步是使用 Excel 中 Power Query Editor 中的 JSON 转换功能将 **AuditData** 列 (（由多属性 JSON 对象) 组成的每个属性）拆分为其自己的列。 这允许您筛选列以查看与共享相关的记录

有关分步说明，请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的“步骤 2：使用 Power Query 编辑器转换 JSON 对象”。

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>步骤 3：筛选 CSV 文件以搜索与外部用户共享的资源

下一步是筛选 CSV，以筛选之前在"共享事件"部分SharePoint[与共享相关的事件](#sharepoint-sharing-events)。 或者，可以筛选 **TargetUserOrGroupType** 列以显示此属性的值为 Guest 的所有 **记录**。 

按照上一步中的说明使用 PowerQuery 编辑器准备 CSV 文件后，执行以下操作：
    
1. 打开Excel 2 中创建的配置文件。 

2. 在"**主页"** 选项卡上，单击"排序&**筛选器"，** 然后单击"筛选器 **"。**
    
3. 在"**操作&** 的"排序筛选器"下拉列表中，清除所有选择，然后选择一个或多个以下与共享相关的事件，然后单击"确定 **"。**
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel显示所选事件的行。
    
4. 转到名为 **TargetUserOrGroupType 的列** 并选择它。 
    
5. 在"**排序&筛选器**"下拉列表中，清除所有选择，然后选择 **"TargetUserOrGroupType：Guest"，** 然后单击"确定 **"。**
    
    现在Excel显示共享事件的行以及目标用户位于组织外部的行，因为外部用户由 **值 TargetUserOrGroupType：Guest** 标识。 
  
> [!TIP]
> 对于显示的审核记录 **，ObjectId** 列标识与目标用户共享的资源;例如  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` 。
