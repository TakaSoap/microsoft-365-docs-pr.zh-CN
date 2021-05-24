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
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="d25ae-103">在管理中心 (Microsoft Viva) 预览Teams Microsoft Viva 学习版预览版</span><span class="sxs-lookup"><span data-stu-id="d25ae-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="d25ae-104">本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。</span><span class="sxs-lookup"><span data-stu-id="d25ae-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="d25ae-105">管理员Teams Viva Learning (Preview) ，并通过 Teams 管理中心应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="d25ae-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="d25ae-106">对于公共预览版，必须先设置更新策略。</span><span class="sxs-lookup"><span data-stu-id="d25ae-106">For Public Preview, you must first set the Update policy.</span></span> <span data-ttu-id="d25ae-107">有关详细信息，请参阅公共预览Teams网站[Microsoft Teams网站](/MicrosoftTeams/public-preview-doc-updates)。</span><span class="sxs-lookup"><span data-stu-id="d25ae-107">For more details, see the Teams site [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="d25ae-108">登录到管理Teams中心。</span><span class="sxs-lookup"><span data-stu-id="d25ae-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="d25ae-109">选择 **Teams**  >  **更新策略"。**</span><span class="sxs-lookup"><span data-stu-id="d25ae-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="d25ae-110">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d25ae-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="d25ae-111">命名更新策略，添加策略，然后打开显示 **预览功能**。</span><span class="sxs-lookup"><span data-stu-id="d25ae-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="d25ae-112">管理员必须通知用户策略更新，以便他们将内部版本移动到公共预览版Teams。</span><span class="sxs-lookup"><span data-stu-id="d25ae-112">The admin must notify users of the policy update so that they move their build into Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="d25ae-113">用户必须选择其个人资料图像 -->关于 --> 公共预览版。</span><span class="sxs-lookup"><span data-stu-id="d25ae-113">User must select their profile image --> About --> Public Preview.</span></span>
   
        ![显示用户配置文件Teams应用程序上的上导航](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="d25ae-115">用户必须接受公共预览版条款。</span><span class="sxs-lookup"><span data-stu-id="d25ae-115">User must accept terms of Public Preview.</span></span>

        ![切换到公共预览版](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="d25ae-117">对于具有限制性策略且需要启用 Viva 学习的组织，请按照下一节中的过程操作。</span><span class="sxs-lookup"><span data-stu-id="d25ae-117">For organizations that have restrictive policies and need to enable Viva Learning, follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="d25ae-118">管理 Viva Learning (Preview) </span><span class="sxs-lookup"><span data-stu-id="d25ae-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="d25ae-119">你必须是管理中心Teams管理员才能执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="d25ae-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="d25ae-120">若要使 Viva Learning (Preview) 组织中用户可以使用，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d25ae-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="d25ae-121">在管理中心左侧导航Teams，转到"管理Teams  >  **应用"。**</span><span class="sxs-lookup"><span data-stu-id="d25ae-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![管理中心左侧导航Teams显示Teams"管理应用"部分。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="d25ae-123">在" **管理应用"** 页上的搜索框中，键入 *Viva learning*，然后选择 **Viva Learning (Preview)**。</span><span class="sxs-lookup"><span data-stu-id="d25ae-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![显示搜索框Teams管理中心中的"管理应用"页面。](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="d25ae-125">在 **Viva 学习 (预览)** 页上：</span><span class="sxs-lookup"><span data-stu-id="d25ae-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="d25ae-126">在 **"状态**"下 **，** 选择"允许"以打开 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="d25ae-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="d25ae-127">在 **"设置"** 选项卡 **上的"应用** 设置"下，转到"Microsoft 365管理中心"[以配置学习内容源](content-sources-365-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d25ae-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![管理中心中的学习Teams"状态"和"应用设置"部分。](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="d25ae-129">管理应用设置后，转到"权限策略"和"设置策略"，向作为组织参与预览的一部分而应有权访问 Viva Learning (Preview) 的员工授予权限。 </span><span class="sxs-lookup"><span data-stu-id="d25ae-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="d25ae-130">如果你的组织在圈 4.0 中作为 Teams TAP100 计划的一部分，你可能需要启用圈 3.0 中的已批准用户才能访问 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="d25ae-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="d25ae-131">作为预览的一部分，Viva Learning (Preview) 在 Ring 3.0 中发布。</span><span class="sxs-lookup"><span data-stu-id="d25ae-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="d25ae-132">如果你的组织在圈 4.0 中，你将看不到管理应用 (预览) **Viva Learning) 预览** 版。</span><span class="sxs-lookup"><span data-stu-id="d25ae-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="d25ae-133">若要测试应用，需要创建自定义应用权限策略，将其设置为"允许所有应用"，并将其分配给圈 3.0 批准用户。</span><span class="sxs-lookup"><span data-stu-id="d25ae-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="d25ae-134">![TAP-AppsPermission-Plcy 页面显示"允许选择所有应用"。](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="d25ae-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="d25ae-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d25ae-135">Next step</span></span>

[<span data-ttu-id="d25ae-136">在管理中心中为 Viva Learning (Preview) 配置Microsoft 365源</span><span class="sxs-lookup"><span data-stu-id="d25ae-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
