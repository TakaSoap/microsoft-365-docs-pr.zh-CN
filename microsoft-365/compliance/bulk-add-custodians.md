---
title: 将保管人导入Advanced eDiscovery案例
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用导入工具 d 快速将多个保管人及其关联的数据源添加到Advanced eDiscovery。
ms.openlocfilehash: 5e2ce53a227462a1fddd7785faf83355ca70611c
ms.sourcegitcommit: 2e05865beeb2051fd9ece212a46179310b946a46
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2021
ms.locfileid: "61148727"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>将保管人导入Advanced eDiscovery案例

对于Advanced eDiscovery多个保管人的情况，可以使用 CSV 文件一次导入多个保管人，其中包含将保管人添加到事例所必需的信息。

## <a name="import-custodians"></a>导入保管人

1. 打开"Advanced eDiscovery"案例并选择"**数据源"** 选项卡。

2. 单击 **"添加数据源**  >  **导入保管人"。**

3. 在" **导入保管人** "飞出页面上，单击 **"下载空白模板** "以下载保管人模板 CSV 文件。

   ![从导入保管人飞出页面下载 CSV 模板。](../media/ImportCustodians1.png)

4. 将信息添加到 CSV 文件，并将其保存到本地计算机。 有关 [CSV 文件中所需](#custodian-csv-file) 属性的信息，请参阅 Custodian CSV 文件部分。

5. 准备好包含保管人信息的 CSV 文件后，返回到"数据源"选项卡，并再次单击"添加数据源  >  **导入保管** 人"。

6. 在"**导入保管人**"飞出页面上，单击"浏览"，然后上载包含保管人信息的 CSV 文件。

   上载 CSV 文件后，将创建名为 **BulkAddCustodian** 的作业，并将其显示在"作业 **"** 选项卡上。作业验证保管人及其关联的数据源，然后将它们添加到案例的" **数据源** "页。

## <a name="custodian-csv-file"></a>保管人 CSV 文件

下载 CSV 保管人模板后，您可以在每行中添加保管人及其数据源。 确保不要更改标题行中的列名称。 使用工作负荷类型和工作负荷位置列将其他数据源关联到保管人。

| 列名称|说明|
|:------- |:------------------------------------------------------------|
|**Custodian contactEmail**     |保管人 UPN 电子邮件地址。 例如，sarad@contoso.onmicrosoft.com。           |
|**Exchange已启用** | 要包含或不包含保管人邮箱的 TRUE/FALSE 值。      |
|**OneDrive已启用** | 要包含或不包含保管人帐户的 TRUE/FALSE OneDrive for Business帐户。 |
|**Is OnHold**        | TRUE/FALSE 值，指示是否将保管人数据源放在保留状态。 <sup>1</sup>     |
|**Workload1 类型**         |指示要与保管人关联的数据源类型的字符串值。 可能的值包括： <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<sup>2</sup><br/>- YammerMailbox<sup>2</sup>| 
|**Workload1 位置**     | 根据您的工作负荷类型，这将是数据源的位置。 例如，用户邮箱Exchange URL 或网站SharePoint URL。 |
|||

> [!NOTE]
> <sup>1</sup> 当您将 1，000 多个邮箱或 100 个网站置于保留状态时，系统将根据需要自动扩展电子数据展示保留。 这意味着系统会自动将数据位置添加到多个保留，而不是将它们添加到单个保留中。 但是，每个组织保留 10，000 个案例的限制仍然适用。 有关保留限制详细信息，请参阅 Advanced eDiscovery[中的限制](limits-ediscovery20.md#hold-limits)。
<br>
> <sup>2</sup> 在 CSV 文件中添加 TeamsMailbox 和 YammerMailbox 工作负载时，默认情况下会自动添加组网站 (TeamSite 和 YammerSite) 。 无需在 CSV 文件中单独指定 TeamsSite 和 YammerSite。

下面是包含保管人信息的 CSV 文件的示例：<br/><br/>

|Custodian contactEmail      | Exchange已启用 | OneDrive已启用 | Is OnHold | Workload1 类型 | Workload1 位置             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@contoso.onmicrosoft.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@contoso.onmicrosoft.com | TRUE             | TRUE             | TRUE      | |  |
|.johnj@contoso.onmicrosoft.com|TRUE|TRUE|TRUE||
|sarad@contoso.onmicrosoft.com|TRUE|TRUE|TRUE|ExchangeMailbox|.saradavis@contoso.onmicrosoft.com
||||||

> [!NOTE]
> 若要导入非活动邮箱作为保管人或将非活动邮箱与另一个保管人关联，请向非活动邮箱的 UPN 地址添加"."前缀。

## <a name="custodian-and-data-source-validation"></a>保管人和数据源验证

上传保管人 CSV 文件后，Advanced eDiscovery执行以下操作：

1. 验证保管人及其数据源。

2. 如果 CSV 文件中 **Is OnHold** 属性设置为 TRUE，则索引每个保管人的所有数据源， (将其保留) 。

### <a name="custodian-validation"></a>保管人验证

目前，我们仅支持导入组织托管服务中包含的保管Azure Active Directory (Azure AD) 。

保管人导入工具使用 CSV 文件的 **Custodian contactEmail** 列中的 UPN 值查找并验证保管人。 经验证的保管人将自动添加到案例，并列在案例的" **数据源** "选项卡上。 如果无法验证保管人，将在"作业"选项卡上列出的 BulkAddCustodian 作业的错误日志中列出保管人。  未验证保管人不会添加到案例或列在"数据源 **"选项卡** 上。

### <a name="data-source-validation"></a>数据源验证

验证保管人并添加到案例后，OneDrive添加与保管人关联的每个主邮箱和邮箱帐户。

但是，如果找不到与保管人关联的任何其他数据源 (例如 SharePoint 网站、Microsoft Teams、Microsoft 365 组或 Yammer 组) ，则没有分配给保管人，并且"未验证"值显示在数据源上保管人旁边的"状态"**列中。** 选项卡。

为保管人添加经过验证的数据源：

1. 在 **"数据源"** 选项卡上，选择包含未验证的数据源的保管人。

2. 在保管人飞出页面上，滚动到 **"显示** 位置"部分以查看与保管人关联的已验证和未验证的数据源。

3. 单击 **飞** 出页面顶部的"编辑"以删除无效数据源或添加新数据源。

4. 删除未验证的数据源或添加新数据源后，值 **Active** 将显示在"数据源"选项卡上保管人 **的状态列中。** 若要添加之前似乎无效的源，请按照下面的修正步骤手动将它们添加到保管人。

### <a name="remediating-invalid-data-sources"></a>修正无效的数据源

若要手动添加和关联之前无效的数据源，

1. 在 **"数据源"** 选项卡上，选择要手动添加和关联以前无效的数据源的保管人。

2. 单击 **飞** 出页面顶部的"编辑"，将邮箱、站点、Teams或Yammer组关联到保管人。 为此 **，单击相应** 数据位置类型旁边的"编辑"。

3. 单击 **"** 下一步"以显示"保留设置"页，并配置您添加的数据源的保留设置。

4. 单击 **"下** 一步"显示 **"审阅** 保管人"页，然后单击" **提交** "以保存更改。
