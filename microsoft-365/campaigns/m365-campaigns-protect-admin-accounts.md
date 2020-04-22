---
title: 保护您的管理员帐户
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 了解如何设置和保护管理员帐户。
ms.openlocfilehash: 2104697320308b329f9fde1b6984c15f9814f9ef
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633649"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="8f495-103">保护您的管理员帐户</span><span class="sxs-lookup"><span data-stu-id="8f495-103">Protect your administrator accounts</span></span>

<span data-ttu-id="8f495-104">由于管理员帐户具有提升的权限，因此它们对于黑客和网络罪犯来说都是非常有用的目标。</span><span class="sxs-lookup"><span data-stu-id="8f495-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="8f495-105">本文内容：</span><span class="sxs-lookup"><span data-stu-id="8f495-105">This article describes:</span></span>

- <span data-ttu-id="8f495-106">如何为紧急情况设置其他管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="8f495-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="8f495-107">如何保护这些帐户。</span><span class="sxs-lookup"><span data-stu-id="8f495-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="8f495-108">当你注册 Microsoft 365 并输入你的信息时，你将自动成为全局管理员。全局管理员拥有对用户帐户和 Microsoft 管理中心中所有其他设置的最终控制权，但有许多不同类型的管理员帐户具有不同级别的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8f495-108">When you sign up for Microsoft 365 and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="8f495-109">有关每种管理员角色的不同访问级别的信息，请参阅[关于管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="8f495-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="8f495-110">创建其他管理员帐户</span><span class="sxs-lookup"><span data-stu-id="8f495-110">Create additional admin accounts</span></span>

<span data-ttu-id="8f495-111">仅使用管理员帐户进行管理。</span><span class="sxs-lookup"><span data-stu-id="8f495-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="8f495-112">管理员应具有单独的用户帐户，以便定期使用 Office 应用，并且仅在需要管理帐户和设备以及在处理其他管理功能时使用其管理帐户。</span><span class="sxs-lookup"><span data-stu-id="8f495-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="8f495-113">最好将 Microsoft 365 许可证从管理员帐户中删除，这样你就不必为其付费。</span><span class="sxs-lookup"><span data-stu-id="8f495-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="8f495-114">你将需要至少设置一个额外的全局管理员帐户，以向其他受信任的员工授予管理员访问权限。</span><span class="sxs-lookup"><span data-stu-id="8f495-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="8f495-115">您还可以为用户管理创建单独的管理员帐户（此角色称为 "**用户管理管理员**"）。</span><span class="sxs-lookup"><span data-stu-id="8f495-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="8f495-116">有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="8f495-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="8f495-117">若要创建其他管理员帐户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8f495-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="8f495-118">转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a>"，然后选择左侧导航中的 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="8f495-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![选择左侧导航中的 "用户" 和 "活动用户"](../media/Activeusers.png)

2. <span data-ttu-id="8f495-120">在 "**活动用户**" 页上，选择页面顶部的 "**添加用户**"，并在新的 "**用户**" 面板上输入名称和其他信息。</span><span class="sxs-lookup"><span data-stu-id="8f495-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="8f495-121">展开 "**角色**" 部分，然后选择 "**全局管理员**" 以向此用户授予全局管理员访问权限。</span><span class="sxs-lookup"><span data-stu-id="8f495-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="8f495-122">您还可以选择 "**自定义管理员**" 并选择显示的任意角色。</span><span class="sxs-lookup"><span data-stu-id="8f495-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="8f495-123">在 "**备选电子邮件地址**" 文本框中输入备用电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8f495-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="8f495-124">如果您被锁定，可以使用此地址来恢复您的密码信息。对于全局管理员，还将向此地址发送帐单声明。</span><span class="sxs-lookup"><span data-stu-id="8f495-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![选择管理员角色](../media/adminroles.png)
    
4. <span data-ttu-id="8f495-126">在 "**产品许可证**" 部分，将 " **Microsoft 365 业务**" 的选择器移到 "**关闭**"，并将 "**创建不含产品许可证的用户** **" 设为**</span><span class="sxs-lookup"><span data-stu-id="8f495-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![选择产品许可证](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="8f495-128">创建紧急管理员帐户</span><span class="sxs-lookup"><span data-stu-id="8f495-128">Create an emergency admin account</span></span>

<span data-ttu-id="8f495-129">此外，还应创建一个不是通过多重身份验证（MFA）设置的备份帐户，这样您就不会意外锁定自己（例如，如果您使用另一种形式的验证丢失了您的电话）。</span><span class="sxs-lookup"><span data-stu-id="8f495-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="8f495-130">请确保此帐户的密码为短语或至少为16个字符长。</span><span class="sxs-lookup"><span data-stu-id="8f495-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="8f495-131">这通常称为 "断开玻璃帐户"。</span><span class="sxs-lookup"><span data-stu-id="8f495-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="8f495-132">为自己创建一个用户帐户</span><span class="sxs-lookup"><span data-stu-id="8f495-132">Create a user account for yourself</span></span>

<span data-ttu-id="8f495-133">使用您的用户帐户参与与您的组织的协作，包括检查邮件。</span><span class="sxs-lookup"><span data-stu-id="8f495-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="8f495-134">这意味着您的管理员凭据可能类似于*Chavez<span></span>@Contoso* ，并且您的常规用户帐户可能类似于*<span></span>小红 @Contoso .com*。</span><span class="sxs-lookup"><span data-stu-id="8f495-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="8f495-135">若要创建新用户帐户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8f495-135">To create a new user account:</span></span>
1. <span data-ttu-id="8f495-136">转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a>"，然后选择左侧导航中的 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="8f495-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="8f495-137">在 "**活动用户**" 页上，选择页面顶部的 "**添加用户**"，并在新的 "**用户**" 面板上输入名称和其他信息。</span><span class="sxs-lookup"><span data-stu-id="8f495-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="8f495-138">展开 "**角色**" 部分，然后选择 "**用户" （无管理访问权限）**。</span><span class="sxs-lookup"><span data-stu-id="8f495-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="8f495-139">在 "**产品许可证**" 部分，将 " **Microsoft 365 企业**" 的选择器移到 **"打开**"。</span><span class="sxs-lookup"><span data-stu-id="8f495-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="8f495-140">为多因素身份验证注册每个帐户</span><span class="sxs-lookup"><span data-stu-id="8f495-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="8f495-141">其他建议</span><span class="sxs-lookup"><span data-stu-id="8f495-141">Additional recommendations</span></span>

- <span data-ttu-id="8f495-142">请确保同时为多因素身份验证设置了管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="8f495-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="8f495-143">我们将在[配置条件访问策略](m365-campaigns-conditional-access.md)中介绍如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8f495-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="8f495-144">使用管理员帐户之前，请关闭所有不相关的浏览器会话和应用，包括个人电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="8f495-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="8f495-145">您还可以在私有或 incognito 浏览器窗口中使用。</span><span class="sxs-lookup"><span data-stu-id="8f495-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="8f495-146">完成管理任务后，请务必注销浏览器会话。</span><span class="sxs-lookup"><span data-stu-id="8f495-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>
