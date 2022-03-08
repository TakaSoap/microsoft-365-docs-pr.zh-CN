---
title: Microsoft 生产力分数
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
description: 了解 Microsoft 生产力分数如何反映人员和技术体验度量，并与类似规模的组织进行比较。
ms.openlocfilehash: 24a84c3780ec3787b76f78acbe9c0c109a27c639
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327065"
---
# <a name="microsoft-productivity-score"></a>Microsoft 生产力分数 

生产力分数通过深入了解你的组织如何使用 Microsoft 365 以及支持它的体验来支持数字化转型历程。 组织的分数反映了人员和技术经验的衡量标准，可以与规模类似的组织基准进行比较。

它会提供：

- **指标** 以帮助你了解目前处于数字化转型历程的哪一阶段。
- **见解** 针对数据帮助你找到组织中提高生产力和满意度机会。
- **建议采取的措施** 可帮助组织高效地使用 Microsoft 365 产品。

我们在两个方面提供指标、见解和建议： 

- **人员的经验：** 量化组织如何使用如内容协作、移动性、通信、会议和团队合作等 Microsoft 365 类别进行工作。  

    对于上述每一个类别，我们通过公共研究来确定一些最佳实践和相关益处，采用提高组织效率的形式。 例如，Forrester 研究显示，当人们互相合作并在云端（而不是电子邮件附件）共享内容时，他们每周能省下100分钟。 此外，我们会量化这些最佳实践在你的组织中的使用情况，以帮助你了解在数字化转型历程中的位置。 

