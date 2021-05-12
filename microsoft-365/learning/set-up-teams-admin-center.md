---
title: 在 Teams 管理中心 (Microsoft Viva) 预览版
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 了解如何在 Teams 管理中心 (Microsoft Viva) 预览版。
ms.openlocfilehash: 40e659796b22097f42515c0cbb704bdaa4ccc972
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333514"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>在 Teams 管理中心 (Microsoft Viva) 预览版

> [!NOTE]
> 本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。 

Teams 管理员安装 Viva Learning (Preview) 并通过 Teams 管理中心应用权限策略。

## <a name="manage-settings-for-viva-learning-preview"></a>管理 Viva Learning (Preview) 

你必须是 Teams 管理中心的管理员才能执行这些任务。

若要使 Viva Learning (Preview) 组织中用户可以使用，请按照以下步骤操作：

1. 在 Teams 管理中心的左侧导航中，转到 **"Teams 应用""**  >  **管理应用"。**

   ![Teams 管理中心中的左侧导航显示 Teams 应用和管理应用部分。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. 在" **管理应用"** 页上的搜索框中，键入 *Viva learning*，然后选择 **Viva Learning (Preview)**。

   ![Teams 管理中心中的"管理应用"页显示搜索框。](../media/learning/learning-app-teams-manage-apps-page.png)

3. 在 **Viva 学习 (预览)** 页上：

   1. 在 **"状态**"下 **，** 选择"允许"以打开 Viva Learning (Preview) 。

   2. 在" **设置"** 选项卡上的" **应用设置"** 下，转到 Microsoft 365 管理中心 [以配置学习内容源](content-sources-365-admin-center.md)。

   ![Teams 管理中心中的"学习"页面显示"状态"和"应用设置"部分。](../media/learning/learning-app-teams-learning-page.png)

4. 管理应用设置后，转到"权限策略"和"设置策略"，向作为组织参与预览的一部分而应有权访问 Viva Learning (Preview) 的员工授予权限。 

> [!NOTE]
>  如果你的组织在圈 4.0 中作为 Teams TAP100 计划的一部分，你可能需要启用圈 3.0 中的批准用户才能访问 Viva Learning (Preview) 。 <br><br>作为预览的一部分，Viva Learning (Preview) 在 Ring 3.0 中发布。 如果你的组织在圈 4.0 中，你将看不到管理应用 (预览) **Viva Learning) 预览** 版。 若要测试应用，需要创建自定义应用权限策略，将其设置为"允许所有应用"，并将其分配给圈 3.0 批准用户。 <br><br>   ![TAP-AppsPermission-Plcy 页面显示"允许选择所有应用"。](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>后续步骤

[在 Microsoft 365 管理中心中配置 Viva 学习 (预览版) 学习内容源](content-sources-365-admin-center.md)