---
title: 导出、配置和查看审核日志记录
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: 本文将了解如何导出、配置和查看 Microsoft 365 审核日志记录。
ms.openlocfilehash: a7f731bb30ffdddfe7898ee4051060b8e22c093e
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454663"
---
# <a name="export-configure-and-view-audit-log-records"></a><span data-ttu-id="46d8f-103">导出、配置和查看审核日志记录</span><span class="sxs-lookup"><span data-stu-id="46d8f-103">Export, configure, and view audit log records</span></span>

<span data-ttu-id="46d8f-104">在搜索审核日志将搜索结果下载到 CSV 文件后，该文件包含一个名为 **AuditData** 的列，其中包含有关每个事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="46d8f-104">After you search the audit log and download the search results to a CSV file, the file contains a column named **AuditData**, which contains additional information about each event.</span></span> <span data-ttu-id="46d8f-105">此列中的数据的格式设置为 JSON 对象，该对象包含多个配置为 *property：value* 对的属性，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="46d8f-105">The data in this column is formatted as a JSON object, which contains multiple properties that are configured as *property:value* pairs separated by commas.</span></span> <span data-ttu-id="46d8f-106">可以使用 Excel Power Query Editor 中的 JSON 转换功能将 **AuditData** 列中 JSON 对象中的每个属性拆分为多个列，以便每个属性都有自己的列。</span><span class="sxs-lookup"><span data-stu-id="46d8f-106">You can use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into multiple columns so that each property has its own column.</span></span> <span data-ttu-id="46d8f-107">这允许您对一个或多个属性进行排序和筛选，这可以帮助您快速找到要查找的特定审核数据。</span><span class="sxs-lookup"><span data-stu-id="46d8f-107">This lets you sort and filter on one or more of these properties, which can help you quickly locate the specific auditing data you're looking for.</span></span>

## <a name="step-1-export-audit-log-search-results"></a><span data-ttu-id="46d8f-108">步骤 1：导出审核日志搜索结果</span><span class="sxs-lookup"><span data-stu-id="46d8f-108">Step 1: Export audit log search results</span></span>

<span data-ttu-id="46d8f-109">第一步是搜索审核日志，然后将结果以逗号分隔的值导出 (CSV) 文件导出到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="46d8f-109">The first step is to search the audit log and then export the results in a comma-separated value (CSV) file to your local computer.</span></span>
  
1. <span data-ttu-id="46d8f-110">运行审核日志 [搜索](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) 并根据需要修改搜索条件，直到获得所需结果。</span><span class="sxs-lookup"><span data-stu-id="46d8f-110">Run an [audit log search](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) and revise the search criteria if necessary until you have the desired results.</span></span>

2. <span data-ttu-id="46d8f-111">单击 **"导出结果"，** 然后选择 **"下载所有结果"。**</span><span class="sxs-lookup"><span data-stu-id="46d8f-111">Click **Export results** and select **Download all results**.</span></span> 

   ![单击"下载所有结果"](../media/ExportAuditSearchResults.png)

   <span data-ttu-id="46d8f-113">此选项可从步骤 1 中审核日志搜索导出所有审核记录，将原始数据从 审核日志下载到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="46d8f-113">This option to exports all the audit records from the audit log search you ran in step 1, and downloads the raw data from the audit log to a CSV file.</span></span> 

   <span data-ttu-id="46d8f-114">窗口底部将显示一条消息，提示您打开或保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="46d8f-114">A message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span> 

