---
title: 使用保留标签管理存储在 SharePoint Online 中的产品文档的生命周期
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 此解决方案说明了如何使用 Office 365 保留标签管理存储在 SharePoint Online 中的产品相关文档的生命周期。 可通过使用文档元数据对内容进行分类来完成此操作，具体方法是自动应用 Office 365 保留标签并配置基于事件的保留。
ms.openlocfilehash: aa73feecbfaa830b2297a5c64f653c4da4d4b325
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079347"
---
# <a name="manage-the-lifecycle-of-sharepoint-documents-with-retention-labels"></a>使用保留标签管理 SharePoint 文档的生命周期

本文介绍如何通过使用 Office 365 保留标签管理存储在 SharePoint Online 中的产品相关文档的生命周期，具体方法是自动应用标签并配置基于事件的保留。 自动应用功能通过使用 SharePoint 元数据来利用文档分类。 本文中的方案基于与产品相关的文档，但是相同的概念也可以用于其他方案。 例如，在石油和天然气行业，可以管理与石油平台、钻井日志或生产许可证等实物资产相关的文档的生命周期。 在金融服务行业，你可以管理与银行账户、抵押或保险合同相关的文档。 在公共部门，你可以管理与施工许可证或纳税表相关的文档。

让我们看一下本文中的方案。 我们将探讨信息体系结构和保留标签的定义。 然后，我们将通过自动应用标签对文档进行分类，最后生成用于触发保留期的事件。

## <a name="information-architecture"></a>信息体系结构

本文中的方案基于一家制造公司，它使用 Office 365 SharePoint Online 来存储与公司开发的产品相关的所有文档。 这些文档包括产品规范、与供应商签订的协议以及用户手册。 将这些文档作为企业内容管理策略的一部分存储在 SharePoint 中时，需要定义文档元数据并将其用于分类。 每个文档都具有以下元数据属性：

- **文档类型**（例如产品规范、协议和用户手册）

- **产品名称**

- **状态**（草稿或终稿）

此元数据形成所有文档的基本内容类型，它称为**生产文档**。

![产品文档元数据](../media/SPRetention1.png)

> [!NOTE]
> 在方案的后面部分中，保留策略将使用**文档类型**和**状态**属性进行分类并自动应用保留标签。

我们可以拥有几种表示不同类型文档的内容类型，但我们将重点介绍产品文档。

在此方案中，我们使用托管元数据服务和术语库为**文档类型**创建一个术语集，并为**产品名称**创建另一个术语集。 对于每个术语集，我们将为每个值创建一个术语。 在 SharePoint 组织的术语库中，它看起来类似于以下示例：

![术语库中的产品文档术语集](../media/SPRetention2.png)

可以使用[内容类型中心](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b)创建和发布内容类型。 也可以使用网站预配工具（例如 [PnP 预配框架](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-framework)或[网站设计 JSON 架构](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type)）创建和发布内容类型。

每个产品都有一个专用的 SharePoint Online 网站，其中包含一个文档库，并且已启用正确的内容类型。 所有文档都存储在此文档库中。

![产品文档库](../media/SPRetention3.png)

> [!NOTE]
> 在此方案中，制造公司可以为每个产品使用 Microsoft 团队以支持与团队成员的协作（例如持久聊天），而不是使每个产品都有一个 SharePoint Online 网站，它还可使用团队中的“**文件**”选项卡进行文档管理。 在本文中，我们只重点介绍文档，因此我们将只使用一个网站。

以下是旋转小组件产品的文档库视图：

![旋转小组件文档库](../media/SPRetention4.png)

现在，我们拥有用于文档管理的基本信息体系结构，下面让我们看一下使用元数据和文档分类的文档保留和处置策略。

## <a name="retention-and-disposition"></a>保留和处置

制造公司的合规性和数据管理策略规定了保存和处置数据的方式。 与产品相关的文档必须在产品生产期间保存，并在生产之后保存一段时间。 对于产品规范、协议和用户手册，此期限有所不同。 下表列出了保留和处置要求：

