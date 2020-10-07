---
title: 设置 SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: 在Project Cortex中设置对内容的理解
ms.openlocfilehash: 0d66076c93eb46ca11977cea12417c0816e0d11b
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367927"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="24c08-103">设置 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="24c08-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="24c08-104">管理员可使用 Microsoft 365 管理中心设置 [Microsoft SharePoint Syntex](document-understanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="24c08-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](document-understanding-overview.md).</span></span> 

<span data-ttu-id="24c08-105">开始之前应考虑下列建议：</span><span class="sxs-lookup"><span data-stu-id="24c08-105">Consider the following before you start:</span></span>

- <span data-ttu-id="24c08-106">哪些SharePoint站点将启用表单处理？</span><span class="sxs-lookup"><span data-stu-id="24c08-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="24c08-107">全部、部分、还是选定的站点？</span><span class="sxs-lookup"><span data-stu-id="24c08-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="24c08-108">你的默认内容中心会采用什么名字？</span><span class="sxs-lookup"><span data-stu-id="24c08-108">What will you name of your default content center?</span></span>

<span data-ttu-id="24c08-109">可在 Microsoft 365 管理中心内的初始设置后更改你的设置。</span><span class="sxs-lookup"><span data-stu-id="24c08-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="24c08-110">本文中的内容适用于 Project Cortex 私人预览版。</span><span class="sxs-lookup"><span data-stu-id="24c08-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="24c08-111">[了解更多关于 Project Cortex的信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="24c08-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="24c08-112">设置前，请确保计划在环境中设置和配置内容理解的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="24c08-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="24c08-113">例如，需要对以下名称进行考虑：</span><span class="sxs-lookup"><span data-stu-id="24c08-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="24c08-114">要启用表单处理的 SharePoint 站点 - 所有这些站点、部分或选定的站点</span><span class="sxs-lookup"><span data-stu-id="24c08-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="24c08-115">你的内容中心和主站管理员的名字</span><span class="sxs-lookup"><span data-stu-id="24c08-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="24c08-116">要求</span><span class="sxs-lookup"><span data-stu-id="24c08-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="24c08-117">必须拥有全局管理员或 SharePoint 管理员权限，才能访问 Microsoft 365 管理中心并设置内容理解。</span><span class="sxs-lookup"><span data-stu-id="24c08-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="24c08-118">作为管理员，你还可在设置后随时对所选择的设置进行更改，并在整个 Microsoft 365 管理中心中的内容理解管理中设置。</span><span class="sxs-lookup"><span data-stu-id="24c08-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="24c08-119">对设置 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="24c08-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="24c08-120">在 Microsoft 365 管理中心中，选择“**设置**”，然后查看“**文件和内容**”部分。</span><span class="sxs-lookup"><span data-stu-id="24c08-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="24c08-121">在“**文件和内容**”部分中，选择“**自动内容理解**”。</span><span class="sxs-lookup"><span data-stu-id="24c08-121">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="24c08-122">在**自动理解内容** 页面上，单击**开始**， 以逐步完成设置流程。</span><span class="sxs-lookup"><span data-stu-id="24c08-122">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![开始设置](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="24c08-124">在开启图像标记页面上，选择是否要允许[图像标记](image-tagging.md)。</span><span class="sxs-lookup"><span data-stu-id="24c08-124">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![图像标记控件的截图](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="24c08-126">在**配置表单处理**页面上，可选择是否希望用户能够在特定的 SharePoint 文档库中创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="24c08-126">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="24c08-127">在文档库功能区中存在一个菜单选项，以便在已启用该功能的SharePoint文档库中**创建表单处理模型**。</span><span class="sxs-lookup"><span data-stu-id="24c08-127">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="24c08-128">对于**应显示用于创建表单处理模型的SharePoint库选项**，可选择：</span><span class="sxs-lookup"><span data-stu-id="24c08-128">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="24c08-129">**所有SharePoint库** ，均使其可供组织中的所有 SharePoint 库使用。</span><span class="sxs-lookup"><span data-stu-id="24c08-129">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="24c08-130">**仅在选定站点中的库**，然后选择需要提供它的站点，或上传最多50个站点的列表。</span><span class="sxs-lookup"><span data-stu-id="24c08-130">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="24c08-131">如果不希望对任何网站提供**SharePoint 库**，则不需要SharePoint库（可在设置后更改）。</span><span class="sxs-lookup"><span data-stu-id="24c08-131">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   ![配置表单处理](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="24c08-133">在收录一个站点后，删除该站点不会影响应用于该站点中的库的现有模型，也不会影响将文档理解模型应用于库的能力。</span><span class="sxs-lookup"><span data-stu-id="24c08-133">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="24c08-p105">在**创建内容中心**页面上，可创建一个 SharePoint 内容中心站点，用户可在该网站上创建和管理文档理解模型。 </span><span class="sxs-lookup"><span data-stu-id="24c08-p105">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models. </span></span></br>
    <span data-ttu-id="24c08-135">a.</span><span class="sxs-lookup"><span data-stu-id="24c08-135">a.</span></span> <span data-ttu-id="24c08-136">对于**站点名称**，键入要为内容中心站点提供的名称。</span><span class="sxs-lookup"><span data-stu-id="24c08-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="24c08-137">b.</span><span class="sxs-lookup"><span data-stu-id="24c08-137">b.</span></span> <span data-ttu-id="24c08-138">**站点地址** 将显示站点的 URL，具体取决于所选择的站点名称。</span><span class="sxs-lookup"><span data-stu-id="24c08-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="24c08-139">若想改变它，请点击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="24c08-139">If you want to change it, click **Edit**.</span></span></br>

      ![创建内容中心](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="24c08-141">选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="24c08-141">Select **Next**.</span></span>

7. <span data-ttu-id="24c08-142">在**审查并完成**页面上，可查看所选设置并选择进行更改。</span><span class="sxs-lookup"><span data-stu-id="24c08-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="24c08-143">如果对你的选择感到满意，请选择**激活**。</span><span class="sxs-lookup"><span data-stu-id="24c08-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="24c08-144">在确认页面上，点击**完成**。</span><span class="sxs-lookup"><span data-stu-id="24c08-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="24c08-145">你将返回到**自动理解内容**页面。</span><span class="sxs-lookup"><span data-stu-id="24c08-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="24c08-146">在此页面中，可选择**管理**，对配置设置进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="24c08-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="24c08-147">分配许可证</span><span class="sxs-lookup"><span data-stu-id="24c08-147">Assign licenses</span></span>

<span data-ttu-id="24c08-148">配置 SharePoint Syntex 后，必须为将使用任何 SharePoint Syntex 功能的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="24c08-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="24c08-149">以分配许可证：</span><span class="sxs-lookup"><span data-stu-id="24c08-149">To assign licenses:</span></span>

1. <span data-ttu-id="24c08-150">在Microsoft 365 管理中心中，在**用户**下，点击**活动用户**。</span><span class="sxs-lookup"><span data-stu-id="24c08-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="24c08-151">选择要给予许可的用户，然后单击 **管理产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="24c08-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="24c08-152">选择**分配更多**。</span><span class="sxs-lookup"><span data-stu-id="24c08-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="24c08-153">选择**智能内容服务**。</span><span class="sxs-lookup"><span data-stu-id="24c08-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="24c08-154">在**应用程序**下，确保 **智能内容服务的通用数据服务**以及**智能内容服务**都已选中。</span><span class="sxs-lookup"><span data-stu-id="24c08-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Microsoft 365 管理中心的SharePoint Syntex许可证。](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="24c08-156">单击**保存更改**。</span><span class="sxs-lookup"><span data-stu-id="24c08-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="24c08-157">AI 生成器点数</span><span class="sxs-lookup"><span data-stu-id="24c08-157">AI Builder credits</span></span>

<span data-ttu-id="24c08-158">如果你的组织中的 SharePoint Syntex有300或更多SharePoint Syntex 许可证，则会分配一百万个 AI 生成器点数。</span><span class="sxs-lookup"><span data-stu-id="24c08-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="24c08-159">如果许可证少于300个，则必须购买AI 生成器点数才能使用表单处理。</span><span class="sxs-lookup"><span data-stu-id="24c08-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="24c08-160">可使用 [AI 生成器计算器](https://powerapps.microsoft.com/ai-builder-calculator)来估算出适合你的AI 生成器容量。</span><span class="sxs-lookup"><span data-stu-id="24c08-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="24c08-161">转到[电源平台管理中心](https://admin.powerplatform.microsoft.com/resources/capacity)查询积分和使用情况。</span><span class="sxs-lookup"><span data-stu-id="24c08-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="24c08-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24c08-162">See also</span></span>

[<span data-ttu-id="24c08-163">表单处理模式概述</span><span class="sxs-lookup"><span data-stu-id="24c08-163">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="24c08-164">逐步：如何构建文档理解模型（视频）</span><span class="sxs-lookup"><span data-stu-id="24c08-164">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

