---
title: 将保管人导入高级电子数据展示案例
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
description: 使用导入工具 dto 将多个保管人及其关联的数据源快速添加到高级电子数据展示的案例中。
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740299"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>将保管人导入高级电子数据展示案例

对于涉及许多保管人的高级电子数据展示事例，可以使用 CSV 文件一次导入多个保管人，该文件包含将保管人添加到事例所必需的信息。

## <a name="import-custodians"></a>导入保管人

1. 打开高级电子数据展示案例并选择 **"数据源"** 选项卡。

2. 单击 **"添加数据源**  >  **导入保管人"。**

3. 在" **导入保管人** "飞出页上，单击"下载 **空白** 模板"以下载保管人模板 CSV 文件。

   ![从导入保管人飞出页面下载 CSV 模板](../media/ImportCustodians1.png)

4. 将信息添加到 CSV 文件，并将其保存到本地计算机。 有关 [CSV 文件中](#custodian-csv-file) 所需属性的信息，请参阅 Custodian CSV 文件部分。

5. 准备好包含保管人信息的 CSV 文件后，返回到"数据源 **"选项卡，** 并再次单击"**添加数据源**  >  **导入保管** 人"。

6. 在"**导入保管人**"飞出页上，单击"浏览"，然后上载包含保管人信息的 CSV 文件。

   上载 CSV 文件后，将创建名为 **BulkAddCustodian** 的作业，并将其显示在"作业 **"** 选项卡上。作业验证保管人及其关联的数据源，然后将它们添加到案例的"数据源 **"** 页。

## <a name="custodian-csv-file"></a>保管人 CSV 文件

下载 CSV 保管人模板后，可以在每行中添加保管人及其数据源。 确保不要更改标题行中的列名称。 使用工作负荷类型和工作负荷位置列将其他数据源关联到保管人。

| 列名称|说明|
|:------- |:------------------------------------------------------------|
|**保管人 contactEmail**     |保管人 UPN 电子邮件地址。 例如，sarad@contoso.onmicrosoft.com。           |
|**Exchange 已启用** | 要包含或不包括保管人邮箱的 TRUE/FALSE 值。      |
|**OneDrive 已启用** | 要包含或不包含保管人 OneDrive for Business 帐户的 TRUE/FALSE 值。 |
|**Is OnHold**        | TRUE/FALSE 值，指示是否将保管人数据源放在保留状态。       |
|**Workload1 类型**         |指示要与保管人关联的数据源类型的字符串值。 可能的值包括： <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Workload1 位置**     | 根据您的工作负荷类型，这将是数据源的位置。 例如，Exchange 邮箱的电子邮件地址或 SharePoint 网站的 URL。 |
|||

下面是包含保管人信息的 CSV 文件的示例：<br/><br/>

|保管人 contactEmail      | Exchange 已启用 | OneDrive 已启用 | Is OnHold | Workload1 类型 | Workload1 位置             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>保管人和数据源验证

上传保管人 CSV 文件后，高级电子数据展示将执行以下操作：

1. 验证保管人及其数据源。

2. 索引每个保管人的所有数据源，如果 CSV (**Is OnHold** 属性设置为 TRUE，则将其) 。

### <a name="custodian-validation"></a>保管人验证

目前，我们仅支持导入包含在组织的 Azure Active Directory (Azure AD) 。

保管人导入工具使用 CSV 文件的 **Custodian contactEmail** 列中的 UPN 值查找并验证保管人。 经验证的保管人将自动添加到案例，并列在案例的"数据源 **"** 选项卡上。 如果无法验证保管人，将在"作业"选项卡上列出的 BulkAddCustodian 作业的错误日志中列出保管人。  未验证保管人不会添加到案例或列在"数据源 **"选项卡** 上。

### <a name="data-source-validation"></a>数据源验证

验证保管人并添加到案例后，将添加与保管人关联的每个主邮箱和 OneDrive 帐户。

但是，如果找不到与保管人关联的任何其他数据源 (例如 SharePoint 网站、Microsoft Teams、Microsoft 365 组或 Yammer 组) ，则不会将任何数据源分配给保管人，并且未验证的值将显示在"数据源"选项卡上保管人旁边的"状态"列中。 

为保管人添加经过验证的数据源：

1. 在 **"数据源"** 选项卡上，选择包含未验证的数据源的保管人。

2. 在保管人飞出页面上，滚动到 **"保管** 人位置"部分以查看与保管人关联的已验证和未验证数据源。

3. 单击 **飞** 出页面顶部的"编辑"以删除无效数据源或添加新数据源。

4. 删除未验证的数据源或添加新数据源后，"数据源"选项卡上保管人的状态列中将显示"**活动****"** 值。若要添加之前似乎无效的源，请按照下面的修正步骤手动将它们添加到保管人。

### <a name="remediating-invalid-data-sources"></a>修正无效数据源

若要手动添加和关联以前无效的数据源：

1. 在 **"数据源"** 选项卡上，选择要手动添加和关联以前无效的数据源的保管人。

2. 单击 **飞** 出页面顶部的"编辑"，将邮箱、网站、Teams 或 Yammer 组关联到保管人。 为此 **，单击相应** 数据位置类型旁边的"编辑"。

3. 单击 **"** 下一步 **"显示"** 保留设置"页，并配置您添加的数据源的保留设置。

4. 单击 **"** 下一步"显示 **"审阅** 保管人"页，然后单击" **提交"保存** 更改。
