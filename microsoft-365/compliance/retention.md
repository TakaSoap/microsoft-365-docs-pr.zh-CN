---
title: 了解用于自动保留或删除内容的保留策略和保留标签
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解有助于保留所需内容并删除不需要内容的保留策略和保留标签。
ms.openlocfilehash: 751b88ea3dde0c4cf2a33dded26a032a1e320b5e
ms.sourcegitcommit: 8d28bce1a3445878b066864e766cf52cb83becd1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50071307"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a>了解保留策略和保留标签

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

对于大多数组织，数据量和数据复杂性每天都在增加 — 包括电子邮件、文档、即时消息等。有效管理或管理此类信息非常重要，因为要：
  
- **主动遵守规定至少必须在一段时间内保留内容的行业法规和内部策略**：例如，《萨班斯-奥克斯利法案》规定，必须保留特定类型的内容七年。 

- **降低发生诉讼或出现安全漏洞的风险**：通过永久删除不再需要保留的旧内容。 
    
- **帮助组织有效共享知识并提高敏捷性**：通过确保用户仅处理与自己相关的最新内容。 
    
你配置的保留设置可有助于实现所有这些目标。 管理内容通常需要执行两项操作：
  
- **保留** 内容，这样除非保留期到期，否则无法永久删除内容。 
    
- 在保留期到期时永久 **删除** 内容。 
    

通过这两项保留操作，可以配置保留设置来实现以下结果：

- 仅保留：永久或在指定的时间段内保留内容。
- 仅删除：在指定的时间段后删除内容。
- 保留后删除：在指定的时间段内保留内容后删除内容。

这些保留设置应用于在适当位置上的内容，如果你出于合规性原因需要保留内容，它们可以为你节省创建和配置附加存储的额外开销。 另外，无需实现自定义流程来复制和同步此数据。

## <a name="how-retention-settings-work-with-content-in-place"></a>保留设置如何应用于在适当位置上的内容

分配有保留设置的内容保留在它的原始位置上。 用户可以继续处理自己的文档或邮件，就像什么都没有改变一样。 但如果他们编辑或删除了包含在保留策略中的内容，则会自动保留一份内容的副本。
  
- 对于 SharePoint 和 OneDrive 网站：副本保留在 **保留** 库中。

- 对于 Exchange 邮箱：副本保留在“可恢复项”文件夹中。 

- 对于 Teams 和 Yammer 消息：副本保留在 Exchange“**可恢复项**”文件夹内名为“**SubstrateHolds**”的隐藏文件夹中。

> [!NOTE]
> 保留库占用的存储计入网站的存储配额。 在对 SharePoint 和 Microsoft 365 组使用保留设置时，可能需要增加存储空间。
> 
这些安全位置和保留的内容对大部分用户不可见。 在大多数情况下，用户甚至不需要知道他们的内容遵循保留设置。

若要详细了解保留设置如何用于不同的工作负载，请参阅以下文章：

