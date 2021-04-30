---
title: '即将推出：SharePoint Microsoft Viva Learning (Preview) '
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 了解如何配置 SharePoint 作为 Microsoft Viva Learning (Preview) 的学习内容源。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: da75ec0573519ed73507994afeac995c0461de0c
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100861"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="c16e0-103">即将推出：SharePoint Microsoft Viva Learning (Preview) </span><span class="sxs-lookup"><span data-stu-id="c16e0-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="c16e0-104">本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。</span><span class="sxs-lookup"><span data-stu-id="c16e0-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="c16e0-105">你可以将SharePoint配置为学习内容源，使组织自己的内容在 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="c16e0-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="c16e0-106">概述</span><span class="sxs-lookup"><span data-stu-id="c16e0-106">Overview</span></span>

<span data-ttu-id="c16e0-107">知识管理员 (或全局管理员) 提供了一个网站 URL，学习服务可在其中创建一个空的集中位置（学习应用程序内容存储库）以结构化 SharePoint 列表的形式。</span><span class="sxs-lookup"><span data-stu-id="c16e0-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="c16e0-108">组织可以使用此列表来存储指向包含学习内容的跨公司SharePoint的链接。</span><span class="sxs-lookup"><span data-stu-id="c16e0-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="c16e0-109">管理员负责收集并创建文件夹的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="c16e0-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="c16e0-110">这些文件夹应仅包含可在 Viva Learning (Preview) 中提供的内容。</span><span class="sxs-lookup"><span data-stu-id="c16e0-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="c16e0-111">Viva Learning (Preview) 支持以下文档类型：</span><span class="sxs-lookup"><span data-stu-id="c16e0-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="c16e0-112">Word、PowerPoint、Excel、PDF</span><span class="sxs-lookup"><span data-stu-id="c16e0-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="c16e0-113">Audio (.m4a) </span><span class="sxs-lookup"><span data-stu-id="c16e0-113">Audio (.m4a)</span></span>
- <span data-ttu-id="c16e0-114">视频 (.mov、.mp4、.avi) </span><span class="sxs-lookup"><span data-stu-id="c16e0-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="c16e0-115">有关详细信息，请参阅 SharePoint [Online 文档](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="c16e0-115">For more information, see the [SharePoint Online documentation](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="c16e0-116">权限</span><span class="sxs-lookup"><span data-stu-id="c16e0-116">Permissions</span></span>

<span data-ttu-id="c16e0-117">可以从组织的任何网站收集SharePoint文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="c16e0-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="c16e0-118">Viva Learning (Preview) 遵循所有现有内容权限。</span><span class="sxs-lookup"><span data-stu-id="c16e0-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="c16e0-119">因此，只有用户有权访问的内容才能在 Viva Learning (Preview) 中搜索和) 。</span><span class="sxs-lookup"><span data-stu-id="c16e0-119">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (Preview).</span></span> <span data-ttu-id="c16e0-120">这些文件夹中的任何内容都可以搜索，但只能使用单个员工具有权限的内容。</span><span class="sxs-lookup"><span data-stu-id="c16e0-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="c16e0-121">目前不支持从组织存储库中删除内容。</span><span class="sxs-lookup"><span data-stu-id="c16e0-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="c16e0-122">若要删除无意中显示的内容，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c16e0-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="c16e0-123">若要限制对文档库的访问，请选择"**显示操作**"选项，然后选择"**管理访问"。**</span><span class="sxs-lookup"><span data-stu-id="c16e0-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![文档库中的文档库SharePoint显示"显示操作"选项，其中"管理访问权限"为"高连字"。](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="c16e0-125">删除文档库中的原始文档。</span><span class="sxs-lookup"><span data-stu-id="c16e0-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="c16e0-126">有关详细信息，请参阅[新式体验中的共享SharePoint权限](/sharepoint/modern-experience-sharing-permissions)。</span><span class="sxs-lookup"><span data-stu-id="c16e0-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="c16e0-127">学习服务</span><span class="sxs-lookup"><span data-stu-id="c16e0-127">Learning Service</span></span>

