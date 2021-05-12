---
title: 在 Microsoft Viva 主题的主题中心管理主题
description: 如何在主题中心管理主题。
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2c29cdb6823e695cb9c96a4f51ef7b1c41642ac9
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333622"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="087fb-103">在 Microsoft Viva 主题的主题中心管理主题</span><span class="sxs-lookup"><span data-stu-id="087fb-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="087fb-104">在 Viva 主题中心，知识管理员可以查看"管理主题"页，以查看知识管理员指定的源位置中标识的主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![主题中心](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="087fb-106">主题阶段</span><span class="sxs-lookup"><span data-stu-id="087fb-106">Topic stages</span></span>

<span data-ttu-id="087fb-107">知识管理器可帮助指导发现的主题完成各个主题生命周期阶段 **：Suggested、Confirmed、Published** 和 **Removed**。 </span><span class="sxs-lookup"><span data-stu-id="087fb-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![主题生命周期图表](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="087fb-109">**建议**: 主题已由 AI 标识，且具有足够的支持资源、连接和属性。</span><span class="sxs-lookup"><span data-stu-id="087fb-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="087fb-110"> (UI.) </span><span class="sxs-lookup"><span data-stu-id="087fb-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="087fb-111">**确认**: 已验证由 AI 建议的主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-111">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="087fb-112">主题验证必须由知识经理确认。</span><span class="sxs-lookup"><span data-stu-id="087fb-112">Topic validation must be confirmed by a knowledge manager.</span></span> <span data-ttu-id="087fb-113">对于要确认的主题，必须使用主题卡片上的反馈机制进行投票的用户获得两个肯定的投票。</span><span class="sxs-lookup"><span data-stu-id="087fb-113">For a topic to be confirmed, there must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="087fb-114">例如，如果一个用户对特定主题的投票是肯定的，而一个用户投了负，则你仍然需要另外两个积极投票来确认该主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-114">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="087fb-115">**已发布**：经确认的主题已计划：已进行手动编辑以提高其质量。</span><span class="sxs-lookup"><span data-stu-id="087fb-115">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>

- <span data-ttu-id="087fb-116">**已删除**：主题被知识管理员拒绝，并且不再对查看者可见。</span><span class="sxs-lookup"><span data-stu-id="087fb-116">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="087fb-117">可以在建议、确认或发布主题 (状态删除主题) 。</span><span class="sxs-lookup"><span data-stu-id="087fb-117">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="087fb-118">对于要删除的主题，必须使用主题卡片上的反馈机制从投票的用户那里获得两个负的投票。</span><span class="sxs-lookup"><span data-stu-id="087fb-118">For a topic to be removed, there must be a net of two negative votes received from users who voted using the feedback mechanisms on the topic card.</span></span> <span data-ttu-id="087fb-119">例如，如果一个用户对特定主题投了负票，而一个用户对特定主题投了肯定票，你仍然需要另外两个否定的投票来删除该主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-119">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span> <span data-ttu-id="087fb-120">删除已发布的主题后，需要通过主题中心的"页面库"手动删除包含特用详细信息的页面。</span><span class="sxs-lookup"><span data-stu-id="087fb-120">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

> [!Note] 
> <span data-ttu-id="087fb-121">在 **"管理主题** "页上，每个知识经理只能查看他们有权访问连接到该主题的基础文件和页面的主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-121">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="087fb-122">此权限修整将反映在"建议"选项卡、"已确认"选项卡、"**已发布**"和"已删除"选项卡 **上的主题** 列表中。 </span><span class="sxs-lookup"><span data-stu-id="087fb-122">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="087fb-123">但是，主题计数会显示组织中所有权限的总计数。</span><span class="sxs-lookup"><span data-stu-id="087fb-123">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="087fb-124">要求</span><span class="sxs-lookup"><span data-stu-id="087fb-124">Requirements</span></span>

<span data-ttu-id="087fb-125">若要在主题中心管理主题，需要：</span><span class="sxs-lookup"><span data-stu-id="087fb-125">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="087fb-126">拥有 Viva 主题许可证。</span><span class="sxs-lookup"><span data-stu-id="087fb-126">Have a Viva Topics license.</span></span>

- <span data-ttu-id="087fb-127">具有" [**谁可以管理主题"**](./topic-experiences-user-permissions.md) 权限。</span><span class="sxs-lookup"><span data-stu-id="087fb-127">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="087fb-128">知识管理员可以在 Viva 主题的主题权限设置中向用户授予此权限。</span><span class="sxs-lookup"><span data-stu-id="087fb-128">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="087fb-129">除非您具有"谁可以管理主题"权限，否则将无法在主题中心查看"管理主题 **"** 页。</span><span class="sxs-lookup"><span data-stu-id="087fb-129">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="087fb-130">在主题中心中，知识经理可以审阅在指定的源位置中标识的主题，并可以确认或删除这些主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-130">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="087fb-131">如果主题发现中未找到新主题页，知识管理员还可以创建和发布新主题页，或者编辑现有主题页（如果需要更新）。</span><span class="sxs-lookup"><span data-stu-id="087fb-131">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="087fb-132">查看建议的主题</span><span class="sxs-lookup"><span data-stu-id="087fb-132">Review suggested topics</span></span>

