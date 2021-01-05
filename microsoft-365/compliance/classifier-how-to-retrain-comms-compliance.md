---
title: 如何在通信合规性中重新分类分类器
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
description: 了解如何在通信合规性中向可训练分类器提供反馈。
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752646"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>如何在通信合规性中重新分类分类器

Microsoft 365 可训练分类器是一种工具，可通过提供要查看的示例来识别各种类型的内容。 接受培训后，可以使用它标识用于应用 Office 敏感度标签、通信合规性策略和保留标签策略的项目。

本文介绍了如何通过提供其他反馈来提高自定义可训练分类器以及一些预先训练的分类器的性能。

若要详细了解不同类型的分类器，请参阅"[了解可训练分类器"。](classifier-learn-about.md)

## <a name="permissions"></a>权限

若要访问 Microsoft 365 合规中心中的分类器：

- 要求合规性管理员角色或合规性数据管理员对分类器进行培训

在这些情况下，你需要具有这些权限的帐户才能使用分类器：

- 通信合规性策略方案：内部风险管理管理员、监管审核管理员 

## <a name="overall-workflow"></a>总体工作流

> [!IMPORTANT]
> 在将分类器用作条件的合规性解决方案中提供反馈。 **如果没有使用分类器作为条件的通信合规性策略，请在此处停止。**

使用分类器时，你可能希望提高分类的精度。 为此，您可以评估针对其标识为匹配或不匹配的项目进行的分类的质量。 对分类器进行 30 次评估后，它采用该反馈并自动自我调整。

若要了解有关重新设置分类器的总体工作流，请参阅用于重新设置分类器 [的过程流](classifier-learn-about.md#retraining-classifiers)。

> [!NOTE]
> 分类器必须先发布并使用，然后才能重新进行分类。

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>如何在通信合规性策略中重新分类分类器

1. 打开使用分类器作为条件的通信合规性策略，然后从"待定"列表中选择其中一个已标识 **的项目。**
2. 选择省略号和改进 **分类**。
3. 在 **"详细反馈"** 窗格中，如果项目为真正，请选择"**匹配"。**  如果项目为误报，即类别未正确包含，请选择"**不匹配"。**
4. 如果有另一个分类器更适用于该项目，您可以从"建议 **其他可** 训练分类器"列表中选择它。 这将触发其他分类器来评估项目。

> [!TIP]
> 可以通过选择所有项目，然后在命令栏中选择"提供详细反馈"来同时提供 **对多个项目** 的反馈。

5. 选择 **"发送反馈** "以发送对 、 分类的评估， `match` `not a match` 并建议其他可训练分类器。 向分类器提供 30 个反馈实例后，分类器将自动重新播放。 重新培训可能需要 1-4 小时。 分类器每天只能重新训练两次。

> [!IMPORTANT]
> 此信息将转到租户中的分类器 **，不会返回到 Microsoft。**

6.  打开 **Microsoft 365 合规中心的数据分类页面**。
7. 打开 **可训练分类器**。
8. 通信合规性策略中使用的分类器将显示在重新培训 **标题** 下。

![正在重新分类状态的分类器](../media/classifier-retraining.png)

9. 完成重新培训后，选择分类器打开重新培训概述。

![分类器重新分析结果概述](../media/classifier-retraining-overview.png)

10. 查看建议的操作，以及分类器经过重新审阅和当前发布的版本的预测比较。
11. 如果你对重新设置的结果感到满意，请选择 **"重新发布"。**
12. 如果您对重新设置的结果不满意，可以选择在通信合规性界面中向分类器提供其他反馈，并开始另一个重新设置周期，或者不执行任何操作，在这种情况下将继续使用当前发布的分类器版本。 

## <a name="details-on-republishing-recommendations"></a>有关重新发布建议的详细信息

下面是一些有关我们如何制定重新发布经过重新分析的分类器的建议或建议进一步重新编制的建议的信息。 这需要更深入地了解可训练分类器如何工作。

完成重新测试后，我们将评估分类器在具有反馈的项以及最初用于训练分类器的任何项上的性能。 

- 对于内置模型，用于训练分类器的项目是 Microsoft 用来生成模型的项目。
- 对于自定义模型，原始培训中使用的分类器项目来自已添加用于测试和审阅的网站。

我们将比较经过优化和发布的分类器的项目集的性能数字，以提供有关重新发布是否有改进的建议。 

## <a name="see-also"></a>另请参阅

- [了解可训练分类器](classifier-learn-about.md)
- [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
