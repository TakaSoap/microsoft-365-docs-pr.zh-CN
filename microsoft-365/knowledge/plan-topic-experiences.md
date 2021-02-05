---
title: 规划 Microsoft Viva 主题
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 了解如何规划 Microsoft Viva 主题
ms.openlocfilehash: 65983f342b3277d33c7bfeb21d8481b1d3d5e817
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107950"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="9fc8c-103">规划 Microsoft Viva 主题</span><span class="sxs-lookup"><span data-stu-id="9fc8c-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="9fc8c-104">你可以控制主题在组织中是如何体验的。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="9fc8c-105">针对主题的规划决策可确保向用户显示高质量主题，并且他们有权使用和贡献知识。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="9fc8c-106">本文将介绍这些规划决策：</span><span class="sxs-lookup"><span data-stu-id="9fc8c-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="9fc8c-107">要针对主题对哪些 SharePoint 网站进行爬网</span><span class="sxs-lookup"><span data-stu-id="9fc8c-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="9fc8c-108">您希望从主题体验中排除的主题（如果有）</span><span class="sxs-lookup"><span data-stu-id="9fc8c-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="9fc8c-109">要向哪些用户显示主题</span><span class="sxs-lookup"><span data-stu-id="9fc8c-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="9fc8c-110">要向哪些用户授予在主题中心管理主题的权限</span><span class="sxs-lookup"><span data-stu-id="9fc8c-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="9fc8c-111">要授予在主题中心创建或编辑主题的权限的用户</span><span class="sxs-lookup"><span data-stu-id="9fc8c-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="9fc8c-112">要为主题中心命名的名称</span><span class="sxs-lookup"><span data-stu-id="9fc8c-112">What name you want to give your topic center</span></span>

<span data-ttu-id="9fc8c-113">将尊重数据的安全性和隐私，并且主题体验不会向用户授予对无权限文件的其他访问权限。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="9fc8c-114">作为规划过程的一部分，我们还建议你阅读 [Microsoft Viva](topic-experiences-security-privacy.md) 主题安全和隐私。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="9fc8c-115">要求</span><span class="sxs-lookup"><span data-stu-id="9fc8c-115">Requirements</span></span>

<span data-ttu-id="9fc8c-116">您必须是全局管理员或 SharePoint 管理员才能访问 Microsoft 365 管理中心并设置主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-116">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="9fc8c-117">将使用主题的所有用户都需要主题 **体验** 许可证。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="9fc8c-118">"设置 Microsoft Viva 主题"中介绍了 [分配许可证的内容](set-up-topic-experiences.md)。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="9fc8c-119">主题发现</span><span class="sxs-lookup"><span data-stu-id="9fc8c-119">Topic discovery</span></span>

<span data-ttu-id="9fc8c-120">主题发现设置指定哪些 SharePoint 网站用作主题源。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="9fc8c-121">您可以选择包括所有 SharePoint 网站、特定网站列表或不包含任何网站。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="9fc8c-122">我们建议你选择所有网站，以便主题体验可以发现大量适合你的用户的主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="9fc8c-123">设置主题时，可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="9fc8c-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="9fc8c-124">**所有网站**：组织的所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="9fc8c-125">这包括当前和将来的网站。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-125">This includes current and future sites.</span></span>
- <span data-ttu-id="9fc8c-126">**所有（所选网站除外**）：除您指定的站点之外的所有网站。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="9fc8c-127">将来创建的网站将包含为主题发现源。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="9fc8c-128">**仅选定网站**：仅指定网站。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="9fc8c-129">将来创建的网站不会作为主题发现源包含在内。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="9fc8c-130">**无网站**：不包括任何 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="9fc8c-131">如果选择"全部 **"（** 所选站点除外）或"仅选定网站"，可以上载包含站点列表的 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="9fc8c-132">如果你要执行试点并且希望包含有限数量的要启动的网站，这些选项将非常有用。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="9fc8c-133">你可以复制下面的 .csv 模板：</span><span class="sxs-lookup"><span data-stu-id="9fc8c-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="9fc8c-134">我们不建议选择"否 **"网站** ，因为它会阻止自动创建或更新主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="9fc8c-135">但是，如果要设置主题，稍后再添加网站，可以选择此选项。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="9fc8c-136">建议为用户或知识管理员创建一个流程，以请求从主题发现中删除各个网站（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="9fc8c-137">用户权限</span><span class="sxs-lookup"><span data-stu-id="9fc8c-137">User permissions</span></span>

