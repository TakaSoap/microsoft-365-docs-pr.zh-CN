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
ms.openlocfilehash: 8295ec4098e90cac963598ab2d53d47a266b23a7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551143"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>将敏感度标签自动应用于内容

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

创建敏感度标签时，你可以自动将该标签分配给内容（如果它符合你指定的条件）。

能否将敏感度标签自动应用于内容非常重要，这是因为：

- 无需为用户提供有关何时使用每种分类的培训。

- 无需依赖用户，即可对全部内容进行正确分类。

- 用户不再需要了解你的策略，反而可以专注于自己的工作。

可通过两种不同的方法来自动应用敏感度标签：

- **用户编辑文档或撰写（以及答复或转发）电子邮件时的客户端标记**：使用为 Office 应用（Word、Excel、PowerPoint 和 Outlook）的自动标记配置的标签。 
    
    此方法支持向用户推荐标签，并自动应用标签。 但在这两种情况下，用户都可以决定接受还是拒绝标签，以帮助确保正确标记内容。 此客户端标记的文档延迟最少，因为即使在保存文档之前也可以应用标签。 但是，并非所有客户端应用都支持自动标记。 Azure 信息保护统一标记客户端和[某些 Office 版本](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)支持此功能。 
    
    有关配置说明，请参阅此页面上的[如何配置 Office 应用的自动标签](#how-to-configure-auto-labeling-for-office-apps)。

- **当内容已保存（在 SharePoint Online 或 OneDrive for Business 中）或通过电子邮件发送（由 Exchange Online 处理）时的服务端标记**：使用自动标记策略—目前处于预览阶段。 
    
    > [!NOTE]
    > 请参阅预览版公告[在 Microsoft 365 服务中推出使用敏感度标签自动分类的公共预览版](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961)。
    
    此方法称为使用敏感度标签自动分类。 你可能还会听到它称为自动标记静态数据（SharePoint 和 OneDrive 中的文档）和传输中的数据（由 Exchange 发送或接收的电子邮件）。 对于 Exchange，它不包含静态电子邮件（邮箱）。 
    
    由于此标记是由服务而不是应用程序应用的，因此无需担心用户拥有的应用和版本。 因此，可立即在整个组织中使用此功能，并且适合大规模标记。 自动标记策略不支持推荐的标记，因为用户不与标记过程交互。 相反，管理员将在模拟模式下运行策略，以便在实际应用标签前，帮助确保正确标记内容。
    
    有关配置说明，请参阅此页面上的[如何为 SharePoint、OneDrive 和 Exchange 配置自动标记策略](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)。
    
    特定于 SharePoint 和 OneDrive 的自动标记：
    - 租户中每天最多自动标记 25,000 个文件（Word、PowerPoint 或 Excel）
    - 所有策略中最多 10 个网站集
    - 租户中最多 10 个策略

    特定于 Exchange 的自动标记：
    - 与 Office 应用的手动标记或自动标记不同，系统还会根据你在自动标记策略中指定的条件来扫描 Office 附件。 如果存在匹配项，则会标记电子邮件，但不标记附件。
    - 如果你拥有已应用 IRM 加密的 Exchange 邮件流规则或数据丢失防护 (DLP) 策略：当内容由这些规则或策略和自动标记策略标识时，将应用该标签。 如果该标签已应用加密，则将忽略 Exchange 邮件流规则或 DLP 策略中的 IRM 设置。 但是，如果该标签未应用加密，则除了标签之外，还会应用邮件流规则或 DLP 策略中的 IRM 设置。
    - 如果存在匹配项，则具有 IRM 加密但没有标签的电子邮件将通过自动标记替换为具有加密设置的标签。
    - 与自动标记条件匹配时，将标记传入电子邮件。 但是，如果已将标签配置为加密，则不会应用该加密。
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a>将 Office 应用的自动标记与自动标记策略进行比较

使用下表可帮助识别两种互补自动标记方法在行为上的差异：

|功能或行为|标签设置：Office 应用的自动标记 |策略：自动标记|
|:-----|:-----|:-----|:-----|
|应用相关性|[是](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |否 |
|按位置限制|否 |是 |
|条件：可训练分类器|是（有限预览） |否 |
|条件：电子邮件的共享选项和其他选项|否 |是 |
|建议、策略工具提示和用户重写|是 |否 |
|模拟模式|否 |是 |
|根据条件检查 Exchange 附件|否 | 是|
|应用视觉标记 |是 |是（仅限电子邮件） |
|覆盖在未带标签的情况下应用的 IRM 加密|如果用户具有“导出”的最低使用权限，则为“是” |是（仅限电子邮件） |
|标记传入电子邮件|否 |是（未应用加密） |

> [!NOTE]
> 手动标记内容后，该标签将永远不会被自动标记替换。 但是，自动标记策略可以替换通过使用 Office 应用的自动标记而应用的[低优先级标签](sensitivity-labels.md#label-priority-order-matters)。

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>在多个条件适用于多个标签时如何评估这些条件

根据你在策略中为标签指定的位置按顺序对标签进行评估：位置最靠前的标签具有最低位置（最不敏感），位置最靠后的标签具有最高位置（最敏感）。有关优先级的详细信息，请参阅[标签优先级（顺序很重要）](sensitivity-labels.md#label-priority-order-matters)。

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>不要将父标签配置为自动应用或推荐使用

请记住，不可向内容应用父标签（即带子标签的标签）。 确保未在 Office 应用中将父标签配置为自动应用或推荐，并且不为自动标记策略选择父标签。 如果执行此操作，则不会将父标签应用于内容。

若要将自动标记用于子标签，请确保同时发布父标签和子标签。

有关父标签和子标签的更多信息，请参阅[子标签（对标签进行分组）](sensitivity-labels.md#sublabels-grouping-labels)。

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>如何配置 Office 应用的自动标签

Azure 信息保护统一标记客户端支持适用于 Windows 的 Office 应用中的自动标签。 对于 Office 应用中的内置标签，此功能[在某些应用中处于预览状态](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

[创建或编辑敏感度标签](create-sensitivity-labels.md)时，可使用 Office 应用的自动标签设置：

![敏感度标签的自动标签选项](../media/sensitivity-labels-auto-labeling-options.png)

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

### <a name="recommend-that-the-user-applies-a-sensitivity-label-in-office-apps"></a>建议用户在 Office 应用中应用敏感度标签

如果愿意，可建议你的用户应用此标签。 通过此选项，你的用户可接受分类及任何相关保护，也可在标签不适合其内容时关闭建议。

![用于向用户建议敏感度标签的选项](../media/Sensitivity-labels-Recommended-label-option.png)

下面的示例展示了 Azure 信息保护统一标记客户端在你配置条件以将标签作为建议操作应用时提供的提示，以及自定义策略提示。 可以选择在策略提示中显示什么文本。

![关于应用建议标签的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied-in-office-apps"></a>何时在 Office 应用中应用自动标签或建议标签

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

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a>如何为 SharePoint、OneDrive 和 Exchange 配置自动标记策略
> [!NOTE]
> 自动标记策略将在公共预览版中逐步向租户推出，并且可能会发生更改。

### <a name="prerequisites-for-auto-labeling-policies"></a>自动标记策略的先决条件

- 必须为模拟模式启用 Office 365 审核。 如果你需要启用审核，或者不确定是否已启用审核，请参阅[启用或禁用 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。

- 若要自动标记 SharePoint 和 OneDrive 中的文件：
    - 你已[启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。
    - 当自动标记策略运行时，该文件不得由其他进程或用户打开。

- 如果计划使用[自定义敏感信息类型](custom-sensitive-info-types.md)，而不是内置敏感度类型： 
    - 针对在保存自定义敏感度信息类型后创建的内容，评估自定义敏感度信息类型。 
    - 若要测试新的自定义敏感信息类型，请在创建自动标记策略前创建它们，然后创建新文档（其中包含用于测试的示例数据）。

- 你可以为自动标记策略选择一个或多个[已创建和发布](create-sensitivity-labels.md)（至少向一个用户发布）的敏感度标签。 对于这些标签：
    - 启用或禁用 Office 应用标签设置中的自动标记无关紧要，因为该标签设置会补充自动标记策略，如简介中所述。 
    - 如果要用于自动标记的标签被配置为使用视觉标记（页眉、页脚、水印），请注意它们不会应用于文档。

### <a name="learn-about-simulation-mode"></a>了解模拟模式

模拟模式是自动标记策略所独有的，并且已整合到工作流中。 在策略至少运行一次模拟前，无法自动标记文档和电子邮件。

用于自动标记策略的工作流：

1. 创建和配置自动标记策略

2. 在模拟模式下运行策略并等待至少 24 小时

3. 查看结果，如有必要，优化策略、重新运行模拟模式并等待至少 24 小时

4. 根据需要重复步骤 3

5. 在生产中部署

模拟部署的运行方式与 PowerShell 的 WhatIf 参数相同。 你将看到报告的结果，如同自动标记策略已使用你定义的规则应用了所选标签一样。 然后，你可以根据需要优化规则的准确性，并重新运行模拟。 但是，由于 Exchange 的自动标记适用于已发送和接收的电子邮件，而不是存储在邮箱中的电子邮件，因此不要期望模拟中的电子邮件结果保持一致，除非你能够发送和接收完全相同的电子邮件。

模拟模式还允许你在部署前逐步增加自动标记策略的范围。 例如，你可以从一个位置（如 SharePoint 网站）和一个文档库开始。 然后，使用迭代更改，将范围增大到多个网站，然后将其增加到其他位置，如 OneDrive。

最后，可以使用模拟模式来提供运行自动标记策略所需时间的近似值，以帮助计划和安排在没有模拟模式的情况下运行自动标记策略的时间。

### <a name="creating-an-auto-labeling-policy"></a>创建自动标记策略

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到敏感度标签：
    
    - **解决方案** > **信息保护**
    
    如果看不到此选项，请先选择“**全部显示**”。

2. 选择“**自动标记(预览)**”选项卡：
    
    ![“自动标记(预览)”选项卡](../media/auto-labeling-tab.png)

3. 选择“**+ 创建策略**”。

4. 对于“**选择要将此标签应用于的信息**”页面：选择其中一个模板，如“**财务**”或“**隐私**”。 可使用“**显示选项**”下拉列表来优化搜索。 或者，如果模板无法满足你的要求，请选择“**自定义策略**”。 选择“**下一步**”。

5. 对于“**为自动标记策略命名**”页面：提供唯一的名称，并选择性地提供描述，以帮助识别自动应用的标签、位置和条件（用于标识要标记的内容）。

6. 对于“**选择要应用标签的位置**”页面：选择并指定 Exchange、SharePoint 网站和 OneDrive 的位置。 然后选择“**下一步**”。

7. 对于“**定义策略设置**”页面：保留“**查找所包含内容**”的默认设置，以定义用于在所有选定位置标识要标记的内容的规则。 如果每个位置需要不同的规则，请选择“**高级设置**”。 然后选择“**下一步**”。
    
    这些规则使用包含敏感信息类型和共享选项的条件：
    - 对于敏感信息类型，你可以选择内置和自定义敏感信息类型。
    - 对于共享选项，你可以选择“**仅与组织内部人员共享**”或“**与组织外部人员共享**”。
    
    如果你的唯一位置是 **Exchange**，或者如果你选择“**高级设置**”，则可供选择的其他条件包括：
    - 发件人 IP 地址为
    - 收件人域为
    - 收件人为
    - 附件的文件扩展名为
    - 附件受密码保护
    - 文档属性为
    - 无法扫描任何电子邮件附件的内容
    - 任何电子邮件附件的内容均未完成扫描

8. 对于“**设置规则以定义要标记的内容**”页面：选择“**+ 创建规则**”，然后选择“**下一步**”。

9. 在“**创建规则**”页面上，使用敏感信息类型或共享选项命名并定义你的规则，然后选择“**保存**”。
    
    敏感信息类型的配置选项与为 Office 应用自动标记所选的选项相同。 如果需要详细信息，请参阅[配置标签的敏感信息类型](#configuring-sensitive-info-types-for-a-label)。

10. 返回到“**设置规则以定义要标记的内容**”页面：如果你需要另一个规则来标识要标记的内容，请再次选择“**+ 创建规则**”，然后重复上一步。 定义所需的所有规则并确认其状态为“开启”后，请选择“**下一步**”。

11. 对于“**选择要自动应用的标签**”页面：选择“**+ 选择标签**”，从“**选择敏感度标签**”窗格中选择一个标签，然后选择“**下一步**”。

12. 对于“**为策略选择模式**”页面：如果你准备立即在模拟模式下运行自动标记策略，请选择“**测试**”。 否则，请选择“**保持禁用**”。 选择“**下一步**”。 

13. 对于“**摘要**”页面：查看自动标记策略的配置并进行所需的任何更改，然后完成向导。
    
    与 Office 应用的自动标记不同，无单独的发布选项。 但是，与发布标签一样，自动标记策略最多需要 24 小时才能在整个组织中复制。

现在，在“**信息保护**”页面的“**自动标记(预览)**”选项卡上，你可以在“**测试**”部分中看到自动标记策略。 选择你的策略以查看配置和状态的详细信息（例如，仍在测试或测试完成）。 选择“**匹配的项**”选项卡，以查看与你指定的规则匹配的电子邮件或文档。

你可以通过选择页面顶部的“**编辑**”选项来直接从此界面修改策略。

如果你已准备好运行策略而不进行模拟，请选择“**开启**”选项。

如果你具有相应的[权限](data-classification-content-explorer.md#permissions)，则还可通过使用[内容资源管理器](data-classification-content-explorer.md)来查看自动标记策略的结果：
- **内容资源管理器列表查看器**允许你查看文件的标签，而不是文件的内容。
- **内容资源管理器内容查看器**允许你查看文件的内容。

> [!TIP]
> 你还可以使用内容资源管理器来标识具有未标记文档的位置，这些文档包含敏感信息。 使用此信息，请考虑将这些位置添加到自动标记策略中，并将标识的敏感信息类型作为规则包括在内。


