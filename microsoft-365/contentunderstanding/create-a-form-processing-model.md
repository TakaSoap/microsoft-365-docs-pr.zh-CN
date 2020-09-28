---
title: 创建表单处理模型
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 在 Microsoft SharePoint Syntex 中创建表单处理模型。
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295474"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint 中创建表单处理模型 Syntex

本文中的内容适用于 Project Cortex 私人预览。 了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。

使用 [AI 生成器](https://docs.microsoft.com/ai-builder/overview) -Microsoft PowerApps-Project Cortex 中的一项功能用户可以直接从 SharePoint 文档库创建 [表单处理模型](form-processing-overview.md) 。 

创建表单处理模型涉及以下内容：
 - 步骤1：创建源处理模型以创建内容类型
 - 步骤2：添加和分析示例文件
 - 步骤3：选择窗体域
 - 步骤4：培训和测试您的模型
 - 步骤5：发布模型
 - 步骤6：使用模型

## <a name="requirements"></a>Requirements

您只能在启用了该模型的 SharePoint 文档库中创建表单处理模型。 如果已启用表单处理，则可以在文档库中的 "**自动**" 菜单下看到 " **AI 生成器**'**创建表单处理模型 '"** 。  如果您需要在文档库上启用处理，则必须与您的 SharePoint 管理员联系。

 ![创建 AI 生成器模型](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>步骤1：创建表单处理模型

创建表单处理模型的第一步是将其命名并创建定义新的内容类型，并为其创建新的文档库视图。

1. 在文档库中，选择 " **自动** " 菜单，选择 " **AI 生成器**"，然后选择 " **创建表单处理模型**"。

    ![创建模型](../media/content-understanding/create-ai-builder-model.png)</br>

2. 在 " **新建表单处理模型** " 窗格中的 "  **名称** " 字段中，键入模型 (的名称，例如，" *采购订单*) "。

    ![新表单处理模型](../media/content-understanding/new-form-model.png)</br> 

3. 创建表单处理模型时，将创建新的 SharePoint 内容类型。 SharePoint 内容类型表示具有共同特征的文档类别，并共享该特定内容的一组列或元数据属性。 SharePoint 内容类型通过 [内容类型库]()进行管理。

    如果要将此模型映射到 SharePoint 内容类型库中的现有内容类型以使用其架构，请选择 " **高级设置** "。 

4. 您的模型将为提取的数据在文档库中创建一个新视图。 如果您不想将其显示在默认视图中，取消选择 **"将视图设置为默认值**"。

5. 选择“创建”****。

## <a name="step-2-add-and-analyze-documents"></a>步骤2：添加和分析文档

在创建新的表单处理模型后，浏览器将打开一个新的 PowerApps AI 生成器表单处理模型页面。 在此页面上，您可以添加和分析示例文档。 </br>

> [!NOTE]
> 在查找要使用的示例文件时，请参阅 [表单处理模型输入文档要求和优化提示](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。 

   ![Power Apps AI 生成器](../media/content-understanding/powerapps.png)</br> 
 
1. 选择 " **添加文档** " 开始添加分析的示例文档，以确定可提取的命名值对。 然后，您可以选择 " **从本地存储**、 **SharePoint**或 **Azure Blob 存储**上载"。 您至少需要使用5个文件进行培训。

2. 添加文件后，选择 " **分析** " 以检查是否有任何常见的信息是文件。 这可能需要几分钟的时间才能完成。</br> 
 
    ![分析文件](../media/content-understanding/analyze.png)</br> 

3. 分析文件后，在 " **选择要保存的表单域** " 页中，选择要查看检测到的字段的文件。</br>

    ![选择窗体域](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>步骤3：选择窗体域

在分析文档中的字段后，您现在可以看到找到的字段，并确定要保存的字段。 保存的域在模型的文档库视图中显示为列，并显示从每个文档中提取的值。

1. 下一页显示您的示例文件之一，并突出显示系统自动检测到的所有常见字段。 </br>

    !["选择字段" 页](../media/content-understanding/select-fields-page.png)</br> 

2. 选择要保存的字段，然后选中复选框以确认您的选择。 例如，在 "采购订单模型" 中，选择选择 " *日期*"、" *PO*" 和 " *总计* " 字段。  请注意，您还可以选择重命名字段（如果选择）。 </br>

    ![选择 PO#](../media/content-understanding/po.png)</br> 

3. 如果分析未检测到某个字段，您仍可以选择添加它。 突出显示要提取的信息，并在 "名称" 框中键入所需的名称。 然后选中 "" 复选框。 请注意，您需要在剩余的示例文件中确认未检测的字段。

4. 在选择了要保存的字段后，单击 " **确认字段** "。 </br>
 
    ![选择字段后确认字段](../media/content-understanding/confirm-fields.png)</br> 
 
5. 在 " **选择要保存的表单域** " 页上，将显示所选的字段数。 选择“完成”****。

## <a name="step-4-train-and-test-your-model"></a>步骤4：培训和测试您的模型

在选择了要保存的字段后，" **模型摘要** " 页允许您对模型进行定型和测试。

1. 在 " **模型摘要** " 页上，保存的字段将显示在 " **选定的字段** " 部分。 选择 " **训练** " 以开始对示例文件进行训练。 请注意，这可能需要几分钟的时间才能完成。</br>

     ![选择字段火车](../media/content-understanding/select-fields-train.png)</br> 

2. 当您看到 "培训已完成" 通知时，请选择 " **转到详细信息" 页**。 

3. 在 " **模型详细信息** " 页上，可以选择 " **快速测试**" 来测试模型的工作方式。 这样，您就可以将文件拖放到页面中，并查看是否检测到字段。

    ![确认字段](../media/content-understanding/select-fields-train.png)</br> 

2. 当您看到 "培训已完成" 通知时，请选择 " **转到详细信息" 页**。 

3. 在 " **模型详细信息** " 页上，选择 " **快速测试**" 以测试模型的工作方式。 这样，您就可以将文件拖放到页面中，并查看是否检测到字段。

## <a name="step-5-publish-your-model"></a>步骤5：发布模型

1. 如果您对模型的结果感到满意，请选择 " **发布** " 以使其可供使用。

2. 在发布模型后，选择 " **使用模型**"。 这将创建可在 SharePoint 文档库中运行的 PowerAutomate 流，并提取已在模型中标识的字段，然后选择 " **创建流**"。
  
3. 完成后，您将看到消息 **您的流已成功创建**。
 
## <a name="step-6-use-your-model"></a>步骤6：使用模型

在发布模型并创建它的 PowerAutomate 流后，可以在 SharePoint 文档库中使用您的模型。

1. 发布模型后，选择 " **转到 SharePoint** " 以转到您的文档库。

2. 在 "文档库模型" 视图中，请注意，您选择的字段现在显示为 "列"。</br>

    ![文档库模型已应用](../media/content-understanding/doc-lib-view.png)</br> 

3. 请注意， **文档** 旁边的信息链接会记录表单处理模型应用于此文档库。

    ![Info 按钮](../media/content-understanding/info-button.png)</br>  

4. 将文件上传到您的文档库。 模型标识为其内容类型的任何文件都会列出视图中的文件，并在列中显示提取的数据。</br>

    ![Done](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>另请参阅
  
[电源自动化文档](https://docs.microsoft.com/power-automate/)</br>
[培训：使用 AI 生成器改进业务绩效](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
