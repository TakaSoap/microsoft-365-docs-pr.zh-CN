---
title: 在 Microsoft SharePoint Syntex中使用内容程序集创建文档
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: anrasto
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: 了解如何在 Microsoft SharePoint Syntex中使用内容程序集自动创建文档和其他内容。
ms.openlocfilehash: 906118458688d40c392cc9333357f1b8c946910b
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823203"
---
# <a name="create-documents-using-content-assembly-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex中使用内容程序集创建文档

可以使用SharePoint Syntex来帮助你自动生成标准重复的业务文档，例如合同、工作声明、服务协议、同意书、销售宣传和通信。 通过在SharePoint Syntex中使用内容程序集，可以更快、更一致、更不容易出错。

使用内容程序集，可以使用现有文档创建 *新式模板*，然后使用该模板使用SharePoint列表或用户输入作为数据源自动生成新内容。

> [!NOTE]
> 必须是许可SharePoint Syntex用户才能访问和使用内容程序集功能。 还必须具有管理SharePoint列表的权限。

## <a name="create-a-modern-template"></a>创建新式模板

按照以下步骤创建新式模板。

1. 在 Sharepoint 文档库中，选择 **NewCreate** >  **新式模板**。

   ![文档库的屏幕截图，其中突出显示了“创建新式模板”选项。](../media/content-understanding/content-assembly-create-template-1.png)

2. 选择要用作创建新式模板的基础的现有 Word 文档，然后选择 **“打开**”。

   ![在其中选择文档的上传页面的屏幕截图。](../media/content-understanding/content-assembly-create-template-2.png)

   > [!NOTE]
   > 目前，只能上传 Word 文档 (.docx 扩展) 来创建模板。 从本地存储或桌面Upload Word 文档。

3. 上传文档后，文档将显示在模板工作室中，可在其中将文档转换为模板。

   ![模板查看器中文档的屏幕截图。](../media/content-understanding/content-assembly-create-template-3.png)

4. 在模板工作室的左上角，选择模板的名称。 默认名称是用于创建模板的文档的名称。 如果要重命名模板，请选择名称旁边的默认名称或铅笔图标，键入新名称，然后选择 **Enter**。

   ![模板查看器的屏幕截图，其中显示了要选择重命名的文档的名称。](../media/content-understanding/content-assembly-create-template-3a.png)

