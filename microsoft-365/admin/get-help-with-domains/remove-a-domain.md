---
title: 删除域
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: 了解如何从 Microsoft 365 中删除旧域，并将用户和组移动到另一个域。
ms.openlocfilehash: c5e629f0d683c6dc3e18b1278027ac3a88cc834b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399892"
---
# <a name="remove-a-domain"></a><span data-ttu-id="e2d29-103">删除域</span><span class="sxs-lookup"><span data-stu-id="e2d29-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e2d29-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="e2d29-104">The admin center is changing.</span></span> <span data-ttu-id="e2d29-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="e2d29-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="e2d29-106">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="e2d29-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e2d29-107">您是否正在删除您的域，因为您想要将其添加到其他 Microsoft 365 订阅计划？</span><span class="sxs-lookup"><span data-stu-id="e2d29-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="e2d29-108">或者只是想取消订阅？</span><span class="sxs-lookup"><span data-stu-id="e2d29-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="e2d29-109">可[更改计划或订阅](../../commerce/subscriptions/switch-to-a-different-plan.md)，也可[取消订阅](../../commerce/subscriptions/cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="e2d29-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="e2d29-110">步骤1：将用户移动到另一个域</span><span class="sxs-lookup"><span data-stu-id="e2d29-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="e2d29-111">移动用户</span><span class="sxs-lookup"><span data-stu-id="e2d29-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e2d29-112">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="e2d29-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e2d29-113">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="e2d29-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e2d29-114">选择 "**用户** > **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e2d29-115">选择要移动的所有用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="e2d29-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e2d29-116">在页面顶部选择 "**更多选项**" （**...**），然后选择 "**更改域**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="e2d29-117">在 "**更改域**" 窗格中，选择其他域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="e2d29-p103">如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。</span><span class="sxs-lookup"><span data-stu-id="e2d29-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2d29-120">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="e2d29-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e2d29-121">选择 "**用户** > **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e2d29-122">选择要移动的所有用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="e2d29-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e2d29-123">在页面顶部，选择 "**更多** > **编辑域**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e2d29-124">在 "**编辑域**" 窗格中，选择其他域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e2d29-p104">如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。</span><span class="sxs-lookup"><span data-stu-id="e2d29-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2d29-127">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="e2d29-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e2d29-128">选择 "**用户** > **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e2d29-129">选择要移动的所有用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="e2d29-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e2d29-130">在页面顶部，选择 "**更多** > **编辑域**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e2d29-131">在 "**编辑域**" 窗格中，选择其他域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e2d29-p105">如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。</span><span class="sxs-lookup"><span data-stu-id="e2d29-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="e2d29-134">移动您自己</span><span class="sxs-lookup"><span data-stu-id="e2d29-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e2d29-135">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="e2d29-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e2d29-136">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="e2d29-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e2d29-137">转到 "**用户** \> **活动用户**"，然后从列表中选择您的帐户。</span><span class="sxs-lookup"><span data-stu-id="e2d29-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="e2d29-138">在 "**帐户**" 选项卡上，选择 "**管理用户名**"，然后选择其他域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="e2d29-139">在顶部，选择您的帐户名称，然后选择 **"注销"。**</span><span class="sxs-lookup"><span data-stu-id="e2d29-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e2d29-140">使用新域登录并使用相同的密码登录。</span><span class="sxs-lookup"><span data-stu-id="e2d29-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e2d29-141">也可使用 PowerShell 将用户移动到另一个域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e2d29-142">有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="e2d29-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e2d29-143">若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="e2d29-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2d29-144">转到 "**用户** \> **活动用户**"，然后在列表中选择您的姓名。</span><span class="sxs-lookup"><span data-stu-id="e2d29-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e2d29-145">在 "**用户名/电子邮件**" 部分，选择 "**编辑**"，然后选择其他域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e2d29-146">选择 "**设置为主** > **保存** > **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e2d29-147">在顶部，选择您的帐户名称，然后选择 **"注销"。**</span><span class="sxs-lookup"><span data-stu-id="e2d29-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e2d29-148">使用新域登录并使用相同的密码登录。</span><span class="sxs-lookup"><span data-stu-id="e2d29-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e2d29-149">也可使用 PowerShell 将用户移动到另一个域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e2d29-150">有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="e2d29-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e2d29-151">若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="e2d29-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2d29-152">转到 "**用户** \> **活动用户**"，然后在列表中选择您的姓名。</span><span class="sxs-lookup"><span data-stu-id="e2d29-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e2d29-153">在 "**用户名/电子邮件**" 部分，选择 "**编辑**"，然后选择其他域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e2d29-154">选择 "**设置为主** > **保存** > **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e2d29-155">在顶部，选择您的帐户名称，然后选择 **"注销"。**</span><span class="sxs-lookup"><span data-stu-id="e2d29-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e2d29-156">使用新域登录并使用相同的密码登录。</span><span class="sxs-lookup"><span data-stu-id="e2d29-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e2d29-157">也可使用 PowerShell 将用户移动到另一个域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e2d29-158">有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="e2d29-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e2d29-159">若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="e2d29-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="e2d29-160">步骤2：将组移动到另一个域</span><span class="sxs-lookup"><span data-stu-id="e2d29-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e2d29-161">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="e2d29-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="e2d29-162">选择组名称，然后在 "**常规**" 选项卡的 "**电子邮件地址"** 下，选择 "主"，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="e2d29-163">使用下拉列表选择其他域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e2d29-164">依次选择“**保存**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="e2d29-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e2d29-165">对与要删除的域关联的任何组或通讯组列表重复此过程。</span><span class="sxs-lookup"><span data-stu-id="e2d29-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2d29-166">在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>" 中，转到 "**组** > **组**" 页面。</span><span class="sxs-lookup"><span data-stu-id="e2d29-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e2d29-167">选择组名称，然后选择 "**名称**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e2d29-168">使用下拉列表选择其他域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e2d29-169">依次选择“**保存**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="e2d29-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e2d29-170">对与要删除的域关联的任何组或通讯组列表重复此过程。</span><span class="sxs-lookup"><span data-stu-id="e2d29-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2d29-171">在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>" 中，转到 "**组** > **组**" 页面。</span><span class="sxs-lookup"><span data-stu-id="e2d29-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e2d29-172">选择组名称，然后选择 "**名称**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e2d29-173">使用下拉列表选择其他域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e2d29-174">依次选择“**保存**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="e2d29-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e2d29-175">对与要删除的域关联的任何组或通讯组列表重复此过程。</span><span class="sxs-lookup"><span data-stu-id="e2d29-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="e2d29-176">步骤3：删除旧域</span><span class="sxs-lookup"><span data-stu-id="e2d29-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e2d29-177">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="e2d29-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2d29-178">在管理中心中，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="e2d29-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2d29-179">在管理中心中，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="e2d29-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="e2d29-180">在 "**域**" 页上，选择要删除的域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="e2d29-181">在右侧窗格中，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="e2d29-182">按照任何其他提示操作，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e2d29-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="e2d29-183">删除域需要多长时间？</span><span class="sxs-lookup"><span data-stu-id="e2d29-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="e2d29-184">如果在许多地方（如安全组、通讯组列表、用户和 Microsoft 365 组）中未引用域，则 Microsoft 365 可能只需5分钟即可删除域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="e2d29-185">如果存在众多使用该域的引用，则删除域可能需要数小时（一天）。</span><span class="sxs-lookup"><span data-stu-id="e2d29-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="e2d29-p113">如果有数百或数千用户，使用 PowerShell 查询所有用户，然后将其移至另一个域。否则，可能大量用户将在 UI 中丢失，然后当你要删除域时，将无法删除而且找不到原因。有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="e2d29-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="e2d29-190">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="e2d29-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e2d29-191">不能从你的帐户中删除 [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 域。</span><span class="sxs-lookup"><span data-stu-id="e2d29-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="e2d29-p114">仍然无法正常工作？你的域可能需要手动删除。[请致电我们](../contact-support-for-business-products.md)，让我们打理一切！</span><span class="sxs-lookup"><span data-stu-id="e2d29-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="e2d29-195">相关文章</span><span class="sxs-lookup"><span data-stu-id="e2d29-195">Related articles</span></span>

[<span data-ttu-id="e2d29-196">关于域的常见问题</span><span class="sxs-lookup"><span data-stu-id="e2d29-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="e2d29-197">获取 Office 365 域的帮助</span><span class="sxs-lookup"><span data-stu-id="e2d29-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="e2d29-198">切换到其他 Microsoft 365 商业版计划</span><span class="sxs-lookup"><span data-stu-id="e2d29-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="e2d29-199">取消订阅</span><span class="sxs-lookup"><span data-stu-id="e2d29-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
