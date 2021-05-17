---
title: 在 Microsoft Viva 主题中创建新主题
description: 如何在 Microsoft Viva 主题中创建新主题。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ms.service: ''
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 7d1dc1af6e845ccfe2fb0e8f5701a2cd3018c308
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687527"
---
# <a name="create-a-new-topic-in-microsoft-viva-topics"></a><span data-ttu-id="ab6b4-103">在 Microsoft Viva 主题中创建新主题</span><span class="sxs-lookup"><span data-stu-id="ab6b4-103">Create a new topic in Microsoft Viva Topics</span></span>

<span data-ttu-id="ab6b4-104">在 Viva 主题中，如果尚未通过索引发现一个主题，或者 AI 技术没有找到足够证据来将它确定为主题，你可以创建新主题。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-104">In Viva Topics, you can create a new topic if one is not discovered through indexing or if the AI technology did not find enough evidence to establish it as a topic.</span></span>

> [!Note] 
> <span data-ttu-id="ab6b4-105">虽然 AI 收集的主题中的信息是经过安全[](topic-experiences-security-trimming.md)修整的，但请注意，手动创建的主题中的主题说明和人员信息对有权查看该主题的所有用户可见。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-105">While information in a topic that is gathered by AI is [security trimmed](topic-experiences-security-trimming.md), note that topic description and people information in a manually created topic is visible to all users who have permissions to view the topic.</span></span> 


## <a name="requirements"></a><span data-ttu-id="ab6b4-106">要求</span><span class="sxs-lookup"><span data-stu-id="ab6b4-106">Requirements</span></span>

