---
title: 可训练的分类器入门
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkDEFENDER
search.appverid:
- MOE150
- MET150
description: 分类Microsoft 365器是一种工具，你可以训练它，通过提供要查看的示例来识别各种类型的内容。 本文演示如何创建和训练自定义分类器以及如何重新设置它们以提高准确性。
ms.openlocfilehash: 263791549e314a116f21231e8dc4cde5be380cb7
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110603"
---
# <a name="get-started-with-trainable-classifiers"></a>可训练的分类器入门

可Microsoft 365分类器是一种工具，你可以训练它，通过提供要查看的示例来识别各种类型的内容。 接受培训后，可用于标识用于应用敏感度Office、通信合规性策略和保留标签策略的项目。

首先，创建自定义可训练分类器涉及为分类器提供人工选取且与类别积极匹配的示例。 然后，处理完这些样本后，通过向分类器提供正样本和负样本的组合来测试分类器预测的能力。 本文介绍了如何创建和训练自定义分类器，以及如何在自定义可训练分类器及其生存期内通过重新培训提高这些分类器的性能。

若要详细了解不同类型的分类器，请参阅 [了解可训练分类器](classifier-learn-about.md)。

观看此视频，了解创建可训练分类器的快速摘要。 你仍然需要阅读此完整文章才能获取详细信息。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a>先决条件

### <a name="licensing-requirements"></a>许可要求

分类器是Microsoft 365 E5 E5 合规性功能。 你必须拥有其中一个订阅，以使用这些订阅。

### <a name="permissions"></a>权限

若要访问 UI 中的分类器， 

- 全局管理员需要选择租户来创建自定义分类器。
- 要训练分类器，需要合规性管理员角色。

在这些情况下，你需要具有这些权限的帐户才能使用分类器：

- 保留标签策略方案：记录管理和保留管理角色 
- 敏感度标签策略方案：安全管理员、合规性管理员、合规性数据管理员
- 通信合规性策略方案：内部风险管理管理员、监管审核管理员 

> [!IMPORTANT]
> 默认情况下，只有创建自定义分类器的用户才能训练和查看该分类器做出预测。

## <a name="prepare-for-a-custom-trainable-classifier"></a>准备自定义可训练分类器 

在深入探讨之前，了解创建自定义可训练分类器所涉及的操作会很有帮助。 

### <a name="timeline"></a>日程表

此时间线反映了可训练分类器的示例部署。

