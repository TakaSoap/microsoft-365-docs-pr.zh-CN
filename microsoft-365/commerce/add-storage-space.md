---
title: 为订阅添加存储空间
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: 在订阅中添加Microsoft 365存储。 通过额外的文件存储，可以在 SharePoint Online 和 OneDrive。
ms.date: 04/02/2021
ms.openlocfilehash: dee7debfbd2b624f3bf82bd573c81e7e1373b31e
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256815"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="1e469-104">为订阅添加存储空间</span><span class="sxs-lookup"><span data-stu-id="1e469-104">Add storage space for your subscription</span></span>

<span data-ttu-id="1e469-105">如果你的 SharePoint Online 网站集存储空间即将用完，并且你的计划符合条件，则可以为你的订阅增加存储空间。</span><span class="sxs-lookup"><span data-stu-id="1e469-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="1e469-106">如果在可用加载项列表中Office 365 额外文件存储空间列表，则意味着你的计划不符合条件。</span><span class="sxs-lookup"><span data-stu-id="1e469-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="1e469-107">有关详细信息，请参阅我的 [计划是否符合条件？](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="1e469-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="1e469-108">如果你通过批量许可或云解决方案提供商购买了订阅，你无法直接从 **microsoft Office 365 额外文件存储空间** 你的组织购买订阅。</span><span class="sxs-lookup"><span data-stu-id="1e469-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="1e469-109">请联系你的代表或合作伙伴寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="1e469-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1e469-110">开始之前</span><span class="sxs-lookup"><span data-stu-id="1e469-110">Before you begin</span></span>

<span data-ttu-id="1e469-111">你必须是全局管理员SharePoint管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="1e469-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="1e469-112">有关详细信息，请参阅 [关于管理员角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="1e469-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="1e469-113">查看可用存储</span><span class="sxs-lookup"><span data-stu-id="1e469-113">View available storage</span></span>

1. <span data-ttu-id="1e469-114">在SharePoint管理中心中，转到"活动站点"<a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a>页面，然后使用对组织具有管理员权限的帐户登录。 [](/sharepoint/sharepoint-admin-role)</span><span class="sxs-lookup"><span data-stu-id="1e469-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="1e469-115">在页面的右上角，查看所有站点使用的存储量以及订阅的总存储量。</span><span class="sxs-lookup"><span data-stu-id="1e469-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="1e469-116">如果你的组织已配置多地理位置Office 365，该栏还会显示跨所有地理位置使用的存储量。</span><span class="sxs-lookup"><span data-stu-id="1e469-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![活动站点页面上的存储栏](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="1e469-118">使用的存储空间不包括最近24-48小时内所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1e469-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="1e469-119">确定使用的存储空间后，可以添加或删除订阅存储空间。</span><span class="sxs-lookup"><span data-stu-id="1e469-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="1e469-120">若要了解添加存储空间需要多少费用，请按照本文中的步骤操作，在购买更多内容之前查看定价信息。</span><span class="sxs-lookup"><span data-stu-id="1e469-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="1e469-121">有关设置网站集存储限制的信息，请参阅 [管理网站集存储限制](/sharepoint/manage-site-collection-storage-limits)。</span><span class="sxs-lookup"><span data-stu-id="1e469-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="1e469-122">向订阅添加存储</span><span class="sxs-lookup"><span data-stu-id="1e469-122">Add storage to your subscription</span></span>

<span data-ttu-id="1e469-123">如果尚未为订阅购买额外存储空间，可以这样做。</span><span class="sxs-lookup"><span data-stu-id="1e469-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="1e469-124">In the admin center， go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span><span class="sxs-lookup"><span data-stu-id="1e469-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="1e469-125">在"购买服务"**页面底部的**"加载项"部分，找到"Office 365 额外文件存储空间"，然后选择"详细信息 **"。**</span><span class="sxs-lookup"><span data-stu-id="1e469-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="1e469-126">在产品详细信息页面上，选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="1e469-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="1e469-127">如果需要，请选择基本订阅，然后输入要添加的存储 GB 数。</span><span class="sxs-lookup"><span data-stu-id="1e469-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="1e469-128">选择 **"现在签出"。**</span><span class="sxs-lookup"><span data-stu-id="1e469-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="1e469-129">在"**看起来如何？"** 页上，验证所选的存储 GB 数，查看定价信息，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="1e469-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="1e469-130">在" **完成订单"** 页上，验证总计。</span><span class="sxs-lookup"><span data-stu-id="1e469-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="1e469-131">如果需要进行更改，请选择"编辑 **顺序"。**</span><span class="sxs-lookup"><span data-stu-id="1e469-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="1e469-132">如果订单需要信用检查，请选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="1e469-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="1e469-133">完成后，选择下 **订单转到** \> **管理员主页**。</span><span class="sxs-lookup"><span data-stu-id="1e469-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="1e469-134">增加或减少存储空间</span><span class="sxs-lookup"><span data-stu-id="1e469-134">Increase or decrease storage</span></span>

<span data-ttu-id="1e469-135">如果你已经通过加载项购买了额外的文件Office 365 额外文件存储空间，可以使用以下步骤增加或减少订阅的额外存储空间。</span><span class="sxs-lookup"><span data-stu-id="1e469-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="1e469-136">可以将存储减少为 1 GB。</span><span class="sxs-lookup"><span data-stu-id="1e469-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="1e469-137">若要删除所有额外存储空间，请联系 [支持人员](../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="1e469-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="1e469-138">在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="1e469-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="1e469-139">在 **"产品**"选项卡上，选择包含加载项 **Office 365 额外文件存储空间** 订阅。</span><span class="sxs-lookup"><span data-stu-id="1e469-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="1e469-140">在产品详细信息页面上的"加载项"部分，选择"**管理加载项"。**</span><span class="sxs-lookup"><span data-stu-id="1e469-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="1e469-141">在 **"管理加载项"窗格中**，从"加载项"列表中选择 **"Office 365 额外文件存储空间"。**</span><span class="sxs-lookup"><span data-stu-id="1e469-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="1e469-142">在 **"数量** "文本框中，输入要用于订阅的存储空间的 GB 数。</span><span class="sxs-lookup"><span data-stu-id="1e469-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="1e469-143">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1e469-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="1e469-144">我的计划是否符合使用 Office 365 额外文件存储空间的条件？</span><span class="sxs-lookup"><span data-stu-id="1e469-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="1e469-145">Office 365 额外文件存储空间可以用于以下订阅：</span><span class="sxs-lookup"><span data-stu-id="1e469-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="1e469-146">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="1e469-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="1e469-147">Office 365 企业版 E2</span><span class="sxs-lookup"><span data-stu-id="1e469-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="1e469-148">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="1e469-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="1e469-149">Office 365 企业版 E4</span><span class="sxs-lookup"><span data-stu-id="1e469-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="1e469-150">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="1e469-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="1e469-151">Office 365 A3 (教职员工) </span><span class="sxs-lookup"><span data-stu-id="1e469-151">Office 365 A3 (faculty)</span></span>
- <span data-ttu-id="1e469-152">Office 365 A5 (教职员工) </span><span class="sxs-lookup"><span data-stu-id="1e469-152">Office 365 A5 (faculty)</span></span>
- <span data-ttu-id="1e469-153">Office 网页版计划 SharePoint 1</span><span class="sxs-lookup"><span data-stu-id="1e469-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="1e469-154">Office 网页版计划 SharePoint 2</span><span class="sxs-lookup"><span data-stu-id="1e469-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="1e469-155">SharePoint Online 计划 1</span><span class="sxs-lookup"><span data-stu-id="1e469-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="1e469-156">SharePoint Online 计划 2</span><span class="sxs-lookup"><span data-stu-id="1e469-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="1e469-157">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="1e469-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="1e469-158">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="1e469-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="1e469-159">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="1e469-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="1e469-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="1e469-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="1e469-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1e469-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="1e469-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="1e469-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="1e469-163">Office 365 额外文件存储空间还可用于GCC、GCC高和 DOD 计划。</span><span class="sxs-lookup"><span data-stu-id="1e469-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="1e469-164">相关内容</span><span class="sxs-lookup"><span data-stu-id="1e469-164">Related content</span></span>

<span data-ttu-id="1e469-165">[管理网站存储限制](/sharepoint/manage-site-collection-storage-limits) (文章) </span><span class="sxs-lookup"><span data-stu-id="1e469-165">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="1e469-166">[在本文OneDrive设置 (](/onedrive/set-default-storage-space)用户) </span><span class="sxs-lookup"><span data-stu-id="1e469-166">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space) (article)</span></span>
