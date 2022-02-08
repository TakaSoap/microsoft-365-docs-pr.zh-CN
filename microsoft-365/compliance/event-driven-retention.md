---
title: 从事件发生时开始计算保留期
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
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
ms.openlocfilehash: c4195f7e5a859cf5a1078566728be5b8567cf5b9
ms.sourcegitcommit: 954c8af658adb270fe843991e048c6a30e86e77c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2022
ms.locfileid: "62428921"
---
# <a name="start-retention-when-an-event-occurs"></a>从事件发生时开始计算保留期

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

如果你保留内容，保留期通常是以内容年限为依据。例如，可以先将文档自创建起保留 7 年，再删除它们。不过配置[保留标签](retention.md#retention-labels)时，还能让保留期以特定类型事件何时发生为依据。也就是说，事件触发开始计算保留期，并对所有包含针对相应事件类型应用的保留标签的内容强制执行标签的保留操作。
  
使用基于事件的保留的示例：
  
- **员工即将离开组织**：假设必须自员工离开组织起将员工记录保留 10 年。10 年之后，必须处置所有与离职员工的聘用、绩效、解雇有关的文档。触发 10 年保留期的事件是员工离开组织。 
    
- **合同到期**：假设必须将与合同相关的所有记录自合同到期起保留 5 年。触发 5 年保留期的事件是合同到期。 
    
- **产品生存期**：组织可能会对技术规范等内容规定与产品最后生产日期相关的保留要求。在这种情况下，触发保留期的事件是最后生产日期。 
    
基于事件的保留通常用于记录管理流程。也就是说：
  
- 基于事件的保留标签通常还会将项目标记为记录，作为记录管理解决方案的一部分。有关详细信息，请参阅[了解记录管理](records-management.md)。

- 如果文档已被声明成记录，但其触发事件尚未发生，那么文档会无限期保留（因为无法永久删除记录），直到触发文档保留期的事件发生。
    
- 基于事件的保留标签通常会在保留期到期时触发处置评审，这样记录管理者便能手动评审和处置内容。有关详细信息，请参阅[处置内容](disposition.md)。
    

基于事件的保留标签具有与 Microsoft 365 中的任何保留标签相同的功能。有关详细信息，请参阅[了解保留策略和保留标签](retention.md)。

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>了解事件类型、标签、事件和资产 ID 之间的关系

为了成功使用基于事件的保留，请务必了解事件类型、保留标签、事件和资产 ID 之间的关系，如下图以及随后的说明所示： 
  
![图 1（共 2 张图）：事件类型、标签、事件和资产 ID 的关系图。](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![图 2（共 2 张图）：事件类型、标签、事件和资产 ID 的关系图。](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. 为不同类型的内容创建保留标签，然后将它们与事件类型相关联。例如，不同类型的产品文件和记录的保留标签与名为“产品生命周期”的事件类型相关联，因为必须将这些记录自产品生命周期结束起保留 10 年。
    
2. 用户（通常为记录管理者）将这些保留标签应用于内容，并（对 SharePoint 和 OneDrive 中的文档）输入每项的资产 ID。在本示例中，资产 ID 是产品名称或组织使用的代码。然后，每个产品的记录都分配有保留标签，且每条记录都有一个包含资产 ID 的属性。此关系图表示组织的所有产品记录的 **全部内容**，且每项都有记录所属产品的资产 ID。 
    
3. 事件类型是“产品生存期”，即事件是特定产品的生存期结束。当相应事件类型的事件（在本示例中，为产品生存期结束）发生时，创建指定以下信息的事件：
    
   - 资产 ID（对于 SharePoint 和 OneDrive 文档）
    
   - 关键字（对于 Exchange 项）。在本示例中，组织在包含产品记录的邮件中使用产品代码，因此 Exchange 项的关键字与 SharePoint 和 OneDrive 文档的资产 ID 在功能上来说是相同的。
    
   - 事件发生日期。此日期用作保留期的开始日期。该日期可以是当前日期、过去日期或未来日期。

4. 创建事件后，该事件日期将同步到具有该事件类型保留标签且包含指定资产 ID 或关键字的所有内容。与任何保留标签一样，此同步可能需要长达七天的时间。在上图中，红色圈出的所有项目的保留期均由此事件触发。换言之，当此产品的生命周期结束时，该事件将触发该产品记录的保留期。

请务必了解，如果没有为事件指定资产 ID 或关键字，那么包含与相应事件类型相关的保留标签的 **所有内容** 的保留期都会由此事件触发。也就是说，在之前关系图中，将会开始保留所有内容。这可能并不符合你的预期。

最后，请记住，每个保留标签都有自己的保留设置。在此示例中，它们都指定了 10 年，但事件可能会触发保留标签，其中每个标签的保留期都不同。
  
## <a name="how-to-set-up-event-driven-retention"></a>如何设置事件驱动保留

事件驱动保留的工作流概览：
  
![事件驱动保留的设置工作流的关系图。](../media/event-based-retention-process.png)
  
> [!TIP]
> 有关使用 SharePont 中的托管属性来自动应用保留标签并实现事件驱动保留的详细方案，请参阅[使用保留标签管理 SharePoint 中存储的文档的生命周期](auto-apply-retention-labels-scenario.md)。

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>第 1 步：创建保留期以事件为依据的标签

若要创建和配置保留标签，请参阅[创建记录管理的保留标签](file-plan-manager.md#create-retention-labels)说明，或[如何为信息管理创建保留标签](create-retention-labels-information-governance.md)。 但特定于基于事件的保留，在创建保留标签时 **定义保留设置** 页上，在 **基于开始保留期** 后，从下拉列表中选择一个默认事件类型，或者通过选择 **创建新事件类型**，创建自己的事件类型：

![为保留标签创建新事件类型。](../media/SPRetention6.png)

事件类型就是对要将标签与之相关联的事件的一般说明。

在下拉列表中的名称后面，默认事件类型都会有 **（事件类型）**，以便更轻松地标识，你还可以从“**记录管理**” > “**事件**”选项卡 > “**管理事件类型**” 那里查看和创建事件类型。

基于事件的保留要求保留设置：
  
- 保留内容。
    
- 在保留期到期时自动删除内容或触发处置评审。
  
基于事件的保留通常用于声明为记录的内容，因此这是检查是否还需要选择将内容标记为[记录](records-management.md#records)的选项的好时机。

如果你使用的是现有事件类型，而不是创建新的事件类型，请跳到第 3 步。

> [!NOTE]
> 选择事件类型并保存保留标签后，便无法再更改事件类型。

### <a name="step-2-create-a-new-event-type-for-your-label"></a>第 2 步：为标签创建新事件类型

对于保留设置，如果已选择“**创建新事件类型**”，那就输入事件类型的名称和说明。 然后选择 “**下一步**”、“**提交**”和“**完成**”。

返回到“**定义保留设置**”页面， 针对“**启动保留期，基于：**”一项，请使用下拉列表选择所创建的事件类型。

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>第 3 步：发布或自动应用基于事件的保留标签

与任何保留标签一样，需要发布或自动应用基于事件的标签，以便将它手动或自动应用于内容：
- [创建保留标签并在应用中应用它们](create-apply-retention-labels.md)
- [自动向内容应用保留标签](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a>第 4 步：输入资产 ID

在基于事件的标签应用于内容后，可以输入每个项目的资产 ID。例如，组织可能会使用：
  
- 产品代码：可用于仅保留特定产品的内容。
    
- 项目代码：可用于仅保留特定项目的内容。
    
- 员工 ID：可用于仅保留特定人员的内容。
    
“资产 ID”就是 SharePoint 和 OneDrive 中可用的另一种文档属性。你的组织可能已使用其他文档属性和 ID 来分类内容。如果是这样，也可以在创建事件时使用这些属性和值（请参阅下面的第 6 步）。重要的是，你必须在文档属性中使用一些 *属性:值* 的组合，以便关联相应项和事件类型。
  
![用于输入资产 ID 的文本框。](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>第 5 步：创建事件

当相应事件类型的特定实例（例如，产品的生存期结束）发生时，请转到 Microsoft 365 合规中心内的“**记录管理**” > “**事件**”页，并选择 “**+ 创建**”来创建事件。你通过在此创建事件来触发它。

![创建事件以便为基于事件的保留标签启动保留。](../media/create-event-records-management.png)

每个租户支持多达一百万个事件。

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>第 6 步：选择第 2 步中标签使用的相同事件类型

创建事件时，请选择第 2 步中的保留标签设置所指定的相同事件类型。 例如，如果你选择了“**产品生命周期**”作为标签设置的事件类型，请在创建事件时选择“**产品生命周期**”。 只有具有相应事件类型的保留标签的内容，才会触发保留期。

![“事件设置”中用于选择事件类型的选项。](../media/choose-event-type-records-management.png)

或者，如果需要为具有不同事件类型的多个保留标签创建事件，请选择“**选择现有标签**”选项。 然后，选择想要与此事件相关联的事件类型所配置的标签。

### <a name="step-7-enter-keywords-or-query-for-exchange-asset-id-for-sharepoint-and-onedrive"></a>步骤 7：对于 Exchange 输入关键字或查询，对于 SharePoint 和 OneDrive 输入资产 ID

现在缩小内容的范围。 对于 Exchange 内容，可通过指定关键字或查询来执行此操作。 对于 SharePoint 和 OneDrive 内容，可通过指定资产 ID 来执行此操作。

对于 Exchange 项目，使用关键字或采用关键字查询语言 (KQL) 的查询。 有关查询语法的详细信息，请参阅[关键字查询语言 (KQL) 语法参考](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。 有关可用于 Exchange 的可搜索属性的详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。

对于资产 ID，仅对具有指定 *属性:值* 对的内容执行保留。 例如，如果使用的是资产 ID 属性，请在框中对下图所示的资产 ID 输入 `ComplianceAssetID:<value>`。

如果未输入资产 ID，具有该事件类型标签的所有内容都将应用相同的保留日期。

组织可能已向与此事件类型相关的文档应用其他属性和 ID。例如，如果你需要检测特定产品的记录，那么 ID 可能是自定义属性 ProductID 和值“XYZ”的组合。在这种情况下，应在下方显示的图片中的资产 ID 框中输入 `ProductID:XYZ`。

最后，选择事件发生的日期；此日期用作保留期的开始日期。创建事件后，该事件日期将同步到具有该事件类型、资产 ID 和关键字或查询的保留标签的所有内容。与任何保留标签一样，此同步可能需要长达七天的时间。
  
![“事件设置”页。](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

创建事件后，保留设置将对已标记和索引的内容生效。 如果创建事件后将保留标签添加到新内容，则必须创建具有相同详细信息的新事件。

删除事件不会取消现在对内容生效的保留设置。 目前，无法在触发事件后取消事件。

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>使用内容搜索来查找所有包含特定标签或资产 ID 的内容

在保留标签分配到内容后，可通过内容搜索，查找所有已使用特定保留标签进行分类或包含特定资产 ID 的内容：
  
- 若要查找所有包含特定保留标签的内容，请选择“**保留标签**”条件，再输入完整或部分标签名称并使用通配符。 
    
- 要查找所有包含特定资产 ID 的内容，请使用格式 `ComplianceAssetID:<value>`，输入 **ComplianceAssetID** 属性和值。 
    
有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。

## <a name="automate-events-by-using-powershell"></a>使用 PowerShell 自动触发事件

可以使用 PowerShell 脚本从业务应用程序中自动执行基于事件的保留。 适用于基于事件的保留的 PowerShell cmdlet：
  
- [Get-ComplianceRetentionEventType](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [New-ComplianceRetentionEventType](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [Remove-ComplianceRetentionEventType](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [Set-ComplianceRetentionEventType](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [Get-ComplianceRetentionEvent](/powershell/module/exchange/get-complianceretentionevent)
    
- [New-ComplianceRetentionEvent](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a>使用 REST API 自动触发事件

可使用 REST API 自动创建用于触发保留期开始的事件。

REST API 是一个支持多组 HTTP 操作（方法）的服务终结点，提供对服务资源的创建/检索/更新/删除操作权限。有关详细信息，请参阅 [REST API 请求/响应组件](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)。通过使用 Microsoft 365 REST API，可以使用 POST 和 GET 方法来创建和检索事件。

使用 REST API 有两种选择：

- **Microsoft Power Automate 或类似的应用程序**，可用于自动触发事件的发生。 Microsoft Power Automate 是一种用于连接其他系统的协调程序，你无需编写自定义解决方案。 有关详细信息，请参阅 [Power Automate 网站](https://flow.microsoft.com/en-us/)。

- **通过 PowerShell 或 HTTP 客户端调用 REST API**，可使用 PowerShell（版本 6 或更高版本）创建事件，它是自定义解决方案的一部分。

在使用 REST API 之前，请以全局管理员身份，确认要用于保留事件调用的 URL。 为此，请使用 REST API URL 运行 GET 保留事件调用：

```http
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

检查响应代码。如果是 302，则从响应标头的 Location 属性获取重定向 URL，并使用该 URL，而不是随后说明中的 `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`。

通过在 Microsoft 365 合规中心 >“**记录管理**” >  “**事件**”中进行查看，确认自动创建的事件。

### <a name="use-microsoft-power-automate-to-create-the-event"></a>使用 Microsoft Power Automate 创建事件

使用 Microsoft 365 REST API 创建用于创建事件的流：

![使用流创建事件。](../media/automate-event-driven-retention-flow-1.png)

![使用流调用 REST API。](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a>创建事件

用于调用 REST API 的示例代码：

- **方法**：POST
- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
- **标头**：键 = Content-Type，值 = application/atom+xml
- **正文**：

    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```

- **身份验证**: 基本
- **用户名**: "Complianceuser"
- **密码**: "Compliancepassword"


##### <a name="available-parameters"></a>可用参数


|参数|说明|注释|
|--- |--- |--- |
|<d:Name></d:Name>|为事件提供唯一的名称，|不能包含尾随空格或以下字符：% * \ & < \> \| # ? , : ;|
|<d:EventType></d:EventType>|输入事件类型名称（或 Guid），|示例：“雇佣终止”。事件类型必须与保留标签相关联。|
|<d:SharePointAssetIdQuery></d:SharePointAssetIdQuery>|输入“ComplianceAssetId:” + 员工 ID|示例："ComplianceAssetId:12345"|
|<d:EventDateTime></d:EventDateTime>|事件日期和时间|格式：yyyy-MM-ddTHH:mm:ssZ，示例：2018-12-01T00:00:00Z
|

###### <a name="response-codes"></a>响应代码

| 响应代码 | 说明       |
| ----------------- | --------------------- |
| 302               | 重定向              |
| 201               | 已创建               |
| 403               | 授权失败  |
| 401               | 身份验证失败 |

##### <a name="get-events-based-on-a-time-range"></a>根据时间范围获取事件

- **方法**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`

- **标头**：键 = Content-Type，值 = application/atom+xml

- **身份验证**: 基本

- **用户名**: "Complianceuser"

- **密码**: "Compliancepassword"

###### <a name="response-codes"></a>响应代码

| 响应代码 | 说明                   |
| ----------------- | --------------------------------- |
| 200               | 正常，atom+ xml 中的事件列表 |
| 404               | 未找到                         |
| 302               | 重定向                          |
| 401               | 授权失败              |
| 403               | 身份验证失败             |

##### <a name="get-an-event-by-id"></a>按 ID 获取事件。

- **方法**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`

- **标头**：键 = Content-Type，值 = application/atom+xml

- **身份验证**: 基本

- **用户名**: "Complianceuser"

- **密码**: "Compliancepassword"

###### <a name="response-codes"></a>响应代码

| 响应代码 | 说明                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 正常，响应正文包含 atom+xml 中的事件 |
| 404               | 未找到                                            |
| 302               | 重定向                                             |
| 401               | 授权失败                                 |
| 403               | 身份验证失败                                |

##### <a name="get-an-event-by-name"></a>按名称获取事件

- **方法**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`

- **标头**：键 = Content-Type，值 = application/atom+xml

- **身份验证**: 基本

- **用户名**: "Complianceuser"

- **密码**: "Compliancepassword"

###### <a name="response-codes"></a>响应代码

| 响应代码 | 说明                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 正常，响应正文包含 atom+xml 中的事件 |
| 404               | 未找到                                            |
| 302               | 重定向                                             |
| 401               | 授权失败                                 |
| 403               | 身份验证失败                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a>使用 PowerShell 或任何 HTTP 客户端创建事件

PowerShell 必须是版本 6 或更高版本。

在 PowerShell 会话中，运行以下脚本：

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *
```
