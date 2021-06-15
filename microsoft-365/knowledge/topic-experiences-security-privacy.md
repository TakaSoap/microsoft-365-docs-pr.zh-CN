---
title: Microsoft Viva 主题安全和隐私
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 了解如何规划 Microsoft Viva 主题安全和隐私
ms.openlocfilehash: b8c82b1914df739ea9086a4ce1585733a7b6d854
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925487"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a><span data-ttu-id="8f85a-103">Microsoft Viva 主题安全和隐私</span><span class="sxs-lookup"><span data-stu-id="8f85a-103">Microsoft Viva Topics security and privacy</span></span>

<span data-ttu-id="8f85a-104">主题使用组织中现有的内容安全功能Microsoft 365管理控件，以控制向组织用户显示哪些 AI 生成的内容。</span><span class="sxs-lookup"><span data-stu-id="8f85a-104">Topics uses existing content security features in Microsoft 365, along with administrative controls, to control what AI-generated content is shown to users in your organization.</span></span> <span data-ttu-id="8f85a-105">它是网站Microsoft 365安全设置 (网站、文件和文件夹) 和主题管理员设置的组合，确定给定用户可以在主题中看到的内容。</span><span class="sxs-lookup"><span data-stu-id="8f85a-105">It is the combination of Microsoft 365 security settings (permissions to sites, files, and folders) and Topics admin settings that determine what a given user can see in topics.</span></span>

<span data-ttu-id="8f85a-106">设置主题不会修改组织中对于内容的任何现有访问控制。</span><span class="sxs-lookup"><span data-stu-id="8f85a-106">Setting up Topics does not modify any existing access controls on content in your organization.</span></span> <span data-ttu-id="8f85a-107">用户将只能查看有权访问的内容。</span><span class="sxs-lookup"><span data-stu-id="8f85a-107">Users will only see what they already have access to.</span></span>

<span data-ttu-id="8f85a-108">本文介绍了主题从安全角度的工作方式，以及知识管理员和知识管理员控制主题可见性时必须选择的选项。</span><span class="sxs-lookup"><span data-stu-id="8f85a-108">This article describes how Topics works from a security perspective and the options that knowledge administrators and knowledge managers have to control topic visibility.</span></span> <span data-ttu-id="8f85a-109">阅读本文作为规划主题 [的一部分](plan-topic-experiences.md)。</span><span class="sxs-lookup"><span data-stu-id="8f85a-109">Read this article as part of your [planning for Topics](plan-topic-experiences.md).</span></span>

<span data-ttu-id="8f85a-110">在阅读[本文之前，](topic-experiences-overview.md)您应熟悉什么是主题、[](topic-center-overview.md)主题中心，以及如何使用主题[](manage-topics.md)中心中的主题。</span><span class="sxs-lookup"><span data-stu-id="8f85a-110">You should be familiar with [what Topics is](topic-experiences-overview.md), the [topic center](topic-center-overview.md), and how to [work with topics in the topic center](manage-topics.md) before you read this article.</span></span>

## <a name="what-users-can-see-in-topics"></a><span data-ttu-id="8f85a-111">用户可以在主题中查看哪些内容</span><span class="sxs-lookup"><span data-stu-id="8f85a-111">What users can see in topics</span></span>

<span data-ttu-id="8f85a-112">若要查看主题，用户必须：</span><span class="sxs-lookup"><span data-stu-id="8f85a-112">To see topics, a user must:</span></span>

