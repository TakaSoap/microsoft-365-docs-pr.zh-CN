---
title: '主题体验安全修整 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 如何使用安全性查看主题的概述。
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698814"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="4d423-103">主题体验安全修整 (预览) </span><span class="sxs-lookup"><span data-stu-id="4d423-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="4d423-104">本文中的内容适用于 Project Cortex 专用预览版。</span><span class="sxs-lookup"><span data-stu-id="4d423-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4d423-105">[了解更多关于 Project Cortex的信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="4d423-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="4d423-106">主题体验用户将无法查看其现有 Office 365 权限阻止他们查看的主题信息。</span><span class="sxs-lookup"><span data-stu-id="4d423-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="4d423-107">用户在主题页面上看到的所有内容 (例如，SharePoint 网站、文档) 文件将是他们已允许查看的信息。</span><span class="sxs-lookup"><span data-stu-id="4d423-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="4d423-108">主题体验不会更改任何现有权限。</span><span class="sxs-lookup"><span data-stu-id="4d423-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="4d423-109">为什么两个用户对同一主题可能有不同的视图</span><span class="sxs-lookup"><span data-stu-id="4d423-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="4d423-110">通过 AI 或手动选择创建主题时，该主题可以包含主题说明、替代名称、与主题关联的人员，以及与该主题相关的网站、页面和文件。</span><span class="sxs-lookup"><span data-stu-id="4d423-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="4d423-111">在主题页面上查看此信息时，查看同一主题的两个用户可能看不到相同的信息。</span><span class="sxs-lookup"><span data-stu-id="4d423-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="4d423-112">例如，当用户 1 查看 Neptune 主题页面时，他们可能会看到该页面。</span><span class="sxs-lookup"><span data-stu-id="4d423-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![用户 1 的 Neptune 主题](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="4d423-114">但是，当用户 2 查看同一 Neptune 主题页时，她的视图与用户 1 不同。</span><span class="sxs-lookup"><span data-stu-id="4d423-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="4d423-115">用户 2 能够在主题页的"固定文件和页面"部分查看 *DG-2000 产品* 概述文件，该文件不会为用户 1 显示。 </span><span class="sxs-lookup"><span data-stu-id="4d423-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![用户 2 的 Neptune 主题](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="4d423-117">用户在同一主题上可能看到的内容的不同之处在于，用户可能没有查看相关站点或文件的 Office 365 权限。</span><span class="sxs-lookup"><span data-stu-id="4d423-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="4d423-118">主题体验会遵守对主题中的项目设置的权限，并且无法更改对它们的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4d423-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="4d423-119">在我们的示例中，用户 1 无法查看 Neptune 主题页中的 *DG-2000 产品* 概述文件，因为用户 1 没有查看该文件的 Office 365 权限。</span><span class="sxs-lookup"><span data-stu-id="4d423-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="4d423-120">如果用户无法查看主题中的足够信息，因此该主题将不可用。</span><span class="sxs-lookup"><span data-stu-id="4d423-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="4d423-121">在此实例中，用户不会看到突出显示的主题。</span><span class="sxs-lookup"><span data-stu-id="4d423-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="4d423-122">但是，对主题中的详细信息具有访问权限的其他用户将能够看到该主题。</span><span class="sxs-lookup"><span data-stu-id="4d423-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="4d423-123">知识管理员和主题参与者的主题权限</span><span class="sxs-lookup"><span data-stu-id="4d423-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="4d423-124">分配了管理主题的权限的用户（知识管理员）只能查看他们有权在主题内查看的信息。</span><span class="sxs-lookup"><span data-stu-id="4d423-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="4d423-125">同样，具有创建和编辑主题权限的用户（主题参与者）将只能查看他们有权在主题内查看的信息。</span><span class="sxs-lookup"><span data-stu-id="4d423-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="4d423-126">AI 与手动选择的主题信息</span><span class="sxs-lookup"><span data-stu-id="4d423-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="4d423-127">主题可以包含 AI 生成的信息以及主题参与者或知识管理员添加或编辑的信息。</span><span class="sxs-lookup"><span data-stu-id="4d423-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="4d423-128">AI 添加的主题中的信息仅对有权访问源内容的人可见。</span><span class="sxs-lookup"><span data-stu-id="4d423-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="4d423-129">主题参与者或知识管理员手动添加或编辑的信息对可以看到该主题的每个人可见。</span><span class="sxs-lookup"><span data-stu-id="4d423-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="4d423-130">下表介绍基于用户权限在给定主题中可以看到哪些用户（主题查看者、参与者和知识管理员）。</span><span class="sxs-lookup"><span data-stu-id="4d423-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="4d423-131">主题项</span><span class="sxs-lookup"><span data-stu-id="4d423-131">Topic item</span></span>|<span data-ttu-id="4d423-132">用户可以看到哪些内容</span><span class="sxs-lookup"><span data-stu-id="4d423-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="4d423-133">主题名称</span><span class="sxs-lookup"><span data-stu-id="4d423-133">Topic name</span></span>|<span data-ttu-id="4d423-134">用户可以在主题中心查看所有主题的主题名称。</span><span class="sxs-lookup"><span data-stu-id="4d423-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="4d423-135">如果某些主题与用户的相关性较低，则这些主题可能不可见。</span><span class="sxs-lookup"><span data-stu-id="4d423-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="4d423-136">主题说明</span><span class="sxs-lookup"><span data-stu-id="4d423-136">Topic description</span></span>|<span data-ttu-id="4d423-137">AI 生成的说明仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="4d423-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="4d423-138">手动输入或编辑的说明对所有用户都可见。</span><span class="sxs-lookup"><span data-stu-id="4d423-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="4d423-139">人员</span><span class="sxs-lookup"><span data-stu-id="4d423-139">People</span></span>|<span data-ttu-id="4d423-140">固定人员对所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="4d423-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="4d423-141">建议的用户仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="4d423-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4d423-142">文件</span><span class="sxs-lookup"><span data-stu-id="4d423-142">Files</span></span>|<span data-ttu-id="4d423-143">文件仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="4d423-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4d423-144">页面</span><span class="sxs-lookup"><span data-stu-id="4d423-144">Pages</span></span>|<span data-ttu-id="4d423-145">只有对源内容具有权限的用户才能看到页面。</span><span class="sxs-lookup"><span data-stu-id="4d423-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4d423-146">网站</span><span class="sxs-lookup"><span data-stu-id="4d423-146">Sites</span></span>|<span data-ttu-id="4d423-147">网站仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="4d423-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="4d423-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d423-148">See also</span></span>

