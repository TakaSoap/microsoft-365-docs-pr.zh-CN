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
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: 了解如何在 Microsoft 365 订阅中添加并减少文件存储。 借助额外的文件存储，可以在 SharePoint Online 和 OneDrive 中存储更多内容。
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114903"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="27474-104">为订阅添加存储空间</span><span class="sxs-lookup"><span data-stu-id="27474-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="27474-105">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="27474-105">The admin center is changing.</span></span> <span data-ttu-id="27474-106">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="27474-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="27474-107">如果你的 SharePoint Online 网站集存储空间即将用完，并且你的计划符合条件，则可以为你的订阅增加存储空间。</span><span class="sxs-lookup"><span data-stu-id="27474-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="27474-108">如果在可用加载项列表中看不到 **Office 365** 额外文件存储，这意味着你的计划不符合条件。</span><span class="sxs-lookup"><span data-stu-id="27474-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="27474-109">有关详细信息，请参阅我的 [计划是否符合条件？](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="27474-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="27474-110">如果你通过批量许可或云解决方案提供商购买了订阅，则不能直接从 Microsoft 为组织购买 **Office 365** 额外文件存储。</span><span class="sxs-lookup"><span data-stu-id="27474-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="27474-111">请联系你的代表或合作伙伴寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="27474-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="27474-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="27474-112">Before you begin</span></span>

