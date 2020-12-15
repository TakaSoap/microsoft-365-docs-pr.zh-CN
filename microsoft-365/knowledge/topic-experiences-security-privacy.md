---
title: 主题体验安全和隐私
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在 Microsoft 365 中规划主题体验安全和隐私
ms.openlocfilehash: 7b88e5bbc8158ebd7dea65b2ecbf77085651b439
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668121"
---
# <a name="topic-experiences-security-and-privacy"></a><span data-ttu-id="af121-103">主题体验安全和隐私</span><span class="sxs-lookup"><span data-stu-id="af121-103">Topic experiences security and privacy</span></span>

<span data-ttu-id="af121-104">主题体验使用 Microsoft 365 中的现有内容安全功能以及知识网络控件来控制向组织中用户显示哪些 AI 生成的内容。</span><span class="sxs-lookup"><span data-stu-id="af121-104">Topic experiences uses existing content security features in Microsoft 365, along with knowledge network controls, to control what AI-generated content is shown to users in your organization.</span></span> <span data-ttu-id="af121-105">它是 Microsoft 365 安全设置和 (网站、文件和文件夹权限的组合，) 主题体验管理员设置决定了给定用户可以在主题中看到的内容。</span><span class="sxs-lookup"><span data-stu-id="af121-105">It is the combination of Microsoft 365 security settings (permissions to sites, files, and folders) and topic experiences admin settings that determine what a given user can see in topics.</span></span>

<span data-ttu-id="af121-106">设置知识网络不会修改组织中内容的任何现有访问控制。</span><span class="sxs-lookup"><span data-stu-id="af121-106">Setting up the knowledge network does not modify any existing access controls on content in your organization.</span></span> <span data-ttu-id="af121-107">用户只会看到他们已有权访问哪些内容。</span><span class="sxs-lookup"><span data-stu-id="af121-107">Users will only see what they already have access to.</span></span>

<span data-ttu-id="af121-108">本文从安全角度介绍了主题体验的工作方式，以及知识管理员和知识管理员控制主题可见性时必须选择的选项。</span><span class="sxs-lookup"><span data-stu-id="af121-108">This article describes how topic experiences works from a security perspective and the options that knowledge administrators and knowledge managers have to control topic visibility.</span></span> <span data-ttu-id="af121-109">阅读本文作为主题 [体验规划的一部分](plan-topic-experiences.md)。</span><span class="sxs-lookup"><span data-stu-id="af121-109">Read this article as part of your [planning for topic experiences](plan-topic-experiences.md).</span></span>

