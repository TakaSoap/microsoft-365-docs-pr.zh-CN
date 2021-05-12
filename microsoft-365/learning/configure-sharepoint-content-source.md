---
title: '即将推出：将 SharePoint 配置为 Microsoft Viva Learning (Preview) '
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 了解如何将 SharePoint 配置为 Microsoft Viva Learning (Preview) 。
ms.openlocfilehash: 2bed3a42d62e2aab2165ee38379eb07503807e6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333574"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="ae237-103">即将推出：将 SharePoint 配置为 Microsoft Viva Learning (Preview) </span><span class="sxs-lookup"><span data-stu-id="ae237-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="ae237-104">本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。</span><span class="sxs-lookup"><span data-stu-id="ae237-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="ae237-105">您可以将 SharePoint 配置为学习内容源，使组织自己的内容在 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="ae237-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="ae237-106">概述</span><span class="sxs-lookup"><span data-stu-id="ae237-106">Overview</span></span>

<span data-ttu-id="ae237-107">知识管理员 (或全局管理员) 提供了一个网站 URL，学习服务可在其中创建一个空的集中位置（"学习应用程序内容存储库"，形式为结构化 SharePoint 列表）。</span><span class="sxs-lookup"><span data-stu-id="ae237-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="ae237-108">您的组织可以使用此列表来存储指向包含学习内容的跨公司 SharePoint 文件夹的链接。</span><span class="sxs-lookup"><span data-stu-id="ae237-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="ae237-109">管理员负责收集并创建文件夹的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="ae237-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="ae237-110">这些文件夹应仅包含可在 Viva Learning (Preview) 中提供的内容。</span><span class="sxs-lookup"><span data-stu-id="ae237-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="ae237-111">Viva Learning (Preview) 支持以下文档类型：</span><span class="sxs-lookup"><span data-stu-id="ae237-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="ae237-112">Word、PowerPoint、Excel、PDF</span><span class="sxs-lookup"><span data-stu-id="ae237-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="ae237-113">Audio (.m4a) </span><span class="sxs-lookup"><span data-stu-id="ae237-113">Audio (.m4a)</span></span>
- <span data-ttu-id="ae237-114">视频 (.mov、.mp4、.avi) </span><span class="sxs-lookup"><span data-stu-id="ae237-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="ae237-115">有关详细信息，请参阅 [SharePoint 限制](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="ae237-115">For more information, see [SharePoint limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="ae237-116">权限</span><span class="sxs-lookup"><span data-stu-id="ae237-116">Permissions</span></span>

<span data-ttu-id="ae237-117">可以从组织的任何 SharePoint 网站收集文档库文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="ae237-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="ae237-118">Viva Learning (Preview) 遵循所有现有内容权限。</span><span class="sxs-lookup"><span data-stu-id="ae237-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="ae237-119">因此，只有用户有权访问的内容才能在 Viva Learning (Preview) 中搜索和) 。</span><span class="sxs-lookup"><span data-stu-id="ae237-119">Therefore, only content for which a user has permission to access is searchable and visible within Viva Learning (Preview).</span></span> <span data-ttu-id="ae237-120">这些文件夹中的任何内容都可以搜索，但只能使用单个员工具有权限的内容。</span><span class="sxs-lookup"><span data-stu-id="ae237-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="ae237-121">目前不支持从组织存储库中删除内容。</span><span class="sxs-lookup"><span data-stu-id="ae237-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="ae237-122">若要删除无意中显示的内容，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ae237-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="ae237-123">若要限制对文档库的访问，请选择"**显示操作**"选项，然后选择"**管理访问"。**</span><span class="sxs-lookup"><span data-stu-id="ae237-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![SharePoint 中的"文档库"页显示"显示操作"选项，其中"管理访问权限"为"高连字"。](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="ae237-125">删除文档库中的原始文档。</span><span class="sxs-lookup"><span data-stu-id="ae237-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="ae237-126">有关详细信息，请参阅 [SharePoint 新式体验中的共享和权限](/sharepoint/modern-experience-sharing-permissions)。</span><span class="sxs-lookup"><span data-stu-id="ae237-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="ae237-127">学习服务</span><span class="sxs-lookup"><span data-stu-id="ae237-127">Learning Service</span></span>

