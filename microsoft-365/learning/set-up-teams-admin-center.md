---
title: 在 Microsoft Viva Learning (管理) 中设置 Teams 预览版
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
ms.custom: admindeeplinkTEAMS
ms.localizationpriority: ''
description: 了解如何在 Microsoft Viva Learning (管理) 配置 Teams 预览版。
ms.openlocfilehash: 4a54bc478c22d7a7ba3cb64c7efe69153882e308
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198321"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>在 Microsoft Viva Learning (管理) 中设置 Teams 预览版

> [!NOTE]
> 本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。 

管理员Teams执行某些步骤，才能在租户中为Learning (用户) Viva 预览预览版。 这些步骤因租户的启用情况而异：[*公共*](set-up-teams-admin-center.md#public-preview-tenants)预览版或专用预览版 [ (Beta) 。](set-up-teams-admin-center.md#private-preview-tenants)

## <a name="public-preview-tenants"></a>公共预览版租户

### <a name="administrator-steps-for-public-preview-tenants"></a>公共预览版租户的管理员步骤

由于 Viva Learning (Preview) 尚未普遍可用，因此需要执行某些步骤才能启用这些功能并设置特定用户或组的权限。 

1. 为 Viva 用户启用公共预览Learning (预览) 用户。

    a. 修改Teams策略以启用公共预览版功能。 请参阅[Microsoft Teams公共预览版](/microsoftteams/public-preview-doc-updates)。

    b. 为将执行 Viva 预览版测试的用户或组Learning (更新) 策略。 请参阅 [向用户和组分配策略](/microsoftteams/assign-policies-users-and-groups)。

2. 修改 Viva 应用程序权限策略Learning (预览) 用户。

    a. 除非它当前是全局策略的一部分，否则允许应用权限策略中所有的 Microsoft 应用。 请参阅[管理应用程序权限策略Microsoft Teams。](/microsoftteams/teams-app-permission-policies) 

    b. 为将执行 Viva 预览版测试的用户或组Learning (应用) 策略。 请参阅 [向用户和组分配策略](/microsoftteams/assign-policies-users-and-groups)。

3. 通知将测试 Viva Learning (Preview) [将生成客户端切换到公共预览版Teams。](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)

> [!IMPORTANT]
> 对于公共预览版租户，Learning (预览) 在最终产品发布之前不会显示在 Teams 管理中心的托管应用中。 但是，启用的公共预览版用户可以在 Teams 应用商店中查找 Viva Learning (Preview) ，一旦设置了正确的策略和权限，就可以使用它。

### <a name="user-steps-for-public-preview-tenants"></a>公共预览版租户的用户步骤

已启用公共预览测试（通过启用之前描述的策略）的用户需要切换到[](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants)其 Teams 客户端。 [](/microsoftteams/public-preview-doc-updates#enable-public-preview)

1. 用户必须在关于公共预览版中选择>  >  **图像**。

    ![显示用户配置文件Teams应用程序上的上导航。](../media/learning/learning-app-select-profile-teams.png)

2. 用户必须接受公共预览版条款和条件。

    ![切换到公共预览版。](../media/learning/learning-app-switch-to-public-preview.png)

3. 现在，用户可以在 Learning (应用商店) Viva Teams预览版，并开始使用它。

## <a name="private-preview-tenants"></a>专用预览版租户

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a>专用预览版或 Beta () 租户的管理员步骤

对于专用预览版租户，无需启用其他策略。 但是，Learning (预览) 必须可供您组织的用户使用。

1. 在管理中心左侧导航Teams，转到"管理Teams  >  <a href="https://go.microsoft.com/fwlink/?linkid=2172960" target="_blank">**应用"。**</a>

   ![管理中心左侧导航Teams显示"Teams""管理应用"部分。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. 在"**管理应用"** 页上的搜索框中，键入 *Viva Learning*，然后选择 **"Viva Learning (Preview) "。**

   ![显示搜索框Teams管理中心中的"管理应用"页面。](../media/learning/learning-app-teams-manage-apps-page.png)

3. 在 **"Viva Learning (预览) "** 页上的"状态"下，选择"允许"以打开 Viva Learning (Preview) 。

   ![Learning"管理Teams显示"状态"和"应用设置"部分。](../media/learning/learning-app-teams-learning-page.png)

<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2066851" target="_blank">Teams admin center</a>.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center > **Teams** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173206" target="_blank">**Update policies**</a>.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile.](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build.](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > <a href="https://go.microsoft.com/fwlink/?linkid=2172960" target="_blank">**Manage apps**</a>.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a>后续步骤

[为 Viva Learning (Preview) 配置学习内容源Microsoft 365 管理中心](content-sources-365-admin-center.md)
