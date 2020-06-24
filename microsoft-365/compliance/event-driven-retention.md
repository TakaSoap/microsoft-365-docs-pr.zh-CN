---
title: 事件驱动保留概述
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: 通常，它是记录管理解决方案的一部分，你可以配置保留标签以根据所识别的事件开始保留期。
ms.openlocfilehash: 1e716cc886e8378308054d4f2eedf961045f4486
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817801"
---
# <a name="overview-of-event-driven-retention"></a>事件驱动保留概述

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them. But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.
  
例如，可对以下事件结合使用标签和事件驱动保留：
  
- **Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization. After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed. The event that triggers the 10-year retention period is the employee leaving the organization. 
    
- **Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract. 
    
- **Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period. 
    
Event-driven retention is typically used as part of a records-management process. This means that:
  
- Labels based on events also usually classify content as a record. For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).
    
- 如果文档已声明为记录，但其触发事件尚未发生，那么文档会无限期保留（因为无法永久删除记录），直到触发文档保留期的事件发生。
    
- Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content. For more information, see [Disposition of content](disposition.md).
    
基于事件的标签与 Microsoft 365 中的任何保留标签具有相同的功能。 有关详细信息，请参阅[了解保留标签](labels.md)。

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>了解事件类型、标签、事件和资产 ID 之间的关系

为了成功使用事件驱动保留，请务必了解事件类型、保留标签、事件和资产 ID 之间的关系，如下图以及随后的说明所示： 
  
