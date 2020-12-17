---
title: '管理主题体验中心中的主题 (预览)  '
description: 如何在主题中心管理主题。
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 832067d157ed9ffcba1ed9ad514c375cbbdd752b
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698803"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="9d45c-103">管理主题中心中的主题 (预览) </span><span class="sxs-lookup"><span data-stu-id="9d45c-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="9d45c-104">本文中的内容适用于 Project Cortex 专用预览版。</span><span class="sxs-lookup"><span data-stu-id="9d45c-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="9d45c-105">[了解更多关于 Project Cortex的信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="9d45c-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="9d45c-106">在主题中心中，知识管理员可以查看"管理主题"页，以查看由知识管理员指定的 SharePoint 源位置中标识的主题。</span><span class="sxs-lookup"><span data-stu-id="9d45c-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![主题中心](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="9d45c-108">知识经理可帮助指导发现的主题在主题生命周期中，主题包括：</span><span class="sxs-lookup"><span data-stu-id="9d45c-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="9d45c-109">建议：主题已由 AI 标识，并且具有足够的支持资源、连接和属性来满足主题阈值。</span><span class="sxs-lookup"><span data-stu-id="9d45c-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="9d45c-110">已确认：验证 AI 建议的主题。</span><span class="sxs-lookup"><span data-stu-id="9d45c-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="9d45c-111">验证通过知识管理员确认完成。此外，如果至少有两个用户通过主题反馈对主题有效提供积极反馈，可以确认主题。</span><span class="sxs-lookup"><span data-stu-id="9d45c-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="9d45c-112">已删除：知识管理员拒绝主题，并且不再对查看者可见。</span><span class="sxs-lookup"><span data-stu-id="9d45c-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="9d45c-113">在建议或确认主题被删除后，主题 (状态) 。</span><span class="sxs-lookup"><span data-stu-id="9d45c-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="9d45c-114">已发布：已手动更新的已确认主题。</span><span class="sxs-lookup"><span data-stu-id="9d45c-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![主题生命周期图表](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="9d45c-116">要求</span><span class="sxs-lookup"><span data-stu-id="9d45c-116">Requirements</span></span>

<span data-ttu-id="9d45c-117">若要管理主题中心中的主题，需要：</span><span class="sxs-lookup"><span data-stu-id="9d45c-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="9d45c-118">拥有主题体验许可证。</span><span class="sxs-lookup"><span data-stu-id="9d45c-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="9d45c-119">对谁 [**可以管理主题具有权限**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)。</span><span class="sxs-lookup"><span data-stu-id="9d45c-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="9d45c-120">知识管理员可以在"知识网络"主题权限设置中授予用户此权限。</span><span class="sxs-lookup"><span data-stu-id="9d45c-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="9d45c-121">除非您具有"谁可以管理主题"权限，否则将无法在主题中心中查看"管理主题 **"** 页。</span><span class="sxs-lookup"><span data-stu-id="9d45c-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="9d45c-122">在主题中心，知识经理可以审阅在指定的 SharePoint 源位置中标识的主题，并可以确认或拒绝这些主题。</span><span class="sxs-lookup"><span data-stu-id="9d45c-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="9d45c-123">如果主题发现中未找到新主题页面，知识管理员还可以创建和发布新主题页面，或者如果需要更新现有主题页面，则编辑这些页面。</span><span class="sxs-lookup"><span data-stu-id="9d45c-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="9d45c-124">查看建议的主题</span><span class="sxs-lookup"><span data-stu-id="9d45c-124">Review suggested topics</span></span>

<span data-ttu-id="9d45c-125">在"主题中心管理主题"页上，在指定的 SharePoint 源位置中发现的主题将在"建议 **"** 选项卡中列出。知识经理可以审阅未确认的主题，并选择确认或拒绝这些主题。</span><span class="sxs-lookup"><span data-stu-id="9d45c-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="9d45c-126">查看建议的主题：</span><span class="sxs-lookup"><span data-stu-id="9d45c-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="9d45c-127">在 **"管理主题"** 页上，选择 **"建议"** 选项卡，选择主题以打开主题页。</span><span class="sxs-lookup"><span data-stu-id="9d45c-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="9d45c-128">在主题页面上，查看主题页面，如果需要对页面进行任何更改，请选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="9d45c-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="9d45c-129">查看主题后，返回到"管理主题"页。</span><span class="sxs-lookup"><span data-stu-id="9d45c-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="9d45c-130">对于所选主题，您可以：</span><span class="sxs-lookup"><span data-stu-id="9d45c-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="9d45c-131">选择选中选中标记以确认主题。</span><span class="sxs-lookup"><span data-stu-id="9d45c-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="9d45c-132">如果要拒绝主题，请选择 **x。**</span><span class="sxs-lookup"><span data-stu-id="9d45c-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="9d45c-133">确认的主题将从"建议 **"** 列表中删除，现在显示在"已确认 **"** 列表中。</span><span class="sxs-lookup"><span data-stu-id="9d45c-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="9d45c-134">拒绝的主题将从"建议 **"** 列表中删除，现在显示在"已删除 **"选项卡中** 。</span><span class="sxs-lookup"><span data-stu-id="9d45c-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="9d45c-135">已确认的主题</span><span class="sxs-lookup"><span data-stu-id="9d45c-135">Confirmed topics</span></span>

<span data-ttu-id="9d45c-136">在"管理主题"页上，在指定的 SharePoint 源位置中发现且已由知识经理确认的主题或由两个或多个人员通过卡片反馈机制确认的"群源"主题将列在"已确认"选项卡中。 如果需要，有权管理主题的用户可以审阅已确认的主题并选择拒绝它们。</span><span class="sxs-lookup"><span data-stu-id="9d45c-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="9d45c-137">查看已确认的主题：</span><span class="sxs-lookup"><span data-stu-id="9d45c-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="9d45c-138">在" **已确认** "选项卡上，选择主题以打开主题页面。</span><span class="sxs-lookup"><span data-stu-id="9d45c-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="9d45c-139">在主题页面上，查看主题页面，如果需要对页面进行任何更改，请选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="9d45c-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="9d45c-140">请注意，您仍可以选择拒绝已确认的主题。</span><span class="sxs-lookup"><span data-stu-id="9d45c-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="9d45c-141">为此，请转到"已确认"列表中的所选主题，如果要拒绝该主题，请选择 **x。**</span><span class="sxs-lookup"><span data-stu-id="9d45c-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="9d45c-142">已发布主题</span><span class="sxs-lookup"><span data-stu-id="9d45c-142">Published topics</span></span>
<span data-ttu-id="9d45c-143">已发布的主题已经过编辑，以便始终向遇到页面的人显示特定信息。</span><span class="sxs-lookup"><span data-stu-id="9d45c-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="9d45c-144">此处列出了手动创建的主题。</span><span class="sxs-lookup"><span data-stu-id="9d45c-144">Manually created topics are listed here.</span></span>




