---
title: 调查电子数据展示中的部分索引项
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: 了解如何管理来自组织中 (、) 、SharePoint Exchange 和 OneDrive for Business 部分索引项。
ms.openlocfilehash: 5160a46e6be825dd858be030fc5cf5941734e65d
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586309"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a>调查电子数据展示中的部分索引项

从搜索运行电子数据展示搜索Microsoft 365 合规中心运行搜索时，自动将部分索引项包括在估计的搜索结果中。 部分索引项目Exchange邮箱项目和文档SharePoint OneDrive for Business由于某种原因未完全编制索引进行搜索的邮箱项目和文档。 大多数电子邮件和网站文档都已成功编制索引，因为它们在电子邮件 [的索引限制范围内](limits-for-content-search.md#indexing-limits-for-email-messages)。 但是，某些项目可能会超出这些索引限制，并且将被部分索引。 以下是在运行电子数据展示搜索时无法对项目编制索引并作为部分索引项返回的其他原因：
  
- 电子邮件具有无法打开的附加文件，如图像文件;这是部分索引电子邮件项目的最常见原因。

- 附加到电子邮件的文件过多。

- 附加到电子邮件的文件过大。

- 文件类型支持检索，但是特定文件出现检索错误。

尽管内容量不同，但大多数组织客户的内容量少于 1%，而按内容大小（部分索引）小于 12%。 卷与大小之间的区别在于，较大的文件包含无法完全编制索引的内容的可能性较高。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>为什么部分索引项计数会更改搜索？

运行电子数据展示搜索后，搜索位置中部分索引项的总数和大小将在搜索结果统计信息中列出，搜索结果统计信息显示在搜索的详细统计信息中。 请注意，这些  *项在搜索统计信息*  中称为未索引项。 下面是将影响搜索结果中返回的部分索引项数的一些事项：
  
- 如果某个项目已部分编制索引且与搜索查询匹配，则该项目将包含在搜索结果项的计数 (和) 索引项的大小限制中。 但是，导出同一搜索的结果时，该项目仅包含在一组搜索结果中;它不包含为部分索引项。

- 位于网站和网站SharePoint OneDrive部分索引项不包括在搜索的详细统计信息中显示的部分索引项的估计值中。 但是，在导出电子数据展示搜索的结果时，可以导出部分索引项。 例如，如果您仅搜索网站，则估计的部分索引项数将为 0。
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>计算组织中部分索引项的比率

若要了解组织对部分索引项目的暴露情况，可以使用空白关键字查询查询来运行对 (邮箱中所有内容) 。 在下面的示例中，有 1，629，904 (146.46 GB) 完全索引项和 10，025 (10.27 GB) 部分索引项。
  
![显示部分索引项的搜索统计信息示例。](../media/PartiallyIndexedItemsTest.png)
  
可以使用以下计算来确定部分索引项的百分比。
  
 **要计算组织中部分索引项的比率，请执行以下各项：**

`(Total number of partially indexed items/Total number of items) x 100`

`(10025/1629904) x 100 = 0.62%`

通过使用上一示例中的搜索结果，0.62% 的邮箱项目已部分编制索引。
  
 **若要计算组织中部分索引项大小的百分比，请执行以下设置：**

`(Size of all partially indexed items/Size of all items) x 100`

`(10.27 GB/146.46 GB) x 100 = 7.0%`

因此，在上一示例中，邮箱项目总大小的 7% 来自部分索引项目。 如前所述，大多数组织客户的内容量少于 1%，而按内容大小（部分索引）则少于 12%。

## <a name="working-with-partially-indexed-items"></a>处理部分索引项

在需要检查部分索引项以验证它们不包含相关信息的情况下，可以导出包含部分索引项相关信息的内容搜索报告。 [](export-a-content-search-report.md) 导出内容搜索报告时，请确保选择包含部分索引项的导出选项之一。
  
![选择第二个或第三个选项导出部分索引项。](../media/PartiallyIndexedItemsExportOptions.png)
  
使用这些选项之一导出电子数据展示搜索结果或搜索报告时，导出包括名为 Unindexed Items.csv。 此报告包括与文件相同的大部分ResultsLog.csv信息;但是，Unindexed Items.csv还包括两个与部分索引项相关的字段： **错误标记** 和 **错误属性**。 这些字段包含有关每个部分索引项的索引错误的信息。 使用这两个字段中的信息可以帮助您确定特定字段的索引错误是否会影响调查。 如果是这样，您可以执行定向搜索，并检索和导出特定电子邮件和 SharePoint 或 OneDrive 文档，以便您可以检查它们以确定它们是否与调查相关。 有关分步说明，请参阅在 Office 365 中为目标搜索[准备 CSV Office 365。](csv-file-for-an-id-list-content-search.md)

> [!NOTE]
> Unindexed Items.csv还包含名为 **Error Type** 和 Error **Message 的字段**。 这些是旧字段，包含的信息与"**错误** 标记"和"错误属性"字段中的信息类似，但信息不太详细。 可以安全地忽略这些旧字段。
  
## <a name="errors-related-to-partially-indexed-items"></a>与部分索引项相关的错误

错误标记由两条信息（错误和文件类型）决定。 例如，在此错误/文件类型对中：

```text
 parseroutputsize_xls
```

 `parseroutputsize` 是错误 `xls` ，也是发生错误的文件的文件类型。 如果无法识别文件类型或文件类型未应用于错误，则会看到值来表示文件类型 `noformat` 。
  
下面列出了索引错误以及错误可能原因的说明。
  
| 错误标记 | 说明 |
|:-----|:-----|
| `attachmentcount` <br/> |电子邮件的附件过多，其中一些附件未处理。  <br/> |
| `attachmentdepth` <br/> |内容检索和文档分析程序发现嵌套在其他附件中的附件级别过多。 其中某些附件未处理。  <br/> |
| `attachmentrms` <br/> |附件解码失败，因为它受 RMS 保护。  <br/> |
| `attachmentsize` <br/> |附加到电子邮件的文件太大，无法处理。  <br/> |
| `indexingtruncated` <br/> |将已处理的电子邮件写入索引时，其中一个可编制索引的属性太大，被截断。 截断的属性列在"错误属性"字段中。  <br/> |
| `invalidunicode` <br/> |电子邮件包含无法作为有效 Unicode 处理的文本。 此项的索引编制可能不完整。  <br/> |
| `parserencrypted` <br/> |附件或电子邮件的内容已加密，Microsoft 365无法解码内容。  <br/> |
| `parsererror` <br/> |分析过程中出现未知错误。 这通常由软件 Bug 或服务崩溃导致。  <br/> |
| `parserinputsize` <br/> |附件太大，分析程序无法处理，并且该附件的解析未发生或未完成。  <br/> |
| `parsermalformed` <br/> |附件格式不正确，无法由分析程序处理。 此结果可能是由于文件格式旧、不兼容的软件创建的文件或冒充声明的病毒。  <br/> |
| `parseroutputsize` <br/> |分析附件的输出太大，必须截断。  <br/> |
| `parserunknowntype` <br/> |附件的文件类型Microsoft 365无法检测。  <br/> |
| `parserunsupportedtype` <br/> |附件具有可检测到Office 365的文件类型，但不支持分析该文件类型。  <br/> |
| `propertytoobig` <br/> |邮件存储中的电子邮件Exchange太大，无法检索，且无法处理邮件。 这通常仅适用于电子邮件的 body 属性。  <br/> |
| `retrieverrms` <br/> |内容检索器无法解码受 RMS 保护的邮件。  <br/> |
| `wordbreakertruncated` <br/> |在编制索引期间，文档中标识的单词过多。 当达到限制时，将停止对属性的处理，并且该属性将被截断。  <br/> |

错误字段描述哪些字段受"错误标记"字段中列出的处理错误的影响。 如果要搜索诸如 或 等属性，邮件正文中的错误不会影响  `subject`  `participants` 搜索结果。 当准确确定哪些部分索引项可能需要进一步调查时，这可能很有用。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>使用 PowerShell 脚本确定组织对部分索引电子邮件项目的曝光

以下步骤显示如何运行 PowerShell 脚本，该脚本在所有 Exchange 邮箱中搜索所有项目，然后按计数和大小) 生成有关组织部分索引电子邮件项目 (的比率的报告) 并显示发生的每个索引错误的项目数 (及其文件类型) 。 使用上一节中的错误标记说明来标识索引错误。
  
1. 将以下文本保存到Windows PowerShell脚本文件中，使用文件名后缀 .ps1;例如， `PartiallyIndexedItems.ps1` 。

   ```powershell
     write-host "**************************************************"
     write-host "     Security & Compliance Center PowerShell      " -foregroundColor yellow -backgroundcolor darkgreen
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

2. [连接到安全与合规中心 PowerShell](/powershell/exchange/exchange-online-powershell)。

3. 在安全&合规中心 PowerShell 中，转到步骤 1 中保存脚本的文件夹，然后运行脚本;例如：

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

下面是脚本返回的输出的示例。
  
![脚本的输出示例，该脚本生成有关组织对部分索引电子邮件项目的曝光的报告。](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> 请注意以下几点：
>  
> - 电子邮件项目的总数和大小，以及组织部分索引电子邮件项目的比率 (计数和大小) 。
> 
> - 列表错误标记和发生错误的相应文件类型。
  
## <a name="see-also"></a>另请参阅

[电子数据展示中的部分索引项](partially-indexed-items-in-content-search.md)
