---
title: 使用精确数据匹配架构和敏感信息类型向导
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 学习如何使用精确数据匹配和敏感信息类型向导。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699141"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>使用精确数据匹配架构和敏感信息类型向导

[使用基于精确数据匹配 (EDM) 分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 包含多个步骤。  可以使用此向导创建您的架构和敏感信息类型（规则包）文件，以帮助简化过程。

> [!NOTE]
> 精确数据匹配架构和敏感信息类型向导仅用于 World Wide 和 GCC。

可以使用此向导而无需：

- [定义敏感信息数据库的架构](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [设置模式（规则包）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

[第 1 部分：设置基于 EDM 的分类](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification) 中的步骤。

## <a name="pre-requisites"></a>先决条件

1. 通过 EDM [工作流程概览](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) 熟悉使用 EDM 创建自定义敏感信息类型的步骤。

2. 执行 [以 .csv 格式保存敏感数据](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) 一节中的步骤。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>使用精确数据匹配架构和敏感信息类型模式向导

1. 在 Microsoft 365 合规中心为租户转到 **数据分类** > **精确数据匹配**。

2. 选择 **创建 EDM 架构** 打开架构向导配置弹出菜单t。

![EDM 架构创建向导配置弹出菜单](../media/edm-schema-wizard-1.png)

3. 填入相应的 **名称** 和 **说明**。

4. 如果愿意，选择 **为所有架构字段忽略分隔符和标点符号**。 若要了解配置 EDM 忽略分隔符方面的详细信息，请参阅 [使用基于精确数据匹配 (EDM) 分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

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

13. 若要为 EDM 敏感信息类型创建其他模式，请选择 **创建模式**。

14. 选择 **下一步** 并填写 **名称** 和 **面向管理员的说明**。

15. 查看并选择 **提交**。

通过选择编辑和删除控制面，可以删除或编辑敏感信息类型模式。

> [!IMPORTANT]
> 若要删除已经关联某一 EDM 敏感信息类型的架构，必须先删除此 EDM 敏感信息类型，然后才能删除架构。

## <a name="post-steps"></a>后续步骤

使用此向导创建 EDM 架构和模式（规则包）文件后，还必须执行 [第二部分：哈希和上传敏感数据](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) 中的步骤，才能使用此 EDM 自定义敏感信息类型。