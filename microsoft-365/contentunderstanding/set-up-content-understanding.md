---
title: 设置 SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 设置项目 Cortex 中的内容理解
ms.openlocfilehash: 31c6b6dd31b3f1bc47deb8424dd847cc0af6d429
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304776"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="66755-103">设置 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="66755-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="66755-104">管理员可以使用 Microsoft 365 管理中心设置和 Microsoft SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="66755-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="66755-105">在开始之前，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="66755-105">Consider the following before you start:</span></span>

- <span data-ttu-id="66755-106">您将在哪些 SharePoint 网站上启用表单处理？</span><span class="sxs-lookup"><span data-stu-id="66755-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="66755-107">所有用户、部分或选择网站？</span><span class="sxs-lookup"><span data-stu-id="66755-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="66755-108">您要将内容中心命名为什么，谁是主网站管理员？</span><span class="sxs-lookup"><span data-stu-id="66755-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="66755-109">你可以在 Microsoft 365 管理中心内初始安装后更改你的设置。</span><span class="sxs-lookup"><span data-stu-id="66755-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="66755-110">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="66755-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="66755-111">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="66755-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="66755-112">在安装之前，请务必规划在您的环境中设置和配置内容理解的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="66755-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="66755-113">例如，您需要考虑以下名称：</span><span class="sxs-lookup"><span data-stu-id="66755-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="66755-114">您要为其启用表单处理的 SharePoint 网站-所有用户、部分或选定网站</span><span class="sxs-lookup"><span data-stu-id="66755-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="66755-115">你的内容中心和主要网站管理员的名称</span><span class="sxs-lookup"><span data-stu-id="66755-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="66755-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="66755-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="66755-117">您必须具有全局管理员或 SharePoint 管理员权限才能访问 Microsoft 365 管理中心并设置内容了解。</span><span class="sxs-lookup"><span data-stu-id="66755-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="66755-118">作为管理员，您还可以在安装后随时更改所选设置，并在 Microsoft 365 管理中心内的内容理解管理设置中进行更改。</span><span class="sxs-lookup"><span data-stu-id="66755-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="66755-119">设置 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="66755-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="66755-120">在 Microsoft 365 管理中心，选择 " **设置**"，然后查看 " **组织知识库** " 部分。</span><span class="sxs-lookup"><span data-stu-id="66755-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="66755-121">在 " **组织知识库** " 部分，选择 " **自动内容理解**"。</span><span class="sxs-lookup"><span data-stu-id="66755-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![组织知识设置页](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="66755-123">在 " **自动化 SharePoint Syntex** " 页上，单击 " **入门** " 以浏览安装过程。</span><span class="sxs-lookup"><span data-stu-id="66755-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![开始安装](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="66755-125">在 "打开图像标记" 页上，选择是否要允许 [图像标记](image-tagging.md)。</span><span class="sxs-lookup"><span data-stu-id="66755-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![图像标记选项的屏幕截图](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="66755-127">在 " **配置表单处理** " 页上，您可以选择是否希望让用户能够使用 AI 生成器在特定的 SharePoint 文档库中创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="66755-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="66755-128">"文档库" 功能区中将提供一个菜单选项，以便在启用了 SharePoint 文档库中 **创建表单处理模型** 。</span><span class="sxs-lookup"><span data-stu-id="66755-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="66755-129">对于 **哪个 SharePoint 库应显示用于创建表单处理模型的选项**，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="66755-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="66755-130">**所有 sharepoint 库** ，使其可用于组织中的所有 sharepoint 库。</span><span class="sxs-lookup"><span data-stu-id="66755-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="66755-131">**仅选定网站中的库**，然后选择要使其可用的网站。</span><span class="sxs-lookup"><span data-stu-id="66755-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![配置表单处理](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="66755-133">在 SharePoint 文档库上启用此设置不会影响应用于库的现有模型，也不会影响将文档理解模型应用于库的功能。</span><span class="sxs-lookup"><span data-stu-id="66755-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="66755-134">在 " **创建内容中心** " 页上，您可以创建 SharePoint 内容中心网站，用户可以在该网站上创建和管理文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="66755-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="66755-135">a.</span><span class="sxs-lookup"><span data-stu-id="66755-135">a.</span></span> <span data-ttu-id="66755-136">在 " **网站名称**" 中，键入要为内容中心网站提供的名称。</span><span class="sxs-lookup"><span data-stu-id="66755-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="66755-137">b.</span><span class="sxs-lookup"><span data-stu-id="66755-137">b.</span></span> <span data-ttu-id="66755-138">**网站地址**将根据您为网站名称选择的内容显示网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="66755-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="66755-139">如果要对其进行更改，请单击 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="66755-139">If you want to change it, click **Edit**.</span></span></br>

      ![创建内容中心](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="66755-141">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="66755-141">Select **Next**.</span></span>

7. <span data-ttu-id="66755-142">在 " **检查和完成** " 页上，您可以查看选定的设置并选择进行更改。</span><span class="sxs-lookup"><span data-stu-id="66755-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="66755-143">如果您对所做的选择感到满意，请选择 " **激活**"。</span><span class="sxs-lookup"><span data-stu-id="66755-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="66755-144">在 "确认" 页上，单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="66755-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="66755-145">您将返回到 " **自动内容理解** " 页面。</span><span class="sxs-lookup"><span data-stu-id="66755-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="66755-146">在此页面中，您可以选择 " **管理** " 以对配置设置进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="66755-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="66755-147">分配许可证</span><span class="sxs-lookup"><span data-stu-id="66755-147">Assign licenses</span></span>

<span data-ttu-id="66755-148">配置 SharePoint Syntex 后，必须为将使用表单处理和文档理解功能的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="66755-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="66755-149">要分配许可证，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="66755-149">To assign licenses:</span></span>

1. <span data-ttu-id="66755-150">在 Microsoft 365 管理中心的 " **用户**" 下，单击 " **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="66755-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="66755-151">选择要许可的用户，然后单击 " **管理产品许可证**"。</span><span class="sxs-lookup"><span data-stu-id="66755-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="66755-152">选择 " **分配更多**"。</span><span class="sxs-lookup"><span data-stu-id="66755-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="66755-153">选择 " **智能内容服务**"。</span><span class="sxs-lookup"><span data-stu-id="66755-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="66755-154">在 "**应用程序**" 下，确保同时选中 "智能内容服务" 和 "**智能内容服务**"**的通用数据服务**。</span><span class="sxs-lookup"><span data-stu-id="66755-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Microsoft 365 管理中心中的 SharePoint Syntex 许可证](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="66755-156">单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="66755-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="66755-157">AI 生成器片尾</span><span class="sxs-lookup"><span data-stu-id="66755-157">AI Builder credits</span></span>

<span data-ttu-id="66755-158">如果你的组织中有针对 SharePoint Syntex 的300或更多 SharePoint Syntex 许可证，则会向你分配 1000000 AI 生成器信用。</span><span class="sxs-lookup"><span data-stu-id="66755-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="66755-159">如果许可证数量少于300个，则必须购买 AI 生成器信用才能使用表单处理。</span><span class="sxs-lookup"><span data-stu-id="66755-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="66755-160">您可以使用 [Ai 生成器计算器](https://powerapps.microsoft.com/ai-builder-calculator)估计适合您的 ai 生成器容量。</span><span class="sxs-lookup"><span data-stu-id="66755-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="66755-161">请转到 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/resources/capacity) 查看你的学分和使用情况。</span><span class="sxs-lookup"><span data-stu-id="66755-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="66755-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66755-162">See also</span></span>

[<span data-ttu-id="66755-163">表单处理模型概述</span><span class="sxs-lookup"><span data-stu-id="66755-163">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="66755-164">分步：了解如何构建文档理解模型 (视频) </span><span class="sxs-lookup"><span data-stu-id="66755-164">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

