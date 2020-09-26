---
title: 将数据从一个评审集添加到另一个评审集
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何从一个评审集选择文档，并在高级电子数据展示事例中单独处理它们，并在另一组中使用它们。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285176"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>从另一个评审集向评审集添加数据

在某些情况下，可能需要从一个评审集选择文档，并在另一个评审集中单独处理这些文档。 如果您已在审阅集中 culled 内容并希望对数据子集运行分析，这将非常有用。

请遵循本文中的工作流，将内容从一个审阅集添加到另一个评审集。

## <a name="create-a-review-set"></a>创建审阅集

在开始之前，您需要创建要将数据添加到的审阅集。  可以在案例的 " **审阅集** " 选项卡上添加新的审阅集。 有关详细信息，请参阅 [创建审阅集](managing-review-sets.md#create-a-review-set)。

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>步骤1：确定要添加到另一评审集的内容

您可以通过选择源评审集中的特定文档或通过选择 "评审集" 查询返回的所有项，将内容从一个评审集添加到另一个评审集。 如果要添加选定项目，请选择 "项目"，选择 " **操作**"，然后选择 " **添加到另一查看集**"。

![在 "操作" 菜单中添加到另一个审阅集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>步骤2：指定用于添加到另一评审集的选项

在 " **添加到另一张审阅集选项** " 飞出页面中，选择要将项目添加到的审阅集。 选择是否添加 **所有搜索结果** 或 **选定的项目**。  **其他信息** 提供选项以包括项目中的所有元数据，以及是否在将文档添加到新的审阅集时通过选中 " **标签** " 复选框) 从源评审集中包含标记 (。  

![用于将数据添加到另一个评审集的选项](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

单击 **"确定"** 后，会创建一个新的作业 (名为 " **将数据添加到另一个评审集** ") 为将内容添加到另一个评审集。 您可以转到 " **作业** " 选项卡并监视此作业的进度。 有关详细信息，请参阅 [管理作业](managing-jobs-ediscovery20.md)。
