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
ms.openlocfilehash: d64e4b341fe96d7aa3636f58bffe3dd8f388838e
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957535"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="c9952-103">规划 Microsoft Viva 主题</span><span class="sxs-lookup"><span data-stu-id="c9952-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="c9952-104">你可以控制主题在组织中是如何体验的。</span><span class="sxs-lookup"><span data-stu-id="c9952-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="c9952-105">针对主题的规划决策可确保向用户显示高质量主题，并且他们具有使用和提供知识所需的正确权限。</span><span class="sxs-lookup"><span data-stu-id="c9952-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="c9952-106">本文将介绍这些规划决策：</span><span class="sxs-lookup"><span data-stu-id="c9952-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="c9952-107">要针对主题对哪些 SharePoint 网站进行爬网</span><span class="sxs-lookup"><span data-stu-id="c9952-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="c9952-108">您希望从主题体验中排除的主题（如果有）</span><span class="sxs-lookup"><span data-stu-id="c9952-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="c9952-109">您希望使主题对哪些用户可见</span><span class="sxs-lookup"><span data-stu-id="c9952-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="c9952-110">要向哪些用户授予在主题中心管理主题的权限</span><span class="sxs-lookup"><span data-stu-id="c9952-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="c9952-111">要向哪些用户授予在主题中心创建或编辑主题的权限</span><span class="sxs-lookup"><span data-stu-id="c9952-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="c9952-112">要为主题中心指定什么名称</span><span class="sxs-lookup"><span data-stu-id="c9952-112">What name you want to give your topic center</span></span>

<span data-ttu-id="c9952-113">将尊重数据的安全和隐私，并且主题体验不会向用户授予对无权限文件的额外访问权限。</span><span class="sxs-lookup"><span data-stu-id="c9952-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="c9952-114">作为规划过程的一部分，我们还建议您阅读 [Microsoft Viva](topic-experiences-security-privacy.md) 主题安全和隐私。</span><span class="sxs-lookup"><span data-stu-id="c9952-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="c9952-115">要求</span><span class="sxs-lookup"><span data-stu-id="c9952-115">Requirements</span></span>