![trainable-classifier-timeline。](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> 可训练分类器首次需要选择加入。 完成组织内容的Microsoft 365评估需要 12 天。 请与全局管理员联系以启动选择加入过程。

### <a name="overall-workflow"></a>总体工作流

若要了解有关创建自定义可训练分类器的整体工作流的更多信息，请参阅用于创建客户可训练分类 [器的流程](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)。

### <a name="seed-content"></a>种子内容

当希望可训练分类器独立准确地将某个项目标识为特定内容类别时，首先必须向该项目显示该类别中的内容类型的许多示例。 将样本馈送到可训练分类器称为"种子 *设定"。* 种子内容由用户选择，并判断为表示内容类别。

> [!TIP]
> 你需要至少具有 50 个正样本和 500 个样本。 可训练分类器将处理多达 500 个最新创建的示例 (文件创建的日期/时间戳) 。 提供的样本数越多，分类器预测的精度就越准确。

### <a name="testing-content"></a>测试内容

在可训练分类器处理了足够的正样本以构建预测模型后，你需要测试它进行预测，以查看分类器能否正确区分与类别匹配的项和不匹配的项。 为此，选择另一组人工选取的内容（希望更大一些）包含应属于类别的样本和不应包含的示例。 你应该使用与首次提供的初始种子数据不同的数据进行测试。 处理这些错误后，你手动浏览结果并验证每个预测是否正确，或者你不确定。 可训练分类器使用此反馈来改进其预测模型。

> [!TIP]
> 为了获得最佳结果，在测试示例集内至少具有 200 个项目，并均匀分布正匹配和负匹配。

## <a name="how-to-create-a-trainable-classifier"></a>如何创建可训练分类器

1. 收集 50-500 个种子内容项。 这些必须只是强烈表示您希望可训练分类器积极标识为分类类别的内容类型的示例。 有关受支持的[文件类型](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)，请参阅 SharePoint Server 中的默认爬网文件扩展名和分析文件类型。

   > [!IMPORTANT]
   > 请确保种子集内的项目是 **类别的** 强示例。 可训练分类器最初基于你为该模型设定种子的模型。 分类器假定所有种子样本都是强正数，并且无法知道样本是该类别的弱匹配还是负匹配。

2. 将种子内容放在专用于SharePoint种子内容的 *联机文件夹中*。 记下网站、库和文件夹 URL。

   > [!TIP]
   > 如果为种子数据创建新的站点和文件夹，请至少允许一小时对位置编制索引，然后再创建将使用该种子数据的可训练分类器。

3. 登录以使用Microsoft 365 合规中心管理员或安全管理员角色访问权限登录，然后打开 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心或Microsoft 365 Defender</a><a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"></a>  >  **门户数据分类"**。

4. 选择" **可训练分类器"** 选项卡。

5. 选择 **"创建可训练分类器"。**

6. 为希望此可训练分类器标识的项目类别的 和 字段填写相应的 `Name` `Description` 值。

7. 从SharePoint 2 中为种子内容网站选择"联机网站、库和文件夹 URL"。 选择 `Add` 。

8. 查看设置并选择 `Create trainable classifier` 。

9. 可训练分类器将在 24 小时内处理种子数据并生成预测模型。 分类器状态为 `In progress` 处理种子数据时的状态。 分类器处理完种子数据后，状态将更改为 `Need test items` 。

10. 现在，可以通过选择分类器来查看详细信息页面。

    > [!div class="mx-imgBorder"]
    > ![可供测试的可训练分类器。](../media/classifier-trainable-ready-to-test-detail.png)

11. 收集至少 200 个测试内容 (最大为 10，000) 以获得最佳结果。 它们应该是强正值、强负和一些本质上不太明显的项目的组合。 有关受支持的[文件类型](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)，请参阅 SharePoint Server 中的默认爬网文件扩展名和分析文件类型。

12. 将测试内容放在专用于SharePoint测试内容的联机 *文件夹中*。 记下 SharePoint Online 网站、库和文件夹 URL。

    > [!TIP]
    > 如果为测试数据创建新的站点和文件夹，请至少允许一小时对位置编制索引，然后再创建使用该种子数据的可训练分类器。

13. 选择 `Add items to test` 。

14. 从SharePoint 12 中选取测试内容网站的联机网站、库和文件夹 URL。 选择 `Add` 。

15. 通过选择 完成向导 `Done` 。 可训练分类器最多需要一小时处理测试文件。

16. 当可训练分类器处理完测试文件时，详细信息页面上的状态将更改为 `Ready to review` 。 如果需要增加测试样本大小，请选择并允许可训练分类器 `Add items to test` 处理其他项目。

    > [!div class="mx-imgBorder"]
    > ![准备查看屏幕截图。](../media/classifier-trainable-ready-to-review-detail.png)

17. 选择 `Tested items to review` 选项卡查看项目。

18. Microsoft 365一次显示 30 个项目。 查看它们，在 `We predict this item is "Relevant". Do you agree?` 框中选择 或 `Yes` `No` 或 `Not sure, skip to next item` 。 模型准确性每 30 个项目自动更新一次。

    > [!div class="mx-imgBorder"]
    > !["审阅项目"框。](../media/classifier-trainable-review-detail.png)

19. 查看 *至少* 200 个项目。 一旦精度分数稳定下来， **发布选项将** 变为可用，分类器状态将显示 `Ready to use` 。

    > [!div class="mx-imgBorder"]
    > ![精度分数和准备发布。](../media/classifier-trainable-review-ready-to-publish.png)

20. 发布分类器。

21. 发布分类器后，将用作使用敏感度标签Office自动[](apply-sensitivity-label-automatically.md)标记的条件，根据条件和通信合规性自动应用保留[标签策略](communication-compliance.md)。 [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)
