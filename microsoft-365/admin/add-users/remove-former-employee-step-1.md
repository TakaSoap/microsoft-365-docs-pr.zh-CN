---
title: 步骤 1 - 阻止员工登录Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 阻止以前的员工登录并阻止访问Microsoft 365服务。
ms.openlocfilehash: 84852e9bccb1d4370db07492baf7ccaed7f6db3d
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698900"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="7b5a1-103">步骤 1 - 阻止以前的员工登录并阻止对 Microsoft 365 服务的访问</span><span class="sxs-lookup"><span data-stu-id="7b5a1-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="7b5a1-104">如果需要立即阻止用户的登录访问，应重置其密码。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="7b5a1-105">在此步骤中，强制注销用户Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="7b5a1-106">你需要是全局管理员才能启动其他管理员的注销。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="7b5a1-107">对于非管理员用户，可以使用用户管理员或支持管理员用户执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span>
> <span data-ttu-id="7b5a1-108">了解有关管理员角色关于 <a href="https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles">管理员角色的更多信息</a></span><span class="sxs-lookup"><span data-stu-id="7b5a1-108">Learn more about the Admin Roles <a href="https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles">About Admin Roles</a></span></span>

1. <span data-ttu-id="7b5a1-109">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="7b5a1-110">选择用户名旁边的框，然后选择重置 **密码**。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="7b5a1-111">输入新密码，然后选择"重置 **"。**</span><span class="sxs-lookup"><span data-stu-id="7b5a1-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="7b5a1-112"> (不要将其发送给他们。) </span><span class="sxs-lookup"><span data-stu-id="7b5a1-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="7b5a1-113">选择要转到其属性窗格的用户名称，在"帐户"选项卡上，选择"**启动注销"。**</span><span class="sxs-lookup"><span data-stu-id="7b5a1-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="7b5a1-114">在一小时内（或离开当前Microsoft 365页面后）将提示他们重新登录。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="7b5a1-115">访问令牌适合一小时，因此时间线取决于该令牌所剩的时间，以及他们是否导航到当前网页。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7b5a1-116">如果用户在 web Outlook，只需在邮箱中四处单击，可能不会立即退出。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="7b5a1-117">当他们选择其他磁贴（如OneDrive或刷新浏览器）时，即会启动注销。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="7b5a1-118">若要使用 PowerShell 立即注销用户，请参阅 [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="7b5a1-119">有关阻止某人继续使用电子邮件所需时长的详细信息，请参阅[终止员工电子邮件会话须知事项](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session)。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="7b5a1-120">阻止以前的员工访问Microsoft 365服务</span><span class="sxs-lookup"><span data-stu-id="7b5a1-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="7b5a1-121">阻止帐户可能需要 24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="7b5a1-122">如果需要立即阻止用户的登录访问，请按照上述步骤操作并重置其密码。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="7b5a1-123">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="7b5a1-124">选择要阻止的员工的姓名，在用户名下，选择"阻止此 **用户"的符号**。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="7b5a1-125">选择 **"阻止用户登录"，** 然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="7b5a1-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="7b5a1-126">阻止以前的员工访问电子邮件 (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="7b5a1-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="7b5a1-127">如果你有电子邮件作为你的 Microsoft 365订阅的一部分，请登录到 Exchange 管理中心，并按照以下步骤阻止以前的员工访问他们的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="7b5a1-128">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="7b5a1-129">在 Exchange 管理中心 中，导航到" **收件人** "\>" **邮箱** "。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="7b5a1-130">双击用户，然后转到" **邮箱功能"** 页。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-130">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="7b5a1-131">在 **"移动设备"** 下，选择"禁用 **Exchange ActiveSync"** 和"**禁用适用于设备的 OWA"，** 当系统提示时，对两者回答"是"。 </span><span class="sxs-lookup"><span data-stu-id="7b5a1-131">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="7b5a1-132">在 **"电子邮件连接"** 下 **，选择"禁用\*\*\*\*"，在系统提示** 时回答"是"。</span><span class="sxs-lookup"><span data-stu-id="7b5a1-132">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
