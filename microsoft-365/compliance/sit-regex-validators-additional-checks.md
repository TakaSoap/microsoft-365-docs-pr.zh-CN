---
title: 敏感信息类型 REGEX 验证程序和其他检查
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在已发送的信息类型中使用 REGEX 验证程序和其他检查。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 615d4757be16b3171005105aea8148536e6f3015
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2022
ms.locfileid: "62902591"
---
# <a name="sensitive-information-type-regex-validators-and-additional-check"></a>敏感信息类型 REGEX 验证程序和其他检查

> [!IMPORTANT]
> 在创建自定义分类或正则表达式模式时，不可从 Microsoft 客户服务和支持获取帮助。 支持工程师可对功能提供有限的支持，例如提供用于测试目的的示例正则表达式，或者帮助排查未如期触发的现有正则表达式模式的问题，但无法保证所有自定义内容匹配开发都将满足你的要求或义务。

## <a name="sensitive-information-type-regular-expression-validators"></a>敏感信息类型正则表达式验证程序

### <a name="checksum-validator"></a>校验和验证程序

如果需要对正则表达式中的数字运行校验和，可以使用 *校验和验证程序*。 例如，假设你需要为八位数的许可证号码创建 SIT，其中最后一个数字是校验和数字，使用 mod 9 计算进行验证。 你已设置校验和算法，如下所示：

```console
Sum = digit 1 * Weight 1 + digit 2 * weight 2 + digit 3 * weight 3 + digit 4 * weight 4 + digit 5 * weight 5 + digit 6 * weight 6 + digit 7 * weight 7 + digit 8 * weight 8
Mod value = Sum % 9
If Mod value == digit 8
    Account number is valid
If Mod value != digit 8
    Account number is invalid
```

1. 定义具有此正则表达式的主元素：

   ```console
   \d{8}
   ```

2. 然后添加校验和验证程序。

3. 添加用逗号分隔的权重值、检查数字的位置和 Mod 值。 有关 Modulo 操作详细信息，请参阅 [Modulo 操作](https://en.wikipedia.org/wiki/Modulo_operation)。

   > [!NOTE]
   > 如果校验位不是校验和计算的一部分，则使用 0 作为校验位的权重。 例如，如果检查数字不用于计算检查数字，则上述情况下权重 8 将等于 0。

   :::image type="content" alt-text="配置的校验和验证器的屏幕截图。" source="../media/checksum-validator.png" lightbox="../media/checksum-validator.png":::

### <a name="date-validator"></a>日期验证程序

如果嵌入在正则表达式中的日期值是正在创建的新模式的一部分，可以使用日期验证程序测试它是否满足您的条件。 例如，假设你要为九位数的员工标识号创建 SIT。 前六个数字是 DDMMYY 格式的雇用日期，最后三个数字是随机生成的数字。 验证前六个数字的格式是否正确。

1. 定义具有此正则表达式的主元素：

   ```console
   \d{9}
   ```

2. 然后添加日期验证程序。

3. 选择日期格式和开始偏移。 由于日期字符串是前六个数字，因此偏移量是 `0`。

   :::image type="content" alt-text="已配置日期验证器的屏幕截图。" source="../media/date-validator.png" lightbox="../media/date-validator.png":::

### <a name="functional-processors-as-validators"></a>作为验证程序的功能处理器

你可以对一些最常用的 SIT 使用函数处理器作为验证程序。 这允许你定义自己的正则表达式，同时确保它们通过 SIT 所需的其他检查。 例如，Func_India_Aadhar将确保您定义的自定义正则表达式传递了"印度 Aadhar"卡所需的验证逻辑。 有关可以用作验证符的 DLP 函数详细信息，请参阅 [敏感信息类型函数](sit-functions.md)。 

### <a name="luhn-check-validator"></a>Luhn 检查验证程序

如果您具有包含应传递 Luhn 算法的正则表达式的自定义敏感信息类型，您可以使用 [Luhn 检查验证程序](https://en.wikipedia.org/wiki/Luhn_algorithm)。

## <a name="sensitive-information-type-additional-checks"></a>敏感信息类型附加检查

以下是可用的其他检查的定义和一些示例。

**排除特定匹配**：在为正在编辑的模式检测匹配时，此检查允许定义关键词以进行排除。 例如，你可能排除测试信用卡号（如 4111111111111111），以便其不会作为有效号码进行匹配。

**以或不以字符开头**：此检查允许定义字符，匹配项必须或禁止以其开头。 例如，如果希望模式仅检测以 41、42 或 43 开头的信用卡号码，请选择“**开头为**”，然后向列表中添加 41、42 和 43，并以逗号分隔。 

**以或不以字符结尾**：此检查允许定义字符，匹配项必须或禁止以其结尾。 例如，如果员工 ID 号不能以 0 或 1 结尾，请选择“**结尾不可为**”，然后向列表添加 0 和 1，并用逗号分隔。

**排除重复字符**：此检查允许忽略所有数字都相同的匹配项。 例如，如果六位数员工 ID 号码不能都是相同数字，可以选择“**排除重复字符**”，以从员工 ID 的有效匹配列表中排除 111111、222222、333333、444444、555555、666666、777777、888888、999999 和 000000。

**包括或排除前缀**：此检查可定义在匹配实体之前必须或不得立即找到的关键字。 如果实体前面带有此处包含的前缀，则这些实体将匹配或不匹配，具体取决于你的选择。 例如，如果 **排除** 前缀 **GUID：**，则将不会把前缀为 **GUID：** 的任何实体视为匹配项。

**包括或排除后缀** 此检查可定义在匹配实体之后必须或不得立即找到的关键字。 如果实体后面是此处包含的后缀，则实体将匹配或不匹配，具体取决于你的选择。 例如，如果 **排除** 后缀 **：GUID**，则后附 **：GUID** 的任何文本将不匹配。
