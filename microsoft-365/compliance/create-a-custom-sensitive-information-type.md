---
title: 创建自定义敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在合规性中心创建、修改、删除和测试自定义敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e21e77fdd113942618c021f69c2cf8be64ac742f
ms.sourcegitcommit: 40f89c46032ea33de25417106f39cbeebef5a049
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2022
ms.locfileid: "63419109"
---
# <a name="create-custom-sensitive-information-types-in-the-compliance-center"></a>在合规中心创建自定义敏感信息类型

如果预先配置的敏感信息类型不满足你的需要，可以创建自己的自定义敏感信息类型，你可以完全定义这些类型，也可以复制其中一个预先配置的类型并进行修改。

使用此方法创建的自定义敏感信息类型将添加到名为 `Microsoft.SCCManaged.CustomRulePack` 的规则包中。

有两种方法可以创建新的敏感信息类型：

- [从头开始完全定义所有元素](#create-a-custom-sensitive-information-type)
- [复制和修改现有的敏感信息类型](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a>开始之前

- 应该熟悉敏感信息类型及其组成。 请参阅，[了解敏感信息类型](sensitive-information-type-learn-about.md)。 了解以下角色至关重要：
    - [正则表达式](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - Microsoft 365 敏感信息类型使用 Boost.RegEx 5.1.3 引擎
    - 关键字列表 - 可以在定义敏感信息类型或从现有关键字列表中选择时创建自己的关键字列表
    - [关键字字典](create-a-keyword-dictionary.md)
    - [敏感信息类型函数](sit-functions.md)
    - [可信度](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- 必须拥有全局管理员或合规性管理员权限，以便可以通过 UI 创建、测试和部署自定义的敏感信息类型。 请参阅 Office 365 中的[关于管理员角色](/office365/admin/add-users/about-admin-roles)。

- 组织必须具有包含数据丢失防护 (DLP) 的订阅（如 Office 365 企业版）。 请参阅[邮件策略和合规性服务说明](/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。 


> [!IMPORTANT]
> 在创建自定义分类或正则表达式模式时，不可从 Microsoft 客户服务和支持获取帮助。 支持工程师可对功能提供有限的支持，例如提供用于测试目的的示例正则表达式，或者帮助排查未如期触发的现有正则表达式模式的问题，但无法保证所有自定义内容匹配开发都将满足你的要求或义务。

## <a name="create-a-custom-sensitive-information-type"></a>创建自定义敏感信息类型

使用以下步骤可以创建完全定义的新敏感信息类型。 

1. 在合规性中心中，转到"**数据分类**\>""敏感信息 **类型"**，然后选择"**创建敏感信息类型"**。

2. 填写“**名称**”和“**说明**” 的值，然后选择“**下一步**”。

3. 选择“**创建模式**”。 在定义新的敏感信息类型时，可以创建多个模式，每个模式具有不同的元素和置信度。

4. 选择模式的默认可信度。 这些值是“**低可信度**”、“**中可信度**”和“**高可信度**”。

5. 选择并定义 **主要元素**。 主要元素可以是带有可选验证程序的 **正则表达式**、**关键字列表**、**关键字字典** 或预先配置的 **函数** 之一。 有关 DLP 函数详细信息，请参阅 [敏感信息类型函数](sit-functions.md)。 有关日期和校验和验证程序的信息，请参阅 [敏感信息类型正则表达式验证程序](sit-regex-validators-additional-checks.md#sensitive-information-type-regular-expression-validators)。

6. 填写 **字符领近度** 的值。

7. （可选）添加支持元素（如有）。 支持元素可以是带有可选验证程序的正则表达式、关键字列表、关键字字典或预定义的函数之一。 支持元素可以有自己的 **字符邻近** 度配置。 

8. （可选）从可用检查列表中添加任何 [**其他检查**](sit-regex-validators-additional-checks.md#sensitive-information-type-additional-checks)。

9. 选择“**创建**”。

10. 选择“**下一步**”。

11. 为此敏感信息类型选择 **建议的可信度**。

12. 检查设置并选择“**提交**”。

    > [!IMPORTANT]
    > Microsoft 365 使用搜索爬网程序来确定 SharePoint Online 和 OneDrive for Business 网站中的敏感信息并对其分类。 要确定现有内容中新的自定义敏感信息类型，必须对该内容重新爬网。 根据计划对内容进行爬网，但你可手动重新爬网内容来查找网站集、列表或库。 有关详细信息，请参阅[Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content)（手动请求对网站、库或列表进行爬网和重新编制索引）。

13. 在“**数据分类**”页面上，将看到列出的所有敏感信息类型。 选择“**刷新**”，然后浏览或使用搜索工具查找你创建的敏感信息类型。

### <a name="copy-and-modify-a-sensitive-information-type"></a>复制和修改敏感信息类型

使用以下步骤可以创建基于现有敏感信息类型的新敏感信息类型。 

> [!NOTE]
> 无法复制以下 SIT：
> - 加拿大驾驶证号码
> - 欧盟驾驶证号码
> - 欧盟国家标识号
> - 欧盟护照号码
> - 欧盟社会保险号或等效标识
> - 欧盟税收标识号
> - ICD-10-CM (国际) 
> - ICD-9-CM (国际) 
> - 美国驾驶证号码

此外，还可以使用 PowerShell 和精确的数据匹配功能创建自定义敏感信息类型。 若要了解有关这些方法的详细信息，请参阅：
- [使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

1. 在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后选择要复制的敏感信息类型。

2. 在浮出控件中，选择“**复制**”。

3. 在敏感信息类型列表中选择“**刷新**”，然后浏览或搜索刚刚创建的副本。 部分字串搜索有用，所以可以只搜索 `copy`，搜索将返回名称中包含 `copy` 文字的所有敏感信息类型。 

4. 填写“**名称**”和“**说明**” 的值，然后选择“**下一步**”。

5. 选择敏感信息类型“副本”，然后选择“**编辑**”。 

6. 为新的敏感信息类型提供新“**名称**”和“**描述**”。

7. 您可以选择编辑或删除现有模式，以及添加新模式。 选择新模式的默认可信度。 这些值是“**低可信度**”、“**中可信度**”和“**高可信度**”。

8. 选择并定义 **主要元素**。 主要元素可以是 **正则表达式**、**关键字列表**、**关键字字典** 或预先配置的 **函数** 之一。 请参阅 [敏感信息类型函数](sit-functions.md)。

9. 填写 **字符领近度** 的值。

10.  (可选) 如果有 **支持元素** 或添加其他 [**检查**](sit-regex-validators-additional-checks.md#sensitive-information-type-additional-checks) 。 如果需要，可以将你的 **支持元素** 分组。

11. 选择“**创建**”。

12. 选择“**下一步**”。

13. 为此敏感信息类型选择 **建议的可信度**。

14. 检查设置并选择“**提交**”。

## <a name="test-a-sensitive-information-type"></a>测试敏感信息类型

可以测试列表中的任何敏感信息类型。 我们建议在策略中使用之前，测试创建的每种敏感信息类型。

1. 准备两个文件，比如 Word 文档。 一个包含与敏感信息类型中指定的元素匹配的内容，另一个不匹配。

2. 在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从列表中选择敏感信息类型，以打开“详细信息”窗格并选择“**测试**”。

3. 上传文件并选择“**测试**”。

4. 在“**匹配结果**”页面上，查看结果并选择“**完成**”。

## <a name="custom-sensitive-information-types-limits"></a>自定义敏感信息类型限制

为了确保高性能和更低的延迟，自定义 SIT 配置存在一些限制。

|限制|值|
|--------|--------|
|通过合规中心创建的自定义 SIT 的最大数量| 500 |
|正则表达式的最大长度| 1024 个字符|
|关键字列表中给定术语的最大长度| 50 个字符|
|关键字列表中的最大术语数| 2048|
|每个敏感信息类型的最大不同正则表达式数| 20|
|关键字词典的最大大小 (后压缩) | 1MB (大约 1，000，000 个字符) |
|租户中基于关键字字典的 SIT 的最大数量|50 |

> [!NOTE] 
> 如果你有创建 500 多个自定义 SIT 的业务需求，请提出支持票证。

### <a name="instance-count-supported-values-for-sit"></a>SIT 的实例计数支持的值

在以下解决方案中使用 SIT 时，将应用 SIT 实例计数限制：

- DLP 策略
- 信息保护
- 信息治理
- 通信合规性
- 记录管理
- Microsoft Defender for Cloud Apps
- Microsoft Priva

若要使扫描的项目满足规则条件，任何单个项中 SIT 的唯一实例数都必须介于最小值和最大值之间。 这称为 **实例计数**。

- **Min** 字段：在 (项) 一项中必须找到的 SIT 的唯一实例的最小数量下限。 min 字段支持以下值：
    - 1 到 500
- **最大** 字段：在项中可找到并仍触发匹配的 SIT 唯一实例数的上限。 max 字段支持以下值：
    - 1 到 500 - 当您要针对项中的 SIT 实例数设置一个小于或 500 的特定上限时，请使用此限制。
    - Any - `Any` 当在扫描的项中发现 SIT 的唯一实例数量未定义且唯一实例数达到或超过唯一实例值的最小数目时，使用 。 换句话说，只要达到最小值，就符合唯一实例计数条件。

例如，如果希望规则在单个项中至少找到 500 个 SIT  `500` 唯一实例时触发匹配，将最小值设置为 ，将最大值设置为 。 `Any`

> [!NOTE]
> Microsoft 365 信息保护支持双字节字符集语言，用于:
> - 简体中文
> - 繁体中文
> - 韩语
> - 日语
>
>此支持适用于敏感信息类型。 有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。

> [!TIP]
> 若要检测含有中文/日文字符和单字节字符的模式，或检测含有中文/日文和英文的模式，则需要定义两个变体的关键词或词组。 
> - 例如，若要检测像“机密的文件”这样的关键词，则要使用该关键词的两个变体; 一个是在日语和英语文本之间有空格，另一个是在日语和英语文本之间没有空格。 因此，在 SIT 中要添加的关键词应该是“机密的 文档”和“机密的文档”。 同样，若要检测短语 "東京オリンピック2020"，则应该使用两个变体;“東京オリンピック 2020”和“東京オリンピック2020”。
>
> 除了中文/日语/双字节字符外，如果关键字/短语列表中还包含非中文/日语字词（如仅含英语的字词），建议创建两个字典/关键字列表。 一个针对包含中文/日语/双字节字符的关键字，另一个针对仅含英语的关键字。 
> - 例如，如果要创建包含“Highly confidential”、“機密性が高い”和“机密的document”这三个短语的关键字字典/列表，则应创建两个关键字列表。 
>     1. Highly confidential
>     2. “機密性が高い”、“机密的document”和“机密的 document”
>
> 当使用双字节连字符或双字节句号创建 regex 时，请确保像在 regex 中转义连字符或句号一样转义这两个字符。以下是供参考的示例 regex：
>    -  (？<！\d)  ([4][0-9]{3}[\-？\-\t]*[0-9]{4}) 
>
> 在关键字中不应使用双字节特殊字符。
> 
> 建议在关键词列表中使用字符串匹配而不是单词匹配。
