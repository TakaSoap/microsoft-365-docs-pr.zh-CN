---
title: 测试准确数据匹配敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 配置服务
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3030a97e3ed80524d2170e74b3d35f897b6ed74c
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914745"
---
# <a name="test-an-exact-data-match-sensitive-information-type"></a>测试准确数据匹配敏感信息类型

在创建了准确数据匹配 (EDM) 敏感信息类型 (SIT) 后，在验证敏感信息表已完成上载和编制索引后一小时，您可以通过使用合规性中心的敏感信息类型部分中的测试函数测试它是否检测到要检测的信息。
 
>[!注意：] 已创建的 EDM SIT 中的更改可能需要一些时间才能在整个系统中传播。 如果要对 EDM 敏感信息类型进行更改以排查检测问题，请确保在进行更改后至少等待一小时，然后再使用测试函数验证其影响。

## <a name="test-your-edm-sit-in-the-compliance-center"></a>在合规中心测试 EDM SIT

1. 打开 **合规中心**  >  **数据分类**  >  **敏感信息类型**。

2. 从列表中选择 EDM SIT，然后在飞 **出窗格中** 选择"测试"。 此选项仅存在于 敏感信息类型下的 SIT 中。
 
3. Upload包含要检测的数据的项。 例如，创建包含敏感信息表中行子集的项。 如果在架构中使用了可配置的匹配功能来定义忽略的分隔符，请确保该项包含包含和不带这些分隔符的示例。

4. 上传并扫描文件后，检查 EDM SIT 的匹配项。

5. 如果 **SIT** 中的 Test 函数检测到匹配项，请验证它未进行剪裁或提取不正确。 例如，通过仅提取它应检测的完整字符串的子字符串，或仅选取多词字符串中的第一个单词，或在提取中添加额外的符号或字符。 有关 [正则表达式语言参考，](/dotnet/standard/base-types/regular-expression-language-quick-reference) 请参阅正则表达式语言 - 快速参考。 

5. 或者，您可以使用以下 PowerShell cmdlet：

```powershell
Test-DataClassification  -ClassificationNames “[Your EDM sensitive info type]” -TexttoClassify “[your own text to scan for matches]” 
```

> [!NOTE]
 创建或编辑 EDM 敏感信息类型或 EDM 类型所基于的主 SIT 时，将针对与新定义匹配的文本对在更改后修改的所有新内容和内容进行爬网，但在修改或重新建立索引之前，不会对预先不存在的内容进行爬网。 

若要强制对 SharePoint 网站或库或 OneDrive 中的现有内容进行重新爬网，请按照手动请求对网站、库或列表进行爬网和重新编制索引中的说明[操作](/sharepoint/crawl-site-content)。

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

如果找不到任何匹配项，请尝试执行以下操作：

- 使用使用 EDM 工具上载敏感数据的指南中介绍的命令确认敏感数据已正确上载。

- 检查在项中输入的示例是否存在于敏感信息表中，以及忽略的分隔符是否正确。

- 测试在每个模式中配置主元素时所使用的 SIT。 这将确认 SIT 能够匹配项中的示例。 将错误定义的 SIT 用作 EDM 敏感信息类型的分类元素是 EDM 中检测失败的最常见原因。 

- 如果为 EDM 类型中的主元素选择的 SIT 在项中找不到匹配项或找到的匹配项数低于预期，请检查它是否支持内容中的分隔符和分隔符。 请务必在架构中包括定义的忽略分隔符。

- 如果 Test 函数完全检测不到任何内容，请检查所选的 SIT 是否包含其他关键字或其他验证的要求。 对于内置 SIT，请参阅敏感信息类型 [实体](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) 定义，以验证匹配每种类型的最低要求。

- 如果"测试"功能有效，但您的 SharePoint 或 OneDrive 项未在 DLP 或自动标记规则中检测到，请检查内容资源管理器中是否显示您预期匹配的文档。 如果不存在，请记住，仅在敏感信息类型更改后创建的内容将显示为匹配项。 您必须对网站和库进行重新爬网，以显示预先存在的项。 有关[对网站、](/sharepoint/crawl-site-content)库或列表进行重新爬网的详细信息，请参阅手动请求对网站、库或SharePoint OneDrive。 

- 如果未触发需要多个匹配的 DLP 或自动标记规则，请检查是否满足 EDM 类型和基本敏感信息类型的邻近度要求。 例如，如果主元素和支持关键字之间的最大距离为 300 个字符，但关键字仅存在于长表的第一行中，则只有前几行匹配值符合邻近度要求。 修改 SIT 定义以支持更宽松的邻近规则，或者将文档选项中的任意位置用于其他证据条件。 

- 如果 EDM 类型的检测不一致或错误，请检查用作 EDM 类型中主元素基础的敏感信息类型是否未检测不必要的内容。 使用与太多不相关的内容（如任何单词、数字）匹配的 SIT，所有电子邮件地址都可能导致服务饱和并忽略相关匹配。 在内容资源管理器中检查与用于主要元素的敏感类型匹配的内容片段数。 若要估计 SIT 是否匹配太多内容：
    1. 将内容资源管理器中的内容项数除以创建敏感类型以来的天数。
    2. 如果每天的匹配数在数十万或数百万之间，则主 SIT 可能过于广泛。 有关 [为](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) EDM 类型选择正确的敏感信息类型的建议和最佳做法，请参阅了解基于准确数据匹配的敏感信息类型。 

- 使用哈希中介绍的命令确认你的敏感数据已正确上载，并上传敏感信息源 [表，了解准确数据匹配敏感信息类型](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)。

- 如果为 EDM 类型中的主元素选择的 SIT 在项中找不到匹配项或找到的匹配项数低于预期，请检查它是否支持内容中的分隔符和分隔符。 请务必在架构中包括定义的忽略分隔符。 

