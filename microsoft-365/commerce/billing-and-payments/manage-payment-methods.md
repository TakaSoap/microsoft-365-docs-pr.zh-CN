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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: 了解如何在 Microsoft 365 管理中心管理你的付款方式。
ms.date: ''
ms.openlocfilehash: a6866a9691e42928a5712c3069704f11fac0546f
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741385"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="ae69d-103">管理支付方式</span><span class="sxs-lookup"><span data-stu-id="ae69d-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="ae69d-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="ae69d-104">The admin center is changing.</span></span> <span data-ttu-id="ae69d-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="ae69d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>
::: moniker-end

<span data-ttu-id="ae69d-106">从 Microsoft 购买企业产品或服务时，可以使用现有付款方式，或添加新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="ae69d-107">可以使用信用卡、借记卡或银行帐户来支付所购买的东西。</span><span class="sxs-lookup"><span data-stu-id="ae69d-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="ae69d-108">如果你的企业帐户具有帐单配置文件，并且你是帐单配置文件所有者或帐单配置文件参与者，可以使用由信用卡或发票付款支持的帐单配置文件进行购买或支付帐单。</span><span class="sxs-lookup"><span data-stu-id="ae69d-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="ae69d-109">如果你是帐单发票管理员，则只能使用帐单配置文件支付帐单。</span><span class="sxs-lookup"><span data-stu-id="ae69d-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="ae69d-110">若要了解有关帐单配置文件和角色的信息，请参阅 [帐单配置文件](manage-billing-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="ae69d-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="ae69d-111">如果你的企业帐户没有帐单配置文件，任何全局管理员或帐单管理员可以管理和使用添加到企业帐户的任何银行帐户。</span><span class="sxs-lookup"><span data-stu-id="ae69d-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="ae69d-112">但是，你只能管理或使用你添加的信用卡。</span><span class="sxs-lookup"><span data-stu-id="ae69d-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="ae69d-113">某些国家和地区未提供使用银行帐户付款的选项。</span><span class="sxs-lookup"><span data-stu-id="ae69d-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="ae69d-114">必须使用与租户相同的国家/地区发布的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ae69d-115">开始之前</span><span class="sxs-lookup"><span data-stu-id="ae69d-115">Before you begin</span></span>

<span data-ttu-id="ae69d-116">你必须是全局管理员或帐单管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="ae69d-116">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="ae69d-117">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ae69d-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="ae69d-118">添加付款方式</span><span class="sxs-lookup"><span data-stu-id="ae69d-118">Add a payment method</span></span>

<span data-ttu-id="ae69d-119">添加付款方式不会将任何订阅关联到该付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-119">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="ae69d-120">若要向付款方式分配单个订阅，请参阅 [订阅的付款方式](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="ae69d-120">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="ae69d-121">若要将其他付款方式的所有订阅替换为新订阅，请参阅 [替换付款方式](#replace-a-payment-method)。</span><span class="sxs-lookup"><span data-stu-id="ae69d-121">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

1. <span data-ttu-id="ae69d-122">在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="ae69d-122">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="ae69d-123">选择“**添加付款方式**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-123">Select **Add a payment method**.</span></span>
3. <span data-ttu-id="ae69d-124">在“**付款方式**”页面上，从下拉菜单中选择一种付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-124">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>
4. <span data-ttu-id="ae69d-125">输入新信用卡或新银行帐户的信息，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-125">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="ae69d-126">更新付款方式详细信息</span><span class="sxs-lookup"><span data-stu-id="ae69d-126">Update payment method details</span></span>

<span data-ttu-id="ae69d-127">你可以更改信用卡或借记卡上的姓名、帐单邮寄地址或现有付款方式的到期日期。</span><span class="sxs-lookup"><span data-stu-id="ae69d-127">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="ae69d-128">但无法更改信用卡号或帐号。</span><span class="sxs-lookup"><span data-stu-id="ae69d-128">However, you can't change the card or account number.</span></span> <span data-ttu-id="ae69d-129">如果帐户编号已更改， [将其替换为不同的付款方式](#replace-a-payment-method)， [旧的](#delete-a-payment-method)。</span><span class="sxs-lookup"><span data-stu-id="ae69d-129">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

