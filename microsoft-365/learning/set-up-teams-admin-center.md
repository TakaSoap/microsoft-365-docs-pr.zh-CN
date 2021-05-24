---
title: 在管理中心 (Microsoft Viva) 预览Teams Microsoft Viva 学习版预览版
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
description: 了解如何在管理中心 (Microsoft Viva learning) Preview Teams预览版。
ms.openlocfilehash: e5af676752064738e26f9b934a60973cb9b0200d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625291"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>在管理中心 (Microsoft Viva) 预览Teams Microsoft Viva 学习版预览版

> [!NOTE]
> 本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。 

管理员Teams Viva Learning (Preview) ，并通过 Teams 管理中心应用权限策略。

1. 对于公共预览版，必须先设置更新策略。 有关详细信息，请参阅公共预览Teams网站[Microsoft Teams网站](/MicrosoftTeams/public-preview-doc-updates)。

    1. 登录到管理Teams中心。

    2. 选择 **Teams**  >  **更新策略"。**

    3. 选择“**添加**”。 

    4. 命名更新策略，添加策略，然后打开显示 **预览功能**。

2. 管理员必须通知用户策略更新，以便他们将内部版本移动到公共预览版Teams。 

    1. 用户必须选择其个人资料图像 -->关于 --> 公共预览版。
   
        ![显示用户配置文件Teams应用程序上的上导航](../media/learning/learning-app-select-profile-teams.png)
    
    2. 用户必须接受公共预览版条款。

        ![切换到公共预览版](../media/learning/learning-app-switch-to-public-preview.png)
 
3. 对于具有限制性策略且需要启用 Viva 学习的组织，请按照下一节中的过程操作。

## <a name="manage-settings-for-viva-learning-preview"></a>管理 Viva Learning (Preview) 

你必须是管理中心Teams管理员才能执行这些任务。

若要使 Viva Learning (Preview) 组织中用户可以使用，请按照以下步骤操作：

1. 在管理中心左侧导航Teams，转到"管理Teams  >  **应用"。**

   ![管理中心左侧导航Teams显示Teams"管理应用"部分。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. 在" **管理应用"** 页上的搜索框中，键入 *Viva learning*，然后选择 **Viva Learning (Preview)**。

   ![显示搜索框Teams管理中心中的"管理应用"页面。](../media/learning/learning-app-teams-manage-apps-page.png)

3. 在 **Viva 学习 (预览)** 页上：

   1. 在 **"状态**"下 **，** 选择"允许"以打开 Viva Learning (Preview) 。

   2. 在 **"设置"** 选项卡 **上的"应用** 设置"下，转到"Microsoft 365管理中心"[以配置学习内容源](content-sources-365-admin-center.md)。

   ![管理中心中的学习Teams"状态"和"应用设置"部分。](../media/learning/learning-app-teams-learning-page.png)

4. 管理应用设置后，转到"权限策略"和"设置策略"，向作为组织参与预览的一部分而应有权访问 Viva Learning (Preview) 的员工授予权限。 

> [!NOTE]
>  如果你的组织在圈 4.0 中作为 Teams TAP100 计划的一部分，你可能需要启用圈 3.0 中的已批准用户才能访问 Viva Learning (Preview) 。 <br><br>作为预览的一部分，Viva Learning (Preview) 在 Ring 3.0 中发布。 如果你的组织在圈 4.0 中，你将看不到管理应用 (预览) **Viva Learning) 预览** 版。 若要测试应用，需要创建自定义应用权限策略，将其设置为"允许所有应用"，并将其分配给圈 3.0 批准用户。 <br><br>   ![TAP-AppsPermission-Plcy 页面显示"允许选择所有应用"。](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>后续步骤

[在管理中心中为 Viva Learning (Preview) 配置Microsoft 365源](content-sources-365-admin-center.md)
