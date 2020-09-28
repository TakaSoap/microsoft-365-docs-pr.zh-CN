---
title: 创建类元
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
description: 了解如何创建分类器
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294898"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中创建分类器

本文中的内容适用于 Project Cortex 私人预览。 了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

分类器是一种类型的模型，可用于自动执行文档类型的标识和分类。 例如，您可能想要确定添加到文档库中的所有 *合同续订* 文档，如下面的插图中所示。

![合同续订文档](../media/content-understanding/contract-renewal.png)

通过创建分类器，可以创建将与模型关联的新 [SharePoint 内容类型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) 。

创建分类器时，需要创建 *说明* 以定义模型。 这样一来，你便可以注意到你希望一致地找到此文档类型的常见数据。 

使用文档类型示例 ( "示例文件" ) "培训" 您的模型以确定具有相同内容类型的文件。

若要创建分类器，需要执行以下操作：
1. 命名模型。
2. 添加示例文件。
3. 为示例文件添加标签。
4. 创建说明。
5. 测试您的模型。

> [!NOTE]
> 虽然您的模型使用分类器来标识和分类文档类型，但您也可以选择从模型标识的每个文件中提取特定的信息部分。 为此，请创建要添加到您的模型的 **提取** 程序。 请参阅 [创建提取程序](create-an-extractor.md)。

## <a name="name-your-model"></a>命名模型

创建模型的第一步是为其指定名称：

1. 在内容中心中，选择 " **新建**"，然后 **创建一个模型**。
2. 在 " **新建文档理解模型** " 窗格中，在 " **名称** " 字段中键入模型的名称。 例如，如果您想要标识合同续订文档，可以命名模型 *合同续订*。
3. 选择“**创建**”。 这将为模型创建一个主页。</br>

    ![分类器模型主页](../media/content-understanding/model-home.png)

创建模型时，还将创建新的 SharePoint 内容类型。 SharePoint 内容类型表示具有共同特征的文档类别，并共享该特定内容的一组列或元数据属性。 SharePoint 内容类型通过 [内容类型库](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)进行管理。 在此示例中，在创建模型时，将创建新的 *合同续订* 内容类型。

如果要将此模型映射到 SharePoint 内容类型库中的现有内容类型以使用其架构，请选择 " **高级设置** "。 请注意，虽然您可以使用现有内容类型来帮助确定和分类，但仍需要对模型进行训练，以便从标识的文件中提取信息。</br>

![高级设置](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>添加示例文件

在模型主页上，添加帮助培训模型以标识文档类型所需的示例文件。 </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> 对于分类器和 [提取器培训](create-an-extractor.md)，应使用相同的文件。 您始终可以选择添加更多更高版本，但通常可以添加完整的示例文件集。 将一些标签标记为培训您的模型，并测试其余未标记的模型以评估模型适用性。 

对于您的培训集，您想要使用正面和负面示例：
- 正则示例：表示文档类型的文档。 这些文档中包含的字符串和信息总是在这种类型的文档中。
- 负示例：不代表文档类型的文档。 这些类型的文档中缺少需要的字符串和信息。

请务必使用至少5个正的示例和至少一个负的示例来培训您的模型。  您想要创建其他模板，以便在培训过程之后测试您的模型。

添加示例文件：

1. 从模型主页的 " **生成示例库** " 磁贴中，单击 " **添加文件**"。
2. 在 " **选择模型的示例文件** " 页上，从内容中心的示例文件库中选择示例文件。 如果尚未将其上传到，请通过单击 " **上载** " 将其移到示例文件库中，选择立即上载。
3. 选择用于培训模型的示例文件后，单击 " **添加**"。

    ![选择示例文件](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>为示例文件添加标签

添加示例文件后，需要将其标记为正数或负数示例。

1. 在模型主页中的 "对 **文件进行分类和运行培训** 图块" 中，单击 " **训练分类器**"。
   这将显示 "标签" 页面，其中显示了示例文件的列表，查看器中的第一个文件可见。
2. 在第一个示例文件顶部的查看器中，您应该会看到文本，询问文件是否为您刚创建的模型的示例。 如果是一个正则示例，请选择 **"是"**。 如果它是一个负示例，请选择 " **否**"。
3. 从左侧的 " **标记的示例** " 列表中，选择要用作示例的其他文件，并为其添加标签。 

    ![分类器主页](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> 至少为五个正则的示例添加标签和一个负的示例。 

## <a name="create-an-explanation"></a>创建说明

下一步是在 "培训" 页面上创建一个说明。 说明可帮助模型了解如何识别文档。 例如，合同续订文档始终包含 *对其他泄露文本字符串的请求* 。

> [!Note]
> 当与提取程序一起使用时，说明标识要从文档中提取的字符串。 

若要创建说明：

1. 从模型主页中，选择 " **定型** " 选项卡以转到 "培训" 页面。
2. 在 "培训" 页上的 " **训练有素的文件** " 部分，您应该会看到先前标记的示例文件的列表。 从列表中选择一个正则文件，它将显示在查看器中。
3. 在 "说明" 部分，选择 " **新建** "，然后选择 " **空白**"。
4. 在 " **创建说明** " 页上：</br>
    a. 键入 **名称** (例如，"披露 Block" ) 。</br>
    b. 选择 " **类型**"。 有关示例，请选择 " **短语列表**"，因为您添加了文本字符串。</br>
    c. 在 " **请键入此处** " 框中，键入字符串。 对于示例，添加 "请求其他披露"。 如果字符串需要区分大小写，则可以选择 "区分 **大小写** "。</br>
    d. 单击“**保存**”。

    ![创建说明](../media/content-understanding/explanation.png) 
    
 
5. 模型现在将检查您创建的解释是否足够好，以确定剩余的标记的示例文件是否正确，如正面和负数示例。 在 "训练有素的文件" 部分，选中 "完成培训后检查 **评估** " 列以查看结果。 如果您创建的解释足以匹配标记为正数或负数的内容，则文件显示值 " **匹配**"。

    ![匹配值](../media/content-understanding/match.png) 

如果您在标记的文件上收到 **不匹配** 项，则可能需要创建其他说明，以提供详细的模型信息来标识文档类型。 如果发生这种情况，请单击文件以获取有关为什么发生不匹配的原因的详细信息。

## <a name="test-your-model"></a>测试模型

如果您在标记的示例文件中接收到匹配项，则现在可以在剩余的未标记的示例文件上测试模型。

1. 从模型主页中，选择 " **测试** " 选项卡。 这将在未标记的示例文件上运行模型。
2. 在 " **测试文件** " 列表中，您的示例文件显示并显示，如果模型预测它们是正数还是负数。 使用此信息有助于在识别文档时确定分类程序的有效性。

    ![未标记文件的测试](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>另请参阅
[创建提取程序](create-an-extractor.md)</br>
[文档理解概述](document-understanding-overview.md)</br>
[创建表单处理模型](create-a-form-processing-model.md)</br>
[应用模型](apply-a-model.md) 
