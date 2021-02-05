---
title: 在 Microsoft Viva 主题中管理主题中心中的主题
description: 如何在主题中心管理主题。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 45e8f26823998278f9a332d2ea1e362b77f2032b
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107180"
---
# <a name="manage-topics-in-the-topic-center"></a><span data-ttu-id="1d667-103">管理主题中心中的主题</span><span class="sxs-lookup"><span data-stu-id="1d667-103">Manage topics in the Topic center</span></span> 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="1d667-104">在 Viva 主题主题中心中，知识管理员可以查看"管理主题"页，以查看由知识管理员指定的 SharePoint 源位置中标识的主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-104">In the Viva Topics Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![主题中心](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="1d667-106">知识经理可帮助指导发现的主题在主题生命周期内，主题包括：</span><span class="sxs-lookup"><span data-stu-id="1d667-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="1d667-107">建议：主题已由 AI 标识，并且具有足够的支持资源、连接和属性。</span><span class="sxs-lookup"><span data-stu-id="1d667-107">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="1d667-108">已确认：已验证 AI 建议的主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-108">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="1d667-109">验证通过知识管理器的确认完成。</span><span class="sxs-lookup"><span data-stu-id="1d667-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="1d667-110">此外，如果至少有两个用户通过主题卡片上的反馈问题提供正面反馈，可以确认主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-110">Additionally, a topic can be confirmed if at least two users give positive feedback through the feedback question on the topic card.</span></span>
- <span data-ttu-id="1d667-111">已发布：已选择一个经确认的主题：已进行手动编辑以改进其质量。</span><span class="sxs-lookup"><span data-stu-id="1d667-111">Published: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="1d667-112">已删除：知识管理器拒绝主题，并且不再对查看者可见。</span><span class="sxs-lookup"><span data-stu-id="1d667-112">Removed: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="1d667-113">在建议、确认或发布主题时，主题 (状态) 。</span><span class="sxs-lookup"><span data-stu-id="1d667-113">The topic can be in any state when it is removed (suggested, confirmed or published).</span></span> <span data-ttu-id="1d667-114">删除已发布的主题后，需要通过主题中心的页面库手动删除包含特用详细信息的页面。</span><span class="sxs-lookup"><span data-stu-id="1d667-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![主题生命周期图表](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="1d667-116">在"管理主题"页中，每个知识管理员只能查看他们有权访问主题的文件和页面的主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-116">In the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the files and pages of the topic.</span></span> <span data-ttu-id="1d667-117">这将反映在"建议、已确认、已删除和已发布"选项卡下列出的主题中。</span><span class="sxs-lookup"><span data-stu-id="1d667-117">This will be reflected in the topics that are listed under the Suggested, Confirmed, Removed, and Published tabs.</span></span> <span data-ttu-id="1d667-118">但是，主题计数会显示组织中的总计数。</span><span class="sxs-lookup"><span data-stu-id="1d667-118">The topic counts, however, show the total counts in the organization.</span></span>

## <a name="requirements"></a><span data-ttu-id="1d667-119">要求</span><span class="sxs-lookup"><span data-stu-id="1d667-119">Requirements</span></span>

<span data-ttu-id="1d667-120">若要管理主题中心中的主题，需要：</span><span class="sxs-lookup"><span data-stu-id="1d667-120">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="1d667-121">拥有 Viva 主题许可证。</span><span class="sxs-lookup"><span data-stu-id="1d667-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="1d667-122">具有 [**"谁可以管理主题"**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) 权限。</span><span class="sxs-lookup"><span data-stu-id="1d667-122">Have the [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) permission.</span></span> <span data-ttu-id="1d667-123">知识管理员可以在 Viva 主题权限设置中授予用户此权限。</span><span class="sxs-lookup"><span data-stu-id="1d667-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="1d667-124">除非您具有"谁可以管理主题"权限，否则将无法在主题中心中查看"管理主题 **"** 页。</span><span class="sxs-lookup"><span data-stu-id="1d667-124">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="1d667-125">在主题中心，知识经理可以审阅在指定的 SharePoint 源位置中标识的主题，并可以确认或拒绝这些主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-125">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="1d667-126">如果主题发现中未找到新主题页面，知识管理员还可以创建和发布新主题页面，或者编辑现有主题页（如果需要进行更新）。</span><span class="sxs-lookup"><span data-stu-id="1d667-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="1d667-127">查看建议的主题</span><span class="sxs-lookup"><span data-stu-id="1d667-127">Review suggested topics</span></span>

