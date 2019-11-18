---
title: 单个项目错误更正
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
description: 您可以修复高级电子数据展示中的审阅集中的文档中的处理错误，而无需遵循批量错误修正过程。
ms.openlocfilehash: 922c0e4b0ab30bae6507fac7e97080a5951ea750
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2019
ms.locfileid: "38685195"
---
# <a name="single-item-error-remediation"></a>单个项目错误更正

错误修正使高级电子数据展示用户能够修正阻止高级电子数据展示正确处理内容的数据问题。 例如，受密码保护的文件无法处理，因为这些文件已锁定或加密。 以前，只能使用[此工作流](error-remediation-when-processing-data-in-advanced-ediscovery.md)对批量更正错误。 但有时，如果您不确定这些文件中的任何文件是否响应您正在调查的事例，则在多个文件中修正错误并不有意义。 在您有机会查看文件元数据（如文件位置或谁有权访问）之前，可能无法对错误进行修正，以帮助您提前做出有关响应的决策。 称为 "*单个项目错误修正*" 的新功能使电子数据展示管理器能够查看带有处理错误的文件的元数据，并在必要时直接在审阅集中更正错误。 本文讨论如何使用审阅集中的处理错误来标识、忽略和修正文件。

## <a name="identify-documents-with-errors"></a>识别出错的文档

在审阅集中有处理错误的文档现在标识为（带有横幅）。 您可以修正或忽略该错误。 下面的屏幕截图显示了 Word 文档在受密码保护的审阅集中的处理错误横幅。 此外，还请注意，您可以查看包含处理错误的文档的文件元数据。

![显示有处理错误的文档的横幅](media/SIERimage1.png)

您还可以通过在[审阅集中查询文档](review-set-search.md)时使用**处理状态**条件来搜索具有处理错误的文档。

![使用处理状态条件搜索错误文档](media/SIERimage2.png)

### <a name="ignore-errors"></a>忽略错误

您可以通过单击处理错误标题中的 "**忽略**" 忽略处理错误。 当您忽略错误时，文档将从[批量错误修正工作流](error-remediation-when-processing-data-in-advanced-ediscovery.md)中删除。 错误被忽略后，文档标题将更改颜色并指示处理错误已被忽略。 您可以随时单击 "**还原**"，恢复决定忽略错误。

![单击 "忽略" 忽略处理错误](media/SIERimage3.png)

您还可以搜索在审阅集中查询文档时使用 "*忽略的处理错误*" 条件忽略的处理错误的所有文档。

![使用 "忽略的处理错误" 条件搜索忽略的错误文档](media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>修正有错误的文档

有时，您可能需要修正文档中的处理错误（通过删除密码、解密加密文件或恢复损坏的文档），然后将修正的文档添加到评审集。 这使您可以查看错误文档并将其与审阅集中的其他文档一起导出。 

若要修正单个文档，请按照以下步骤操作：

1. 单击 "**下载** > **原始**版本" 将该文件的副本下载到本地计算机。

   ![下载包含处理错误的文档](media/SIERimage5.png)

2. 脱机更正文件中的错误。 对于需要解密软件的加密文件，若要删除密码保护，请提供密码并保存该文件，或使用密码破解程序。 修正文件后，请转到下一步。

3. 在审阅集中，选择包含修正的处理错误的文件，然后单击 "**修正**"。

   ![在包含处理错误的文档的标题中单击 "修正"](media/SIERimage6.png)


4. 单击 "**浏览**"，转到您的本地计算机上已修正文件的位置，然后选择该文件。

   ![单击 "浏览" 并选择本地计算机上的修正文件](media/SIERimage7.png)

    选择修正的文件后，会自动将其上载到审阅集。 您可以跟踪文件的处理状态。

    ![将显示修正过程的状态](media/SIERimage8.png)

   处理完成后，您可以查看修正的文档。

    ![您可以在审阅集中以本机格式查看修正的文件](media/SIERimage9.png)

有关修正文档时所发生情况的详细信息，请参阅[当修正文件时会发生什么情况](error-remediation.md#what-happens-when-files-are-remediated)。

## <a name="search-for-remediated-documents"></a>搜索已修正的文档

您可以使用**关键字**条件搜索已修正的审阅集中的所有文档，并指定以下属性：值对： **IsFromErrorRemediation： true**。 当您从审阅集中导出文档时，也可以在导出加载文件中使用此属性。