1. <span data-ttu-id="ae69d-130">在管理中心，转到“**账单**” > “**账单与付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="ae69d-130">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="ae69d-131">选择要更新的付款方式行。</span><span class="sxs-lookup"><span data-stu-id="ae69d-131">Select the row of the payment method to update.</span></span> <span data-ttu-id="ae69d-132">在右窗格中，选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-132">In the right pane, select **Edit**.</span></span>
3. <span data-ttu-id="ae69d-133">更新付款方式信息，包括信用卡或借记卡上的姓名、帐单邮寄地址或到期日期，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-133">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="ae69d-134">替换付款方式</span><span class="sxs-lookup"><span data-stu-id="ae69d-134">Replace a payment method</span></span>

<span data-ttu-id="ae69d-135">替换付款方式时，将替换所有使用相同付款方式的订阅和帐单配置文件。</span><span class="sxs-lookup"><span data-stu-id="ae69d-135">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="ae69d-136">替换付款方式不会删除现有付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-136">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="ae69d-137">它仍然可用于其他订阅和帐单配置文件选择和使用。</span><span class="sxs-lookup"><span data-stu-id="ae69d-137">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="ae69d-138">若要更改单个订阅的付款方式，请参阅 [订阅的付款方式](#change-a-payment-method-for-a-single-subscription)。</span><span class="sxs-lookup"><span data-stu-id="ae69d-138">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

1. <span data-ttu-id="ae69d-139">在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="ae69d-139">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="ae69d-140">选择要替换的付款方式行。</span><span class="sxs-lookup"><span data-stu-id="ae69d-140">Select the row of the payment method to replace.</span></span> <span data-ttu-id="ae69d-141">右窗格列出了使用所选付款方式的所有计费对象信息和单个订阅。</span><span class="sxs-lookup"><span data-stu-id="ae69d-141">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>
3. <span data-ttu-id="ae69d-142">在右窗格中，选择“**所有商品的替换付款方式**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-142">In the right pane, select **Replace payment method for all items**.</span></span>
4. <span data-ttu-id="ae69d-143">若要使用现有付款方式，请从下拉列表中选择一个，然后选择“**替换**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-143">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="ae69d-144">如果你有与计费对象信息相关联的订阅，则只能使用信用卡或借记卡支付。</span><span class="sxs-lookup"><span data-stu-id="ae69d-144">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="ae69d-145">如果“**付款方式**”页面上列出了银行帐户，则不能在下拉列表中选择它们。</span><span class="sxs-lookup"><span data-stu-id="ae69d-145">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>
5. <span data-ttu-id="ae69d-146">若要添加新的付款方式，请选择“**添加付款方式**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-146">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="ae69d-147">在“**添加付款方式**”窗格中，输入帐户信息，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-147">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="ae69d-148">你必须使用租户所在国家/地区的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-148">You must use a payment method from the same country as your tenant.</span></span>
7. <span data-ttu-id="ae69d-149">已在下拉列表中选择新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-149">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="ae69d-150">选择“**替换**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-150">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="ae69d-151">更改单个订阅的付款方式</span><span class="sxs-lookup"><span data-stu-id="ae69d-151">Change a payment method for a single subscription</span></span>

<span data-ttu-id="ae69d-152">可更改单个订阅的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-152">You can change the payment method used to pay for a single subscription.</span></span>

1. <span data-ttu-id="ae69d-153">在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="ae69d-153">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="ae69d-154">在" **"** 选项卡上，找到你想要使用备用付款方式付款的订阅。</span><span class="sxs-lookup"><span data-stu-id="ae69d-154">On the **Products** tab, find the subscription that you want to pay for with the alternate payment method.</span></span>
3. <span data-ttu-id="ae69d-155">选择 **执行更多** （三个点），然后选择 **替换付款方式**。</span><span class="sxs-lookup"><span data-stu-id="ae69d-155">Select **More actions** (three dots), then select **Replace payment method**.</span></span>
4. <span data-ttu-id="ae69d-156">在 **替换付款方式** "窗格中的下拉列表中，选择其他付款方式，或选择添加付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-156">In the **Replace payment method** pane, from the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>
5. <span data-ttu-id="ae69d-157">如果添加付款方式，请输入卡或帐户详细信息，然后选择 **另**。</span><span class="sxs-lookup"><span data-stu-id="ae69d-157">If you add a payment method, enter the card or account details, then select **Save**.</span></span>
6. <span data-ttu-id="ae69d-158">验证所选付款方式是否正确，然后选择“**替换**”。。</span><span class="sxs-lookup"><span data-stu-id="ae69d-158">Verify that the selected payment method is correct, then select **Replace**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="ae69d-159">删除付款方式</span><span class="sxs-lookup"><span data-stu-id="ae69d-159">Delete a payment method</span></span>

