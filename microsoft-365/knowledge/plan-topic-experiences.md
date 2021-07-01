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
ms.openlocfilehash: a407fd6e6919c3b85235e317e5ed3ff103607700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229535"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="6c8ca-103">规划 Microsoft Viva 主题</span><span class="sxs-lookup"><span data-stu-id="6c8ca-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="6c8ca-104">你可以控制主题在组织中是如何体验的。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="6c8ca-105">针对主题的规划决策可确保向用户显示高质量主题，并且他们具有使用和提供知识所需的正确权限。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="6c8ca-106">本文将介绍这些规划决策：</span><span class="sxs-lookup"><span data-stu-id="6c8ca-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="6c8ca-107">要SharePoint主题爬网的网站</span><span class="sxs-lookup"><span data-stu-id="6c8ca-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="6c8ca-108">您希望从主题体验中排除的主题（如果有）</span><span class="sxs-lookup"><span data-stu-id="6c8ca-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="6c8ca-109">您希望使主题对哪些用户可见</span><span class="sxs-lookup"><span data-stu-id="6c8ca-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="6c8ca-110">要向哪些用户授予在主题中心管理主题的权限</span><span class="sxs-lookup"><span data-stu-id="6c8ca-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="6c8ca-111">要向哪些用户授予在主题中心创建或编辑主题的权限</span><span class="sxs-lookup"><span data-stu-id="6c8ca-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="6c8ca-112">要为主题中心指定什么名称</span><span class="sxs-lookup"><span data-stu-id="6c8ca-112">What name you want to give your topic center</span></span>

