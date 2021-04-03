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
description: 了解如何在 Microsoft 365 订阅中添加和减少文件存储。 通过额外的文件存储，可以在 SharePoint Online 和 OneDrive 中存储更多内容。
ms.date: ''
ms.openlocfilehash: d65677b9c078026343410b53acd48932258cb4b1
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576957"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="6f748-104">为订阅添加存储空间</span><span class="sxs-lookup"><span data-stu-id="6f748-104">Add storage space for your subscription</span></span>

<span data-ttu-id="6f748-105">如果你的 SharePoint Online 网站集存储空间即将用完，并且你的计划符合条件，则可以为你的订阅增加存储空间。</span><span class="sxs-lookup"><span data-stu-id="6f748-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="6f748-106">如果你未在可用加载项列表中看到 **Office 365** 额外文件存储，这意味着你的计划不符合条件。</span><span class="sxs-lookup"><span data-stu-id="6f748-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="6f748-107">有关详细信息，请参阅我的 [计划是否符合条件？](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="6f748-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="6f748-108">如果你通过批量许可或云解决方案提供商购买了订阅，则不能直接从 Microsoft 为组织购买 **Office 365** 额外文件存储。</span><span class="sxs-lookup"><span data-stu-id="6f748-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="6f748-109">请联系你的代表或合作伙伴寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="6f748-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6f748-110">准备工作</span><span class="sxs-lookup"><span data-stu-id="6f748-110">Before you begin</span></span>

<span data-ttu-id="6f748-111">您必须是全局管理员或 SharePoint 管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="6f748-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="6f748-112">有关详细信息，请参阅[关于管理员角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="6f748-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="6f748-113">查看可用存储</span><span class="sxs-lookup"><span data-stu-id="6f748-113">View available storage</span></span>

1. <span data-ttu-id="6f748-114">在 SharePoint 管理中心中，转到" <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">活动</a> 网站"页面，然后使用对组织具有 [管理员](/sharepoint/sharepoint-admin-role) 权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="6f748-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="6f748-115">在页面的右上角，查看所有站点使用的存储量以及订阅的总存储量。</span><span class="sxs-lookup"><span data-stu-id="6f748-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="6f748-116">如果组织在 Office 365 中配置了多地理位置，此栏还会显示跨所有地理位置使用的存储量。</span><span class="sxs-lookup"><span data-stu-id="6f748-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![活动站点页面上的存储栏](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="6f748-118">使用的存储空间不包括最近24-48小时内所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6f748-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="6f748-119">确定使用的存储空间后，可以添加或删除订阅存储空间。</span><span class="sxs-lookup"><span data-stu-id="6f748-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="6f748-120">若要了解添加存储空间需要多少费用，请按照本文中的步骤操作，在购买更多内容之前查看定价信息。</span><span class="sxs-lookup"><span data-stu-id="6f748-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="6f748-121">有关设置网站集存储限制的信息，请参阅 [管理网站集存储限制](/sharepoint/manage-site-collection-storage-limits)。</span><span class="sxs-lookup"><span data-stu-id="6f748-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="6f748-122">向订阅添加存储</span><span class="sxs-lookup"><span data-stu-id="6f748-122">Add storage to your subscription</span></span>

<span data-ttu-id="6f748-123">如果尚未为订阅购买额外存储空间，可以这样做。</span><span class="sxs-lookup"><span data-stu-id="6f748-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="6f748-124">In the admin center， go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span><span class="sxs-lookup"><span data-stu-id="6f748-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="6f748-125">在"购买 **服务**"页面底部的"加载项"部分，找到 **"Office 365 额外** 文件存储"，然后选择"详细信息 **"。**</span><span class="sxs-lookup"><span data-stu-id="6f748-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="6f748-126">在产品详细信息页面上，选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="6f748-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="6f748-127">如果需要，请选择基本订阅，然后输入要添加的存储 GB 数。</span><span class="sxs-lookup"><span data-stu-id="6f748-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="6f748-128">选择 **"现在签出"。**</span><span class="sxs-lookup"><span data-stu-id="6f748-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="6f748-129">在"**看起来如何？"** 页上，验证所选的存储 GB 数，查看定价信息，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="6f748-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="6f748-130">在" **完成订单"** 页上，验证总计。</span><span class="sxs-lookup"><span data-stu-id="6f748-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="6f748-131">如果需要进行更改，请选择"编辑 **顺序"。**</span><span class="sxs-lookup"><span data-stu-id="6f748-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="6f748-132">如果订单需要信用检查，请选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="6f748-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="6f748-133">完成后，选择下 **订单转到** \> **管理员主页**。</span><span class="sxs-lookup"><span data-stu-id="6f748-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="6f748-134">增加或减少存储空间</span><span class="sxs-lookup"><span data-stu-id="6f748-134">Increase or decrease storage</span></span>

<span data-ttu-id="6f748-135">如果已经通过 **Office 365** 额外文件存储加载项购买了额外的文件存储空间，可以使用以下步骤增加或减少订阅的额外存储空间。</span><span class="sxs-lookup"><span data-stu-id="6f748-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="6f748-136">可以将存储减少为 1 GB。</span><span class="sxs-lookup"><span data-stu-id="6f748-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="6f748-137">若要删除所有额外存储空间，请联系 [支持人员](../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="6f748-137">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="6f748-138">在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="6f748-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="6f748-139">在" **产品** "选项卡上，选择包含 **Office 365** 额外文件存储加载项的订阅。</span><span class="sxs-lookup"><span data-stu-id="6f748-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="6f748-140">在产品详细信息页面上的"加载项"部分，选择"**管理加载项"。**</span><span class="sxs-lookup"><span data-stu-id="6f748-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="6f748-141">在 **"管理加载项"窗格中**，从"加载项"列表中选择 **"Office 365 额外文件存储"。**</span><span class="sxs-lookup"><span data-stu-id="6f748-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="6f748-142">在 **"数量** "文本框中，输入要用于订阅的存储空间的 GB 数。</span><span class="sxs-lookup"><span data-stu-id="6f748-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="6f748-143">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6f748-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="6f748-144">我的计划是否符合使用 Office 365 额外文件存储空间的条件？</span><span class="sxs-lookup"><span data-stu-id="6f748-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="6f748-145">Office 365 额外文件存储空间可以用于以下订阅：</span><span class="sxs-lookup"><span data-stu-id="6f748-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="6f748-146">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="6f748-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="6f748-147">Office 365 企业版 E2</span><span class="sxs-lookup"><span data-stu-id="6f748-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="6f748-148">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="6f748-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="6f748-149">Office 365 企业版 E4</span><span class="sxs-lookup"><span data-stu-id="6f748-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="6f748-150">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="6f748-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="6f748-151">具有 SharePoint 计划 1 的 Office 网页</span><span class="sxs-lookup"><span data-stu-id="6f748-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="6f748-152">具有 SharePoint 计划 2 的 Office 网页</span><span class="sxs-lookup"><span data-stu-id="6f748-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="6f748-153">SharePoint Online 计划 1</span><span class="sxs-lookup"><span data-stu-id="6f748-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="6f748-154">SharePoint Online 计划 2</span><span class="sxs-lookup"><span data-stu-id="6f748-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="6f748-155">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="6f748-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="6f748-156">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="6f748-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="6f748-157">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="6f748-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="6f748-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="6f748-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="6f748-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6f748-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="6f748-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="6f748-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="6f748-161">Office 365 额外文件存储还可用于 GCC、GCC High 和 DOD 计划。</span><span class="sxs-lookup"><span data-stu-id="6f748-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="6f748-162">相关内容</span><span class="sxs-lookup"><span data-stu-id="6f748-162">Related content</span></span>

<span data-ttu-id="6f748-163">[管理网站存储限制](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (文章) </span><span class="sxs-lookup"><span data-stu-id="6f748-163">[Manage site storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="6f748-164">[设置 OneDrive 用户的默认](/onedrive/set-default-storage-space) 存储空间 (文章) </span><span class="sxs-lookup"><span data-stu-id="6f748-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>