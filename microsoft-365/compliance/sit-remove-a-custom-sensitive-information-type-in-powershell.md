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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用 PowerShell 删除自定义敏感信息类型
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322496"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="49db7-103">使用 PowerShell 删除自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="49db7-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="49db7-104">在合规中心 PowerShell 中，有两种方法可以删除自定义敏感信息类型：</span><span class="sxs-lookup"><span data-stu-id="49db7-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="49db7-105">**删除单个自定义敏感信息类型**：使用 PowerShell 修改自定义 [敏感信息类型中介绍的方法](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="49db7-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="49db7-106">导出包含自定义敏感信息类型的自定义规则包，从 XML 文件中删除敏感信息类型，将更新后的 XML 文件导入回现有的自定义规则包。</span><span class="sxs-lookup"><span data-stu-id="49db7-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="49db7-107">删除自定义规则包及其包含的所有自定义敏感信息类型：本部分介绍了此方法。</span><span class="sxs-lookup"><span data-stu-id="49db7-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="49db7-108">删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="49db7-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. [<span data-ttu-id="49db7-109">连接到合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="49db7-109">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="49db7-110">若要删除自定义规则包，请使用 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet：</span><span class="sxs-lookup"><span data-stu-id="49db7-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="49db7-111">可使用 Name 值（适用于任何语言）或 `RulePack id` (GUID) 值来标识规则包。</span><span class="sxs-lookup"><span data-stu-id="49db7-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="49db7-112">本示例删除名为“Employee ID Custom Rule Pack”的规则包。</span><span class="sxs-lookup"><span data-stu-id="49db7-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="49db7-113">有关语法和参数的详细信息，请参阅 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage)。</span><span class="sxs-lookup"><span data-stu-id="49db7-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="49db7-114">若要验证是否已成功删除自定义敏感信息类型，请执行以下任意步骤：</span><span class="sxs-lookup"><span data-stu-id="49db7-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="49db7-115">运行 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet，验证规则包不再列出：</span><span class="sxs-lookup"><span data-stu-id="49db7-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="49db7-116">运行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet，验证已删除的规则包中的敏感信息类型不再列出：</span><span class="sxs-lookup"><span data-stu-id="49db7-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="49db7-117">对于自定义敏感信息类型，Publisher 属性值将不是 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="49db7-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="49db7-118">将 \<Name\> 替换为敏感信息类型的 Name 值（例如，员工 ID），然后运行 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet ，验证敏感信息类型是否不再列出：</span><span class="sxs-lookup"><span data-stu-id="49db7-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="49db7-119">更多信息</span><span class="sxs-lookup"><span data-stu-id="49db7-119">More information</span></span>

- [<span data-ttu-id="49db7-120">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="49db7-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="49db7-121">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="49db7-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="49db7-122">DLP 函数查找什么</span><span class="sxs-lookup"><span data-stu-id="49db7-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
