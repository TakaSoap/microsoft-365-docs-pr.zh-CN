---
title: 在管理中心 (Microsoft Viva) 预览Teams Microsoft Viva 学习版预览版
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
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
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636130"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="b9602-103">在管理中心 (Microsoft Viva) 预览Teams Microsoft Viva 学习版预览版</span><span class="sxs-lookup"><span data-stu-id="b9602-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="b9602-104">本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。</span><span class="sxs-lookup"><span data-stu-id="b9602-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="b9602-105">管理员Teams Viva Learning (Preview) ，并通过 Teams 管理中心应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="b9602-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="b9602-106">对于 Viva Learning (Preview) ，您必须先在 Teams 中设置更新策略。</span><span class="sxs-lookup"><span data-stu-id="b9602-106">For Viva Learning (Preview), you must first set the Update policy in Teams.</span></span> <span data-ttu-id="b9602-107">有关详细信息，请参阅公共[Microsoft Teams预览版](/MicrosoftTeams/public-preview-doc-updates)。</span><span class="sxs-lookup"><span data-stu-id="b9602-107">For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="b9602-108">登录到管理Teams中心。</span><span class="sxs-lookup"><span data-stu-id="b9602-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="b9602-109">选择 **Teams**  >  **更新策略"。**</span><span class="sxs-lookup"><span data-stu-id="b9602-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="b9602-110">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="b9602-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="b9602-111">命名更新策略，添加策略，然后打开显示 **预览功能**。</span><span class="sxs-lookup"><span data-stu-id="b9602-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="b9602-112">管理员必须通知用户策略更新，以便他们将内部版本移动到公共预览版Teams。</span><span class="sxs-lookup"><span data-stu-id="b9602-112">The admin must notify users of the policy update so that they move their build into the Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="b9602-113">用户必须选择其个人资料图像>**关于**  >  **公共预览版**。</span><span class="sxs-lookup"><span data-stu-id="b9602-113">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
        ![显示用户配置文件Teams应用程序上的上导航](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="b9602-115">用户必须接受 **公共预览** 条款和条件。</span><span class="sxs-lookup"><span data-stu-id="b9602-115">Users must accept the **Public preview** terms and conditions.</span></span>

        ![切换到公共预览版](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="b9602-117">对于具有限制性策略且需要启用 Viva Learning (Preview) ，请按照下一节中的过程操作。</span><span class="sxs-lookup"><span data-stu-id="b9602-117">For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="b9602-118">管理 Viva Learning (Preview) </span><span class="sxs-lookup"><span data-stu-id="b9602-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="b9602-119">你必须是管理中心Teams管理员才能执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="b9602-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="b9602-120">若要使 Viva Learning (Preview) 组织中用户可以使用，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b9602-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="b9602-121">在管理中心左侧导航Teams，转到"管理Teams  >  **应用"。**</span><span class="sxs-lookup"><span data-stu-id="b9602-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![管理中心左侧导航Teams显示Teams"管理应用"部分。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="b9602-123">在" **管理应用"** 页上的搜索框中，键入 *Viva learning*，然后选择 **Viva Learning (Preview)**。</span><span class="sxs-lookup"><span data-stu-id="b9602-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![显示搜索框Teams管理中心中的"管理应用"页面。](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="b9602-125">在 **Viva 学习 (预览)** 页上：</span><span class="sxs-lookup"><span data-stu-id="b9602-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="b9602-126">在 **"状态**"下 **，** 选择"允许"以打开 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="b9602-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="b9602-127">在 **"设置"** 选项卡 **上的"应用** 设置"下，转到"Microsoft 365管理中心"[以配置学习内容源](content-sources-365-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b9602-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![管理中心中的学习Teams"状态"和"应用设置"部分。](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="b9602-129">管理应用设置后，转到"权限策略"和"设置策略"，向作为组织参与预览的一部分而应有权访问 Viva Learning (Preview) 的员工授予权限。 </span><span class="sxs-lookup"><span data-stu-id="b9602-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="b9602-130">如果你的组织在圈 4.0 中作为 Teams TAP100 计划的一部分，你可能需要启用圈 3.0 中的已批准用户才能访问 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="b9602-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="b9602-131">作为预览的一部分，Viva Learning (Preview) 在 Ring 3.0 中发布。</span><span class="sxs-lookup"><span data-stu-id="b9602-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="b9602-132">如果你的组织在圈 4.0 中，你将看不到管理应用 (预览) **Viva Learning) 预览** 版。</span><span class="sxs-lookup"><span data-stu-id="b9602-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="b9602-133">若要测试应用，需要创建自定义应用权限策略，将其设置为"允许所有应用"，并将其分配给圈 3.0 批准用户。</span><span class="sxs-lookup"><span data-stu-id="b9602-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="b9602-134">![TAP-AppsPermission-Plcy 页面显示"允许选择所有应用"。](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="b9602-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="b9602-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b9602-135">Next step</span></span>

[<span data-ttu-id="b9602-136">在管理中心中为 Viva Learning (Preview) 配置Microsoft 365源</span><span class="sxs-lookup"><span data-stu-id="b9602-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
