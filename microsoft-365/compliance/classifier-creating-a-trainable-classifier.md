---
title: 创建 trainable 分类器（预览）
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 如果其中一个内置的类元无法满足您的需求，则使用 trainable 分类程序。 Microsoft 365 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以对其进行训练以识别各种类型的内容。 本主题介绍如何创建自定义分类器。
ms.openlocfilehash: 31fb4374290bcf92a5c68bc4e7531e9472622b0b
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266891"
---
# <a name="creating-a-trainable-classifier-preview"></a>创建 trainable 分类器（预览）

当一个现成的类元中的一个无法满足您的需求时，使用 trainable 分类程序。 Microsoft 365 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以对其进行训练以识别各种类型的内容。 培训分类器首先需要为其提供人工挑选的示例，并正确匹配类别。 然后，在处理完这些后，通过为其混合使用正负样本来测试预测。

若要了解有关不同类型的分类器的详细信息，请参阅[trainable 类元入门（预览）](classifier-getting-started-with.md)

此时间线反映了一个示例部署。

![trainable-分类轴](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> 第一次需要 trainable 分类器时，自愿加入是必需的。 Microsoft 365 需要在12天内完成组织内容的基准评估。 请与全局管理员联系以启动自愿加入过程。

## <a name="seed-content"></a>种子内容

当您希望 trainable 分类程序独立且准确地将项目标识为特定的内容类别时，您首先必须向其提供类别中的内容类型的多个示例。 此示例向 trainable 分类符进行的馈送称为*种子设定*。 种子内容由人选择，并被判定为表示内容的类别。

> [!TIP]
> 您需要至少有50个肯定样本以及多达500个。 Trainable 分类器将处理最多500个最近创建的示例（通过文件创建的日期/时间戳）。 提供的示例越多，分类器将产生的预测越精确。

## <a name="testing-content"></a>测试内容

在 trainable 分类器处理足够的正样本以生成预测模型后，需要测试它所做的预测，以确定分类器能否正确区分与类别和项目不匹配的项目。 为此，请将其放在另一组中，这是一组人工挑选的内容，这些内容由应归入的类别和样本组成的样本组成。 在处理这些工作后，您需要手动浏览结果，并验证每个预测是否正确、不正确或是否不确定。 Trainable 分类器使用此反馈来改进其预测模型。

> [!TIP]
> 为获得最佳结果，您的测试示例集中有10000个项目，并且这些项目的分布为正和负匹配。

## <a name="how-to-create-a-trainable-classifier"></a>如何创建 trainable 类元

1. 在50-500 种子内容项之间进行收集。 这些示例必须是那些强烈表示您希望 trainable 分类程序正确标识为分类类别中的内容类型的示例。 有关受支持的文件类型，请参阅[SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。

> [!IMPORTANT]
> 种子和测试示例项不得加密且必须为英语。

> [!IMPORTANT]
> 请确保种子集中的项是类别的**强**示例。 Trainable 分类器最初根据您对其进行种子设定的内容生成模型。 分类器假定所有种子示例都是强的，并且无法知道样本是否为类别的弱匹配或负匹配。

2. 将种子内容放在专门用于保存*种子内容*的 SharePoint Online 文件夹中。 请记下网站、库和文件夹 URL。

> [!TIP]
> 如果为种子数据创建新的网站和文件夹，则在创建将使用该种子数据的 trainable 分类器之前，至少要为该位置编制索引一个小时。

3. 使用合规性管理或安全管理员角色访问和开放**microsoft 365 合规性中心**或**microsoft 365 安全中心** > **数据分类**登录 microsoft 365 合规性中心

4. 选择 " **Trainable 类元**" 选项卡。

5. 选择 "**创建 trainable 分类器**"。

6. 为您希望此 trainable 分类`Name`器标识`Description`的项目类别的 "" 和 "" 字段填写相应的值。

7. 为第2步中的种子内容网站输入确切的 SharePoint Online 网站、库和文件夹 URL。 选择`Add`。

8. 查看设置并选择`Create trainable classifier`。

9. 在24小时内，trainable 分类器将处理种子数据并生成一个预测模型。 分类器状态是`In progress`在处理种子数据时。 分类器处理完种子数据后，状态将更改为`Need test items`。

10. 您现在可以通过选择分类器查看详细信息页。


![trainable 分类器准备好进行测试](../media/classifier-trainable-ready-to-test-detail.png)

11. 至少收集200个测试内容项。 Microsoft 建议10000以获得最佳效果。 这些项目应混合成强阳性的项目，而这些项目的性质不是很明显。 有关受支持的文件类型，请参阅[SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。

> [!IMPORTANT]
> 示例项目不能加密且必须为英语。

12. 将测试内容放置在专门用于保存*测试内容*的 SharePoint Online 文件夹中。 请记下 SharePoint Online 网站、库和文件夹 URL。

> [!TIP]
> 如果为测试数据创建新的网站和文件夹，则在创建将使用该种子数据的 trainable 分类程序之前，至少要为该位置编制索引一个小时。

13. 选择`Add items to test`。

14. 为第12步中的测试内容网站输入确切的 SharePoint Online 网站、库和文件夹 URL。 选择`Add`。

15. 通过选择`Done`完成向导。 您的 trainable 分类器将需要一个小时来处理测试文件。

16. 当 trainable 分类器处理完测试文件后，"详细信息" 页上的状态将更改`Ready to review`为。 如果需要增加测试样本大小，请选择`Add items to test`并允许 trainable 分类器处理其他项。

![准备查看屏幕截图](../media/classifier-trainable-ready-to-review-detail.png)

17. 选择`Tested items to review` "选项卡" 以查看项目。

18. Microsoft 365 将一次显示30个项目。 查看它们，然后在`We predict this item is "Relevant". Do you agree?`框中选择`Yes` " `No`或`Not sure, skip to next item`" 或 "" 或 ""。 模型准确性在每30个项目后自动更新。

!["查看项目" 框](../media/classifier-trainable-review-detail.png)

19. 查看*至少200个*项目。

<!-- insert Analyze steps here-->

20. 继续查看，直到准确性达到至少70%， `Publish the classifier`状态为。 `Ready to use`

![准确性并准备好发布](../media/classifier-trainable-review-ready-to-publish.png)

21. 发布分类器。

22. 一旦发布分类器，便可作为基于条件和[通信合规性](communication-compliance.md)的[自动应用保留标签策略](labels.md#applying-a-retention-label-automatically-based-on-conditions)中的条件。

> [!CAUTION]
> 分类器发布后，将无法通过任何其他培训，因此请务必确保您已经测试和检查了尽可能多的项目，以确保准确性尽可能高。

## <a name="see-also"></a>另请参阅

- [可训练分类器入门（预览）](classifier-getting-started-with.md)
- [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