<span data-ttu-id="ae237-128">学习服务使用提供的文件夹 URL 从存储在这些文件夹中的所有内容获取元数据。</span><span class="sxs-lookup"><span data-stu-id="ae237-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="ae237-129">在集中式存储库中提供文件夹 URL 的 24 小时内，员工可以在 Viva Learning (Preview) 中搜索和使用组织的内容。</span><span class="sxs-lookup"><span data-stu-id="ae237-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="ae237-130">对内容的所有更改（包括更新的元数据和权限）也将在 24 小时内应用到学习服务中。</span><span class="sxs-lookup"><span data-stu-id="ae237-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="ae237-131">将 SharePoint 配置为源</span><span class="sxs-lookup"><span data-stu-id="ae237-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="ae237-132">您必须是 Microsoft 365 全局管理员、SharePoint 管理员或知识管理员才能执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="ae237-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="ae237-133">若要在 Viva Learning (Preview) 中将 SharePoint 配置为学习内容源，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ae237-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="ae237-134">在 Microsoft 365 管理中心的左侧导航中，转到 **"设置**  >  **""组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="ae237-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="ae237-135">在"**组织设置"** 页上的"服务 **"选项卡上**，选择 **"Viva Learning (Preview) "。**</span><span class="sxs-lookup"><span data-stu-id="ae237-135">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![Microsoft 365 管理中心中的"设置"页面显示"Viva 学习"已列出。](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="ae237-137">在 **Viva Learning (Preview)** 面板上的 SharePoint 下，提供您希望 Viva Learning (Preview) 创建集中式存储库的 SharePoint 网站的网站 URL。</span><span class="sxs-lookup"><span data-stu-id="ae237-137">On the **Viva Learning (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning (Preview) to create a centralized repository.</span></span>

     ![Microsoft 365 管理中心中的学习面板显示已选中的 SharePoint。](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="ae237-139">SharePoint 列表在提供的 SharePoint 网站中自动创建。</span><span class="sxs-lookup"><span data-stu-id="ae237-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![SharePoint 网站中新创建的 SharePoint 列表。](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="ae237-141">在 SharePoint 网站的左侧导航栏中，选择"网站 **内容**  >  **""学习应用程序内容存储库"。**</span><span class="sxs-lookup"><span data-stu-id="ae237-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![显示"网站内容"导航和"了解应用程序内容存储库"部分的 SharePoint 列表。](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="ae237-143">在" **学习应用程序内容存储库"** 页上，使用学习内容文件夹的 URL 填充 SharePoint 列表。</span><span class="sxs-lookup"><span data-stu-id="ae237-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="ae237-144">选择 **"新建** "以查看 **"新建项目"** 面板。</span><span class="sxs-lookup"><span data-stu-id="ae237-144">Select **New** to view the **New item** panel.</span></span> 

       ![SharePoint 中的"了解内容存储库"页显示"新建"选项。](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="ae237-146">在 **"新建项目** "面板的" **标题** "字段中，添加你选择的目录名称。</span><span class="sxs-lookup"><span data-stu-id="ae237-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="ae237-147">在 **"文件夹 URL"** 字段中，将 URL 添加到学习内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="ae237-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="ae237-148">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ae237-148">Select **Save**.</span></span>

       ![SharePoint 中显示"标题"和"文件夹 URL"字段的"新建项目"面板。](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="ae237-150">" **学习应用程序内容存储库"** 页使用新的学习内容进行更新。</span><span class="sxs-lookup"><span data-stu-id="ae237-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![SharePoint 中的"了解内容存储库"页显示更新的信息。](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="ae237-152">为了允许更广泛的访问"学习应用程序内容存储库"，即将在 Viva Learning (Preview) 界面中提供指向列表的链接，用户可以在这里请求访问并最终帮助填充列表。</span><span class="sxs-lookup"><span data-stu-id="ae237-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="ae237-153">网站所有者和全局管理员需要授予对列表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ae237-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="ae237-154">访问权限仅特定于列表，不适用于存储列表的网站。</span><span class="sxs-lookup"><span data-stu-id="ae237-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="ae237-155">有关详细信息，请参阅本文稍后 [介绍的提供您自己的](#provide-your-own-organizations-content) 组织的内容。</span><span class="sxs-lookup"><span data-stu-id="ae237-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="ae237-156">文件夹 URL 文档库库的库</span><span class="sxs-lookup"><span data-stu-id="ae237-156">Folder URL document library curation</span></span>

<span data-ttu-id="ae237-157">Microsoft Graph API (修改日期、创建者、文档名称、内容类型和组织名称) 等默认元数据将自动拉入 Viva Learning (Preview) 中。</span><span class="sxs-lookup"><span data-stu-id="ae237-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="ae237-158">若要改进内容的总体发现和搜索相关性，建议添加"说明 **"** 列。</span><span class="sxs-lookup"><span data-stu-id="ae237-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="ae237-159">若要将 **"说明"** 列添加到文档库页面，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ae237-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="ae237-160">在"**文档"** 页上，选择"**添加列"。**</span><span class="sxs-lookup"><span data-stu-id="ae237-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="ae237-161">选择"**显示操作**"选项，然后选择"**单行文本"。**</span><span class="sxs-lookup"><span data-stu-id="ae237-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![SharePoint 中的"文档"页显示突出显示了单行文本的"显示操作"选项。](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="ae237-163">在 **"创建列"面板** 的"名称 **"字段中，** 添加列的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="ae237-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="ae237-164">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ae237-164">Select **Save**.</span></span>

     ![在 SharePoint 中创建一个显示"名称"和其他字段的列面板。](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="ae237-166">在" **文档** "页上的" **说明** "列中，添加每个项目的自定义说明。</span><span class="sxs-lookup"><span data-stu-id="ae237-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="ae237-167">如果未提供任何说明，Viva Learning (Preview) 将提供一条默认消息，突出显示内容来自自己的 SharePoint 库。</span><span class="sxs-lookup"><span data-stu-id="ae237-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![SharePoint 中的"文档"页，显示"说明"列中的说明。](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="ae237-169">提供你自己组织的内容</span><span class="sxs-lookup"><span data-stu-id="ae237-169">Provide your own organization's content</span></span>

<span data-ttu-id="ae237-170">知识管理员可在 SharePoint 中访问其组织的"学习应用程序内容存储库"，可在其中提供对跨组织文档库的引用。</span><span class="sxs-lookup"><span data-stu-id="ae237-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="ae237-171">然后，这些库中的内容将在 Viva Learning (Preview) 中显示。</span><span class="sxs-lookup"><span data-stu-id="ae237-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="ae237-172">在 Viva Learning (Preview) 中，选择"更多 **选项** (**...) "，** 然后选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="ae237-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![显示"更多选项和设置"选项的 SharePoint 库页面。](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="ae237-174">在 **"设置"** 下，**选择"权限"。**</span><span class="sxs-lookup"><span data-stu-id="ae237-174">Under **Settings**, select **Permissions**.</span></span>

     ![SharePoint 中的"设置"选项页面，显示"权限"和"检查访问选项"。](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="ae237-176">选择 **"检查** 访问权限"以连接到组织的集中式库。</span><span class="sxs-lookup"><span data-stu-id="ae237-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
