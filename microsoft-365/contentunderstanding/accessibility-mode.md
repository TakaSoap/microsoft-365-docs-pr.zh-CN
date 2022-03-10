---
title: 辅助功能模式SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.localizationpriority: medium
description: 了解如何在培训和使用 SharePoint Syntex 中的模型时使用辅助功能SharePoint Syntex。
ms.openlocfilehash: 09fd16259a44a2aa4d1b82dca49fffa76065690b
ms.sourcegitcommit: 40f89c46032ea33de25417106f39cbeebef5a049
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2022
ms.locfileid: "63419053"
---
# <a name="accessibility-mode-in-sharepoint-syntex"></a>辅助功能模式SharePoint Syntex

在[SharePoint Syntex](index.md)中，用户可以在使用示例文档时在模型 (、标签、培训和测试) 所有阶段启用辅助功能模式。 使用辅助功能模式可帮助低视力用户在文档查看器中导航和标记项目时更轻松地使用键盘辅助功能。

这有助于用户在文档查看器中使用键盘在文本中导航，并不仅听到所选值的旁白，还有助于听到操作 (例如标记或删除选定文本) 中的标签，或者使用其他示例文档训练模型时预测的标签值。 


![辅助功能模式。](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>要求

若要听到旁白的音频，请确保在"讲述人"系统上的"讲述[](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1)人"设置中Windows 10应用。

![打开"讲述人"。](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>键盘用户标签

对于使用辅助功能模式的键盘用户，如果在查看器中为示例文档中的文本添加标签，可以使用以下键：

- Tab：向前移动并选择下一个单词。
- Tab + Shift：向后移动并选择上一个单词。
- 输入：为所选单词添加标签或删除标签。
- 向右键：在选定单词中的单个字符之间向前移动。
- 向左箭头：在所选单词中的单个字符之间向后移动。

> [!NOTE]
> 如果要为单个标签标记多个单词，则需要标记每个单词。


## <a name="narration"></a>旁白

对于使用辅助功能模式的讲述人用户，请使用为键盘用户描述的相同键盘导航，以在查看器中浏览示例文档。

在示例文档和标签字符串值中导航时，讲述人会向用户提供以下音频提示：

- 当您使用键盘在文档查看器中导航时，讲述人音频将指出所选的字符串。
- 在选定的字符串中，当你使用向左或向右箭头键选择字符串时，讲述人音频将说明字符串中的每个字符。
- 如果选择已标记的字符串，"讲述人"将声明该值，然后"标记"。  例如，如果标签值为"Contoso"，它将声明"Costoso 已标记"。 
- 在培训选项卡中，如果在文档查看器中选择一个仅预测的字符串，"讲述人"音频将声明该值，然后"预测"。 当培训预测文件中与用户标记的值不匹配的值时，会出现此情况。
- 在培训选项卡中，如果在已标记和预测的文档查看器中选择一个字符串，"讲述人"音频将声明该值，然后"标记并预测"。 当培训成功且预测值与用户标签匹配时，会出现此情况。

在查看器中标记字符串或删除标签后，讲述人音频会警告你退出之前保存更改。

## <a name="see-also"></a>另请参阅

[创建提取程序](create-an-extractor.md)

[创建分类器](create-a-classifier.md)










 


  
  



