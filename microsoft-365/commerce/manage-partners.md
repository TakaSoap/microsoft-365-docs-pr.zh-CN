---
title: 使用解决方案提供商
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration <!-- need to figure out what this value should be -->
localization_priority: Normal
ms.collection:
- commerce <!-- probably need to change this -->
ms.custom: ''
search.appverid:
- MET150
description: 您可以与 Microsoft 认证的解决方案提供商合作，以购买和管理组织或学校的产品和服务。
keywords: 合作伙伴、解决方案提供商
ms.openlocfilehash: bb78e1a704529fd2d12ff49639913fe80b75be7a
ms.sourcegitcommit: a7edd3840226e67e82126bb9dee423b3458fef4d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2019
ms.locfileid: "36994073"
---
# <a name="working-with-solution-providers-in-microsoft-store-for-business"></a><span data-ttu-id="e7ce4-104">在 Microsoft Store for Business 中使用解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="e7ce4-104">Working with solution providers in Microsoft Store for Business</span></span>

<span data-ttu-id="e7ce4-105">您可以与 Microsoft 认证的解决方案提供商合作，以购买和管理组织或学校的产品和服务。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-105">You can work with Microsoft-certified solution providers to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="e7ce4-106">在获取设置的过程中，需要执行几个步骤。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-106">There's a few steps involved in getting the things set up.</span></span> 

<span data-ttu-id="e7ce4-107">该过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7ce4-107">The process goes like this:</span></span>
- <span data-ttu-id="e7ce4-108">管理员使用在 Microsoft Store for Business 中**查找解决方案提供商**查找和联系解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-108">Admins find and contact a solution provider using **Find a solution provider** in Microsoft Store for Business.</span></span> 
- <span data-ttu-id="e7ce4-109">解决方案提供商向客户发送来自合作伙伴中心的请求，以成为其解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-109">Solution providers send a request from Partner center to customers to become their solution provider.</span></span>
- <span data-ttu-id="e7ce4-110">客户接受 Microsoft Store for Business 中的邀请，并开始使用解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-110">Customers accept the invitation in Microsoft Store for Business and start working with the solution provider.</span></span>
- <span data-ttu-id="e7ce4-111">客户可以在 Microsoft Store for Business 中管理与合作伙伴的关系设置。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-111">Customers can manage settings for the relationship with Partner in Microsoft Store for Business.</span></span> 

## <a name="what-can-a-solution-provider-do-for-my-organization-or-school"></a><span data-ttu-id="e7ce4-112">解决方案提供商可以为我的组织或学校做些什么？</span><span class="sxs-lookup"><span data-stu-id="e7ce4-112">What can a solution provider do for my organization or school?</span></span>

<span data-ttu-id="e7ce4-113">解决方案提供商可以通过多种方式与您协作。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-113">There are several ways that a solution provider can work with you.</span></span> <span data-ttu-id="e7ce4-114">当解决方案提供商发送其请求以与你的合作伙伴合作时，它们将在其中选择一个。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-114">Solution providers will choose one of these when they send their request to work as a partner with you.</span></span>

