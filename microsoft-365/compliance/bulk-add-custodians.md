---
title: 向高级电子数据展示案例批量添加保管人
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
ROBOTS: NOINDEX, NOFOLLOW
description: 使用批量添加工具将多个保管人及其关联的数据源快速添加到高级电子数据展示的案例中。
ms.openlocfilehash: 921d4a1616d97f2adde7e40baa5c73f607c849b6
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741640"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a>向高级电子数据展示案例批量添加保管人

对于涉及大量保管人的高级电子数据展示事例，您可以一次导入多个保管人（包含将其添加到事例所需的所有信息的 CSV 文件）。

## <a name="bulk-add-custodians"></a>批量添加保管人

1. 输入大小写并导航到 "**源**" 选项卡。

2. 单击 "**导入保管人**"

3. 在弹出页面上，单击 "**下载空白模板**" 以下载 CSV 保管人模板文件。

4. 将 custodial 信息添加到 CSV 文件，并将其保存在您的本地计算机上。 有关 CSV 文件中的属性的信息，请参阅下一节。

5. 在 "**源**" 选项卡上，再次单击 "**导入保管人**"。 
6. 在弹出页面上，单击 "**浏览**"，然后上传 CSV 文件。

   在上传 CSV 文件后，将创建一个 BulkAddCustodian 作业并将其显示在 "**作业**" 选项卡上。该作业将验证保管人及其相应的数据源，然后将其添加到事例的 "**源**" 页上的 "**保管人**" 选项卡上。

## <a name="custodian-csv-file"></a>保管人 CSV 文件

下载 CSV 模板后，可以在每行中添加保管人及其数据源。 请务必不要更改标题行中的列名称。

| 列名称|说明|
|:------- |:------------------------------------------------------------|
|**保管人 ContactEmail**     | 保管人的 UPN 电子邮件。 示例： sarad@onmicrosoft.contoso.com           |
|**已启用 Exchange** | TRUE/FALSE 值，指示是否添加保管人的邮箱。      |
|**已启用 OneDrive** | TRUE/FALSE 值，该值指示是否添加保管人的 OneDrive for business 帐户。 |
|**为 OnHold**        | TRUE/FALSE 值，指示是否将保管人置于保留状态。       |
|**Workload1 类型**         | 指示要与保管人关联的数据源的类型的字符串值。 <br />可能的值包括： <br />ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite |
|**Workload1 位置**     | 根据您的工作负载类型，这将是工作负荷的数据位置（例如，Exchange 邮箱的电子邮件地址或 SharePoint 网站的 URL）。 |
|||

以下是包含保管人信息的 CSV 文件的示例：  

| ContactEmail      | 已启用 Exchange | 已启用 OneDrive | 为 OnHold | Workload1 类型 | Workload1 位置             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|sarad@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>保管人和数据源验证

当您上载保管人 CSV 文件时，高级电子数据展示将执行以下操作：

1. 验证保管人及其数据源。 

2. 为每个保管人的所有数据源编制索引，并将其置于保留状态（如果 "OnHold" 属性设置为 TRUE）。

### <a name="custodian-validation"></a>保管人验证

目前，我们仅支持在 Azure Active Directory （AAD）中导入保管人。

我们使用 CSV 文件的 "**联系人电子邮件**" 列中的 UPN 值验证和查找保管人。 已验证的保管人将自动添加到事例中，并在案例的 "**源**" 页上的 "**保管人**" 选项卡上列出。 如果无法验证某个保管人，则会在该事例的 "**作业**" 选项卡上列出的 BulkAddCustodian 作业的错误日志中列出。 Unvalidated 保管人不会添加到事例中。

### <a name="data-source-validation"></a>数据源验证

在对保管人进行验证并将其添加到事例之后，将验证与保管人关联的每个数据源。 如果找不到某个保管人的任何数据源，则**未验证**的值将显示在该保管人的 "**保管人**" 选项卡上的 "已**验证**" 列中。

### <a name="remediating-unvalidated-data-sources"></a>修正 unvalidated 数据源

使用 unvalidated 数据源修正保管人： 

1. 在 "**管理员**" 选项卡上，选择未验证的管理员。

2. 在 "保管人" 弹出页面上，滚动到 "**数据源**" 部分以查看与保管人关联的数据源。 已列出经过验证和 unvalidated 的数据源。

3. 在 "**数据源**" 部分，单击 "**编辑**"。

4. 在 "**选择 custodial 位置**" 页上，删除 "unvalidated" 数据源。

5. 在 "**选择其他位置**" 页上，单击 "**更新**" 为保管人添加其他数据源。
