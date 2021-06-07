---
title: 在管理中心 (Microsoft Viva) 预览Teams Microsoft Viva 学习版预览版
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
localization_priority: None
description: 了解如何在管理中心 (Microsoft Viva learning) Preview Teams预览版。
ms.openlocfilehash: 860f16bee7d93f2212072c5d738263402704272f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789227"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="660cb-103">在管理中心 (Microsoft Viva) 预览Teams Microsoft Viva 学习版预览版</span><span class="sxs-lookup"><span data-stu-id="660cb-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="660cb-104">本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。</span><span class="sxs-lookup"><span data-stu-id="660cb-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="660cb-105">管理员Teams执行某些步骤，才能为租户中的 (用户) Viva Learning) 预览版。</span><span class="sxs-lookup"><span data-stu-id="660cb-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="660cb-106">这些步骤因租户的启用情况而异：[*公共*](set-up-teams-admin-center.md#public-preview-tenants)预览版或专用预览版 [ (或 Beta) 。](set-up-teams-admin-center.md#private-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="660cb-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="660cb-107">公共预览版租户</span><span class="sxs-lookup"><span data-stu-id="660cb-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="660cb-108">公共预览版租户的管理员步骤</span><span class="sxs-lookup"><span data-stu-id="660cb-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="660cb-109">由于 Viva Learning (Preview) 尚未普遍可用，因此需要执行某些步骤才能启用这些功能并设置特定用户或组的权限。</span><span class="sxs-lookup"><span data-stu-id="660cb-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="660cb-110">为 Viva Learning (Preview) 公共预览功能。</span><span class="sxs-lookup"><span data-stu-id="660cb-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="660cb-111">a.</span><span class="sxs-lookup"><span data-stu-id="660cb-111">a.</span></span> <span data-ttu-id="660cb-112">修改Teams策略以启用公共预览版功能。</span><span class="sxs-lookup"><span data-stu-id="660cb-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="660cb-113">请参阅[Microsoft Teams预览版](/microsoftteams/public-preview-doc-updates)。</span><span class="sxs-lookup"><span data-stu-id="660cb-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="660cb-114">b.</span><span class="sxs-lookup"><span data-stu-id="660cb-114">b.</span></span> <span data-ttu-id="660cb-115">为将执行 Viva Learning (Preview) 策略。</span><span class="sxs-lookup"><span data-stu-id="660cb-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="660cb-116">请参阅 [向用户和组分配策略](/microsoftteams/assign-policies-users-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="660cb-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="660cb-117">修改 Viva Learning (Preview) 策略。</span><span class="sxs-lookup"><span data-stu-id="660cb-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="660cb-118">a.</span><span class="sxs-lookup"><span data-stu-id="660cb-118">a.</span></span> <span data-ttu-id="660cb-119">除非它当前是全局策略的一部分，否则允许应用权限策略中所有的 Microsoft 应用。</span><span class="sxs-lookup"><span data-stu-id="660cb-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="660cb-120">请参阅[管理应用程序权限策略Microsoft Teams。](/microsoftteams/teams-app-permission-policies)</span><span class="sxs-lookup"><span data-stu-id="660cb-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="660cb-121">b.</span><span class="sxs-lookup"><span data-stu-id="660cb-121">b.</span></span> <span data-ttu-id="660cb-122">为将执行 Viva Learning (Preview 测试的用户或组) 策略。</span><span class="sxs-lookup"><span data-stu-id="660cb-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="660cb-123">请参阅 [向用户和组分配策略](/microsoftteams/assign-policies-users-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="660cb-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3.  <span data-ttu-id="660cb-124">通知将测试 Viva Learning (Preview [) ，以将](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)生成客户端切换到 Teams 公共预览版。</span><span class="sxs-lookup"><span data-stu-id="660cb-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="660cb-125">对于公共预览版租户，直到最终产品 (，Viva Learning) Preview Teams不会显示在Teams 管理中心的托管应用中。</span><span class="sxs-lookup"><span data-stu-id="660cb-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="660cb-126">但是，启用的公共预览版用户可以在 Teams 应用商店中查找 Viva Learning (Preview) ，一旦设置了正确的策略和权限，就可以使用它。</span><span class="sxs-lookup"><span data-stu-id="660cb-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="660cb-127">公共预览版租户的用户步骤</span><span class="sxs-lookup"><span data-stu-id="660cb-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="660cb-128">已启用公共预览版测试（通过启用之前描述的策略）的用户需要[](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants)切换到其 Teams 客户端[](/microsoftteams/public-preview-doc-updates#enable-public-preview)。</span><span class="sxs-lookup"><span data-stu-id="660cb-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="660cb-129">用户必须选择其个人资料图像>**关于**  >  **公共预览版**。</span><span class="sxs-lookup"><span data-stu-id="660cb-129">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
    ![显示用户配置文件Teams应用程序上的上导航](../media/learning/learning-app-select-profile-teams.png)
    
2. <span data-ttu-id="660cb-131">用户必须接受公共预览版条款和条件。</span><span class="sxs-lookup"><span data-stu-id="660cb-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![切换到公共预览版](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="660cb-133">用户现在可以在 Teams 应用商店 (Viva Learning) Preview Teams并开始使用它。</span><span class="sxs-lookup"><span data-stu-id="660cb-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="660cb-134">专用预览版租户</span><span class="sxs-lookup"><span data-stu-id="660cb-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="660cb-135">专用预览版或 Beta (租户的) 步骤</span><span class="sxs-lookup"><span data-stu-id="660cb-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="660cb-136">对于专用预览版租户，无需启用其他策略。</span><span class="sxs-lookup"><span data-stu-id="660cb-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="660cb-137">但是，Viva learning (Preview) 必须可供您组织的用户使用。</span><span class="sxs-lookup"><span data-stu-id="660cb-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="660cb-138">在管理中心左侧导航Teams，转到"管理Teams  >  **应用"。**</span><span class="sxs-lookup"><span data-stu-id="660cb-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![管理中心左侧导航Teams显示Teams"管理应用"部分。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="660cb-140">在"**管理应用"** 页上的搜索框中，键入 *Viva Learning，* 然后选择 **"Viva Learning (Preview) "。**</span><span class="sxs-lookup"><span data-stu-id="660cb-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![显示搜索框Teams管理中心中的"管理应用"页面。](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="660cb-142">在 **"Viva learning (Preview) "** 页上的"状态"下，选择"允许"以打开 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="660cb-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   ![管理中心中的学习Teams"状态"和"应用设置"部分。](../media/learning/learning-app-teams-learning-page.png)


<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

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

## <a name="next-step"></a><span data-ttu-id="660cb-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="660cb-144">Next step</span></span>

[<span data-ttu-id="660cb-145">在管理中心中为 Viva Learning (Preview) 配置Microsoft 365源</span><span class="sxs-lookup"><span data-stu-id="660cb-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