3. <span data-ttu-id="46d8f-115">单击 **">另存** 为"，将 CSV 文件保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="46d8f-115">Click **Save > Save as** and save the CSV file to your local computer.</span></span> <span data-ttu-id="46d8f-116">下载许多搜索结果需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="46d8f-116">It takes a while to download many search results.</span></span> <span data-ttu-id="46d8f-117">搜索所有活动或广泛日期范围时，通常会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="46d8f-117">This is typically the case when searching for all activities or a broad date range.</span></span> <span data-ttu-id="46d8f-118">当 CSV 文件完成下载时，窗口底部将显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="46d8f-118">A message at the bottom of the windows is displayed when the CSV file is finished downloading.</span></span>

   ![CSV 文件完成下载时显示的消息](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > <span data-ttu-id="46d8f-120">你可以将最多 50,000 个条目从单个审核日志搜索中下载到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="46d8f-120">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="46d8f-121">如果下载了 50,000 个条目到 CSV 文件，则可以假定可能存在超过 50,000 个符合搜索条件的事件。</span><span class="sxs-lookup"><span data-stu-id="46d8f-121">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="46d8f-122">若要导出超过此限制，请尝试使用日期范围来减少记录审核日志的数量。</span><span class="sxs-lookup"><span data-stu-id="46d8f-122">To export more than this limit, try using a date range to reduce the number of audit log records.</span></span> <span data-ttu-id="46d8f-123">你可能需要使用更小日期范围运行多个搜索来导出超过 50,000 个条目。</span><span class="sxs-lookup"><span data-stu-id="46d8f-123">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a><span data-ttu-id="46d8f-124">步骤 2：使用 Power Query 编辑器审核日志导出的查询</span><span class="sxs-lookup"><span data-stu-id="46d8f-124">Step 2: Format the exported audit log using the Power Query Editor</span></span>

<span data-ttu-id="46d8f-125">下一步是使用 Excel Power Query Editor 中的 JSON 转换功能将 **AuditData** 列中 JSON 对象的每个属性拆分为其自己的列。</span><span class="sxs-lookup"><span data-stu-id="46d8f-125">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="46d8f-126">然后，筛选列以根据特定属性的值查看记录。</span><span class="sxs-lookup"><span data-stu-id="46d8f-126">Then you filter columns to view records based on the values of specific properties.</span></span> <span data-ttu-id="46d8f-127">这可以帮助您快速找到要查找的特定审核数据。</span><span class="sxs-lookup"><span data-stu-id="46d8f-127">This can help you quickly locate the specific auditing data you're looking for.</span></span>

1. <span data-ttu-id="46d8f-128">在 Excel for Office 365、Excel 2019 或 Excel 2016 中打开空白工作簿。</span><span class="sxs-lookup"><span data-stu-id="46d8f-128">Open a blank workbook in Excel for Office 365, Excel 2019, or Excel 2016.</span></span>

2. <span data-ttu-id="46d8f-129">在"**数据"** 选项卡上的"&**转换数据** 功能区组中，单击 **"自文本/CSV"。**</span><span class="sxs-lookup"><span data-stu-id="46d8f-129">On the **Data** tab, in the **Get & Transform Data** ribbon group, click **From Text/CSV**.</span></span>

    ![在"数据"选项卡上，单击"自文本/CSV"](../media/JSONTransformOpenCSVFile.png)

3. <span data-ttu-id="46d8f-131">打开在步骤 1 中下载的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="46d8f-131">Open the CSV file that you downloaded in Step 1.</span></span>

4. <span data-ttu-id="46d8f-132">在显示的窗口中，单击"**转换数据"。**</span><span class="sxs-lookup"><span data-stu-id="46d8f-132">In the window that's displayed, click **Transform Data**.</span></span>

   ![单击"转换数据"](../media/JSONOpenPowerQuery.png)

   <span data-ttu-id="46d8f-134">CSV 文件在查询编辑器 **中打开**。</span><span class="sxs-lookup"><span data-stu-id="46d8f-134">The CSV file is opened in the **Query Editor**.</span></span> <span data-ttu-id="46d8f-135">有四列：CreationDate、UserIds、Operations和 **AuditData。**  </span><span class="sxs-lookup"><span data-stu-id="46d8f-135">There are four columns: **CreationDate**, **UserIds**, **Operations**, and **AuditData**.</span></span> <span data-ttu-id="46d8f-136">**AuditData** 列是包含多个属性的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="46d8f-136">The **AuditData** column is a JSON object that contains multiple properties.</span></span> <span data-ttu-id="46d8f-137">下一步是为 JSON 对象中的每个属性创建一列。</span><span class="sxs-lookup"><span data-stu-id="46d8f-137">The next step is to create a column for each property in the JSON object.</span></span>

5. <span data-ttu-id="46d8f-138">右键单击 **AuditData** 列中的标题，单击 **"转换**"，然后单击 **JSON。**</span><span class="sxs-lookup"><span data-stu-id="46d8f-138">Right-click the title in the **AuditData** column, click **Transform**, and then click **JSON**.</span></span> 

   ![右键单击 AuditData 列，单击"转换"，然后选择 JSON](../media/JSONTransform.png)

6. <span data-ttu-id="46d8f-140">在 **AuditData** 列的右上角，单击展开图标。</span><span class="sxs-lookup"><span data-stu-id="46d8f-140">In the upper-right corner of the **AuditData** column, click the expand icon.</span></span>

   ![在 AuditData 列中，单击展开图标](../media/JSONTransformExpandIcon.png)

   <span data-ttu-id="46d8f-142">将显示 **AuditData** 列中 JSON 对象中的属性部分列表。</span><span class="sxs-lookup"><span data-stu-id="46d8f-142">A partial list of the properties in the JSON objects in the **AuditData** column is displayed.</span></span>

7. <span data-ttu-id="46d8f-143">单击 **"加载更多** "以显示 **AuditData** 列中 JSON 对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="46d8f-143">Click **Load more** to display all properties in the JSON objects in the **AuditData** column.</span></span>

   ![单击"加载更多"以显示 JSON 对象中的所有属性](../media/JSONTransformLoadJSONProperties.png)

   <span data-ttu-id="46d8f-145">可以取消选中不想包含的任何属性旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="46d8f-145">You can unselect the checkbox next to any property that you don't want to include.</span></span> <span data-ttu-id="46d8f-146">消除对调查没有用处的列是减少数据展示中审核日志。</span><span class="sxs-lookup"><span data-stu-id="46d8f-146">Eliminating columns that aren't useful for your investigation is a good way to reduce the amount of data displayed in the audit log.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="46d8f-147">单击"加载更多) "后，上一个屏幕截图中显示的 J  (SON 属性) 这些属性基于 CSV 文件中前 1，000 行的 **AuditData** 列中的属性。</span><span class="sxs-lookup"><span data-stu-id="46d8f-147">The JSON properties displayed in the previous screenshot (after you click **Load more**) are based on the properties found in the **AuditData** column from the first 1,000 rows in the CSV file.</span></span> <span data-ttu-id="46d8f-148">如果前 1，000 行后的记录中有不同的 JSON 属性，则当 **AuditData** 列拆分为多个列时，这些属性 (和相应的列) 将不包含。</span><span class="sxs-lookup"><span data-stu-id="46d8f-148">If there are different JSON properties in records after the first 1,000 rows, these properties (and a corresponding column) won't be included when the **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="46d8f-149">为了帮助防止这种情况，请考虑重新运行审核日志并缩小搜索条件范围，以便返回的记录更少。</span><span class="sxs-lookup"><span data-stu-id="46d8f-149">To help prevent this, consider re-running the audit log search and narrow the search criteria so that fewer records are returned.</span></span> <span data-ttu-id="46d8f-150">另一个解决方法是筛选"操作"列中的项，以减少 (行数，然后再在 **AuditData** 列中转换 JSON 对象之前执行) 上的步骤 5。</span><span class="sxs-lookup"><span data-stu-id="46d8f-150">Another workaround is to filter items in the **Operations** column to reduce the number of rows (before you perform step 5 above) before transforming the JSON object in the **AuditData** column.</span></span>

   > [!TIP]
   > <span data-ttu-id="46d8f-151">若要查看列表（如 AuditData.AffectedItems）中的属性，请单击要拉取属性的列右上角的"展开"图标，然后选择"展开到 **新建行"。**</span><span class="sxs-lookup"><span data-stu-id="46d8f-151">To view an attribute within a list such as AuditData.AffectedItems, click the **Expand** icon in the upper right corner of the column you want to pull an attribute from, and then select **Expand to New Row**.</span></span>  <span data-ttu-id="46d8f-152">在这里，它将是一条记录，您可以单击列右上角的"展开"图标，查看属性，然后选择要查看或提取的属性。</span><span class="sxs-lookup"><span data-stu-id="46d8f-152">From there it will be a record and you can click the **Expand** icon in the upper right corner of the column, view the attributes, and select the one you want to view or extract.</span></span>

8. <span data-ttu-id="46d8f-153">执行下列操作之一，设置为所选每个 JSON 属性添加的列标题的格式。</span><span class="sxs-lookup"><span data-stu-id="46d8f-153">Do one of the following things to format the title of the columns that are added for each JSON property that's selected.</span></span>

    - <span data-ttu-id="46d8f-154">取消选择"使用原始 **列名称作为** 前缀"复选框，以使用 JSON 属性的名称作为列名称;例如 **，RecordType** 或 **SourceFileName。**</span><span class="sxs-lookup"><span data-stu-id="46d8f-154">Unselect the **Use original column name as prefix** checkbox to use the name of the JSON property as the column names; for example, **RecordType** or **SourceFileName**.</span></span>

    - <span data-ttu-id="46d8f-155">保留 **选中"使用原始列名称作为前缀**"复选框以将 AuditData 前缀添加到列名称中;例如 **，AuditData.RecordType** 或 **AuditData.SourceFileName。**</span><span class="sxs-lookup"><span data-stu-id="46d8f-155">Leave the **Use original column name as prefix** checkbox selected to add the AuditData prefix to the column names; for example, **AuditData.RecordType** or **AuditData.SourceFileName**.</span></span>

9. <span data-ttu-id="46d8f-156">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="46d8f-156">Click **OK**.</span></span>

    <span data-ttu-id="46d8f-157">**AuditData** 列拆分为多个列。</span><span class="sxs-lookup"><span data-stu-id="46d8f-157">The **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="46d8f-158">每个新列对应于 AuditData JSON 对象中的一个属性。</span><span class="sxs-lookup"><span data-stu-id="46d8f-158">Each new column corresponds to a property in the AuditData JSON object.</span></span> <span data-ttu-id="46d8f-159">列的每一行都包含属性的值。</span><span class="sxs-lookup"><span data-stu-id="46d8f-159">Each row in the column contains the value for the property.</span></span> <span data-ttu-id="46d8f-160">如果属性不包含值，则显示 *空* 值。</span><span class="sxs-lookup"><span data-stu-id="46d8f-160">If the property doesn't contain a value, the *null* value is displayed.</span></span> <span data-ttu-id="46d8f-161">在 Excel 中，值为 null 的单元格为空。</span><span class="sxs-lookup"><span data-stu-id="46d8f-161">In Excel, cells with null values are empty.</span></span>
  
10. <span data-ttu-id="46d8f-162">在 **"主页** "选项卡 **上** ，&加载以关闭 Power Query 编辑器，并打开 Excel 工作簿中转换后的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="46d8f-162">On the **Home** tab, click **Close & Load** to close the Power Query Editor and open the transformed CSV file in an Excel workbook.</span></span>

## <a name="use-powershell-to-search-and-export-audit-log-records"></a><span data-ttu-id="46d8f-163">使用 PowerShell 搜索和导出审核日志记录</span><span class="sxs-lookup"><span data-stu-id="46d8f-163">Use PowerShell to search and export audit log records</span></span>

<span data-ttu-id="46d8f-164">您可以使用 Exchange Online PowerShell 中的 [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet 将 审核日志 搜索的结果导出到 CSV 文件，而不是使用安全与合规中心中的 审核日志 & 搜索工具。</span><span class="sxs-lookup"><span data-stu-id="46d8f-164">Instead of using the audit log search tool in the Security & Compliance Center, you can use the [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell to export the results of an audit log search to a CSV file.</span></span> <span data-ttu-id="46d8f-165">然后，可以按照步骤 2 中所述的相同过程，审核日志 Power Query 编辑器设置数据格式。</span><span class="sxs-lookup"><span data-stu-id="46d8f-165">Then you can follow the same procedure described in Step 2 to format the audit log using the Power Query editor.</span></span> <span data-ttu-id="46d8f-166">使用 PowerShell cmdlet 的一个优点是，可以使用 RecordType 参数从特定 *服务搜索* 事件。</span><span class="sxs-lookup"><span data-stu-id="46d8f-166">One advantage of using the PowerShell cmdlet is that you can search for events from a specific service by using the *RecordType* parameter.</span></span> <span data-ttu-id="46d8f-167">下面是几个使用 PowerShell 将审核记录导出到 CSV 文件的示例，以便您可以使用 Power Query 编辑器转换 **AuditData** 列中的 JSON 对象，如步骤 2 中所述。</span><span class="sxs-lookup"><span data-stu-id="46d8f-167">Here are few examples of using PowerShell to export audit records to a CSV file so you can use the Power Query editor to transform the JSON object in the **AuditData** column as described in Step 2.</span></span>

<span data-ttu-id="46d8f-168">本示例中，运行以下命令以返回与 SharePoint 共享操作相关的所有记录。</span><span class="sxs-lookup"><span data-stu-id="46d8f-168">In this example, run the following commands to return all records related to SharePoint sharing operations.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

<span data-ttu-id="46d8f-169">搜索结果将导出到名为 *PowerShellAuditlog* 的 CSV 文件，该文件包含四列：CreationDate、UserIds、RecordType、AuditData) 。</span><span class="sxs-lookup"><span data-stu-id="46d8f-169">The search results are exported to a CSV file named *PowerShellAuditlog* that contains four columns: CreationDate, UserIds, RecordType, AuditData).</span></span>

<span data-ttu-id="46d8f-170">您还可以将记录类型的名称或枚举值用作 *RecordType* 参数的值。</span><span class="sxs-lookup"><span data-stu-id="46d8f-170">You can also use the name or enum value for the record type as the value for the *RecordType* parameter.</span></span> <span data-ttu-id="46d8f-171">有关记录类型名称及其对应的枚举值的列表，请参阅 [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)管理活动 API 架构中的 *AuditLogRecordType* 表。</span><span class="sxs-lookup"><span data-stu-id="46d8f-171">For a list of record type names and their corresponding enum values, see the *AuditLogRecordType* table in [Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).</span></span>

<span data-ttu-id="46d8f-172">只能包含 *RecordType* 参数的单个值。</span><span class="sxs-lookup"><span data-stu-id="46d8f-172">You can only include a single value for the *RecordType* parameter.</span></span> <span data-ttu-id="46d8f-173">若要搜索其他记录类型的审核记录，必须再次运行上述两个命令以指定不同的记录类型，将这些结果追加到原始 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="46d8f-173">To search for audit records for other record types, you have to run the two previous commands again to specify a different record type and append those results to the original CSV file.</span></span> <span data-ttu-id="46d8f-174">例如，您将运行以下两个命令，将 SharePoint 文件活动从同一日期范围添加到PowerShellAuditlog.csv文件。</span><span class="sxs-lookup"><span data-stu-id="46d8f-174">For example, you would run the following two commands to add SharePoint file activities from the same date range to the PowerShellAuditlog.csv file.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a><span data-ttu-id="46d8f-175">导出和查看视图的审核日志</span><span class="sxs-lookup"><span data-stu-id="46d8f-175">Tips for exporting and viewing the audit log</span></span>

<span data-ttu-id="46d8f-176">下面是使用 JSON 转换功能将 **AuditData** 列拆分为多个审核日志之前和之后导出和查看列的一些提示和示例。</span><span class="sxs-lookup"><span data-stu-id="46d8f-176">Here are some tips and examples of exporting and viewing the audit log before and after you use the JSON transform feature to split the **AuditData** column into multiple columns.</span></span>

- <span data-ttu-id="46d8f-177">筛选 **RecordType** 列，以仅显示特定服务或功能区域中的记录。</span><span class="sxs-lookup"><span data-stu-id="46d8f-177">Filter the **RecordType** column to display only the records from a specific service or functional area.</span></span> <span data-ttu-id="46d8f-178">例如，若要显示与 SharePoint 共享相关的事件，请选择 **14** (SharePoint 共享活动触发的记录的枚举) 。</span><span class="sxs-lookup"><span data-stu-id="46d8f-178">For example, to show events related to SharePoint sharing, you would select **14** (the enum value for records triggered by SharePoint sharing activities).</span></span> <span data-ttu-id="46d8f-179">有关与 **RecordType** 列中显示的枚举值对应的服务列表，请参阅 "记录类型"[列中审核日志。](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="46d8f-179">For a list of the services that correspond to the enum values displayed in the **RecordType** column, see [Detailed properties in the audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span>

- <span data-ttu-id="46d8f-180">筛选 **"操作** "列以显示特定活动的记录。</span><span class="sxs-lookup"><span data-stu-id="46d8f-180">Filter the **Operations** column to display the records for specific activities.</span></span> <span data-ttu-id="46d8f-181">有关与安全 & 合规中心 审核日志 搜索工具中的可搜索活动对应的大多数操作的列表，请参阅安全与合规中心的 审核日志 中的"审核的活动 [&"部分](search-the-audit-log-in-security-and-compliance.md#audited-activities)。</span><span class="sxs-lookup"><span data-stu-id="46d8f-181">For a list of most operations that correspond to a searchable activity in the audit log search tool in the Security & Compliance Center, see the "Audited activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>
