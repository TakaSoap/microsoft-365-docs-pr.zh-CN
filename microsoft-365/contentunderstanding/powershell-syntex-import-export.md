---
title: 使用 PowerShell 导出和导入了解模型的文档
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
description: 了解如何在 SharePoint Syntex 中通过 PowerShell 导出和导入文档理解SharePoint Syntex
ms.openlocfilehash: 289d802fdea50daa0261ec16ea760e9a57b0e9c5
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074823"
---
# <a name="export-and-import-document-understanding-models-with-powershell"></a>使用 PowerShell 导出和导入了解模型的文档

> [!IMPORTANT]
> PowerShell cmdlet SharePoint Syntex所有其他 PnP 组件都是开源工具，由提供相关支持的活动社区提供支持。 没有来自 Microsoft 的官方支持渠道的开放源代码工具支持的 SLA。

SharePoint Syntex模型可以导出为 PnP 模板，从而实现跨内容中心或租户重用。

## <a name="export-all-models-in-a-content-center"></a>导出内容中心内的所有模型

若要将内容中心内的所有模型导出到单个 PnP 模板，请使用以下 [PnP PowerShell](https://pnp.github.io/powershell/) cmdlet：

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Handlers SyntexModels
```

## <a name="export-specific-models"></a>导出特定模型

若要将特定模型从内容中心导出到 PnP 模板，请使用以下 [PnP PowerShell](https://pnp.github.io/powershell/) cmdlet：

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Configuration .\extract.json
```

extract.json 定义要导出的模型，允许按名称或 ID 指定模型，并可以选择配置为不提取培训数据

### <a name="example--specify-model-by-name"></a>示例 - 按名称指定模型

```json
{
    "$schema": "https://developer.microsoft.com/en-us/json-schemas/pnp/provisioning/202102/extract-configuration.schema.json",
    "persistAssetFiles": true,
    "handlers": [        
        "SyntexModels"
    ],
    "syntexModels": {
        "models": [
            {
                "name": "Sample - benefits change notice.classifier"
            }
        ]
    }
}
```

### <a name="example--specify-model-by-id"></a>示例 - 按 ID 指定模型

```json
{
    "$schema": "https://developer.microsoft.com/en-us/json-schemas/pnp/provisioning/202102/extract-configuration.schema.json",
    "persistAssetFiles": true,
    "handlers": [        
        "SyntexModels"
    ],
    "syntexModels": {
        "models": [
            {
                "id": 3,
                "excludeTrainingData": true
            }
        ]
    }
}
```

如果不包括属性"includeTrainingData"，则默认行为是包含 。

> 注意：将模型导入目标内容中心时，需要培训数据才能编辑模型

## <a name="import-models-to-a-content-center"></a>将模型导入到内容中心
可以将已导出到 PnP 模板的文档了解模型导入到任何租户上的内容中心。 如果导出包括培训数据，则导入后模型可编辑。

若要导入模型，请使用以下命令：

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Invoke-PnPSiteTemplate -Path .\sampleModel.pnp
```