| <span data-ttu-id="e7ce4-115">解决方案提供程序函数</span><span class="sxs-lookup"><span data-stu-id="e7ce4-115">Solution provider function</span></span> | <span data-ttu-id="e7ce4-116">说明</span><span class="sxs-lookup"><span data-stu-id="e7ce4-116">Description</span></span> | 
| ------ | ------------------- | 
| <span data-ttu-id="e7ce4-117">增值</span><span class="sxs-lookup"><span data-stu-id="e7ce4-117">Reseller</span></span> | <span data-ttu-id="e7ce4-118">解决方案提供商将 Microsoft 产品销售给你的组织或学校。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-118">Solution providers sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="e7ce4-119">委派管理员</span><span class="sxs-lookup"><span data-stu-id="e7ce4-119">Delegated administrator</span></span> | <span data-ttu-id="e7ce4-120">解决方案提供商管理组织或学校的产品和服务。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-120">Solution provider manages products and services for your organization or school.</span></span> <span data-ttu-id="e7ce4-121">在 Azure Active Directory （AD）中，合作伙伴将成为租户的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-121">In Azure Active Directory (AD), the Partner will be a Global Administrator for tenant.</span></span> <span data-ttu-id="e7ce4-122">这样，他们就可以管理诸如创建用户帐户、分配和管理许可证以及密码重置等服务。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-122">This allows them to manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="e7ce4-123">& 委派管理员的转销商</span><span class="sxs-lookup"><span data-stu-id="e7ce4-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="e7ce4-124">为您的组织或学校销售和管理 Microsoft 产品和服务的解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-124">Solution providers that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="e7ce4-125">合作伙伴</span><span class="sxs-lookup"><span data-stu-id="e7ce4-125">Partner</span></span> | <span data-ttu-id="e7ce4-126">您可以向解决方案提供商提供租户中的用户帐户，并代表其他 Microsoft 服务工作。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-126">You can give your solution provider a user account in your tenant, and they work on your behalf with other Microsoft services.</span></span> |
| <span data-ttu-id="e7ce4-127">Microsoft 产品 & Services 协议（MPSA）合作伙伴</span><span class="sxs-lookup"><span data-stu-id="e7ce4-127">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="e7ce4-128">如果你已通过 MPSA 程序使用了多个解决方案提供商，则可以允许合作伙伴查看彼此的购买。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-128">If you've worked with multiple solution providers through the MPSA program, you can allow partners to see purchases made by each other.</span></span> |
| <span data-ttu-id="e7ce4-129">OEM 电脑合作伙伴</span><span class="sxs-lookup"><span data-stu-id="e7ce4-129">OEM PC partner</span></span> | <span data-ttu-id="e7ce4-130">解决方案提供商可以上传[使用 Autopilot 管理](https://docs.microsoft.com/microsoft-store/add-profile-to-devices)的电脑的设备 id。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-130">Solution providers can upload device IDs for PCs that you're [managing with Autopilot](https://docs.microsoft.com/microsoft-store/add-profile-to-devices).</span></span>   |
| <span data-ttu-id="e7ce4-131">业务线（LOB）合作伙伴</span><span class="sxs-lookup"><span data-stu-id="e7ce4-131">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="e7ce4-132">解决方案提供商可以开发、提交和管理特定于您的组织或学校的 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-132">Solution providers can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-solution-provider"></a><span data-ttu-id="e7ce4-133">查找解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="e7ce4-133">Find a solution provider</span></span>

<span data-ttu-id="e7ce4-134">你可以在 Microsoft Store for Business and 教育中找到合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-134">You can find partner in Microsoft Store for Business and Education.</span></span> 

1. <span data-ttu-id="e7ce4-135">登录[Microsoft store For Business](https://businessstore.microsoft.com/)或[Microsoft store for 教育](https://educationstore.microsoft.com/)版。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-135">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com/) or [Microsoft Store for Education](https://educationstore.microsoft.com/).</span></span>
2. <span data-ttu-id="e7ce4-136">选择 "**查找解决方案提供商**"。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-136">Select **Find a solution provider**.</span></span>
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-find-partner.png)
-->
3. <span data-ttu-id="e7ce4-137">优化列表或搜索解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-137">Refine the list, or search for a solution provider.</span></span> 
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-provider-list.png)
-->
4. <span data-ttu-id="e7ce4-138">当您找到要使用的解决方案提供商时，请单击 "**联系人**"。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-138">When you find a solution provider you're interested in working with, click **Contact**.</span></span>
5. <span data-ttu-id="e7ce4-139">完成并发送窗体。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-139">Complete and send the form.</span></span>

<span data-ttu-id="e7ce4-140">解决方案提供商将与你取得联系。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-140">The solution provider will get in touch with you.</span></span> <span data-ttu-id="e7ce4-141">你将有机会了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-141">You'll have a chance to learn more about them.</span></span> <span data-ttu-id="e7ce4-142">如果您决定使用解决方案提供商，他们将向您发送来自合作伙伴中心的电子邮件邀请。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-142">If you decide to work with the solution provider, they will send you an email invitation from Partner Center.</span></span> 

## <a name="work-with-a-solution-provider"></a><span data-ttu-id="e7ce4-143">使用解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="e7ce4-143">Work with a solution provider</span></span>

