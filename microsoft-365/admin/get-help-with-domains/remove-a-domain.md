---
title: 从 Office 365 中删除域
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: 了解如何从 Office 365 中删除旧域，并将用户和组移动到另一个域。
ms.openlocfilehash: 621b50384b39a21bc0bf5256841c703b3ee0f74a
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210364"
---
# <a name="remove-a-domain-from-office-365"></a><span data-ttu-id="8259e-103">从 Office 365 中删除域</span><span class="sxs-lookup"><span data-stu-id="8259e-103">Remove a domain from Office 365</span></span>

<span data-ttu-id="8259e-104">撰稿人：[![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span><span class="sxs-lookup"><span data-stu-id="8259e-104">Contributors: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span></span>
  
 <span data-ttu-id="8259e-105">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="8259e-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8259e-p101">是否由于想将域添加到其他 Office 365 订阅计划而要删除该域？或者只是想取消订阅？可[更改计划或订阅](../../commerce/subscriptions/switch-to-a-different-plan.md)，也可[取消订阅](../../commerce/subscriptions/cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="8259e-p101">Are you removing your domain because you want to add it to a different Office 365 subscription plan? Or do you just want to cancel your subscription? You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="8259e-109">步骤1：将用户移动到另一个域</span><span class="sxs-lookup"><span data-stu-id="8259e-109">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="8259e-110">移动用户</span><span class="sxs-lookup"><span data-stu-id="8259e-110">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="8259e-111">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="8259e-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="8259e-112">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="8259e-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="8259e-113">选择 "**用户** > **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="8259e-114">选择要移动的所有用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="8259e-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="8259e-115">在页面顶部选择 "**更多选项**" （**...**），然后选择 "**更改域**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="8259e-116">在 "**更改域**" 窗格中，选择其他域。</span><span class="sxs-lookup"><span data-stu-id="8259e-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="8259e-p102">如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。</span><span class="sxs-lookup"><span data-stu-id="8259e-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8259e-119">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="8259e-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="8259e-120">选择 "**用户** > **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="8259e-121">选择要移动的所有用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="8259e-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="8259e-122">在页面顶部，选择 "**更多** > **编辑域**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="8259e-123">在 "**编辑域**" 窗格中，选择其他域。</span><span class="sxs-lookup"><span data-stu-id="8259e-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="8259e-p103">如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。</span><span class="sxs-lookup"><span data-stu-id="8259e-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8259e-126">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="8259e-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="8259e-127">选择 "**用户** > **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="8259e-128">选择要移动的所有用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="8259e-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="8259e-129">在页面顶部，选择 "**更多** > **编辑域**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="8259e-130">在 "**编辑域**" 窗格中，选择其他域。</span><span class="sxs-lookup"><span data-stu-id="8259e-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="8259e-p104">如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。</span><span class="sxs-lookup"><span data-stu-id="8259e-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="8259e-133">移动您自己</span><span class="sxs-lookup"><span data-stu-id="8259e-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="8259e-134">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="8259e-134">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="8259e-135">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="8259e-135">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="8259e-136">转到 "**用户** \> **活动用户**"，然后从列表中选择您的帐户。</span><span class="sxs-lookup"><span data-stu-id="8259e-136">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="8259e-137">在 "**帐户**" 选项卡上，选择 "**管理用户名**"，然后选择其他域。</span><span class="sxs-lookup"><span data-stu-id="8259e-137">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="8259e-138">在顶部，选择您的帐户名称，然后选择 **"注销"。**</span><span class="sxs-lookup"><span data-stu-id="8259e-138">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="8259e-139">使用新域登录并使用相同的密码登录。</span><span class="sxs-lookup"><span data-stu-id="8259e-139">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="8259e-140">也可使用 PowerShell 将用户移动到另一个域。</span><span class="sxs-lookup"><span data-stu-id="8259e-140">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="8259e-141">有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="8259e-141">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="8259e-142">若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="8259e-142">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8259e-143">转到 "**用户** \> **活动用户**"，然后在列表中选择您的姓名。</span><span class="sxs-lookup"><span data-stu-id="8259e-143">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="8259e-144">在 "**用户名/电子邮件**" 部分，选择 "**编辑**"，然后选择其他域。</span><span class="sxs-lookup"><span data-stu-id="8259e-144">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="8259e-145">选择 "**设置为主** > **保存** > **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-145">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="8259e-146">在顶部，选择您的帐户名称，然后选择 **"注销"。**</span><span class="sxs-lookup"><span data-stu-id="8259e-146">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="8259e-147">使用新域登录并使用相同的密码登录。</span><span class="sxs-lookup"><span data-stu-id="8259e-147">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="8259e-148">也可使用 PowerShell 将用户移动到另一个域。</span><span class="sxs-lookup"><span data-stu-id="8259e-148">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="8259e-149">有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="8259e-149">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="8259e-150">若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="8259e-150">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8259e-151">转到 "**用户** \> **活动用户**"，然后在列表中选择您的姓名。</span><span class="sxs-lookup"><span data-stu-id="8259e-151">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="8259e-152">在 "**用户名/电子邮件**" 部分，选择 "**编辑**"，然后选择其他域。</span><span class="sxs-lookup"><span data-stu-id="8259e-152">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="8259e-153">选择 "**设置为主** > **保存** > **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-153">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="8259e-154">在顶部，选择您的帐户名称，然后选择 **"注销"。**</span><span class="sxs-lookup"><span data-stu-id="8259e-154">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="8259e-155">使用新域登录并使用相同的密码登录。</span><span class="sxs-lookup"><span data-stu-id="8259e-155">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="8259e-156">也可使用 PowerShell 将用户移动到另一个域。</span><span class="sxs-lookup"><span data-stu-id="8259e-156">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="8259e-157">有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="8259e-157">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="8259e-158">若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="8259e-158">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="8259e-159">步骤2：将组移动到另一个域</span><span class="sxs-lookup"><span data-stu-id="8259e-159">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8259e-160">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="8259e-160">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="8259e-161">选择组名称，然后在 "**常规**" 选项卡的 "**电子邮件地址"** 下，选择 "主"，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-161">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="8259e-162">使用下拉列表选择其他域。</span><span class="sxs-lookup"><span data-stu-id="8259e-162">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="8259e-163">依次选择“**保存**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="8259e-163">Select **Save**, then **Close**.</span></span> <span data-ttu-id="8259e-164">对与要删除的域关联的任何组或通讯组列表重复此过程。</span><span class="sxs-lookup"><span data-stu-id="8259e-164">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8259e-165">在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>" 中，转到 "**组** > **组**" 页面。</span><span class="sxs-lookup"><span data-stu-id="8259e-165">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="8259e-166">选择组名称，然后选择 "**名称**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-166">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="8259e-167">使用下拉列表选择其他域。</span><span class="sxs-lookup"><span data-stu-id="8259e-167">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="8259e-168">依次选择“**保存**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="8259e-168">Select **Save**, then **Close**.</span></span> <span data-ttu-id="8259e-169">对与要删除的域关联的任何组或通讯组列表重复此过程。</span><span class="sxs-lookup"><span data-stu-id="8259e-169">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8259e-170">在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>" 中，转到 "**组** > **组**" 页面。</span><span class="sxs-lookup"><span data-stu-id="8259e-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="8259e-171">选择组名称，然后选择 "**名称**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-171">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="8259e-172">使用下拉列表选择其他域。</span><span class="sxs-lookup"><span data-stu-id="8259e-172">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="8259e-173">依次选择“**保存**”和“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="8259e-173">Select **Save**, then **Close**.</span></span> <span data-ttu-id="8259e-174">对与要删除的域关联的任何组或通讯组列表重复此过程。</span><span class="sxs-lookup"><span data-stu-id="8259e-174">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="8259e-175">步骤3：删除旧域</span><span class="sxs-lookup"><span data-stu-id="8259e-175">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8259e-176">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="8259e-176">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8259e-177">在管理中心中，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8259e-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8259e-178">在管理中心中，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8259e-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="8259e-179">在 "**域**" 页上，选择要删除的域。</span><span class="sxs-lookup"><span data-stu-id="8259e-179">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="8259e-180">在右侧窗格中，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-180">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="8259e-181">按照任何其他提示操作，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8259e-181">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="8259e-182">删除域需要多长时间？</span><span class="sxs-lookup"><span data-stu-id="8259e-182">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="8259e-183">如果在很多地方（如安全组、通讯组列表、用户和 Office 365 组）中未引用域，则 Office 365 只需5分钟即可删除域。</span><span class="sxs-lookup"><span data-stu-id="8259e-183">It can take as little as 5 minutes for Office 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Office 365 groups.</span></span> <span data-ttu-id="8259e-184">如果存在众多使用该域的引用，则删除域可能需要数小时（一天）。</span><span class="sxs-lookup"><span data-stu-id="8259e-184">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="8259e-p112">如果有数百或数千用户，使用 PowerShell 查询所有用户，然后将其移至另一个域。否则，可能大量用户将在 UI 中丢失，然后当你要删除域时，将无法删除而且找不到原因。有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="8259e-p112">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="8259e-189">是否仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="8259e-189">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="8259e-190">不能从你的帐户中删除 [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) 域。</span><span class="sxs-lookup"><span data-stu-id="8259e-190">You can't remove the [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) domain from your account.</span></span>
  
<span data-ttu-id="8259e-p113">仍然无法正常工作？你的域可能需要手动删除。[请致电我们](../contact-support-for-business-products.md)，让我们打理一切！</span><span class="sxs-lookup"><span data-stu-id="8259e-p113">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="8259e-194">相关文章</span><span class="sxs-lookup"><span data-stu-id="8259e-194">Related articles</span></span>

[<span data-ttu-id="8259e-195">关于域的常见问题</span><span class="sxs-lookup"><span data-stu-id="8259e-195">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="8259e-196">获取 Office 365 域的帮助</span><span class="sxs-lookup"><span data-stu-id="8259e-196">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="8259e-197">切换到其他 Office 365 商业版计划</span><span class="sxs-lookup"><span data-stu-id="8259e-197">Switch to a different Office 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="8259e-198">取消订阅</span><span class="sxs-lookup"><span data-stu-id="8259e-198">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
