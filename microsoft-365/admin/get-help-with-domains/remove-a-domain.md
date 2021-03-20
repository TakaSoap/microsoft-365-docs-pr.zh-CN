---
title: 删除域
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: 了解如何从 Microsoft 365 中删除旧域，以及如何将用户和组移动到另一个域。
ms.openlocfilehash: f4281eb793e6a832e3bd7f31484a97ccd5065bf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915610"
---
# <a name="remove-a-domain"></a><span data-ttu-id="9cb65-103">删除域</span><span class="sxs-lookup"><span data-stu-id="9cb65-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9cb65-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="9cb65-104">The admin center is changing.</span></span> <span data-ttu-id="9cb65-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="9cb65-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="9cb65-106">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="9cb65-106">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9cb65-107">是否要删除域，因为你想要将其添加到其他 Microsoft 365 订阅计划中？</span><span class="sxs-lookup"><span data-stu-id="9cb65-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="9cb65-108">或者只是想取消订阅？</span><span class="sxs-lookup"><span data-stu-id="9cb65-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="9cb65-109">可[更改计划或订阅](../../commerce/subscriptions/switch-to-a-different-plan.md)，也可[取消订阅](../../commerce/subscriptions/cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="9cb65-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="9cb65-110">步骤 1：将用户移动到另一个域</span><span class="sxs-lookup"><span data-stu-id="9cb65-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="9cb65-111">移动用户</span><span class="sxs-lookup"><span data-stu-id="9cb65-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9cb65-112">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="9cb65-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="9cb65-113">选择 **"用户** > **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="9cb65-114">选中要移动的所有用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="9cb65-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="9cb65-115">选择 **页面顶部的**" (...) "，然后选择"更改 **域"。** </span><span class="sxs-lookup"><span data-stu-id="9cb65-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="9cb65-116">在" **更改域** "窗格中，选择其他域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="9cb65-p103">如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。</span><span class="sxs-lookup"><span data-stu-id="9cb65-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9cb65-119">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="9cb65-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="9cb65-120">选择 **"用户** > **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="9cb65-121">选中要移动的所有用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="9cb65-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="9cb65-122">在页面顶部，选择"更多 **编辑** > **域"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="9cb65-123">在" **编辑域"** 窗格中，选择其他域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="9cb65-p104">如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。</span><span class="sxs-lookup"><span data-stu-id="9cb65-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9cb65-126">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="9cb65-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="9cb65-127">选择 **"用户** > **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="9cb65-128">选中要移动的所有用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="9cb65-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="9cb65-129">在页面顶部，选择"更多 **编辑** > **域"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="9cb65-130">在" **编辑域"** 窗格中，选择其他域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="9cb65-p105">如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。</span><span class="sxs-lookup"><span data-stu-id="9cb65-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="9cb65-133">移动自己</span><span class="sxs-lookup"><span data-stu-id="9cb65-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9cb65-134">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="9cb65-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="9cb65-135">转到 **"用户** \> **""活动** 用户"，然后从列表中选择你的帐户。</span><span class="sxs-lookup"><span data-stu-id="9cb65-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="9cb65-136">在" **帐户"** 选项卡上， **选择"管理用户名**"，然后选择其他域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="9cb65-137">At the top， select your account name， then select **Sign Out**.</span><span class="sxs-lookup"><span data-stu-id="9cb65-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="9cb65-138">使用新域和相同的密码登录。</span><span class="sxs-lookup"><span data-stu-id="9cb65-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="9cb65-139">也可使用 PowerShell 将用户移动到另一个域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="9cb65-140">有关详细信息，请参阅 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="9cb65-140">See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="9cb65-141">若要设置默认域，请使用 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="9cb65-141">To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9cb65-142">转到 **"用户** \> **""** 活动用户"，在列表中选择你的姓名。</span><span class="sxs-lookup"><span data-stu-id="9cb65-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="9cb65-143">在" **用户名/电子邮件** "部分，选择" **编辑"，** 然后选择其他域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="9cb65-144">选择 **"设置为主保存** > **关闭** > **"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="9cb65-145">At the top， select your account name， then select **Sign Out**.</span><span class="sxs-lookup"><span data-stu-id="9cb65-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="9cb65-146">使用新域和相同的密码登录。</span><span class="sxs-lookup"><span data-stu-id="9cb65-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="9cb65-147">也可使用 PowerShell 将用户移动到另一个域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="9cb65-148">有关详细信息，请参阅 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="9cb65-148">See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="9cb65-149">若要设置默认域，请使用 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="9cb65-149">To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9cb65-150">转到 **"用户** \> **""** 活动用户"，在列表中选择你的姓名。</span><span class="sxs-lookup"><span data-stu-id="9cb65-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="9cb65-151">在" **用户名/电子邮件** "部分，选择" **编辑"，** 然后选择其他域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="9cb65-152">选择 **"设置为主保存** > **关闭** > **"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="9cb65-153">At the top， select your account name， then select **Sign Out**.</span><span class="sxs-lookup"><span data-stu-id="9cb65-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="9cb65-154">使用新域和相同的密码登录。</span><span class="sxs-lookup"><span data-stu-id="9cb65-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="9cb65-155">也可使用 PowerShell 将用户移动到另一个域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="9cb65-156">有关详细信息，请参阅 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="9cb65-156">See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="9cb65-157">若要设置默认域，请使用 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="9cb65-157">To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="9cb65-158">步骤 2：将组移动到另一个域</span><span class="sxs-lookup"><span data-stu-id="9cb65-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9cb65-159">在管理中心，转到组 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>页面。</span><span class="sxs-lookup"><span data-stu-id="9cb65-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="9cb65-160">选择组名称，然后在"电子邮件地址"下的"常规 **"** 选项卡上 **，选择"主**"，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="9cb65-161">使用下拉列表选择另一个域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="9cb65-162">依次选择“**保存**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9cb65-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="9cb65-163">对与要删除的域关联的任何组或通讯组列表重复此过程。</span><span class="sxs-lookup"><span data-stu-id="9cb65-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9cb65-164">在管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">中心</a>中，转到组 > **组** 页面。</span><span class="sxs-lookup"><span data-stu-id="9cb65-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="9cb65-165">选择组名称，然后选择 **"名称"** 旁边的"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="9cb65-166">使用下拉列表选择另一个域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="9cb65-167">依次选择“**保存**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9cb65-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="9cb65-168">对与要删除的域关联的任何组或通讯组列表重复此过程。</span><span class="sxs-lookup"><span data-stu-id="9cb65-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9cb65-169">在管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">中心</a>中，转到组 > **组** 页面。</span><span class="sxs-lookup"><span data-stu-id="9cb65-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="9cb65-170">选择组名称，然后选择 **"名称"** 旁边的"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="9cb65-171">使用下拉列表选择另一个域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="9cb65-172">依次选择“**保存**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9cb65-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="9cb65-173">对与要删除的域关联的任何组或通讯组列表重复此过程。</span><span class="sxs-lookup"><span data-stu-id="9cb65-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="9cb65-174">步骤 3：删除旧域</span><span class="sxs-lookup"><span data-stu-id="9cb65-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9cb65-175">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="9cb65-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9cb65-176">在管理中心，转到"设置 **域** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="9cb65-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9cb65-177">在管理中心，转到"设置 **域** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="9cb65-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="9cb65-178">在 **"域** "页面上，选择要删除的域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="9cb65-179">在右侧窗格中，选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="9cb65-180">按照任何其他提示，然后选择关闭 **。**</span><span class="sxs-lookup"><span data-stu-id="9cb65-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="9cb65-181">删除域需要多长时间？</span><span class="sxs-lookup"><span data-stu-id="9cb65-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="9cb65-182">如果域未在安全组、通讯组列表、用户和 Microsoft 365 组等多个位置引用，Microsoft 365 删除域可能需要 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="9cb65-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="9cb65-183">如果存在众多使用该域的引用，则删除域可能需要数小时（一天）。</span><span class="sxs-lookup"><span data-stu-id="9cb65-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="9cb65-p113">如果有数百或数千用户，使用 PowerShell 查询所有用户，然后将其移至另一个域。否则，可能大量用户将在 UI 中丢失，然后当你要删除域时，将无法删除而且找不到原因。有关详细信息，请参阅 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。若要设置默认域，请使用 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="9cb65-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="9cb65-188">仍然需要帮助？</span><span class="sxs-lookup"><span data-stu-id="9cb65-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="9cb65-189">不能从你的帐户中删除 [".onmicrosoft.com"](../setup/domains-faq.yml) 域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-189">You can't remove the [".onmicrosoft.com"](../setup/domains-faq.yml) domain from your account.</span></span> <span data-ttu-id="9cb65-190">删除域时，用户帐户将恢复为".onmicrosoft.com"地址作为主 SMTP/UserprincipalName。</span><span class="sxs-lookup"><span data-stu-id="9cb65-190">When you remove a domain, user accounts will revert back to the ".onmicrosoft.com" address as the Primary SMTP/UserprincipalName.</span></span>
  
<span data-ttu-id="9cb65-191">仍然无法工作？</span><span class="sxs-lookup"><span data-stu-id="9cb65-191">Still not working?</span></span> <span data-ttu-id="9cb65-192">可能需要手动删除你的域。</span><span class="sxs-lookup"><span data-stu-id="9cb65-192">Your domain might need to be manually removed.</span></span> <span data-ttu-id="9cb65-193">[请致电我们](../contact-support-for-business-products.md) ，我们将帮助你处理！</span><span class="sxs-lookup"><span data-stu-id="9cb65-193">[Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="9cb65-194">相关文章</span><span class="sxs-lookup"><span data-stu-id="9cb65-194">Related articles</span></span>

[<span data-ttu-id="9cb65-195">关于域的常见问题</span><span class="sxs-lookup"><span data-stu-id="9cb65-195">Domains FAQ</span></span>](../setup/domains-faq.yml)

[<span data-ttu-id="9cb65-196">切换到其他 Microsoft 365 商业版计划</span><span class="sxs-lookup"><span data-stu-id="9cb65-196">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="9cb65-197">取消订阅</span><span class="sxs-lookup"><span data-stu-id="9cb65-197">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)