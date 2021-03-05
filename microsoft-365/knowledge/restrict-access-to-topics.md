---
title: 限制对 Microsoft Viva 主题中主题的访问
description: 如何排除主题以防止被发现。
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
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: b8c49c96ace14ac1ba03411b5670d8e77268109a
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453904"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="a37df-103">限制对 Microsoft Viva 主题中主题的访问</span><span class="sxs-lookup"><span data-stu-id="a37df-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="a37df-104">在 Microsoft Viva 中，贵组织中的利益干系人可能希望确保不会发现特定主题，不会向许可用户公开这些主题。</span><span class="sxs-lookup"><span data-stu-id="a37df-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="a37df-105">例如，您可能正在处理一个您不想公开任何相关信息的项目。</span><span class="sxs-lookup"><span data-stu-id="a37df-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="a37df-106">虽然对网站、文件和其他资源的 Office 365 权限将阻止主题体验用户查看主题中的敏感信息，但还有其他安全措施来防止发现特定主题。</span><span class="sxs-lookup"><span data-stu-id="a37df-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="a37df-107">虽然知识管理员控制知识网络设置以防止发现主题，但知识管理员和其他利益干系人需要知道如何操作，以便可以协作工作。</span><span class="sxs-lookup"><span data-stu-id="a37df-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="a37df-108">本文介绍防止主题通过 AI 标识或在环境中作为附加安全保护措施进行查看的方法。</span><span class="sxs-lookup"><span data-stu-id="a37df-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="a37df-109">需要注意的是，在 Viva 主题中，不允许用户查看主题中不允许他们通过 Office 365 权限访问的内容。</span><span class="sxs-lookup"><span data-stu-id="a37df-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="a37df-110">即使用户能够查看主题，他们无权查看的 Office 365 文件、网站和页面也将不可见。</span><span class="sxs-lookup"><span data-stu-id="a37df-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="a37df-111">确保正确设置对敏感文件的权限应该是主要的安全保护措施。</span><span class="sxs-lookup"><span data-stu-id="a37df-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="a37df-112">阻止标识主题</span><span class="sxs-lookup"><span data-stu-id="a37df-112">Prevent topics from being identified</span></span>

<span data-ttu-id="a37df-113">知识管理员可以通过阻止在初始索引中发现特定主题来限制对特定主题的访问。</span><span class="sxs-lookup"><span data-stu-id="a37df-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="a37df-114">在 Microsoft 365 管理中心的知识库管理员设置中，有两种方法可以执行此任务。</span><span class="sxs-lookup"><span data-stu-id="a37df-114">There are two ways to do this task in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="a37df-115">[选择要从主题发现中排除的 SharePoint](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)网站：可以使用此设置阻止对特定 SharePoint 网站进行主题爬网。</span><span class="sxs-lookup"><span data-stu-id="a37df-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="a37df-116">[按名称排除](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)主题：管理员可以使用此设置阻止按名称发现特定主题。</span><span class="sxs-lookup"><span data-stu-id="a37df-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="a37df-117">在知识网络管理员设置中，管理员可以上载要排除在 CSV 文件中的主题列表。</span><span class="sxs-lookup"><span data-stu-id="a37df-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="a37df-118">可以排除与主题名称完全匹配或部分匹配的主题。</span><span class="sxs-lookup"><span data-stu-id="a37df-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="a37df-119">阻止特定用户查看主题</span><span class="sxs-lookup"><span data-stu-id="a37df-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="a37df-120">知识管理员还可以 [选择谁可以查看组织的主题](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)。</span><span class="sxs-lookup"><span data-stu-id="a37df-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="a37df-121">此设置允许你选择哪些许可用户可以查看所有主题。</span><span class="sxs-lookup"><span data-stu-id="a37df-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="a37df-122">例如，在试验环境中，您可能只希望允许一小组用户查看主题。</span><span class="sxs-lookup"><span data-stu-id="a37df-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="a37df-123">从查看中删除主题</span><span class="sxs-lookup"><span data-stu-id="a37df-123">Remove topics from being viewed</span></span>

<span data-ttu-id="a37df-124">知识经理可以选择 [删除主题](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) ，以便用户无法再看到它们。</span><span class="sxs-lookup"><span data-stu-id="a37df-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="a37df-125">在 **主题中心的**"管理主题"页上，知识经理可以选择拒绝特定主题以防止查看这些主题。</span><span class="sxs-lookup"><span data-stu-id="a37df-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="a37df-126">可以删除主题，无论主题是位于建议状态还是已确认状态。</span><span class="sxs-lookup"><span data-stu-id="a37df-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="a37df-127">删除的主题稍后可以添加回可查看主题（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="a37df-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="a37df-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a37df-128">See also</span></span>



  






