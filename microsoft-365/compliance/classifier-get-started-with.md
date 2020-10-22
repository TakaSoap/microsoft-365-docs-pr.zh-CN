---
title: 可训练的分类器入门（预览版）
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以对其进行训练以识别各种类型的内容。 本文介绍如何创建和培训自定义分类器，以及如何重新培训它们以提高准确性。
ms.openlocfilehash: 4c9f5dae702c71fe7f2da1ccbc0364e7bdd15b0e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636981"
---
# <a name="get-started-with-trainable-classifiers-preview"></a>可训练的分类器入门（预览版）

Microsoft 365 trainable 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以进行培训以识别这些类型的内容。 经过培训后，您可以使用它来确定应用 Office 灵敏度标签、通信合规性策略和保留标签策略的项目。

创建自定义 trainable 分类器首先涉及为其提供人工挑选的示例，并与类别正确匹配。 然后，在处理这些程序后，通过为其提供混合的正负样本来测试该分类程序的预测能力。 本文介绍如何创建和培训自定义分类器，以及如何通过重新培训在其生命周期中提高自定义 trainable 分类器和预培训的分类器的性能。

若要了解有关不同类型的分类器的详细信息，请参阅 [了解 trainable 类元 (preview) ](classifier-learn-about.md)。

## <a name="prerequisites"></a>先决条件

### <a name="licensing-requirements"></a>许可要求

分类器是 Microsoft 365 E5 或 E5 合规性功能。 您必须拥有其中一种订阅才能使用它们。

### <a name="permissions"></a>权限

若要访问 UI 中的分类器： 

- 全局管理员需要选择加入租户以创建自定义分类器。
- 合规性管理员角色或合规性数据管理员是培训分类器所必需的。

在这些情况下，您需要具有这些权限的帐户才能使用分类器：

- 保留标签策略方案：记录管理和保留管理角色 
- 敏感度标签策略方案：安全管理员、合规性管理员、合规性数据管理员
- 通信合规性策略方案：内部人员风险管理管理员、监管审核管理员 

