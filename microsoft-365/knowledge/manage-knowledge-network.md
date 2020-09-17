---
title: '管理您的知识管理网络 (预览)  '
description: 如何设置知识管理。
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 3ca180dba82e677dbc0d9f112b713df14820ce61
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950768"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="8e79a-103">管理您的知识管理网络 (预览) </span><span class="sxs-lookup"><span data-stu-id="8e79a-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="8e79a-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="8e79a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="8e79a-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="8e79a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="8e79a-106">在 [设置知识管理](set-up-knowledge-network.md)之后，在任何时间之后，管理员都可以通过 Microsoft 365 管理中心对您的配置设置进行调整。</span><span class="sxs-lookup"><span data-stu-id="8e79a-106">After you [set up knowledge management](set-up-knowledge-network.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="8e79a-107">例如，您可能需要调整以下任一项的设置：</span><span class="sxs-lookup"><span data-stu-id="8e79a-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="8e79a-108">将新的 SharePoint 源代码添加到 "我的应用" 主题。</span><span class="sxs-lookup"><span data-stu-id="8e79a-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="8e79a-109">更改哪些用户将有权访问主题。</span><span class="sxs-lookup"><span data-stu-id="8e79a-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="8e79a-110">更改哪些用户具有在主题中心执行任务的权限。</span><span class="sxs-lookup"><span data-stu-id="8e79a-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="8e79a-111">更改你的主题中心的名称</span><span class="sxs-lookup"><span data-stu-id="8e79a-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="8e79a-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="8e79a-112">Requirements</span></span> 
<span data-ttu-id="8e79a-113">您必须具有全局管理员或 SharePoint 管理员权限才能访问 Microsoft 365 管理中心并管理组织知识任务。</span><span class="sxs-lookup"><span data-stu-id="8e79a-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="8e79a-114">若要访问知识管理设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e79a-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="8e79a-115">在 Microsoft 365 管理中心，选择 " **设置**"，然后查看 " **组织知识库** " 部分。</span><span class="sxs-lookup"><span data-stu-id="8e79a-115">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="8e79a-116">在 " **组织知识** " 部分，单击 " **将人员连接到知识**"。</span><span class="sxs-lookup"><span data-stu-id="8e79a-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![将用户连接到知识](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="8e79a-118">在 " **将用户连接到知识** " 页上，选择 " **管理** " 以打开 " **知识网络设置** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="8e79a-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![知识网络-设置](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="8e79a-120">更改知识网络查找主题的方式</span><span class="sxs-lookup"><span data-stu-id="8e79a-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="8e79a-121">如果要为 SharePoint 主题源更新您的选择，请选择 " **主题发现** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e79a-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="8e79a-122">通过此设置，可以选择租户中将对主题进行爬网和挖掘的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="8e79a-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="8e79a-123">在 " **主题发现** " 选项卡上的 " **选择 SharePoint 主题源**" 下，选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8e79a-123">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="8e79a-124">在 " **选择 SharePoint 主题源** " 页上，选择要在发现过程中将哪些 SharePoint 网站作为主题的源进行爬网。</span><span class="sxs-lookup"><span data-stu-id="8e79a-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="8e79a-125">这包括：</span><span class="sxs-lookup"><span data-stu-id="8e79a-125">This includes:</span></span></br>
    <span data-ttu-id="8e79a-126">a.</span><span class="sxs-lookup"><span data-stu-id="8e79a-126">a.</span></span> <span data-ttu-id="8e79a-127">**所有网站**：租户中的所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="8e79a-127">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="8e79a-128">这将捕获当前和未来的网站。</span><span class="sxs-lookup"><span data-stu-id="8e79a-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="8e79a-129">b.</span><span class="sxs-lookup"><span data-stu-id="8e79a-129">b.</span></span> <span data-ttu-id="8e79a-130">**所有（选定网站除外）**：键入要排除的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="8e79a-130">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="8e79a-131">您还可以上载要从发现中退出的网站列表。</span><span class="sxs-lookup"><span data-stu-id="8e79a-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="8e79a-132">将来创建的网站将作为主题发现的源包括在内。</span><span class="sxs-lookup"><span data-stu-id="8e79a-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="8e79a-133">c.</span><span class="sxs-lookup"><span data-stu-id="8e79a-133">c.</span></span> <span data-ttu-id="8e79a-134">**仅选定网站**：键入要包含的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="8e79a-134">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="8e79a-135">您还可以上载网站列表。</span><span class="sxs-lookup"><span data-stu-id="8e79a-135">You can also upload a list of sites.</span></span> <span data-ttu-id="8e79a-136">将来创建的网站不会作为主题发现的源包括在内。</span><span class="sxs-lookup"><span data-stu-id="8e79a-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![选择如何查找主题](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="8e79a-138">如果您有大量要排除的网站 (如果选择 **"全部" （选择的网站除外**) 或包含 (）（如果只选择 **了 "选定网站**) "，则可以选择使用网站名称和 url 上传 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="8e79a-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites**) or include (if you selected **Only selected sites**), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="8e79a-139">如果要使用 CSV 模板文件，则可以选择 "**下载网站模板 .csv"。**</span><span class="sxs-lookup"><span data-stu-id="8e79a-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="8e79a-140">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8e79a-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="8e79a-141">更改可以查看组织中的主题的用户</span><span class="sxs-lookup"><span data-stu-id="8e79a-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="8e79a-142">如果要更新组织中的哪些用户可以在搜索结果中查看发现的主题以及在 SharePoint 页面等内容中突出显示主题，请选择 " **主题发现** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e79a-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="8e79a-143">在 " **主题发现** " 选项卡上，在 " **谁可以查看知识网络中的主题**" 下，选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8e79a-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network**, select **Edit**.</span></span>
2. <span data-ttu-id="8e79a-144">在 " **知识库中可以查看主题** " 页中，选择谁将有权访问主题详细信息，如突出显示的主题、主题卡片、搜索中的主题答案和主题页面。</span><span class="sxs-lookup"><span data-stu-id="8e79a-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="8e79a-145">可以选择：</span><span class="sxs-lookup"><span data-stu-id="8e79a-145">You can select:</span></span></br>
    <span data-ttu-id="8e79a-146">a.</span><span class="sxs-lookup"><span data-stu-id="8e79a-146">a.</span></span> <span data-ttu-id="8e79a-147">**组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="8e79a-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="8e79a-148">b.</span><span class="sxs-lookup"><span data-stu-id="8e79a-148">b.</span></span> <span data-ttu-id="8e79a-149">**仅选定的人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="8e79a-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="8e79a-150">c.</span><span class="sxs-lookup"><span data-stu-id="8e79a-150">c.</span></span> <span data-ttu-id="8e79a-151">**没人**</span><span class="sxs-lookup"><span data-stu-id="8e79a-151">**No one**</span></span></br>

    ![谁可以查看主题](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="8e79a-153">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8e79a-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="8e79a-154">虽然此设置允许您选择组织中的任何用户，但只有分配有知识管理许可证的用户才能查看主题。</span><span class="sxs-lookup"><span data-stu-id="8e79a-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="8e79a-155">更改有权在主题中心执行任务的谁</span><span class="sxs-lookup"><span data-stu-id="8e79a-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="8e79a-156">如果要在 "主题中心" 页中更新有权执行以下操作的用户，请选择 " **主题权限** " 选项卡：</span><span class="sxs-lookup"><span data-stu-id="8e79a-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="8e79a-157">哪些用户可以创建和编辑主题：创建在发现或编辑现有主题页面详细信息时找不到的新主题。</span><span class="sxs-lookup"><span data-stu-id="8e79a-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="8e79a-158">哪些用户可以管理主题：确认或拒绝已发现的主题。</span><span class="sxs-lookup"><span data-stu-id="8e79a-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="8e79a-159">若要更新有权创建和编辑主题的人士，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e79a-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="8e79a-160">在 " **主题权限** " 选项卡上，在 " **哪些人员可以创建和编辑主题**" 中，选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8e79a-160">On the **Topic permissions** tab, under **Who can create and edit topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="8e79a-161">在 " **可以创建和编辑主题的用户** " 页上，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="8e79a-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="8e79a-162">a.</span><span class="sxs-lookup"><span data-stu-id="8e79a-162">a.</span></span> <span data-ttu-id="8e79a-163">**组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="8e79a-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="8e79a-164">b.</span><span class="sxs-lookup"><span data-stu-id="8e79a-164">b.</span></span> <span data-ttu-id="8e79a-165">**仅选定的人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="8e79a-165">**Only selected people or security groups**</span></span></br>

    ![创建和编辑主题](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="8e79a-167">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8e79a-167">Select **Save**.</span></span></br>

<span data-ttu-id="8e79a-168">若要更新谁有权管理主题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e79a-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="8e79a-169">在 " **主题权限** " 选项卡上，在 " **谁可以管理主题**" 中，选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8e79a-169">On the **Topic permissions** tab, under **Who can manage topics**, select **Edit**.</span></span></br>
2. <span data-ttu-id="8e79a-170">在 " **谁可以管理主题** " 页上，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="8e79a-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="8e79a-171">a.</span><span class="sxs-lookup"><span data-stu-id="8e79a-171">a.</span></span> <span data-ttu-id="8e79a-172">**组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="8e79a-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="8e79a-173">b.</span><span class="sxs-lookup"><span data-stu-id="8e79a-173">b.</span></span> <span data-ttu-id="8e79a-174">**选定的人员或安全组**</span><span class="sxs-lookup"><span data-stu-id="8e79a-174">**Selected people or security groups**</span></span></br>

    ![管理主题](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="8e79a-176">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8e79a-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="8e79a-177">更新你的主题中心名称</span><span class="sxs-lookup"><span data-stu-id="8e79a-177">Update your topic center name</span></span>

<span data-ttu-id="8e79a-178">如果要更新您的主题中心的名称，请选择 " **主题中心** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e79a-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="8e79a-179">在 " **主题中心** " 选项卡上的 " **主题中心名称**" 下，选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8e79a-179">On the **Topic center** tab, under **Topic center name**, select **Edit**.</span></span>
2. <span data-ttu-id="8e79a-180">在 " **编辑主题中心名称** " 页上的 " **主题居中名称** " 框中，键入您的主题中心的新名称。</span><span class="sxs-lookup"><span data-stu-id="8e79a-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="8e79a-181">选择“**保存**”</span><span class="sxs-lookup"><span data-stu-id="8e79a-181">Select **Save**</span></span>

    ![编辑主题中心名称](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="8e79a-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e79a-183">See also</span></span>



  