<span data-ttu-id="1d667-128">在"主题中心管理主题"页上，在指定的 SharePoint 源位置中发现的主题将在"建议 **"** 选项卡中列出。如果需要，知识经理可以审阅未确认的主题，并选择确认或拒绝这些主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-128">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![建议的主题](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="1d667-130">查看建议的主题：</span><span class="sxs-lookup"><span data-stu-id="1d667-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="1d667-131">在 **"管理主题"** 页上，选择 **"建议"** 选项卡，选择主题以打开主题页面。</span><span class="sxs-lookup"><span data-stu-id="1d667-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="1d667-132">在主题页面上，查看主题页面，如果需要对页面进行任何更改，请选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="1d667-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="1d667-133">发布任何编辑将本主题移至"已发布 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1d667-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="1d667-134">查看主题后，返回到"管理主题"页。</span><span class="sxs-lookup"><span data-stu-id="1d667-134">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="1d667-135">对于所选主题，您可以：</span><span class="sxs-lookup"><span data-stu-id="1d667-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="1d667-136">选择选中选中标记以确认主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="1d667-137">如果要拒绝主题，请选择 **x。**</span><span class="sxs-lookup"><span data-stu-id="1d667-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="1d667-138">确认的主题将从"建议 **"** 列表中删除，现在显示在"已确认 **"** 列表中。</span><span class="sxs-lookup"><span data-stu-id="1d667-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="1d667-139">拒绝的主题将从"建议 **"** 列表中删除，现在显示在"已删除 **"选项卡中** 。</span><span class="sxs-lookup"><span data-stu-id="1d667-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="1d667-140">质量分数</span><span class="sxs-lookup"><span data-stu-id="1d667-140">Quality score</span></span>

<span data-ttu-id="1d667-141">显示在"建议的主题"页中的每个 <b>主题都有分配给</b> 它的质量分数。</span><span class="sxs-lookup"><span data-stu-id="1d667-141">Each topic that appears in your Suggested Topics page has a <b>Quality</b> score assigned to it.</span></span> <span data-ttu-id="1d667-142">质量分数反映了普通用户将看到有关主题信息的信息量，请记住，每个用户可能会看到更多或更少的信息，因为他们可能拥有或可能没有对主题中信息的权限。</span><span class="sxs-lookup"><span data-stu-id="1d667-142">The Quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user may see more or less information because of the permissions they may or may not have on the information in a topic.</span></span> 

<span data-ttu-id="1d667-143">质量分数可帮助深入了解包含最多信息的主题，并且对于查找可能需要手动编辑的主题非常有用。</span><span class="sxs-lookup"><span data-stu-id="1d667-143">The Quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span>  <span data-ttu-id="1d667-144">例如，质量分数较低的主题可能是某些用户对 AI 在主题中包含的相关文件或网站没有 SharePoint 权限的结果。</span><span class="sxs-lookup"><span data-stu-id="1d667-144">For example, a topic with a lower quality score may be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="1d667-145">参与者随后可以编辑主题，以在适当 (包含) ，然后所有可查看该主题的用户都可以查看这些信息。</span><span class="sxs-lookup"><span data-stu-id="1d667-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

