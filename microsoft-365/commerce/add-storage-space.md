---
title: 为订阅添加存储空间
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: 了解如何添加并减少 Microsoft 365 订阅中的文件存储。 通过额外的文件存储，您可以在 SharePoint Online 和 OneDrive 中存储更多内容。
ms.date: ''
ms.openlocfilehash: 626cc81faea43ebdcf618a4f26c33069bae6a206
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405884"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="ebb61-104">为订阅添加存储空间</span><span class="sxs-lookup"><span data-stu-id="ebb61-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ebb61-105">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="ebb61-105">The admin center is changing.</span></span> <span data-ttu-id="ebb61-106">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="ebb61-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="ebb61-107">如果你的 SharePoint Online 网站集存储空间即将用完，并且你的计划符合条件，则可以为你的订阅增加存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebb61-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="ebb61-108">如果你未在可用加载项列表中看到 **Office 365** 额外文件存储，这意味着你的计划不符合条件。</span><span class="sxs-lookup"><span data-stu-id="ebb61-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="ebb61-109">有关详细信息，请参阅我的 [计划是否符合条件？](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="ebb61-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="ebb61-110">如果你通过批量许可或云解决方案提供商购买了订阅，则不能直接从 Microsoft 为组织购买 **Office 365** 额外文件存储。</span><span class="sxs-lookup"><span data-stu-id="ebb61-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="ebb61-111">请联系你的代表或合作伙伴寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="ebb61-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ebb61-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="ebb61-112">Before you begin</span></span>

<span data-ttu-id="ebb61-113">您必须是全局管理员或 SharePoint 管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="ebb61-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="ebb61-114">有关详细信息，请参阅 [关于管理员角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ebb61-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="ebb61-115">查看可用存储</span><span class="sxs-lookup"><span data-stu-id="ebb61-115">View available storage</span></span>

