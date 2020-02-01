---
title: Microsoft 合规性分数常见问题解答
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 查找有关 Microsoft 合规性分数的常见问题的解答，这有助于组织简化和自动化风险评估。
ms.openlocfilehash: 81541c66f1bc1ec179faa0180b3135f9b623d319
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595769"
---
# <a name="microsoft-compliance-score-preview-frequently-asked-questions"></a>Microsoft 合规性分数（预览）常见问题解答

## <a name="what-is-compliance-score"></a>合规性分数是什么？

Microsoft 合规性分数是[microsoft 365 合规性中心](microsoft-365-compliance-center.md)中的一项预览功能，可帮助您了解组织的合规性状况。 它将计算基于风险的分数，以衡量您在帮助降低数据保护和法规标准方面的风险的完成操作的进度。 此外，它还提供了内置的控件映射，可帮助您在关键管理法规和标准之间连接通用控件，因此您可以采取一个操作同时满足多个要求，并更好地扩展合规性计划。

## <a name="how-do-i-access-compliance-score"></a>如何访问合规性分数？

请转到[microsoft 365 合规性中心](https://compliance.microsoft.com/)并使用 microsoft 365 全局管理员、合规性管理员或合规性数据管理员角色**登录**。 在左侧导航窗格中选择 "**合规性分数**"。 然后，您应看到[符合性分数仪表板与您的分数](compliance-score-setup.md#understand-the-compliance-score-dashboard)。 如果您没有适当的角色访问权限，则组织的全局管理员可以授予您权限。

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>使用合规性分数所需的角色或权限是什么？

合规性分数使用基于角色的访问控制（RBAC）权限模型，并且您可以执行的操作取决于分配给您的角色的类型。 您的组织的 Microsoft 365 全局管理员是可以在合规性分数中执行安装程序功能和管理角色的人员。 用户至少需要使用**AZURE AD 全局读取器**角色以按合规性分数阅读数据。 在[合规性分数设置](compliance-score-setup.md)中了解有关权限、角色和设置过程的详细信息。

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>合规性分数和合规性管理器之间有何区别？

合规性分数和合规性管理器共享相同的后端，但它们位于两个不同的位置（合规性分数位于 Microsoft 365 合规性中心中，并且合规性管理器位于 Microsoft 服务信任门户中）。 将合规性分数视为合规性管理器的简化版本，使您可以更完整地了解组织的当前合规性状态以及您可以采取的措施来改进它。 虽然您可以在合规性分数中直接执行很多操作，但现在某些功能位于合规性管理器中。 阅读有关[合规性分数和合规性管理器之间关系](compliance-score.md#relationship-to-compliance-manager)的详细信息。

## <a name="who-should-use-compliance-score-and-who-should-use-compliance-manager"></a>应使用合规性分数和谁应使用合规性管理器？

合规性分数对组织中扮演了监视合规性的角色并执行活动以帮助符合法规标准的所有人都很有用。 通过遵守合规性分数，您无需熟悉管理法规和标准，以帮助改进组织的数据保护。 合规性分数是所有用户的最佳起始位置。 在这里，您可以看到您的合规性分数，了解哪些推荐的操作可帮助最大限度地减少风险，在许多情况下，请立即启动以执行这些操作的解决方案。

目前，合规性管理器是用户可以在其中管理评估和创建自定义模板以建立评估的位置。 了解有关仅在公共预览版中[由合规性管理器支持的操作的](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)详细信息。

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>如果得分较高，这是否意味着我完全合规？

不是。 您的合规性分数可衡量您在完成建议的操作以帮助降低数据保护和法规标准方面的风险的过程。 它并不表示对任何特定的标准或法规的组织合规性的绝对度量。 不应以任何方式将合规性分数解释为保证。

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>合规性分数监视的法规和标准是什么？

合规性分数为您提供了基于 Microsoft 365 数据保护基准的初始分数，这是一组包含常见行业法规和标准的控件。 此基线主要从 NIST CSF （美国国家标准和技术协会 Cybersecurity Framework）和 ISO （国际标准化组织）和 FedRAMP （联邦风险和授权管理）中绘制元素程序）和 GDPR （欧盟的常规数据保护法规）。

组织可以创建和添加与组织更相关的自定义评估。 您可以使用合规性分数的[现成模板](compliance-score.md#templates)之一来创建特定标准的评估，或[创建自己的模板](working-with-compliance-manager.md#create-a-template-1)。

阅读有关[合规性分数如何计算成绩](compliance-score-methodology.md)的详细信息。

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>合规性分数和安全评分的区别是什么？

合规性分数提供了组织的数据保护和合规性状况的广泛视图。 合规性分数还提供了内置工作流工具;它允许组织向用户分配工作、跟踪控件实现和测试状态以及上传证据和创建审核报告。

Microsoft 安全分数是一种帮助了解安全状态的安全分析工具。 [了解有关安全分数及其工作方式的详细信息](../security/mtp/microsoft-secure-score.md)。

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>合规性分数涵盖了哪些云服务？

合规性分数目前提供 Office 365 和 Intune 的评估。 将来的版本中应有扩展的覆盖范围，并将在[合规性分数发行说明](compliance-score-release-notes.md)中注明。

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>我是否可以对非 Microsoft 产品使用合规性分数？

虽然合规性分数仅提供针对 Microsoft 云服务的连续监视和建议操作，但您可以在合规性管理器中为内部部署第三方服务添加自定义评估。 通过这种方式，您可以使用 Microsoft 合规性分数作为 SaaS 合规性管理工具，帮助您管理所有数字资产中的所有控件。

您可以使用合规性分数的[现成模板](compliance-score.md#templates)之一来创建特定标准的评估，或[创建自己的模板](working-with-compliance-manager.md#create-a-template-1)。

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>如何删除不再需要的模板或评估？

您不能删除某个评估或模板，但可以从视图中隐藏它们。 查看有关[隐藏评估的说明](working-with-compliance-manager.md#hide-a-template-or-an-assessment)。