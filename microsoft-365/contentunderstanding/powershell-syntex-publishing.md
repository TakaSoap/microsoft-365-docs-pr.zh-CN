---
title: 使用 PowerShell 发布文档了解模型
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
description: 了解如何使用 PowerShell 发布SharePoint Syntex文档了解模型。
ms.openlocfilehash: 215a073ea5cabe7c701d24a9b8972268c4dd21ff
ms.sourcegitcommit: d37fce3b708ea5232b4102fd0e693f4bf17a8948
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2022
ms.locfileid: "62159693"
---
# <a name="publish-document-understanding-models-with-powershell"></a>使用 PowerShell 发布文档了解模型

> [!IMPORTANT]
> PowerShell cmdlet SharePoint Syntex所有其他 PnP 组件都是开源工具，由提供相关支持的活动社区提供支持。 没有来自 Microsoft 的官方支持渠道的开放源代码工具支持的 SLA。

SharePoint Syntex模型通常部署到租户中的文档库。 这可以使用内容中心网站完成，但也可使用 [PnP PowerShell](https://pnp.github.io/powershell/) 完成此操作，如本文所述。

## <a name="listing-the-available-models-in-a-content-center"></a>列出内容中心中的可用模型

若要概览添加到当前内容中心SharePoint Syntex模型，请使用[Get-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModel.html) cmdlet：

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModel
```

## <a name="apply-a-model-to-a-library"></a>将模型应用到库

若要将模型应用到库，请使用 [Publish-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Publish-PnPSyntexModel.html) cmdlet：

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Publish-PnPSyntexModel -Model "Contract Notice" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="understanding-where-a-model-is-used"></a>了解模型的使用位置

将模型部署到多个库后，你可能想要使用模型查看库列表。 这可以使用 [Get-PnPSyntexModelPublication](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModelPublication.html) cmdlet 完成：

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModelPublication -Identity "Contract Notice"
```

## <a name="removing-a-model-from-a-library"></a>从库中删除模型

从库中删除模型与应用模式相同，可以使用 [Unpublish-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Unpublish-PnPSyntexModel.html) cmdlet 以交互方式或作为多个操作批处理完成。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourSite"
Unpublish-PnPSyntexModel -Model "Invoice model" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="apply-models-in-bulk"></a>批量应用模型

如果要将多个模型发布到多个库，请创建一个输入 CSV 文件，列出模型和目标位置：

```CSV
ModelName,TargetSiteUrl,TargetWebServerRelativeUrl,TargetLibraryServerRelativeUrl
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/shared%20documents
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/other
Trade Confirmation,https://contoso.sharepoint.com/sites/Site2,/sites/Site2,/sites/site2/shared%20documents
```

然后，此 CSV 文件可以用作脚本的输入，该脚本将列出模型发布到相应的库。 在下面的示例中，批处理用于提高请求的效率。

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourSite"
$targetsCSV = "./Publish-SyntexModelBulk.csv"

Connect-PnPOnline -url $contentCenterURL

$targetLibraries = Import-Csv -Path $targetsCSV

$batch = New-PnPBatch

foreach ($target in $targetLibraries) {
    Publish-PnPSyntexModel -Model $target.ModelName -TargetSiteUrl $target.TargetSiteUrl -TargetWebServerRelativeUrl $target.TargetWebServerRelativeUrl -TargetLibraryServerRelativeUrl $target.TargetLibraryServerRelativeUrl -Batch $batch
}

Invoke-PnPBatch -Batch $batch
```