| **文档类型**          | **保留**                          | **处置**                              |
| -------------------------- | -------------------------------------- | -------------------------------------------- |
| 产品规范      | 产品停产后保留 5 年  | 删除                                       |
| 产品协议          | 产品停产后保留 10 年 | 审阅                                       |
| 用户手册                | 产品停产后保留 5 年  | 删除                                       |
| 所有其他类型的文档 | 不主动保留其他文档  | 文档超过 3 年时删除<sup>\*</sup>  |
|||

> [!NOTE]
> <sup>\*</sup> 如果文档在过去 3 年内未曾修改，则视为超过 3 年。

使用安全与合规中心，我们将创建以下保留标签：

  - 产品规范

  - 产品协议

  - 用户手册

在本文中，我们只介绍如何创建和自动应用产品规范保留标签。 若要实施完整方案，可创建并自动应用其他两种文档类型的保留标签。

### <a name="settings-for-the-product-specification-retention-label"></a>产品规范保留标签的设置

以下是产品规范保留标签的[文件计划](file-plan-manager.md)： 

- **名称：** 产品规范

- **管理员说明：** 产品规范标签，产品停产后保留五年，自动删除，基于事件的保留，事件类型为“产品停产”。

- **用户说明：** 在产品停产后保留五年。

- **保留操作：** 保留和删除

- **保留期：** 五年（1825 天）

