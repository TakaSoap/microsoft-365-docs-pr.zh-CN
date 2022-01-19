---
title: 使用 PowerShell 请求文档理解模型进行处理
ms.author: jaeccles
author: jameseccles
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: normal
description: 了解如何使用 PowerShell 请求文档SharePoint Syntex处理。
ms.openlocfilehash: a4bdf9b450306686d19218e13a7a708b37fdb04e
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074807"
---
# <a name="use-powershell-to-request-processing-by-a-document-understanding-model"></a>使用 PowerShell 请求文档理解模型进行处理

> [!IMPORTANT]
> PowerShell cmdlet SharePoint Syntex所有其他 PnP 组件都是开源工具，由提供支持的活动社区提供支持。 没有来自 Microsoft 的官方支持渠道的开放源代码工具支持的 SLA。

了解模型的文档将处理新上载到库的文件。 还可以在 UI 中手动请求处理。 但是，在某些情况下，通过 PowerShell 触发处理会更有效。

## <a name="request-processing-of-all-items-that-have-not-been-previously-classified"></a>请求处理以前未分类的所有项目

可以使用以下命令请求处理库中以前未分类的所有项目：

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents"
```

对于优先级较低的处理，还可以考虑使用 -OffPeak 参数，这将对文件进行排队，以在租户所在的工作时间之外进行处理。 有关详细信息[，请参阅 Request-PnPSyntexClassifyAndExtract。](https://pnp.github.io/powershell/cmdlets/Request-PnPSyntexClassifyAndExtract.html)

## <a name="request-processing-of-all-items-in-a-library"></a>请求处理库中的所有项目

你可以请求处理库内的所有文件，即使这些文件之前已分类。 如果你已更新模型或向库添加了其他模型，这可能很有用。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents" -Force
```

> [!NOTE]
> 将 -Force 选项用于超过 5000 个项目将能自动启用非高峰处理。

## <a name="request-processing-of-all-items-based-on-a-property"></a>基于属性请求处理所有项目

如果要将处理限制为库中的特定项目子集，可以使用脚本选择一组特定文件。 在下面的示例中，该脚本允许选择一个字段，以及一个字段值进行筛选。 可以使用 [Get-PnPListItem](https://pnp.github.io/powershell/cmdlets/Get-PnPListItem.html)完成更复杂的查询。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"
$list = Get-PnPList -Identity "Documents"
# Set the field name to filter items by
$fieldName = "Vendor"
# Set the field value to filter by
$fieldFilter = "Fabrikam"

$listItems = (Get-PnPListItem -List $list -fields $fieldName).fieldValues
$targetItems = $listItems | Where-Object -Property Provider -EQ -Value $fieldFilter

# Create a new batch
$batch = New-PnPBatch

# Add files to classify to the batch
foreach ($listItem in $targetItems) {
    Request-PnPSyntexClassifyAndExtract -FileUrl $listItem.FileRef -Batch $classifyBatch
}

# Execute batch
Invoke-PnPBatch -Batch $batch
```

## <a name="request-processing-of-specific-files"></a>请求处理特定文件

也可以请求处理特定文件。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/contoso contract.docx"
```

按文件模型的文件还支持批处理：

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

# Create a new batch
$batch = New-PnPBatch

# Add files to classify to the batch
Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/contoso contract.docx" -Batch $batch
Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/relecloud contract.docx" -Batch $batch

# Execute batch
Invoke-PnPBatch -Batch $batch
```
