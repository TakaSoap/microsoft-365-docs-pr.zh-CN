---
title: 单个项目错误更正
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
description: 您可以修复高级电子数据展示中审阅集内文档的处理错误，而无需遵循批量错误修正过程。
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751579"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a>高级电子数据展示中的单个项目错误修正

错误修正使高级电子数据展示用户能够纠正阻止高级电子数据展示正确处理内容的数据问题。 例如，由于这些文件被锁定或加密，因此无法处理受密码保护的文件。 以前，只能使用此工作流批量 [修正错误](error-remediation-when-processing-data-in-advanced-ediscovery.md)。 但有时，如果你不确定其中任何文件是否对正在调查的情况做出响应，则修正多个文件的错误没有意义。 在有机会查看文件元数据 (（如文件位置或有权访问) ）来帮助你做出响应性决策之前修正错误可能没有意义。 名为" *单个* 项目错误修正"的新功能使电子数据展示管理员能够查看包含处理错误的文件的元数据，并在必要时直接在审阅集内修正错误。 本文讨论如何识别、忽略和修正审阅集内处理错误的文件。

## <a name="identify-documents-with-errors"></a>识别包含错误的文档

审阅集内处理错误的文档现在被标识 (横幅) 。 可以修正或忽略错误。 以下屏幕截图显示了受密码保护的审阅集内 Word 文档的处理错误横幅。 另请注意，您可以查看包含处理错误的文档的文件元数据。

![显示文档处理错误的横幅](../media/SIERimage1.png)

在查询审阅集内的文档时，您还可以使用"处理状态"条件搜索处理[错误的文档](review-set-search.md)。

![使用处理状态条件搜索错误文档](../media/SIERimage2.png)

### <a name="ignore-errors"></a>忽略错误

可以通过单击处理错误横幅中的 **"** 忽略"来忽略处理错误。 当您忽略错误时，文档将从批量 [错误修正工作流中删除](error-remediation-when-processing-data-in-advanced-ediscovery.md)。 忽略错误后，文档横幅将更改颜色，并指示已忽略处理错误。 你随时可以通过单击"还原"来恢复忽略错误 **的决定**。

![单击"忽略"忽略处理错误](../media/SIERimage3.png)

您还可以搜索具有处理错误的所有文档，这些文档在查询审阅集内的文档时使用"忽略处理错误"条件被忽略。

![使用"忽略处理错误"条件搜索被忽略的错误文档](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>修正出错的文档

有时，您可能需要通过删除密码、解密加密文件或恢复损坏的文档) 然后将修正的文档添加到审阅集来修正文档 (中的处理错误。 这样，您能够查看和导出错误文档以及审阅集内的其他文档。 

若要修正单个文档，请执行以下步骤：

1. 单击  >  **"下载原始** 文件"，将文件副本下载到本地计算机。

   ![下载包含处理错误的文档](../media/SIERimage5.png)

2. 脱机修复文件中的错误。 对于需要解密软件才能删除密码保护的加密文件，请提供密码并保存文件或使用密码破解程序。 修正文件后，转到下一步。

3. 在审阅集内，选择处理错误已修正的文件，然后单击"**修正"。**

   ![单击文档横幅中的"修正"，处理错误](../media/SIERimage6.png)


4. 单击 **"** 浏览"，转到本地计算机上已修复文件的位置，然后选择该文件。

   ![单击"浏览"，然后选择本地计算机上修正的文件](../media/SIERimage7.png)

    选择修正后的文件会自动上载到审阅集。 您可以跟踪文件的处理状态。

    ![将显示修正过程的状态](../media/SIERimage8.png)

   处理完成后，您可以查看修正后的文档。

    ![可以在审阅集内以本机格式查看修正后的文件](../media/SIERimage9.png)

有关在修正文档时会发生什么情况，请参阅修正文件时 [会发生什么情况](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)。

## <a name="search-for-remediated-documents"></a>搜索已修正的文档

您可以使用 **Keywords** 条件并指定以下属性：值对搜索审阅集内已修正的所有文档 **：IsFromErrorRemediation：true。** 从审阅集导出文档时，导出加载文件中也提供此属性。
