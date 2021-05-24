---
title: 在 Microsoft Viva 主题中大规模管理主题
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: lauriellis
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: 了解使用 Viva 主题管理组织中许多主题的最佳实践。
ms.openlocfilehash: 613c4ed85a62efd22ba104c810420a2d0af015c5
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624833"
---
# <a name="manage-topics-at-scale-in-microsoft-viva-topics"></a><span data-ttu-id="7436f-103">在 Microsoft Viva 主题中大规模管理主题</span><span class="sxs-lookup"><span data-stu-id="7436f-103">Manage topics at scale in Microsoft Viva Topics</span></span>

<span data-ttu-id="7436f-104">为 Viva 主题SharePoint或整个组织编制索引时，可能会生成许多主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-104">When you index your SharePoint sites or your entire organization for Viva Topics, many topics might be generated.</span></span> <span data-ttu-id="7436f-105">如果发生这种情况，并且你在"管理主题"页上看到数千个建议的主题，那么了解从何处开始可能会非常困难。</span><span class="sxs-lookup"><span data-stu-id="7436f-105">When this happens and you see thousands of suggested topics on the **Manage topics** page, it can be challenging to know where to start.</span></span> <span data-ttu-id="7436f-106">本文介绍 Viva 主题如何帮助您优化向搜索信息的用户显示的主题和信息，即使在具有大量主题的大型组织中。</span><span class="sxs-lookup"><span data-stu-id="7436f-106">This article describes how Viva Topics helps you optimize which topics and information are shown to users who are searching for information, even in large organizations with large numbers of topics.</span></span>

