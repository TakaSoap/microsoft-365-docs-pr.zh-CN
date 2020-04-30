---
title: 关闭你的帐户
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 了解如何使用 Microsoft 关闭你的帐户。
ms.openlocfilehash: b71cfe8246b5e3e9471c76cf8043bad52840f194
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942849"
---
# <a name="close-your-account"></a><span data-ttu-id="6f502-103">关闭你的帐户</span><span class="sxs-lookup"><span data-stu-id="6f502-103">Close your account</span></span>

<span data-ttu-id="6f502-104">当关闭你的 Microsoft 帐户时，与你的帐户相关的所有信息都将被删除。</span><span class="sxs-lookup"><span data-stu-id="6f502-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="6f502-105">此信息包括订阅、许可证、付款方式、用户和用户数据。</span><span class="sxs-lookup"><span data-stu-id="6f502-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="6f502-106">在开始此过程之前，请确保备份要保留的任何数据。</span><span class="sxs-lookup"><span data-stu-id="6f502-106">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="6f502-107">步骤1：删除用户</span><span class="sxs-lookup"><span data-stu-id="6f502-107">Step 1: Delete users</span></span>

<span data-ttu-id="6f502-108">删除除一个全局管理员之外的所有用户，以完成关闭该帐户的步骤。</span><span class="sxs-lookup"><span data-stu-id="6f502-108">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="6f502-109">必须删除所有其他用户，然后才能在此过程结束后删除该目录。</span><span class="sxs-lookup"><span data-stu-id="6f502-109">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="6f502-110">如果用户从本地同步，请先关闭 sync，然后使用 Azure 门户或 Azure PowerShell cmdlet 删除云目录中的用户。</span><span class="sxs-lookup"><span data-stu-id="6f502-110">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="6f502-111">若要删除用户，请参阅<a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">用户管理管理员：删除一个或多个用户</a>。</span><span class="sxs-lookup"><span data-stu-id="6f502-111">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="6f502-112">您还可以使用<a href="https://go.microsoft.com/fwlink/?linkid=842230">Get-msoluser</a> PowerShell cmdlet 批量删除用户。</span><span class="sxs-lookup"><span data-stu-id="6f502-112">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="6f502-113">如果您的组织使用与 Azure AD 同步的 Active Directory，则改为从 Active Directory 中删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6f502-113">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="6f502-114">有关说明，请参阅<a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">批量删除用户在 Azure Active Directory 中</a>。</span><span class="sxs-lookup"><span data-stu-id="6f502-114">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="6f502-115">步骤2：取消所有活动订阅</span><span class="sxs-lookup"><span data-stu-id="6f502-115">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="6f502-116">在 "管理中心" 中，转到 "**帐单** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品 & 服务</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="6f502-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="6f502-117">如果 "订阅" 列表位于**表格**视图中，则在右侧，选择 "**卡片**"。</span><span class="sxs-lookup"><span data-stu-id="6f502-117">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="6f502-118">查找活动订阅，并在 "**设置" & "操作**" 部分，选择 "**取消订阅**"。</span><span class="sxs-lookup"><span data-stu-id="6f502-118">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="6f502-119">按照提示完成此过程。</span><span class="sxs-lookup"><span data-stu-id="6f502-119">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="6f502-120">重复步骤1到4以取消所有活动订阅。</span><span class="sxs-lookup"><span data-stu-id="6f502-120">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="6f502-121">步骤3：删除所有禁用的订阅</span><span class="sxs-lookup"><span data-stu-id="6f502-121">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="6f502-122">在 "管理中心" 中，转到 "**帐单** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品 & 服务</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="6f502-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="6f502-123">如果 "订阅" 列表位于**表格**视图中，则在右侧，选择 "**卡片**"。</span><span class="sxs-lookup"><span data-stu-id="6f502-123">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="6f502-124">在 "**订阅状态**" 旁边，选择 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="6f502-124">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="6f502-125">查找已禁用的订阅，并在 "**设置" & "操作**" 部分，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="6f502-125">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="6f502-126">在 "**删除订阅**" 对话框中，选中 "**我了解影响"** 复选框，然后选择 "**删除订阅**"。</span><span class="sxs-lookup"><span data-stu-id="6f502-126">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="6f502-127">对于每个禁用的订阅，重复步骤4和步骤5，直到删除所有订阅。</span><span class="sxs-lookup"><span data-stu-id="6f502-127">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="6f502-128">步骤4：禁用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="6f502-128">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="6f502-129">在 "管理中心" 中，转到 "**用户** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="6f502-129">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="6f502-130">选择**多因素身份验证**。</span><span class="sxs-lookup"><span data-stu-id="6f502-130">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="6f502-131">在 "多重身份验证" 页上，禁用除当前正在使用的全局管理员帐户之外的所有帐户。</span><span class="sxs-lookup"><span data-stu-id="6f502-131">On the multi-factor authentication page, disable all accounts except for the global admin account that you’re currently using.</span></span>

<span data-ttu-id="6f502-132">您还可以<a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">使用 PowerShell 为多个用户禁用多重身份验证</a>。</span><span class="sxs-lookup"><span data-stu-id="6f502-132">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="6f502-133">步骤5：删除 Azure Active Directory 中的目录</span><span class="sxs-lookup"><span data-stu-id="6f502-133">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="6f502-134">使用全局管理员帐户登录到<a href="https://aad.portal.azure.com/" target="_blank">AZURE AD 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="6f502-134">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="6f502-135">选择“**Azure Active Directory**”。</span><span class="sxs-lookup"><span data-stu-id="6f502-135">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="6f502-136">切换到要删除的目录。</span><span class="sxs-lookup"><span data-stu-id="6f502-136">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="6f502-137">选择 "**删除目录**"。</span><span class="sxs-lookup"><span data-stu-id="6f502-137">Select **Delete directory**.</span></span>

5. <span data-ttu-id="6f502-138">如果目录未通过一个或多个检查，则会看到有关如何传递检查的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="6f502-138">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="6f502-139">传递所有检查后，选择 "**删除**" 以完成此过程。</span><span class="sxs-lookup"><span data-stu-id="6f502-139">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="6f502-140">完成此最后一步之后，你的 Microsoft 帐户将关闭并被删除。</span><span class="sxs-lookup"><span data-stu-id="6f502-140">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
