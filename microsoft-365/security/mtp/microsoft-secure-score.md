---
title: Microsoft 安全功能分数
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员可预期的内容。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b337f020702b60ceeb02043e9b66d5614f58c228
ms.sourcegitcommit: 27a7a373ca77375fdab0690a899135fad16c3cf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435556"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全功能分数

Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。 从 Microsoft 365 安全中心的中央仪表板中，组织可以监视和使用其 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。

安全分数可帮助组织执行以下操作：  

* 报告组织安全状况的当前状态。
* 通过提供可发现性、可见性、指导和控制改进其安全状况。  
* 与基准进行比较并建立关键绩效指标（Kpi）。

安全得分为组织提供了对指标和趋势的强健可视化的访问，与其他 Microsoft 产品的集成，与类似组织的分数比较，以及更多。 分数还可以反映第三方解决方案解决建议操作的时间。

此外，你还可以通过[Microsoft GRAPH API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)访问你的建议和评分。

## <a name="how-it-works"></a>如何工作

为您提供配置推荐安全功能、执行与安全相关的任务（如查看报告）或使用第三方应用程序或软件解决改进操作的相关积分。 某些改进操作仅在完全完成时给出点，而有些改进操作在为某些设备或用户完成一些点时提供部分点。 安全性应始终与可用性平衡，而不是每个建议对您的环境都适用。

你的分数将实时更新，以反映可视化和改进操作页面中显示的信息。 安全分数也会每天同步，以接收有关每个操作的已实现分数的系统数据。

### <a name="how-improvement-actions-are-scored"></a>如何对改进行动进行评分

大多数都是以二进制方式进行评分—如果实施改进操作（如创建新策略或打开特定设置），则将获得 100% 的点数。 对于其他改进操作，点作为总配置的百分比提供。 例如，如果通过使用多重身份验证保护您的所有用户，并且您只有 5% 以上的用户都受到保护，则提高操作的状态为30点。在 2 100 个点的部分分数（5个受保护/100 总数 * 30 个最大值 = 2 pt）中，可获得系数 部分分数）。

## <a name="required-permissions"></a>所需权限

若要拥有访问 Microsoft 安全分数的权限，您必须在 Azure Active Directory 中为以下角色分配一个角色。

### <a name="read-and-write-roles"></a>读取和写入角色

通过读取和写入访问权限，您可以进行更改，并直接与安全分数进行交互。 您还可以将只读访问权限分配给其他用户。

* CompanyAdministrator
* SecurityAdministrator
* ExchangeAdmin
* SharePointAdmin

### <a name="read-only-roles"></a>只读角色

如果具有只读访问权限，您将无法编辑 "改进" 操作的状态或注释、编辑分数区域或编辑自定义比较。

* HelpdeskAdmin
* UserAccountAdmin
* ServiceSupportAdmin
* SecurityReader
* SecurityOperator
* GlobalReader

### <a name="graph-api"></a>Graph API

若要访问 Graph API，除了角色之外，还需要具有以下作用域之一：

* Securityevents.readwrite.all （适用于只读角色）
* Securityevents.readwrite.all （用于读取和写入角色）

## <a name="rich-experiences--security-recommendations"></a>安全建议 & 丰富的体验

在 Microsoft 安全得分中，Office 365、Azure AD、Intune 和云应用安全性方面有一些建议，其中包含来自 Azure 安全中心和 Microsoft Defender Security Center 的建议即将推出。

为了帮助您更快地了解所需的信息，Microsoft 建议已分成组：

* Identity （Azure AD 帐户和角色）
* 数据（Office 365 文档）
* 设备（Microsoft Defender ATP 设备）
* 应用（电子邮件和云应用）
* 基础结构（Azure 资源）

