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
ms.openlocfilehash: 9ab456cd5b1f5f1bf47a1e24a3d7e58b7992ede0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196375"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a>自动应用保留标签来保留或删除内容

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

> [!NOTE]
> [规章记录](records-management.md#records)不支持这种情况。

[保留标签](retention.md)最强大的功能之一是能够将其自动应用于符合特定条件的内容。 此情况下，组织中的人员无需应用保留标签。 Microsoft 365 会代为操作。
  
自动应用保留标签的功能非常强大，这是因为：
  
- 无需为用户提供有关所有分类的培训。
    
- 无需依赖用户，即可对全部内容进行正确分类。
    
- 用户不再需要了解数据管理策略，反而可以专注于自己的工作。
    
当内容包含敏感信息、关键字或可搜索属性，或者[可训练分类器](classifier-get-started-with.md)的匹配项时，可以自动将保留标签应用于内容。

> [!TIP]
> 现在在预览中，使用可搜索的属性标识 [Teams 会议记录](#microsoft-teams-meeting-recordings)。

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

组织的全局管理员拥有创建和编辑保留标签及其策略的完全权限。 如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。

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
    
    - 若要使用保留标签来声明记录，请选择 **“将项目标记为记录”**，或者 **“将项目标记为合规性记录”**。 有关详细信息，请参阅[配置保留标签以声明记录](declare-records.md#configuring-retention-labels-to-declare-records)。

3. 创建标签后，你会看到用于发布标签、自动应用标签或 仅保存标签的选项：请选择“**将此标签自动应用到特定的内容类型**”，然后选择“**完成**”以启动“创建自动标记向导”，该向导将直接带你跳转到以下过程中的第 2 步。

若要编辑现有标签，请将其选中，然后选择“**编辑标签**”来启动“编辑保留向导”，这个向导使你能够更改来自第 2 步的标签说明和任何[符合条件的设置](#updating-retention-labels-and-their-policies)。


### <a name="step-2-create-an-auto-apply-policy"></a>步骤 2：创建自动应用策略

创建自动应用策略时，根据指定的条件，选择要自动应用到内容的保留标签。

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：
    
    - 如果你正在使用记录管理：“**信息治理**”：
        - **“解决方案”** > **“记录管理”** > **“标签策略”** 选项卡 > **“自动应用标签”**
    
    - 如果你没有使用记录管理：
        - **“解决方案”** > **“信息治理”** > **“标签策略”** 选项卡 > **“自动应用标签”**
    
    没有立即看到你的选项？ 首先选择“**全部显示**”。 

2. 按照“创建自动标记向导”中的提示进行操作。
    
    有关配置自动应用保留标签的条件的信息，请参阅此页面上的[配置自动应用保留标签的条件](#configuring-conditions-for-auto-apply-retention-labels)部分。
    
    有关保留标签支持的位置的信息，请参阅[保留标签和位置](retention.md#retention-label-policies-and-locations)部分。

若要编辑现有的自动应用策略，请将其选中以启动“编辑保留策略向导”，该向导可用于更改从第 2 步中选定的保留标签和的任何[符合条件的设置](#updating-retention-labels-and-their-policies) 。


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a>配置自动应用保留标签的条件

可将保留标签自动应用于包含以下各项的内容：

- [特定类型敏感信息](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [指定与所创建的查询匹配的特定关键字或可搜索属性](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [可训练分类器的匹配项](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>将标签自动应用于包含特定类型敏感信息的内容

为敏感信息创建自动应用保留标签时，可看到与创建数据丢失防护 (DLP) 策略时相同的策略模板列表。 每个策略模板都是预配置的，用于查找特定类型的敏感信息。 例如，此处显示的模板查找来自“**隐私**”类别的美国 ITIN、SSN 和护照号码，以及**美国个人身份信息（PII）数据模板**：

![包含敏感信息类型的策略模板](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

若要了解有关敏感信息类型的详细信息，请参阅“[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)”。

选择策略模板后，可添加或删除任意类型的敏感信息，且可更改实例计数和匹配准确度。 在下面的示例屏幕截图中，保留标签将只会在以下情况下自动应用：
  
- 检测到的敏感信息类型具有至少 75 的匹配准确度（或可信度）。 许多敏感信息类型都由多个模式定义，其中具有较高匹配准确度的模式需要发现较多证据（如关键字、日期或地址），而具有较低匹配准确度的模式需要较少的证据。 **最小**匹配准确度越低，内容越容易与条件匹配。

- 内容包含 1 到 9 个这三种敏感信息类型的实例。 可删除“**至**”值，将其更改为“**任何**”。

有关这些选项的详细信息，请参阅 DLP 文档中的以下指南“[调整规则，使它们更易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)”。
    
![用于确定敏感信息类型的选项](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>将标签自动应用于包含关键字或可搜索属性的内容

可使用包含特定字词、短语或可搜索属性值的查询对内容自动应用标签。可使用搜索运算符（如 AND、OR 和 NOT）优化查询。

![查询编辑器](../media/new-retention-query-editor.png)

有关使用关键字查询语言 (KQL) 的详细信息，请参阅[关键字查询语言 (KQL) 语法参考](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。

基于查询的标签使用搜索索引来标识内容。 有关可使用的可搜索属性的详细信息，请参阅：

- [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
- [已爬网和托管属性在 SharePoint Server 中的概述](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> 尽管 SharePoint 托管属性支持别名，但在配置保留标签时，请不要使用它们。 始终指定托管属性的实际名称，例如“RefinableString01”。

示例查询：

| 工作负载 | 示例 |
|:-----|:-----|
|Exchange   | `subject:"Quarterly Financials"` |
|Exchange   | `recipients:garthf@contoso.com` |
|SharePoint | `contenttype:contract` |
|SharePoint | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

##### <a name="microsoft-teams-meeting-recordings"></a>Microsoft Teams 会议记录

> [!NOTE]
> 保留和删除 Teams 会议记录将在预览中进行，记录保存到 OneDrive 或 SharePoint 前，将无法正常工作。 有关详细信息，请参阅[使用 OneDrive for Business 和 SharePoint 或 Stream 进行会议记录](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change)。

若要确定存储在用户的 OneDrive 帐户或 SharePoint 中的 Microsoft Teams 会议记录，请为**关键字查询编辑器**指定以下内容：

``` 
ProgID:Media AND ProgID:Meeting
```

对于此保留标签，还必须通过创建标签策略将其发布到相关用户的 OneDrive 帐户或 SharePoint 网站。 大多数情况下，会议记录将保存到 OneDrive，但对于渠道会议，它们将保存在 SharePoint 中。

保存了自动应用策略时：

1. 选择 **“标签策略”** 选项卡，> **“发布标签”**

2. 系统提示选择标签时，选择用 KQL 查询创建的标签，标识 Teams 会议记录。

3. 系统提示位置时，请选择 **“SharePoint 网站”** 和 **“OneDrive 帐户”**。 然后，可保留**所有**的默认值，或指定单独的位置，例如包含或排除特定 OneDrive 帐户。

4. 完成向导并保存此标签策略。

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>使用可训练分类器向内容自动应用标签

选择可训练分类器的选项后，可选择其中一个内置分类器或选择自定义分类器。 内置分类器包含**简历**、**源代码**、**有针对性的骚扰**、**侮辱**和**威胁**：

![选择可训练分类器](../media/retention-label-classifers.png)

> [!CAUTION]
> 我们正在弃用**冒犯性语言**内置分类器，因为它会生成大量误报。 请不要使用此内置分类器，如果你正在使用它，则应将其业务流程中移出。 我们建议改用**针对性的骚扰**、**侮辱**和**猥亵**内置分类器。

要通过此选项自动应用标签，SharePoint 网站和邮箱必须至少有 10 MB 的数据。

有关可训练分类器的详细信息，请参阅“[了解可训练分类器（预览版）](classifier-learn-about.md)”。

> [!TIP]
> 如果你将可训练的分类器用于 Exchange，请参阅最近发布的[如何重新培训内容资源管理器（预览版）](classifier-how-to-retrain-content-explorer.md)中的分类器。

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>保留标签需要多长时间才能生效

自动应用保留标签时，可能需要等待长达 7 天，才能将保留标签应用于与条件匹配的所有现有内容。
  
![自动应用标签生效时间关系图](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a>更新保留标签及其策略

在编辑保留标签或自动应用策略，并且该保留标签已应用到内容时，更新后的设置将自动应用于此内容以及新标识的内容。

某些设置无法在创建并保存标签或策略后更改，包括：
- 除保留期外的保留设置，除非已将标签配置为根据创建的时间保留或删除内容。
- 用于将项目标记为记录的选项。

## <a name="next-steps"></a>后续步骤

有关使用事件驱动的保留和 SharePoint 中带有托管属性的自动应用策略来开启保留期的示例方案，请参阅[使用保留标签管理 SharePoint 中存储的文档的生命周期](auto-apply-retention-labels-scenario.md)。
