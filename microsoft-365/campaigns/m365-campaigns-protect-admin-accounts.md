---
title: 保护管理员帐户
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 了解如何设置和保护管理员帐户。
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398237"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="ea941-103">保护管理员帐户</span><span class="sxs-lookup"><span data-stu-id="ea941-103">Protect your administrator accounts</span></span>

<span data-ttu-id="ea941-104">由于管理员帐户具有提升的特权，因此它们是黑客和网络犯罪有价值的目标。</span><span class="sxs-lookup"><span data-stu-id="ea941-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="ea941-105">本文内容：</span><span class="sxs-lookup"><span data-stu-id="ea941-105">This article describes:</span></span>

- <span data-ttu-id="ea941-106">如何为紧急情况设置其他管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="ea941-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="ea941-107">如何保护这些帐户。</span><span class="sxs-lookup"><span data-stu-id="ea941-107">How to protect these accounts.</span></span>

<span data-ttu-id="ea941-108">当你注册 Microsoft 365 并输入你的信息时，将自动成为全局管理员。全局管理员对 Microsoft 管理中心中的用户帐户和所有其他设置具有最终控制权，但有很多不同类型的管理员帐户具有不同的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ea941-108">When you sign up for Microsoft 365 and enter your information, you automatically become the Global admin. A Global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="ea941-109">有关 [每种管理员角色](/office365/admin/add-users/about-admin-roles) 的不同访问级别的信息，请参阅有关管理员角色的信息。</span><span class="sxs-lookup"><span data-stu-id="ea941-109">See [about admin roles](/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="ea941-110">创建其他管理员帐户</span><span class="sxs-lookup"><span data-stu-id="ea941-110">Create additional admin accounts</span></span>

