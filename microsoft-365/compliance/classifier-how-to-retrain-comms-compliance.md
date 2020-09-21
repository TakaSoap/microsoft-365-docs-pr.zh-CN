---
title: '如何重新培训通信合规性 (预览中的分类器) '
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在通信合规性中向 trainable 分类器提供反馈。
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132299"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a>如何重新培训通信合规性 (预览中的分类器) 

Microsoft 365 trainable 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以进行培训以识别这些类型的内容。 经过培训后，您可以使用它来确定应用 Office 灵敏度标签、通信合规性策略和保留标签策略的项目。

本文介绍了如何通过提供其他反馈来提高自定义 trainable 分类器和某些预先培训的分类程序的性能。

若要了解有关不同类型的分类器的详细信息，请参阅 [了解 trainable 类元 (preview) ](classifier-learn-about.md)。

## <a name="permissions"></a>权限

要访问 Microsoft 365 合规性中心中的分类器，请执行以下操作：

- 合规性管理员角色或合规性数据管理员是培训分类器所必需的

在这些情况下，您需要具有这些权限的帐户才能使用分类器：

- 通信合规性策略方案：内部人员风险管理管理员、监管审核管理员 

## <a name="overall-workflow"></a>整体工作流

> [!IMPORTANT]
> 在使用分类器作为条件的合规性解决方案中提供反馈。 **如果您没有使用分类器作为条件的通信合规性策略，请在此处停止。**

在使用分类器时，您可能需要增加所进行的分类的精度。 为此，请评估为其标识为匹配或不匹配的项目所做分类的质量。 在对分类器进行30个评估之后，它将接受反馈并自动 retrains 自身。

若要了解有关重新培训分类器的整个工作流的详细信息，请参阅 [Process flow for 可再培训分类器](classifier-learn-about.md#retraining-classifiers)。

> [!NOTE]
> 分类器必须已发布且在可 retrained 之前使用。

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a>如何重新培训通信合规性策略中的分类器 (预览) 

1. 打开使用分类器作为条件的通信合规性策略，并从 " **待定** " 列表中选择已标识的项之一。
2. 选择省略号并 **改进分类**。
3. 在 " **详细反馈** " 窗格中，如果项目是真正的正数，请选择 " **匹配**"。  如果项目是误报，则表示它不正确包含在类别中，请选择 " **不匹配**"。
4. 如果有更适合该项目的另一个分类器，则可以从 " **建议其他 trainable 类元** " 列表中进行选择。 这将触发其他分类器来评估项目。

> [!TIP]
> 您可以通过选择所有项目并在命令栏中选择 " **提供详细反馈** " 来同时提供对多个项目的反馈。

5. 选择 " **发送反馈** " 以发送对 `match` 、 `not a match` 分类和建议其他 trainable 类元的评估。 向分类器提供30个反馈的实例后，它将自动重新培训。 重新培训可能需要1-4 小时。 分类器每日只能有两次 retrained。

> [!IMPORTANT]
> 此信息会转到租户中的分类器，而 **不会返回到 Microsoft**。

6.  打开**Microsoft 365 合规性中心**中的 "**数据分类**" 页。
7. 打开 **Trainable 类元 (预览) **。
8. 在通信合规性策略中使用的分类符将显示在 " **重新培训** " 标题下。

![重新培训状态中的分类符](../media/classifier-retraining.png)

9. 重新培训完成后，选择分类器打开重新培训概述。

![分类器重新培训结果概述](../media/classifier-retraining-overview.png)

10. 查看建议的操作，以及分类器的 retrained 和当前已发布版本的预测比较。
11. 如果您对重新培训的结果感到满意，请选择 " **重新发布**"。
12. 如果对重新培训的结果不满意，可以选择在通信合规性接口中向分类器提供其他反馈，并启动另一个重新培训周期，或者不执行任何操作，这种情况下将继续使用分类器的当前已发布版本。 

## <a name="details-on-republishing-recommendations"></a>有关重新发布建议的详细信息

以下是有关我们如何阐明重新发布 retrained 分类符或建议进一步重新培训的建议的一些信息。 这需要对 trainable 分类器的工作方式稍有深入了解。

重新培训后，我们会使用反馈以及任何最初用于培训分类器的项目来评估分类器的性能。 

- 对于内置模型，用于培训分类器的项是 Microsoft 用来生成模型的项。
- 对于自定义模型，在原始培训中使用的项目分类器来自您为进行测试和查看而添加的网站。

我们比较 retrained 和已发布分类器的两组项目的性能数字，以提供有关是否有改进重新发布的建议。 

## <a name="see-also"></a>另请参阅

- [了解 trainable 分类 (预览) ](classifier-learn-about.md)
- [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
