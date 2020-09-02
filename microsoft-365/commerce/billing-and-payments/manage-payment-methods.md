---
title: 管理支付方式
f1.keywords:
- CSH
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
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: 了解如何在 Microsoft 365 管理中心中管理你的支付方式。
ms.date: ''
ms.openlocfilehash: 81c7509fb2f3be982890ec6b68dafb83ff0c1876
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324230"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="24fe8-103">管理支付方式</span><span class="sxs-lookup"><span data-stu-id="24fe8-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="24fe8-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="24fe8-104">The admin center is changing.</span></span> <span data-ttu-id="24fe8-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="24fe8-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="24fe8-106">当您从 Microsoft 购买业务产品或服务时，您可以使用现有的付款方式，也可以添加一个新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="24fe8-107">您可以使用信用卡或借记卡或银行帐户支付购买的物品。</span><span class="sxs-lookup"><span data-stu-id="24fe8-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="24fe8-108">如果您的企业帐户有一个记帐配置文件，并且您是帐单档案文件所有者或帐单个人资料参与者，则可以使用信用卡或发票付款支持的计费配置文件来进行购买或支付帐单。</span><span class="sxs-lookup"><span data-stu-id="24fe8-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="24fe8-109">如果您是帐单发票管理者，则只能使用计费配置文件来支付帐单。</span><span class="sxs-lookup"><span data-stu-id="24fe8-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="24fe8-110">若要了解有关计费配置文件和角色的详细信息，请参阅 [管理计费配置文件](manage-billing-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="24fe8-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="24fe8-111">如果你的企业帐户没有记帐配置文件，则任何全局或帐单管理员都可以管理和使用添加到企业帐户的任何银行帐户。</span><span class="sxs-lookup"><span data-stu-id="24fe8-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="24fe8-112">但是，您只能管理或使用您添加的信用卡。</span><span class="sxs-lookup"><span data-stu-id="24fe8-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="24fe8-113">在某些国家或地区不提供用银行帐户付款的选项。</span><span class="sxs-lookup"><span data-stu-id="24fe8-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="24fe8-114">您必须使用与您的租户从同一国家/地区颁发的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="24fe8-115">准备工作</span><span class="sxs-lookup"><span data-stu-id="24fe8-115">Before you begin</span></span>

<span data-ttu-id="24fe8-116">您必须是全局管理员或帐单管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="24fe8-116">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="24fe8-117">有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="24fe8-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="24fe8-118">添加付款方式</span><span class="sxs-lookup"><span data-stu-id="24fe8-118">Add a payment method</span></span>

<span data-ttu-id="24fe8-119">添加付款方法不会将任何订阅关联。</span><span class="sxs-lookup"><span data-stu-id="24fe8-119">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="24fe8-120">若要将单个订阅分配给付款方法，请参阅 [更改单个订阅的付款方式](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="24fe8-120">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="24fe8-121">若要将使用其他付款方式的所有订阅替换为新的，请参阅 [替换付款方法](#replace-a-payment-method)。</span><span class="sxs-lookup"><span data-stu-id="24fe8-121">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

1. <span data-ttu-id="24fe8-122">在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="24fe8-122">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="24fe8-123">选择“**添加付款方式**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-123">Select **Add a payment method**.</span></span>
3. <span data-ttu-id="24fe8-124">在“**付款方式**”页面上，从下拉菜单中选择一种付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-124">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>
4. <span data-ttu-id="24fe8-125">输入新卡或银行帐户的信息，然后选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-125">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="24fe8-126">更新付款方式详细信息</span><span class="sxs-lookup"><span data-stu-id="24fe8-126">Update payment method details</span></span>

<span data-ttu-id="24fe8-127">您可以更改现有付款方式的信用卡或借记卡、帐单地址或到期日期的名称。</span><span class="sxs-lookup"><span data-stu-id="24fe8-127">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="24fe8-128">但是，不能更改卡片或帐号。</span><span class="sxs-lookup"><span data-stu-id="24fe8-128">However, you can't change the card or account number.</span></span> <span data-ttu-id="24fe8-129">如果帐户号码已更改，请将 [其替换为其他付款方式](#replace-a-payment-method)，然后 [删除旧的](#delete-a-payment-method)付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-129">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

1. <span data-ttu-id="24fe8-130">在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="24fe8-130">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="24fe8-131">选择要更新的付款方式行。</span><span class="sxs-lookup"><span data-stu-id="24fe8-131">Select the row of the payment method to update.</span></span> <span data-ttu-id="24fe8-132">在右窗格中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-132">In the right pane, select **Edit**.</span></span>
3. <span data-ttu-id="24fe8-133">更新付款方式信息，包括信用卡或借记卡上的姓名、帐单邮寄地址或到期日期，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-133">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="24fe8-134">替换付款方法</span><span class="sxs-lookup"><span data-stu-id="24fe8-134">Replace a payment method</span></span>

<span data-ttu-id="24fe8-135">当您替换付款方式时，会将其替换为使用相同付款方式的所有订阅和计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="24fe8-135">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="24fe8-136">替换支付方式不会删除现有的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-136">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="24fe8-137">您仍可以选择和使用其他订阅和计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="24fe8-137">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="24fe8-138">若要更改单个订阅的付款方式，请参阅 [更改单个订阅的支付方式](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="24fe8-138">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

1. <span data-ttu-id="24fe8-139">在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="24fe8-139">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="24fe8-140">选择要替换的付款方式行。</span><span class="sxs-lookup"><span data-stu-id="24fe8-140">Select the row of the payment method to replace.</span></span> <span data-ttu-id="24fe8-141">右窗格列出了使用所选付款方式的所有计费对象信息和单个订阅。</span><span class="sxs-lookup"><span data-stu-id="24fe8-141">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>
3. <span data-ttu-id="24fe8-142">在右窗格中，选择“**所有商品的替换付款方式**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-142">In the right pane, select **Replace payment method for all items**.</span></span>
4. <span data-ttu-id="24fe8-143">若要使用现有付款方式，请从下拉列表中选择一个，然后选择“**替换**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-143">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="24fe8-144">如果你有与计费对象信息相关联的订阅，则只能使用信用卡或借记卡支付。</span><span class="sxs-lookup"><span data-stu-id="24fe8-144">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="24fe8-145">如果“**付款方式**”页面上列出了银行帐户，则不能在下拉列表中选择它们。</span><span class="sxs-lookup"><span data-stu-id="24fe8-145">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>
5. <span data-ttu-id="24fe8-146">若要添加新的付款方式，请选择“**添加付款方式**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-146">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="24fe8-147">在“**添加付款方式**”窗格中，输入帐户信息，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-147">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="24fe8-148">你必须使用租户所在国家/地区的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-148">You must use a payment method from the same country as your tenant.</span></span>
7. <span data-ttu-id="24fe8-149">已在下拉列表中选择新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-149">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="24fe8-150">选择“**替换**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-150">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="24fe8-151">更改单个订阅的付款方式</span><span class="sxs-lookup"><span data-stu-id="24fe8-151">Change a payment method for a single subscription</span></span>

<span data-ttu-id="24fe8-152">您可以更改用于支付单个订阅的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-152">You can change the payment method used to pay for a single subscription.</span></span>

1. <span data-ttu-id="24fe8-153">在管理中心中，转到 "**付费**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="24fe8-153">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="24fe8-154">在 " **产品** " 选项卡上，查找要使用备用付款方式支付的订阅。</span><span class="sxs-lookup"><span data-stu-id="24fe8-154">On the **Products** tab, find the subscription that you want to pay for with the alternate payment method.</span></span>
3. <span data-ttu-id="24fe8-155">选择 " **更多操作** (三个点) "，然后选择 " **替换支付方式**"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-155">Select **More actions** (three dots), then select **Replace payment method**.</span></span>
4. <span data-ttu-id="24fe8-156">在 " **替换付款方法** " 窗格中，从下拉列表中选择一个备用付款方式，或选择 "添加支付方式"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-156">In the **Replace payment method** pane, from the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>
5. <span data-ttu-id="24fe8-157">如果添加付款方法，请输入信用卡或帐户详细信息，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-157">If you add a payment method, enter the card or account details, then select **Save**.</span></span>
6. <span data-ttu-id="24fe8-158">确认所选的支付方式正确，然后选择 " **替换**"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-158">Verify that the selected payment method is correct, then select **Replace**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="24fe8-159">删除付款方法</span><span class="sxs-lookup"><span data-stu-id="24fe8-159">Delete a payment method</span></span>

<span data-ttu-id="24fe8-160">您只能删除未附加到订阅或帐单配置文件的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-160">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="24fe8-161">这适用于所有订阅（无论其状态如何）。</span><span class="sxs-lookup"><span data-stu-id="24fe8-161">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="24fe8-162">删除没有订阅或附加的计费配置文件的付款方式</span><span class="sxs-lookup"><span data-stu-id="24fe8-162">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="24fe8-163">如果付款方法不与任何订阅或计费配置文件关联，则可以立即将其删除。</span><span class="sxs-lookup"><span data-stu-id="24fe8-163">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

1. <span data-ttu-id="24fe8-164">在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="24fe8-164">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="24fe8-165">找到要删除的付款方法，选择三个点，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-165">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>
3. <span data-ttu-id="24fe8-166">在右侧窗格的底部，选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-166">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="24fe8-167">删除带有订阅或附加的计费配置文件的付款方式</span><span class="sxs-lookup"><span data-stu-id="24fe8-167">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="24fe8-168">如果向任何订阅或计费配置文件附加了付款方式，请首先将其替换为现有付款方式，或添加新的付款方式，然后删除旧的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-168">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

1. <span data-ttu-id="24fe8-169">在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="24fe8-169">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="24fe8-170">选择要删除的付款方法所在的行。</span><span class="sxs-lookup"><span data-stu-id="24fe8-170">Select the row for the payment method to delete.</span></span> <span data-ttu-id="24fe8-171">右侧窗格中列出了使用该付款方式的现有订阅。</span><span class="sxs-lookup"><span data-stu-id="24fe8-171">The right pane lists existing subscriptions that use that payment method.</span></span>
3. <span data-ttu-id="24fe8-172">在右侧窗格中，选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-172">In the right pane, select **Delete**.</span></span>
4. <span data-ttu-id="24fe8-173">若要使用现有的付款方式，请从下拉列表中选择一个，然后选择 " **下一步**"，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-173">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="24fe8-174">如果你有与付费配置文件关联的订阅，则只能使用信用卡支付。</span><span class="sxs-lookup"><span data-stu-id="24fe8-174">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="24fe8-175">如果您在 " **付款方式** " 页上列出了银行帐户，则不能在下拉列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="24fe8-175">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>
5. <span data-ttu-id="24fe8-176">若要添加新的付款方式，请选择“**添加付款方式**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-176">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="24fe8-177">选择要添加的付款方式类型，输入帐户信息，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="24fe8-177">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>
7. <span data-ttu-id="24fe8-178">已在下拉列表中选择新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-178">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="24fe8-179">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="24fe8-179">Select **Next**.</span></span>
8. <span data-ttu-id="24fe8-180">选择“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="24fe8-180">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="24fe8-181">付款方式疑难解答</span><span class="sxs-lookup"><span data-stu-id="24fe8-181">Troubleshoot payment methods</span></span>

|<span data-ttu-id="24fe8-182">**问题**</span><span class="sxs-lookup"><span data-stu-id="24fe8-182">**Issue**</span></span>|<span data-ttu-id="24fe8-183">**疑难解答步骤**</span><span class="sxs-lookup"><span data-stu-id="24fe8-183">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="24fe8-184">**我收到一条错误消息，显示 "浏览器当前设置为阻止 cookie"。**</span><span class="sxs-lookup"><span data-stu-id="24fe8-184">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="24fe8-185">将浏览器设置为允许第三方 Cookie，然后重试。</span><span class="sxs-lookup"><span data-stu-id="24fe8-185">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="24fe8-186">**已拒绝信用卡或借出卡。**</span><span class="sxs-lookup"><span data-stu-id="24fe8-186">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="24fe8-187">如果通过信用卡或借记卡付款，并且您的卡被拒绝，您会收到一封电子邮件，指出 Microsoft 无法处理付款。</span><span class="sxs-lookup"><span data-stu-id="24fe8-187">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="24fe8-188">请仔细检查卡片的详细信息 &mdash; 卡号、到期日期、卡片上的名称以及地址（包括城市、省/市/自治区和邮政编码） &mdash; 是否与在卡片和语句上显示的相同。</span><span class="sxs-lookup"><span data-stu-id="24fe8-188">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="24fe8-189">您可以使用 "订阅详细信息" 页的 "**计费**" 部分中的 "**结算余额**" 链接更新您的卡片信息并立即提交付款。</span><span class="sxs-lookup"><span data-stu-id="24fe8-189">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="24fe8-190">有关详细信息，请参阅 [如果我的信用卡被拒绝且付款过期，该怎么办？](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span><span class="sxs-lookup"><span data-stu-id="24fe8-190">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="24fe8-191">如果仍然看到"拒绝"消息，请联系你的银行。</span><span class="sxs-lookup"><span data-stu-id="24fe8-191">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="24fe8-192">您的卡可能不是活动的。</span><span class="sxs-lookup"><span data-stu-id="24fe8-192">It's possible that your card isn't active.</span></span> <span data-ttu-id="24fe8-193">如果你最近在邮件中接收到包含更新到期日期的卡，请确保其已激活。</span><span class="sxs-lookup"><span data-stu-id="24fe8-193">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="24fe8-194">您的银行还可以告诉您您的卡片是否未被批准为在线、国际或重复事务。</span><span class="sxs-lookup"><span data-stu-id="24fe8-194">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="24fe8-195">**我想要更新一个或多个银行帐号。**</span><span class="sxs-lookup"><span data-stu-id="24fe8-195">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="24fe8-196">您不能在现有的付款方式上更改卡号或帐号。</span><span class="sxs-lookup"><span data-stu-id="24fe8-196">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="24fe8-197">如果您的卡或帐号已更改，请 [使用不同的付款方式替换它](#replace-a-payment-method)，将所有活动的订阅从付款方式移到新的付款方式，然后 [删除旧的付款方式](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)。</span><span class="sxs-lookup"><span data-stu-id="24fe8-197">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="24fe8-198">**我的帐户上仅有一个卡或银行帐户，我想将其删除。**</span><span class="sxs-lookup"><span data-stu-id="24fe8-198">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="24fe8-199">如果只有一种付款方式，则必须 [将其替换为新的付款方式](#replace-a-payment-method) ，然后才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="24fe8-199">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="24fe8-200">**我无法添加我的卡或银行帐户。**</span><span class="sxs-lookup"><span data-stu-id="24fe8-200">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="24fe8-201">您必须使用与您的租户从同一国家/地区颁发的付款方式。</span><span class="sxs-lookup"><span data-stu-id="24fe8-201">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="24fe8-202">如果您在输入卡或银行帐户信息时遇到问题，可以 [联系支持人员](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="24fe8-202">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-content"></a><span data-ttu-id="24fe8-203">相关内容</span><span class="sxs-lookup"><span data-stu-id="24fe8-203">Related content</span></span>

<span data-ttu-id="24fe8-204">[为你的业务订阅付费](pay-for-your-subscription.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="24fe8-204">[Pay for your business subscription](pay-for-your-subscription.md) (article)</span></span>\
<span data-ttu-id="24fe8-205">[管理帐单配置文件](manage-billing-profiles.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="24fe8-205">[Manage billing profiles](manage-billing-profiles.md) (article)</span></span>\
<span data-ttu-id="24fe8-206">更改 (文章) [的帐单频率](change-payment-frequency.md)</span><span class="sxs-lookup"><span data-stu-id="24fe8-206">[Change your billing frequency](change-payment-frequency.md) (article)</span></span>