![事件类型、标签、事件和资产 ID 的关系图](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![事件类型、标签、事件和资产 ID 的关系图](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. 为不同类型的内容创建保留标签，然后将其与事件类型相关联。 例如，不同类型的产品文件和记录的保留标签与“产品生存期”事件类型相关联，因为必须将这些记录自产品生存期结束起保留 10 年。
    
2. 用户（通常是记录管理人员）将这些保留标签应用于内容，并（对于 SharePoint 和 OneDrive 文档）为每一项输入资产 ID。 在此示例中，资产 ID 是组织使用的产品名称或代码。 因此，每个产品的记录都分配有一个保留标签，且每个记录都有包含资产 ID 的属性。 上图表示组织中所有产品记录的**全部内容**，且每一项都有记录所属产品的资产 ID。 
    
3. Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:
    
  - 资产 ID（对于 SharePoint 和 OneDrive 文档）
    
  - Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.
    
  - The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.
    
4. 在你创建事件后，相应事件日期就会同步到符合以下条件的所有内容：具有相应事件类型的保留标签，且包含指定的资产 ID 或关键字。 与任何保留标签一样，这种同步最长可能需要 7 天才能完成。 在上图中，所有用红色圈起来的项的保留期都是由此事件触发的。 换言之，当此产品的生存期结束时，相应事件就会触发此产品的记录的保留期。
    
请务必注意，如果没有为事件指定资产 ID 或关键字，则具有该事件类型标签的**所有内容**均由该事件触发保留期。 也就是说，在上图中，所有内容将开始被保留。 这可能并非如你所愿。 
  
最后，请注意，每个保留标签都有自己的保留设置。 在此示例中，它们全都指定保留 10 年，但事件也可触发保留期不同的各个保留标签。
  
## <a name="how-to-set-up-event-driven-retention"></a>如何设置事件驱动保留

事件驱动保留的工作流概览：
  
![事件驱动保留的设置工作流的关系图](../media/event-based-retention-process.png)
  
> [!TIP]
> 有关使用 SharePont 中的托管属性来自动应用保留标签并实施事件驱动保留的详细方案，请参阅[使用保留标签管理 SharePoint 文档的生命周期](auto-apply-retention-labels-scenario.md)。

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>第 1 步：创建保留期以事件为依据的标签

在 Microsoft 365 合规中心的左侧导航中，选择“**信息治理**” > “**标签**” > “**创建标签**”。 如果“**信息治理**”未显示在导航窗格中，请向下滚动并选择“**全部显示**”。
  
When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event. This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page. 
  
请注意，事件驱动保留通常用于分类为记录的内容。 因此，创建基于事件的保留标签时，通常需要选择“使用标签将内容分类为‘记录’”**** 选项。
  
另请注意，事件驱动保留要求保留设置必须：
  
- 保留内容。
    
- 在保留期到期时自动删除内容或触发处置评审。
    
![让标签基于事件的选项](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a>第 2 步：选择与此标签关联的事件类型

在标签设置中，选择将标签基于**事件**的选项后，将看到“**选择事件类型**”选项。 事件类型就是对要将标签与之相关联的事件的一般说明。
  
例如，如果创建“产品生存期”事件类型，将创建基于事件的保留标签，标签名称描述了要将标签应用于什么类型的内容（如“产品开发文件”或“产品业务决策记录”）。
  
请注意，一旦选择事件类型和创建保留标签后，便无法再更改事件类型。
  
![用于创建或选择事件类型的选项](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>第 3 步：发布或自动应用基于事件的保留标签

与任何保留标签类似，需要[发布或自动应用](create-retention-labels.md)基于事件的标签，以便将其手动或自动应用到内容。

> [!NOTE]
> 如果从“**记录管理**” > “**文件计划**”选项卡或“**数据管理**” > “**标签**”选项卡中选择事件驱动的保留标签，“**自动应用标签**”按钮将不可用。
> 
> 请使用以下位置之一的标签或策略列表上方的“**自动应用标签**”选项来代替此按钮：
> - “**记录管理**” > “**标签策略**”选项卡
> - “**数据管理**” > “**标签**”选项卡或“**标签策略**”选项卡


![用于发布或自动应用保留标签的选项](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a>第 4 步：输入资产 ID

After an event-driven label is applied to content, you can enter an asset ID for each item. For example, your organization might use:
  
- 产品代码：可用于仅保留特定产品的内容。
    
- 项目代码：可用于仅保留特定项目的内容。
    
- 员工 ID：可用于仅保留特定人员的内容。
    
请务必理解，资产 ID 只是 SharePoint 和 OneDrive for Business 中的另一种文档属性。 你的组织可能已经使用其他文档属性和 ID 来分类内容。 如果是这样，还可以在创建事件时使用这些属性和值（请参见后面的第 6 步）。 请务必注意，组织必须在文档属性中使用某种属性:值组合，将相应项与事件类型相关联。
  
![用于输入资产 ID 的文本框](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>第 5 步：创建事件

When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event. You need to manually trigger an event by creating it.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>第 6 步：选择第 2 步中标签使用的相同事件类型

创建事件时，请选择第 2 步中的保留标签所使用的相同事件类型，如“产品生存期”。 只有具有相应事件类型的保留标签的内容，才会触发保留期。
  
![“事件设置”中用于选择事件类型的选项](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>第 7 步：输入关键字或资产 ID

Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content. For asset IDs, retention will be enforced only on content with the specified property:value pair. If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them. 
  
请务必理解，资产 ID 只是 SharePoint 和 OneDrive for Business 中的另一种文档属性。 如果使用的是资产 ID 属性，需在下方所示的资产 ID 框中输入 ComplianceAssetID:\<value\>。
  
Your organization might have applied other properties and IDs to the documents related to this event type. For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ". In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.
  
For Exchange items, you can include keywords. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
  
最后，选择事件发生日期；此日期用作保留期的开始日期。 创建事件后，相应事件日期就会同步到所有具有相应事件类型的保留标签、资产 ID 和关键字的内容。 与任何保留标签一样，这种同步最长可能需要 7 天才能完成。
  
![“事件设置”页](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>使用内容搜索来查找所有包含特定标签或资产 ID 的内容

在保留标签分配到内容后，可通过内容搜索，查找所有已使用特定保留标签进行分类或包含特定资产 ID 的内容。
  
创建内容搜索后：
  
- 若要查找所有包含特定保留标签的内容，请选择“合规性标记”**** 条件，再输入完整或部分标签名称并使用通配符。 
    
- 要查找所有包含特定资产 ID 的内容，请输入 **ComplianceAssetID** 属性和值，如 ComplianceAssetID:\<value\>。 
    
有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。
  
## <a name="permissions"></a>权限

To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group. 
  
有关详细信息，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
  
## <a name="automate-events-by-using-powershell"></a>使用 PowerShell 自动触发事件

In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs. However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).

此外，还可使用 PowerShell 脚本从业务应用程序中自动执行基于事件的保留。 适用于事件驱动保留的 PowerShell cmdlet：
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