<span data-ttu-id="ea941-111">仅将管理员帐户用于管理。</span><span class="sxs-lookup"><span data-stu-id="ea941-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="ea941-112">管理员应具有一个单独的用户帐户，用于定期使用 Office 应用，并且仅在管理帐户和设备时以及处理其他管理功能时，才使用其管理帐户。</span><span class="sxs-lookup"><span data-stu-id="ea941-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="ea941-113">此外，从管理员帐户中删除 Microsoft 365 许可证也是一个好主意，这样你不必支付这些许可证费用。</span><span class="sxs-lookup"><span data-stu-id="ea941-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="ea941-114">你需要设置至少一个额外的全局管理员帐户，以向另一个受信任员工授予管理员访问权限。</span><span class="sxs-lookup"><span data-stu-id="ea941-114">You'll want to set up at least one additional Global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="ea941-115">还可以为用户管理创建单独的管理员帐户 (此角色称为用户 **管理管理员**) 。</span><span class="sxs-lookup"><span data-stu-id="ea941-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="ea941-116">有关详细信息，请参阅 [管理员角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ea941-116">For more information, see [about admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="ea941-117">创建其他管理员帐户：</span><span class="sxs-lookup"><span data-stu-id="ea941-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="ea941-118">转到管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">中心，</a>**然后选择左侧导航** \> **中的"用户""** 活动用户"。</span><span class="sxs-lookup"><span data-stu-id="ea941-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![选择"用户"，然后选择左侧导航中的"活动用户"](../media/Activeusers.png)

 2. <span data-ttu-id="ea941-120">在 **"活动用户**"页上，选择页面顶部的"添加用户"，在"新建用户"面板中，输入名称和其他信息。</span><span class="sxs-lookup"><span data-stu-id="ea941-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="ea941-121">展开" **角色"** 部分，然后选择" **全局管理员** "为此用户授予全局管理员访问权限。</span><span class="sxs-lookup"><span data-stu-id="ea941-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="ea941-122">还可以选择" **自定义管理员"** 并选择显示的任何角色。</span><span class="sxs-lookup"><span data-stu-id="ea941-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="ea941-123">在"备用电子邮件地址" **文本框中输入备用** 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ea941-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="ea941-124">如果锁定，可以使用此地址恢复密码信息。对于全局管理员，帐单也会发送到此地址。</span><span class="sxs-lookup"><span data-stu-id="ea941-124">You can use this address to recover your password information if you get locked out. For Global admins, a billing statement will also be sent to this address.</span></span>

    ![选择管理员角色](../media/adminroles.png)

 4. <span data-ttu-id="ea941-126">在"**产品许可证"** 部分，将 **"Microsoft 365 商业** 版"的选择器移到 **"** 关闭"，将"创建 **没有** 产品许可证的用户"移动到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="ea941-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![选择产品许可证](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="ea941-128">创建紧急管理员帐户</span><span class="sxs-lookup"><span data-stu-id="ea941-128">Create an emergency admin account</span></span>

<span data-ttu-id="ea941-129">您还应该创建一个未设置多重身份验证 (MFA) 的备份帐户，以便不会意外锁定 (例如，如果你丢失了用作第二种验证) 形式的手机。</span><span class="sxs-lookup"><span data-stu-id="ea941-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="ea941-130">确保此帐户的密码是短语或至少 16 个字符长。</span><span class="sxs-lookup"><span data-stu-id="ea941-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="ea941-131">这通常称为"中断式帐户"。</span><span class="sxs-lookup"><span data-stu-id="ea941-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="ea941-132">为自己创建用户帐户</span><span class="sxs-lookup"><span data-stu-id="ea941-132">Create a user account for yourself</span></span>

<span data-ttu-id="ea941-133">使用用户帐户与组织协作，包括检查邮件。</span><span class="sxs-lookup"><span data-stu-id="ea941-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="ea941-134">这意味着你的管理员凭据可能类似于  *Alice.Chavez <span></span> @Contoso.org* 并且你的常规用户帐户可能类似于 *Alice <span></span> @Contoso.com*。</span><span class="sxs-lookup"><span data-stu-id="ea941-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="ea941-135">创建新用户帐户：</span><span class="sxs-lookup"><span data-stu-id="ea941-135">To create a new user account:</span></span>

1. <span data-ttu-id="ea941-136">转到管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">中心，</a>**然后选择左侧导航** \> **中的"用户""** 活动用户"。</span><span class="sxs-lookup"><span data-stu-id="ea941-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="ea941-137">在 **"活动用户**"页上，选择页面顶部的"添加用户"，在"新建用户"面板中，输入名称和其他信息。</span><span class="sxs-lookup"><span data-stu-id="ea941-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="ea941-138">展开"**角色"** 部分，然后选择" (**没有管理访问权限) 。**</span><span class="sxs-lookup"><span data-stu-id="ea941-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="ea941-139">在"**产品许可证"** 部分，将 **"Microsoft 365 商业版"的选择器移动到\*\*\*\*"打开"。**</span><span class="sxs-lookup"><span data-stu-id="ea941-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="turn-on-security-defaults"></a><span data-ttu-id="ea941-140">打开安全默认值</span><span class="sxs-lookup"><span data-stu-id="ea941-140">Turn on security defaults</span></span>

<span data-ttu-id="ea941-141">安全默认值通过提供 Microsoft 代表组织管理的预配置安全设置来帮助保护组织免受与标识相关的攻击。</span><span class="sxs-lookup"><span data-stu-id="ea941-141">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="ea941-142">这些设置包括在所有管理员和用户帐户 (MFA) 多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="ea941-142">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="ea941-143">有关安全默认值和如何启用安全默认值的信息，请参阅 [启用安全默认值](m365-campaigns-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ea941-143">For more information about security defaults and to learn how to enable them on, see [Turn on security defaults](m365-campaigns-conditional-access.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="ea941-144">其他建议</span><span class="sxs-lookup"><span data-stu-id="ea941-144">Additional recommendations</span></span>

- <span data-ttu-id="ea941-145">使用管理员帐户之前，请关闭所有不相关的浏览器会话和应用，包括个人电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="ea941-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="ea941-146">还可以在专用或隐身浏览器窗口中使用。</span><span class="sxs-lookup"><span data-stu-id="ea941-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="ea941-147">完成管理员任务后，请务必注销浏览器会话。</span><span class="sxs-lookup"><span data-stu-id="ea941-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