<span data-ttu-id="c16e0-128">学习服务使用提供的文件夹 URL 从存储在这些文件夹中的所有内容获取元数据。</span><span class="sxs-lookup"><span data-stu-id="c16e0-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="c16e0-129">在集中式存储库中提供文件夹 URL 的 24 小时内，员工可以在 Viva Learning (Preview) 中搜索和使用组织的内容。</span><span class="sxs-lookup"><span data-stu-id="c16e0-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="c16e0-130">对内容的所有更改（包括更新的元数据和权限）也将在 24 小时内应用到学习服务中。</span><span class="sxs-lookup"><span data-stu-id="c16e0-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="c16e0-131">将SharePoint配置为源</span><span class="sxs-lookup"><span data-stu-id="c16e0-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="c16e0-132">您必须是全局Microsoft 365管理员、SharePoint管理员或知识管理员才能执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="c16e0-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="c16e0-133">若要将 SharePoint配置为 Viva Learning (Preview) 中的学习内容源，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c16e0-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="c16e0-134">在管理中心左侧导航Microsoft 365，**转到"设置**  >  **组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="c16e0-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="c16e0-135">在"**组织设置"** 页上的"服务 **"选项卡上**，选择"学习应用 (**预览) "。**</span><span class="sxs-lookup"><span data-stu-id="c16e0-135">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![设置管理中心中的"Microsoft 365页面，其中列出了 Viva Learning。](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="c16e0-137">在"学习 **(预览) "** 面板的"SharePoint"下，提供您希望 Viva Learning 创建集中式存储库的 SharePoint 网站的网站 URL。</span><span class="sxs-lookup"><span data-stu-id="c16e0-137">On the **Learning app (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![管理中心中的学习Microsoft 365显示已选中SharePoint面板。](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="c16e0-139">将在SharePoint网站中自动创建SharePoint列表。</span><span class="sxs-lookup"><span data-stu-id="c16e0-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![新SharePoint网站中的SharePoint列表。](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="c16e0-141">在网站左侧导航栏中 **，SharePoint"网站内容**  >  **""学习应用程序内容存储库"。**</span><span class="sxs-lookup"><span data-stu-id="c16e0-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePoint"网站内容导航"和"学习应用程序内容存储库"部分的列表。](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="c16e0-143">在"**学习应用程序内容** 存储库"页上，使用SharePoint内容文件夹的 URL 填充列表。</span><span class="sxs-lookup"><span data-stu-id="c16e0-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="c16e0-144">选择 **"新建** "以查看 **"新建项目"** 面板。</span><span class="sxs-lookup"><span data-stu-id="c16e0-144">Select **New** to view the **New item** panel.</span></span> 

       !["学习内容库"页SharePoint显示"新建"选项。](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="c16e0-146">在 **"新建项目** "面板的" **标题** "字段中，添加你选择的目录名称。</span><span class="sxs-lookup"><span data-stu-id="c16e0-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="c16e0-147">在 **"文件夹 URL"** 字段中，将 URL 添加到学习内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="c16e0-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="c16e0-148">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="c16e0-148">Select **Save**.</span></span>

       ![显示"标题"SharePoint"文件夹 URL"字段的"新建项目"面板。](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="c16e0-150">" **学习应用程序内容存储库"** 页使用新的学习内容进行更新。</span><span class="sxs-lookup"><span data-stu-id="c16e0-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       !["学习内容库"页SharePoint更新的信息。](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="c16e0-152">为了允许更广泛的访问"学习应用程序内容存储库"，即将在 Viva Learning (Preview) 界面中提供指向列表的链接，用户可以在这里请求访问并最终帮助填充列表。</span><span class="sxs-lookup"><span data-stu-id="c16e0-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="c16e0-153">网站所有者和全局管理员需要授予对列表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c16e0-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="c16e0-154">访问权限仅特定于列表，不适用于存储列表的网站。</span><span class="sxs-lookup"><span data-stu-id="c16e0-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="c16e0-155">有关详细信息，请参阅本文稍后 [介绍的提供您自己的](#provide-your-own-organizations-content) 组织的内容。</span><span class="sxs-lookup"><span data-stu-id="c16e0-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="c16e0-156">文件夹 URL 文档库库的库</span><span class="sxs-lookup"><span data-stu-id="c16e0-156">Folder URL document library curation</span></span>

<span data-ttu-id="c16e0-157">Graph Microsoft (API 会自动将默认元数据（如修改日期、创建者、文档名称、内容类型和组织名称) ）拉入 Viva Learning (Preview) 中。</span><span class="sxs-lookup"><span data-stu-id="c16e0-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="c16e0-158">若要改进内容的总体发现和搜索相关性，建议添加"说明 **"** 列。</span><span class="sxs-lookup"><span data-stu-id="c16e0-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="c16e0-159">若要将 **"说明"** 列添加到文档库页面，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c16e0-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="c16e0-160">在"**文档"** 页上，选择"**添加列"。**</span><span class="sxs-lookup"><span data-stu-id="c16e0-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="c16e0-161">选择"**显示操作**"选项，然后选择"**单行文本"。**</span><span class="sxs-lookup"><span data-stu-id="c16e0-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![文档中的"文档SharePoint显示突出显示了单行文本的"显示操作"选项。](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="c16e0-163">在 **"创建列"面板** 的"名称 **"字段中，** 添加列的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="c16e0-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="c16e0-164">选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="c16e0-164">Select **Save**.</span></span>

     ![创建一个列面板SharePoint显示"名称"和其他字段。](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="c16e0-166">在" **文档** "页上的" **说明** "列中，添加每个项目的自定义说明。</span><span class="sxs-lookup"><span data-stu-id="c16e0-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="c16e0-167">如果未提供任何说明，Viva Learning (Preview) 将提供一条默认消息，突出显示内容来自您自己的 SharePoint 库。</span><span class="sxs-lookup"><span data-stu-id="c16e0-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![文档页SharePoint"说明"列中的说明。](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="c16e0-169">提供你自己组织的内容</span><span class="sxs-lookup"><span data-stu-id="c16e0-169">Provide your own organization's content</span></span>

<span data-ttu-id="c16e0-170">知识管理员可以在 SharePoint 中访问其组织的"学习应用内容存储库"，他们可以在这里提供对跨组织文档库的引用。</span><span class="sxs-lookup"><span data-stu-id="c16e0-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="c16e0-171">然后，这些库中的内容将在 Viva Learning (Preview) 中显示。</span><span class="sxs-lookup"><span data-stu-id="c16e0-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="c16e0-172">在 Viva Learning (Preview) 中，选择"更多 **选项** (**...) "，** 然后选择 **"设置"。**</span><span class="sxs-lookup"><span data-stu-id="c16e0-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![SharePoint显示更多选项和选项的设置页面。](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="c16e0-174">在 **"设置"** 下，选择 **"权限"。**</span><span class="sxs-lookup"><span data-stu-id="c16e0-174">Under **Settings**, select **Permissions**.</span></span>

     ![设置选项页SharePoint显示"权限"和"检查访问"选项。](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="c16e0-176">选择 **"检查** 访问权限"以连接到组织的集中式库。</span><span class="sxs-lookup"><span data-stu-id="c16e0-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