5. 为文档中用户可能希望从一个文档更改为另一个文档的所有动态文本创建占位符。 例如，你可能想要为输入创建占位符，例如公司名称、客户端名称、地址、电话号码或日期。

    若要创建占位符，请选择文本 (，例如日期) 。 “ **所有占位符”** 面板将打开，你将在其中为占位符提供相关名称，并选择要与占位符关联的输入类型。

   ![模板查看器的屏幕截图，其中突出显示了一个字段和“所有占位符”面板。](../media/content-understanding/content-assembly-create-template-4a.png)

   目前，用户可以通过两种方式填写占位符：

   - [输入文本或选择日期](#associate-a-placeholder-by-entering-text-or-selecting-a-date)
   - [从列表或库列中的选项中进行选择](#associate-a-placeholder-by-selecting-from-choices-in-a-column-of-a-list-or-library)

   > [!NOTE]
   > 只能为文本创建占位符。 目前，不支持图像、智能艺术、表格和项目符号列表。

### <a name="associate-a-placeholder-by-entering-text-or-selecting-a-date"></a>通过输入文本或选择日期来关联占位符

在 **“所有占位符”** 面板上：

1. 在 **“名称”** 字段中，输入占位符的相关名称。

   ![模板查看器的屏幕截图，其中显示了手动输入的“所有占位符”面板。](../media/content-understanding/content-assembly-create-template-5.png)

2. 在 **“作者如何填写此占位符”部分中** ，选择 **“输入文本”或选择日期**。

3. 在 **“信息类型”** 字段中，选择要与占位符关联的数据类型。 目前，有六个选项可用： **单行文本**、 **多行文本**、 **数字**、 **日期和时间**、 **电子邮件** 和 **超链接**。

4. 选择“**添加**”。

### <a name="associate-a-placeholder-by-selecting-from-choices-in-a-column-of-a-list-or-library"></a>通过从列表或库列中的选项中进行选择来关联占位符

在 **“所有占位符”** 面板上：

1. 在 **“名称”** 字段中，输入占位符的相关名称。

   ![模板查看器的屏幕截图，其中显示了从SharePoint列表输入的“所有占位符”面板。](../media/content-understanding/content-assembly-create-template-6.png)

2. 在 **“作者如何填写此占位符”部分中** ， **从列表或库列中的选项中** 选择“选择”，然后选择“ **选择**”。

3. 在 **“选择用于添加源列** 页的列表”中，选择要使用的列表，然后选择 **“下一步**”。

   ![“选择用于添加源列页的列表”的屏幕截图，其中显示了列表。](../media/content-understanding/content-assembly-create-template-7.png)

4. 在 **现有列表页的“选择源列** ”上，选择要与占位符关联的列名称，然后选择 **“保存**”。

   ![从显示列名称的现有列表页中选择源列的屏幕截图。](../media/content-understanding/content-assembly-create-template-8.png)

    如果想要再次看到列表的原始页面，请选择 **“转到 (列表名称)** 列表底部的链接。

5. 完成后，你将看到列表字段已与占位符关联。

   ![“所有占位符”面板的屏幕截图，其中显示了与占位符关联的列表字段。](../media/content-understanding/content-assembly-create-template-9.png)

6. 如果希望用户能够手动添加输入，除了从列表中进行选择外，还选择 **“允许作者”添加新选项**。 在这种情况下，手动输入数据类型的默认值为 *单行文本*。 此外，作者输入的值将仅用于生成文档。 它们不会添加到SharePoint列表中。

   可以根据需要创建任意数量的占位符。 完成后，可以选择将模板另存为草稿或发布模板。

   - **保存草稿** - 将模板另存为草稿，稍后可以访问它。 可以通过从文档库中选择 **“NewEdit** >  **New”菜单**，从 **“新模板**”部分查看、编辑或发布保存的草稿。
   - **发布** – 发布要由组织中的其他用户用于创建文档的模板。 可以通过从文档库中选择 **“NewEdit** >  **New”菜单**，从 **“新模板**”部分查看、编辑或取消发布 *已发布的* 模板。

## <a name="edit-a-modern-template"></a>编辑新式模板

如果需要编辑现有模板或删除或取消发布模板，请执行以下步骤。

1. 在 Sharepoint 文档库中，选择 **“NewEdit** >  **新建”菜单**。

   ![文档库的屏幕截图，其中突出显示了“编辑新建”菜单选项。](../media/content-understanding/content-assembly-edit-template-1.png)

2. 在 **“编辑新建”菜单** 面板的“ **新式模板”** 部分中，选择要编辑的已发布或草稿模板。

   ![显示“新式模板”部分的“编辑新建”菜单面板的屏幕截图。](../media/content-understanding/content-assembly-edit-template-2.png)

3. 若要编辑已发布的模板或草稿模板，请执行以下操作：

   - 对于 **已发布的模板**，请选择 **“编辑** ”以打开模板工作室，可在其中编辑已发布的模板。 还可以选择删除或取消发布模板。

      ![“新式模板”部分的屏幕截图，其中显示了已发布的模板。](../media/content-understanding/content-assembly-edit-published.png)

   - 对于 **草稿模板**，选择 **“编辑** ”以打开模板工作室，可在其中编辑草稿模板。 还可以选择删除或发布模板。

      ![显示草稿模板的“新式模板”部分的屏幕截图。](../media/content-understanding/content-assembly-edit-draft.png)

## <a name="create-a-document-from-a-modern-template"></a>从新式模板创建文档

可以使用 *已发布的* 新式模板快速创建类似的文档，而无需从头开始。 若要使用已发布的模板创建文档，请执行以下步骤：

1. 在 Sharepoint 文档库中，选择 **“新建**”，然后选择要使用的新式模板。

   ![文档库的屏幕截图，其中显示了“新建”菜单上的新式模板选项。](../media/content-understanding/content-assembly-create-document-1.png)

2. 模板将在模板工作室中打开。

3. 在 **“从模板面板创建文档”** 上，输入信息，然后选择 **“创建文档**”。

   ![显示从模板面板创建文档的文档库的屏幕截图。](../media/content-understanding/content-assembly-create-document-2.png)

   为了帮助减少填充占位符值所涉及的时间和精力，SharePoint Syntex提供：

      - 建议可帮助你在从列表中选择值时轻松选择值。
      - 如果能够唯一标识与同一列表关联的占位符的记录，则自动填充占位符值。

> [!NOTE]
>
> - 目前，仅支持Microsoft Word文档 (.docx 扩展) 创建模板。 在上传文档之前，请确保 Word 文档未启用 **Track 更改** 或注释。 如果文档包含图像的文本占位符，请确保它们不是文本包装的。 目前，我们不支持 Word 中 **的内容控** 件。 如果要通过包含内容控件的 Word 文档创建模板，请在创建新式模板之前将其删除。
> - 模板和文档与一个文档库相关联。 若要在另一个文档库中使用模板，需要在该文档库中再次创建模板。
> - 用于创建新式模板的上传文档将另存为单独的副本，并放置在文档库的 /forms 目录中。 磁盘上的原始文件将不受影响。
> - 只能为文本创建占位符。 目前，不支持图像、智能艺术、表格和项目符号列表。
> - 从模板创建文档后，它将与模板不关联。