<span data-ttu-id="087fb-133">在" **管理主题** "页上，在指定的 SharePoint 源位置发现的主题将列在"建议 **"** 选项卡上。如果需要，知识经理可以审阅未确认的主题，并选择确认或删除它们。</span><span class="sxs-lookup"><span data-stu-id="087fb-133">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![建议的主题](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="087fb-135">查看建议的主题：</span><span class="sxs-lookup"><span data-stu-id="087fb-135">To review a suggested topic:</span></span>

1. <span data-ttu-id="087fb-136">在" **管理主题"** 页上，选择" **建议"选项卡** ，然后选择主题以打开主题页面。</span><span class="sxs-lookup"><span data-stu-id="087fb-136">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="087fb-137">在主题页面上，查看主题页面，如果需要对页面做出任何更改，请选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="087fb-137">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="087fb-138">发布任何编辑将本主题移至"已发布 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="087fb-138">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="087fb-139">查看主题后，返回到"管理 **主题"** 页。</span><span class="sxs-lookup"><span data-stu-id="087fb-139">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="087fb-140">对于所选主题，您可以：</span><span class="sxs-lookup"><span data-stu-id="087fb-140">For the selected topic, you can:</span></span>

   - <span data-ttu-id="087fb-141">选择选中标记以确认主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-141">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="087fb-142">如果要删除主题，请选择 **x。**</span><span class="sxs-lookup"><span data-stu-id="087fb-142">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="087fb-143">已确认的主题将从"建议 **"** 列表中删除，现在显示在"已确认 **"** 列表中。</span><span class="sxs-lookup"><span data-stu-id="087fb-143">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="087fb-144">已删除的主题将从"建议"列表中 **删除，** 现在显示在"已删除" **选项卡** 中。</span><span class="sxs-lookup"><span data-stu-id="087fb-144">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="087fb-145">质量分数</span><span class="sxs-lookup"><span data-stu-id="087fb-145">Quality score</span></span>

<span data-ttu-id="087fb-146">显示在"建议的主题" **页上的每个** 主题都分配有质量分数。</span><span class="sxs-lookup"><span data-stu-id="087fb-146">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="087fb-147">质量分数反映了普通用户将看到有关该主题的信息的信息量，同时请记住，每个用户可能会看到更多或更少的信息，因为他们可能拥有或可能不会查看主题中信息的权限。</span><span class="sxs-lookup"><span data-stu-id="087fb-147">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="087fb-148">质量分数可帮助深入了解包含最多信息的主题，并且可用于查找可能需要手动编辑的主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-148">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="087fb-149">例如，质量分数较低的主题可能是某些用户对 AI 在主题中包含的相关文件或网站没有 SharePoint 权限的结果。</span><span class="sxs-lookup"><span data-stu-id="087fb-149">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="087fb-150">然后，参与者可编辑该主题以包含该信息 (在适当的时候)，然后所有可查看该主题的用户都可以查看。</span><span class="sxs-lookup"><span data-stu-id="087fb-150">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="087fb-151">展现量</span><span class="sxs-lookup"><span data-stu-id="087fb-151">Impressions</span></span>

<span data-ttu-id="087fb-152">" **印象** "列显示向最终用户显示主题次数。</span><span class="sxs-lookup"><span data-stu-id="087fb-152">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="087fb-153">这包括通过搜索中的主题答案卡和主题突出显示的视图。</span><span class="sxs-lookup"><span data-stu-id="087fb-153">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="087fb-154">它并不反映这些主题的点击率，但已显示该主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-154">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="087fb-155">The **Impressions** column will show for topics in the **Suggested**， **Confirmed，** **Published，** and **Removed** tabs on the **Manage topics** page.</span><span class="sxs-lookup"><span data-stu-id="087fb-155">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="087fb-156">已确认主题</span><span class="sxs-lookup"><span data-stu-id="087fb-156">Confirmed topics</span></span>

<span data-ttu-id="087fb-157">在"管理主题"页上，在指定的 SharePoint 源位置中发现并已被知识经理确认或"众源"确认的主题 (通过卡片反馈机制平衡负用户投票与正用户投票) 将在"已确认"选项卡中列出。 如果需要，具有管理主题权限的用户可以审阅已确认的主题，并选择拒绝它们。</span><span class="sxs-lookup"><span data-stu-id="087fb-157">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="087fb-158">查看已确认的主题：</span><span class="sxs-lookup"><span data-stu-id="087fb-158">To review a confirmed topic:</span></span>

1. <span data-ttu-id="087fb-159">在 **“确认”** 选项卡上，选择主题以打开主题页面。</span><span class="sxs-lookup"><span data-stu-id="087fb-159">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="087fb-160">在主题页面上，查看主题页面，如果需要对页面做出任何更改，请选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="087fb-160">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="087fb-161">请注意，您仍可以选择拒绝已确认的主题。</span><span class="sxs-lookup"><span data-stu-id="087fb-161">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="087fb-162">为此，请转到"已确认"选项卡上的所选主题，如果要拒绝该主题，请选择 **"x"。**</span><span class="sxs-lookup"><span data-stu-id="087fb-162">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="087fb-163">已发布的主题</span><span class="sxs-lookup"><span data-stu-id="087fb-163">Published topics</span></span>

<span data-ttu-id="087fb-164">已发布的主题已经过编辑，以便始终向遇到页面的任何人显示特定信息。</span><span class="sxs-lookup"><span data-stu-id="087fb-164">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="087fb-165">手动创建的主题也会在此列出。</span><span class="sxs-lookup"><span data-stu-id="087fb-165">Manually created topics are listed here as well.</span></span>

   ![管理主题](../media/knowledge-management/manage-topics-new.png)
