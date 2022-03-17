---
title: 测试基于精确数据匹配的敏感信息类型
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
description: 配置服务
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 583a07eee97024d59efc8d81c1d7a9fd02d176ff
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526451"
---
# <a name="test-an-exact-data-match-sensitive-information-type"></a>测试基于精确数据匹配的敏感信息类型

在创建了准确数据匹配 (EDM) 敏感信息类型 (SIT) 后，在验证敏感信息表已完成上载和编制索引后一小时，您可以通过使用合规性中心的敏感信息类型部分中的测试函数测试它是否检测到要检测的信息。
 
>[!注意：] 已创建的 EDM SIT 中的更改可能需要一些时间才能在整个系统中传播。 如果要对 EDM 敏感信息类型进行更改以排查检测问题，请确保在进行更改后至少等待一小时，然后再使用测试函数验证其影响。

## <a name="test-your-edm-sit-in-the-compliance-center"></a>在合规中心测试 EDM SIT

1. Open **Compliance centerData** >  **classificationSensitive** >  Information Types.

2. 从列表中选择 EDM SIT，然后在飞 **出窗格中** 选择"测试"。 此选项仅在敏感信息类型下存在。
 
3. Upload包含要检测的数据的项。 例如，创建一个包含敏感信息表中行子集的项。 如果在架构中使用了可配置的匹配功能来定义忽略的分隔符，请确保该项包含包含和不带这些分隔符的示例。

4. 上传并扫描文件后，检查 EDM SIT 的匹配项。

5. 如果 **SIT 中的 Test** 函数检测到匹配项，请验证它未进行剪裁或提取不正确。 例如，通过仅提取应检测的完整字符串的子字符串，或仅选取多词字符串中的第一个单词，或在提取中添加额外的符号或字符。 有关 [正则表达式语言参考，](/dotnet/standard/base-types/regular-expression-language-quick-reference) 请参阅正则表达式语言 - 快速参考。 

5. 或者，您可以使用以下 PowerShell cmdlet：

```powershell
Test-DataClassification  -ClassificationNames “[Your EDM sensitive info type]” -TexttoClassify “[your own text to scan for matches]” 
```

> [!NOTE]
 创建或编辑 EDM 敏感信息类型或 EDM 类型所基于的主 SIT 时，将针对与新定义匹配的文本对在更改后修改的所有新内容和内容进行爬网，但在修改或重新建立索引之前，不会对预先不存在的内容进行爬网。 

若要强制对 SharePoint 网站或库或 OneDrive 中的现有内容进行重新爬网，请按照手动请求对网站、库或列表进行爬网和重新[](/sharepoint/crawl-site-content)索引中的说明操作。

## <a name="test-your-edm-sit-in-mip-policies"></a>在 MIP 策略中测试 EDM SIT

在策略中使用它们，你可以看到 EDM SIT 的使用位置以及它在生产中的准确性：

1. 创建自动 [标记策略，然后](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) 运行模拟 **概述**。

1. 将一些将触发 EDM SIT 的内容和一些不会触发 EDM SIT 的内容添加到策略正在监视的位置。

1. 打开" **要审阅的项目"** 选项卡以检查匹配项。

1. 根据情况调整策略。 

一旦对测试和调整的结果感到满意，基于 EDM 的自定义 SIT 就可以用于信息保护策略，例如：

- [DLP 策略](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
- [自动标记策略](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Cloud App Security文件策略](/cloud-app-security/data-protection-policies)

## <a name="troubleshooting-tips"></a>疑难解答提示

如果找不到任何匹配项，以下是一些疑难解答提示。


|问题  |疑难解答提示  |
|---------|---------|
|未找到匹配项     |  使用哈希中介绍的命令确认敏感数据已正确上载，并上传敏感信息源表，了解 [准确数据匹配敏感信息类型](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|
|未找到匹配项   | 测试在每个模式中配置主元素时所使用的 SIT。 这将确认 SIT 能够匹配项中的示例。 将错误定义的 SIT 用作 EDM 敏感信息类型的分类元素是 EDM 中检测失败的最常见原因。         |
|为 EDM 类型中的主元素选择的 SIT 在项中找不到匹配项或找到的匹配项数低于预期    |  检查是否支持内容中的分隔符和分隔符。 请务必在架构中包括定义的忽略分隔符。       |
|主元素 SIT 在项中查找匹配项，但 EDM SIT 找不到匹配项。     | - 检查 REGEX 语句以开始或结束捕获空格分隔符，如 /s。 空格与数据表中的哈希值不匹配。 请改为使用类似 /b 的单词分隔符。 </br> - 检查 REGEX 语句以确保它们捕获你想要捕获的整个字符串，而不只是一个子字符串。 例如，电子邮件地址的此模式 [a-zA-Z]{30}@[a-zA-Z]{20}[[a-zA-Z]{2,3} 将匹配 *user@contoso.com* 和 *user@contoso.co.jp*。  |
|具有主要元素且未定义辅助元素的 EDM SIT 在需要主元素和辅助元素时检测项目，但不检测或检测不到预期数。  | 确保辅助证据的值由一个不包含空格的字词或字符串组成，或使用检测多词字符串的 REGEX 语句。 例如，\b[A-Z][a-z]{1,25} ([ -][A-Z][a-z]{1,25}) {0,4}\b，它将匹配以大写字符开头的一到五个连续单词的任何序列。 使用此 SIT 作为 EDM 敏感信息类型 XML 中其他证据条件的分类元素。 请参阅 [手动创建规则包](sit-get-started-exact-data-match-create-rule-package.md#create-a-rule-package-manually)|
|SIT 测试函数不会检测任何匹配项。   | 检查所选的 SIT 是否包含其他关键字或其他验证的要求。 对于内置 SIT，请参阅 [敏感信息类型实体](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) 定义，以验证匹配每种类型的最低要求。        |
|测试功能有效，但SharePoint或OneDrive DLP 或自动标记规则中检测项目     | 检查内容资源管理器中是否显示预期匹配的文档。 如果不存在，请记住，仅在敏感信息类型更改后创建的内容将显示为匹配项。 您必须对网站和库重新进行crawl，以显示预先存在的项。 请参阅[手动请求对网站](/sharepoint/crawl-site-content)、库或列表进行爬网和重新索引，了解有关重新爬网SharePoint和OneDrive。        |
|不触发需要多个匹配的 DLP 或自动标记规则     |检查是否满足 EDM 类型和基本敏感信息类型的邻近度要求。 例如，如果主元素和支持关键字之间的最大距离为 300 个字符，但关键字仅存在于长表的第一行中，则只有前几行匹配值符合邻近度要求。 修改 SIT 定义以支持更宽松的邻近规则，或者将文档选项中的任意位置用于其他证据条件。         |
|检测 EDM 类型不一致或错误     |检查用作 EDM 类型中主元素基础的敏感信息类型是否未检测不必要的内容。 使用与太多不相关的内容（如任何单词、数字或所有电子邮件地址）匹配的 SIT 可能会导致服务饱和并忽略相关匹配。 在内容资源管理器中检查与用于主要元素的敏感类型匹配的内容片段数。 </br> 若要估计 SIT 是否匹配太多内容： </br> - 将内容资源管理器中的内容项数除以创建敏感类型以来的天数。 </br> - 如果每天的匹配数在数十万或数百万之间，则主 SIT 可能过于广泛。 有关 [为](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) EDM 类型选择正确的敏感信息类型的建议和最佳做法，请参阅了解基于准确数据匹配的敏感信息类型。         |