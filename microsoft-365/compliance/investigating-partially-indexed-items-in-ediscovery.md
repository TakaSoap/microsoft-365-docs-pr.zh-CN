---
title: 在电子数据展示中调查部分索引项目
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: 了解如何从组织内的 Exchange、SharePoint 和 OneDrive for Business 中管理部分索引的 (或未编制索引的) 项目。
ms.openlocfilehash: 132a174f0c163c75939b75906baa3833c6387fa7
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588559"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a>在电子数据展示中调查部分索引项目

在运行搜索时，从 Microsoft 365 合规中心运行的电子数据展示搜索将自动包含在估计的搜索结果中部分索引的项目。 部分索引项目是指 SharePoint 和 OneDrive for business 网站上的 Exchange 邮箱项目和文档，因为某些原因未完全编制搜索索引。 大多数电子邮件和网站文档都已成功编制索引，因为它们位于 [电子邮件的索引限制](limits-for-content-search.md#indexing-limits-for-email-messages)内。 但是，某些项目可能超出这些索引限制，将对其进行部分索引。 以下是在运行电子数据展示搜索时，无法将项目编入索引并作为部分索引项目返回的其他原因：
  
- 电子邮件有一个没有有效处理程序的附加文件，如图像文件;这是部分索引的电子邮件项的最常见原因。

- 附加到电子邮件的文件过多。

- 附加到电子邮件的文件过大。

- 文件类型支持检索，但是特定文件出现检索错误。

尽管它不同，但大多数组织的内容的数量少于1%，而按部分索引的大小少于12% 的内容。 卷与大小之间的差异在于，较大的文件包含无法完全编制索引的内容的可能性较高。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>对于搜索，部分索引项目数的变化是什么？

在运行电子数据展示搜索后，搜索位置中的部分索引项目的总数和大小将列在搜索结果统计信息中，并显示在搜索的详细统计信息中。 请注意，这些项在搜索统计信息中称为未  *编制索引的项*  。 下面几项操作将影响在搜索结果中返回的部分已编制索引项的数目：
  
- 如果某个项目已部分编制了索引，并且与搜索查询相匹配，则会将其包含在 (的计数和) 的搜索结果项目和部分索引项目的大小。 但是，当导出相同搜索的结果时，该项目仅包含在一组搜索结果中;它不包含为部分索引项。

- 如果为搜索查询指定日期范围 (通过将其包含在关键字查询中，或使用条件) ，则不符合日期范围的任何部分索引项将不包含在部分索引项的计数中。 索引项计数中仅包含在日期范围内的部分已编制索引的项。

  > [!NOTE]
  > 位于 SharePoint 和 OneDrive 网站中的部分索引项 *不* 包含在搜索的详细统计信息中显示的部分索引项的估计中。 但是，在导出电子数据展示搜索结果时，可以导出部分索引的项目。 例如，如果您仅搜索网站，估计的数字部分索引项将为零。
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>计算组织中部分索引项目的比率

若要了解组织对部分索引项目的暴露程度，可以使用空白关键字查询) 在所有邮箱 (中运行所有内容的搜索。 在下面的示例中，有 56208 (4830 MB) 完全索引项，并 470 (316 MB) 部分索引项。
  
![显示部分索引项目的搜索统计信息示例](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
您可以使用以下计算来确定部分索引项目的百分比。
  
 **若要计算组织中部分索引项目的比率，请执行以下操作：**

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

通过使用上一示例中的搜索结果，将对所有邮箱项目的84% 进行部分索引。
  
 **若要计算组织中部分索引项目大小的百分比，请执行以下操作：**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

所以在上一示例中，邮箱项目总大小的6.54% 来自部分索引项目。 如前所述，大多数组织的内容数量少于1%，而按部分索引的大小少于12% 的内容。

## <a name="working-with-partially-indexed-items"></a>使用部分索引项目

在需要检查部分项目以验证它们不包含相关信息的情况下，您可以导出包含部分索引项目相关信息的 [内容搜索报告](export-a-content-search-report.md) 。 导出内容搜索报告时，请务必选择包含部分索引项目的导出选项之一。
  
![选择第二个或第三个选项以导出部分索引项目](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
当您使用这些选项之一导出电子数据展示搜索结果或搜索报告时，该导出会包含一个名为 "未编制索引 Items.csv" 的报表。 此报告包含与 ResultsLog.csv 文件相同的大部分信息;但是，未编制索引的 Items.csv 文件还包含与部分索引项目相关的两个字段： **错误标记** 和 **错误属性**。 这些字段包含有关每个部分索引项的索引错误的信息。 使用这两个字段中的信息可帮助您确定您的调查是否有特定影响的索引错误。 如果这样做，您可以执行目标搜索并检索和导出特定的电子邮件和 SharePoint 或 OneDrive 文档，以便您可以对其进行检查以确定它们是否与您的调查相关。 有关分步说明，请参阅为 [Office 365 中的目标搜索准备 CSV 文件](csv-file-for-an-id-list-content-search.md)。

> [!NOTE]
> 未编制索引的 Items.csv 文件还包含名为 " **错误类型** " 和 " **错误消息**" 的字段。 这些字段包含的信息与 " **错误标记** " 和 " **错误属性** " 字段中的信息类似，但详细信息较少。 您可以安全地忽略这些旧字段。
  
## <a name="errors-related-to-partially-indexed-items"></a>与部分索引项目相关的错误

错误标记由两条信息组成，即错误和文件类型。 例如，在此错误/文件类型对：

```text
 parseroutputsize_xls
```

 `parseroutputsize` 是错误， `xls` 是发生错误的文件的文件类型。 在无法识别文件类型或文件类型不适用于该错误的情况下，您将看到 `noformat` 文件类型的替换值。
  
下面列出了索引错误和可能的错误原因的说明。
  
| 错误标记 | Description |
|:-----|:-----|
| `attachmentcount` <br/> |电子邮件的附件过多，其中一些附件未处理。  <br/> |
| `attachmentdepth` <br/> |内容检索器和文档分析程序发现嵌套在其他附件中的附件级别过多。 其中一些附件未处理。  <br/> |
| `attachmentrms` <br/> |由于受 RMS 保护，附件无法进行解码。  <br/> |
| `attachmentsize` <br/> |附加到电子邮件的文件太大，无法处理。  <br/> |
| `indexingtruncated` <br/> |将已处理的电子邮件写入索引时，其中一个可索引的属性太大，已被截尾取整。 截断的属性在 "错误属性" 字段中列出。  <br/> |
| `invalidunicode` <br/> |电子邮件包含无法处理为有效 Unicode 的文本。 此项的索引可能不完整。  <br/> |
| `parserencrypted` <br/> |附件或电子邮件的内容已加密，Microsoft 365 无法对内容进行解码。  <br/> |
| `parsererror` <br/> |分析过程中出现未知错误。 这通常是由于软件错误或服务崩溃造成的。  <br/> |
| `parserinputsize` <br/> |由于附件太大，分析程序无法处理该附件，并且该附件的分析未发生或未完成。  <br/> |
| `parsermalformed` <br/> |附件格式不正确，无法由分析器进行处理。 此结果可能是由于旧文件格式、由不兼容软件创建的文件或假装为其他内容的病毒所致。  <br/> |
| `parseroutputsize` <br/> |对附件解析的输出太大，必须将其截断。  <br/> |
| `parserunknowntype` <br/> |附件的文件类型为 Microsoft 365 无法检测到的文件类型。  <br/> |
| `parserunsupportedtype` <br/> |附件具有 Office 365 可以检测到的文件类型，但分析该文件类型不受支持。  <br/> |
| `propertytoobig` <br/> |Exchange 存储中的电子邮件属性的值太大，无法检索，并且无法处理邮件。 这通常只发生在电子邮件的 body 属性中。  <br/> |
| `retrieverrms` <br/> |内容检索器无法对受 RMS 保护的邮件进行解码。  <br/> |
| `wordbreakertruncated` <br/> |编制索引期间在文档中标识了过多的单词。 属性处理在达到限制时停止，属性被截断。  <br/> |

"错误" 域说明 "错误标记" 字段中列出的处理错误会影响哪些字段。 如果您正在搜索属性（例如  `subject` 或  `participants` ），则邮件正文中的错误不会影响您的搜索结果。 当准确确定可能需要进一步调查的部分已编制索引项时，这可能很有用。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>使用 PowerShell 脚本确定组织部分索引的电子邮件项的公开程度

下面的步骤演示了如何运行在所有 Exchange 邮箱中搜索所有项目的 PowerShell 脚本，然后生成有关组织的部分索引的电子邮件项目 (按计数和大小) 的比率的报告，并显示每个出现的索引错误 (的项目数和文件类型) 。 使用上一节中的错误标记说明来标识索引错误。
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如， `PartiallyIndexedItems.ps1` 。

```powershell
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
```

2. [连接到安全与合规中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。

3. 在安全 & 合规性中心 PowerShell 中，转到在步骤1中保存脚本的文件夹，然后运行该脚本;例如：

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

下面的示例展示了脚本返回的输出。
  
![生成来自组织公开的报告的脚本的输出示例，以部分索引的电子邮件项目](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
请注意以下事项：
  
1. 电子邮件项目的总数和大小，以及按计数和大小 (的部分索引的电子邮件项目的组织比率) 

2. 列表错误标记以及发生错误的相应文件类型。
  
## <a name="see-also"></a>另请参阅

[电子数据展示中的部分索引项](partially-indexed-items-in-content-search.md)
