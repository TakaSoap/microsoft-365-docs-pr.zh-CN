---
title: 在 Microsoft Viva 主题中管理主题发现
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 了解如何管理 Microsoft Viva 主题中的主题发现。
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768970"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="0dcff-103">在 Microsoft Viva 主题中管理主题发现</span><span class="sxs-lookup"><span data-stu-id="0dcff-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="0dcff-104">可以在管理中心 中管理Microsoft 365[发现设置](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="0dcff-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="0dcff-105">您必须是全局管理员或SharePoint才能执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="0dcff-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="0dcff-106">若要访问主题管理设置：</span><span class="sxs-lookup"><span data-stu-id="0dcff-106">To access topics management settings:</span></span>

1. <span data-ttu-id="0dcff-107">在管理Microsoft 365，单击"设置"，**然后单击"\*\*\*\*组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="0dcff-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="0dcff-108">在"**服务"** 选项卡上，单击 **"主题体验"。**</span><span class="sxs-lookup"><span data-stu-id="0dcff-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![连接人员了解知识](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="0dcff-110">选择" **主题发现"** 选项卡。有关每个设置的信息，请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="0dcff-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="0dcff-112">选择SharePoint主题源</span><span class="sxs-lookup"><span data-stu-id="0dcff-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="0dcff-113">您可以更改SharePoint主题的爬网网站。</span><span class="sxs-lookup"><span data-stu-id="0dcff-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="0dcff-114">如果要包含或排除特定的网站列表，可以使用以下.csv模板：</span><span class="sxs-lookup"><span data-stu-id="0dcff-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="0dcff-115">如果使用网站选取器添加网站，这些网站将添加到现有网站列表以包含或排除。</span><span class="sxs-lookup"><span data-stu-id="0dcff-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="0dcff-116">如果上传 .csv 文件，则会覆盖任何现有列表。</span><span class="sxs-lookup"><span data-stu-id="0dcff-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="0dcff-117">如果之前已包含或排除特定网站，则以文件.csv下载列表，进行更改，并上载新列表。</span><span class="sxs-lookup"><span data-stu-id="0dcff-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="0dcff-118">为主题发现选择站点</span><span class="sxs-lookup"><span data-stu-id="0dcff-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="0dcff-119">在“**主题发现**”选项卡上，“**SharePoint 主题源**”下方，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="0dcff-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="0dcff-120">在"**选择SharePoint** 源"页上，选择将在发现SharePoint哪些网站作为主题源进行爬网。</span><span class="sxs-lookup"><span data-stu-id="0dcff-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="0dcff-121">这包括：</span><span class="sxs-lookup"><span data-stu-id="0dcff-121">This includes:</span></span>
    - <span data-ttu-id="0dcff-122">**所有网站**：SharePoint网站。</span><span class="sxs-lookup"><span data-stu-id="0dcff-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="0dcff-123">这将捕获当前和将来的网站。</span><span class="sxs-lookup"><span data-stu-id="0dcff-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="0dcff-124">**全部，所选网站除外**：键入要排除的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="0dcff-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="0dcff-125">还可以上载要选择从发现中退出的网站列表。</span><span class="sxs-lookup"><span data-stu-id="0dcff-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="0dcff-126">将包含未来创建的网站作为主题发现源。</span><span class="sxs-lookup"><span data-stu-id="0dcff-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="0dcff-127">**仅选定网站**：键入要包含的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="0dcff-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="0dcff-128">您还可以上载网站列表。</span><span class="sxs-lookup"><span data-stu-id="0dcff-128">You can also upload a list of sites.</span></span> <span data-ttu-id="0dcff-129">将不包含未来创建的网站作为发现源。</span><span class="sxs-lookup"><span data-stu-id="0dcff-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="0dcff-130">**无网站**：主题不会自动生成或更新SharePoint内容。</span><span class="sxs-lookup"><span data-stu-id="0dcff-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="0dcff-131">现有主题保留在主题中心。</span><span class="sxs-lookup"><span data-stu-id="0dcff-131">Existing topics remain in the topic center.</span></span>

    ![主题SharePoint用户界面的屏幕截图](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="0dcff-133">单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="0dcff-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="0dcff-134">按名称排除主题</span><span class="sxs-lookup"><span data-stu-id="0dcff-134">Exclude topics by name</span></span>

<span data-ttu-id="0dcff-135">可以通过使用 .csv 文件上传列表，将主题从发现中排除。</span><span class="sxs-lookup"><span data-stu-id="0dcff-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="0dcff-136">如果之前排除过主题，可以下载 .csv、进行更改，然后再次上传。</span><span class="sxs-lookup"><span data-stu-id="0dcff-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="0dcff-137">在“**主题**”选项卡上，“**排除主题**”下方，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="0dcff-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="0dcff-138">单击 **"按名称排除主题"。**</span><span class="sxs-lookup"><span data-stu-id="0dcff-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="0dcff-139">如果需要创建列表，请下载 .csv 模板并添加要排除 (请参阅下面的使用 .csv *模板*) 。</span><span class="sxs-lookup"><span data-stu-id="0dcff-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="0dcff-140">文件准备就绪后，单击" **浏览** "并上载该文件。</span><span class="sxs-lookup"><span data-stu-id="0dcff-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="0dcff-141">如果存在现有列表，可以下载包含.csv的列表。</span><span class="sxs-lookup"><span data-stu-id="0dcff-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="0dcff-142">单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="0dcff-142">Click **Save**.</span></span>

    ![排除主题用户界面的屏幕截图](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="0dcff-144">使用.csv模板</span><span class="sxs-lookup"><span data-stu-id="0dcff-144">Working with the .csv template</span></span>

<span data-ttu-id="0dcff-145">你可以复制下面的 csv 模板：</span><span class="sxs-lookup"><span data-stu-id="0dcff-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="0dcff-146">在 CSV 模板中，输入与要排除的主题相关的以下信息：</span><span class="sxs-lookup"><span data-stu-id="0dcff-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="0dcff-147">**名称**：键入要排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="0dcff-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="0dcff-148">可以通过两种方式来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="0dcff-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="0dcff-149">完全匹配：可以排除确切的名称或缩写 (例如 *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="0dcff-149">Exact match: You can exclude the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="0dcff-150">部分匹配：可以排除其中包含特定单词的所有主题。</span><span class="sxs-lookup"><span data-stu-id="0dcff-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="0dcff-151">例如 *，arc 将* 排除包含单词 *arc* 的所有主题，如弧 *形圆*、*弧* 形圆或 *培训弧*。请注意，它将不会排除将文本作为单词的一部分包含的主题，例如体系结构 *。*</span><span class="sxs-lookup"><span data-stu-id="0dcff-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="0dcff-152">**代表 (可选**) ：如果要排除首字母缩写词，请键入首字母缩写词代表的单词。</span><span class="sxs-lookup"><span data-stu-id="0dcff-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="0dcff-153">**MatchType-Exact/Partial**：键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。</span><span class="sxs-lookup"><span data-stu-id="0dcff-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="0dcff-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0dcff-155">See also</span></span>

[<span data-ttu-id="0dcff-156">管理主题在Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dcff-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="0dcff-157">管理主题权限Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dcff-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="0dcff-158">更改主题中心的名称Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dcff-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