<span data-ttu-id="af121-110">在阅读本文之前，你应该熟悉主题体验[](topic-center-overview.md)、主题中心以及如何使用主题[](work-with-topics.md)中心中的主题。 [](knowledge-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="af121-110">You should be familiar with [Topic experiences](knowledge-management-overview.md), the [topic center](topic-center-overview.md), and how to [work with topics in the topic center](work-with-topics.md) before you read this article.</span></span>

## <a name="what-users-can-see-in-topics"></a><span data-ttu-id="af121-111">用户可以在主题中查看哪些内容</span><span class="sxs-lookup"><span data-stu-id="af121-111">What users can see in topics</span></span>

<span data-ttu-id="af121-112">若要查看主题，用户必须：</span><span class="sxs-lookup"><span data-stu-id="af121-112">To see topics, a user must:</span></span>

- <span data-ttu-id="af121-113">拥有主题体验许可证</span><span class="sxs-lookup"><span data-stu-id="af121-113">Have a Topic Experiences license</span></span>
- <span data-ttu-id="af121-114">成为 [主题查看器](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)、 [参与者或知识管理员](topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="af121-114">Be a [topic viewer](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [contributor, or knowledge manager](topic-experiences-user-permissions.md)</span></span>

<span data-ttu-id="af121-115">通过这两项操作，用户可以查看主题中心的访问权限，并允许他们查看突出显示和主题卡片。</span><span class="sxs-lookup"><span data-stu-id="af121-115">These two things give users view access to the topic center and allow them to see highlights and topic cards.</span></span>

<span data-ttu-id="af121-116">此外，主题参与者 [还具有](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) 主题的创建和编辑权限，并且知识管理员可以确认或删除主题。</span><span class="sxs-lookup"><span data-stu-id="af121-116">Topic contributors additionally have [create and edit](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) permissions for topics, and knowledge managers can confirm or remove topics.</span></span>

<span data-ttu-id="af121-117">首次发现主题时，知识管理人员可以在主题中心看到它。</span><span class="sxs-lookup"><span data-stu-id="af121-117">When a topic is first discovered, knowledge managers can see it in the topic center.</span></span> <span data-ttu-id="af121-118">根据主题的完整性和相关性，主题查看者可能会或可能不会看到主题卡片中提供的主题。</span><span class="sxs-lookup"><span data-stu-id="af121-118">Depending on the completeness and relevance of the topic, topic viewers may or may not see the topic presented in topic cards.</span></span>

<span data-ttu-id="af121-119">主题可以包含 AI 生成的信息以及主题参与者或知识管理员添加或编辑的信息。</span><span class="sxs-lookup"><span data-stu-id="af121-119">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

- <span data-ttu-id="af121-120">AI 添加的主题中的信息仅对有权访问源内容的人可见。</span><span class="sxs-lookup"><span data-stu-id="af121-120">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
- <span data-ttu-id="af121-121">主题参与者或知识管理员手动添加或编辑的文本对可以看到该主题的每个人可见。</span><span class="sxs-lookup"><span data-stu-id="af121-121">Text that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="af121-122">主题查看者和参与者可以在主题中心查看已确认和已发布主题的列表，但给定人员可以看到的主题详细信息取决于他们对源材料具有的权限以及主题是否已手动编辑。</span><span class="sxs-lookup"><span data-stu-id="af121-122">Topic viewers and contributors can see the list of confirmed and published topics in the topic center, but the topic details that a given person can see depends on the permissions that they have to the source material and on whether the topic has been manually edited.</span></span>

<span data-ttu-id="af121-123">下表介绍了基于用户的权限在给定主题中可以看到哪些用户（主题查看者、参与者和知识管理员）。</span><span class="sxs-lookup"><span data-stu-id="af121-123">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="af121-124">主题项</span><span class="sxs-lookup"><span data-stu-id="af121-124">Topic item</span></span>|<span data-ttu-id="af121-125">用户可以看到哪些内容</span><span class="sxs-lookup"><span data-stu-id="af121-125">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="af121-126">主题名称</span><span class="sxs-lookup"><span data-stu-id="af121-126">Topic name</span></span>|<span data-ttu-id="af121-127">用户可以在主题中心查看所有主题的主题名称。</span><span class="sxs-lookup"><span data-stu-id="af121-127">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="af121-128">如果某些主题与用户的相关性较低，则这些主题可能不可见。</span><span class="sxs-lookup"><span data-stu-id="af121-128">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="af121-129">主题说明</span><span class="sxs-lookup"><span data-stu-id="af121-129">Topic description</span></span>|<span data-ttu-id="af121-130">AI 生成的说明仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="af121-130">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="af121-131">手动输入或编辑的说明对所有用户都可见。</span><span class="sxs-lookup"><span data-stu-id="af121-131">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="af121-132">人员</span><span class="sxs-lookup"><span data-stu-id="af121-132">People</span></span>|<span data-ttu-id="af121-133">固定人员对所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="af121-133">Pinned people are visible to all users.</span></span> <span data-ttu-id="af121-134">建议的用户仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="af121-134">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="af121-135">文件</span><span class="sxs-lookup"><span data-stu-id="af121-135">Files</span></span>|<span data-ttu-id="af121-136">文件仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="af121-136">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="af121-137">页面</span><span class="sxs-lookup"><span data-stu-id="af121-137">Pages</span></span>|<span data-ttu-id="af121-138">只有对源内容具有权限的用户才能看到页面。</span><span class="sxs-lookup"><span data-stu-id="af121-138">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="af121-139">网站</span><span class="sxs-lookup"><span data-stu-id="af121-139">Sites</span></span>|<span data-ttu-id="af121-140">网站仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="af121-140">Sites are only visible to users who have permissions to the source content.</span></span>|

## <a name="best-practices"></a><span data-ttu-id="af121-141">最佳做法</span><span class="sxs-lookup"><span data-stu-id="af121-141">Best practices</span></span>

<span data-ttu-id="af121-142">主题体验基于用户对内容的现有权限向用户显示信息。</span><span class="sxs-lookup"><span data-stu-id="af121-142">Topic experiences presents information to users based on their existing permissions to content.</span></span> <span data-ttu-id="af121-143">Microsoft 365 提供了多种方式来确保敏感内容仅限于适当的用户。</span><span class="sxs-lookup"><span data-stu-id="af121-143">Microsoft 365 provides a variety of ways to ensure that sensitive content is restricted to appropriate users.</span></span> <span data-ttu-id="af121-144">除了标准团队权限或网站权限外，您还可以使用敏感度标签或数据丢失[](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)防护来限制对内容和访问评审的访问，[](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)以定期检查用户对敏感信息的访问。 [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)</span><span class="sxs-lookup"><span data-stu-id="af121-144">Beyond standard team or site permissions, you can use [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) or [data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to restrict access to content and [access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) to periodically review user access to sensitive information.</span></span>

<span data-ttu-id="af121-145">建议您使用这些工具来确保在组织内部正确设置内容权限。</span><span class="sxs-lookup"><span data-stu-id="af121-145">We recommend that you use these tools to ensure that your content permissions are set appropriately inside your organization.</span></span> <span data-ttu-id="af121-146">然后，主题体验可以为用户提供有用且合适的信息。</span><span class="sxs-lookup"><span data-stu-id="af121-146">Topic experiences can then provide useful and appropriate information to your users.</span></span>

<span data-ttu-id="af121-147">如果你希望从主题体验中完全排除某些主题，则还可以：</span><span class="sxs-lookup"><span data-stu-id="af121-147">If there are topics that you want to exclude entirely from topic experiences, you can also:</span></span>

- <span data-ttu-id="af121-148">[从主题发现中排除敏感 SharePoint 网站](topic-experiences-discovery.md#select-sharepoint-topic-sources)。</span><span class="sxs-lookup"><span data-stu-id="af121-148">[Exclude sensitive SharePoint sites from topic discovery](topic-experiences-discovery.md#select-sharepoint-topic-sources).</span></span> <span data-ttu-id="af121-149">这些网站中的内容不会显示在主题体验中。</span><span class="sxs-lookup"><span data-stu-id="af121-149">Content in these sites will not appear in topic experiences.</span></span>

- <span data-ttu-id="af121-150">[按名称排除主题](topic-experiences-discovery.md#exclude-topics-by-name)。</span><span class="sxs-lookup"><span data-stu-id="af121-150">[Exclude topics by name](topic-experiences-discovery.md#exclude-topics-by-name).</span></span> <span data-ttu-id="af121-151">明确排除的主题不会显示在主题体验中。</span><span class="sxs-lookup"><span data-stu-id="af121-151">Topics explicitly excluded will not appear in topic experiences.</span></span>

- <span data-ttu-id="af121-152">使知识经理删除主题中心中的主题。</span><span class="sxs-lookup"><span data-stu-id="af121-152">Have knowledge managers remove topics in the topic center.</span></span>

<span data-ttu-id="af121-153">此外，我们建议采用以下最佳实践：</span><span class="sxs-lookup"><span data-stu-id="af121-153">Additionally, we recommend these best practices:</span></span>

- <span data-ttu-id="af121-154">从组织的不同区域招募知识经理。</span><span class="sxs-lookup"><span data-stu-id="af121-154">Recruit knowledge managers from different areas of your organization.</span></span> <span data-ttu-id="af121-155">让知识经理具有各种专业知识（以及访问 AI 使用的基础内容）可以帮助你为用户选择最有用的知识，并删除敏感信息（如果找到）。</span><span class="sxs-lookup"><span data-stu-id="af121-155">Having knowledge managers with a variety of expertise - and access to the underlying content used by AI - can help you curate the most useful knowledge for your users and remove sensitive information if found.</span></span>

- <span data-ttu-id="af121-156">设置用于请求更改的工作流。</span><span class="sxs-lookup"><span data-stu-id="af121-156">Set up a workflow for requesting changes.</span></span> <span data-ttu-id="af121-157">知识管理员或团队或网站所有者应具有一个流程，通过此过程，他们可以请求在组织中启动新项目时排除主题或网站，或者当他们发现内容具有不当权限设置时。</span><span class="sxs-lookup"><span data-stu-id="af121-157">Knowledge managers or team or site owners should have a process by which they can request exclusion of topics or sites as new projects are started within your organization or if they find content with inappropriate permissions settings.</span></span>

- <span data-ttu-id="af121-158">在创建主题说明时，请注意访问群体和信息敏感度。</span><span class="sxs-lookup"><span data-stu-id="af121-158">Be aware of the audience and the sensitivity of information when creating topic descriptions.</span></span> <span data-ttu-id="af121-159">这些说明对于没有主题源内容权限的用户可能可见。</span><span class="sxs-lookup"><span data-stu-id="af121-159">These descriptions may be visible to users who don't have permissions to the source content for the topic.</span></span>

<span data-ttu-id="af121-160">虽然您可以更改单个主题页面上的权限以缩小对特定组用户的访问范围，但我们不建议使用这种方法，因为需要执行很高的管理工作。</span><span class="sxs-lookup"><span data-stu-id="af121-160">While you can change the permissions on individual topic pages to narrow access to a specific group of users, we don't recommend this approach because of the high degree of administrative effort required.</span></span>

## <a name="see-also"></a><span data-ttu-id="af121-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af121-161">See also</span></span>

[<span data-ttu-id="af121-162">配置具有三层保护的 Teams</span><span class="sxs-lookup"><span data-stu-id="af121-162">Configure Teams with three tiers of protection</span></span>](../solutions/configure-teams-three-tiers-protection.md)

[<span data-ttu-id="af121-163">规划主题体验</span><span class="sxs-lookup"><span data-stu-id="af121-163">Plan topic experiences</span></span>](plan-topic-experiences.md)

[<span data-ttu-id="af121-164">设置主题体验</span><span class="sxs-lookup"><span data-stu-id="af121-164">Set up topic experiences</span></span>](set-up-topic-experiences.md)
