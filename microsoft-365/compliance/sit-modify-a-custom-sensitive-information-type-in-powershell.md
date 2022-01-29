---
title: 使用 PowerShell 修改自定义敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用 PowerShell 修改自定义敏感信息。
ms.openlocfilehash: d402586463da1bed13d15dbaa32aece6badc9c72
ms.sourcegitcommit: 99067d5eb1fa7b094e7cdb1f7be65acaaa235a54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2022
ms.locfileid: "62271486"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>使用 PowerShell 修改自定义敏感信息类型

在合规中心 PowerShell 中，若要修改自定义敏感信息类型，需要执行以下操作：

1. 将包含自定义敏感信息类型的现有规则包导出到 XML 文件（或者，如果已有 XML 文件，则使用它）。

2. 修改导出的 XML 文件中的自定义敏感信息类型。

3. 将更新的 XML 文件导回现有规则包。

若要连接到合规中心 PowerShell，请参阅[连接到合规中心 PowerShell](/powershell/exchange/exchange-online-powershell)。

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>步骤 1：将现有的规则包导出到 XML 文件

> [!NOTE]
> 如果有 XML 文件的副本 （例如，只需创建并导入它），可跳到下一步来修改 XML 文件。

1. 如果你还不确定，请运行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet，查找自定义规则包的名称：

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > 包含内置敏感信息类型的内置规则包名为 Microsoft Rule Package。包含你在合规中心 UI 中创建的自定义敏感信息类型的规则包名为 Microsoft.SCCManaged.CustomRulePack。

2. 使用 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet，将自定义规则包存储到变量：

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   例如，如果规则包的名称是“Employee ID Custom Rule Pack”，请运行以下 cmdlet：

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. 使用以下语法将自定义规则包导出到 XML 文件：

   ```powershell
   [System.IO.File]::WriteAllBytes('XMLFileAndPath', $rulepak.SerializedClassificationRuleCollection)
   ```

   本示例将规则包导出到 C:\My Documents 文件夹中名为 ExportedRulePackage.xml 的文件。

   ```powershell
   [System.IO.File]::WriteAllBytes('C:\My Documents\ExportedRulePackage.xml', $rulepak.SerializedClassificationRuleCollection)
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>步骤 2：修改导出的 XML 文件中的敏感信息类型

本文前面介绍了 XML 文件中的敏感信息类型和文件中的其他元素。

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>步骤 3：将更新的 XML 文件导回现有规则包。

若要将更新的 XML 导回现有规则包，请使用 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet：

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('C:\My Documents\External Sensitive Info Type Rule Collection.xml'))
```

有关语法和参数的详细信息，请参阅 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage)。

## <a name="more-information"></a>更多信息

- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [DLP 函数查找什么](what-the-dlp-functions-look-for.md)
