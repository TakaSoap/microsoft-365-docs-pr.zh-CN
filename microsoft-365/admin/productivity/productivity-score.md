---
title: Microsoft 工作效率分数
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 工作效率分数概述。
ms.openlocfilehash: 82dc26aea5c573b63bb66d087b332e3301e71409
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48376969"
---
# <a name="microsoft-productivity-score-preview"></a> (预览的 Microsoft 工作效率分数) 

生产效率分数可帮助组织转换工作方式，并了解有关用户如何使用 Microsoft 365 以及支持它们的技术体验方面的见解。 分数反映了贵组织对人员和技术体验的业绩，并将您的成绩与您的组织（如您的组织）进行比较。

分数包括：

- 帮助您了解用户如何使用 Microsoft 365 产品在平台之间进行协作、沟通和工作的**指标**。
- 有关数据的**见解**，可帮助您确定提高员工工作效率和满意度的机会。
- 您可以采取一些**建议的措施**来帮助组织中的人员有效地使用 Microsoft 365 产品，以便每个人都可以完成其最佳工作。

我们在两个方面提供数据、见解和建议： 

- **人员体验：** 我们衡量人员如何对内容进行协作、如何使用 Microsoft 365 产品进行通信，以及它们是否在平台上使用 Microsoft 365。 

    我们提供了这些见解，因为当人们在线协作时，他们可以节省时间。 由于可以自由地在任何设备上运行，因此它们的工作效率更高且实现满意。 以灵活的方式进行通信可使用户更加高效、形成更好的关系，并且您的组织更加统一。 有关证据，请参阅 [Forrester report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)。

