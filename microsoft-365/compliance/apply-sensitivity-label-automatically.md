---
title: 将敏感度标签自动应用于内容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 创建敏感度标签时，你可以自动为文档或电子邮件分配标签，也可以提示用户选择你建议的标签。
ms.openlocfilehash: 7edfa83648ecb86ab23a898299edb63df851d123
ms.sourcegitcommit: 7eaecb91c7cb1f8679f99882563f5c1149175992
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "43022929"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>将敏感度标签自动应用于内容

创建敏感度标签时，你可以自动将该标签分配给内容（如果它包含敏感信息），也可以提示用户应用你建议的标签。

能否将敏感度标签自动应用于内容非常重要，这是因为：

- 你无需为用户提供有关所有分类的培训。

- 无需依赖用户，即可对全部内容进行正确分类。

- 用户不再需要了解你的策略，反而可以专注于自己的工作。

Azure 信息保护统一标记客户端支持适用于 Windows 的 Office 应用中的自动标签。 对于 Office 应用中的内置标签，此功能[在某些应用中处于预览状态](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

[创建或编辑敏感度标签](create-sensitivity-labels.md)时，可使用 Office 应用的自动标签设置：

![敏感度标签的自动标签选项](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>如何配置 Office 应用的自动标签

敏感度标签最强大的功能之一是，能够自动应用于符合特定条件的内容。 此情况下，组织中的人员无需应用敏感度标签 - Office 365 会代为操作。

当内容包含特定类型的敏感信息时，可选择自动将敏感度标签应用于内容。 从敏感信息类型或分类器列表中选择：

![Office 应用中的自动标签的标签条件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> 目前，“**分类器**”选项处于有限预览状态，要求你向 Microsoft 提交表单，以便为你的租户启用此功能。 有关详细信息，请参阅博客文章[宣布在 Office 应用中推出使用内置分类器的自动标签 - 有限预览](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889)。

当自动应用此敏感度标签时，用户会在其 Office 应用中看到通知。 例如：

![指出文档自动应用了标签的通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>配置标签的敏感信息类型

当你选择“**敏感信息类型**”选项时，可看到与创建数据丢失防护 (DLP) 策略时相同的敏感信息类型列表。 例如，你可以将高度机密的标签自动应用到任何包含客户个人身份信息 (PII) 的内容，如信用卡号码或社会保险号码：

![Office 应用中的自动标签的敏感信息类型](../media/sensitivity-labels-sensitive-info-types.png)

选择敏感信息类型后，可通过更改实例计数或匹配准确度来优化条件。 有关详细信息，请参阅[调整规则以使其更容易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。

此外，也可选择某项条件是必须删除所有敏感信息类型还是只删除其中一种。 要使条件更灵活或更复杂，可添加组并在组之间使用逻辑运算符。 有关详细信息，请参阅[分组和逻辑运算符](data-loss-prevention-policies.md#grouping-and-logical-operators)。

![实例计数和匹配准确度的选项](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a>为标签配置分类器

当你选择“**分类器**”选项时，请选择一个或多个内置分类器：

![分类器和敏感度标签选项](../media/sensitivity-labels-classifers.png)

有关这些分类器的详细信息，请参阅[可训练分类器（预览版）入门](classifier-getting-started-with.md)。

在预览期间，以下应用支持敏感度标签的分类器：

- 适用于 Windows 的 Office 365 专业增强版桌面应用，从 [Office 预览体验成员](https://office.com/insider)：
    - Word
    - Excel
    - PowerPoint

- Office 网页版应用 - 如果你已[启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)：
    - Word
    - Excel
    - PowerPoint
    - Outlook

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a>建议用户应用敏感度标签

如果愿意，可建议你的用户应用此标签。 通过此选项，你的用户可接受分类及任何相关保护，也可在标签不适合其内容时关闭建议。

![用于向用户建议敏感度标签的选项](../media/Sensitivity-labels-Recommended-label-option.png)

下面的示例展示了 Azure 信息保护统一标记客户端在你配置条件以将标签作为建议操作应用时提供的提示，以及自定义策略提示。 可以选择在策略提示中显示什么文本。

![关于应用建议标签的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a>如何应用自动标签或建议标签

在 Office 应用中，自动标签和建议标签的实现取决于你使用的是内置于 Office 的标签，还是 Azure 信息保护统一标记客户端。 不过，在这两种情况下：

- 不可对之前已手动标记或者之前已自动标记有更高敏感度的文档和电子邮件使用自动标签。 请记住，除了一个保留标签，另外仅可向文档或电子邮件应用一个敏感度标签。

- 都不能对之前有更高敏感度标签的文档或电子邮件使用建议标签。 如果内容已有更高敏感度标签，用户就看不到建议操作提示和策略提示。

特定于内置标签的注意事项：

- 并非所有 Office 应用都支持自动（和建议）标签。 有关详细信息，请参阅[应用中的敏感度标签功能支持](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

- 对于桌面版 Word 中的建议标签，触发建议的敏感内容会被标记，这样用户就能审阅和删除敏感内容，而不用应用建议的敏感度标签。

- 若要详细了解如何在 Office 应用中应用这些标签、示例屏幕截图，以及如何检测敏感信息，请参阅[对 Office 中的文件和电子邮件自动应用或建议敏感度标签](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)。

特定于 Azure 信息保护统一标记客户端的注意事项：

-  自动标签和建议标签在你保存文档时应用于 Word、Excel 和 PowerPoint，并在你发送电子邮件时应用于 Outlook。

- 为了让 Outlook 支持建议标签，必须先配置[高级策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)。

- 敏感信息可以在文档和电子邮件的正文文本和页眉、页脚中检测到，但不能在电子邮件的主题行或附件中检测到。

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>在多个条件适用于多个标签时如何评估这些条件

根据你在策略中为标签指定的位置按顺序对标签进行评估：位置最靠前的标签具有最低位置（最不敏感），位置最靠后的标签具有最高位置（最敏感）。有关优先级的详细信息，请参阅[标签优先级（顺序很重要）](sensitivity-labels.md#label-priority-order-matters)。

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>不要将父标签配置为自动应用或推荐使用

请记住，不可向内容应用父标签（即带子标签的标签）。 确保未将父标签配置为自动应用或推荐使用，因为父标签不会应用于使用 Azure 信息保护统一标签客户端的 Office 应用程序中的内容。 有关父标签和子标签的更多信息，请参阅[子标签（对标签进行分组）](sensitivity-labels.md#sublabels-grouping-labels)。
