---
title: '知识管理概述 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 项目 Cortex 中的知识管理概述。
ms.openlocfilehash: d422b54bb7991fb5fd61465cd0428ab586d10bf5
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906937"
---
# <a name="knowledge-management-overview-preview"></a><span data-ttu-id="30397-103">知识管理概述 (预览) </span><span class="sxs-lookup"><span data-stu-id="30397-103">Knowledge management Overview (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="30397-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="30397-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="30397-105">[了解更多关于 Project Cortex的信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="30397-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="30397-106">知识管理使用 Microsoft AI 技术、Microsoft 365、Delve、搜索以及其他组件和服务在 Microsoft 365 环境中构建一个知识网络。</span><span class="sxs-lookup"><span data-stu-id="30397-106">Knowledge management uses Microsoft AI technology, Microsoft 365, Delve, Search, and other components and services to build a knowledge network in your Microsoft 365 environment.</span></span> 

   ![知识管理流程](../media/content-understanding/knowledge-management-flowchart.png) </br> 

<span data-ttu-id="30397-108">其目标是将信息传递给用户日常使用的应用程序中的用户，如 Outlook、团队和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="30397-108">It's goal is to deliver information to you users in apps they use everyday, such as Outlook, Teams, and SharePoint.</span></span>

<span data-ttu-id="30397-109">例如，用户可以在其电子邮件、SharePoint 网站或团队对话中看到不熟悉的术语，他们希望了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="30397-109">For example, users see unfamiliar terms in their emails, SharePoint sites, or in Teams conversations, that they want to know more about.</span></span> <span data-ttu-id="30397-110">知识管理使用 AI 自动搜索和标识这些主题，并编译有关这些 **主题** 的信息，如简短说明、主题的主题专家以及与之相关的网站、文件和页面。</span><span class="sxs-lookup"><span data-stu-id="30397-110">Knowledge management uses AI to automatically searches for and identifies these **topics** , and compiles information about them, such as a short description, subject matter experts on the topic, and sites, files, and pages that are related to it.</span></span> <span data-ttu-id="30397-111">您可以根据需要选择更新主题信息。</span><span class="sxs-lookup"><span data-stu-id="30397-111">You can choose to update the topic information as needed.</span></span> <span data-ttu-id="30397-112">然后，您可以让这些主题对您的用户可用，这意味着对于在 Outlook、团队和 SharePoint 等应用程序中显示的每个主题实例，都会突出显示该文本。</span><span class="sxs-lookup"><span data-stu-id="30397-112">You can then make the topics available to your users, which means that for every instance of the topic that appears in apps such as Outlook, Teams, and SharePoint, the text will be highlighted.</span></span> <span data-ttu-id="30397-113">用户可以选择通过主题详细信息来详细了解主题。</span><span class="sxs-lookup"><span data-stu-id="30397-113">Users can choose to select the topic to learn more about it through the topic details.</span></span>


## <a name="topic-indexing"></a><span data-ttu-id="30397-114">主题索引</span><span class="sxs-lookup"><span data-stu-id="30397-114">Topic indexing</span></span>

<span data-ttu-id="30397-115">知识管理使用 Microsoft AI 技术来识别 Office 365 环境中的 **主题** 。</span><span class="sxs-lookup"><span data-stu-id="30397-115">Knowledge Management uses Microsoft AI technology to identify **topics** in your Office 365 environment.</span></span>

<span data-ttu-id="30397-116">主题是非常重要或重要的短语或术语。</span><span class="sxs-lookup"><span data-stu-id="30397-116">A topic is a phrase or term that is organizationally significant or important.</span></span> <span data-ttu-id="30397-117">它具有对组织的特定含义，并具有与之相关的资源，可帮助用户了解其内容并查找有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="30397-117">It has a specific meaning to the organization, and has resources related to it that can help people understand what it is and find more information about it.</span></span>

<span data-ttu-id="30397-118">在标识主题时，将为其创建一个 **主题页面** ，其中包含通过主题索引收集的信息，例如：</span><span class="sxs-lookup"><span data-stu-id="30397-118">When a topic is identified, a **topic page** is created for it that contains information that was gathered through topic indexing, such as:</span></span>

