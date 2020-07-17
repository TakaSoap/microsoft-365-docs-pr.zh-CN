---
title: 自动应用保留标签来保留或删除内容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 创建和自动发布保留标签，以便你可以自动应用标签来保留所需内容并删除不需要的内容
ms.openlocfilehash: eb29a846f6a7352eec02683c70dad1b0a423bdfa
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127575"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a>自动应用保留标签来保留或删除内容

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

[保留标签](retention.md)最强大的功能之一是能够将其自动应用于符合特定条件的内容。 此情况下，组织中的人员无需应用保留标签。 Microsoft 365 会代为操作。
  
自动应用保留标签的功能非常强大，这是因为：
  
- 无需为用户提供有关所有分类的培训。
    
- 无需依赖用户，即可对全部内容进行正确分类。
    
- 用户不再需要了解数据管理策略，反而可以专注于自己的工作。
    
当内容包含敏感信息、关键字或[可训练分类器](classifier-getting-started-with.md)的匹配项时，可以自动将保留标签应用于内容。
    
将基于以下条件自动应用保留标签的流程：

![自动应用标签的角色和任务关系图](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

按照以下说明进行两个管理步骤。

> [!NOTE]
> "自动策略" 使用服务侧标记（带条件）自动应用保留标签。 执行以下操作时，还可使用标签策略自动应用保留标签： 
>
> - 将默认保留标签应用于 SharePoint 库、文件夹或文档集，以便自动标记该容器中未标记的内容
>- 使用规则将保留标签应用于电子邮件
>
> 有关这些情况，请参阅 [在应用中创建和应用保留标签](create-apply-retention-labels.md)。

## <a name="before-you-begin"></a>准备工作

组织的全局管理员具有创建和编辑保留标签及其策略的完全权限。 如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。

## <a name="how-to-auto-apply-a-retention-label"></a>如何自动应用保留标签

首先，创建你的保留标签。 然后创建 "自动策略" 以应用该标签。 如果已创建保留标签，请跳转到 [创建自动策略](#step-2-create-an-auto-apply-policy)。

导航说明取决于你是否正在使用[记录管理](records-management.md)。 针对这两种情况提供了说明。

### <a name="step-1-create-a-retention-label"></a>步骤 1：创建保留标签

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：
    
    - 如果你正在使用记录管理：
        - “**解决方案**” > “**记录管理**” > “**文件计划**”选项卡 > + “**创建标签**” > “**保留标签**”
        
    - 如果你没有使用记录管理：
       - “**解决方案**” > “**信息治理**” > “**标签**”选项卡 > +“**创建标签**”
    
    没有立即看到你的选项？ 首先选择“**全部显示**”。 

2. 按照向导中的提示进行操作。 如果你正在使用记录管理：
    
    - 有关文件计划描述符的信息，请参阅[使用文件计划管理保留标签](file-plan-manager.md)
    
    - 要使用保留标签将内容声明为记录，请启用“**使用标签将内容分类为“记录”**”复选框。

若要编辑现有标签，请将其选中，然后选择“**编辑标签**”启动同一向导，以便在步骤 2 中更改标签说明和任何[符合条件的设置](#updating-retention-labels-and-their-policies)。 或者，选择任意可用的**编辑**选项，直接转到相关页面进行更新。


### <a name="step-2-create-an-auto-apply-policy"></a>步骤 2：创建自动应用策略

创建自动应用策略时，根据指定的条件，选择要自动应用到内容的保留标签。

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：
    
    - 如果你正在使用记录管理：“**信息治理**”：
        - “**解决方案**” > “**记录管理**” > “**标签策略**”选项卡 >“**自动应用标签**”
    
    - 如果你没有使用记录管理：
        - “**解决方案**” > “**信息治理**” > “**标签策略**”选项卡 >“**自动应用标签**”
    
    没有立即看到你的选项？ 首先选择“**全部显示**”。 

2. 按照向导中的提示进行操作。
    
    有关配置自动应用保留标签的条件的信息，请参阅此页面上的[配置自动应用保留标签的条件](#configuring-conditions-for-auto-apply-retention-labels)部分。
    
    有关保留标签支持的位置的信息，请参阅[保留标签和位置](retention.md#retention-label-policies-and-locations)部分。

若要编辑现有自动应用标签策略，请将其选中，然后选择“**编辑策略**”启动同一向导，以便在步骤 2 中更改策略描述和任何[符合条件的设置](#updating-retention-labels-and-their-policies)。 或者，选择任意可用的**编辑**选项，直接转到相关页面进行更新。

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a>配置自动应用保留标签的条件

可将保留标签自动应用于包含以下各项的内容：

- [特定类型敏感信息](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [与你创建的查询匹配的特定关键字](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [可训练分类器的匹配项](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>将标签自动应用于包含特定类型敏感信息的内容

为敏感信息创建自动应用保留标签时，可看到与创建数据丢失防护 (DLP) 策略时相同的策略模板列表。 预配置每个策略模板以查找特定类型的敏感信息。 例如，此处显示的模板用于查找美国 ITIN、SSN 和护照号码。 若要深入了解 DLP，请参阅[数据丢失防护策略概述](data-loss-prevention-policies.md)。
  
![包含敏感信息类型的策略模板](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
选择策略模板后，既可以添加或删除任意类型敏感信息，也可以更改实例计数和匹配准确度。在下面的示例中，保留标签仅在以下情况下自动应用：
  
- 内容包含的这三种类型敏感信息的实例数介于 1 和 9 个之间。可删除“最大”**** 值，这样就会变为“任意”****。
    
- 检测到的敏感信息类型具有至少 75 的匹配准确度（或可信度）。 许多敏感信息类型都由多个模式定义，其中具有较高匹配准确度的模式需要发现较多证据（如关键字、日期或地址），而具有较低匹配准确度的模式需要较少的证据。 **最小**匹配准确度越低，内容越容易与条件匹配。 
    
要详细了解这些选项，请参阅[微调规则以增加或降低匹配的难度](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。
    
![用于确定敏感信息类型的选项](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>将标签自动应用于包含关键字或可搜索属性的内容

可将标签自动应用于满足特定条件的内容。目前可用的条件支持将标签应用于包含特定字词、短语或可搜索属性值的内容。可使用搜索运算符（如 AND、OR 和 NOT）优化查询。

有关查询语法的详细信息，请参阅：

- [关键字查询语言 (KQL) 语法参考](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

基于查询的标签使用搜索索引来标识内容。有关有效可搜索属性的详细信息，请参阅：

- [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
- [已爬网和托管属性在 SharePoint Server 中的概述](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

示例查询：

- Exchange
    - subject:"Quarterly Financials"
    - recipients:garthf<!--nolink-->@contoso.com
- SharePoint 和 OneDrive
    - contenttype:contract
    - site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract

![查询编辑器](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>使用可训练分类器向内容自动应用标签

选择可训练分类器的选项后，可选择其中一个内置分类器或选择自定义分类器。 内置分类器包含**简历**、**源代码**、**有针对性的骚扰**、**侮辱**和**威胁**：

![选择可训练分类器](../media/retention-label-classifers.png)

> [!CAUTION]
> 我们正在弃用**冒犯性语言**内置分类器，因为它会生成大量误报。 请不要使用此内置分类器，如果你正在使用它，则应将其业务流程中移出。 我们建议改用**针对性的骚扰**、**侮辱**和**猥亵**内置分类器。

要通过此选项自动应用标签，SharePoint Online 网站和邮箱必须至少有 10 MB 的数据。

有关可训练分类器的详细信息，请参阅[可训练分类器（预览版）入门](classifier-getting-started-with.md)。

有关示例配置，请参阅[如何做好准备并使用内置分类器](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)。

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>保留标签需要多长时间才能生效

自动应用保留标签时，可能需要等待长达 7 天，才能将保留标签应用于与条件匹配的所有现有内容。
  
![自动应用标签生效时间关系图](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a>更新保留标签及其策略

在编辑保留标签或自动应用策略，并且该保留标签已应用到内容时，更新后的设置将自动应用于此内容以及新标识的内容。

某些设置无法在创建并保存标签或策略后更改，包括：
- 除保留期外的保留设置，除非已将标签配置为根据创建的时间保留或删除内容。
- 用于分类为记录的选项。

## <a name="next-steps"></a>后续步骤

请考虑将保留标签与另一种形式的自动化配合使用，[事件驱动的保留](event-driven-retention.md)。 使用此配置时，将通过你标识的事件触发保留开始。 可通过自动策略或标签策略使用事件驱动的保留。

有关使用 SharePont 中的托管属性来自动应用保留标签并实施事件驱动保留的详细方案，请参阅[使用保留标签管理 SharePoint 文档的生命周期](auto-apply-retention-labels-scenario.md)。