在 "Microsoft 安全分数概述" 页中，您可以看到在这些组之间如何拆分点以及哪些点可用。 [！注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置，以及可采取的优先改进措施以提高成绩。 您可以使用此数据进行操作，并对安全状态进行重大差别。  

![安全积分主页](../media/secure-score/homepage-original.png)
*图1： Microsoft 安全分数概述页面*

## <a name="take-action-to-improve-your-score"></a>采取行动以提高成绩

"改进操作" 选项卡列出了解决可能的攻击面的安全建议，以及它们的状态（已完成、未完成、已通过第三方解决和忽略）。 您可以搜索、筛选和分组所有改进操作。

### <a name="ranking"></a>排名

排名基于要达到的剩余点数、实现难度、用户影响和复杂性。 最高排名改进操作的剩余分数与较低的难度、用户影响和复杂性较低。

### <a name="actions"></a>操作

Microsoft 安全分数不会跟踪标记为 [未评分] 的操作。 你仍可以采取措施，但完成这些操作不会影响你的分数。 如果某个操作在将来被 Microsoft 安全得分跟踪，并且您已完成该操作，则安全得分将自动反映所做的更改。

当您选择特定的 "改进" 操作时，将显示 "飞出"。 若要完成此操作，您有几个选项：

1. 选择 "**查看设置**" 以转到配置屏幕并进行更改。 然后，您可以在飞出的顶部看到该操作值得的要点。点可能需要长达24小时才能更新。

2. 选择 "**通过第三方解决**"，因为改进操作已由第三方应用程序或软件解决。 您可以获得该操作所需要的要点，这样您的安全分数就能更好地反映您的总体安全状况。 如果第三方不再涵盖该控件，则可以将 "改进" 操作标记为 "不完成"。 请注意，如果将改进操作标记为通过第三方解决，Microsoft 无法了解是否满足评分要求。

3. 选择 "**忽略**"，因为您已决定接受风险而不执行改进操作。 忽略 "改进" 操作后，您可以实现的安全分数点总数将减少。 您可以在历史记录中查看此操作，也可以随时撤消。

4. 选择 "**审阅**"，因为改进操作要求您定期查看环境的一部分以获取和保留点。 例如，应每周查看邮箱转发规则，以确保不会从您的网络中泄露数据。 您无需进行任何更改，但需要执行操作。 如果您定期查看规则，您将收到要点。 如果不是，则减少分数。

![安全分数提高操作示例](../media/secure-score/secure-score1x450.png) ![安全分数评审改进操作示例](../media/secure-score/secure-score2x450.png)

*图 2 & 3：改进操作 flyouts*

## <a name="monitor-improvements-over-time"></a>随着时间的推移监视改进

您可以在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。在图下方是在所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。 您可以自定义日期范围并按类别进行筛选。

## <a name="risk-awareness"></a>风险感知

Microsoft 安全分数是基于系统配置、用户行为和其他与安全相关的度量的安全状态的数字摘要;它并不是对系统或数据受到破坏的可能性的绝对度量。 相反，它表示您在 Microsoft 环境中已采用安全控制的程度，这有助于抵消受到破坏的风险。 无在线服务完全不受安全破坏，并且安全分数不应以任何方式解释为保证安全。

## <a name="whats-coming"></a>接下来是什么？

为了使 Microsoft 安全得分更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。 你的分数和可能的最大分数都将发生变化。 但是，这并不意味着您的安全状况发生了变化。

### <a name="removing-not-scored-and-review-improvement-actions"></a>删除 "未评分" 和 "审阅" 改进操作

安全得分的原则之一是，分数应标准化且易于关联。 具有不可衡量或可操作的改进操作已导致混淆。 仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。 不计分的提高操作不可度量，并且与其他改进操作相比，不会将 "改进" 操作评估为与相同标准。  

出于这些原因，所有未评分或要求的改进操作将暂时删除。 您的部件不需要执行任何操作。

### <a name="simplification-of-the-point-system"></a>简化了点系统

若要在多个体验中标准化要点，每个安全分数改进操作点总数将更新为10磅或更少。 在我们目前所拥有的安全控制的广泛 breather 和将来将添加的安全控制中，必须更加一致。 虽然这是一项重大更改，并且你将在点汇总中看到一个拖放，但你的安全状态不会有任何变化。  

### <a name="preview-features"></a>预览功能

预览版本中将包含以下功能：

* CISO 和潜在客户级别讨论的所有新指标和趋势视图
* 跟踪和基准成绩的新方法
* 更好地跟踪和监控分数回归
* 筛选、标记、搜索和分组您的改进操作
* 使用分数预测和计划操作来管理未来目标
* 更多！

## <a name="we-want-to-hear-from-you"></a>我们希望收到你的来信

如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。 我们正在监视社区，并将提供帮助。