<span data-ttu-id="ae69d-160">只能删除未附加到订阅或帐单个人资料的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-160">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="ae69d-161">这适用于所有订阅，无论其状态如何。</span><span class="sxs-lookup"><span data-stu-id="ae69d-161">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="ae69d-162">删除不附加订阅或帐单配置文件的付款方式</span><span class="sxs-lookup"><span data-stu-id="ae69d-162">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="ae69d-163">如果付款方式未与任何订阅或帐单配置文件相关联，可以立即将其删除。</span><span class="sxs-lookup"><span data-stu-id="ae69d-163">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

1. <span data-ttu-id="ae69d-164">在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="ae69d-164">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="ae69d-165">找到要删除的付款方式，选择三个点，然后选择 **"删除“**。</span><span class="sxs-lookup"><span data-stu-id="ae69d-165">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>
3. <span data-ttu-id="ae69d-166">在右侧窗格底部，选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-166">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="ae69d-167">删除附加了订阅或帐单配置文件的付款方式</span><span class="sxs-lookup"><span data-stu-id="ae69d-167">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="ae69d-168">如果向任何订阅或帐单配置文件附加了付款方式，请首先将其替换为现有的付款方式，或添加新的付款方式，然后删除旧的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-168">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

1. <span data-ttu-id="ae69d-169">在管理中心，转到“**账单**” > “**账单和付款**“ > “<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">付款方式</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="ae69d-169">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
2. <span data-ttu-id="ae69d-170">选择要删除的付款方式行。</span><span class="sxs-lookup"><span data-stu-id="ae69d-170">Select the row for the payment method to delete.</span></span> <span data-ttu-id="ae69d-171">右窗格列出了使用该付款方式的现有订阅。</span><span class="sxs-lookup"><span data-stu-id="ae69d-171">The right pane lists existing subscriptions that use that payment method.</span></span>
3. <span data-ttu-id="ae69d-172">在右窗格中，选择" **删除**。</span><span class="sxs-lookup"><span data-stu-id="ae69d-172">In the right pane, select **Delete**.</span></span>
4. <span data-ttu-id="ae69d-173">若要使用现有付款方式，请从下拉列表中选择一种，选择"**下一**，然后选择 **"删除”**。</span><span class="sxs-lookup"><span data-stu-id="ae69d-173">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="ae69d-174">如果你有与计费对象信息相关联的订阅，则只能使用信用卡或借记卡支付。</span><span class="sxs-lookup"><span data-stu-id="ae69d-174">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="ae69d-175">如果“**付款方式**”页面上列出了银行帐户，则不能在下拉列表中选择它们。</span><span class="sxs-lookup"><span data-stu-id="ae69d-175">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>
5. <span data-ttu-id="ae69d-176">若要添加新的付款方式，请选择“**添加付款方式**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-176">To add a new payment method, select **Add payment method**.</span></span>
6. <span data-ttu-id="ae69d-177">选择要添加的付款方式类型，输入帐户信息，然后选择 **另**。</span><span class="sxs-lookup"><span data-stu-id="ae69d-177">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>
7. <span data-ttu-id="ae69d-178">已在下拉列表中选择新的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-178">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="ae69d-179">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-179">Select **Next**.</span></span>
8. <span data-ttu-id="ae69d-180">选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="ae69d-180">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="ae69d-181">付款方式疑难解答</span><span class="sxs-lookup"><span data-stu-id="ae69d-181">Troubleshoot payment methods</span></span>