<span data-ttu-id="9fc8c-138">您指定的用户权限决定了组织中哪些人员与主题进行交互以及他们可以做什么。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="9fc8c-139">*管理主题*</span><span class="sxs-lookup"><span data-stu-id="9fc8c-139">*Manage topics*</span></span>

<span data-ttu-id="9fc8c-140">知识管理人员监督信息的质量、信息的结构化方式以及组织的其他最佳做法。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="9fc8c-141">他们可以确认和拒绝主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="9fc8c-142">虽然您可以指定各个主题管理员，但我们建议您创建一个安全组 (或使用包含要成为知识管理员) 的现有组。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="9fc8c-143">您可以在安装过程中指定此安全组。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="9fc8c-144">*创建和编辑主题*</span><span class="sxs-lookup"><span data-stu-id="9fc8c-144">*Create and edit topics*</span></span>

<span data-ttu-id="9fc8c-145">主题参与者是组织中冠军和主题专家。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="9fc8c-146">他们可以创建和编辑主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-146">They can create and edit topics.</span></span> 

<span data-ttu-id="9fc8c-147">我们建议您允许组织中的每个人创建和编辑主题，因为当所有用户都可以共享信息时，主题体验效果最佳。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="9fc8c-148">如果要将创建和编辑主题限制为特定人员或组，请为这些人员或组创建一个安全组，并指定它在安装过程中。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="9fc8c-149">你可以选择不允许任何人参与主题，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="9fc8c-150">如果选择此选项，知识管理员仍可以编辑和创建主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-150">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="9fc8c-151">*主题查看者*</span><span class="sxs-lookup"><span data-stu-id="9fc8c-151">*Topic viewers*</span></span>

<span data-ttu-id="9fc8c-152">主题查看者可以在搜索结果和 SharePoint 页面等内容中突出显示主题时查看主题页面的信息。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="9fc8c-153">只有在用户有权访问发现主题的文件和页面时，他们才能看到已发现的主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="9fc8c-154">设置主题查看器时，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="9fc8c-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="9fc8c-155">**我的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="9fc8c-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="9fc8c-156">**仅选定人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="9fc8c-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="9fc8c-157">**没人**</span><span class="sxs-lookup"><span data-stu-id="9fc8c-157">**No one**</span></span>

<span data-ttu-id="9fc8c-158">我们建议 **我的组织中的每个人**，但如果进行试点，你可能希望仅选择选定的人员或安全组。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="9fc8c-159">如果要设置 **主题** ，也可以选择"否"，但不允许用户查看主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="9fc8c-160"> (知识管理员仍可查看这些主题，并帮助他们做出让主题广泛可用的决定。) </span><span class="sxs-lookup"><span data-stu-id="9fc8c-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="9fc8c-161">知识规则</span><span class="sxs-lookup"><span data-stu-id="9fc8c-161">Knowledge rules</span></span>

<span data-ttu-id="9fc8c-162">作为管理员，你可以从主题体验中排除某些主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="9fc8c-163">如果要使敏感数据不显示在主题中，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="9fc8c-164">虽然知识管理员可以排除主题中心中的主题，但管理员排除的主题甚至对知识管理员不可见。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="9fc8c-165"> (管理员还可以在 discovery.) 之后删除主题中心中的主题) </span><span class="sxs-lookup"><span data-stu-id="9fc8c-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="9fc8c-166">如果要排除管理员级别的主题，则必须将它们添加到 .csv 文件并上载文件。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="9fc8c-167">您可以在设置期间或更高版本中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-167">You can do this during setup or later.</span></span>

