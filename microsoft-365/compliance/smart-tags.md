---
title: 在智能标记中设置Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 智能标记使你可以应用机器学习功能，在查看事件案例Advanced eDiscovery功能。 使用智能标记组显示机器学习检测模型（如律师-客户特权模型）的结果。
ms.openlocfilehash: c47db0c38c13820013615ff986517a86236f186b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195541"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>在智能标记中设置Advanced eDiscovery

机器学习 (ML) 功能Advanced eDiscovery审阅审阅集内案例文档时，提高决策流程的效率。 智能标记是一种将ML记录决策的方法：在审阅过程中标记文档时。 创建智能标记组时，与智能标记组关联的 ML 模型的结果决策与标记组中的标记内联显示。 这有助于在查看ML文档时，内行查看结果信息。

## <a name="how-to-set-up-a-smart-tag-group"></a>如何设置智能标记组

1. 在审阅集内，单击 **"管理审阅集"，** 然后单击"**管理标记"。**

2. 单击 **"添加标记组"，** 然后选择"**添加智能标记组"。**

3. 选择要ML组关联的标记模型。
    
   这将创建一个标记组 *和 N* 个子标记，其中 *N* 是模型可能的输出数。 例如，律师 [-客户特权检测模型](attorney-privilege-detection.md) 有两个可能的输出： 

   - **正** – 用于标记包含律师-客户特权内容的文档。
   
   - **负** – 用于标记不包含律师-客户特权内容的文档。
    
    如果选择此模型，将创建一个包含两个子标记 (一个名为 **Positive** 的子标记，另一个名为 **Negative** 的子标记) 审阅集创建一个名为 Negative 的标记。 本示例中，每个子标记对应于律师-客户特权检测模型可能的输出之一。

4. （可选）您可以重命名标记组和子标记。 例如，你可以将 **Positive** 标记重命名为 **Privileged，** 将 **Negative** 标记重命名为 **Not privileged**。

## <a name="how-to-use-smart-tags"></a>如何使用智能标记

查看文档时，模型的结果将显示在相应的子标记旁边。 例如，如果您有一个智能标记组用于律师-客户特权检测，并且您查看了一个可能特权的文档，则相应标记旁边将显示该结论的原因。 请注意，标记不会自动应用于文档。 审阅者决定如何标记文档。