- **记录标签：** 配置保留标签以将内容分类为[记录](labels.md#using-retention-labels-for-records-management)（用户无法修改或删除分类为记录的文档）

- **文件计划描述符：**（为简化方案，未提供文件描述符）

以下屏幕截图显示了在安全与合规中心内创建产品规范[保留标签](labels.md)时的设置。 创建保留标签时，可创建“**产品停产**”事件类型。 请参阅以下步骤。

![产品规标签保留设置](../media/SPRetention5.png)

> [!NOTE]
> 出于实用目的，为了避免需要等待 5 年才能看到自动删除的文档，如果要在测试环境中重新创建此方案，请将保留期设置为 1 天。

### <a name="create-an-event-type-when-creating-a-retention-label"></a>创建保留标签时创建事件类型

1. 在“**基于以下条件保留或删除内容**”下拉列表中，选择“**事件**”。

2. 选择“**选择事件类型**”。

   ![为产品规范标签新建事件类型](../media/SPRetention6.png)

3. 在“**选择事件类型**”页面上，选择“**你可以在此处创建新的事件类型**”。

4. 创建名为“**产品停产**”的事件类型，提供说明，然后选择“**完成**”以创建它。 

5. 返回到“**选择事件类型**”页面上，选择所创建的“**产品停产**”事件类型，然后选择“**添加**”。

以下是产品规范保留标签的设置的示例。 选择“**创建此标签**”以创建它。

![新产品规范标签设置](../media/SPRetention7.png)

> [!TIP]
> 有关更详细的步骤，请参阅[创建保留期基于事件的标签](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event)。

现已创建保留标签，让我们看一下如何将保留标签自动应用于产品规范内容。

## <a name="classifying-content-by-auto-applying-retention-labels"></a>通过自动应用保留标签对内容进行分类

我们将使用关键字查询语言 (KQL) [自动应用](labels.md#applying-a-retention-label-automatically-based-on-conditions)为此方案创建的保留标签。 KQL 是用于构建搜索查询的语言。 在 KQL 中，可使用关键字或托管属性进行搜索。 有关 KQL 的详细信息，请参阅 <https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference>

在较高级别中，我们希望告诉 Office 365 将**产品规范**保留标签应用于所有**状态**为“**终稿**”且**文档类型**为“**产品规范**”的文档。 请记住，**状态**和**文档类型**是我们先前在“[信息体系结构](#information-architecture)”部分中为产品文档内容类型定义的网站栏。 为了完成此操作，我们需要配置搜索架构。

当 SharePoint 为内容创建索引时，它将自动为每个网站栏生成已爬网属性。 对于此方案，我们对**文档类型**和**状态**属性感兴趣。 对于库中的文档，需要使用正确的内容类型，并填写网站栏，以便搜索并创建已爬网属性。

在 SharePoint 管理中心，我们可以打开“搜索”配置，然后选择“**管理搜索架构**”以查看并配置已爬网属性。

![搜索架构中已爬网属性](../media/SPRetention8.png)

如果在“**已爬网属性**”框中键入**状态**，然后选择绿色箭头，则会看到如下所示的结果：

![ows_Status已爬网属性](../media/SPRetention9.png)

属性 **ows\_\_Status**（注意双下划线）是我们感兴趣的属性。 它将映射到生产文档内容类型的**状态**属性。

现在，如果我们键入 **ows\_doc** 并选择绿色箭头，则会看到如下所示的内容：

![ows_Doc_Type已爬网属性](../media/SPRetention10.png)

属性 **ows\_Doc\_x0020\_Type** 是我们感兴趣的第二个属性。 它将映射到生产文档内容类型的**文档类型**属性。

> [!TIP]
> 若要标识此方案的已爬网属性的名称，请转到包含生产文档的文档库，然后转到库设置。 在“**栏**”中，选择栏名称（例如**状态**或**文档类型**）以打开网站栏页面。 该页面的 URL 中的“**字段**”参数包含字段名称。 该字段名称以“ows_”为前缀，是已爬网属性的名称。 例如，URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` 对应于 **ows\_\_Status** 已爬网属性。

如果你要查找的已爬网属性未显示在 SharePoint 管理中心的“管理搜索架构”部分中，则可能是由以下原因之一造成的：

- 文档尚未编入索引。 你可以通过转到“文档库设置”>“高级设置”来强制重新编制库的索引。

- 如果文档库位于新式网站中，请确保 SharePoint 管理员也是网站集管理员。

有关已爬网属性和托管属性的详细信息，请参阅[在 SharePoint 服务器中自动创建托管的属性](https://docs.microsoft.com/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint)。

### <a name="mapping-crawled-properties-to-pre-defined-managed-properties"></a>将已爬网属性映射到预定义的托管属性。

KQL 不能在搜索查询中使用已爬网属性。 它必须使用托管属性。 在普通搜索方案中，我们将创建托管属性，并将其映射到所需的已爬网属性。 但是，对于自动应用保留标签，只能在 KQL 中指定预定义的托管属性，而不能指定自定义托管属性。 已在系统中创建一组预定义的托管属性，可使用字符串 RefinableString00 到 RefinableString199。 有关完整列表，请参阅[默认未使用托管属性](https://docs.microsoft.com/sharepoint/manage-search-schema#default-unused-managed-properties)。 这些默认托管属性通常用于定义搜索精简程序。

为了使 KQL 查询正常工作并自动将正确的保留标签应用于产品文档内容，我们将已爬网属性 **ows\_Doc\_x0020\_Type** 和 **ows\_\_Status** 映射到两个可精简的托管属性。 在此方案的测试环境中，未使用 **RefinableString00** 和 **RefinableString01**。 通过在 SharePont 管理中心的“**管理搜索架构**”中查看“**托管属性**”，可以确定这一点。

![搜索架构中托管属性](../media/SPRetention12.png)

请注意，先前屏幕截图中的“**映射的已爬网属性**”栏为空。

若要映射 **ows\_Doc\_x0020\_Type** 已爬网属性，请执行下列操作：

1. 在“**托管属性**”筛选器框中，键入 **RefinableString00**，然后选择绿色箭头。

2. 在结果列表中，选择**RefinableString00** 链接，然后向下滚动到“**到已爬网属性的映射**”部分。  

3. 选择“**添加映射**”，然后在“**已爬网属性选择**”窗口的“**搜索已爬网属性名称**”框中键入 **ows\_Doc\_x0020\_Type**。 选择“**查找**”。  

4. 在结果列表中，选择“**ows\_Doc\_x0020\_Type**”，然后选择“**确定**”。

   在**映射的已爬网属性**部分中，你将看到类似于以下屏幕截图的内容：

   ![选择 "映射的已爬网属性" 部分中的 "添加映射"](../media/SPRetention13.png)

5. 滚动到页面的底部，然后选择“**确定**”以保存映射。

重复上述步骤，以映射 RefinableString01 和 ows\_\_Status。

现在，应该已将两个托管属性映射到两个已爬网属性：

![托管属性现在映射至已爬网属性](../media/SPRetention14.png)

通过运行企业级搜索来验证所有这一切都正确设置。 在浏览器中，转到 https://yourtenant.sharepoint.com/search。 在搜索框中，键入 **RefinableString00：“产品规范”**，然后按 Enter。 这会返回**文档类型**为产品规范的所有文档。

现在，在搜索框中，键入 **RefinableString00：“产品规范”和 RefinableString01：终稿**，然后按 Enter。 这会返回**文档类型**为产品规范且状态为**终稿**的所有文档。

### <a name="creating-the-auto-apply-label-policies"></a>创建自动应用标签策略

现在，我们已验证 KQL 查询可正常工作，下面让我们创建标签策略，它使用 KQL 查询将产品规范保留标签自动应用于相应的文档。

1. 在[安全与合规中心](https://protection.office.com)，转到“**分类**” > “**保留标签**”，然后选择“**自动应用标签**”。 

   ![选择“标签”页面上的“自动应用标签”](../media/SPRetention16.png)

2. 在“**选择要自动应用的标签**”向导页面上，选择“**选择要自动应用的标签**”。

3. 在标签列表中，选择“**产品规范**”，选择“**添加**”，然后选择“**下一步**”。

4. 选择“**将标签应用到包含特定字词或短语或属性的内容**”，然后选择“**下一步**”。

   ![选择应用标签至含有指定单词、短语或属性的内容](../media/SPRetention17.png)

   在下一步中，提供与我们在上一节中测试的查询相同的 KQL 搜索查询。 回忆一下，此查询返回状态为“终稿”的所有产品规范文档。 在标签策略中使用此相同查询的结果意味着，产品规范保留标签将自动应用于与该搜索查询匹配的所有文档。

5. 在“**关键字查询编辑器**”框中，键入 **RefinableString00：“产品规范”和 RefinableString01：终稿**，然后选择“**下一步**”。

   ![在 "关键字查询编辑器" 框中指定查询](../media/SPRetention19.png)

6. 输入标签策略的名称（例如，“**自动应用产品规范标签**”）和可选说明，然后选择“**下一步**”。 

7. 在**选择位置**向导页面上，选择要应用策略的内容位置。 对于此方案，我们将策略仅应用于 SharePoint 位置，因为所有生产文档仅存储在 SharePoint 文档库中。 选择“**让我选择特定位置**”，将 Exchange 电子邮件、OneDrive 帐户和 Office 365 组的状态切换为关闭，并确保将 SharePoint 网站的状态切换为打开。 

    ![选择自动应用标签的指定网站](../media/SPRetentionSPlocations.png)

   > [!TIP]
   > 可以选择“**选择网站**”并添加特定 SharePoint 网站的 URL，而不是将策略应用于所有 SharePoint 网站。

8. 选择“**下一步**”以显示“**查看你的设置**”页面。 

    ![自动应用标签设置](../media/SPRetention18.png)

9. 选择“**自动应用**”以创建标签策略。 最多需要七天时间才能将产品规范标签自动应用到与你提供的 KQL 搜索查询匹配的所有文档。

### <a name="verifying-the-retention-label-was-automatically-applied"></a>验证保留标签是否已自动应用

七天后，使用安全与合规中心内的“[标签活动资源管理器](view-label-activity-for-documents.md)”，查看我们创建的标签策略是否已自动将此方案中的保留标签应用于产品文档。 在以下屏幕截图中，保留标签也已应用于产品协议和用户手册，即使我们在本文中并未介绍如何创建这些保留标签和标签策略。

![使用标签活动浏览器验证标是否自动应用](../media/SPRetention20.png)

另一个验证步骤是查看文档库中文档的属性。 在信息面板中，你可以看到保留标签已应用于所选文档。

![通过查看文档库中的文档属性，验证标签是否已应用](../media/SPRetention21.png)

由于保留标签已自动应用于文档，因此可以保护文档免遭删除，因为该保留标签已配置为将文档声明为记录。 作为此保护的示例，当我们试图删除其中一个文档时，会收到以下屏幕截图所示的错误消息。

![无法删除文档，因为标签声明了文档记录](../media/SPRetention22.png)

## <a name="generating-the-events-that-trigger-the-start-of-the-retention-period"></a>生成用于触发保留期的事件

现在已成功地自动应用了保留标签，下面我们将重点介绍用于指示特定产品停产的事件。 发生此事件时，它将触发在自动应用于文档的保留标签中定义的保留期。 例如，对于产品规范文档，当触发“产品停产”事件时，将开始五年的保留期。

可在安全与合规中心内手动创建事件（方法是转到**记录管理** > **事件**），选择事件类型，设置正确的资产 ID，然后输入事件的日期。 有关详细信息，请参阅[事件驱动保留概述](event-driven-retention.md)。

对于此方案，我们将通过从外部生产系统生成事件来自动创建事件。 在这种情况下，生成事件的系统是一个简单的 SharePoint 列表，它指示产品是否在生产中，[Microsoft 流程](https://docs.microsoft.com/flow/getting-started)是否与列表相关并触发事件。 在现实方案中，它可以是生成事件的任何系统，例如 HR 或 CRM 系统。 Flow 包含许多可供 Office 365 工作负载（例如 Exchange、SharePoint、Teams 和 Dynamics 365）及第三方应用（例如 Twitter、Box、Salesforce 和 Workdays）使用的交互和构建块。 这使你可以轻松地将 Flow 与这些系统进行集成。 有关详细信息，请参阅[自动执行事件驱动的保留](automate-event-driven-retention.md)。

以下屏幕截图显示将用于触发事件的 SharePoint 列表： 

![列表将用于触发保留事件](../media/SPRetention23.png)

目前有两种产品已投入生产，“**投入生产**”栏中的“**是**”值指明了这一点。 当产品的此栏中的值设置为“**否**”时，与列表关联的流将自动生成事件。 反过来，这会触发自动应用到相应产品文档的保留标签的保留期。

对于此方案，我们将使用以下流来触发事件：

![配置将触发事件的流程](../media/SPRetention24.png)

若要创建此流，请从 SharePoint 连接器开始，并选择“**创建或修改项目时**”触发器。 指定网站地址和列表名称，然后根据“**投入生产**”列表栏值是否设置为“**否**”（或在条件卡中等于“false”）来添加条件。 然后添加基于内置 HTTP 模板的操作。 使用以下部分中的值来配置 HTTP 操作。 可复制以下部分中的 URI 和正文属性值，然后将其粘贴到模板中。

- **方法**：POST
- **URI**：https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
- **标头**：键 = Content-Type，值 = application/atom+xml
- **正文**：

```HTML
<?xml version='1.0' encoding='utf-8' standalone='yes'>
<entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices' xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata' xmlns='https://www.w3.org/2005/Atom'>
<category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent'>
<updated>9/9/2017 10:50:00 PM</updated>
<content type='application/xml'>
<m:properties>
<d:Name>Cessation Production @{triggerBody()?['Product_x0020_Name']?['Value']}</d:Name>
<d:EventType>Product Cessation&lt;</d:EventType>
<d:SharePointAssetIdQuery>ProductName:&quot;@{triggerBody()?['Product_x0020_Name']?['Value']}<d:SharePointAssetIdQuery>
<d:EventDateTime>@{formatDateTime(utcNow(),'yyyy-MM-dd')}</d:EventDateTime>
</m:properties>
</content&gt>
</entry>
```

以下部分介绍必须专为此方案配置的操作*正文*属性内的参数。

- **名称**：此参数指定将在安全与合规中心内创建的事件的名称。 对于此方案，名称为“产品停产 xxx”，其中 xxx 是我们之前创建的 ProductName 托管属性的值。
- **EventType**：此参数的数值与将应用已创建事件的事件类型对应。 此事件类型是在创建保留标签时定义的。 对于此方案，事件类型为“产品停产”。
- **SharePointAssetIdQuery**：此参数定义事件的资产 ID。 基于事件的保留需要文档的唯一标识符。。 我们可以使用资产 ID 来标识特定事件适用的文档，或者像此方案一样，使用元数据栏（自己的产品名称）进行标识。 为此，我们必须创建一个名为 ProductName 的新托管属性，可在 KQL 查询中使用该属性（或我们可以使用 RefinableString00，而不是创建新的托管属性）。 我们还需要将此新托管属性映射到 ows_Product_x0020_Name 已爬网属性。 下面是此托管属性的屏幕截图。

    ![保留托管属性](../media/SPRetention25.png)

- **EventDateTime**：此参数定义事件发生的日期。 使用当前日期格式：*formatDateTime(utcNow(),'yyyy-MM-dd'*)

### <a name="putting-it-all-together"></a>汇总

现在，已创建并自动应用保留标签，并且已创建并配置流，下面是当产品列表中旋转小组件产品的“**投入生产**”栏中的值从“**是**”更改为“**否**”时发生的情况。 将触发流并创建事件。 若要在安全与合规中心内查看此事件，请转到“**记录管理**” > “**事件**”。

!["安全与合规性中心" 的 "事件" 页面上显示的流程触发的事件](../media/SPRetention28.png)

选择事件以查看弹出页面上的详细信息。 请注意，即使已创建事件，事件状态中的详细信息仍显示未处理任何 SharePoint 网站或文档。

![事件详情](../media/SPRetention29.png)

但在一段时间后，“事件状态”部分将显示已处理 SharePoint 网站和 SharePoint 文档。  

![事件详情显示处理的文档](../media/SPRetention31.png)
 
这意味着，根据旋转小组件产品停产事件的事件日期，已触发应用于旋转小组件产品文档的标签的保留期。 假设你通过配置一天的保留期在测试环境中实施了该方案，则可以在创建事件后的几天内转到产品文档的文档库，并验证该文档是否已被删除（在运行 SharePoint 中的删除作业之后）。

### <a name="more-about-asset-ids"></a>有关资产 ID 的详细信息

如[事件驱动保留概述](event-driven-retention.md)中所述，了解事件类型、标签、事件和资产 ID 之间的关系非常重要。 资产 ID 只是 SharePoint 和 OneDrive 中的另一种文档属性。 它可以帮助你进一步标识将由事件触发其保留期的文档。 默认情况下，SharePoint 具有一个资产 ID 属性，你可以将其用于事件驱动的保留：

![文档属性详细信息页面中显示的资产 Id 属性](../media/SPRetention26.png)

如以下屏幕截图所示，资产 ID 托管属性称为 **ComplianceAssetId**。

![ComplianceAssetId托管属性](../media/SPRetention27.png)

像此方案一样，你也可以使用任何其他属性，而不是使用默认资产 ID 属性。 但是，请务必注意，如果没有为事件指定资产 ID 或关键字，则具有该事件类型标签的所有内容均由该事件触发保留期。

### <a name="using-advanced-search-in-sharepoint"></a>在 SharePoint 中使用高级搜索

在前一屏幕截图中，我们还可以看到有另一个与保留标签相关的托管属性，它称为 **ComplianceTag** 并且已映射到已爬网属性。 **ComplianceAssetId** 托管属性也已映射到已爬网属性。 这意味着可在高级搜索中使用这些托管属性来检索已应用保留标签的所有文档。

## <a name="summary"></a>总结

本文介绍了一种文档管理方案，它根据 SharePoint 中的网站栏自动应用了保留标签。 然后，我们使用基于事件的保留和 Microsoft Flow 根据外部事件自动触发保留期。

## <a name="credits"></a>制作人员

该方案的作者： 

Frederic Lapierre<br/>Microsoft 服务首席顾问