- <span data-ttu-id="30397-119">替代名称和/或首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="30397-119">Alternate names and/or acronyms.</span></span>
- <span data-ttu-id="30397-120">主题的简短说明。</span><span class="sxs-lookup"><span data-stu-id="30397-120">A short description of the topic.</span></span>
- <span data-ttu-id="30397-121">可能熟悉主题的用户。</span><span class="sxs-lookup"><span data-stu-id="30397-121">Users who might be knowledgeable about the topic.</span></span>
- <span data-ttu-id="30397-122">与主题相关的文件、页面和网站。</span><span class="sxs-lookup"><span data-stu-id="30397-122">Files, pages, and sites that are related to the topic.</span></span>


## <a name="topic-discovery"></a><span data-ttu-id="30397-123">主题发现</span><span class="sxs-lookup"><span data-stu-id="30397-123">Topic discovery</span></span>
<span data-ttu-id="30397-124">当 SharePoint 新闻和页面上的内容中提到主题时，您会看到它突出显示。</span><span class="sxs-lookup"><span data-stu-id="30397-124">When a topic is mentioned in content on SharePoint news and pages, you'll see it highlighted.</span></span> <span data-ttu-id="30397-125">从突出显示内容中打开主题摘要。</span><span class="sxs-lookup"><span data-stu-id="30397-125">Open the topic summary from the highlight.</span></span> <span data-ttu-id="30397-126">从摘要的标题中打开主题详细信息。</span><span class="sxs-lookup"><span data-stu-id="30397-126">Open the topic details from the title of the summary.</span></span> <!--(msg for Efren: not sure if I should use discovery for this; we use discovered in-product for indexing?)--> <span data-ttu-id="30397-127">可以自动识别提到的主题，也可以通过页面作者直接引用主题的方式将其添加到页面中。</span><span class="sxs-lookup"><span data-stu-id="30397-127">The mentioned topic could be identified automatically or have been added to the page with a direct reference to the topic by the page author.</span></span>

<span data-ttu-id="30397-128">您还可以通过 Microsoft Search 发现主题。</span><span class="sxs-lookup"><span data-stu-id="30397-128">You can also discover topics through Microsoft Search.</span></span>


## <a name="topic-management"></a><span data-ttu-id="30397-129">主题管理</span><span class="sxs-lookup"><span data-stu-id="30397-129">Topic management</span></span>

<span data-ttu-id="30397-130">主题管理是在组织的 **主题中心** 完成的。</span><span class="sxs-lookup"><span data-stu-id="30397-130">Topic management is done in your organization's **topic center**.</span></span> <span data-ttu-id="30397-131">主题中心网站是在安装过程中创建的，可充当贵组织的知识中心。</span><span class="sxs-lookup"><span data-stu-id="30397-131">The topic center site is created during setup and serves as your center of knowledge for your organization.</span></span> <span data-ttu-id="30397-132">它将包含在您的环境中发现的所有主题的列表，以及为这些主题创建的所有主题页面。</span><span class="sxs-lookup"><span data-stu-id="30397-132">It will contain a list of all topics that were discovered in your environment, as well as all topic pages that were created for these topics.</span></span> 

<span data-ttu-id="30397-133">提供正确权限的用户将能够在主题中心中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="30397-133">Users who are provided the correct permissions will be able to do the following in the topic center:</span></span>

- <span data-ttu-id="30397-134">确认或拒绝在租户中发现的主题。</span><span class="sxs-lookup"><span data-stu-id="30397-134">Confirm or reject topics that were discovered in your tenant.</span></span>
- <span data-ttu-id="30397-135">根据需要手动创建新主题 (例如，如果未提供足够的信息，则无法通过 AI) 发现它。</span><span class="sxs-lookup"><span data-stu-id="30397-135">Create new topics manually as needed (for example, if not enough information was provided for it to be discovered through AI).</span></span>
- <span data-ttu-id="30397-136">编辑现有主题页面。</span><span class="sxs-lookup"><span data-stu-id="30397-136">Edit existing topic pages.</span></span></br>

<span data-ttu-id="30397-137">有关详细信息，请参阅 [主题 center 中的使用主题一主题](work-with-topics.md) 。</span><span class="sxs-lookup"><span data-stu-id="30397-137">See [Work with topic in the topic center](work-with-topics.md) for more information.</span></span>  


## <a name="admin-controls"></a><span data-ttu-id="30397-138">管理控件</span><span class="sxs-lookup"><span data-stu-id="30397-138">Admin controls</span></span>

<span data-ttu-id="30397-139">Microsoft 365 管理中心中的管理员控件允许您管理您的知识网络。</span><span class="sxs-lookup"><span data-stu-id="30397-139">Admin controls in the Microsoft 365 admin center  allow you to manage your knowledge network.</span></span> <span data-ttu-id="30397-140">它们允许 Microsoft 365 全局或 SharePoint 管理员执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="30397-140">They allow a Microsoft 365 global or SharePoint admin to:</span></span>