1. <span data-ttu-id="ebb61-116">在 SharePoint 管理中心，转到<a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">"活动</a>网站"页，然后使用对组织具有管理员权限[](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ebb61-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="ebb61-117">在页面的右上角，查看所有站点使用的存储量以及订阅的总存储量。</span><span class="sxs-lookup"><span data-stu-id="ebb61-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="ebb61-118">如果组织在 Office 365 中配置了多地理位置，则栏还显示跨所有地理位置使用的存储量。</span><span class="sxs-lookup"><span data-stu-id="ebb61-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![活动站点页面上的存储栏](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="ebb61-120">使用的存储空间不包括最近24-48小时内所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ebb61-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="ebb61-121">确定使用的存储空间后，可以添加或删除订阅的存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebb61-121">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="ebb61-122">若要了解增加存储空间的成本，请按照本文中的步骤操作，在购买更多存储空间之前查看定价信息。</span><span class="sxs-lookup"><span data-stu-id="ebb61-122">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="ebb61-123">有关设置网站集存储限制的信息，请参阅["管理网站集存储限制"。](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="ebb61-123">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="ebb61-124">将存储添加到订阅</span><span class="sxs-lookup"><span data-stu-id="ebb61-124">Add storage to your subscription</span></span>

<span data-ttu-id="ebb61-125">如果尚未为订阅购买额外存储空间，可以这样做。</span><span class="sxs-lookup"><span data-stu-id="ebb61-125">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="ebb61-126">在管理中心，转到" **计费** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">购买服务"</a> 页。</span><span class="sxs-lookup"><span data-stu-id="ebb61-126">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="ebb61-127">在"购买服务"**页面底部的**"加载项"部分，查找 **Office 365 额外文件存储**，然后选择 **"详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="ebb61-127">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="ebb61-128">在产品详细信息页上，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ebb61-128">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="ebb61-129">如果需要，请选择基本订阅，然后输入要添加的存储 GB 数。</span><span class="sxs-lookup"><span data-stu-id="ebb61-129">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="ebb61-130">选择 **"现在签出"。**</span><span class="sxs-lookup"><span data-stu-id="ebb61-130">Select **Check out now**.</span></span>
6. <span data-ttu-id="ebb61-131">在"**看起来如何？"** 页上，验证所选存储的 GB 数，查看定价信息，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ebb61-131">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="ebb61-132">在 **"完成订单"** 页上，验证总计。</span><span class="sxs-lookup"><span data-stu-id="ebb61-132">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="ebb61-133">如果需要进行任何更改，请选择"编辑 **顺序"。**</span><span class="sxs-lookup"><span data-stu-id="ebb61-133">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="ebb61-134">如果订单需要信用检查，请选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="ebb61-134">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="ebb61-135">完成后，选择"**下订单转到** \> **管理员主页"。**</span><span class="sxs-lookup"><span data-stu-id="ebb61-135">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="ebb61-136">增加或减少存储空间</span><span class="sxs-lookup"><span data-stu-id="ebb61-136">Increase or decrease storage</span></span>

<span data-ttu-id="ebb61-137">如果已经通过 **Office 365** 额外文件存储加载项购买了额外的文件存储，可以使用这些步骤来增加或减少订阅的额外存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebb61-137">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="ebb61-138">可以将存储减少为 1 GB。</span><span class="sxs-lookup"><span data-stu-id="ebb61-138">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="ebb61-139">若要删除所有额外的存储空间，请联系 [支持人员](../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="ebb61-139">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="ebb61-140">在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="ebb61-140">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="ebb61-141">在 **"产品** "选项卡上，选择包含 **Office 365** 额外文件存储加载项的订阅。</span><span class="sxs-lookup"><span data-stu-id="ebb61-141">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="ebb61-142">在产品详细信息页面上的 **"加载项**"部分，选择"**管理加载项"。**</span><span class="sxs-lookup"><span data-stu-id="ebb61-142">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="ebb61-143">在 **"管理加载项"窗格中**，从加载项列表中选择 **"Office 365 额外文件存储"。** </span><span class="sxs-lookup"><span data-stu-id="ebb61-143">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="ebb61-144">在 **"数量** "文本框中，输入订阅的存储空间的 GB 数。</span><span class="sxs-lookup"><span data-stu-id="ebb61-144">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="ebb61-145">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ebb61-145">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="ebb61-146">我的计划是否符合使用 Office 365 额外文件存储空间的条件？</span><span class="sxs-lookup"><span data-stu-id="ebb61-146">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="ebb61-147">Office 365 额外文件存储空间可以用于以下订阅：</span><span class="sxs-lookup"><span data-stu-id="ebb61-147">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="ebb61-148">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="ebb61-148">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="ebb61-149">Office 365 企业版 E2</span><span class="sxs-lookup"><span data-stu-id="ebb61-149">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="ebb61-150">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="ebb61-150">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="ebb61-151">Office 365 企业版 E4</span><span class="sxs-lookup"><span data-stu-id="ebb61-151">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="ebb61-152">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="ebb61-152">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="ebb61-153">具有 SharePoint 计划 1 的 Office 网页</span><span class="sxs-lookup"><span data-stu-id="ebb61-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="ebb61-154">具有 SharePoint 计划 2 的 Office 网页</span><span class="sxs-lookup"><span data-stu-id="ebb61-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="ebb61-155">SharePoint Online 计划 1</span><span class="sxs-lookup"><span data-stu-id="ebb61-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="ebb61-156">SharePoint Online 计划 2</span><span class="sxs-lookup"><span data-stu-id="ebb61-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="ebb61-157">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="ebb61-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="ebb61-158">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="ebb61-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="ebb61-159">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="ebb61-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="ebb61-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="ebb61-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="ebb61-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ebb61-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="ebb61-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="ebb61-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="ebb61-163">Office 365 额外文件存储还可用于 GCC、GCC High 和 DOD 计划。</span><span class="sxs-lookup"><span data-stu-id="ebb61-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="ebb61-164">相关内容</span><span class="sxs-lookup"><span data-stu-id="ebb61-164">Related content</span></span>

<span data-ttu-id="ebb61-165">[管理网站存储限制 (](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) 文章) </span><span class="sxs-lookup"><span data-stu-id="ebb61-165">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="ebb61-166">[设置 OneDrive 用户的默认存储空间， (](https://docs.microsoft.com/onedrive/set-default-storage-space) 文章) </span><span class="sxs-lookup"><span data-stu-id="ebb61-166">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>