<span data-ttu-id="ab6b4-107">若要创建新主题，您需要：</span><span class="sxs-lookup"><span data-stu-id="ab6b4-107">To create a new topic, you need to:</span></span>
- <span data-ttu-id="ab6b4-108">拥有 Viva 主题许可证。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-108">Have a Viva Topics license.</span></span>
- <span data-ttu-id="ab6b4-109">具有创建或 [**Who主题的权限**](./topic-experiences-user-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-109">Have permissions to [**Who can create or edit topics**](./topic-experiences-user-permissions.md).</span></span> <span data-ttu-id="ab6b4-110">知识管理员可以在 Viva 主题的主题权限设置中向用户授予此权限。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-110">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

> [!Note] 
> <span data-ttu-id="ab6b4-111">具有在主题中心管理主题的权限的用户 (知识) 已拥有创建和编辑主题的权限。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-111">Users who have permission to manage topics in the topic center (knowledge managers) already have permissions to create and edit topics.</span></span>

## <a name="to-create-a-topic"></a><span data-ttu-id="ab6b4-112">创建主题</span><span class="sxs-lookup"><span data-stu-id="ab6b4-112">To create a topic</span></span>

<span data-ttu-id="ab6b4-113">可以从两个位置创建新主题：</span><span class="sxs-lookup"><span data-stu-id="ab6b4-113">You can create a new topic from two locations:</span></span>

- <span data-ttu-id="ab6b4-114">主题中心主页：任何具有 **Who** 的许可用户可以创建或编辑主题权限 (参与者) 可以通过选择"新建"菜单并选择"主题页面"，从主题中心创建新主题。  </span><span class="sxs-lookup"><span data-stu-id="ab6b4-114">Topic center home page: Any licensed user with the **Who can create or edit topics** permission (contributors) can create a new topic from the topic center by selecting the **New** menu and select **Topic page**.</span></span> 

    ![主题中心的新主题](../media/knowledge-management/new-topic.png)  

- <span data-ttu-id="ab6b4-116">管理主题页面：具有 Who 的任何许可用户都可以管理主题权限 (knowledge managers) 可以通过选择"新建主题"页从主题中心中的"管理主题"页创建新 **主题。**</span><span class="sxs-lookup"><span data-stu-id="ab6b4-116">Manage topics page:  Any licensed user who has **Who can manage topics** permission (knowledge managers) can create a new topic from the Manage topics page in the Topic Center by selecting **New topic page**.</span></span> 

    ![管理主题中的新主题](../media/knowledge-management/new-topic-topic-center.png)  

### <a name="to-create-a-new-topic"></a><span data-ttu-id="ab6b4-118">要创建新主题：</span><span class="sxs-lookup"><span data-stu-id="ab6b4-118">To create a new topic:</span></span>

1. <span data-ttu-id="ab6b4-119">请从“管理主题”页上的功能区中选择选项，以创建 新主题页。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-119">Select the option to create a new Topic Page from the ribbon on the Manage Topics page.</span></span>

2.  <span data-ttu-id="ab6b4-120">在“**为本主题命名**”部分，键入新主题的名称。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-120">In the **Name this topic** section, type the name of the new topic.</span></span>

    ![将本主题命名](../media/knowledge-management/k-new-topic-page.png)  

3. <span data-ttu-id="ab6b4-122">在 **"备用名称** "部分，键入本主题可能引用的其他任何名称。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-122">In the **Alternate Names** section, type any other names that the topic might be referred to.</span></span> 

    ![备用名称](../media/knowledge-management/alt-names.png)  

4. <span data-ttu-id="ab6b4-124">在 **"说明** "部分，键入几个描述该主题的句子。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-124">In the **Description** section, type a couple of sentences that describe the topic.</span></span> 

    ![主题的说明](../media/knowledge-management/description.png)

4. <span data-ttu-id="ab6b4-126">在 **"固定人员** "部分中，你可以"固定"一个人，以将其显示与主题 (例如，已连接资源的所有者) 。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-126">In the **Pinned people** section, you can "pin" a person to show them as having a connection to the topic (for example, an owner of a connected resource).</span></span> <span data-ttu-id="ab6b4-127">首先在"添加新用户"框中键入用户的姓名或电子邮件地址，然后从搜索结果中选择要添加的用户。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-127">Begin by typing their name or email address in the **add a new user** box, and then select the user you want to add from the search results.</span></span> <span data-ttu-id="ab6b4-128">您还可以通过选择用户卡片上的"从列表中删除" **图标来** "取消固定"它们。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-128">You can also "unpin" them by selecting the **Remove from list** icon on the user card.</span></span> <span data-ttu-id="ab6b4-129">您还可以将该人员拖动到列表中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-129">You can also drag the person to another place in the list.</span></span>
 
    ![固定人员](../media/knowledge-management/pinned-people.png)

5. <span data-ttu-id="ab6b4-131">在 **"固定的文件和** 页面"部分，可以添加或"固定"SharePoint主题关联的文件或页面。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-131">In the **Pinned files and pages** section, you can add or "pin" a file or SharePoint site page that is associated to the topic.</span></span>

   ![固定的文件和页面](../media/knowledge-management/pinned-files-and-pages.png)
 
    <span data-ttu-id="ab6b4-133">若要添加新文件，请选择"添加"，从"常用SharePoint"或"关注的网站"中选择"网站"，然后从网站的文档库中选择该文件。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-133">To add a new file, select **Add**, select the SharePoint site from your Frequent or Followed sites, and then select the file from the site's document library.</span></span>

    <span data-ttu-id="ab6b4-134">您还可以通过提供 URL，使用"自链接"选项添加文件或页面。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-134">You can also use the **From a link** option to add a file or page by providing the URL.</span></span> 

    > [!Note] 
    > <span data-ttu-id="ab6b4-135">添加的文件和页面必须位于同一租户Microsoft 365租户中。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-135">Files and pages that you add must be located within the same Microsoft 365 tenant.</span></span> <span data-ttu-id="ab6b4-136">如果要在主题中添加指向外部资源的链接，可以通过步骤 8 中的画布图标添加该链接。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-136">If you want to add a link to an external resource in the topic, you can add it through the canvas icon in step 8.</span></span>


6.  <span data-ttu-id="ab6b4-137">" **相关网站** "部分显示包含有关该主题的信息的网站。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-137">The **Related sites** section shows sites that have information about the topic.</span></span> 

    ![相关网站部分](../media/knowledge-management/related-sites.png)

    <span data-ttu-id="ab6b4-139">您可以通过选择"添加"，然后搜索网站或从"常用"或"最近"网站列表中选择来添加相关网站。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-139">You can add a related site by selecting **Add** and then either searching for the site, or selecting it from your list of Frequent or Recent sites.</span></span>
    
    ![选择站点](../media/knowledge-management/sites.png)

7. <span data-ttu-id="ab6b4-141">" **相关主题** "部分显示主题之间的连接。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-141">The **Related topics** section shows connections that exist between topics.</span></span> <span data-ttu-id="ab6b4-142">您可以通过选择"与相关主题的 连接"按钮，然后键入相关主题的名称，然后从搜索结果中选择它，来添加与其他主题的连接。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-142">You can add a connection to a different topic by selecting the **Connect to a related topic** button, and then typing the name of the related topic, and selecting it from the search results.</span></span> 

   ![相关主题](../media/knowledge-management/related-topic.png)  

    <span data-ttu-id="ab6b4-144">然后，您可以对主题的相关情况进行说明，然后选择"更新 **"。**</span><span class="sxs-lookup"><span data-stu-id="ab6b4-144">You can then give a description of how the topics are related, and select **Update**.</span></span>

   ![相关主题说明](../media/knowledge-management/related-topics-update.png) 

   <span data-ttu-id="ab6b4-146">所添加的相关主题将显示为已连接的主题。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-146">The related topic you added will display as a connected topic.</span></span>

   ![已连接的相关主题](../media/knowledge-management/related-topics-final.png) 

   <span data-ttu-id="ab6b4-148">若要删除相关主题，请选择要删除的主题，然后选择" **删除主题"** 图标。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-148">To remove a related topic, select the topic you want to remove, then select the **Remove topic** icon.</span></span>
 
   ![删除相关主题](../media/knowledge-management/remove-related.png)  

   <span data-ttu-id="ab6b4-150">然后选择"**删除"。**</span><span class="sxs-lookup"><span data-stu-id="ab6b4-150">Then select **Remove**.</span></span>

   ![确认删除](../media/knowledge-management/remove-related-confirm.png) 

8. <span data-ttu-id="ab6b4-152">您还可以通过选择画布图标（可在简短说明下方找到 (，将静态项目添加到页面) ，如文本、图像或链接。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-152">You can also add static items to the page (such as text, images, or links) by selecting the canvas icon, which you can find below the short description.</span></span> <span data-ttu-id="ab6b4-153">选择它将打开SharePoint工具箱，您可以从中选择要添加到页面的项。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-153">Selecting it will open the SharePoint toolbox from which you can choose the item you want to add to the page.</span></span>

   ![画布图标](../media/knowledge-management/webpart-library.png) 

9. <span data-ttu-id="ab6b4-155">选择“**发布**”以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-155">Select **Publish** to save your changes.</span></span> 

<span data-ttu-id="ab6b4-156">发布页面后，将向查看主题的所有许可用户显示主题名称、备用名称、说明和固定的人员。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-156">After you publish the page, the topic name, alternate name, description, and pinned people will display to all licensed users who view the topic.</span></span> <span data-ttu-id="ab6b4-157">只有在查看者对项目具有 Office 365 权限的情况下，特定文件、页面和网站才会显示在主题页上。</span><span class="sxs-lookup"><span data-stu-id="ab6b4-157">Specific files, pages, and sites will only appear on the topic page if the viewer has Office 365 permissions to the item.</span></span> 



## <a name="see-also"></a><span data-ttu-id="ab6b4-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab6b4-158">See also</span></span>