- **技术体验：** 生产效率取决于可靠和能力强的技术以及 Microsoft 365 的有效使用。 我们提供了 [终结点分析](https://aka.ms/endpointanalytics)，可帮助你了解你的终结点硬件和软件的性能和运行状况问题对你的用户的生产率有何影响。 我们还为你的组织提供了建议的操作，以便对其进行补救以及 Microsoft 365 网络连接见解。

有关概述和先决条件的详细信息，请参阅 [什么是终结点分析](https://docs.microsoft.com/mem/analytics/overview) 。 若要了解有关 Microsoft 365 网络 connectivity insights 的详细信息，请阅读 [网络连接概述](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-networking-overview)。
  

## <a name="how-the-score-is-calculated"></a>如何计算分数

你的工作效率分数基于你的人员和技术体验类别的组合得分。 每个类别平均加权，每个类别总共100点。 生产率分数的总可能分数为500。

### <a name="score-categories"></a>分数类别 

- 内容协作 (100 点) 
-  (100 磅的通信) 
- 移动 (100 点) 
- 终结点分析 (100 点) 
- 网络连接 (100 磅) 
- **总可能值 = 500 磅**
 
 在每个类别中，我们都确定主要活动的模式，这些是有关用户如何使用 Microsoft 365 产品在平台之间进行协作、通信和工作的指标。 我们为关键活动提供了28天和180天的视图。 我们还提供不属于分数计算的支持指标，但对于帮助您确定可对其进行驱动更改的基础行为和设置，这一点非常重要。

### <a name="products-included-in-productivity-score"></a>包含在工作效率分数中的产品 

生产效率分数包括来自 Exchange、SharePoint、OneDrive、工作组、Word、Excel、PowerPoint、OneNote、Outlook、Yammer 和 Skype 的数据。

你的得分每天更新，并反映最近 28 (中完成的用户操作，包括当前日期) 。


## <a name="pre-requisites"></a>先决条件 

你需要 Microsoft 365 for business 或 Office 365 for business 订阅才能获取人员体验数据，并且你需要使用多租户云服务。 若要获取租户的终结点分析数据，需要将 Microsoft Intune 添加到你的订阅中。 Intune 可帮助您通过管理设备和应用来保护您的组织的数据。       安装 Intune 后，可以在 Intune 体验中启用终结点分析。 了解有关 Microsoft Intune 的详细信息。 

若要查看组织的工作效率分数，您必须具有以下角色之一： 

- 全局管理员 
- Exchange 管理员
- SharePoint 管理员 
- Skype for Business 管理员 
- Teams 管理员 
- 全局读取者 
- 报告读取者 

您可以在 "**报告**  >  **效率分数**" 下访问 Microsoft 365 管理主页的体验。

## <a name="interpreting-productivity-score"></a>解释工作效率分数 

"生产力分数" 主页显示总分和分数历史记录，以及每个类别的主要洞察力

![工作效率分数主页](../../media/pslanding.png)

**您的分数** 显示为百分比值和磅值，以便您可以查看 (分子) 的要点以及 (分母) 的最大可能分数。

**对等基准** 使您能够将您的成绩与像你的组织进行比较。 对于 "人员体验" 类别，对等基准度量值计算为一组相似组织中的度量值的平均值。 该集由您所在区域中的组织组成，其中包含数量相似的许可用户、许可证类型、行业和 tenure 与 Microsoft 365。 

终结点分析对等基准包括设备启动性能的目标以及基于所有租户中聚合的中间值的建议软件配置。

对于网络连接，推荐的准则为80点。

" **分数细分** " 部分提供了按人员和技术经验领域的基准的工作效率分数细分。

分数历史记录显示最近6个月内每个类别中的得分如何变化。

**人员体验**和**技术体验**领域包含这些领域中类别的主要见解。 您可以单击每个类别以查看更深入的见解。

## <a name="category-details-pages"></a>类别详细信息页面

每个类别详细信息页面显示主要的洞察力和支持指标，以及可以采取的相关研究和操作以促进组织中的变化。 研究支持每个类别的主要见解背后的重要性和基本原理。 有关详细信息，请 [参阅 Forrester report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)。

### <a name="content-collaboration-details"></a>内容协作详细信息

内容协作的主要洞察力是创建、阅读和协作 (编辑和共享) online 的人员数量。 这些措施很重要，因为信息检索显示当人们使用联机文件进行协作时，每个人平均每周保存约2个小时。

我们将内容协作定义为一个人，创建和共享 Office 文件，然后至少是其他人阅读它。 

**读者**：访问或下载 OneDrive 或 SharePoint 中的联机文件的用户。

**创建者：** 创建、修改、上传、同步、签入、复制或移动联机 OneDrive 或 SharePoint 文件的人员。

**协作**者：使用 OneDrive 或 SharePoint 与联机文件进行协作的人员。 如果用户在创建或修改了一个或多个联机 Office 应用程序或 PDF 云文档之后，他们会在28天的时段内读取或编辑该文档，这两个人是协作者。

考虑协作的文件类型为 Word、Excel、PowerPoint、OneNote 和 PDF 文件。

我们为您组织中的设备以及网络连接见解提供了有关内容协作的深入了解，因为联机文件协作需要能够快速启动并拥有最新软件以及与 Microsoft 365 的良好连接的可靠设备。

### <a name="communication-details"></a>通信详细信息

通信的主要洞察力是组织中的人员使用电子邮件、聊天和社区帖子进行通信的频率。 当用户使用各种实时通信工具时，他们可以选择可帮助他们实现最高效的通信模式，如聊天和社区，帮助他们跨不同的办公室位置开发关系。

### <a name="mobility-details"></a>移动性详细信息

移动的主要洞察力是访问文件以及跨多个平台使用电子邮件和聊天的人员数量。 能够在所选设备上的任何位置工作，对于具有销售角色、高级经理、顾问和其他需要从 office 执行工作以提高工作效率的人员来说非常重要。 对这些工作人员的改进会产生很大影响。 

我们衡量在两个或更多平台（包括桌面、移动和 web）中使用至少一个 Microsoft 365 效率应用的人员的百分比和绝对数量。 我们测量的工作效率应用是 Outlook、团队、Word、Excel、PowerPoint、OneNote、Yammer 和 Skype。 用户必须拥有 Microsoft 365 应用程序，才能衡量企业、Exchange、Yammer、Skype 或团队许可证。 

## <a name="business-continuity-special-report"></a>业务连续性特殊报告

业务连续性报告是适用于所有 Microsoft 365 客户的受限制的工作场所智能报告，可帮助他们在这一富有挑战性的时间指导其组织。  

此报告可帮助业务负责人了解： 

- 移动与远程工作的转变对协作和通信的影响。 

- 用户调整为在家工作时对工作寿命余额的影响。 

- 如果远程会议支持有效的决策制定。

[了解有关业务连续性报告的详细信息](https://aka.ms/bcrps)

[了解有关 Microsoft Graph 的详细信息](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>我们希望收到你的来信

分享你对工作效率分数的看法以及你对如何改进想法的看法。 使用产品中的 **反馈** 部分和/或与 ProductivityScorePreview@service.microsoft.com 的工作效率分数团队联系。
