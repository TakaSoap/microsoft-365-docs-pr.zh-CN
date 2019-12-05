---
title: Microsoft 合规性分数设置
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
description: 了解如何登录、设置权限以及了解 Microsoft 合规性分数的仪表板，这有助于简化和自动化风险评估。
ms.openlocfilehash: 03bcc5663e3b57728eb4ba791bbcba9593e5afc7
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831175"
---
# <a name="microsoft-compliance-score-preview-setup"></a>Microsoft 合规性分数（预览）设置

## <a name="before-you-begin"></a>开始之前

您的组织的 Microsoft 365 全局管理员可能是第一个访问合规性分数的用户。 我们建议全局管理员登录并设置用户权限，如第一次访问合规性得分时所述。

## <a name="sign-in"></a>登录

1. 请转到[microsoft 365 合规性中心](https://compliance.microsoft.com/)并使用 microsoft 365 全局管理员帐户**登录**。
2. 在左侧导航窗格中选择 "**合规性分数**"。 然后，您应看到[符合性分数仪表板与您的分数](#understand-the-compliance-score-dashboard)。

## <a name="set-user-permissions-and-assign-roles"></a>设置用户权限并分配角色

合规性分数使用基于角色的访问控制（RBAC）权限模型。 只有分配有角色的用户才可以访问合规性分数，并且每个用户允许的操作受角色类型的限制。

### <a name="where-to-set-permissions"></a>设置权限的位置

您的组织的全局管理员可以在 Microsoft 365 合规性中心或 Azure Active Directory （Azure AD）中设置用户权限。 一旦在这两个位置中设置了角色，用户就能够访问合规性分数（以及合规性管理器）。

请注意，现有合规性管理器角色**不会**转移到合规性分数。  这意味着，如果之前在合规性管理器中分配了一个角色，该角色将不会向您授予对合规性分数的访问权限。 全局管理员需要在 Microsoft 365 合规性中心或 Azure AD 中为你设置权限和角色，以便你可以访问合规性分数。

### <a name="role-types"></a>角色类型

下表显示了每个 Microsoft 365 合规性中心角色如何映射到现有合规性管理器角色，以及每个角色所允许的功能。


| 用户可以： | Microsoft 365 合规性中心角色 | 合规性管理器角色 | 
| :------------- | :-------------: | :------------: |
| **读取但不编辑数据**| Azure AD 全局读取器  | Azure AD 全局读取器 | 
| **读取但不编辑数据**| 安全读者 | 合规性管理器阅读器  | 
| **编辑数据**| 合规性管理员 | 合规性管理器参与者 | 
| **编辑测试结果**| 合规性管理员 | 合规性管理器评估员 | 
| **管理评估、模板和租户数据**| 合规性管理员<br>合规性数据管理员<br>安全管理员 | 合规性管理器管理员 | 
| **分配用户**| 全局管理员 | 门户管理员 | 

> [!NOTE]
> 当您从符合性分数转到合规性管理器以完成任务（例如，管理评估）时，浏览器将打开一个新选项卡，并显示一个对话框。 在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？ 登录您的帐户，选择 "**登录**以访问合规性管理器";您无需重新输入凭据。

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a>如何在 Microsoft 365 合规性中心中设置权限和角色

要在 Microsoft 365 合规性中心中设置权限，请执行以下操作：

1. 请转到[Microsoft 365 合规性中心](https://compliance.microsoft.com)并使用全局管理员帐户登录。
2. 在左侧导航窗格中选择 "**权限**"。 在此处，您可以查看角色和分配权限。

## <a name="understand-the-compliance-score-dashboard"></a>了解合规性分数仪表板

合规性分数仪表板旨在向您提供当前合规性状况的一览视图。

![合规性分数-仪表板](media/compliance-score-dashboard.png "合规性分数仪表板")

### <a name="overall-compliance-score"></a>总体合规性分数

你的合规性分数，在顶部突出重点，显示了根据完成提高操作（解决关键数据保护标准和法规）实现的积分的百分比。 

首次遇到合规性得分时，最初的分数基于内置的 Microsoft 365 数据保护基准，这是一组包含常见行业法规和标准的控件。 由于合规性分数会扫描您的现有 Microsoft 365 解决方案的系统，因此它会根据您的组织当前启用的隐私和安全设置对合规性状态进行初始评估。

在添加与您的组织相关的评估时，分数会变得更有意义。 了解有关[如何计算你的分数的](compliance-score-methodology.md)详细信息。

### <a name="key-improvement-actions"></a>关键改进操作

此部分列出了您现在可以执行的首要改进操作，以对您的总体合规性分数产生最大的积极影响。 它列出了未完成或因具有高风险的评估而失败的操作。

### <a name="solutions-that-affect-your-score"></a>影响你的成绩的解决方案

此部分显示哪些解决方案包含的操作具有最大的积极影响得分的机会，以及每个解决方案中有多少未解决的改进操作。

### <a name="compliance-score-breakdown"></a>合规性分数细分

本节提供了以两种不同的方式更详细地查看分数：

- **类别**：显示数据保护类别中整体得分的百分比，例如 "保护信息" 或 "管理设备"。
- **评估**：显示管理特定合规性和数据保护标准、法规或法律（如 GDPR 或 NIST 800-53）的评估进度的百分比。

### <a name="filtering-your-dashboard-view"></a>筛选你的仪表板视图

您可以筛选仪表板视图，以仅查看与特定法规和标准、解决方案、操作类型、组或数据保护类别相关的项目。 以这种方式筛选视图还将筛选仪表板上的分数，并根据筛选条件显示已实现的总积分数。

应用筛选器：

1. 选择仪表板右上侧的 "**筛选器**"。
2. 从飞出的 "**筛选**器" 窗格中选择筛选条件，然后选择 "**应用**"。

你将看到实时调整了你的分数，你将只会看到符合你的筛选器条件的改进操作、解决方案和分数细分信息。 如果你注销合规性分数，则在重新登录时将保留你的筛选视图。

若要删除筛选器：

- 在 "**应用的筛选器**" 标题高于您的合规性分数后，选择要删除的单个筛选器旁边的**X** ;和
- 选择仪表板右上侧的 "**筛选器**"，然后选择 "**清除筛选器**"。

## <a name="next-step"></a>后续步骤

访问[合规性分数](working-with-compliance-score.md)以了解如何采取行动以提高成绩的工作流。