| <span data-ttu-id="ae69d-182">问题</span><span class="sxs-lookup"><span data-stu-id="ae69d-182">Issue</span></span> | <span data-ttu-id="ae69d-183">故障排除步骤</span><span class="sxs-lookup"><span data-stu-id="ae69d-183">Troubleshooting steps</span></span> |
|:----------|:-----|
|<span data-ttu-id="ae69d-184">**我收到错误消息，显示"浏览器当前设置为阻止 Cookie"。**</span><span class="sxs-lookup"><span data-stu-id="ae69d-184">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="ae69d-185">将浏览器设置为允许第三方 Cookie，然后重试。</span><span class="sxs-lookup"><span data-stu-id="ae69d-185">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="ae69d-186">**我的信用卡或借记卡被拒绝。**</span><span class="sxs-lookup"><span data-stu-id="ae69d-186">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="ae69d-187">如果通过信用卡或借记卡付款，并且信用卡被拒绝，则将收到一封电子邮件，指出 Microsoft 无法处理该付款。</span><span class="sxs-lookup"><span data-stu-id="ae69d-187">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="ae69d-188">仔细检查卡详细信息&mdash;卡号、到期日期、卡上的姓名以及地址，包括省/市/县和邮政编码&mdash;在卡上和语句中是否完全相同。</span><span class="sxs-lookup"><span data-stu-id="ae69d-188">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="ae69d-189">您可以使用订阅详细信息页面 **“结算”** 部分中的 **“结算余额”** 链接来更新您的卡信息并立即提交付款。</span><span class="sxs-lookup"><span data-stu-id="ae69d-189">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="ae69d-190">如需了解更多信息，请参阅[如果我有未清偿的余额，我应该怎么做？](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)</span><span class="sxs-lookup"><span data-stu-id="ae69d-190">For more information, see [What if I have an outstanding balance?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)</span></span>  <br/><br/>  <span data-ttu-id="ae69d-191">如果仍然看到“拒绝”消息，请联系你的银行。</span><span class="sxs-lookup"><span data-stu-id="ae69d-191">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="ae69d-192">有可能你的卡片未处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="ae69d-192">It's possible that your card isn't active.</span></span> <span data-ttu-id="ae69d-193">如果你最近在邮件中收到该卡，到期日期已更新，请确保其已激活。</span><span class="sxs-lookup"><span data-stu-id="ae69d-193">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="ae69d-194">你的银行还可告知你卡片是否未获得批准进行联机、国际或定期交易。</span><span class="sxs-lookup"><span data-stu-id="ae69d-194">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="ae69d-195">**我想更新卡号或银行帐户帐号。**</span><span class="sxs-lookup"><span data-stu-id="ae69d-195">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="ae69d-196">不能更改现有付款方式的卡号或帐号。</span><span class="sxs-lookup"><span data-stu-id="ae69d-196">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="ae69d-197">如果你的卡号或帐号已更改， [请将其替换为不同的付款方式](#replace-a-payment-method)，该付款方式会将所有活动订阅从付款方式移动到新付款方式， [删除旧的付款方式](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)。</span><span class="sxs-lookup"><span data-stu-id="ae69d-197">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="ae69d-198">**我的帐户中仅有一张信用卡或一个银行帐户，我想删除它。**</span><span class="sxs-lookup"><span data-stu-id="ae69d-198">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="ae69d-199">如果只有一种付款方式，则必须 [，将其替换为新的付款方式](#replace-a-payment-method) 才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="ae69d-199">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="ae69d-200">**无法添加信用卡或银行帐户。**</span><span class="sxs-lookup"><span data-stu-id="ae69d-200">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="ae69d-201">必须使用与租户相同的国家/地区发布的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ae69d-201">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="ae69d-202">如果在输入信用卡或银行帐户信息时遇到问题。请[联系支持人员](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="ae69d-202">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-content"></a><span data-ttu-id="ae69d-203">相关内容</span><span class="sxs-lookup"><span data-stu-id="ae69d-203">Related content</span></span>

<span data-ttu-id="ae69d-204">[支付企业版订阅费用](pay-for-your-subscription.md) （文章）</span><span class="sxs-lookup"><span data-stu-id="ae69d-204">[Pay for your business subscription](pay-for-your-subscription.md) (article)</span></span>\
<span data-ttu-id="ae69d-205">[管理帐单配置文件](manage-billing-profiles.md) （文章）</span><span class="sxs-lookup"><span data-stu-id="ae69d-205">[Manage billing profiles](manage-billing-profiles.md) (article)</span></span>\
<span data-ttu-id="ae69d-206">[更改记帐频率](change-payment-frequency.md) （文章）</span><span class="sxs-lookup"><span data-stu-id="ae69d-206">[Change your billing frequency](change-payment-frequency.md) (article)</span></span>
