---
title: 标记审阅集中的文档
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在审阅集内标记文档有助于删除不必要的内容，并识别Advanced eDiscovery内容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285278"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a>标记审阅集内的文档Advanced eDiscovery

组织审阅集内的内容对于完成电子数据展示过程中的各种工作流非常重要。 这包括：

- 剔除不必要的内容

- 确定相关内容
 
- 确定必须由专家或律师审阅的内容

当专家、律师或其他用户审阅审阅集内容时，可以使用标签来捕获他们有关内容的意见。 例如，如果意图是剔除不必要的内容，用户可以使用标记（如"无响应"）标记文档。 在审阅和标记内容后，可创建审阅集搜索以排除标记为"无响应"的任何内容，这将从电子数据展示工作流中的下一步骤中清除此内容。 可以针对每个案例自定义标记面板，以便标记可以支持预期的审阅工作流。

## <a name="tag-types"></a>标记类型

Advanced eDiscovery两种类型的标记：

- **单个选项标记** - 限制用户选择组中单个标记。 这可用于确保用户不会选择冲突标记，如"响应"和"无响应"。 这些按钮将显示为单选按钮。

- **多个选择标记** - 允许用户选择一个组内的多个标记。 它们将显示为复选框。

## <a name="tag-structure"></a>标记结构

除了标记类型之外，标记面板中标记组织方式的结构还可用于使标记文档更为直观。 标记按节分组。 审阅集搜索支持按标记和按标记部分搜索。 这意味着您可以创建审阅集搜索来检索用节中的任何标记标记的文档。

![标记面板中的标记部分](../media/Tagtypes.png)

可以通过在节中嵌套标记来进一步组织标记。 例如，如果目的是标识和标记特权内容，可以使用嵌套来明确用户可以将文档标记为"Privileged"，并检查相应的嵌套标记来选择特权类型。

![标记节中的嵌套标记](../media/Nestingtags.png)

## <a name="applying-tags"></a>应用标记

有几种方法将标记应用于内容。

### <a name="tagging-a-single-document"></a>标记单个文档

查看审阅集内的文档时，可以通过单击"标记"面板来显示审阅 **可以使用的标记**。

![单击"标记面板"以显示标记面板](../media/Singledoctag.png)

这样，你能够将标记应用于查看器中显示的文档。

### <a name="bulk-tagging"></a>批量标记

可以通过在结果网格中选择多个文件，然后使用标记面板中的标记（类似于标记单个文档）完成批量标记。 批量取消标记可以通过选择两次标记完成;第一次单击将应用标记，第二次选择将确保已清除所有选定文件的标记。

![自动生成的手机描述的屏幕截图](../media/Bulktag.png)

> [!NOTE]
> 批量标记时，标记面板将显示针对面板中每个标记标记的文件计数。

### <a name="tagging-in-other-review-panels"></a>其他审阅面板中的标记

查看文档时，可以使用其他审阅面板查看结果网格中文档的其他特征。 这包括查看其他相关文档、电子邮件线程、近重复项和哈希重复项。 例如，在使用文档系列审阅 (查看相关文档时) ，可以通过批量标记相关文档来大大减少审阅时间。 例如，如果电子邮件具有多个附件，并且您希望确保整个系列都一致标记。

例如，下面介绍在使用文档系列审阅面板时如何 **显示** 标记面板：

1. 打开所选文档的审阅面板后 (例如，在"文档系列审阅"面板中显示相关内容的列表，单击文档系列审阅面板下的"标记文档"。

   标记面板显示为弹出窗口。

2. 选择一个或多个标记以应用所选文档。 

3. 若要标记所有文档，请选择"文档系列"面板中的所有文档，单击"标记文档"，然后选择要应用于整个文档系列的标签。

![自动生成的社交媒体文章描述的屏幕截图](../media/Relatedtag.png)