<span data-ttu-id="7436f-107">首先，提醒主题 [的四个阶段](manage-topics.md#topic-stages)：</span><span class="sxs-lookup"><span data-stu-id="7436f-107">First, a reminder of the [four stages for topics](manage-topics.md#topic-stages):</span></span>

- <span data-ttu-id="7436f-108">**建议**: 主题已由 AI 标识，且具有足够的支持资源、连接和属性。</span><span class="sxs-lookup"><span data-stu-id="7436f-108">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="7436f-109"> (UI.) </span><span class="sxs-lookup"><span data-stu-id="7436f-109">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="7436f-110">**Confirmed：AI** 已发现并经过验证的主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-110">**Confirmed**: A topic that has been discovered by AI and has been validated.</span></span> <span data-ttu-id="7436f-111">当出现两种情况之一时，将进行主题验证：</span><span class="sxs-lookup"><span data-stu-id="7436f-111">Topic validation occurs when either:</span></span>

   - <span data-ttu-id="7436f-112">知识经理确认主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-112">A knowledge manager confirms a topic.</span></span> <span data-ttu-id="7436f-113">知识经理 [在"管理主题"页上](manage-topics.md#confirmed-topics)**确认主题**。</span><span class="sxs-lookup"><span data-stu-id="7436f-113">A knowledge manager [confirms a topic](manage-topics.md#confirmed-topics) on the **Manage topics** page.</span></span>

   - <span data-ttu-id="7436f-114">多个用户确认主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-114">Multiple users confirm a topic.</span></span> <span data-ttu-id="7436f-115">对于使用主题卡片上的反馈机制进行投票的用户，必须获得两个肯定的投票。</span><span class="sxs-lookup"><span data-stu-id="7436f-115">There must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="7436f-116">例如，如果一个用户对特定主题的投票是肯定的，而一个用户投了负，则你仍然需要另外两个积极投票来确认该主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-116">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="7436f-117">**已发布**：已选择的主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-117">**Published**: A topic that has been curated.</span></span> <span data-ttu-id="7436f-118">已进行手动编辑以改进其质量，或者已由用户创建。</span><span class="sxs-lookup"><span data-stu-id="7436f-118">Manual edits have been made to improve its quality, or it has been created by a user.</span></span>

- <span data-ttu-id="7436f-119">**已删除**：主题已被拒绝，不再对查看者可见。</span><span class="sxs-lookup"><span data-stu-id="7436f-119">**Removed**: A topic that has been rejected and will no longer be visible to viewers.</span></span> <span data-ttu-id="7436f-120">可以在建议、确认或发布主题 (状态删除主题) 。</span><span class="sxs-lookup"><span data-stu-id="7436f-120">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="7436f-121">当出现两种情况之一时，将删除主题：</span><span class="sxs-lookup"><span data-stu-id="7436f-121">Topic removal occurs when either:</span></span>

   - <span data-ttu-id="7436f-122">知识经理会删除一个主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-122">A knowledge manager removes a topic.</span></span> <span data-ttu-id="7436f-123">知识经理删除"管理主题" **页上的主题** 。</span><span class="sxs-lookup"><span data-stu-id="7436f-123">A knowledge manager removes a topic on the **Manage topics** page.</span></span>

   - <span data-ttu-id="7436f-124">多个用户在主题卡片上使用反馈机制投了负票。</span><span class="sxs-lookup"><span data-stu-id="7436f-124">Multiple users cast negative votes using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="7436f-125">若要删除主题，必须存在从用户收到的两个负数投票。</span><span class="sxs-lookup"><span data-stu-id="7436f-125">For a topic to be removed, there must be a net of two negative votes received from users.</span></span> <span data-ttu-id="7436f-126">例如，如果一个用户对特定主题投了负票，而一个用户对特定主题投了肯定票，你仍然需要另外两个否定的投票来删除该主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-126">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span>

  <span data-ttu-id="7436f-127">删除已发布的主题后，需要通过主题中心的"页面库"手动删除包含特用详细信息的页面。</span><span class="sxs-lookup"><span data-stu-id="7436f-127">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

## <a name="knowledge-manager-role"></a><span data-ttu-id="7436f-128">知识管理器角色</span><span class="sxs-lookup"><span data-stu-id="7436f-128">Knowledge manager role</span></span> 

<span data-ttu-id="7436f-129">配置 Viva 主题时，您将添加一组被授予权限以查看主题中心中的" **管理** 主题"页的用户。</span><span class="sxs-lookup"><span data-stu-id="7436f-129">When you configure Viva Topics, you'll add a group of users who are granted permissions to see the **Manage topics** page in the topic center.</span></span> <span data-ttu-id="7436f-130">它仅针对那些担任主题主要选文角色的用户显示。</span><span class="sxs-lookup"><span data-stu-id="7436f-130">It will appear only for these users who hold the role of primary curation for the topics.</span></span> <span data-ttu-id="7436f-131">他们将有权访问有关主题的数据，并且将能够查看他们有权访问的所有主题的列表进行审阅和选择。</span><span class="sxs-lookup"><span data-stu-id="7436f-131">They'll have access to data about the topics and will be able to see lists of all topics that they have access to review and curate.</span></span>

<span data-ttu-id="7436f-132">此角色的员工应具有查看各种主题的广泛权限。</span><span class="sxs-lookup"><span data-stu-id="7436f-132">Employees in this role should have broad permissions to view a wide array of topics.</span></span> <span data-ttu-id="7436f-133">或者，如果权限被分段，你可能希望选择一组代表不同业务区域并可以自己进行组织的用户。</span><span class="sxs-lookup"><span data-stu-id="7436f-133">Or if permissions are segmented, you might want to select a group of users that represent different areas of the business and can curate for their own areas.</span></span>

<span data-ttu-id="7436f-134">首次在主题中心查看主题时，建议的主题完全由 AI 定义。</span><span class="sxs-lookup"><span data-stu-id="7436f-134">When you first review topics in the topic center, suggested topics are purely AI-defined.</span></span> <span data-ttu-id="7436f-135">知识管理人员可能需要先查看每个主题，然后再向广泛的用户社区推出 Viva 主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-135">Knowledge managers might want to review each one before rolling out Viva Topics to a broad user community.</span></span> <span data-ttu-id="7436f-136">大规模工作时，这种方法很少可行，因为有数千个主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-136">When working at scale, this approach is rarely a practical because of the thousands of topics.</span></span>

<span data-ttu-id="7436f-137">建议的方法是为初始用户集找到最相关或最重要的主题的平衡点，并侧重于在推出 Viva 主题之前确定这些主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-137">The recommended approach is to find a balance of the most pertinent or important topics for your initial set of users and focus on curation of those topics before rollout of Viva Topics.</span></span> <span data-ttu-id="7436f-138">开始收集用户的反馈并允许众包确定用户的使用情况和贡献模式，以通知本文中建议的策略。</span><span class="sxs-lookup"><span data-stu-id="7436f-138">Begin to collect feedback from the users and allow crowdsourcing to determine the usage and contribution patterns of your users to inform the strategies suggested in this article.</span></span>

<span data-ttu-id="7436f-139">必须认识到，系统将识别 AI 建议和人工设计发布的主题，并同时向所有用户显示这些主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-139">It's important to recognize that the system will identify and show both AI-suggested and human-curated published topics to all users.</span></span> <span data-ttu-id="7436f-140">但是，这并不意味着将向所有最终用户显示每个建议的主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-140">However, this doesn't mean that every suggested topic will be shown to all end users.</span></span> <span data-ttu-id="7436f-141">就地安全设置将只显示每个员工根据对内容本身设置的权限可以访问的主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-141">The security settings in place will show only the topics that each employee can access based on the permissions that are set on the content itself.</span></span>

<span data-ttu-id="7436f-142">作为有权查看"管理主题"页的知识管理员，你可能会看到更多主题列出，因为您自己的提升的权限取决于您在组织中的角色和访问级别。</span><span class="sxs-lookup"><span data-stu-id="7436f-142">As a knowledge manager with permissions to view the **Manage topics** page, you might see a much larger number of topics listed because of your own elevated permissions, depending on your role in the organization and level of access.</span></span> <span data-ttu-id="7436f-143">你还将有权访问允许查看单个位置中列出的主题的视图，而不是使用突出显示或搜索来访问这些视图。</span><span class="sxs-lookup"><span data-stu-id="7436f-143">You'll also have access to views that allow you see topics listed in a single location rather than accessing them by using highlights or search.</span></span>

<span data-ttu-id="7436f-144">此外，大多数用户将查看的主题百分比可能较小，由于权限，查看频率会少得多的更多主题集。</span><span class="sxs-lookup"><span data-stu-id="7436f-144">In addition, there is likely a smaller percentage of topics that will be viewed by most users and a larger set of more topics that will be seen much less frequently due to permissions.</span></span> <span data-ttu-id="7436f-145">因此，首先关注对组织最重要的主题以及最可能更宽泛地看到的主题是一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="7436f-145">As a result, it is good to first focus any curation tasks on the topics that are the most important for your organization and that are the most likely to be seen more broadly.</span></span>

<span data-ttu-id="7436f-146">本文介绍一些用于管理的策略。</span><span class="sxs-lookup"><span data-stu-id="7436f-146">This article covers a few strategies for curation.</span></span> <span data-ttu-id="7436f-147">这些策略可能意味着不频繁或不常用的主题可能并非由知识经理全面制定。</span><span class="sxs-lookup"><span data-stu-id="7436f-147">These strategies might mean that the less frequent or less common topics might not be fully curated by knowledge managers.</span></span> <span data-ttu-id="7436f-148">但是，这些建议的主题仍很有用，可以提供见解或指向某人的指针，从而节省员工查找起点的时间。</span><span class="sxs-lookup"><span data-stu-id="7436f-148">However, these suggested topics remain useful and can provide insight or a pointer to a person, which can save an employee hours of looking for a starting point.</span></span> <span data-ttu-id="7436f-149">允许对主题进行众包更新非常有益，并且可为不太常见的主题提供更多内容和覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="7436f-149">Allowing crowdsourced updates to topics is beneficial and provides more content and coverage for the less common topics.</span></span>

<span data-ttu-id="7436f-150">本文提供了一些指导和最佳做法，用于主题管理和设计。</span><span class="sxs-lookup"><span data-stu-id="7436f-150">This article provides some guidance and best practices to approach topic management and curation.</span></span>

## <a name="understanding-suggested-topics"></a><span data-ttu-id="7436f-151">了解建议的主题</span><span class="sxs-lookup"><span data-stu-id="7436f-151">Understanding suggested topics</span></span>

<span data-ttu-id="7436f-152">当 AI 发现主题时，将在"管理主题"页面上和向用户显示的主题卡片中将主题标记为"建议主题"。</span><span class="sxs-lookup"><span data-stu-id="7436f-152">When topics are discovered by AI, they're marked as a **Suggested Topic**, both on the **Manage topics** page, and in the topic cards that are presented to users.</span></span> <span data-ttu-id="7436f-153">任何未标记为已删除的主题都会显示给用户，其中包括已确认、已发布和推荐的主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-153">Any topic that hasn't been marked as removed will be shown to users—this includes confirmed, published, and suggested topics.</span></span> <span data-ttu-id="7436f-154">最终用户可以使用所有三种状态的主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-154">Topics in all three states are available to end users.</span></span>

<span data-ttu-id="7436f-155">在主题卡片或页面中，我们使用各种提示来显示 AI 是如何生成信息的。</span><span class="sxs-lookup"><span data-stu-id="7436f-155">Within a topic card or page, we use various cues to show how the AI has generated the information.</span></span> <span data-ttu-id="7436f-156">系统主要通过内容本身使用各种证据来添加资源。</span><span class="sxs-lookup"><span data-stu-id="7436f-156">The system uses a variety of evidence to add the resources, primarily through the content itself.</span></span>

- <span data-ttu-id="7436f-157">标签显示建议了主题，并且该主题是由 Viva 主题发现的。</span><span class="sxs-lookup"><span data-stu-id="7436f-157">Labels show that a topic is suggested and that it was discovered by Viva Topics.</span></span>  

   ![显示建议的主题的示例卡片，其中包括建议的人和推荐的资源。](../media/knowledge-management/scale-topics-sample-card-suggested-topic.png)

- <span data-ttu-id="7436f-159">通过指定定义的来源来说明定义来自的卡片状态的信息。</span><span class="sxs-lookup"><span data-stu-id="7436f-159">Information on the card states where a definition has come from by specifying its source.</span></span>

- <span data-ttu-id="7436f-160">建议人员通过聚合使用主题证据编写或编辑文档的人派生。</span><span class="sxs-lookup"><span data-stu-id="7436f-160">Suggested people are derived by aggregating people who have written or edited documents with topic evidence.</span></span> <span data-ttu-id="7436f-161">如果用户写入的文档的标题中具有主题名称，并且该文档具有很多视图，则它可能只需要一个文档来建立相关人员。</span><span class="sxs-lookup"><span data-stu-id="7436f-161">If a person writes a document that has a topic name in the title, and that document has many views, it might only require one document to establish the person as related.</span></span> <span data-ttu-id="7436f-162">但是，在许多情况下，更多的证据更好，并且列出的人员已处理多个文档。</span><span class="sxs-lookup"><span data-stu-id="7436f-162">However, in many cases more evidence is better, and people who are listed have worked on multiple documents.</span></span>  

   ![显示建议主题并包括建议人员、文件和页面的页面。](../media/knowledge-management/scale-topics-sample-page-suggested-topic.png)

- <span data-ttu-id="7436f-164">对于显示的文件和页面，系统会标识在文档中提及主题多少次，但还必须在标识对特定类型 (如项目或工作组) 的主题的引用的特定上下文中提及该主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-164">For the files and pages shown, the system identifies how many times the topic has been mentioned in the document, but the topic also must be mentioned in a specific context that identifies the reference to the topic of specific type (such as project or team).</span></span> <span data-ttu-id="7436f-165">这是 AI 的证据。</span><span class="sxs-lookup"><span data-stu-id="7436f-165">This is what counts as evidence for the AI.</span></span> <span data-ttu-id="7436f-166">系统还会考虑主题名称在文档标题、文档类型和其他分析功能（如视图视图） (出现) 。</span><span class="sxs-lookup"><span data-stu-id="7436f-166">The system also considers the occurrence of a topic name in the titles of documents, types of documents, and other analytics features (such as views).</span></span>

   ![显示"建议主题"的横幅图像和 Microsoft Viva 发现了此主题。](../media/knowledge-management/scale-topics-suggested-you-have-access.png)

   ![显示"建议主题"和"编辑此页面"描述你参与本主题的横幅的图像。](../media/knowledge-management/scale-topics-suggested-describe-your-involvement.png)

   ![显示"建议主题"的横幅图像，以及"如果可以添加已连接到该主题的人，则编辑此页面"的图像。](../media/knowledge-management/scale-topics-suggested-add-people.png)

<span data-ttu-id="7436f-170">这些属性演示了 AI 已添加内容，以及 AI 如何做出该决定。</span><span class="sxs-lookup"><span data-stu-id="7436f-170">These attributes demonstrate that the content has been added by AI, and how the AI has made that determination.</span></span>

### <a name="communication"></a><span data-ttu-id="7436f-171">通信</span><span class="sxs-lookup"><span data-stu-id="7436f-171">Communication</span></span>

<span data-ttu-id="7436f-172">在向用户传达 Viva 主题时，必须阐明 AI 建议的主题和内容及其特有等效内容的区别。</span><span class="sxs-lookup"><span data-stu-id="7436f-172">When communicating to your users about Viva Topics, it's important to clarify the difference between AI-suggested topics and content and their curated equivalents.</span></span>

<span data-ttu-id="7436f-173">作为读者，你应该以更重要的眼睛查看建议的主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-173">As a reader, you should view suggested topics with a more critical eye.</span></span> <span data-ttu-id="7436f-174">不应将它们视为组织真实性的权威来源。</span><span class="sxs-lookup"><span data-stu-id="7436f-174">They shouldn't be perceived as authoritative sources of organizational truth.</span></span> <span data-ttu-id="7436f-175">相反，它们是一种查找方法的工具，用于访问通过您有权访问的内容呈现的引文知识。</span><span class="sxs-lookup"><span data-stu-id="7436f-175">Rather, they're a way-finding tool to access tacit knowledge that is presented through the content that you have access to.</span></span> <span data-ttu-id="7436f-176">AI 已发现该主题，并且有足够的证据可以展示给你，但其价值尚未得到人员确认。</span><span class="sxs-lookup"><span data-stu-id="7436f-176">The AI has discovered the topic and has enough evidence to show it to you, but its value hasn't been confirmed by a person.</span></span>

### <a name="crowdsourced-controls"></a><span data-ttu-id="7436f-177">众源控件</span><span class="sxs-lookup"><span data-stu-id="7436f-177">Crowdsourced controls</span></span>

<span data-ttu-id="7436f-178">建议的主题可以通过浏览页面和通过有关该主题的众包反馈进行改进。</span><span class="sxs-lookup"><span data-stu-id="7436f-178">Suggested topics can be improved by curation of the page and through crowdsourced feedback on the topic.</span></span>

<span data-ttu-id="7436f-179">当用户与建议的主题交互时，在 UI 中可能会询问他们一个简单的问题。</span><span class="sxs-lookup"><span data-stu-id="7436f-179">When users interact with a suggested topic, they might be asked a simple question in the UI.</span></span> <span data-ttu-id="7436f-180">例如： *本主题与页面相关吗？*</span><span class="sxs-lookup"><span data-stu-id="7436f-180">For example: *Was this topic relevant to the page?*</span></span> <span data-ttu-id="7436f-181">*此人是否与主题相关？*</span><span class="sxs-lookup"><span data-stu-id="7436f-181">*Is this person relevant for the topic?*</span></span> <span data-ttu-id="7436f-182">*此定义准确吗？*</span><span class="sxs-lookup"><span data-stu-id="7436f-182">*Was this definition accurate?*</span></span> <span data-ttu-id="7436f-183">通过使用对此类问题的反馈，主题的准确性可以增加，而无需指定个人来选择页面。</span><span class="sxs-lookup"><span data-stu-id="7436f-183">By using the feedback to such questions, the accuracy of the topics can increase without the need for a named individual to curate the page.</span></span>

<span data-ttu-id="7436f-184">主题中心的主页是收集有关建议主题的反馈的另一个位置。</span><span class="sxs-lookup"><span data-stu-id="7436f-184">The home page of a topic center is another location where feedback on suggested topics is gathered.</span></span> <span data-ttu-id="7436f-185">在主题中心，用户可以查看已与其关联的主题，并可以选择确认此关联或将其删除。</span><span class="sxs-lookup"><span data-stu-id="7436f-185">In the topic center, a user can see the topics that they have been associated with and are given the option to either confirm this association or have it removed.</span></span>

   ![主题中心的示例，显示建议的主题，以便用户确认或删除其与建议主题的连接。](../media/knowledge-management/scale-topics-topic-center-confirm-connections.png)

<span data-ttu-id="7436f-187">当你允许广泛的众包主题时，应考虑以下因素：</span><span class="sxs-lookup"><span data-stu-id="7436f-187">When you allow broad crowdsourcing of topics, you should consider the following factors:</span></span>

-   <span data-ttu-id="7436f-188">用户将在主题 **页面上** 看到"编辑"选项，并可以与其他新式页面相同的体验编辑SharePoint页面。</span><span class="sxs-lookup"><span data-stu-id="7436f-188">Users will see the **Edit** option on topic pages and can edit the pages in the same experience as other modern SharePoint pages.</span></span>

-   <span data-ttu-id="7436f-189">无法 **删除一** 些建议的主题 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="7436f-189">Some **Suggested Topic** web parts can't be removed.</span></span> <span data-ttu-id="7436f-190">主题名称、备用名称、定义、建议人员以及建议的资源无法删除。</span><span class="sxs-lookup"><span data-stu-id="7436f-190">The topic name, alternate names, definition, suggested people, and suggested resources can't be removed.</span></span>

-   <span data-ttu-id="7436f-191">可能需要一些时间，才能将已发布的建议或已确认主题移至"管理主题"页上的"**已发布"** 列表。 </span><span class="sxs-lookup"><span data-stu-id="7436f-191">It can take some time for a suggested or confirmed topic that has been published to be moved to the **Published** list on the **Manage topics** page.</span></span>

    -   <span data-ttu-id="7436f-192">主题在搜索、突出显示、井号或批注中的显示估计时间为 2 小时。</span><span class="sxs-lookup"><span data-stu-id="7436f-192">The estimated time for a topic to appear in search, highlights, hashtags, or annotations is 2 hours.</span></span>

    -   <span data-ttu-id="7436f-193">在大多数情况下，在"托管主题"页上的"已发布"列表中显示主题的估计时间不超过 24 小时。</span><span class="sxs-lookup"><span data-stu-id="7436f-193">The estimated time for a topic to appear in **Published** list on the **Managed topics** page is no more than 24 hours in most cases.</span></span> <span data-ttu-id="7436f-194">你应该在 2 小时内看到它们，但由于每 24 小时有一次完全同步，因此等待不应超过 24 小时。</span><span class="sxs-lookup"><span data-stu-id="7436f-194">You should see them within 2 hours, but because there's a full sync every 24 hours, the wait shouldn't be longer than 24 hours.</span></span>

-   <span data-ttu-id="7436f-195">用户可能会将已发布的主题保留为签出或编辑状态。</span><span class="sxs-lookup"><span data-stu-id="7436f-195">It's possible that a user might leave a published topic in a checked-out or editing state.</span></span> <span data-ttu-id="7436f-196">知识经理可以在主题中心的"页面库"中查看这些页面，并可以放弃用户所做的更改以重新发布主题，也可以联系该用户以请求签入主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-196">A knowledge manager can see these in the Pages Library of the topic center and either can discard the user's changes to republish the topic or contact that user to request that they check in the topic.</span></span>

### <a name="topic-visibility-and-content-is-based-on-a-users-permissions"></a><span data-ttu-id="7436f-197">主题可见性和内容基于用户的权限</span><span class="sxs-lookup"><span data-stu-id="7436f-197">Topic visibility and content is based on a user's permissions</span></span>

<span data-ttu-id="7436f-198">当您以知识管理员角色查看建议的主题列表时，请记住，建议主题上的内容将基于权限动态显示。</span><span class="sxs-lookup"><span data-stu-id="7436f-198">When you review the list of suggested topics as a knowledge manager, keep in mind that the contents on a suggested topic will be dynamically based on permissions.</span></span> <span data-ttu-id="7436f-199">向您显示的建议内容和人员可能与向任何用户或其他知识经理呈现的内容和人员不同。</span><span class="sxs-lookup"><span data-stu-id="7436f-199">The suggested content and people that are shown to you might not be the same as those who are presented to any user or another knowledge manager.</span></span>

<span data-ttu-id="7436f-200">根据查看与主题关联的内容的权限，每个用户可能会看到一组不同的建议资源、人员、替代名称和定义。</span><span class="sxs-lookup"><span data-stu-id="7436f-200">Based on the permissions to view content that is associated with a topic, each user might see a different set of suggested resources, people, alternative names, and definition.</span></span>

## <a name="prioritize-the-topics-for-curation"></a><span data-ttu-id="7436f-201">确定主题的优先级</span><span class="sxs-lookup"><span data-stu-id="7436f-201">Prioritize the topics for curation</span></span>

<span data-ttu-id="7436f-202">可以使用以下策略来确定可能非常突出的主题，因此是适合进行选选的主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-202">You can use the following strategies to identify topics that are likely to be prominent, and therefore are good candidates for curation.</span></span> 

### <a name="taxonomies"></a><span data-ttu-id="7436f-203">分类</span><span class="sxs-lookup"><span data-stu-id="7436f-203">Taxonomies</span></span>

<span data-ttu-id="7436f-204">使用现有分类可以提供用户可能非常突出的主题列表。</span><span class="sxs-lookup"><span data-stu-id="7436f-204">Using existing taxonomies can provide a list of topics that are likely to be prominent for users.</span></span> <span data-ttu-id="7436f-205">例如，这些可能是：</span><span class="sxs-lookup"><span data-stu-id="7436f-205">For example, these could be:</span></span>

-   <span data-ttu-id="7436f-206">组织提供的产品和服务</span><span class="sxs-lookup"><span data-stu-id="7436f-206">Products and services that your organization provides</span></span>

-   <span data-ttu-id="7436f-207">Teams组织中工作</span><span class="sxs-lookup"><span data-stu-id="7436f-207">Teams in your organization</span></span>

-   <span data-ttu-id="7436f-208">高配置文件项目</span><span class="sxs-lookup"><span data-stu-id="7436f-208">High-profile projects</span></span>

<span data-ttu-id="7436f-209">还可以在部门或功能级别采用此方法，与了解组织该领域的行业专家合作。</span><span class="sxs-lookup"><span data-stu-id="7436f-209">This approach could also be taken on a departmental or functional level, with subject-matter experts who understand that area of your organization.</span></span> <span data-ttu-id="7436f-210">目标不是让他们查看所选内容或所有主题。</span><span class="sxs-lookup"><span data-stu-id="7436f-210">The goal isn't to have them review a selection or all of the topics.</span></span> <span data-ttu-id="7436f-211">相反，他们利用自己的域专业知识来指导选择性选择。</span><span class="sxs-lookup"><span data-stu-id="7436f-211">Rather, they bring their own domain expertise to guide selective curation.</span></span>

### <a name="search"></a><span data-ttu-id="7436f-212">搜索</span><span class="sxs-lookup"><span data-stu-id="7436f-212">Search</span></span>

<span data-ttu-id="7436f-213">常见搜索词通常作为主题发现。</span><span class="sxs-lookup"><span data-stu-id="7436f-213">Common search terms are often discovered as topics.</span></span> <span data-ttu-id="7436f-214">通过使用 [Microsoft 搜索中排名居](/sharepoint/view-search-usage-reports)首的查询报告，您可以确定组织中最常见的搜索词。</span><span class="sxs-lookup"><span data-stu-id="7436f-214">By using the [top query reports in Microsoft Search](/sharepoint/view-search-usage-reports), you can identify the most frequent search terms in your organization.</span></span> <span data-ttu-id="7436f-215">如果已发现这些术语的主题，则它们适合进行选择。</span><span class="sxs-lookup"><span data-stu-id="7436f-215">If topics have been discovered for these terms, they're good candidates for curation.</span></span> <span data-ttu-id="7436f-216">这些主题可在 Microsoft 搜索中作为答案卡片显示。</span><span class="sxs-lookup"><span data-stu-id="7436f-216">These topics can be presented as answer cards in Microsoft Search.</span></span>

<span data-ttu-id="7436f-217">如果当前使用的是 Microsoft [搜索书签，](/microsoftsearch/manage-bookmarks)请考虑使用主题替换其中哪一个。</span><span class="sxs-lookup"><span data-stu-id="7436f-217">If you're currently using [Microsoft Search bookmarks](/microsoftsearch/manage-bookmarks), consider which of these can be replaced with a topic.</span></span> <span data-ttu-id="7436f-218">书签应答卡包含标题、说明和 URL。</span><span class="sxs-lookup"><span data-stu-id="7436f-218">A bookmark answer card contains a title, description, and URL.</span></span> <span data-ttu-id="7436f-219">在某些情况下，主题卡片可能更适用于用户，主题卡片还显示资源和人员。</span><span class="sxs-lookup"><span data-stu-id="7436f-219">In some circumstances, a topic card might be more useful to a user, and a topic card also shows resources and people.</span></span>

<span data-ttu-id="7436f-220">在用户的搜索体验中，当用户搜索"旅行"等字词时，搜索结果将按以下优先级顺序显示在 Microsoft 搜索中：</span><span class="sxs-lookup"><span data-stu-id="7436f-220">In the user's search experience, when a user searches for a term like *travel*, search results are displayed in the following priority order in Microsoft Search:</span></span>

1.  <span data-ttu-id="7436f-221">已发布或已确认的主题</span><span class="sxs-lookup"><span data-stu-id="7436f-221">Published or confirmed topics</span></span>

2.  <span data-ttu-id="7436f-222">书签</span><span class="sxs-lookup"><span data-stu-id="7436f-222">Bookmarks</span></span>

3.  <span data-ttu-id="7436f-223">建议的主题</span><span class="sxs-lookup"><span data-stu-id="7436f-223">Suggested topics</span></span>

### <a name="impressions-and-quality-score"></a><span data-ttu-id="7436f-224">展示次数和质量分数</span><span class="sxs-lookup"><span data-stu-id="7436f-224">Impressions and quality score</span></span>

<span data-ttu-id="7436f-225">展示 [次数](manage-topics.md#impressions) 和质量 [分数是](manage-topics.md#quality-score) 了解主题行为的重要指标。</span><span class="sxs-lookup"><span data-stu-id="7436f-225">The [impressions](manage-topics.md#impressions) count and [quality score](manage-topics.md#quality-score) are important metrics for understanding the behavior of a topic.</span></span> <span data-ttu-id="7436f-226">当只有知识经理或 IT 团队有权访问主题时，这些指标的值将受到限制。</span><span class="sxs-lookup"><span data-stu-id="7436f-226">The value of these metrics will be limited when only knowledge managers or IT teams have access to topics.</span></span> <span data-ttu-id="7436f-227">向试点用户组公开主题将生成更具有代表性的测量数据。</span><span class="sxs-lookup"><span data-stu-id="7436f-227">Exposing topics to a pilot group of users will generate more representative data for these measures.</span></span>

<span data-ttu-id="7436f-228">具有高印象计数的主题可能更频繁地交互。</span><span class="sxs-lookup"><span data-stu-id="7436f-228">Topics with a high impression count are likely to be more frequently interacted with.</span></span> <span data-ttu-id="7436f-229">这些主题的质量分数将说明这些主题的丰富内容。</span><span class="sxs-lookup"><span data-stu-id="7436f-229">The quality score for these topics will give a sense of how rich those topics are.</span></span> <span data-ttu-id="7436f-230">具有高印象计数和低质量分数的主题是适合进行建议的目标。</span><span class="sxs-lookup"><span data-stu-id="7436f-230">Topics with a high impression count and a low quality score are good targets for curation.</span></span>

### <a name="key-terms-from-the-information-architecture-of-larger-organizational-sites"></a><span data-ttu-id="7436f-231">大型组织网站的信息体系结构中的关键术语</span><span class="sxs-lookup"><span data-stu-id="7436f-231">Key terms from the information architecture of larger organizational sites</span></span>

<span data-ttu-id="7436f-232">贵组织中较大的门户网站可能投入了一些时间来组织其信息体系结构以及其网站围绕其业务部门、产品线、主要项目等关键主题领域的导航。</span><span class="sxs-lookup"><span data-stu-id="7436f-232">Larger portal sites within your organization might have invested time in organizing their information architecture and the navigation of their site around key topic areas for their business units, product lines, major projects, and so on.</span></span> <span data-ttu-id="7436f-233">查看这些术语以及确定和选择这些术语的主题可帮助查找有关这些方面的信息的用户。</span><span class="sxs-lookup"><span data-stu-id="7436f-233">Reviewing these terms and identifying and curating topics for these terms can help users who are looking for information on these areas.</span></span>

### <a name="leverage-internal-knowledge-bases-or-wiki-sites"></a><span data-ttu-id="7436f-234">利用内部知识库或 Wiki 网站</span><span class="sxs-lookup"><span data-stu-id="7436f-234">Leverage internal knowledge bases or wiki sites</span></span>

<span data-ttu-id="7436f-235">如果您的组织已投资知识库或 Wiki 网站，这些网站可以提供用于初始设计工作的主题列表。</span><span class="sxs-lookup"><span data-stu-id="7436f-235">If your organization has invested in knowledge bases or wiki sites, these can provide a list of topics to use for your initial curation efforts.</span></span> <span data-ttu-id="7436f-236">如果它们特别大，请选择查看量最多的或编辑过的主题作为起点。</span><span class="sxs-lookup"><span data-stu-id="7436f-236">If they're particularly large, select the most viewed or edited topics as a starting point.</span></span>

## <a name="see-also"></a><span data-ttu-id="7436f-237">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7436f-237">See also</span></span>

[<span data-ttu-id="7436f-238">在主题中心管理主题</span><span class="sxs-lookup"><span data-stu-id="7436f-238">Manage topics in the topic center</span></span>](manage-topics.md)

[<span data-ttu-id="7436f-239">主题中心概述</span><span class="sxs-lookup"><span data-stu-id="7436f-239">Topic center overview</span></span>](topic-center-overview.md)