<span data-ttu-id="1d667-146">质量分数的范围为 1 到 100。</span><span class="sxs-lookup"><span data-stu-id="1d667-146">The Quality score could range from 1 to 100.</span></span> <span data-ttu-id="1d667-147">新发现的主题的质量分数将为 0，直到两个或多个用户已查看它。</span><span class="sxs-lookup"><span data-stu-id="1d667-147">A newly discovered topic will have a quality score of 0 until two or more users have viewed it.</span></span> <span data-ttu-id="1d667-148">每个用户的质量分数由许多因素决定，例如为特定用户显示的内容量，由于每个主题页都针对 AI 生成的内容都进行安全修整，因此将控制用户的权限。</span><span class="sxs-lookup"><span data-stu-id="1d667-148">Each users quality score is determined by a number of factors, such as the amount of content displayed for the specific user, which is controlled the user's permissions as each topic page has security trimming in place for AI-generated content.</span></span> <span data-ttu-id="1d667-149">"建议的主题"选项卡上显示的质量分数是每个用户个人分数的平均值。</span><span class="sxs-lookup"><span data-stu-id="1d667-149">The Quality score shown on the Suggested topics tab is an average of each users individual score.</span></span>

### <a name="impressions"></a><span data-ttu-id="1d667-150">展示次数</span><span class="sxs-lookup"><span data-stu-id="1d667-150">Impressions</span></span>

<span data-ttu-id="1d667-151">" <b>展示</b> 次数"列显示向最终用户显示主题次数。</span><span class="sxs-lookup"><span data-stu-id="1d667-151">The <b>Impressions</b> column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="1d667-152">这包括通过搜索中的主题卡片、主题突出显示和主题中心视图查看视图。</span><span class="sxs-lookup"><span data-stu-id="1d667-152">This includes views through topic cards in search, through topic highlights, and through Topic center views.</span></span> <span data-ttu-id="1d667-153">它不反映这些主题的点击率，但已显示该主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-153">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="1d667-154">"展示次数"列将在"管理主题"页的"建议、确认、已发布和已删除"选项卡中显示主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-154">The Impressions column will show for topics in the Suggested, Confirmed, Published, and Removed tabs in the Manage Topics page.</span></span>


## <a name="confirmed-topics"></a><span data-ttu-id="1d667-155">已确认的主题</span><span class="sxs-lookup"><span data-stu-id="1d667-155">Confirmed topics</span></span>

<span data-ttu-id="1d667-156">在"管理主题"页上，在指定的 SharePoint 源位置中发现并且已由知识经理确认的主题或由两个或多个人员通过卡片反馈机制确认的"群源"主题将列在"已确认" **选项卡中。** 如果需要，有权管理主题的用户可以审阅已确认的主题并选择拒绝它们。</span><span class="sxs-lookup"><span data-stu-id="1d667-156">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="1d667-157">查看已确认的主题：</span><span class="sxs-lookup"><span data-stu-id="1d667-157">To review a confirmed topic:</span></span>

1. <span data-ttu-id="1d667-158">在" **已确认** "选项卡上，选择主题以打开主题页面。</span><span class="sxs-lookup"><span data-stu-id="1d667-158">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="1d667-159">在主题页面上，查看主题页面，如果需要对页面进行任何更改，请选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="1d667-159">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="1d667-160">请注意，您仍可以选择拒绝已确认的主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-160">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="1d667-161">为此，请转到"已确认"列表中的所选主题，如果要拒绝该主题，请选择 **x。**</span><span class="sxs-lookup"><span data-stu-id="1d667-161">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="1d667-162">已发布主题</span><span class="sxs-lookup"><span data-stu-id="1d667-162">Published topics</span></span>
<span data-ttu-id="1d667-163">已编辑已发布的主题，以便始终向遇到页面的人显示特定信息。</span><span class="sxs-lookup"><span data-stu-id="1d667-163">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="1d667-164">此处也列出了手动创建的主题。</span><span class="sxs-lookup"><span data-stu-id="1d667-164">Manually created topics are listed here as well.</span></span>

   ![管理主题](../media/knowledge-management/manage-topics-new.png) </br> 