> [!IMPORTANT]
> 默认情况下，只有创建自定义分类器的用户才可以训练和查看该分类器所做的预测。 如果您希望其他人能够培训和查看分类器预测，请参阅 [为他人定型和审阅权限](#give-others-train-and-review-rights)。

## <a name="prepare-for-a-custom-trainable-classifier"></a>准备自定义 trainable 分类器 

在进行深入研究之前，了解创建自定义 trainable 分类器所涉及的内容非常有用。 

### <a name="timeline"></a>日程表

此时间线反映了 trainable 分类器的示例部署。

![trainable-分类轴](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> 第一次需要 trainable 分类器时，自愿加入是必需的。 Microsoft 365 需要在12天内完成组织内容的基准评估。 请与全局管理员联系以启动自愿加入过程。

### <a name="overall-workflow"></a>整体工作流

若要了解有关创建自定义 trainable 分类器的整个工作流的详细信息，请参阅 [用于创建 customer trainable 分类器的过程流](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)。

### <a name="seed-content"></a>种子内容

当您希望 trainable 分类程序独立且准确地将项目标识为特定的内容类别时，您首先必须向其提供类别中的内容类型的多个示例。 此示例向 trainable 分类符进行的馈送称为 *种子设定*。 种子内容由人选择，并被判定为表示内容的类别。

> [!TIP]
> 您需要至少有50个肯定样本以及多达500个。 Trainable 分类器将最多处理500个最近创建的示例， (由文件创建的日期/时间戳) 。 提供的示例越多，分类器将产生的预测越精确。

### <a name="testing-content"></a>测试内容

在 trainable 分类器处理足够的正样本以生成预测模型后，需要测试它所做的预测，以确定分类器能否正确区分与类别和项目不匹配的项目。 为此，请选择另一组人工选取的内容，这些内容由应归入类别和样本的示例组成。 应使用与第一次提供的初始种子数据不同的数据进行测试。 在处理这些工作后，您需要手动浏览结果，并验证每个预测是否正确、不正确或是否不确定。 Trainable 分类器使用此反馈来改进其预测模型。

> [!TIP]
> 为获得最佳效果，测试示例集中至少有200个项目，并且这些项目的平均分布为正和负匹配。

## <a name="how-to-create-a-trainable-classifier"></a>如何创建 trainable 类元

1. 在50-500 种子内容项之间进行收集。 这些示例必须是那些强烈表示您希望 trainable 分类程序正确标识为分类类别中的内容类型的示例。 有关受支持的文件类型，请参阅 [SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 。

   > [!IMPORTANT]
   > 种子和测试示例项不得加密且必须为英语。

   > [!IMPORTANT]
   > 请确保种子集中的项是类别的 **强** 示例。 Trainable 分类器最初根据您对其进行种子设定的内容生成模型。 分类器假定所有种子示例都是强的，并且无法知道样本是否为类别的弱匹配或负匹配。

2. 将种子内容放在专门用于保存 *种子内容*的 SharePoint Online 文件夹中。 请记下网站、库和文件夹 URL。

   > [!TIP]
   > 如果为种子数据创建新的网站和文件夹，则在创建将使用该种子数据的 trainable 分类器之前，至少要为该位置编制索引一个小时。

3. 使用合规性管理或安全管理员角色访问和开放**microsoft 365 合规性中心**或**microsoft 365 security center**  >  **Data 分类**登录 microsoft 365 合规性中心。

4. 选择 " **Trainable 类元** " 选项卡。

5. 选择 " **创建 trainable 分类器**"。

6. 为 `Name` `Description` 您希望此 trainable 分类器标识的项目类别的 "和" 字段填写相应的值。

7. 从步骤2中的种子内容网站选取 SharePoint Online 网站、库和文件夹 URL。 选择 `Add` 。

8. 查看设置并选择 `Create trainable classifier` 。

9. 在24小时内，trainable 分类器将处理种子数据并生成一个预测模型。 分类器状态是 `In progress` 在处理种子数据时。 分类器处理完种子数据后，状态将更改为 `Need test items` 。

10. 您现在可以通过选择分类器查看详细信息页。

    > [!div class="mx-imgBorder"]
    > ![trainable 分类器准备好进行测试](../media/classifier-trainable-ready-to-test-detail.png)

11. 至少收集200个测试内容项 (10000 最大) 以获得最佳效果。 这些项目应混合成强阳性的项目，而这些项目的性质不是很明显。 有关受支持的文件类型，请参阅 [SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 。

    > [!IMPORTANT]
    > 示例项目不能加密且必须为英语。

12. 将测试内容放置在专门用于保存 *测试内容*的 SharePoint Online 文件夹中。 请记下 SharePoint Online 网站、库和文件夹 URL。

    > [!TIP]
    > 如果为测试数据创建新的网站和文件夹，则在创建将使用该种子数据的 trainable 分类程序之前，至少要为该位置编制索引一个小时。

13. 选择 `Add items to test` 。

14. 从步骤12中选择测试内容网站的 SharePoint Online 网站、库和文件夹 URL。 选择 `Add` 。

15. 通过选择完成向导 `Done` 。 您的 trainable 分类器将需要一个小时来处理测试文件。

16. 当 trainable 分类器处理完测试文件后，"详细信息" 页上的状态将更改为 `Ready to review` 。 如果需要增加测试样本大小，请选择 `Add items to test` 并允许 trainable 分类器处理其他项。

    > [!div class="mx-imgBorder"]
    > ![准备查看屏幕截图](../media/classifier-trainable-ready-to-review-detail.png)

17. 选择 `Tested items to review` "选项卡" 以查看项目。

18. Microsoft 365 将一次显示30个项目。 查看它们，然后在框中选择 "或" 或 "" 或 "" `We predict this item is "Relevant". Do you agree?` `Yes` `No` `Not sure, skip to next item` 。 模型准确性在每30个项目后自动更新。

    > [!div class="mx-imgBorder"]
    > !["查看项目" 框](../media/classifier-trainable-review-detail.png)

19. 查看 *至少200个* 项目。 在准确性得分稳定之后，" **发布** " 选项将变为可用，分类器状态将会 `Ready to use` 。

    > [!div class="mx-imgBorder"]
    > ![准确性分数并准备好发布](../media/classifier-trainable-review-ready-to-publish.png)

20. 发布分类器。

21. 一旦发布了分类符，就可以[使用敏感度标签作为 Office 自动标记](apply-sensitivity-label-automatically.md)中的条件，根据条件和[通信合规性](communication-compliance.md)[自动应用保留标签策略](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。

## <a name="give-others-train-and-review-rights"></a>向其他人授予培训和审核权限

使用此过程可向他人授予培训、审阅和调整自定义 trainable 分类器的权限。  
 
1. 作为分类器的创建者，全局管理员或电子数据展示管理员使用 [连接到安全 & 合规性中心 powershell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true)中的过程连接到合规中心（使用 PowerShell）。

2. 运行此命令：

   ```powershell
   Add-ComplianceCaseMember -Case "<classifier name>" -Member "<user or role group>"
   ```
   
   例如：
   
   `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`

   您可以多次运行此命令以添加多个用户。 请注意，您只能将 Exchange Online Protection (EOP) 角色组和 Azure 角色组。