<span data-ttu-id="e7ce4-144">一旦找到了解决方案提供商并决定使用它们，他们就会向您发送一封邀请，让他们从合作伙伴中心协同工作。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-144">Once you've found a solution provider and decided to work with them, they'll send you an invitation to work together from Partner Center.</span></span> <span data-ttu-id="e7ce4-145">在 Microsoft Store for Business 或教育版中，需要接受邀请。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-145">In Microsoft Store for Business or Education, you'll need to accept the invitation.</span></span> <span data-ttu-id="e7ce4-146">之后，你可以管理他们的权限。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-146">After that, you can manage their permissions.</span></span>

<span data-ttu-id="e7ce4-147">**接受解决方案提供商邀请**</span><span class="sxs-lookup"><span data-stu-id="e7ce4-147">**To accept a solution provider invitation**</span></span>
1. <span data-ttu-id="e7ce4-148">**关注电子邮件链接**-你将收到一封电子邮件，其中包含可接受来自解决方案提供商的解决方案提供商邀请的链接。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-148">**Follow email link** - You'll receive an email with a link to accept the solution provider invitation from your solution provider.</span></span> <span data-ttu-id="e7ce4-149">此链接将带你转到 Microsoft Store for Business 或教育版。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-149">The link will take you to Microsoft Store for Business or Education.</span></span>
2. <span data-ttu-id="e7ce4-150">**接受邀请**-On **accept Partner 请柬**，选择 "**授权**" 以接受邀请，接受 Microsoft 云协议的条款，并开始使用解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-150">**Accept invitation** - On **Accept Partner Invitation**, select **Authorize** to accept the invitation, accept terms of the Microsoft Cloud Agreement, and start working with the solution provider.</span></span> 
<!---
![Image shows accepting an invitation from a solution provider in Microsoft Store for Business.](images/msft-accept-partner.png)
--> 
## <a name="delegate-admin-privileges"></a><span data-ttu-id="e7ce4-151">委派管理员权限</span><span class="sxs-lookup"><span data-stu-id="e7ce4-151">Delegate admin privileges</span></span>

<span data-ttu-id="e7ce4-152">根据解决方案提供商发出的请求，接受邀请的部分将包括同意向解决方案提供商授予委派管理员权限。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-152">Depending on the request made by the solution provider, part of accepting the invitation will include agreeing to give delegated admin privileges to the solution provider.</span></span> <span data-ttu-id="e7ce4-153">当解决方案提供程序请求包括作为委派的管理员时，将会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-153">This will happen when the solution provider request includes acting as a delegated administrator.</span></span> <span data-ttu-id="e7ce4-154">有关详细信息，请参阅[AZURE AD 中的委派管理员权限](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-154">For more information, see [Delegated admin privileges in Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span> 

<span data-ttu-id="e7ce4-155">如果您不想将管理员权限委派给解决方案提供商，则需要取消邀请，而不是接受它。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-155">If you don't want to delegate admin privileges to the solution provider, you'll need to cancel the invitation instead of accepting it.</span></span> 

<span data-ttu-id="e7ce4-156">如果您将管理员权限委派给解决方案提供商，则可以在以后删除。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-156">If you delegate admin privileges to a solution provider, you can remove that later.</span></span> 

<span data-ttu-id="e7ce4-157">**删除委派管理员权限**</span><span class="sxs-lookup"><span data-stu-id="e7ce4-157">**To remove delegate admin privileges**</span></span>
1. <span data-ttu-id="e7ce4-158">登录[Microsoft store For Business](https://businessstore.microsoft.com/)或[Microsoft store for 教育](https://educationstore.microsoft.com/)版。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-158">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com/) or [Microsoft Store for Education](https://educationstore.microsoft.com/).</span></span>
2. <span data-ttu-id="e7ce4-159">选择**合作伙伴**</span><span class="sxs-lookup"><span data-stu-id="e7ce4-159">Select **Partner**</span></span>
3. <span data-ttu-id="e7ce4-160">选择要管理的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-160">Choose the Partner you want to manage.</span></span>
4. <span data-ttu-id="e7ce4-161">选择 "**删除委派权限**"。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-161">Select **Remove Delegated Permissions**.</span></span> 

<span data-ttu-id="e7ce4-162">解决方案提供商仍将能够与你协作，例如，作为转销商。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-162">The solution provider will still be able to work with you, for example, as a Reseller.</span></span> 
