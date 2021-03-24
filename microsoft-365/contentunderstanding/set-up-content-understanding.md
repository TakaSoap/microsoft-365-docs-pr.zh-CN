---
title: 设置 SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: 在Project Cortex中设置对内容的理解
ms.openlocfilehash: cc6fbfbfc130cc6e64b5d7c30e0a9db5f39036ac
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051563"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="cb927-103">设置 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="cb927-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="cb927-104">管理员可使用 Microsoft 365 管理中心设置 [Microsoft SharePoint Syntex](index.md)。</span><span class="sxs-lookup"><span data-stu-id="cb927-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="cb927-105">开始之前应考虑下列建议：</span><span class="sxs-lookup"><span data-stu-id="cb927-105">Consider the following before you start:</span></span>

- <span data-ttu-id="cb927-106">要在哪些 SharePoint 网站中启用表单处理？</span><span class="sxs-lookup"><span data-stu-id="cb927-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="cb927-107">全部、部分、还是选定的站点？</span><span class="sxs-lookup"><span data-stu-id="cb927-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="cb927-108">你会如何为默认内容中心命名？</span><span class="sxs-lookup"><span data-stu-id="cb927-108">What will you name your default content center?</span></span>

<span data-ttu-id="cb927-109">可在 Microsoft 365 管理中心内的初始设置后更改你的设置。</span><span class="sxs-lookup"><span data-stu-id="cb927-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="cb927-110">设置前，请确保计划在环境中设置和配置内容理解的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="cb927-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="cb927-111">例如，你需要做出以下决策：</span><span class="sxs-lookup"><span data-stu-id="cb927-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="cb927-112">要启用表单处理的 SharePoint 网站 - 所有网站、部分网站或所选网站</span><span class="sxs-lookup"><span data-stu-id="cb927-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="cb927-113">内容中心的名称和管理员</span><span class="sxs-lookup"><span data-stu-id="cb927-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="cb927-114">要求</span><span class="sxs-lookup"><span data-stu-id="cb927-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="cb927-115">必须拥有全局管理员或 SharePoint 管理员权限，才能访问 Microsoft 365 管理中心并设置 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="cb927-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="cb927-116">作为管理员，你还可在设置后随时对所选择的设置进行更改，并在整个 Microsoft 365 管理中心中的内容理解管理中设置。</span><span class="sxs-lookup"><span data-stu-id="cb927-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

### <a name="licensing"></a><span data-ttu-id="cb927-117">许可</span><span class="sxs-lookup"><span data-stu-id="cb927-117">Licensing</span></span>

<span data-ttu-id="cb927-118">若要使用 SharePoint 整合，您的组织必须具有 SharePoint Syntex 订阅，并且每个用户必须分配以下许可证：</span><span class="sxs-lookup"><span data-stu-id="cb927-118">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="cb927-119">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="cb927-119">SharePoint Syntex</span></span>
- <span data-ttu-id="cb927-120">SharePoint 整合 - SPO 类型</span><span class="sxs-lookup"><span data-stu-id="cb927-120">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="cb927-121">用于 SharePoint 整合的常用数据服务</span><span class="sxs-lookup"><span data-stu-id="cb927-121">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="cb927-122">如果将来（或试用版过期）取消 SharePoint Syntex 订阅，用户将无法创建或运行文档了解或表单处理模型，且内容中心模板将不再可用。</span><span class="sxs-lookup"><span data-stu-id="cb927-122">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="cb927-123">此外，术语库报表、SKOS 分类导入和内容类型推送将不再可用。</span><span class="sxs-lookup"><span data-stu-id="cb927-123">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="cb927-124">不会删除任何内容，且网站权限不会更改。</span><span class="sxs-lookup"><span data-stu-id="cb927-124">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="cb927-125">AI 生成器点数</span><span class="sxs-lookup"><span data-stu-id="cb927-125">AI Builder credits</span></span>