<span data-ttu-id="c9952-116">您必须订阅 [Viva 主题](https://www.microsoft.com/microsoft-viva/topics) ，并且必须是全局管理员或 SharePoint 管理员才能访问 Microsoft 365 管理中心并设置主题。</span><span class="sxs-lookup"><span data-stu-id="c9952-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="c9952-117">将使用主题的所有用户都需要主题 **体验** 许可证。</span><span class="sxs-lookup"><span data-stu-id="c9952-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="c9952-118">"设置 Microsoft Viva 主题"中介绍了 [分配许可证的内容](set-up-topic-experiences.md)。</span><span class="sxs-lookup"><span data-stu-id="c9952-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="c9952-119">主题发现</span><span class="sxs-lookup"><span data-stu-id="c9952-119">Topic discovery</span></span>

<span data-ttu-id="c9952-120">主题发现设置指定哪些 SharePoint 网站用作主题源。</span><span class="sxs-lookup"><span data-stu-id="c9952-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="c9952-121">可以选择包括所有 SharePoint 网站、特定网站列表或不包含任何网站。</span><span class="sxs-lookup"><span data-stu-id="c9952-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="c9952-122">我们建议您选择所有网站，以便主题体验可以发现大量适合用户的主题。</span><span class="sxs-lookup"><span data-stu-id="c9952-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="c9952-123">设置主题时，可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="c9952-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="c9952-124">**所有网站**：组织的所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="c9952-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="c9952-125">这包括当前网站和未来网站。</span><span class="sxs-lookup"><span data-stu-id="c9952-125">This includes current and future sites.</span></span>
- <span data-ttu-id="c9952-126">**全部，所选网站除外**：除指定的站点之外的所有网站。</span><span class="sxs-lookup"><span data-stu-id="c9952-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="c9952-127">将来创建的网站将包含为主题发现源。</span><span class="sxs-lookup"><span data-stu-id="c9952-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="c9952-128">**仅选定网站**：仅指定网站。</span><span class="sxs-lookup"><span data-stu-id="c9952-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="c9952-129">将来创建的网站不会作为主题发现源包含在内。</span><span class="sxs-lookup"><span data-stu-id="c9952-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="c9952-130">**无网站**：不包括任何 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="c9952-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="c9952-131">如果您选择"全部 **"（** 所选网站除外）或 **"仅** 选定网站"，您可以上载包含站点列表的 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="c9952-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="c9952-132">如果你进行试验并且希望包含有限数量的站点来启动，这些选项非常有用。</span><span class="sxs-lookup"><span data-stu-id="c9952-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="c9952-133">你可以复制下面的 .csv 模板：</span><span class="sxs-lookup"><span data-stu-id="c9952-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="c9952-134">我们不建议选择"否 **网站** "，因为它会阻止自动创建或更新主题。</span><span class="sxs-lookup"><span data-stu-id="c9952-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="c9952-135">但是，如果要设置"主题"，稍后再添加网站，可以选择此选项。</span><span class="sxs-lookup"><span data-stu-id="c9952-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="c9952-136">建议为用户或知识管理员创建一个流程，以请求从主题发现中删除各个网站（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="c9952-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="c9952-137">多地理位置</span><span class="sxs-lookup"><span data-stu-id="c9952-137">Multi-geo</span></span>

<span data-ttu-id="c9952-138">如果组织已部署 [Microsoft 365](/microsoft-365/enterprise/microsoft-365-multi-geo)多地理位置，主题中心将预配在中心位置，并且只有中心位置的 SharePoint 网站可以用作主题源。</span><span class="sxs-lookup"><span data-stu-id="c9952-138">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="c9952-139"> (如果选择"所有 **站点"，Viva** 主题将使用中心位置的所有站点) </span><span class="sxs-lookup"><span data-stu-id="c9952-139">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="c9952-140">所有内容处理和存储均在中心位置完成。</span><span class="sxs-lookup"><span data-stu-id="c9952-140">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="c9952-141">用户权限</span><span class="sxs-lookup"><span data-stu-id="c9952-141">User permissions</span></span>

<span data-ttu-id="c9952-142">您指定的用户权限确定组织中哪些人员与主题交互以及他们可以做什么。</span><span class="sxs-lookup"><span data-stu-id="c9952-142">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="c9952-143">目前，Viva 主题不支持为来宾和外部用户 (或) 权限。</span><span class="sxs-lookup"><span data-stu-id="c9952-143">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="c9952-144">*管理主题*</span><span class="sxs-lookup"><span data-stu-id="c9952-144">*Manage topics*</span></span>

<span data-ttu-id="c9952-145">知识管理人员监督信息的质量、信息的结构化方式以及组织的其他最佳做法。</span><span class="sxs-lookup"><span data-stu-id="c9952-145">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="c9952-146">他们可以确认和拒绝主题。</span><span class="sxs-lookup"><span data-stu-id="c9952-146">They can confirm and reject topics.</span></span>

<span data-ttu-id="c9952-147">虽然您可以指定各个主题管理员，但建议您创建一个安全 (或使用包含要成为知识管理员) 的现有安全组。</span><span class="sxs-lookup"><span data-stu-id="c9952-147">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="c9952-148">您可以在安装过程中指定此安全组。</span><span class="sxs-lookup"><span data-stu-id="c9952-148">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="c9952-149">*创建和编辑主题*</span><span class="sxs-lookup"><span data-stu-id="c9952-149">*Create and edit topics*</span></span>

<span data-ttu-id="c9952-150">主题参与者是贵组织中冠军和主题专家。</span><span class="sxs-lookup"><span data-stu-id="c9952-150">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="c9952-151">他们可以创建和编辑主题。</span><span class="sxs-lookup"><span data-stu-id="c9952-151">They can create and edit topics.</span></span> 

<span data-ttu-id="c9952-152">建议允许组织中的每个人创建和编辑主题，因为主题体验在所有用户都可以共享信息时效果最佳。</span><span class="sxs-lookup"><span data-stu-id="c9952-152">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="c9952-153">如果要将创建和编辑主题限制为特定人员或组，请为这些人员或组创建一个安全组，在设置过程中指定它。</span><span class="sxs-lookup"><span data-stu-id="c9952-153">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="c9952-154">你可以选择不允许任何人参与主题，但建议不要这样做。</span><span class="sxs-lookup"><span data-stu-id="c9952-154">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="c9952-155">如果选择此选项，知识管理员仍可以编辑和创建主题。</span><span class="sxs-lookup"><span data-stu-id="c9952-155">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="c9952-156">*主题查看者*</span><span class="sxs-lookup"><span data-stu-id="c9952-156">*Topic viewers*</span></span>

<span data-ttu-id="c9952-157">主题查看者可以在搜索结果和 SharePoint 页面等内容中突出显示主题时查看有关主题页面的信息。</span><span class="sxs-lookup"><span data-stu-id="c9952-157">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="c9952-158">只有在用户有权访问发现主题的文件和页面时，他们才能看到已发现的主题。</span><span class="sxs-lookup"><span data-stu-id="c9952-158">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="c9952-159">设置主题查看器时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="c9952-159">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="c9952-160">**我的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="c9952-160">**Everyone in my organization**</span></span>
- <span data-ttu-id="c9952-161">**仅选定人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="c9952-161">**Only selected people or security groups**</span></span>
- <span data-ttu-id="c9952-162">**没人**</span><span class="sxs-lookup"><span data-stu-id="c9952-162">**No one**</span></span>

<span data-ttu-id="c9952-163">我们建议 **"我的组织"中的**"每个人"，但如果进行试点，你可能希望仅选择所选人员或安全组。</span><span class="sxs-lookup"><span data-stu-id="c9952-163">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="c9952-164">如果要设置 **主题** ，但不允许用户查看主题，也可以选择"否"。</span><span class="sxs-lookup"><span data-stu-id="c9952-164">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="c9952-165"> (知识管理员仍可访问，以便他们查看主题，并帮助做出让主题广泛可用的决定。) </span><span class="sxs-lookup"><span data-stu-id="c9952-165">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="c9952-166">知识规则</span><span class="sxs-lookup"><span data-stu-id="c9952-166">Knowledge rules</span></span>

<span data-ttu-id="c9952-167">作为管理员，你可以从主题体验中排除某些主题。</span><span class="sxs-lookup"><span data-stu-id="c9952-167">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="c9952-168">如果希望使敏感数据不显示在主题中，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="c9952-168">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="c9952-169">虽然知识管理员可以排除主题中心中的主题，但管理员排除的主题甚至对知识管理员不可见。</span><span class="sxs-lookup"><span data-stu-id="c9952-169">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="c9952-170"> (管理员还可以在发现之后删除主题中心中) </span><span class="sxs-lookup"><span data-stu-id="c9952-170">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="c9952-171">如果要排除管理员级别的主题，则必须将它们添加到 .csv 文件并上载该文件。</span><span class="sxs-lookup"><span data-stu-id="c9952-171">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="c9952-172">可以在安装过程中或以后执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="c9952-172">You can do this during setup or later.</span></span>

<span data-ttu-id="c9952-173">.csv 文件必须包含以下参数：</span><span class="sxs-lookup"><span data-stu-id="c9952-173">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="c9952-174">**名称**：键入要排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="c9952-174">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="c9952-175">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="c9952-175">There are two ways to do this:</span></span>
- <span data-ttu-id="c9952-176">**MatchType-Exact/Partial**：键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。</span><span class="sxs-lookup"><span data-stu-id="c9952-176">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="c9952-177">完全匹配：可以包含确切的名称或缩写词 (例如 *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="c9952-177">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="c9952-178">部分匹配：可以排除其中包含特定单词的所有主题。</span><span class="sxs-lookup"><span data-stu-id="c9952-178">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="c9952-179">例如 *，arc 将* 排除包含单词 *arc* 的所有主题，如弧 *形圆*、*弧* 形圆或 *培训弧*。请注意，它将不会排除将文本作为单词的一部分包含的主题，例如体系结构 *。*</span><span class="sxs-lookup"><span data-stu-id="c9952-179">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="c9952-180">**代表 (** 可选) ： (也称为 *扩展) 如果要* 排除缩略词，请键入首字母缩写词代表的单词。</span><span class="sxs-lookup"><span data-stu-id="c9952-180">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

<span data-ttu-id="c9952-182">你可以复制下面的 csv 模板：</span><span class="sxs-lookup"><span data-stu-id="c9952-182">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="c9952-183">管理</span><span class="sxs-lookup"><span data-stu-id="c9952-183">Administration</span></span>

<span data-ttu-id="c9952-184">在设置主题时，作为设置过程的一部分，将自动创建主题中心。</span><span class="sxs-lookup"><span data-stu-id="c9952-184">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="c9952-185">考虑要命名主题中心的内容以及希望 URL 的名称。</span><span class="sxs-lookup"><span data-stu-id="c9952-185">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="c9952-186">可以在设置过程中同时设置名称和 URL，也可以稍后在 Microsoft 365 管理中心中更改名称 (但不能更改 URL) URL。</span><span class="sxs-lookup"><span data-stu-id="c9952-186">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c9952-187">只能有一个主题中心。</span><span class="sxs-lookup"><span data-stu-id="c9952-187">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="c9952-188">设置清单</span><span class="sxs-lookup"><span data-stu-id="c9952-188">Setup checklist</span></span>

<span data-ttu-id="c9952-189">设置主题体验时，在安装向导中需要以下项：</span><span class="sxs-lookup"><span data-stu-id="c9952-189">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="c9952-190">要包含或排除的网站列表（如果未包括主题发现的所有站点）</span><span class="sxs-lookup"><span data-stu-id="c9952-190">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="c9952-191">主题查看者的安全组（如果不允许所有用户查看主题）</span><span class="sxs-lookup"><span data-stu-id="c9952-191">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="c9952-192">主题参与者的安全组（如果不允许所有用户创建和编辑主题）</span><span class="sxs-lookup"><span data-stu-id="c9952-192">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="c9952-193">主题知识管理员的安全组（如果不允许所有用户管理主题）</span><span class="sxs-lookup"><span data-stu-id="c9952-193">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="c9952-194">主题发现中排除的敏感主题列表</span><span class="sxs-lookup"><span data-stu-id="c9952-194">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="c9952-195">主题中心网站的名称</span><span class="sxs-lookup"><span data-stu-id="c9952-195">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="c9952-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9952-196">See also</span></span>

[<span data-ttu-id="c9952-197">设置主题体验</span><span class="sxs-lookup"><span data-stu-id="c9952-197">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="c9952-198">在 Microsoft 365 中管理主题发现</span><span class="sxs-lookup"><span data-stu-id="c9952-198">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="c9952-199">在 Microsoft 365 中管理主题可见性</span><span class="sxs-lookup"><span data-stu-id="c9952-199">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="c9952-200">在 Microsoft 365 中管理主题权限</span><span class="sxs-lookup"><span data-stu-id="c9952-200">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="c9952-201">在 Microsoft 365 中更改主题中心的名称</span><span class="sxs-lookup"><span data-stu-id="c9952-201">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
