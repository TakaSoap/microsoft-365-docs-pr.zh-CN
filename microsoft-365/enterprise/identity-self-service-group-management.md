---
title: 步骤 6：使用组实现更轻松地管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 自助服务组管理。
ms.openlocfilehash: 9400e99ced45370600d1d5dcee4388ddef4250fe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283517"
---
# <a name="step-6-use-groups-for-easier-management"></a><span data-ttu-id="277dd-103">步骤 6：使用组实现更轻松地管理</span><span class="sxs-lookup"><span data-stu-id="277dd-103">Step 6: Use groups for easier management</span></span>

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="277dd-104">允许用户创建和管理自己的组</span><span class="sxs-lookup"><span data-stu-id="277dd-104">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="277dd-105">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="277dd-105">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="277dd-106">在此部分中，将标识可由组所有者而不是 IT 管理员来管理的 Azure Active Directory (Azure AD) 组。</span><span class="sxs-lookup"><span data-stu-id="277dd-106">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="277dd-107">此功能称为*自助服务组管理*，允许未分配管理角色的组所有者创建和管理安全组。</span><span class="sxs-lookup"><span data-stu-id="277dd-107">In this step, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="277dd-p102">用户可以请求安全组中的成员身份，该请求将转到组所有者而不是 IT 管理员。这可将组成员身份的日常控制委托给团队、项目或业务所有者，他们了解组的商业用途，可更好地管理其成员身份。</span><span class="sxs-lookup"><span data-stu-id="277dd-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="277dd-110">自助服务组管理仅适用于 Azure AD 安全和 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="277dd-110">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span> <span data-ttu-id="277dd-111">不适用于启用邮件的组、通讯组列表或已从本地 Active Directory 域服务 (AD DS) 同步的任何组。</span><span class="sxs-lookup"><span data-stu-id="277dd-111">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="277dd-112">有关详细信息，请参阅[配置 Azure AD 组进行自助服务管理的说明](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。</span><span class="sxs-lookup"><span data-stu-id="277dd-112">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="277dd-113">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-self-service-groups)。</span><span class="sxs-lookup"><span data-stu-id="277dd-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="277dd-114">设置动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="277dd-114">Set up dynamic group membership</span></span>

<span data-ttu-id="277dd-115">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="277dd-115">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="277dd-116">在此部分中，将创建一系列规则来为 Azure AD 组的成员自动添加或删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="277dd-116">In this step, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as dynamic group membership. The rules are based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="277dd-117">这称为*动态组成员身份*。</span><span class="sxs-lookup"><span data-stu-id="277dd-117">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="277dd-118">这些规则将基于用户帐户属性，如部门或国家/地区。</span><span class="sxs-lookup"><span data-stu-id="277dd-118">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="277dd-119">下面是如何应用这些规则：</span><span class="sxs-lookup"><span data-stu-id="277dd-119">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="277dd-120">如果新用户帐户符合组的所有规则，则其会变为成员。</span><span class="sxs-lookup"><span data-stu-id="277dd-120">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="277dd-121">如果用户帐户不是组成员，但其属性更改，以便其匹配组的所有规则，则其会变为该组的成员。</span><span class="sxs-lookup"><span data-stu-id="277dd-121">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="277dd-122">如果用户帐户不匹配组的所有规则，则其不会添加到组。</span><span class="sxs-lookup"><span data-stu-id="277dd-122">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="277dd-123">如果用户帐户是组成员，但其属性更改，以便其不再匹配组的所有规则，则会从该组成员中将其删除。</span><span class="sxs-lookup"><span data-stu-id="277dd-123">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="277dd-p105">若要使用动态成员身份，则必须先确定有一组常用的用户帐户属性。例如，销售部门的所有成员都应在“销售 Azure AD”组中，根据用户帐户属性部门设置为“Sales”。</span><span class="sxs-lookup"><span data-stu-id="277dd-p105">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="277dd-126">请参阅[为动态 Azure AD 组创建并配置规则的说明](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="277dd-126">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="277dd-127">此部分的结果是：</span><span class="sxs-lookup"><span data-stu-id="277dd-127">The results of this step are:</span></span>

- <span data-ttu-id="277dd-128">可以为动态成员身份配置的 Azure AD 组集</span><span class="sxs-lookup"><span data-stu-id="277dd-128">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="277dd-129">每个动态组的规则集</span><span class="sxs-lookup"><span data-stu-id="277dd-129">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="277dd-131">测试实验室指南：自动化许可和组成员身份</span><span class="sxs-lookup"><span data-stu-id="277dd-131">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="277dd-132">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-dyn-groups)。</span><span class="sxs-lookup"><span data-stu-id="277dd-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="277dd-133">设置自动许可</span><span class="sxs-lookup"><span data-stu-id="277dd-133">Set up automatic licensing</span></span>

<span data-ttu-id="277dd-134">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="277dd-134">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="277dd-135">在此部分中，将在 Azure AD 中配置安全组，以将许可证从一组订阅自动分配到组的所有成员。</span><span class="sxs-lookup"><span data-stu-id="277dd-135">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="277dd-136">这称为*基于组的许可*。</span><span class="sxs-lookup"><span data-stu-id="277dd-136">This is known as *group-based licensing*.</span></span> <span data-ttu-id="277dd-137">如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或从该用户帐户中删除。</span><span class="sxs-lookup"><span data-stu-id="277dd-137">In this step, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as group-based licensing. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="277dd-138">对于 Microsoft 365 企业版，将配置 Azure AD 安全组，以分配这两种许可证：</span><span class="sxs-lookup"><span data-stu-id="277dd-138">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="277dd-139">Office 365 企业版 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="277dd-139">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="277dd-140">企业移动性 + 安全性 (EMS) E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="277dd-140">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="277dd-p107">使用在步骤 2 中标识的组，查找包含该组中所有用户必须同时具有 Office 365 和 EMS 许可证的帐户列表的组。请确保对所有组成员具有足够的许可证。一旦许可证用完，将无法向新用户分配许可证，直到有可用的许可证为止。</span><span class="sxs-lookup"><span data-stu-id="277dd-p107">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="277dd-144">不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”\*\*。</span><span class="sxs-lookup"><span data-stu-id="277dd-144">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="277dd-145">有关更多信息，请参阅 [Azure Active Directory 中基于组的许可基础知识](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="277dd-145">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="277dd-146">请参阅[为 Azure 安全组配置基于组的许可的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="277dd-146">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="277dd-147">此部分的结果是：</span><span class="sxs-lookup"><span data-stu-id="277dd-147">The results of this step are:</span></span>

- <span data-ttu-id="277dd-148">已标识哪些安全组适用于基于组的许可。</span><span class="sxs-lookup"><span data-stu-id="277dd-148">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="277dd-149">已为基于组的许可配置了这些组。</span><span class="sxs-lookup"><span data-stu-id="277dd-149">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="277dd-151">测试实验室指南：自动化许可和组成员身份</span><span class="sxs-lookup"><span data-stu-id="277dd-151">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="277dd-152">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-group-license)。</span><span class="sxs-lookup"><span data-stu-id="277dd-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="277dd-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="277dd-153">Next step</span></span>

[<span data-ttu-id="277dd-154">身份基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="277dd-154">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)