<span data-ttu-id="cb927-126">如果你的组织中的 SharePoint Syntex有300或更多SharePoint Syntex 许可证，则会分配一百万个 AI 生成器点数。</span><span class="sxs-lookup"><span data-stu-id="cb927-126">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="cb927-127">如果许可证少于300个，则必须购买AI 生成器点数才能使用表单处理。</span><span class="sxs-lookup"><span data-stu-id="cb927-127">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="cb927-128">可使用 [AI 生成器计算器](https://powerapps.microsoft.com/ai-builder-calculator)来估算出适合你的AI 生成器容量。</span><span class="sxs-lookup"><span data-stu-id="cb927-128">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="cb927-129">转到[电源平台管理中心](https://admin.powerplatform.microsoft.com/resources/capacity)查询积分和使用情况。</span><span class="sxs-lookup"><span data-stu-id="cb927-129">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="cb927-130">对设置 SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="cb927-130">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="cb927-131">在 Microsoft 365 管理中心中，选择“**设置**”，然后查看“**文件和内容**”部分。</span><span class="sxs-lookup"><span data-stu-id="cb927-131">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="cb927-132">在“**文件和内容**”部分中，选择“**自动内容理解**”。</span><span class="sxs-lookup"><span data-stu-id="cb927-132">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="cb927-133">在 **自动理解内容** 页面上，单击 **开始**， 以逐步完成设置流程。</span><span class="sxs-lookup"><span data-stu-id="cb927-133">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cb927-134">![开始设置](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="cb927-134">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="cb927-135">在 **配置表单处理** 页面上，可选择是否希望用户能够在特定的 SharePoint 文档库中创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="cb927-135">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="cb927-136">在文档库功能区中存在一个菜单选项，以便在已启用该功能的SharePoint文档库中 **创建表单处理模型**。</span><span class="sxs-lookup"><span data-stu-id="cb927-136">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="cb927-137">对于 **应显示用于创建表单处理模型的SharePoint库选项**，可选择：</span><span class="sxs-lookup"><span data-stu-id="cb927-137">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="cb927-138">“**所有 SharePoint 网站中的库**”，从而使组织内的所有 SharePoint 库都可显示该选项。</span><span class="sxs-lookup"><span data-stu-id="cb927-138">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="cb927-139">“**所选 SharePoint 网站中的库**”，然后选择可显示该选项的网站或上传一个包含最多 50 个网站的列表。</span><span class="sxs-lookup"><span data-stu-id="cb927-139">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="cb927-140">如果不希望对任何网站提供 **SharePoint 库**，则不需要SharePoint库（可在设置后更改）。</span><span class="sxs-lookup"><span data-stu-id="cb927-140">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb927-141">![配置表单处理](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="cb927-141">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="cb927-142">在收录一个站点后，删除该站点不会影响应用于该站点中的库的现有模型，也不会影响将文档理解模型应用于库的能力。</span><span class="sxs-lookup"><span data-stu-id="cb927-142">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="cb927-143">在 **创建内容中心** 页面上，可创建一个 SharePoint 内容中心站点，用户可在该网站上创建和管理文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="cb927-143">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="cb927-144">对于 **站点名称**，键入要为内容中心站点提供的名称。</span><span class="sxs-lookup"><span data-stu-id="cb927-144">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="cb927-145">**站点地址** 将显示站点的 URL，具体取决于所选择的站点名称。</span><span class="sxs-lookup"><span data-stu-id="cb927-145">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="cb927-146">若想改变它，请点击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="cb927-146">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="cb927-147">![创建内容中心](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="cb927-147">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="cb927-148">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cb927-148">Select **Next**.</span></span>

6. <span data-ttu-id="cb927-149">在 **审查并完成** 页面上，可查看所选设置并选择进行更改。</span><span class="sxs-lookup"><span data-stu-id="cb927-149">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="cb927-150">如果对你的选择感到满意，请选择 **激活**。</span><span class="sxs-lookup"><span data-stu-id="cb927-150">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="cb927-151">在确认页面上，点击 **完成**。</span><span class="sxs-lookup"><span data-stu-id="cb927-151">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="cb927-152">你将返回到 **自动理解内容** 页面。</span><span class="sxs-lookup"><span data-stu-id="cb927-152">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="cb927-153">在此页面中，可选择 **管理**，对配置设置进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="cb927-153">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="cb927-154">分配许可证</span><span class="sxs-lookup"><span data-stu-id="cb927-154">Assign licenses</span></span>

<span data-ttu-id="cb927-155">配置 SharePoint Syntex 后，必须为将使用任何 SharePoint Syntex 功能的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="cb927-155">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="cb927-156">以分配许可证：</span><span class="sxs-lookup"><span data-stu-id="cb927-156">To assign licenses:</span></span>

1. <span data-ttu-id="cb927-157">在Microsoft 365 管理中心中，在 **用户** 下，点击 **活动用户**。</span><span class="sxs-lookup"><span data-stu-id="cb927-157">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="cb927-158">选择要给予许可的用户，然后选择“**管理产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="cb927-158">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="cb927-159">从下拉菜单中选择“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="cb927-159">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="cb927-160">选择“**显示 SharePoint Syntex 相关应用**”。</span><span class="sxs-lookup"><span data-stu-id="cb927-160">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="cb927-161">在“**应用**”下，确保“**面向 SharePoint Syntex 的 Common Data Service**”、“**SharePoint Syntex**”和“**SharePoint Syntex - SPO 类型**”都已选中。</span><span class="sxs-lookup"><span data-stu-id="cb927-161">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cb927-162">![Microsoft 365 管理中心的 SharePoint Syntex 许可证](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="cb927-162">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="cb927-163">单击 **保存更改**。</span><span class="sxs-lookup"><span data-stu-id="cb927-163">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb927-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb927-164">See also</span></span>

[<span data-ttu-id="cb927-165">表单处理模式概述</span><span class="sxs-lookup"><span data-stu-id="cb927-165">Overview of the form processing model</span></span>](/ai-builder/form-processing-model-overview)

[<span data-ttu-id="cb927-166">逐步：如何构建文档理解模型（视频）</span><span class="sxs-lookup"><span data-stu-id="cb927-166">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)
