---
title: Microsoft 工作效率分数-隐私
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
description: 使用效率分数保护隐私的方式。
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287222"
---
# <a name="privacy-controls-for-productivity-score"></a>用于提高工作效率的隐私控制分数

生产效率分数可帮助组织转换工作方式，并了解有关用户如何使用 Microsoft 365 以及支持它们的技术体验方面的见解。 得分反映了贵组织&#39;的针对员工和技术体验指标的绩效，并将您的成绩与像您这样的组织进行比较。 有关更多详细信息，请查看 " [生产力分数概述](productivity-score.md) " 主题。

你的隐私对我们非常重要，你可以在 [此处](https://privacy.microsoft.com/privacystatement)查看 Microsoft 的隐私声明。 在工作效率分数中，我们提供了有关组织中的人员如何工作的重要信息。 因此，我们还将向你提供控制，以确保以一种有意义的方式操作信息，同时不会危及我们所处的信任。

我们提供了以下控件，以允许对数据进行更安全的处理：

- 灵活的管理员角色，可控制谁可以查看工作效率分数中的信息。
- Anonymization 的用户级指标。
- 能够选择退出员工体验。

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>灵活的管理员角色，可控制谁可以查看工作效率分数中的信息

若要查看具有管理员角色（包括租户级见解和每用户级别的详细信息）的整个生产效率评分体验，您的角色应为以下项之一：

- 全局管理员
- Exchange 管理员
- SharePoint 管理员
- Skype for Business 管理员
- Teams 管理员
- 全局读取者
- 报告读取者

若要邀请负责更改管理和采用但不是 IT 管理员的用户体验，同时让他们能够访问完整体验（包括租户级见解和每用户级别的详细信息），可以为他们提供报告读者角色。

在员工体验中，我们为每个用户级别的活动详细信息提供每个类别详细信息页面的网格格式。 由于此级别的详细信息不适合于工作效率分数的所有潜在访问者，我们已在 Azure AD 中创建了一个自定义角色–使用率摘要报告读者角色–使您能够访问您的组织内的更广泛的访问群体，使其仅包含聚合指标，并且在体验中不会对每一级别的详细信息进行访问。

:::image type="content" source="../../media/communicationspage.jpg" alt-text="生产率报告中的 "通信" 页面。":::

## <a name="anonymization-of-user-level-metrics"></a>Anonymization 的用户级指标

若要使为所有报告匿名收集的数据，您必须是全局管理员。 这将隐藏所有报告中的可识别信息，如用户、组和网站名称–包括工作效率分数和 Microsoft 365 使用率。

1. 在管理中心中，转到 "**设置**   >   **组织设置**"，在 "**服务**" 选项卡下，选择 "**报告**"。
2. 选择 "  **报告** "，然后选择  **显示用户、组和网站名称的匿名标识符，以提高工作效率的分数和使用情况报告**。 此设置既可应用于使用情况报告，也可应用于模板应用。
3. 选择 "  **保存更改**"。

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="将用户信息设为匿名的报告。":::

## <a name="capability-to-opt-out-of-employee-experience"></a>能够选择退出员工体验

我们还将提供在正式供货时自愿退出 "员工体验成绩" 领域的功能。 启用此设置将阻止组织中的任何人能够查看这些指标，并从涉及通信、会议、团队合作、内容协作和移动性的任何计算中删除您的组织。

1. 在管理中心中，转到 "**设置**   >   **组织设置**"，在 "**服务**" 选项卡下，选择 "**报告**"。
2. 选择 "  **报告** "，然后取消选中 "  **共享你的组织&#39;的数据，其中包含生产率评分的员工体验见解**" 框。 若要了解如何在 Intune 配置管理器中修改终结点分析的数据共享设置，请单击 " **了解更多**"。
3. 选择 "  **保存更改**"。

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="您可以选择退出员工体验的 "组织设置" 页。":::