- <span data-ttu-id="30397-141">控制允许组织中的哪些用户查看其客户端应用程序或 SharePoint 搜索结果中的主题。</span><span class="sxs-lookup"><span data-stu-id="30397-141">Control which users in your organization are allowed to see topics in their client apps or in SharePoint search results.</span></span>
- <span data-ttu-id="30397-142">控制将对哪些 SharePoint 网站进行爬网以搜索主题。</span><span class="sxs-lookup"><span data-stu-id="30397-142">Control which SharePoint sites will be crawled to search for topics.</span></span>
- <span data-ttu-id="30397-143">将主题发现配置为排除您不想成为主题的特定术语。</span><span class="sxs-lookup"><span data-stu-id="30397-143">Configure topic discovery to exclude specific terms that you don't want to be a topic.</span></span>
- <span data-ttu-id="30397-144">控制哪些用户可以确认或拒绝主题中心中的主题。</span><span class="sxs-lookup"><span data-stu-id="30397-144">Control which users can to confirm or reject topics in the topic center.</span></span>
- <span data-ttu-id="30397-145">控制哪些用户可以在主题中心创建和编辑主题。</span><span class="sxs-lookup"><span data-stu-id="30397-145">Control which users can create and edit topics in the topic center.</span></span>

<span data-ttu-id="30397-146">有关详细信息，请参阅 [管理您的知识网络](manage-knowledge-network.md) 。</span><span class="sxs-lookup"><span data-stu-id="30397-146">See [Manage your knowledge network](manage-knowledge-network.md) for more information.</span></span> 

## <a name="topic-curation--feedback"></a><span data-ttu-id="30397-147">主题 curation & 反馈</span><span class="sxs-lookup"><span data-stu-id="30397-147">Topic curation & feedback</span></span>

<span data-ttu-id="30397-148">在环境中发生更改时，AI 将持续提供有关改进主题的建议。</span><span class="sxs-lookup"><span data-stu-id="30397-148">AI will continually work to provide you suggestions to improve your topics as changes occur in your environment.</span></span>

<span data-ttu-id="30397-149">允许 access 查看其日常工作中的主题的用户可以提出改进这些主题的建议。</span><span class="sxs-lookup"><span data-stu-id="30397-149">Users who you allow access to see topics in their daily work are allowed to make suggestions to improve them.</span></span> <span data-ttu-id="30397-150">例如，如果用户查看主题页面并查看不正确或需要添加的信息，主题页面上的链接使他们能够直接编辑信息。</span><span class="sxs-lookup"><span data-stu-id="30397-150">For example, if a user views the topic page and sees information that is incorrect or needs to be added, a link on the topic page allows them to edit the information directly.</span></span> <span data-ttu-id="30397-151">另一个示例是，如果用户在 SharePoint 新闻页面上查看突出显示项，则会发现询问是否突出显示或建议的主题是否适用于您的组织的问题。</span><span class="sxs-lookup"><span data-stu-id="30397-151">Another example, if a user views a a highlight on a SharePoint news page, you will find questions asking whether or not the highlight is appropriate or the suggested topic is appropriate for your organization.</span></span> <span data-ttu-id="30397-152">您的回答将帮助您确定主题摘要和主题详细信息中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="30397-152">Your answer will help determine what's shown on topic summaries and in topic details.</span></span>

<span data-ttu-id="30397-153">此外，具有适当权限的用户可以标记与主题相关的 Yammer 对话等项目，并将其添加到特定主题中。</span><span class="sxs-lookup"><span data-stu-id="30397-153">Additionally, users with proper permissions can tag items such as Yammer conversation that are relevant to a topic, and add them to a specific topic.</span></span> <!--(msg for Efren: changed to Yammer, because we will not have shipped Teams yet)-->


## <a name="see-also"></a><span data-ttu-id="30397-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30397-154">See also</span></span>
[<span data-ttu-id="30397-155">设置知识管理</span><span class="sxs-lookup"><span data-stu-id="30397-155">Set up knowledge management</span></span>](set-up-knowledge-network.md)</br>
[<span data-ttu-id="30397-156">主题中心概述</span><span class="sxs-lookup"><span data-stu-id="30397-156">Topic center overview</span></span>](topic-center-overview.md)
