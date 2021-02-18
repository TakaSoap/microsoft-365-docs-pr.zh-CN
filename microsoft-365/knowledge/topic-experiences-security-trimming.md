---
title: Microsoft Viva 主题安全修整
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: 如何使用安全性查看主题的概述。
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279328"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="4e11e-103">Microsoft Viva 主题安全修整</span><span class="sxs-lookup"><span data-stu-id="4e11e-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="4e11e-104">Viva 主题用户无法查看其现有 Office 365 权限阻止他们查看的主题信息。</span><span class="sxs-lookup"><span data-stu-id="4e11e-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="4e11e-105">用户在主题页面上看到的所有内容 (例如，SharePoint 网站、文档、文件) 都是他们已允许查看的信息。</span><span class="sxs-lookup"><span data-stu-id="4e11e-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="4e11e-106">Viva 主题不会更改任何现有权限。</span><span class="sxs-lookup"><span data-stu-id="4e11e-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="4e11e-107">为什么两个用户对同一主题可能有不同的视图</span><span class="sxs-lookup"><span data-stu-id="4e11e-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="4e11e-108">通过 AI 或手动创作创建主题时，它可以包含主题说明、替代名称、与主题关联的人员，以及与该主题相关的网站、页面和文件。</span><span class="sxs-lookup"><span data-stu-id="4e11e-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="4e11e-109">在主题页面上查看此信息时，查看同一主题的两个用户可能看不到相同的信息。</span><span class="sxs-lookup"><span data-stu-id="4e11e-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="4e11e-110">例如，当用户 1 查看 Neptune 主题页面时，他们可能会看到主题页面的此视图。</span><span class="sxs-lookup"><span data-stu-id="4e11e-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![用户 1 的 Neptune 主题](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="4e11e-112">但是，当用户 2 查看相同的 Neptune 主题页时，其视图与用户 1 不同。</span><span class="sxs-lookup"><span data-stu-id="4e11e-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="4e11e-113">用户 2 能够在主题页的"固定文件和页面"部分查看 *DG-2000* 产品概述文件，该文件不会为用户 1 显示。 </span><span class="sxs-lookup"><span data-stu-id="4e11e-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![用户 2 的 Neptune 主题](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="4e11e-115">用户在同一主题上可能看到的内容差异在于，用户可能没有查看相关站点或文件的 Office 365 权限。</span><span class="sxs-lookup"><span data-stu-id="4e11e-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="4e11e-116">Viva 主题尊重对主题中的项目设置的权限，并且无法更改对它们的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4e11e-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="4e11e-117">在我们的示例中，用户 1 无法查看其主题页中有关 Neptune 的 *DG-2000 产品* 概述文件，因为用户 1 没有查看该文件的 Office 365 权限。</span><span class="sxs-lookup"><span data-stu-id="4e11e-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="4e11e-118">如果用户无法查看主题中的足够信息，因此该主题将不可用。</span><span class="sxs-lookup"><span data-stu-id="4e11e-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="4e11e-119">发生这种情况时，用户不会看到突出显示的主题。</span><span class="sxs-lookup"><span data-stu-id="4e11e-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="4e11e-120">对主题中的详细信息具有访问权限的其他用户将能够看到该主题。</span><span class="sxs-lookup"><span data-stu-id="4e11e-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="4e11e-121">知识经理和主题参与者的主题权限</span><span class="sxs-lookup"><span data-stu-id="4e11e-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="4e11e-122">分配了管理主题的权限的用户（知识经理）只能查看他们有权在主题内查看的信息。</span><span class="sxs-lookup"><span data-stu-id="4e11e-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="4e11e-123">同样，具有创建和编辑主题权限的用户（主题参与者）将只能查看他们有权在主题内查看的信息。</span><span class="sxs-lookup"><span data-stu-id="4e11e-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="4e11e-124">AI 与手动选择的主题信息</span><span class="sxs-lookup"><span data-stu-id="4e11e-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="4e11e-125">主题可以包含 AI 生成的信息以及由主题参与者或知识经理添加或编辑的信息。</span><span class="sxs-lookup"><span data-stu-id="4e11e-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="4e11e-126">AI 添加的主题中的信息仅对有权访问源内容的人可见。</span><span class="sxs-lookup"><span data-stu-id="4e11e-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="4e11e-127">主题参与者或知识经理手动添加或编辑的主题说明和人员信息对可以看到该主题的每个人可见。</span><span class="sxs-lookup"><span data-stu-id="4e11e-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="4e11e-128">文件、页面和网站仅对具有源内容权限的用户可见，无论是手动添加还是由 AI 添加。</span><span class="sxs-lookup"><span data-stu-id="4e11e-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="4e11e-129">下表介绍了基于用户的权限在给定主题中可以看到哪些用户（主题查看者、参与者和知识管理员）。</span><span class="sxs-lookup"><span data-stu-id="4e11e-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="4e11e-130">主题项</span><span class="sxs-lookup"><span data-stu-id="4e11e-130">Topic item</span></span>|<span data-ttu-id="4e11e-131">用户可以看到哪些内容</span><span class="sxs-lookup"><span data-stu-id="4e11e-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="4e11e-132">主题名称</span><span class="sxs-lookup"><span data-stu-id="4e11e-132">Topic name</span></span>|<span data-ttu-id="4e11e-133">用户可以在主题中心查看所有主题的主题名称。</span><span class="sxs-lookup"><span data-stu-id="4e11e-133">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="4e11e-134">如果某些主题与用户的相关性较低，则这些主题可能不可见。</span><span class="sxs-lookup"><span data-stu-id="4e11e-134">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="4e11e-135">主题说明</span><span class="sxs-lookup"><span data-stu-id="4e11e-135">Topic description</span></span>|<span data-ttu-id="4e11e-136">AI 生成的说明仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="4e11e-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="4e11e-137">手动输入或编辑的说明对所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="4e11e-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="4e11e-138">人员</span><span class="sxs-lookup"><span data-stu-id="4e11e-138">People</span></span>|<span data-ttu-id="4e11e-139">固定人员对所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="4e11e-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="4e11e-140">建议人员仅对对源内容具有权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="4e11e-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4e11e-141">文件</span><span class="sxs-lookup"><span data-stu-id="4e11e-141">Files</span></span>|<span data-ttu-id="4e11e-142">文件仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="4e11e-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4e11e-143">页面</span><span class="sxs-lookup"><span data-stu-id="4e11e-143">Pages</span></span>|<span data-ttu-id="4e11e-144">只有对源内容具有权限的用户才能看到页面。</span><span class="sxs-lookup"><span data-stu-id="4e11e-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4e11e-145">网站</span><span class="sxs-lookup"><span data-stu-id="4e11e-145">Sites</span></span>|<span data-ttu-id="4e11e-146">网站仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="4e11e-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="4e11e-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e11e-147">See also</span></span>