<span data-ttu-id="27474-113">您必须是全局管理员或 SharePoint 管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="27474-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="27474-114">有关详细信息，请参阅[关于管理员角色](../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="27474-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="27474-115">查看可用存储</span><span class="sxs-lookup"><span data-stu-id="27474-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="27474-116">在 SharePoint 管理中心，转到<a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">"活动</a>网站"页，然后使用对组织具有管理员权限[](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="27474-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="27474-117">在页面的右上角，查看所有站点使用的存储量以及订阅的总存储量。</span><span class="sxs-lookup"><span data-stu-id="27474-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="27474-118">如果组织在 Office 365 中配置了多地理位置，则栏还显示跨所有地理位置使用的存储量。</span><span class="sxs-lookup"><span data-stu-id="27474-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![活动站点页面上的存储栏](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="27474-120">使用的存储空间不包括最近24-48小时内所做的更改。</span><span class="sxs-lookup"><span data-stu-id="27474-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="27474-121">以全局管理员或 SharePoint 管理员状态登录，然后选择"管理"磁贴 https://portal.office.de 以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="27474-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="27474-122">如果你看到一条消息，表明你无权访问该页面，这意味着你组织中没有 Microsoft 365 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="27474-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="27474-123">在左窗格中的"管理 **中心"** 下，选择 **"SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="27474-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="27474-124">如果看到经典 SharePoint 管理中心，请选择页面顶部的“**立即打开**”，打开新的 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="27474-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="27474-125">在新的 SharePoint 管理中心的左侧窗格中，选择“**活动网站数**”。</span><span class="sxs-lookup"><span data-stu-id="27474-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="27474-126">在页面的右上角，查看所有站点使用的存储量以及订阅的总存储量。</span><span class="sxs-lookup"><span data-stu-id="27474-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![活动站点页面上的存储栏](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="27474-128">使用的存储空间不包括最近24-48小时内所做的更改。</span><span class="sxs-lookup"><span data-stu-id="27474-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="27474-129">以全局管理员或 SharePoint 管理员状态登录，然后选择"管理"磁贴 https://login.partner.microsoftonline.cn/ 以打开管理中心。</span><span class="sxs-lookup"><span data-stu-id="27474-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="27474-130"> (如果看到一条消息，表明你无权访问页面，这意味着你组织中没有 Microsoft 365 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="27474-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="27474-131">在左窗格中的"管理 **中心"** 下，选择 **"SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="27474-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="27474-132">如果看到经典 SharePoint 管理中心，请选择页面顶部的“**立即打开**”，打开新的 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="27474-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="27474-133">在新的 SharePoint 管理中心的左侧窗格中，选择“**活动网站数**”。</span><span class="sxs-lookup"><span data-stu-id="27474-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="27474-134">在页面的右上角，查看所有站点使用的存储量以及订阅的总存储量。</span><span class="sxs-lookup"><span data-stu-id="27474-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![活动站点页面上的存储栏](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="27474-136">使用的存储空间不包括最近24-48小时内所做的更改。</span><span class="sxs-lookup"><span data-stu-id="27474-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="27474-137">确定你使用的存储空间后，你可以为订阅添加或删除存储空间。</span><span class="sxs-lookup"><span data-stu-id="27474-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="27474-138">若要了解添加存储空间需要多少费用，请按照本文中的步骤操作，在购买之前查看定价信息。</span><span class="sxs-lookup"><span data-stu-id="27474-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="27474-139">有关设置网站集存储限制的信息，请参阅["管理网站集存储限制"。](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="27474-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="27474-140">将存储添加到订阅</span><span class="sxs-lookup"><span data-stu-id="27474-140">Add storage to your subscription</span></span>

<span data-ttu-id="27474-141">如果尚未为订阅购买额外存储空间，可以这样做。</span><span class="sxs-lookup"><span data-stu-id="27474-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="27474-142">在管理中心，转到" **帐单** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">购买服务"</a> 页。</span><span class="sxs-lookup"><span data-stu-id="27474-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="27474-143">在"购买服务 **"** 页的底部，选择 **"加载项"。**</span><span class="sxs-lookup"><span data-stu-id="27474-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="27474-144">选择 **Office 365 额外文件存储**。</span><span class="sxs-lookup"><span data-stu-id="27474-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="27474-145">在 **"Office 365** 额外文件存储"页上，如果显示，请选择基本订阅，然后输入要添加的存储 GB 数。</span><span class="sxs-lookup"><span data-stu-id="27474-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="27474-146">选择 **"现在签出"。**</span><span class="sxs-lookup"><span data-stu-id="27474-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="27474-147">在"**此外观如何？"** 页上，验证所选的存储 GB 数，查看定价信息，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="27474-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="27474-148">在 **"完成订单"** 页上，验证总计。</span><span class="sxs-lookup"><span data-stu-id="27474-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="27474-149">如果需要进行任何更改，请选择"编辑 **顺序"。**</span><span class="sxs-lookup"><span data-stu-id="27474-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="27474-150">如果订单需要信用检查，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="27474-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="27474-151">完成后，选择"**下订单转到** \> **管理员主页"。**</span><span class="sxs-lookup"><span data-stu-id="27474-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="27474-152">在管理中心，转到"**计费** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅"</a>页。  </span><span class="sxs-lookup"><span data-stu-id="27474-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="27474-153">在 **"订阅"** 页上，选择要添加存储空间的订阅，然后选择 **"加载项"。**</span><span class="sxs-lookup"><span data-stu-id="27474-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="27474-155">如果你 **看不到加载项，** 并且你的订阅是通过合作伙伴购买的，请选择"批量许可服务中心" (**VLSC) 。**</span><span class="sxs-lookup"><span data-stu-id="27474-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="27474-156">选择 **"购买加载项"。**</span><span class="sxs-lookup"><span data-stu-id="27474-156">Select **Buy add-ons**.</span></span>

    ![在管理中心的"订阅"页面上购买加载项链接。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="27474-158">在"**购买服务**"页上，将鼠标悬停在 **Office 365** 额外文件存储上或点击，然后选择"立即 **购买"。**</span><span class="sxs-lookup"><span data-stu-id="27474-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="27474-159">输入所需的用户许可证数量，如果显示，则选择基本订阅。</span><span class="sxs-lookup"><span data-stu-id="27474-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="27474-160">选择 **"现在签出"。**</span><span class="sxs-lookup"><span data-stu-id="27474-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="27474-161">在"**此外观如何？"** 页上，验证所选的存储 GB 数，查看定价信息，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="27474-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="27474-162">在"**完成订单"** 页上，选择 **"下订单"。**</span><span class="sxs-lookup"><span data-stu-id="27474-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="27474-163">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="27474-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="27474-164">在 **"订阅"** 页上，选择要添加存储空间的订阅，然后选择 **"加载项"。**</span><span class="sxs-lookup"><span data-stu-id="27474-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="27474-166">如果你 **看不到加载项，** 并且你的订阅是通过合作伙伴购买的，请选择"批量许可服务中心" (**VLSC) 。**</span><span class="sxs-lookup"><span data-stu-id="27474-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="27474-167">选择 **"购买加载项"。**</span><span class="sxs-lookup"><span data-stu-id="27474-167">Select **Buy add-ons**.</span></span>

    ![在管理中心的"订阅"页面上购买加载项链接。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="27474-169">在"**购买服务**"页上，将鼠标悬停在 **Office 365** 额外文件存储上或点击，然后选择"立即 **购买"。**</span><span class="sxs-lookup"><span data-stu-id="27474-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="27474-170">输入所需的用户许可证数量，如果显示，则选择基本订阅。</span><span class="sxs-lookup"><span data-stu-id="27474-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="27474-171">选择 **"现在签出"。**</span><span class="sxs-lookup"><span data-stu-id="27474-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="27474-172">在"**此外观如何？"** 页上，验证所选的存储 GB 数，查看定价信息，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="27474-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="27474-173">在"**完成订单"** 页上，选择 **"下订单"。**</span><span class="sxs-lookup"><span data-stu-id="27474-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="27474-174">增加或减少存储空间</span><span class="sxs-lookup"><span data-stu-id="27474-174">Increase or decrease storage</span></span>

<span data-ttu-id="27474-175">如果已经通过 **Office 365** 额外文件存储加载项购买了额外的文件存储空间，可以使用这些步骤来增加或减少订阅的额外存储空间。</span><span class="sxs-lookup"><span data-stu-id="27474-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="27474-176">可以将存储减小到 1 GB 以下。</span><span class="sxs-lookup"><span data-stu-id="27474-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="27474-177">若要删除所有额外的存储空间，请联系 [支持人员](../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="27474-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="27474-178">在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="27474-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="27474-179">在 **"产品** "选项卡上，选择包含 **Office 365** 额外文件存储加载项的订阅。</span><span class="sxs-lookup"><span data-stu-id="27474-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="27474-180">在产品详细信息页面上的"加载项"**部分，** 选择"**管理加载项"。**</span><span class="sxs-lookup"><span data-stu-id="27474-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="27474-181">在 **"管理加载项"窗格中**，从加载项列表中选择 **"Office 365 额外文件存储"。** </span><span class="sxs-lookup"><span data-stu-id="27474-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="27474-182">在 **"数量** "文本框中，输入订阅的存储空间的 GB 数。</span><span class="sxs-lookup"><span data-stu-id="27474-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="27474-183">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="27474-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="27474-184">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="27474-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="27474-185">在 **"订阅"** 页上，选择 **"加载项"。**</span><span class="sxs-lookup"><span data-stu-id="27474-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="27474-187">如果你 **看不到加载项，** 并且你的订阅是通过合作伙伴购买的，请选择"批量许可服务中心" (**VLSC) 。**</span><span class="sxs-lookup"><span data-stu-id="27474-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="27474-188">在 **"Office 365 额外文件存储"下**，选择 **"更改数量"。**</span><span class="sxs-lookup"><span data-stu-id="27474-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    !['更改数量'链接。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="27474-190">在右侧窗格中，输入所需的总 GB 数，然后选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="27474-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="27474-191">例如，如果你目前拥有 200 GB 的额外文件存储空间，但你只需要 100 GB，则可以在框中输入" **100**"。</span><span class="sxs-lookup"><span data-stu-id="27474-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="27474-192">选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="27474-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="27474-193">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="27474-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="27474-194">在 **"订阅"** 页上，选择 **"加载项"。**</span><span class="sxs-lookup"><span data-stu-id="27474-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="27474-196">如果你 **看不到加载项，** 并且你的订阅是通过合作伙伴购买的，请选择"批量许可服务中心" (**VLSC) 。**</span><span class="sxs-lookup"><span data-stu-id="27474-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="27474-197">在 **"Office 365 额外文件存储"下**，选择 **"更改数量"。**</span><span class="sxs-lookup"><span data-stu-id="27474-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    !['更改数量'链接。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="27474-199">在右侧窗格中，输入所需的总 GB 数，然后选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="27474-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="27474-200">例如，如果你目前拥有 200 GB 的额外文件存储空间，但你只需要 100 GB，则可以在框中输入" **100**"。</span><span class="sxs-lookup"><span data-stu-id="27474-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="27474-201">选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="27474-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="27474-202">我的计划是否符合使用 Office 365 额外文件存储空间的条件？</span><span class="sxs-lookup"><span data-stu-id="27474-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="27474-203">Office 365 额外文件存储空间可以用于以下订阅：</span><span class="sxs-lookup"><span data-stu-id="27474-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="27474-204">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="27474-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="27474-205">Office 365 企业版 E2</span><span class="sxs-lookup"><span data-stu-id="27474-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="27474-206">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="27474-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="27474-207">Office 365 企业版 E4</span><span class="sxs-lookup"><span data-stu-id="27474-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="27474-208">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="27474-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="27474-209">具有 SharePoint 计划 1 的 Office 网页</span><span class="sxs-lookup"><span data-stu-id="27474-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="27474-210">具有 SharePoint 计划 2 的 Office 网页</span><span class="sxs-lookup"><span data-stu-id="27474-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="27474-211">SharePoint Online 计划 1</span><span class="sxs-lookup"><span data-stu-id="27474-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="27474-212">SharePoint Online 计划 2</span><span class="sxs-lookup"><span data-stu-id="27474-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="27474-213">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="27474-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="27474-214">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="27474-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="27474-215">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="27474-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="27474-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="27474-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="27474-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="27474-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="27474-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="27474-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="27474-219">Office 365 额外文件存储还可用于 GCC、GCC High 和 DOD 计划。</span><span class="sxs-lookup"><span data-stu-id="27474-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="27474-220">相关内容</span><span class="sxs-lookup"><span data-stu-id="27474-220">Related content</span></span>

<span data-ttu-id="27474-221">[管理网站存储限制 (](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) 文章) </span><span class="sxs-lookup"><span data-stu-id="27474-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="27474-222">[设置 OneDrive 用户的默认存储空间， (](https://docs.microsoft.com/onedrive/set-default-storage-space) 文章) </span><span class="sxs-lookup"><span data-stu-id="27474-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