<span data-ttu-id="6c8ca-113">将尊重数据的安全和隐私，并且主题体验不会向用户授予对无权限文件的额外访问权限。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="6c8ca-114">作为规划过程的一部分，我们还建议您阅读 [Microsoft Viva](topic-experiences-security-privacy.md) 主题安全和隐私。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="6c8ca-115">若要了解有关 Viva 主题背后的 AI 技术，请阅读 Microsoft Viva 主题中的 [Alexandria：从大数据到大数据](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="6c8ca-116">要求</span><span class="sxs-lookup"><span data-stu-id="6c8ca-116">Requirements</span></span>

<span data-ttu-id="6c8ca-117">您必须订阅[Viva 主题](https://www.microsoft.com/microsoft-viva/topics)，并且必须是全局管理员或 SharePoint管理员才能访问Microsoft 365 管理中心设置主题。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="6c8ca-118">将使用主题的所有用户都需要主题 **体验** 许可证。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="6c8ca-119">"设置 Microsoft Viva 主题"中介绍了 [分配许可证的内容](set-up-topic-experiences.md)。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="6c8ca-120">主题发现</span><span class="sxs-lookup"><span data-stu-id="6c8ca-120">Topic discovery</span></span>

<span data-ttu-id="6c8ca-121">主题发现设置指定将哪些 SharePoint 网站用作主题源。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="6c8ca-122">这包括经典网站和新式网站，以及与组Microsoft Teams Microsoft 365网站。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-122">This includes both classic and modern sites, as well as sites associated with Microsoft Teams and Microsoft 365 Groups.</span></span> <span data-ttu-id="6c8ca-123">OneDrive网站。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-123">OneDrive sites are not included.</span></span>

<span data-ttu-id="6c8ca-124">可以选择包含所有 SharePoint 网站、特定网站列表或无网站。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-124">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="6c8ca-125">我们建议您选择所有网站，以便主题体验可以发现大量适合用户的主题。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-125">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="6c8ca-126">当设置好主题后，可从下列选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="6c8ca-126">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="6c8ca-127">**所有网站**：组织内的所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-127">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="6c8ca-128">这其中包括当前和未来的网站。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-128">This includes current and future sites.</span></span>
- <span data-ttu-id="6c8ca-129">**除所选网站之外的所有网站**：除指定网站之外的所有网站。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-129">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="6c8ca-130">将来创建的网站将包含为主题发现源。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-130">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="6c8ca-131">**仅选定网站**：仅指定网站。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-131">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="6c8ca-132">将不包含未来创建的网站作为发现源。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-132">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="6c8ca-133">**无网站**：不包含任何 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-133">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="6c8ca-134">如果您选择"全部 **"（** 所选网站除外）或"仅所选网站"，您可以上载包含.csv列表的配置文件。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-134">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="6c8ca-135">如果你进行试验并且希望包含有限数量的站点来启动，这些选项非常有用。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-135">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="6c8ca-136">你可以复制以下.csv模板：</span><span class="sxs-lookup"><span data-stu-id="6c8ca-136">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="6c8ca-137">我们不建议选择"否 **网站** "，因为它会阻止自动创建或更新主题。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-137">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="6c8ca-138">但是，如果要设置"主题"，稍后再添加网站，可以选择此选项。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-138">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="6c8ca-139">建议为用户或知识管理员创建一个流程，以请求从主题发现中删除各个网站（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-139">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="6c8ca-140">多地理位置</span><span class="sxs-lookup"><span data-stu-id="6c8ca-140">Multi-geo</span></span>

<span data-ttu-id="6c8ca-141">如果你的组织已Microsoft 365多地理位置[](/microsoft-365/enterprise/microsoft-365-multi-geo)，主题中心将预配在中心位置，并且只有SharePoint站点可以用作主题源。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-141">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="6c8ca-142"> (如果选择"所有 **站点"，Viva** 主题将使用中心位置的所有站点) </span><span class="sxs-lookup"><span data-stu-id="6c8ca-142">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="6c8ca-143">所有内容处理和存储均在中心位置完成。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-143">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="6c8ca-144">用户权限</span><span class="sxs-lookup"><span data-stu-id="6c8ca-144">User permissions</span></span>

<span data-ttu-id="6c8ca-145">您指定的用户权限确定组织中哪些人员与主题交互以及他们可以做什么。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-145">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="6c8ca-146">目前，Viva 主题不支持为来宾和外部用户 (或) 权限。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-146">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="6c8ca-147">*管理主题*</span><span class="sxs-lookup"><span data-stu-id="6c8ca-147">*Manage topics*</span></span>

<span data-ttu-id="6c8ca-148">知识管理人员监督信息的质量、信息的结构化方式以及组织的其他最佳做法。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-148">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="6c8ca-149">他们可以确认和拒绝主题。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-149">They can confirm and reject topics.</span></span>

<span data-ttu-id="6c8ca-150">虽然您可以指定各个主题管理员，但建议您创建一个安全 (或使用包含要成为知识管理员) 的现有安全组。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-150">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="6c8ca-151">您可以在安装过程中指定此安全组。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-151">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="6c8ca-152">*创建和编辑主题*</span><span class="sxs-lookup"><span data-stu-id="6c8ca-152">*Create and edit topics*</span></span>

<span data-ttu-id="6c8ca-153">主题参与者是贵组织中冠军和主题专家。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-153">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="6c8ca-154">他们可以创建和编辑主题。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-154">They can create and edit topics.</span></span> 

<span data-ttu-id="6c8ca-155">建议允许组织中的每个人创建和编辑主题，因为主题体验在所有用户都可以共享信息时效果最佳。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-155">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="6c8ca-156">如果要将创建和编辑主题限制为特定人员或组，请为这些人员或组创建一个安全组，在设置过程中指定它。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-156">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="6c8ca-157">你可以选择不允许任何人参与主题，但建议不要这样做。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-157">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="6c8ca-158">如果选择此选项，知识管理员仍可以编辑和创建主题。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-158">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="6c8ca-159">*主题查看器*</span><span class="sxs-lookup"><span data-stu-id="6c8ca-159">*Topic viewers*</span></span>

<span data-ttu-id="6c8ca-160">主题查看者可以在搜索结果和主题页面等内容中突出显示主题SharePoint信息。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-160">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="6c8ca-161">只有在用户有权访问发现主题的文件和页面时，他们才能看到已发现的主题。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-161">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="6c8ca-162">设置主题查看器时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="6c8ca-162">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="6c8ca-163">**我的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="6c8ca-163">**Everyone in my organization**</span></span>
- <span data-ttu-id="6c8ca-164">**仅选定人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="6c8ca-164">**Only selected people or security groups**</span></span>
- <span data-ttu-id="6c8ca-165">**没人**</span><span class="sxs-lookup"><span data-stu-id="6c8ca-165">**No one**</span></span>

<span data-ttu-id="6c8ca-166">我们建议 **"我的组织"中的**"每个人"，但如果进行试点，你可能希望仅选择所选人员或安全组。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-166">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="6c8ca-167">如果要设置 **主题** ，但不允许用户查看主题，也可以选择"否"。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-167">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="6c8ca-168"> (知识管理员仍可访问，以便他们查看主题，并帮助做出让主题广泛可用的决定。) </span><span class="sxs-lookup"><span data-stu-id="6c8ca-168">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="6c8ca-169">知识规则</span><span class="sxs-lookup"><span data-stu-id="6c8ca-169">Knowledge rules</span></span>

<span data-ttu-id="6c8ca-170">作为管理员，你可以从主题体验中排除某些主题。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-170">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="6c8ca-171">如果希望使敏感数据不显示在主题中，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-171">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="6c8ca-172">虽然知识管理员可以排除主题中心中的主题，但管理员排除的主题甚至对知识管理员不可见。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-172">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="6c8ca-173"> (管理员还可以在发现之后删除主题中心中) </span><span class="sxs-lookup"><span data-stu-id="6c8ca-173">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="6c8ca-174">如果要排除管理员级别的主题，则必须将它们添加到一个.csv文件并上载该文件。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-174">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="6c8ca-175">可以在安装过程中或以后执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-175">You can do this during setup or later.</span></span>

<span data-ttu-id="6c8ca-176">.csv文件必须包含以下参数：</span><span class="sxs-lookup"><span data-stu-id="6c8ca-176">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="6c8ca-177">**名称**：键入要排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-177">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="6c8ca-178">可以通过两种方式来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="6c8ca-178">There are two ways to do this:</span></span>
- <span data-ttu-id="6c8ca-179">**MatchType-Exact/Partial**：键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-179">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="6c8ca-180">完全匹配：可以包含确切的名称或缩写词 (例如 *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-180">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="6c8ca-181">部分匹配：可以排除其中包含特定单词的所有主题。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-181">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="6c8ca-182">例如 *，arc 将* 排除包含单词 *arc* 的所有主题，如弧 *形圆*、*弧* 形圆或 *培训弧*。请注意，它将不会排除将文本作为单词的一部分包含的主题，例如体系结构 *。*</span><span class="sxs-lookup"><span data-stu-id="6c8ca-182">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="6c8ca-183">**代表 (** 可选) ： (也称为 *扩展) 如果要* 排除缩略词，请键入首字母缩写词代表的单词。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-183">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

<span data-ttu-id="6c8ca-185">你可以复制下面的 csv 模板：</span><span class="sxs-lookup"><span data-stu-id="6c8ca-185">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="6c8ca-186">管理</span><span class="sxs-lookup"><span data-stu-id="6c8ca-186">Administration</span></span>

<span data-ttu-id="6c8ca-187">在设置主题时，作为设置过程的一部分，将自动创建主题中心。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-187">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="6c8ca-188">考虑要命名主题中心的内容以及希望 URL 的名称。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-188">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="6c8ca-189">可以在设置过程中同时设置名称和 URL，也可以稍后在 (中更改 url) URL Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-189">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6c8ca-190">只能有一个主题中心。</span><span class="sxs-lookup"><span data-stu-id="6c8ca-190">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="6c8ca-191">设置清单</span><span class="sxs-lookup"><span data-stu-id="6c8ca-191">Setup checklist</span></span>

<span data-ttu-id="6c8ca-192">设置主题体验时，在安装向导中需要以下项：</span><span class="sxs-lookup"><span data-stu-id="6c8ca-192">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="6c8ca-193">不包含所有主题发现网站时要包括或排除的网站列表</span><span class="sxs-lookup"><span data-stu-id="6c8ca-193">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="6c8ca-194">不允许所有用户查看主题时，查看者的安全组</span><span class="sxs-lookup"><span data-stu-id="6c8ca-194">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="6c8ca-195">不允许所有用户创建和编辑主题时，参与者的安全组</span><span class="sxs-lookup"><span data-stu-id="6c8ca-195">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="6c8ca-196">不允许所有用户管理主题时，知识管理员的安全组</span><span class="sxs-lookup"><span data-stu-id="6c8ca-196">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="6c8ca-197">主题发现中排除的敏感主题列表</span><span class="sxs-lookup"><span data-stu-id="6c8ca-197">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="6c8ca-198">主题中心网站的名称</span><span class="sxs-lookup"><span data-stu-id="6c8ca-198">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="6c8ca-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c8ca-199">See also</span></span>

[<span data-ttu-id="6c8ca-200">设置主题体验</span><span class="sxs-lookup"><span data-stu-id="6c8ca-200">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="6c8ca-201">在"管理主题发现"Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c8ca-201">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="6c8ca-202">管理主题在Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c8ca-202">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="6c8ca-203">管理主题权限Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c8ca-203">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="6c8ca-204">更改主题中心的名称Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c8ca-204">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
