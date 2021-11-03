---
title: '了解预览 (命名) '
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 了解命名实体如何帮助您通过数据丢失防护策略检测包含人员姓名、物理地址和医疗术语的敏感项目
ms.openlocfilehash: 22019e3f3a270c6205b788a48544e2a462d9dfa7
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661655"
---
# <a name="learn-about-named-entities-preview"></a>了解预览 (命名) 

> [!IMPORTANT]
> 命名实体功能正在推出，并且将在可供你使用时显示在租户中。 在内容资源管理器和 DLP 策略创作流的数据丢失 (检查) 检查它们。 

*命名实体是* SIT [ (](sensitive-information-type-learn-about.md) 敏感信息) 。 它们是复杂的字典和基于模式的分类器，可用于检测人名、物理地址和医疗条款和条件。 可以在合规性中心内查看>**数据分类>敏感信息类型。** 下面是可以使用 SIT 的部分列表：

- [DLP 策略 (数据丢失) ](dlp-learn-about-dlp.md) 
- [敏感度标签](sensitivity-labels.md)
- [内部风险管理](insider-risk-management-solution-overview.md)
- [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)

DLP 在增强策略模板中特别使用了命名实体，这些模板是预先配置的 DLP 策略，您可以为组织需求自定义这些策略。 您还可以从[空白模板](create-test-tune-dlp-policy.md)创建自己的 DLP 策略，[](create-a-dlp-policy-from-a-template.md)并使用命名实体 SIT 作为条件。

<!-- There are many other SITs that detect strings like social security, credit card, or bank account numbers to identify sensitive items. For more information, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md).-->



## <a name="examples-of-named-entity-sits"></a>命名实体 SIT 的示例

命名实体 SIT 有两种风格，*捆绑**和未捆绑*

捆绑命名实体 SIT 检测所有可能的匹配项。 将它们用作 DLP 策略中用于检测敏感项目的广泛标准。

未发包的命名实体 SIT 具有更窄的焦点，如单个国家/地区。 当你需要检测范围更窄的 DLP 策略时，请使用它们。
 
下面是命名实体 SIT 的一些示例。 可以在合规性中心"数据分类"和"敏感信息类型"中>所有> **52 个**。

|命名实体 |说明  |Bundled/Unbundled  |
|---------|---------|---------|
|所有全名    |将检测完整名称的所有可能的匹配项         |   bundled      |
|所有物理地址    |将检测物理地址的所有可能的匹配     | bundled |
|所有医疗条款和条件    |将检测所有可能的医疗条款和条件匹配项 |bundled |
|澳大利亚物理地址 |  检测与澳大利亚的物理地址相关的模式。 |unbundled |
|检测条款     |检测与流测试相关的字词，例如"hCG"。 仅英语术语。      |unbundled |
|品牌品牌名称     |检测品牌品牌的名称，例如"Tylenol"。 仅英语术语。         |unbundled |

## <a name="examples-of-enhanced-dlp-policies"></a>增强的 DLP 策略示例

下面是使用命名实体 SIT 的增强 DLP 策略的一些示例。 可以在"创建策略""数据丢失防护">"合规> **全部 10 个**。 增强模板可用于 DLP 和自动标记。

|策略类别  |模板  |说明  |
|---------|---------|---------|
|金融|美国格雷姆-格雷姆-拉雷法案 (GLBA) 增强版         |帮助检测受雷姆-里奇-比利雷法案 (GLBA) 约束的信息（包括社会保险号或信用卡号等信息）是否存在。 此增强模板通过检测用户的完整姓名（美国/英国）来扩展原始模板。 passport number、 U.S. driver's license number and U.S. physical addresses.         |
| 医疗和健康   |澳大利亚健康记录法案 (HRIP 法案) 增强         |帮助检测在澳大利亚通常被认为受健康记录和信息保密 (HRIP) 法案约束的信息（如医疗帐号和税号）是否存在。 此增强模板通过检测人们的完整姓名、医疗条款和条件以及澳大利亚物理地址来扩展原始模板。         |
|隐私   |一般数据保护条例 (GDPR) 增强         | 帮助检测欧盟或欧盟 (内部的个人) ，以帮助履行 GDPR 隐私义务。 此增强模板可检测欧盟国家/地区用户的完整姓名和物理地址。        |


## <a name="next-steps"></a>后续步骤

- [使用数据丢失防护策略中的命名实体 (预览) ](named-entities-use.md)


## <a name="for-further-information"></a>有关详细信息
<!--- [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [了解敏感信息类型](sensitive-information-type-learn-about.md)
- [创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)
- [在 PowerShell 中创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [DLP 策略 (数据丢失) ](data-loss-prevention-policies.md) 
- [敏感度标签](sensitivity-labels.md)
- [保留标签](retention.md)
- [通信合规性](communication-compliance.md)
- [自动标记策略](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [根据模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md) 