- **技术体验：** 你组织的工作效率取决于可靠、性能良好的技术以及对 Microsoft 365 的高效使用。 [终结点分析](https://aka.ms/endpointanalytics) 可帮助你了解硬件和软件的性能和运行状况问题如何影响你的组织。 Microsoft 365 应用程序健康状况可帮助你了解组织中的设备是否在推荐渠道上运行 Microsoft 365 应用程序。

## <a name="before-you-begin"></a>准备工作

有关概述和先决条件的详细信息，请参阅[什么是终结点分析](/mem/analytics/overview)。 若要了解有关 Microsoft 365 网络连接见解的详细信息，请参阅 [网络连接概述](../../enterprise/microsoft-365-networking-overview.md)。

要获取人员体验数据，需要 Microsoft 365 商业版或 Office 365 企业版订阅。 要获取租户的终结点分析数据，需要将 Microsoft Intune 添加到你的订阅中。 Intune 通过管理设备和应用来帮助保护组织数据。 拥有 Intune 后，可在 Intune 体验内启用终结点分析。 若要了解关于 Microsoft Intune 的详细信息，请参阅 [Microsoft Intune 文档](/mem/intune/)。 

> [!NOTE]
> 获取生产力分数功能无需工作区分析许可证。

Productivity Score 仅在 Microsoft 365 管理中心中提供，并且只能由具有以下角色之一的 IT 专业人员访问：  

- 全局管理员
- Exchange 管理员
- SharePoint 管理员
- Skype for Business 管理员
- Teams 管理员
- 全局读取者
- 报告读取者
- 使用情况摘要报告阅读器

> [!NOTE]
> 只有具有全局管理员角色的 IT 专业人员才能注册或选择加入 Productivity Score 租户。

Microsoft 生产力分数基于角色的访问控制模型能够帮助组织使用 Microsoft 365 进一步推动数字转型，它为组织内的 IT 专家提供了分配角色的灵活功能。

Microsoft 致力于保护个人隐私。此 [隐私文件](privacy.md) 解释了我们为你（作为组织的 IT 管理员）提供的控制措施，用于确保信息的可操作性，同时不会损害你对 Microsoft 的信任。

可在 Microsoft 365 管理员主页的“**报告** > **生产力分数**”下访问该体验。
  
## <a name="how-the-score-is-calculated"></a>计算分数的方式

生产力分数是根据人员和技术体验类别的总分数计算出的。 每个类别的权重均等，共计 100 分。 最高可能的生产力分数为 800。

### <a name="score-categories"></a>分数类别 

- 沟通（100 分）
- 会议（100 分）
- 内容协作（100 分）
- 团队合作（100 分）
- 移动性（100 分）
- 终结点分析（100 分）
- 网络连接失败（100 分）
- Microsoft 365 应用版运行状况（100 分）
- **总共可能 = 800 分**
 
在每个得分类别中，我们都会量化你的组织在数字化转型过程中如何使用 Microsoft 365 的关键指标。 我们提供有关关键活动的 28 天和 180 天视图。 我们还提供了不计入分数但对于帮助你确定可解决的基本的使用统计和配置非常重要的支持性指标。

### <a name="products-included-in-productivity-score"></a>生产力分数中包含的产品 

生产力分数包括 Exchange、SharePoint、OneDrive、Teams、Word、Excel、PowerPoint、OneNote、Outlook、Yammer 和 Skype 中的数据。

你的组织的分数会每天更新，反映最近 28 天（包括当天）完成的用户操作。

## <a name="interpreting-your-organizations-productivity-score"></a>解读你的组织的生产力分数 

“生产力分数”主页显示了组织的总分和分数历史记录以及每个类别的主要见解。

:::image type="content" source="../../media/prodscore-landing.png" alt-text="“报告”中的生产力分数页面。":::

**组织分数** 显示为百分比值和分数。 可查看分子中的分数和分母中的最大可能分数。

**同行基准** 可将你的组织分数与类似组织的分数进行比较。 “人员体验”类别的同行基准是根据一组类似组织中度量值的平均值来计算的。 该组组织由你所在地区中具有相似的许可证用户数、许可证类型、行业和 Microsoft 365 使用期限的组织组成。

> [!NOTE]
> Microsoft 使用内部数据确定组织映射到的行业。 父组织下的租户映射到与父组织相同的行业。 组织无法查看或修改行业映射。

终结点分析同行基准包括设备启动性能的目标，以及基于跨所有租户聚合的中间值而推荐的软件配置。

对于网络连接，推荐的基准是 80 分。

**分数细分** 部分使用人员和技术体验方面的基准对生产力分数进行细分。

“分数历史记录”显示过去 6 个月每个类别中的分数变化。

**人员体验** 和 **技术体验** 包含这两方面中的类别的主要见解。 可以选择每个类别以查看更深入的见解。

## <a name="category-details-pages"></a>类别详细信息页面

每个类别详细信息页面都显示了主要的见解和支持性指标，以及可以采取的推动组织变革的相关调研和行动。 调研可支持每个类别的主要见解的重要性和理论。 有关详细信息，请[阅读 Forrester 报告](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE2PBrb)。

详细信息页面如下：
- [内容协作-人员体验](content-collaboration.md)
- [沟通–人员体验](communication.md)
- [会议-人员体验](meetings.md)
- [移动性-人员体验](mobility.md)
- [团队合作-人员体验](teamwork.md)
- [Microsoft 365 应用版运行状况–技术体验](apps-health.md)
- [终结点分析](/mem/analytics/productivity-score)

## <a name="business-continuity-special-report"></a>业务连续性特殊报告

“业务连续性”报告是向所有 Microsoft 365 客户提供的限时工作区智能报告，可帮助他们在这一困难时期指导其组织。  

此报告帮助组织理解： 

- 改为远程工作的方式对协作和沟通产生的影响。 

- 人们适应在家工作时对工作与生活平衡的影响。 

- 远程会议是否能支持有效的决策制定。

[了解有关业务连续性报告的详细信息](/Workplace-Analytics/tutorials/bcrps)

[了解有关 Microsoft Graph 的详细信息](/graph/)

> [!NOTE]
> 用户也可以选择从 [MyAnalytics 仪表板](/workplace-analytics/myanalytics/use/dashboard-2)获取生产力见解。


## <a name="we-want-to-hear-from-you"></a>欢迎提出宝贵意见

分享有关生产力分数和你对如何改进它的想法。 使用产品中的 **反馈** 部分和/或通过 ProductivityScorePreview@service.microsoft.com 与生产力分数团队联系。

## <a name="related-content"></a>相关内容

[使用报告监视 Microsoft 365 活动](../../admin/activity-reports/activity-reports.md)（文章）\
[启用 Microsoft 365 使用情况分析](../../admin/usage-analytics/enable-usage-analytics.md)（文章）\
[Microsoft 365 管理中心概述]（Microsoft 365 管理中心概述）（../admin-overview/admin-center-overview.md）（视频）