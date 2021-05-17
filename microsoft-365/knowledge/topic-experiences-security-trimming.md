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
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939619"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="46537-103">Microsoft Viva 主题安全修整</span><span class="sxs-lookup"><span data-stu-id="46537-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="46537-104">Viva 主题用户无法查看主题中他们现有的Office 365权限阻止他们查看的信息。</span><span class="sxs-lookup"><span data-stu-id="46537-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="46537-105">用户在主题页面上看到的所有内容 (例如，SharePoint网站、文档) 文件将是他们已被允许查看的信息。</span><span class="sxs-lookup"><span data-stu-id="46537-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="46537-106">Viva 主题不更改任何现有权限。</span><span class="sxs-lookup"><span data-stu-id="46537-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="46537-107">为什么两个用户对同一主题可能有不同的视图</span><span class="sxs-lookup"><span data-stu-id="46537-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="46537-108">当通过 AI 或手动选择创建主题时，它可以包含主题描述、替代名称、与主题关联的人员，以及与该主题相关的网站、页面和文件。</span><span class="sxs-lookup"><span data-stu-id="46537-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="46537-109">在主题页面上查看此信息时，查看同一主题的两个用户可能看不到相同的信息。</span><span class="sxs-lookup"><span data-stu-id="46537-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="46537-110">例如，当用户 1 查看 Neptune 主题页面时，他们可能会看到主题页面的此视图。</span><span class="sxs-lookup"><span data-stu-id="46537-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![用户 1 的 Neptune 主题](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="46537-112">但是，当用户 2 查看同一 Neptune 主题页时，其视图与用户 1 不同。</span><span class="sxs-lookup"><span data-stu-id="46537-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="46537-113">用户 2 可以在主题页面的"固定的文件和页面"部分查看 *DG-2000 产品* 概述文件，该文件不会为用户 1 显示。 </span><span class="sxs-lookup"><span data-stu-id="46537-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![用户 2 的 Neptune 主题](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="46537-115">用户在同一主题上看到的内容的不同之处在于，用户可能Office 365查看相关站点或文件的权限。</span><span class="sxs-lookup"><span data-stu-id="46537-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="46537-116">Viva 主题遵守对主题中的项目设置的权限，并且无法更改对它们的访问权限。</span><span class="sxs-lookup"><span data-stu-id="46537-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="46537-117">在我们的示例中，用户 1 无法查看 Neptune 的主题页中的 *DG-2000 产品* 概述文件，因为用户 1 Office 365查看该文件的权限。</span><span class="sxs-lookup"><span data-stu-id="46537-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="46537-118">如果用户无法查看主题中的足够信息，因此该主题将不可用。</span><span class="sxs-lookup"><span data-stu-id="46537-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="46537-119">发生这种情况时，用户将看不到突出显示的主题。</span><span class="sxs-lookup"><span data-stu-id="46537-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="46537-120">另一个拥有主题中更多信息的权限的用户将能够查看该主题。</span><span class="sxs-lookup"><span data-stu-id="46537-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="46537-121">知识经理和主题参与者的主题权限</span><span class="sxs-lookup"><span data-stu-id="46537-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="46537-122">分配了主题管理权限的用户（知识管理员）只能查看他们有权在主题内查看的信息。</span><span class="sxs-lookup"><span data-stu-id="46537-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="46537-123">同样，具有创建和编辑主题权限的用户（主题参与者）将只能查看他们有权在主题内查看的信息。</span><span class="sxs-lookup"><span data-stu-id="46537-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="46537-124">AI 与手动选择的主题信息</span><span class="sxs-lookup"><span data-stu-id="46537-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="46537-125">主题可以包含 AI 生成的信息以及由主题参与者或知识管理员添加或编辑的信息。</span><span class="sxs-lookup"><span data-stu-id="46537-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="46537-126">AI 添加的主题中的信息仅对有权访问源内容的人可见。</span><span class="sxs-lookup"><span data-stu-id="46537-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="46537-127">主题参与者或知识经理手动添加或编辑的主题说明和人员信息对可以看到该主题的每个人可见。</span><span class="sxs-lookup"><span data-stu-id="46537-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="46537-128">文件、页面和网站仅对具有源内容权限的用户可见，无论是手动添加还是由 AI 添加。</span><span class="sxs-lookup"><span data-stu-id="46537-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="46537-129">下表介绍了哪些用户（主题查看者、参与者和知识管理员）可以基于其权限在给定主题中查看。</span><span class="sxs-lookup"><span data-stu-id="46537-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="46537-130">主题项</span><span class="sxs-lookup"><span data-stu-id="46537-130">Topic item</span></span>|<span data-ttu-id="46537-131">用户可以看到的内容</span><span class="sxs-lookup"><span data-stu-id="46537-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="46537-132">主题名称</span><span class="sxs-lookup"><span data-stu-id="46537-132">Topic name</span></span>|<span data-ttu-id="46537-133">用户可以在主题中心查看主题的主题名称。</span><span class="sxs-lookup"><span data-stu-id="46537-133">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="46537-134">如果用户对源内容没有权限或与用户相关性较低，则某些主题可能不可见。</span><span class="sxs-lookup"><span data-stu-id="46537-134">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="46537-135">主题描述</span><span class="sxs-lookup"><span data-stu-id="46537-135">Topic description</span></span>|<span data-ttu-id="46537-136">AI 生成的描述仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="46537-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="46537-137">手动输入或编辑的描述对所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="46537-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="46537-138">人员</span><span class="sxs-lookup"><span data-stu-id="46537-138">People</span></span>|<span data-ttu-id="46537-139">固定的人员对所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="46537-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="46537-140">建议的人员仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="46537-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="46537-141">文件</span><span class="sxs-lookup"><span data-stu-id="46537-141">Files</span></span>|<span data-ttu-id="46537-142">文件仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="46537-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="46537-143">页面</span><span class="sxs-lookup"><span data-stu-id="46537-143">Pages</span></span>|<span data-ttu-id="46537-144">页面仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="46537-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="46537-145">网站</span><span class="sxs-lookup"><span data-stu-id="46537-145">Sites</span></span>|<span data-ttu-id="46537-146">网站仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="46537-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="46537-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46537-147">See also</span></span>

