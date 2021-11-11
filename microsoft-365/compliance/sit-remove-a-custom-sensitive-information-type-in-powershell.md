---
title: 使用 PowerShell 删除自定义敏感信息类型
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
description: 了解如何使用 PowerShell 删除自定义敏感信息类型
ms.openlocfilehash: bb3bf67a1493ec232a66b2bdc0c784ea52de32f5
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914400"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>使用 PowerShell 删除自定义敏感信息类型

在合规中心 PowerShell 中，有两种方法可以删除自定义敏感信息类型：

- **删除单个自定义敏感信息类型**：使用 PowerShell 修改自定义敏感信息类型 [中介绍的方法](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)。 导出包含自定义敏感信息类型的自定义规则包，从 XML 文件中删除敏感信息类型，将更新后的 XML 文件导入回现有的自定义规则包。

- 删除自定义规则包及其包含的所有自定义敏感信息类型：本部分介绍了此方法。

> [!NOTE]
> 删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。

1. [连接到合规中心 PowerShell](/powershell/exchange/exchange-online-powershell)

2. 若要删除自定义规则包，请使用 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet：

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   可使用 Name 值（适用于任何语言）或 `RulePack id` (GUID) 值来标识规则包。

   本示例删除名为“Employee ID Custom Rule Pack”的规则包。

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   有关语法和参数的详细信息，请参阅 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage)。

3. 若要验证是否已成功删除自定义敏感信息类型，请执行以下任意步骤：

   - 运行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet，验证规则包不再列出：

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - 运行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet，验证已删除的规则包中的敏感信息类型不再列出：

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     对于自定义敏感信息类型，Publisher 属性值将不是 Microsoft Corporation。

   - 将 \<Name\> 替换为敏感信息类型的 Name 值（例如，员工 ID），然后运行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet ，验证敏感信息类型是否不再列出：

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>更多信息

- [了解数据丢失防护](dlp-learn-about-dlp.md)

- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)

- [DLP 函数查找什么](what-the-dlp-functions-look-for.md)
