---
title: 在 Microsoft 365 中管理主题发现
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在 Microsoft 365 中管理主题发现。
ms.openlocfilehash: 035fb74f1989dc7ef5b7fcf8e9c6d59b63cf2b42
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667845"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a><span data-ttu-id="0d9e0-103">在 Microsoft 365 中管理主题发现</span><span class="sxs-lookup"><span data-stu-id="0d9e0-103">Manage topic discovery in Microsoft 365</span></span>

<span data-ttu-id="0d9e0-104">可以在 [Microsoft 365](https://admin.microsoft.com)管理中心管理主题发现设置。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="0d9e0-105">您必须是全局管理员或 SharePoint 管理员才能执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="0d9e0-106">访问主题管理设置：</span><span class="sxs-lookup"><span data-stu-id="0d9e0-106">To access topics management settings:</span></span>

1. <span data-ttu-id="0d9e0-107">在 Microsoft 365 管理中心中，单击"**设置**"，然后单击"**组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="0d9e0-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="0d9e0-108">在"**服务"** 选项卡上，单击 **"知识网络"。**</span><span class="sxs-lookup"><span data-stu-id="0d9e0-108">On the **Services** tab, click **Knowledge network**.</span></span>

    ![将人员连接到知识](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="0d9e0-110">选择 **"主题发现"** 选项卡。有关每个设置的信息，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="0d9e0-112">选择 SharePoint 主题源</span><span class="sxs-lookup"><span data-stu-id="0d9e0-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="0d9e0-113">您可以更改组织中将针对主题进行爬网的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="0d9e0-114">如果要包含或排除特定网站列表，可以使用以下 .csv 模板：</span><span class="sxs-lookup"><span data-stu-id="0d9e0-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="0d9e0-115">如果使用网站选取器添加网站，则它们将被添加到要包含或排除的现有网站列表中。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="0d9e0-116">如果上载 .csv 文件，它将覆盖任何现有列表。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="0d9e0-117">如果之前已包含或排除特定网站，则以 .csv 文件下载列表、进行更改并上载新列表。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="0d9e0-118">为主题发现选择网站</span><span class="sxs-lookup"><span data-stu-id="0d9e0-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="0d9e0-119">在 **"主题发现"** 选项卡上的 **"选择 SharePoint 主题源"下**，选择"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="0d9e0-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="0d9e0-120">在 **"选择 SharePoint 主题源** "页上，选择要在发现过程中作为主题源对哪些 SharePoint 网站进行爬网。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="0d9e0-121">这包括：</span><span class="sxs-lookup"><span data-stu-id="0d9e0-121">This includes:</span></span>
    - <span data-ttu-id="0d9e0-122">**所有网站**：租户中所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="0d9e0-123">这将捕获当前和将来的网站。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="0d9e0-124">**全部，所选网站除外**：键入要排除的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="0d9e0-125">还可以上载要选择从发现中退出的网站列表。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="0d9e0-126">将来创建的网站将包含为主题发现源。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="0d9e0-127">**仅选定网站**：键入要包含的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="0d9e0-128">还可以上载网站列表。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-128">You can also upload a list of sites.</span></span> <span data-ttu-id="0d9e0-129">将来创建的网站不会作为主题发现源包含在内。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="0d9e0-130">**无网站**：主题不会自动生成或随 SharePoint 内容一起更新。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="0d9e0-131">现有主题保留在主题中心。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-131">Existing topics remain in the topic center.</span></span>

    ![SharePoint 主题源用户界面的屏幕截图](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="0d9e0-133">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="0d9e0-134">按名称排除主题</span><span class="sxs-lookup"><span data-stu-id="0d9e0-134">Exclude topics by name</span></span>

<span data-ttu-id="0d9e0-135">可以通过使用 .csv 文件上载列表来从发现中排除主题。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="0d9e0-136">如果之前已排除主题，可以下载 .csv，进行更改，然后重新上载。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="0d9e0-137">在"**主题发现"** 选项卡上的 **"排除主题**"下，选择 **"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="0d9e0-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="0d9e0-138">单击 **"按名称排除主题"。**</span><span class="sxs-lookup"><span data-stu-id="0d9e0-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="0d9e0-139">如果需要创建列表，请下载 .csv 模板，并添加要排除的主题 (请参阅下面的 *.csv* 模板) 。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="0d9e0-140">文件准备就绪后，单击" **浏览** "并上载文件。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="0d9e0-141">如果存在现有列表，可以下载包含该列表的 .csv。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="0d9e0-142">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-142">Click **Save**.</span></span>

    ![排除主题用户界面的屏幕截图](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="0d9e0-144">使用 .csv 模板</span><span class="sxs-lookup"><span data-stu-id="0d9e0-144">Working with the .csv template</span></span>

<span data-ttu-id="0d9e0-145">你可以复制下面的 csv 模板：</span><span class="sxs-lookup"><span data-stu-id="0d9e0-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="0d9e0-146">在 CSV 模板中，输入有关要排除的主题的以下信息：</span><span class="sxs-lookup"><span data-stu-id="0d9e0-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="0d9e0-147">**名称**：键入要排除的主题的名称。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="0d9e0-148">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="0d9e0-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="0d9e0-149">完全匹配：可以包括确切的名称或首字母缩写词 (例如 *Contoso* 或 *ATL*) 。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="0d9e0-150">部分匹配：可以排除其中具有特定单词的所有主题。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="0d9e0-151">例如 *，arc* 将排除其中带弧字的所有主题，如 *弧形圆*、圆弧 *弧* 线或 *培训弧*。请注意，它将不会排除作为单词的一部分包含的文本的主题，例如 *体系结构。*</span><span class="sxs-lookup"><span data-stu-id="0d9e0-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="0d9e0-152">**代表 (可选**) ：如果要排除首字母缩略词，请键入首字母缩写词代表的单词。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="0d9e0-153">**MatchType-Exact/Partial：** 键入您输入的名称 *是精确匹配* 类型还是 *部分* 匹配类型。</span><span class="sxs-lookup"><span data-stu-id="0d9e0-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="0d9e0-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d9e0-155">See also</span></span>

[<span data-ttu-id="0d9e0-156">在 Microsoft 365 中管理主题可见性</span><span class="sxs-lookup"><span data-stu-id="0d9e0-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="0d9e0-157">在 Microsoft 365 中管理主题权限</span><span class="sxs-lookup"><span data-stu-id="0d9e0-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="0d9e0-158">在 Microsoft 365 中更改主题中心的名称</span><span class="sxs-lookup"><span data-stu-id="0d9e0-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

