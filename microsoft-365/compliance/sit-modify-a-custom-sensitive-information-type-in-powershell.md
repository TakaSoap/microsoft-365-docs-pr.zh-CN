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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用 PowerShell 修改自定义敏感信息。
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322497"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="cee75-103">使用 PowerShell 修改自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="cee75-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="cee75-104">在合规中心 PowerShell 中，若要修改自定义敏感信息类型，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cee75-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="cee75-105">将包含自定义敏感信息类型的现有规则包导出到 XML 文件（或者，如果已有 XML 文件，则使用它）。</span><span class="sxs-lookup"><span data-stu-id="cee75-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="cee75-106">修改导出的 XML 文件中的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="cee75-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="cee75-107">将更新的 XML 文件导回现有规则包。</span><span class="sxs-lookup"><span data-stu-id="cee75-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="cee75-108">若要连接到合规中心 PowerShell，请参阅[连接到合规中心 PowerShell](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cee75-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="cee75-109">步骤 1：将现有的规则包导出到 XML 文件</span><span class="sxs-lookup"><span data-stu-id="cee75-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="cee75-110">如果有 XML 文件的副本 （例如，只需创建并导入它），可跳到下一步来修改 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="cee75-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="cee75-111">如果你还不确定，请运行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet，查找自定义规则包的名称：</span><span class="sxs-lookup"><span data-stu-id="cee75-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="cee75-p101">包含内置敏感信息类型的内置规则包名为 Microsoft Rule Package。包含你在合规中心 UI 中创建的自定义敏感信息类型的规则包名为 Microsoft.SCCManaged.CustomRulePack。</span><span class="sxs-lookup"><span data-stu-id="cee75-p101">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="cee75-114">使用 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet，将自定义规则包存储到变量：</span><span class="sxs-lookup"><span data-stu-id="cee75-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="cee75-115">例如，如果规则包的名称是“Employee ID Custom Rule Pack”，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="cee75-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="cee75-116">使用 [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet 将自定义规则包导出到 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="cee75-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="cee75-117">本示例将规则包导出到 C:\My Documents 文件夹中名为 ExportedRulePackage.xml 的文件。</span><span class="sxs-lookup"><span data-stu-id="cee75-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="cee75-118">步骤 2：修改导出的 XML 文件中的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="cee75-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="cee75-119">本文前面介绍了 XML 文件中的敏感信息类型和文件中的其他元素。</span><span class="sxs-lookup"><span data-stu-id="cee75-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="cee75-120">步骤 3：将更新的 XML 文件导回现有规则包。</span><span class="sxs-lookup"><span data-stu-id="cee75-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="cee75-121">若要将更新的 XML 导回现有规则包，请使用 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet：</span><span class="sxs-lookup"><span data-stu-id="cee75-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="cee75-122">有关语法和参数的详细信息，请参阅 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage)。</span><span class="sxs-lookup"><span data-stu-id="cee75-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="cee75-123">更多信息</span><span class="sxs-lookup"><span data-stu-id="cee75-123">More information</span></span>

- [<span data-ttu-id="cee75-124">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="cee75-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="cee75-125">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="cee75-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="cee75-126">DLP 函数查找什么</span><span class="sxs-lookup"><span data-stu-id="cee75-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