- <span data-ttu-id="8f85a-113">拥有 Viva 主题许可证</span><span class="sxs-lookup"><span data-stu-id="8f85a-113">Have a Viva Topics license</span></span>
- <span data-ttu-id="8f85a-114">成为主题 [查看器](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)、 [参与者或知识管理员](topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="8f85a-114">Be a [topic viewer](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [contributor, or knowledge manager](topic-experiences-user-permissions.md)</span></span>

<span data-ttu-id="8f85a-115">这两项内容使用户能够查看对主题中心的访问权限，并允许用户查看突出显示和主题卡片。</span><span class="sxs-lookup"><span data-stu-id="8f85a-115">These two things give users view access to the topic center and allow them to see highlights and topic cards.</span></span>

<span data-ttu-id="8f85a-116">主题参与者还 [具有主题的](topic-experiences-user-permissions.md) 创建和编辑权限，并且知识管理人员可以确认或删除主题。</span><span class="sxs-lookup"><span data-stu-id="8f85a-116">Topic contributors additionally have [create and edit](topic-experiences-user-permissions.md) permissions for topics, and knowledge managers can confirm or remove topics.</span></span>

<span data-ttu-id="8f85a-117">首次发现主题时，知识管理人员可以在主题中心看到它。</span><span class="sxs-lookup"><span data-stu-id="8f85a-117">When a topic is first discovered, knowledge managers can see it in the topic center.</span></span> <span data-ttu-id="8f85a-118">根据主题的完整性和相关性，主题查看者可能会或可能不会看到主题卡片中提供的主题。</span><span class="sxs-lookup"><span data-stu-id="8f85a-118">Depending on the completeness and relevance of the topic, topic viewers may or may not see the topic presented in topic cards.</span></span>

<span data-ttu-id="8f85a-119">主题可以包含 AI 生成的信息以及由主题参与者或知识管理员添加或编辑的信息。</span><span class="sxs-lookup"><span data-stu-id="8f85a-119">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

- <span data-ttu-id="8f85a-120">主题中由 AI 添加的信息仅对具有对该源内容访问权限的人员可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-120">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
- <span data-ttu-id="8f85a-121">主题参与者或知识管理员手动添加或编辑的文本对可以看到该主题的每个人可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-121">Text that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="8f85a-122">主题查看者和参与者可以在主题中心查看已确认和已发布主题的列表，但给定人员可以看到的主题详细信息取决于他们对源材料的权限以及主题是否已手动编辑。</span><span class="sxs-lookup"><span data-stu-id="8f85a-122">Topic viewers and contributors can see the list of confirmed and published topics in the topic center, but the topic details that a given person can see depends on the permissions that they have to the source material and on whether the topic has been manually edited.</span></span>

<span data-ttu-id="8f85a-123">下表介绍了哪些用户（主题查看者、参与者和知识管理员）可以基于其权限在给定主题中查看。</span><span class="sxs-lookup"><span data-stu-id="8f85a-123">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="8f85a-124">主题项</span><span class="sxs-lookup"><span data-stu-id="8f85a-124">Topic item</span></span>|<span data-ttu-id="8f85a-125">用户可以看到的内容</span><span class="sxs-lookup"><span data-stu-id="8f85a-125">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="8f85a-126">主题名称</span><span class="sxs-lookup"><span data-stu-id="8f85a-126">Topic name</span></span>|<span data-ttu-id="8f85a-127">用户可以在主题中心查看主题的主题名称。</span><span class="sxs-lookup"><span data-stu-id="8f85a-127">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="8f85a-128">如果用户对源内容没有权限或与用户相关性较低，则某些主题可能不可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-128">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="8f85a-129">主题描述</span><span class="sxs-lookup"><span data-stu-id="8f85a-129">Topic description</span></span>|<span data-ttu-id="8f85a-130">AI 生成的描述仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-130">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="8f85a-131">手动输入或编辑的描述对所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-131">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="8f85a-132">人员</span><span class="sxs-lookup"><span data-stu-id="8f85a-132">People</span></span>|<span data-ttu-id="8f85a-133">固定的人员对所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-133">Pinned people are visible to all users.</span></span> <span data-ttu-id="8f85a-134">建议的人员仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-134">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="8f85a-135">文件</span><span class="sxs-lookup"><span data-stu-id="8f85a-135">Files</span></span>|<span data-ttu-id="8f85a-136">文件仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-136">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="8f85a-137">页面</span><span class="sxs-lookup"><span data-stu-id="8f85a-137">Pages</span></span>|<span data-ttu-id="8f85a-138">页面仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-138">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="8f85a-139">网站</span><span class="sxs-lookup"><span data-stu-id="8f85a-139">Sites</span></span>|<span data-ttu-id="8f85a-140">网站仅对具有源内容权限的用户可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-140">Sites are only visible to users who have permissions to the source content.</span></span>|

## <a name="users-personal-and-private-data"></a><span data-ttu-id="8f85a-141">用户的个人数据和私有数据</span><span class="sxs-lookup"><span data-stu-id="8f85a-141">Users' personal and private data</span></span>

<span data-ttu-id="8f85a-142">Viva 主题仅发现您SharePoint网站中的主题。</span><span class="sxs-lookup"><span data-stu-id="8f85a-142">Viva Topics only discovers topics in the SharePoint sites that you specify.</span></span> <span data-ttu-id="8f85a-143">不包括用户的个人存储，例如OneDrive邮件或邮件。</span><span class="sxs-lookup"><span data-stu-id="8f85a-143">Users’ personal storage such as personal mail or OneDrive is not included.</span></span>

## <a name="best-practices"></a><span data-ttu-id="8f85a-144">最佳做法</span><span class="sxs-lookup"><span data-stu-id="8f85a-144">Best practices</span></span>

<span data-ttu-id="8f85a-145">主题根据用户现有的内容权限向用户显示信息。</span><span class="sxs-lookup"><span data-stu-id="8f85a-145">Topics presents information to users based on their existing permissions to content.</span></span> <span data-ttu-id="8f85a-146">Microsoft 365提供了多种方式来确保敏感内容仅限于适当的用户。</span><span class="sxs-lookup"><span data-stu-id="8f85a-146">Microsoft 365 provides a variety of ways to ensure that sensitive content is restricted to appropriate users.</span></span> <span data-ttu-id="8f85a-147">除了标准团队或网站权限之外，您还可以使用敏感度标签或数据丢失防护[](../compliance/dlp-learn-about-dlp.md)来限制对内容和访问评审的访问，以[](/azure/active-directory/governance/access-reviews-overview)定期检查用户对敏感信息的访问。 [](../compliance/sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="8f85a-147">Beyond standard team or site permissions, you can use [sensitivity labels](../compliance/sensitivity-labels.md) or [data loss prevention](../compliance/dlp-learn-about-dlp.md) to restrict access to content and [access reviews](/azure/active-directory/governance/access-reviews-overview) to periodically review user access to sensitive information.</span></span>

<span data-ttu-id="8f85a-148">建议您使用这些工具来确保在组织内部正确设置内容权限。</span><span class="sxs-lookup"><span data-stu-id="8f85a-148">We recommend that you use these tools to ensure that your content permissions are set appropriately inside your organization.</span></span> <span data-ttu-id="8f85a-149">然后，主题体验可以为用户提供有用的适当信息。</span><span class="sxs-lookup"><span data-stu-id="8f85a-149">Topic experiences can then provide useful and appropriate information to your users.</span></span>

<span data-ttu-id="8f85a-150">如果要将主题完全从主题体验中排除，还可以：</span><span class="sxs-lookup"><span data-stu-id="8f85a-150">If there are topics that you want to exclude entirely from topic experiences, you can also:</span></span>

- <span data-ttu-id="8f85a-151">[从主题发现 SharePoint敏感网站](topic-experiences-discovery.md#select-sharepoint-topic-sources)。</span><span class="sxs-lookup"><span data-stu-id="8f85a-151">[Exclude sensitive SharePoint sites from topic discovery](topic-experiences-discovery.md#select-sharepoint-topic-sources).</span></span> <span data-ttu-id="8f85a-152">这些网站的内容不会出现在主题经验中。</span><span class="sxs-lookup"><span data-stu-id="8f85a-152">Content in these sites will not appear in topic experiences.</span></span>

- <span data-ttu-id="8f85a-153">[按名称排除主题](topic-experiences-discovery.md#exclude-topics-by-name)。</span><span class="sxs-lookup"><span data-stu-id="8f85a-153">[Exclude topics by name](topic-experiences-discovery.md#exclude-topics-by-name).</span></span> <span data-ttu-id="8f85a-154">明确排除的主题将不会出现在主题体验中。</span><span class="sxs-lookup"><span data-stu-id="8f85a-154">Topics explicitly excluded will not appear in topic experiences.</span></span>

- <span data-ttu-id="8f85a-155">使知识经理删除主题中心中的主题。</span><span class="sxs-lookup"><span data-stu-id="8f85a-155">Have knowledge managers remove topics in the topic center.</span></span>

<span data-ttu-id="8f85a-156">此外，我们建议采用以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="8f85a-156">Additionally, we recommend these best practices:</span></span>

- <span data-ttu-id="8f85a-157">从组织的不同区域招聘知识经理。</span><span class="sxs-lookup"><span data-stu-id="8f85a-157">Recruit knowledge managers from different areas of your organization.</span></span> <span data-ttu-id="8f85a-158">让具有各种专业知识的知识管理人员（以及访问 AI 使用的基础内容）可以帮助你为用户选择最有用的知识，并删除敏感信息（如果找到）。</span><span class="sxs-lookup"><span data-stu-id="8f85a-158">Having knowledge managers with a variety of expertise - and access to the underlying content used by AI - can help you curate the most useful knowledge for your users and remove sensitive information if found.</span></span>

- <span data-ttu-id="8f85a-159">设置用于请求更改的工作流。</span><span class="sxs-lookup"><span data-stu-id="8f85a-159">Set up a workflow for requesting changes.</span></span> <span data-ttu-id="8f85a-160">知识经理、工作组或网站所有者应具有一个流程，当在组织中启动新项目或当他们发现内容具有不适当的权限设置时，他们可以请求排除主题或网站。</span><span class="sxs-lookup"><span data-stu-id="8f85a-160">Knowledge managers or team or site owners should have a process by which they can request exclusion of topics or sites as new projects are started within your organization or if they find content with inappropriate permissions settings.</span></span>

- <span data-ttu-id="8f85a-161">在创建主题描述时要注意受众和信息的敏感度。</span><span class="sxs-lookup"><span data-stu-id="8f85a-161">Be aware of the audience and the sensitivity of information when creating topic descriptions.</span></span> <span data-ttu-id="8f85a-162">这些描述可能对没有权限访问该主题源内容的用户可见。</span><span class="sxs-lookup"><span data-stu-id="8f85a-162">These descriptions may be visible to users who don't have permissions to the source content for the topic.</span></span>

<span data-ttu-id="8f85a-163">虽然可以改变个别主题页面的权限，以缩小对特定用户群的访问范围，但我们不推荐这种方法，因为这需要高度的管理工作量。</span><span class="sxs-lookup"><span data-stu-id="8f85a-163">While you can change the permissions on individual topic pages to narrow access to a specific group of users, we don't recommend this approach because of the high degree of administrative effort required.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f85a-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f85a-164">See also</span></span>

[<span data-ttu-id="8f85a-165">配置具有三层保护的 Teams</span><span class="sxs-lookup"><span data-stu-id="8f85a-165">Configure Teams with three tiers of protection</span></span>](../solutions/configure-teams-three-tiers-protection.md)

[<span data-ttu-id="8f85a-166">计划主题体验</span><span class="sxs-lookup"><span data-stu-id="8f85a-166">Plan topic experiences</span></span>](plan-topic-experiences.md)

[<span data-ttu-id="8f85a-167">设置主题体验</span><span class="sxs-lookup"><span data-stu-id="8f85a-167">Set up topic experiences</span></span>](set-up-topic-experiences.md)
