---
title: 管理支付方式
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: 了解如何在 Microsoft 365 管理中心中管理你的支付方式。
ms.openlocfilehash: d31da19c10eb61719ba813d271dbdcf573a5aff3
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322155"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="82169-103">管理支付方式</span><span class="sxs-lookup"><span data-stu-id="82169-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="82169-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="82169-104">The admin center is changing.</span></span> <span data-ttu-id="82169-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="82169-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="82169-106">当您从 Microsoft 购买业务产品或服务时，您可以使用现有的付款方式，也可以添加一个新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="82169-107">您可以使用信用卡或借记卡或银行帐户支付购买的物品。</span><span class="sxs-lookup"><span data-stu-id="82169-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="82169-108">如果您的企业帐户有一个记帐配置文件，并且您是帐单档案文件所有者或帐单个人资料参与者，则可以使用信用卡或发票付款支持的计费配置文件来进行购买或支付帐单。</span><span class="sxs-lookup"><span data-stu-id="82169-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="82169-109">如果您是帐单发票管理者，则只能使用计费配置文件来支付帐单。</span><span class="sxs-lookup"><span data-stu-id="82169-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="82169-110">若要了解有关计费配置文件和角色的详细信息，请参阅[管理计费配置文件](manage-billing-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="82169-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="82169-111">如果你的企业帐户没有记帐配置文件，则任何全局或帐单管理员都可以管理和使用添加到企业帐户的任何银行帐户。</span><span class="sxs-lookup"><span data-stu-id="82169-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="82169-112">但是，您只能管理或使用您添加的信用卡。</span><span class="sxs-lookup"><span data-stu-id="82169-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="82169-113">在某些国家或地区不提供用银行帐户付款的选项。</span><span class="sxs-lookup"><span data-stu-id="82169-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="82169-114">您必须使用与您的租户从同一国家/地区颁发的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="82169-115">添加付款方式</span><span class="sxs-lookup"><span data-stu-id="82169-115">Add a payment method</span></span>

<span data-ttu-id="82169-116">添加付款方法不会将任何订阅关联。</span><span class="sxs-lookup"><span data-stu-id="82169-116">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="82169-117">若要将单个订阅分配给付款方法，请参阅[更改单个订阅的付款方式](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="82169-117">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="82169-118">若要将使用其他付款方式的所有订阅替换为新的，请参阅[替换付款方法](#replace-a-payment-method)。</span><span class="sxs-lookup"><span data-stu-id="82169-118">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="82169-119">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-119">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="82169-120">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-120">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="82169-121">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-121">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="82169-122">选择“**添加付款方式**”。</span><span class="sxs-lookup"><span data-stu-id="82169-122">Select **Add a payment method**.</span></span>

3. <span data-ttu-id="82169-123">在“**付款方式**”页面上，从下拉菜单中选择一种付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-123">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>

4. <span data-ttu-id="82169-124">输入新卡或银行帐户的信息，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="82169-124">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="82169-125">更新付款方式详细信息</span><span class="sxs-lookup"><span data-stu-id="82169-125">Update payment method details</span></span>

<span data-ttu-id="82169-126">您可以更改现有付款方式的信用卡或借记卡、帐单地址或到期日期的名称。</span><span class="sxs-lookup"><span data-stu-id="82169-126">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="82169-127">但是，不能更改卡片或帐号。</span><span class="sxs-lookup"><span data-stu-id="82169-127">However, you can't change the card or account number.</span></span> <span data-ttu-id="82169-128">如果帐户号码已更改，请将[其替换为其他付款方式](#replace-a-payment-method)，然后[删除旧的](#delete-a-payment-method)付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-128">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="82169-129">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-129">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="82169-130">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-130">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="82169-131">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-131">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="82169-132">选择要更新的付款方式的行。</span><span class="sxs-lookup"><span data-stu-id="82169-132">Select the row of the payment method to update.</span></span> <span data-ttu-id="82169-133">在右侧窗格中，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="82169-133">In the right pane, select **Edit**.</span></span>

3. <span data-ttu-id="82169-134">更新付款方式信息，包括信用卡或借记卡上的姓名、帐单地址或到期日期，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="82169-134">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="82169-135">替换付款方法</span><span class="sxs-lookup"><span data-stu-id="82169-135">Replace a payment method</span></span>

<span data-ttu-id="82169-136">当您替换付款方式时，会将其替换为使用相同付款方式的所有订阅和计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="82169-136">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="82169-137">替换支付方式不会删除现有的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-137">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="82169-138">您仍可以选择和使用其他订阅和计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="82169-138">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="82169-139">若要更改单个订阅的付款方式，请参阅[更改单个订阅的支付方式](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="82169-139">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="82169-140">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-140">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="82169-141">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-141">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="82169-142">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-142">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="82169-143">选择要替换的付款方法的行。</span><span class="sxs-lookup"><span data-stu-id="82169-143">Select the row of the payment method to replace.</span></span> <span data-ttu-id="82169-144">右侧窗格列出了所有帐单配置文件和使用所选付款方式的各个订阅。</span><span class="sxs-lookup"><span data-stu-id="82169-144">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>

3. <span data-ttu-id="82169-145">在右侧窗格中，选择 "**替换所有项目的付款方式**"。</span><span class="sxs-lookup"><span data-stu-id="82169-145">In the right pane, select **Replace payment method for all items**.</span></span>

4. <span data-ttu-id="82169-146">若要使用现有的付款方式，请从下拉列表中选择一个，然后选择 "**替换**"。</span><span class="sxs-lookup"><span data-stu-id="82169-146">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="82169-147">如果你有与帐单配置文件关联的订阅，则只能使用信用卡或借记卡支付。</span><span class="sxs-lookup"><span data-stu-id="82169-147">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="82169-148">如果您在 "**付款方式**" 页上列出了银行帐户，则不能在下拉列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="82169-148">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>

5. <span data-ttu-id="82169-149">若要添加新的付款方式，请选择 "**添加支付方式**"。</span><span class="sxs-lookup"><span data-stu-id="82169-149">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="82169-150">在 "**添加付款方法**" 窗格中，输入帐户信息，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="82169-150">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="82169-151">您必须使用与您的租户来自同一国家/地区的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-151">You must use a payment method from the same country as your tenant.</span></span>

7. <span data-ttu-id="82169-152">已在下拉列表中选择新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-152">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="82169-153">选择“**替换**”。</span><span class="sxs-lookup"><span data-stu-id="82169-153">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="82169-154">更改单个订阅的付款方式</span><span class="sxs-lookup"><span data-stu-id="82169-154">Change a payment method for a single subscription</span></span>

<span data-ttu-id="82169-155">您可以更改用于支付单个订阅的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-155">You can change the payment method used to pay for a single subscription.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="82169-156">在管理中心中，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="82169-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="82169-157">在管理中心中，转到“**计费**”>“**你的产品**”页面。</span><span class="sxs-lookup"><span data-stu-id="82169-157">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="82169-158">在管理中心中，转到“**计费**”>“**你的产品**”页面。</span><span class="sxs-lookup"><span data-stu-id="82169-158">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

2. <span data-ttu-id="82169-159">在 "**订阅**" 选项卡上，选择要使用备用付款方式支付的订阅。</span><span class="sxs-lookup"><span data-stu-id="82169-159">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span>

3. <span data-ttu-id="82169-160">在 "**帐单**" 下，选择 "付款方法" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="82169-160">Under **Billing**, next to the payment method, select **Edit**.</span></span>

4. <span data-ttu-id="82169-161">在现有付款方法旁边，选择 "**更改**"。</span><span class="sxs-lookup"><span data-stu-id="82169-161">Next to your existing payment method, select **Change**.</span></span>

5. <span data-ttu-id="82169-162">从下拉列表中，选择另一种付款方式，或选择添加付款方法。</span><span class="sxs-lookup"><span data-stu-id="82169-162">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>

6. <span data-ttu-id="82169-163">如果添加付款方法，请输入信用卡或帐户详细信息，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="82169-163">If you add a payment method, enter the card or account details, then select **Save**.</span></span>

7. <span data-ttu-id="82169-164">确认所选的支付方式正确，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="82169-164">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="82169-165">删除付款方法</span><span class="sxs-lookup"><span data-stu-id="82169-165">Delete a payment method</span></span>

<span data-ttu-id="82169-166">您只能删除未附加到订阅或帐单配置文件的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-166">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="82169-167">这适用于所有订阅（无论其状态如何）。</span><span class="sxs-lookup"><span data-stu-id="82169-167">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="82169-168">删除没有订阅或附加的计费配置文件的付款方式</span><span class="sxs-lookup"><span data-stu-id="82169-168">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="82169-169">如果付款方法不与任何订阅或计费配置文件关联，则可以立即将其删除。</span><span class="sxs-lookup"><span data-stu-id="82169-169">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="82169-170">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-170">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="82169-171">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-171">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="82169-172">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-172">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="82169-173">找到要删除的付款方法，选择三个点，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="82169-173">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>

3. <span data-ttu-id="82169-174">在右侧窗格的底部，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="82169-174">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="82169-175">删除带有订阅或附加的计费配置文件的付款方式</span><span class="sxs-lookup"><span data-stu-id="82169-175">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="82169-176">如果向任何订阅或计费配置文件附加了付款方式，请首先将其替换为现有付款方式，或添加新的付款方式，然后删除旧的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-176">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="82169-177">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">方法</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-177">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="82169-178">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-178">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="82169-179">在 "管理中心" 中，转到 "**计费** > **帐单 & 付款** > **方法**" 页。</span><span class="sxs-lookup"><span data-stu-id="82169-179">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="82169-180">选择要删除的付款方法所在的行。</span><span class="sxs-lookup"><span data-stu-id="82169-180">Select the row for the payment method to delete.</span></span> <span data-ttu-id="82169-181">右侧窗格中列出了使用该付款方式的现有订阅。</span><span class="sxs-lookup"><span data-stu-id="82169-181">The right pane lists existing subscriptions that use that payment method.</span></span>

3. <span data-ttu-id="82169-182">在右侧窗格中，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="82169-182">In the right pane, select **Delete**.</span></span>

4. <span data-ttu-id="82169-183">若要使用现有的付款方式，请从下拉列表中选择一个，然后选择 "**下一步**"，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="82169-183">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="82169-184">如果你有与付费配置文件关联的订阅，则只能使用信用卡支付。</span><span class="sxs-lookup"><span data-stu-id="82169-184">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="82169-185">如果您在 "**付款方式**" 页上列出了银行帐户，则不能在下拉列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="82169-185">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>

5. <span data-ttu-id="82169-186">若要添加新的付款方式，请选择 "**添加支付方式**"。</span><span class="sxs-lookup"><span data-stu-id="82169-186">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="82169-187">选择要添加的付款方式类型，输入帐户信息，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="82169-187">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>

7. <span data-ttu-id="82169-188">已在下拉列表中选择新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-188">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="82169-189">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="82169-189">Select **Next**.</span></span>

8. <span data-ttu-id="82169-190">选择“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82169-190">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="82169-191">付款方式疑难解答</span><span class="sxs-lookup"><span data-stu-id="82169-191">Troubleshoot payment methods</span></span>

|<span data-ttu-id="82169-192">**问题**</span><span class="sxs-lookup"><span data-stu-id="82169-192">**Issue**</span></span>|<span data-ttu-id="82169-193">**疑难解答步骤**</span><span class="sxs-lookup"><span data-stu-id="82169-193">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="82169-194">**我收到一条错误消息，显示 "浏览器当前设置为阻止 cookie"。**</span><span class="sxs-lookup"><span data-stu-id="82169-194">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="82169-195">将浏览器设置为允许第三方 Cookie，然后重试。</span><span class="sxs-lookup"><span data-stu-id="82169-195">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="82169-196">**已拒绝信用卡或借出卡。**</span><span class="sxs-lookup"><span data-stu-id="82169-196">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="82169-197">如果通过信用卡或借记卡付款，并且您的卡被拒绝，您会收到一封电子邮件，指出 Microsoft 无法处理付款。</span><span class="sxs-lookup"><span data-stu-id="82169-197">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="82169-198">请仔细检查卡片的详细信息 &mdash; 卡号、到期日期、卡片上的名称以及地址（包括城市、省/市/自治区和邮政编码） &mdash; 是否与在卡片和语句上显示的相同。</span><span class="sxs-lookup"><span data-stu-id="82169-198">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="82169-199">您可以使用 "订阅详细信息" 页的 "**计费**" 部分中的 "**结算余额**" 链接更新您的卡片信息并立即提交付款。</span><span class="sxs-lookup"><span data-stu-id="82169-199">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="82169-200">有关详细信息，请参阅[如果我的信用卡被拒绝且付款过期，该怎么办？](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span><span class="sxs-lookup"><span data-stu-id="82169-200">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="82169-201">如果仍然看到"拒绝"消息，请联系你的银行。</span><span class="sxs-lookup"><span data-stu-id="82169-201">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="82169-202">您的卡可能不是活动的。</span><span class="sxs-lookup"><span data-stu-id="82169-202">It's possible that your card isn't active.</span></span> <span data-ttu-id="82169-203">如果你最近在邮件中接收到包含更新到期日期的卡，请确保其已激活。</span><span class="sxs-lookup"><span data-stu-id="82169-203">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="82169-204">您的银行还可以告诉您您的卡片是否未被批准为在线、国际或重复事务。</span><span class="sxs-lookup"><span data-stu-id="82169-204">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="82169-205">**我想要更新一个或多个银行帐号。**</span><span class="sxs-lookup"><span data-stu-id="82169-205">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="82169-206">您不能在现有的付款方式上更改卡号或帐号。</span><span class="sxs-lookup"><span data-stu-id="82169-206">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="82169-207">如果您的卡或帐号已更改，请[使用不同的付款方式替换它](#replace-a-payment-method)，将所有活动的订阅从付款方式移到新的付款方式，然后[删除旧的付款方式](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)。</span><span class="sxs-lookup"><span data-stu-id="82169-207">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="82169-208">**我的帐户上仅有一个卡或银行帐户，我想将其删除。**</span><span class="sxs-lookup"><span data-stu-id="82169-208">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="82169-209">如果只有一种付款方式，则必须[将其替换为新的付款方式](#replace-a-payment-method)，然后才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="82169-209">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="82169-210">**我无法添加我的卡或银行帐户。**</span><span class="sxs-lookup"><span data-stu-id="82169-210">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="82169-211">您必须使用与您的租户从同一国家/地区颁发的付款方式。</span><span class="sxs-lookup"><span data-stu-id="82169-211">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="82169-212">如果您在输入卡或银行帐户信息时遇到问题，可以[联系支持人员](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="82169-212">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="82169-213">相关文章</span><span class="sxs-lookup"><span data-stu-id="82169-213">Related articles</span></span>

[<span data-ttu-id="82169-214">为你的业务订阅付费</span><span class="sxs-lookup"><span data-stu-id="82169-214">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="82169-215">管理计费对象信息</span><span class="sxs-lookup"><span data-stu-id="82169-215">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="82169-216">更改付款频率</span><span class="sxs-lookup"><span data-stu-id="82169-216">Change your payment frequency</span></span>](change-payment-frequency.md)