- [了解用于 SharePoint 和 OneDrive 的保留](retention-policies-sharepoint.md)
- [了解用于 Microsoft Teams 的保留](retention-policies-teams.md)
- [了解用于 Yammer 的保留](retention-policies-yammer.md)
- [了解用于 Exchange 的保留](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a>保留策略和保留标签

可以使用保留策略和带有标签策略的保留标签来为内容分配保留设置。 

使用保留策略可以在网站或邮箱级别为内容分配相同的保留设置，使用保留标签可以在项（文件夹、文档、电子邮件）级别分配保留设置。

例如，如果某 SharePoint 网站中的所有文档都应保留 5 年，那么使用保留策略比将相同的保留标签应用于此网站中的所有文档更高效。 不过，如果此网站中的一些文档应保留 5 年，另一些文档应保留 10 年，那么保留策略就无法实现这一点。 如果需要在项级别指定保留设置，请使用保留标签。 

与保留策略不同，如果内容移动到 Microsoft 365 租户内的不同位置，保留标签的保留设置会随着内容移动而移动。 另外，保留标签具有保留策略不支持的以下功能： 
 
- 除了根据内容年限或上次修改时间计算保留期之外，还可以从内容被标记时或根据事件开始计算保留期。

- 使用[可训练的分类器](classifier-learn-about.md)来标识要标记的内容。

- 为 SharePoint 文档应用默认标签。

- 支持[处置评审](disposition-reviews.md) ，以在永久删除内容前评审内容。

- 将内容标记为[记录](records-management.md#records)作为标签设置的一部分，并对在保留期结束时删除的内容始终都有 [处置证明](disposition.md#disposition-of-records) 。

### <a name="retention-policies"></a>保留策略

可以将保留策略应用于以下位置：
- Exchange 电子邮件
- SharePoint 网站
- OneDrive 账户
- Microsoft 365 组
- Skype for Business
- Exchange 公用文件夹
- Teams 通道消息
- Teams 聊天
- yammer 社区消息
- Yammer 私信

可以非常高效地将一个策略应用于多个位置，也可以应用于特定的位置或用户。

对于保留期的开始，你可以选择内容创建的时间，或者上次修改内容的时间（仅支持文件和 SharePoint、OneDrive 和 Microsoft 365 组位置）。

项目从保留策略所指定的容器中继承保留设置。 如果当策略配置为保留内容之后将它们移动到该容器之外，则该项目的副本将保留在工作负载的安全位置。 然而，保留设置不会随着内容在新的位置而一起移动。 如果需要，请使用保留标签而不是保留策略。

### <a name="retention-labels"></a>保留标签

对于需要不同保留设置的不同类型的内容，可以使用保留标签。 例如：
  
- 至少必须保留一段时间的税务表单。 
    
- 达到特定年限后必须永久删除的新闻材料。 
    
- 必须在保留一段时间后永久删除的竞争性研究。 
    
- 必须标记为记录以免被编辑或删除的工作签证。 
    
在所有这些情况下，可以使用保留标签在项（文档或电子邮件）级别应用保留设置来实现管理控制。
  
使用保留标签，你可以：
  
- **允许组织中的人员将保留标签手动应用于** Outlook 和 Outlook 网页版、OneDrive、SharePoint​​ 和 Microsoft 365 组中的内容。 用户通常最了解自己处理的内容的类型，因此他们可以对内容进行分类，并应用适当的保留设置。 
    
- **将保留标签自动应用于** 符合特定条件的内容，如内容包含： 
    - 特定类型敏感信息。
    - 与所创建的查询匹配的特定关键字。
    - 可训练分类器的模式匹配。

- **从内容被标记时开始计算保留期**，适用于 SharePoint 网站和 OneDrive 帐户中的文档，以及除日历项外的电子邮件项。 如果你将具有此配置的保留标签应用于日历项，保留期从日历项发送时开始计算。

- **从事件发生时开始计算保留期**，如员工离开组织或合同到期。

- **将默认保留标签应用于 SharePoint 中的文档库、文件夹或文档集**，以让存储在该位置的所有文档都继承默认保留标签。

此外，保留标签支持跨 Microsoft 365 应用和服务对电子邮件和文档实施[记录管理](records-management.md)。 可使用保留标签将项目标记为记录。 如果发生这种情况，而内容仍保留在 Microsoft 365 中，则标签会对内容进行进一步的限制，这可能是监管原因所致。 有关详细信息，请参阅[比较对允许或阻止的操作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。

如果内容被移动到 Microsoft 365 之外，则保留标签将不会继续存在，这一点与[敏感度标签](sensitivity-labels.md)是不同的。

租户支持的保留标签数没有限制。 但是，租户支持的最大策略数为 10,000，其中包括应用标签的策略（保留标签策略和自动应用保留策略）以及保留策略。

#### <a name="classifying-content-without-applying-any-actions"></a>对内容分类但不执行任何操作

虽然保留标签的主要用途是保留或删除内容，但也可以在使用保留标签时不启用任何保留或其他操作。 在这种情况下，可以简单地将保留标签用作文本标签，而不强制执行任何操作。
  
例如，可以创建并应用名为“稍后评审”且不含任何操作的保留标签，稍后使用此标签来查找相应内容。
  
![将设置标记为仅分类](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>将保留标签用作 DLP 策略中的条件

对于 SharePoint 中的文档，可以将保留标签指定为数据丢失防护 (DLP) 策略中的条件。 例如，配置一个 DLP 策略，以防在组织外部共享应用了指定保留标签的文档。

有关详细信息，请参阅[将保留标签用作 DLP 策略中的条件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。

#### <a name="retention-labels-and-policies-that-apply-them"></a>保留标签和应用它们的策略

在你发布保留标签后，它们将包含在 **保留标签策略** 中，以便管理员和用户将其应用至内容。 如下图所示：

1. 一个保留标签可包含在多个保留标签策略中。

2. 保留标签策略指定了保留标签的发布位置。 同一位置可包含在多个保留标签策略中。

![如何将保留标签添加到为其指定位置的标签策略](../media/retention-labels-and-policies.png)

你还可以创建一个或多个 **自动应用保留标签策略**，其中每个策略都有一个保留标签。 如果使用此策略，当满足你在策略中指定的条件时，保留标签就会自动应用。

#### <a name="retention-label-policies-and-locations"></a>保留标签策略和位置

不同类型的保留标签可发布到不同位置，具体视保留标签用途而定。
  
| 如果保留标签是… | 可以将标签策略应用于… |
|:-----|:-----|
|发布给管理员和最终用户  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 组  <br/> |
|根据敏感信息类型或可训练的分类器自动应用  <br/> |Exchange（仅全部邮箱）、SharePoint 和 OneDrive  <br/> |
|根据查询自动应用  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 组  <br/> |
   
在 Exchange 中，你自动应用的保留标签只会应用于新发送的邮件（传输中的数据），而不是应用于邮箱中当前的所有项（静态数据）。 此外，用于敏感信息类型和可训练的分类器的自动应用保留标签应用于所有邮箱；你无法选择特定的邮箱。
  
Exchange 公用文件夹、Skype、Teams 和 Yammer 消息不支持保留标签。 若要保留并从这些位置中删除内容，请改用保留策略。

#### <a name="only-one-retention-label-at-a-time"></a>一次只能分配一个保留标签

电子邮件或文档一次只能应用有一个保留标签。 保留标签可以由最终用户或管理员[手动](create-apply-retention-labels.md#manually-apply-retention-labels)应用，也可以使用以下任一方法自动应用：

- [自动应用标签策略](apply-retention-labels-automatically.md)
- [Microsoft SharePoint Syntex 中的文档理解模型](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- [SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) 或 [Outlook 的默认标签](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)
- [Outlook 规则](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

对于标准保留标签（它们不会将项目标记为[记录或监管记录](records-management.md#records)）：

- 管理员和最终用户可以手动更改或删除应用于内容的现有保留标签。 

- 当内容已应用保留标签时，现有标签不会自动删除或替换为另一个保留标签，但有一个可能的例外：现有标签已作为默认标签应用。
    
    有关使用默认标签应用标签行为的详细信息，请执行以下操作：
    - SharePoint 的默认标签：[对 SharePoint 使用默认标签时的标签行为](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)
    - Outlook 的默认标签：[将默认保留标签应用于 Outlook 文件夹](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)

- 如果有多个自动应用标签策略可以应用保留标签，并且内容满足多个策略的条件，则应用最旧的自动应用标签策略（按创建日期）的保留标签。

当保留标签将项目标记为记录或管理记录时，这些标签不会自动更改。 只有容器的管理员才能手动更改或删除将项目标记为记录而不是管理记录的保留标签。 有关详细信息，请参阅[比较对允许或阻止的操作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。

#### <a name="monitoring-retention-labels"></a>监视保留标签

在 Microsoft 365 合规中心，使用 **“数据分类”** > **“概述”** 来监视保留标签在租户中的使用方式，并确定已标记项目的位置。 有关详细信息（包括重要先决条件），请参阅[了解你的数据 - 数据分类概述](data-classification-overview.md)。

然后，你可以通过使用[内容资源管理器](data-classification-content-explorer.md)和[活动资源管理器](data-classification-activity-explorer.md)来深入了解详细信息。

> [!TIP]
>请考虑使用其他的一些数据分类见解（如可训练分类器和敏感信息类型），帮助你识别可能需要保留或删除的内容，或者作为记录进行管理的内容。

Office 365 安全与合规中心的保留标签概述信息与 **“信息管理政策”** > **“仪表板”** 中的概述信息相同，更加详细的信息可以在 **“信息管理政策”** > **“标签活动资源管理器”** 中找到。 有关从较旧版本的管理中心监视保留标签的更多信息，请参阅以下文档：
- [查看数据管理报告](view-the-data-governance-reports.md)
- [数据分类入门](data-classification-overview.md)。
- [查看文档的标签活动](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a>使用“内容搜索”来查找所有带有特定保留标签的内容

在将保留标签应用到内容后（无论是由用户应用还是自动应用），你都可以通过内容搜索来查找已经应用特定保留标签的所有项目。

创建内容搜索时，选择“**保留标签**”条件，然后输入完整的保留标签名称或标签名称的一部分，并使用通配符。 有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。
  
![保留标签条件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a>比较保留策略和保留标签的功能

请使用下表来帮助你根据功能确定是使用保留策略还是保留标签。

|功能|保留策略 |保留标签|
|:-----|:-----|:-----|:-----|
|保留设置可以是“保留后删除”、“仅保留”或“仅删除” |是 |是 |
|支持的工作负载： <br />- Exchange <br />- SharePoint <br />- OneDrive <br />- Microsoft 365 组 <br />- Skype for Business <br />- Teams<br />- Yammer|<br /> 是 <br /> 是 <br /> 是 <br /> 是 <br /> 是 <br /> 是 <br /> 是 | <br /> 是，但公用文件夹除外 <br /> 是 <br /> 是 <br /> 是 <br /> 否 <br /> 否 <br /> 否 |
|自动应用保留 | 是 | 是 |
|基于条件应用保留 <br /> - 敏感信息类型、KQL 查询、可训练的分类器| 否 | 是 |
|手动应用保留 | 否 | 是 |
|对最终用户显示 UI | 否 | 是 |
|在内容移动时仍继续应用在内容上 | 否 | 是，在您的 Microsoft 365 租户中 |
|将项声明为记录| 否 | 是 |
|从内容被标记或事件发生时开始计算保留期 | 否 | 是 |
|处置评审 | 否| 是 |
|最长 7 年的处置证明 | 否 |是，当项被声明为记录时|
|审核管理员活动| 是 | 是|
|识别遵循保留设置的项： <br /> - 内容搜索 <br /> - 数据分类页、内容资源管理器、活动资源管理器 | <br /> 否 <br /> 否 | <br /> 是 <br /> 是|

请注意，可以同时将保留策略和保留标签用作互补的保留方法。 例如：

1. 你创建并配置一个保留策略，以便在自最后一次修改内容起 5 年后自动删除内容，同时你将此策略应用于所有 OneDrive 帐户。

2. 你创建并配置一个保留标签来永久保留内容，同时你将此标签添加到发布到所有 OneDrive 帐户的标签策略中。 你向用户解释如何将此标签手动应用于特定文档，这些文档应排除在 5 年未修改后自动删除范围之外。

若要详细了解保留策略和保留标签是如何协同工作的，以及如何确定它们的合并结果，请参阅下一部分，其中介绍了保留原则和优先级。

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>保留原则或优先级

与保留标签不同，您可以对同一内容应用多个保留策略。 每个保留策略都可以导致保留操作和删除操作。 此外，该商品还可能受到保留标签上的这些措施的约束。

在这种情况下，当项目可以经受可能彼此冲突的多个保留设置时，确定结果的优先顺序是什么？

结果不是赢得单个保留策略或单个保留标签的结果，而是保留项目多长时间（如果适用）以及删除项目的时间（如果适用）。 这两个操作是根据应用于项目的所有保留设置彼此独立计算的。

例如，一个项目可能要受一个已配置为仅删除操作的保留策略的约束，而另一个则要配置为保留然后删除的保留策略。 因此，此项只有一个保留操作和两个删除操作。 保留和删除操作可能彼此冲突，并且这两个删除操作的日期可能冲突。 为了得出结果，你必须运用保留原则。

概括来说，可以确定的是，保留始终优先于删除，然后是最长保留期胜出。 这两个简单的规则总是决定一个项目将保留多长时间。

还有其他一些因素决定何时删除项目，其中包括保留标签中的删除操作始终优先于保留策略中的删除操作。

使用以下流程了解单个项目的保留和删除结果，其中每个级别从上到下都充当冲突平局。 如果结果由第一个级别决定，由于没有进一步冲突，则不需要再前进到下一个级别，等等。

> [!IMPORTANT]
> 如果您使用的是保留标签：在使用此流程确定同一项目上多个保留设置的结果之前，请确保您知道[应用了哪个保留标签](#only-one-retention-label-at-a-time)。

![保留原则关系图](../media/principles-of-retention.png)
  
有关四种不同级别的说明：
  
1. **保留优先于删除。** 当内容也具有保留设置以保留它时，它不会被永久删除。  
    
    示例：电子邮件必须遵循Exchange的保留策略，该策略配置为在三年后删除项目，并且还应用了保留标签，该标签被配置为可以保留项目五年。
    
    电子邮件将保留五年，因为此保留操作优先于删除操作。 由于推迟了删除操作，该电子邮件在五年结束时被删除。

2. **优选最长的保留期。** 如果内容遵循多个在不同时间段内保留内容的保留设置，内容会一直保留到最长保留期结束。
    
    示例：Marketing SharePoint网站中的文档受两个保留策略的约束。 为所有SharePoint网站配置第一个保留策略，以将项目保留五年。 为特定的SharePoint网站配置第二个保留策略，以将项目保留十年。
    
    该Marketing SharePoint网站中的文档将保留十年，因为这是最长的保留期。

3. **显式包含优先于隐式包含。** 适用于确定何时删除项目： 
    
    1. 与保留策略相比，保留标签（无论如何应用）都提供了显式保留，因为保留设置将应用于单个项目，而不是从容器隐式分配。 这意味着从保留标签删除操作始终优先于从任何保留策略删除操作。
        
        示例：文档受两个保留策略的约束，删除策略分别为5年和10年，以及保留标签的删除策略为7年。
        
        七年后删除文档，因为保留标签的删除操作具有优先权。
    
    2. 仅当具有保留策略时：如果某个位置的保留策略的作用域是使用包含配置（例如Exchange电子邮件的特定用户），则该保留策略优先于同一位置的无范围保留策略。
        
        不受限制的保留策略是在不指定特定实例的情况下选择位置的位置。 例如，**Exchange电子邮件** 和默认设置 **“所有收件人”** 是不受范围限制的保留策略。 或者，**SharePoint网站** 和 **“所有网站”** 的默认设置。 在对保留策略进行范围划分时，它们在此级别具有相同的优先级。
        
        示例1：电子邮件受两个保留策略的约束。 第一个保留策略不受范围限制，并在十年后删除项目。 第二个保留策略适用于特定邮箱，并在五年后删除项目。
        
        五年后将删除电子邮件，因为有范围的保留策略中的删除操作优先于无范围的保留策略。
        
        示例2：用户的OneDrive帐户中的文档受两个保留策略的约束。 第一个保留策略的范围包括该用户的OneDrive帐户，并在10年后执行删除操作。 第二个保留策略的范围包括该用户的OneDrive帐户，并且七年后将执行删除操作。
        
        由于两个保留策略都已确定范围，因此无法在此级别确定何时删除此文档。

4. **最短删除期优先。** 适用于确定何时从保留策略中删除项目以及从上一级别无法解决结果：在最短保留期结束时删除内容。
    
    示例：用户的OneDrive帐户中的文档受两个保留策略的约束。 第一个保留策略的范围包括该用户的OneDrive帐户，并在10年后执行删除操作。 第二个保留策略的范围包括该用户的OneDrive帐户，并且七年后将执行删除操作。
    
    七年后将删除此文档，因为这是这两个范围的保留策略的最短保留期。

请注意，受到电子数据展示保留的项目也属于保留的第一原则； 它们不能被任何保留策略或保留标签删除。 解除保留后，保留原则将继续适用于它们。 例如，它们然后可能会受到未期满的保留期限或推迟的删除操作。

结合了保留和删除操作的更复杂的示例：

1. 一个项目已应用以下保留设置：
    
    - 五年后只能删除的保留政策
    - 保留政策，保留三年然后删除
    - 仅保留七年的保留标签
    
    **结果**：该项目保留7年，因为保留优先于删除，并且7年是最长的保留期。 在此保留期结束时，由于在保留项目时推迟了对保留策略的删除操作，因此删除了该项目。
    
    尽管两种保留策略的删除操作日期不同，但是最早可以删除的项目是最长保留期（比两个删除日期长）的结束。 在本示例中，删除日期没有冲突需要解决，因此所有冲突都在第二个级别解决。

2.  一个项目已应用以下保留设置：
    
    - 不受限制的保留策略，仅在十年后删除
    - 有范围的保留策略，可以保留五年然后删除
    - 保留标签，保留三年，然后删除
    
    **结果**：该项目将保留五年，因为这是最长的保留期。 在该保留期结束时，由于从保留标签时推迟了三年的保留标签删除操作，删除了该项目。 从保留标签中删除优先于从所有保留策略中删除。 在此示例中，所有冲突都由第三个级别解决。

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a>使用保存锁来限制对策略的更改

某些组织可能需要遵从由监管机构定义的规则，如美国证券交易委员会 (SEC) 规则 17a-4，该规则要求在启用保留策略之后，不得关闭该策略或降低其限制。 

保存锁可确保组织符合此类监管要求，因为它可以锁定保留策略或保留标签策略，因此任何人（包括管理员）都无法关闭该策略、删除该策略或降低其限制性。
  
在创建保留策略或保留标签策略后应用保存锁。 有关更多信息和说明，请参阅 [使用保存锁来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)。

## <a name="releasing-a-policy-for-retention"></a>发布保留策略

如果你的保留策略没有保留锁，你可以随时删除你的策略，这将有效地关闭之前应用的保留设置。 你也可以保留该策略，但将位置状态更改为关闭。
 
当你执行上述任一操作时，保留在保存库中的任何 SharePoint 或 OneDrive 内容都不会立即永久删除。 相反，为了防止意外的数据丢失，我们设置了 30 天的宽限期。在此期间，相应策略的内容不会在保留库中到期，所以你可以根据需要从其中还原任何内容。 此外，在宽限期内无法手动删除此内容。

你可以在宽限期内将位置状态更改为启用，并且不会删除该策略的内容。

SharePoint 和 OneDrive 中的此 30 天宽限期对应于 Exchange 中的 30 天延迟保留。 有关详细信息，请参阅[管理延迟保留的邮箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。

## <a name="auditing-retention-configuration"></a>审核保留配置

[启用审核后](turn-audit-log-search-on-or-off.md)，管理员针对保留政策和保留标签的操作会被保存到审核日志中。 例如，创建、配置或删除保留政策或标签时会创建审核事件。 如需完整的列表，请参阅[保留策略和保留标签活动](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>用于保留策略和保留标签的 PowerShell cmdlet

若要使用保留 cmdlet，必须先[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。 然后，使用以下任何 cmdlet：

- [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a>何时使用保留策略和保留标签或电子数据展示保留

虽然保留设置和[电子文件展示案列创建的保留](create-ediscovery-holds.md)都可以防止数据被永久删除，它们是针对不同情况设计的。 为了帮助你了解差异并决定使用哪个，请使用以下指南：

- 在保留策略和保留标签中指定的保留设置旨在用于长期信息管理策略，以保留或删除符合法规要求的数据。 通常范围很广，主要重点是位置和内容，而不是单个用户。 保留期的开始和结束是可配置的，可以选择自动删除内容，无需其他管理员干预。

- 电子数据展示保留（核心电子数据展示或高级电子数据展示案例）的设计期限有限，可以保存数据以进行法律调查。 范围是特定的，重点是已识别用户拥有的内容。 保留期的开始和结束是不可配置的，但取决于单个管理员的操作，如果保留被释放，则无法选择自动删除内容。

比较保留与电子数据展示保留的摘要：

|注意事项|保留 |电子数据展示保留|
|:-----|:-----|:-----|:-----|
|业务需求： |合规性 |法律 |
|时间范围： |长期 |短期 |
|焦点： |广泛、基于内容 |特定、基于用户 |
|开始和结束日期可配置： |是 |否 |
|内容删除： |是（可选） |否 |
|管理开销： |低 |高 |

如果内容遵循保留设置和电子数据展示保留，则保存电子数据展示保留的内容始终具有优先权。 这样，[保留原则](#the-principles-of-retention-or-what-takes-precedence)扩展到电子数据展示保留，因为它们保留数据，直到管理员手动释放保留为止。 但是，尽管有此优先顺序，但不要将电子数据展示保留用于长期信息治理。 如果担心自动删除数据，则可以将保留设置配置为永久保留项目，或将[处置审查](disposition.md#disposition-reviews)与保留标签一起使用。

如果你使用的是旧的电子数据展示工具来保留数据，请参阅以下资源：

- Exchange: 
    - [就地保留和诉讼保留](https://go.microsoft.com/fwlink/?linkid=846124)
    - [如何识别为 Exchange Online 邮箱设置的保留类型](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)

- SharePoint 和 OneDrive： 
    - [在电子数据展示中心将内容添加到事例并将源就地保留](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)

- [旧版电子数据展示工具的停用](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a>使用保留策略和保留标签，而不是旧功能

如果需要在 Microsoft 365 中主动保留或删除内容来实现信息管理，建议使用保留策略和保留标签，而不是以下旧功能。

如果当前使用这些旧功能，可以继续将它们与保留策略和保留标签并行使用。 但我们建议今后使用保留策略和保留标签。 它们为你提供了在 Microsoft 365 中集中管理内容保留和删除的单一机制。

**Exchange Online 中的早期功能：**

- [保留标记和保留策略](https://go.microsoft.com/fwlink/?linkid=846125)，亦称为[邮件传递记录管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126)（仅限删除）

**SharePoint 和 OneDrive 中的早期功能：**

- [文档删除策略](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff)（仅删除）
    
- [配置就地记录管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a)（仅限保留） 
    
- [使用网站关闭和删除策略](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5)（仅限删除） 
    
- [信息管理策略](intro-to-info-mgmt-policies.md)（仅限删除）
     
如果已将 SharePoint 网站配置为应用保留列表或库的内容的内容类型策略或信息管理策略，则这些策略会在保留策略生效时被忽略。 

## <a name="related-information"></a>相关信息

- [SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Microsoft Teams 的限制和规范](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [有助于你满足信息治理和记录管理监管要求的资源](retention-regulatory-requirements.md)

## <a name="configuration-guidance"></a>配置指南

如果已准备好创建保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。

若要创建和应用保留标签，请执行以下操作：
- [创建保留标签并在应用中应用它们](create-apply-retention-labels.md)
- [自动向内容应用保留标签](apply-retention-labels-automatically.md)