<span data-ttu-id="9fc8c-168">.csv 文件必须包含以下参数：</span><span class="sxs-lookup"><span data-stu-id="9fc8c-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="9fc8c-169">**名称**：键入要排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="9fc8c-170">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="9fc8c-170">There are two ways to do this:</span></span>
- <span data-ttu-id="9fc8c-171">**MatchType-Exact/Partial：** 键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="9fc8c-172">完全匹配：可以包括确切的名称或首字母缩写词 (例如 *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="9fc8c-173">部分匹配：可以排除其中具有特定单词的所有主题。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="9fc8c-174">例如 *，arc* 将排除其中带弧字的所有主题，如 *弧形圆*、弧形弧形 *或\*\*培训弧*。请注意，它将不会排除其中的文本作为单词的一部分包含的主题，如 *体系结构。*</span><span class="sxs-lookup"><span data-stu-id="9fc8c-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="9fc8c-175">**代表 (** 可选) ： (也称为 *扩展)* 如果要排除首字母缩略词，请键入首字母缩写词代表的单词。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

<span data-ttu-id="9fc8c-177">你可以复制下面的 csv 模板：</span><span class="sxs-lookup"><span data-stu-id="9fc8c-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="9fc8c-178">管理</span><span class="sxs-lookup"><span data-stu-id="9fc8c-178">Administration</span></span>

<span data-ttu-id="9fc8c-179">在设置主题时，作为设置过程的一部分，将自动创建主题中心。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-179">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="9fc8c-180">考虑要命名主题中心的内容以及希望 URL 是什么。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="9fc8c-181">可以在设置过程中同时设置名称和 URL，稍后可以在 Microsoft 365 管理中心中更改名称 (但不能更改 URL) URL。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9fc8c-182">只能有一个主题中心。</span><span class="sxs-lookup"><span data-stu-id="9fc8c-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="9fc8c-183">设置清单</span><span class="sxs-lookup"><span data-stu-id="9fc8c-183">Setup checklist</span></span>

<span data-ttu-id="9fc8c-184">设置主题体验时，在安装向导中需要以下项：</span><span class="sxs-lookup"><span data-stu-id="9fc8c-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="9fc8c-185">要包含或排除的网站列表（如果未包括主题发现的所有网站）</span><span class="sxs-lookup"><span data-stu-id="9fc8c-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="9fc8c-186">如果不允许所有用户查看主题，适用于主题查看者的安全组</span><span class="sxs-lookup"><span data-stu-id="9fc8c-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="9fc8c-187">如果不允许所有用户创建和编辑主题，适用于主题参与者的安全组</span><span class="sxs-lookup"><span data-stu-id="9fc8c-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="9fc8c-188">主题知识管理员的安全组（如果不允许所有用户管理主题）</span><span class="sxs-lookup"><span data-stu-id="9fc8c-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="9fc8c-189">要从主题发现中排除的敏感主题列表</span><span class="sxs-lookup"><span data-stu-id="9fc8c-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="9fc8c-190">主题中心网站的名称</span><span class="sxs-lookup"><span data-stu-id="9fc8c-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="9fc8c-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fc8c-191">See also</span></span>

[<span data-ttu-id="9fc8c-192">设置主题体验</span><span class="sxs-lookup"><span data-stu-id="9fc8c-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="9fc8c-193">在 Microsoft 365 中管理主题发现</span><span class="sxs-lookup"><span data-stu-id="9fc8c-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="9fc8c-194">在 Microsoft 365 中管理主题可见性</span><span class="sxs-lookup"><span data-stu-id="9fc8c-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="9fc8c-195">在 Microsoft 365 中管理主题权限</span><span class="sxs-lookup"><span data-stu-id="9fc8c-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="9fc8c-196">在 Microsoft 365 中更改主题中心的名称</span><span class="sxs-lookup"><span data-stu-id="9fc8c-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
