---
title: 使用精确数据匹配架构和敏感信息类型向导
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
description: 学习如何使用精确数据匹配和敏感信息类型向导。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 056dc858fdd2da729cb076afc5deb50f1d21602e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150962"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>使用精确数据匹配架构和敏感信息类型向导

[使用基于精确数据匹配 (EDM) 分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 包含多个步骤。  可以使用此向导创建架构和敏感信息类型， (SIT) 模式 (规则包) 文件来帮助简化此过程。

可以使用此向导而无需：

- [定义敏感信息数据库的架构](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [设置模式（规则包）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

[第 1 部分：设置基于 EDM 的分类](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification) 中的步骤。

## <a name="pre-requisites"></a>先决条件

1. 通过 EDM [工作流程概览](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) 熟悉使用 EDM 创建自定义敏感信息类型的步骤。

2. 执行以 .csv [.tsv 格式保存敏感数据中的步骤](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format)。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>使用精确数据匹配架构和敏感信息类型模式向导

1. 在 Microsoft 365 合规中心为租户转到 **数据分类** > **精确数据匹配**。

2. 选择 **创建 EDM 架构** 打开架构向导配置弹出菜单t。

![EDM 架构创建向导配置飞出控件。](../media/edm-schema-wizard-1.png)

3. 填入相应的 **名称** 和 **说明**。

4. 如果需要 **此行为，** 请选择"忽略所有架构字段的分隔符和标点符号"。 若要了解有关配置 EDM 以忽略大小写或分隔符的信息，请参阅使用基于 [EDM 和 EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)的精确数据匹配 (自定义) 类型。

5. 在 **架构字段 #1** 中填入所需值，并按需要添加新字段。 

> [!IMPORTANT]
> 必须指定至少 1 个，但不超过 5 个架构字段为可搜索字段。

6. 选择保存。 您的架构现已加入列表。

7. 选择 **EDM 敏感信息类型** 和 **创建 EDM 敏感信息类型** 以打开敏感信息类型配置向导。

8. 选择 **选择已有的 EDM 架构**，然后从列表中选择按照步骤 2-6 所创建的架构。

9. 选择 **下一步**，然后选择 **创建模式**。

10. 选择 **可信度** 和 **主元素**。  若要了解有关配置模式的详细信息，请参阅 [在合规中心中创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)

11.  选择 **主元素敏感信息类型** 以建立关联。 若要了解可用敏感信息类型的详细信息，请参阅[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)。

12. 选择 **完成**。

13. 选择所需的 **可信度和字符邻近度**。  此操作将设定整个 EDM 敏感信息类型的默认值。

13. 如果要 **为** EDM 敏感信息类型创建其他模式，请选择"创建模式"。

14. 选择 **下一步** 并填写 **名称** 和 **面向管理员的说明**。

15. 查看并选择 **提交**。

通过选择编辑和删除控制面，可以删除或编辑敏感信息类型模式。

> [!IMPORTANT]
> 若要删除已经关联某一 EDM 敏感信息类型的架构，必须先删除此 EDM 敏感信息类型，然后才能删除架构。

## <a name="post-creation-steps"></a>创建后的步骤

使用此向导创建 EDM 架构和模式（规则包）文件后，还必须执行 [第二部分：哈希和上传敏感数据](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) 中的步骤，才能使用此 EDM 自定义敏感信息类型。

验证敏感信息表是否已正确上载后，可以测试其是否正常工作。

1. 打开 **合规中心**  >  **数据分类**  >  **敏感信息类型**。
2. 从列表中选择 EDM SIT，然后在飞 **出窗格中** 选择"测试"。 
3. Upload包含要检测的数据的项，例如创建包含敏感信息表中的部分数据的项。 如果在架构中使用了可配置的匹配功能来定义忽略的分隔符，请确保该项包含包含和不带这些分隔符的示例。
4. 上传并扫描文件后，检查 EDM SIT 的匹配项。
5. 如果 **SIT** 中的 Test 函数检测到匹配项，请检查它未进行修整或提取不正确。 例如，通过仅提取它应检测的完整字符串的子字符串，或仅选取多词字符串中的第一个单词，或在提取中添加额外的符号或字符。 有关 [正则表达式语言参考，](/dotnet/standard/base-types/regular-expression-language-quick-reference) 请参阅正则表达式语言 - 快速参考。 

### <a name="troubleshooting"></a>疑难解答

如果找不到任何匹配项，请尝试执行以下操作：
- 使用使用 [EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)工具上传敏感数据的指南中介绍的命令确认你的敏感数据已正确上载。
- 检查在项中输入的示例是否存在于敏感信息表中，以及忽略的分隔符是否正确。
- **测试** 在每个模式中配置主元素时所使用的 SIT。 这将确认 SIT 能够匹配项中的示例。 
  -  如果为 EDM 类型中的主元素选择的 SIT 在项中找不到匹配项或找到的匹配项数低于预期，请检查它是否支持内容中的分隔符和分隔符。 请务必在架构中包括定义的忽略分隔符。 
  -  如果 **Test** 函数完全检测不到任何内容，请检查所选的 SIT 是否包含其他关键字或其他验证的要求。 有关内置 SIT，请参阅敏感信息类型 [实体](sensitive-information-type-entity-definitions.md) 定义，以验证匹配每种类型的最低要求。
