---
title: 管理 Microsoft 365 组
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 了解如何管理 Microsoft 365 组。
ms.openlocfilehash: 529bdb874661329497b103a1207b90625ad33a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911003"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="e61a0-103">管理 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="e61a0-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="e61a0-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="e61a0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e61a0-105">你可通过几种不同的方式管理 Microsoft 365 组，具体取决于你的配置。</span><span class="sxs-lookup"><span data-stu-id="e61a0-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="e61a0-106">可以在 [Microsoft 365](../admin/add-users/index.yml)管理中心 、PowerShell、Active Directory 域服务 (AD DS) 或 Azure Active [Directory (Azure AD) 管理](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)中心 中管理用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e61a0-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="e61a0-107">规划管理组位置和方式</span><span class="sxs-lookup"><span data-stu-id="e61a0-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="e61a0-108">在哪里以及如何管理用户帐户取决于你要用于 Microsoft 365 的标识模型。</span><span class="sxs-lookup"><span data-stu-id="e61a0-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="e61a0-109">这两种整体模型是仅云模型和混合模型。</span><span class="sxs-lookup"><span data-stu-id="e61a0-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="e61a0-110">仅限云</span><span class="sxs-lookup"><span data-stu-id="e61a0-110">Cloud-only</span></span>

<span data-ttu-id="e61a0-111">创建和管理组时，需要：</span><span class="sxs-lookup"><span data-stu-id="e61a0-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="e61a0-112">Microsoft 365 管理员中心</span><span class="sxs-lookup"><span data-stu-id="e61a0-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- [<span data-ttu-id="e61a0-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e61a0-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e61a0-114">Azure AD 管理中心</span><span class="sxs-lookup"><span data-stu-id="e61a0-114">Azure AD admin center</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="e61a0-115">混合</span><span class="sxs-lookup"><span data-stu-id="e61a0-115">Hybrid</span></span>

<span data-ttu-id="e61a0-116">AD DS 组从 AD DS 与 Microsoft 365 同步，因此必须使用本地 AD DS 工具管理这些组。</span><span class="sxs-lookup"><span data-stu-id="e61a0-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="e61a0-117">还可以创建和管理独立于 AD DS 组但可以包含 AD DS 中的用户和组的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="e61a0-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="e61a0-118">在这种情况下，可以使用：</span><span class="sxs-lookup"><span data-stu-id="e61a0-118">In this case, you can use:</span></span>

- [<span data-ttu-id="e61a0-119">Microsoft 365 管理员中心</span><span class="sxs-lookup"><span data-stu-id="e61a0-119">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- [<span data-ttu-id="e61a0-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e61a0-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e61a0-121">Azure AD 管理中心</span><span class="sxs-lookup"><span data-stu-id="e61a0-121">Azure AD admin center</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="e61a0-122">允许用户创建和管理自己的组</span><span class="sxs-lookup"><span data-stu-id="e61a0-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="e61a0-123">Azure AD 允许由组所有者而不是 IT 管理员管理的组。</span><span class="sxs-lookup"><span data-stu-id="e61a0-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="e61a0-124">此功能称为 *自助服务组管理*，允许未分配管理角色的组所有者创建和管理安全组。</span><span class="sxs-lookup"><span data-stu-id="e61a0-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="e61a0-p105">用户可以请求安全组中的成员身份，该请求将转到组所有者而不是 IT 管理员。这可将组成员身份的日常控制委托给团队、项目或业务所有者，他们了解组的商业用途，可更好地管理其成员身份。</span><span class="sxs-lookup"><span data-stu-id="e61a0-p105">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="e61a0-127">自助服务组管理仅适用于 Azure AD 安全和 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="e61a0-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="e61a0-128">它不适用于启用邮件的组、通讯组列表或从 AD DS 同步的任何组。</span><span class="sxs-lookup"><span data-stu-id="e61a0-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="e61a0-129">有关详细信息，请参阅[配置 Azure AD 组进行自助服务管理的说明](/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。</span><span class="sxs-lookup"><span data-stu-id="e61a0-129">For more information, see the [instructions to configure an Azure AD group for self-service management](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="e61a0-130">设置动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="e61a0-130">Set up dynamic group membership</span></span>

<span data-ttu-id="e61a0-131">Azure AD 支持配置一系列规则，以自动添加或删除用户帐户作为 Azure AD 组的成员。</span><span class="sxs-lookup"><span data-stu-id="e61a0-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="e61a0-132">这称为 *动态组成员身份*。</span><span class="sxs-lookup"><span data-stu-id="e61a0-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="e61a0-133">这些规则将基于用户帐户属性，如部门或国家/地区。</span><span class="sxs-lookup"><span data-stu-id="e61a0-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="e61a0-134">下面是如何应用这些规则：</span><span class="sxs-lookup"><span data-stu-id="e61a0-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="e61a0-135">如果新用户帐户符合组的所有规则，则其会变为成员。</span><span class="sxs-lookup"><span data-stu-id="e61a0-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="e61a0-136">如果用户帐户不是组成员，但其属性更改，以便其匹配组的所有规则，则其会变为该组的成员。</span><span class="sxs-lookup"><span data-stu-id="e61a0-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="e61a0-137">如果用户帐户不匹配组的所有规则，则其不会添加到组。</span><span class="sxs-lookup"><span data-stu-id="e61a0-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="e61a0-138">如果用户帐户是组成员，但其属性更改，以便其不再匹配组的所有规则，则会从该组成员中将其删除。</span><span class="sxs-lookup"><span data-stu-id="e61a0-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="e61a0-p108">若要使用动态成员身份，则必须先确定有一组常用的用户帐户属性。例如，销售部门的所有成员都应在“销售 Azure AD”组中，根据用户帐户属性部门设置为“Sales”。</span><span class="sxs-lookup"><span data-stu-id="e61a0-p108">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="e61a0-141">请参阅[为动态 Azure AD 组创建并配置规则的说明](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="e61a0-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="e61a0-142">设置自动许可</span><span class="sxs-lookup"><span data-stu-id="e61a0-142">Set up automatic licensing</span></span>

<span data-ttu-id="e61a0-143">可以在 Azure AD 中配置安全组，以自动将一组订阅中的许可证分配给组的所有成员。</span><span class="sxs-lookup"><span data-stu-id="e61a0-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="e61a0-144">这称为 *基于组的许可*。</span><span class="sxs-lookup"><span data-stu-id="e61a0-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="e61a0-145">如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或取消分配给该用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e61a0-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="e61a0-146">对于 Microsoft 365 企业版，将配置 Azure AD 安全组，以分配相应的 Microsoft 365 企业版许可证。</span><span class="sxs-lookup"><span data-stu-id="e61a0-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="e61a0-147">确保所有组成员都有足够的许可证。</span><span class="sxs-lookup"><span data-stu-id="e61a0-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="e61a0-148">如果许可证用完，将不会向新用户分配许可证，直到许可证可用。</span><span class="sxs-lookup"><span data-stu-id="e61a0-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="e61a0-149">不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”。</span><span class="sxs-lookup"><span data-stu-id="e61a0-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="e61a0-150">有关详细信息，请参阅 [Azure AD](/azure/active-directory/active-directory-licensing-whatis-azure-portal)中基于组的许可基础知识。</span><span class="sxs-lookup"><span data-stu-id="e61a0-150">For more information, see [Group-based licensing basics in Azure AD](/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="e61a0-151">请参阅 [为 Azure 安全组](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)配置基于组的许可的说明。</span><span class="sxs-lookup"><span data-stu-id="e61a0-151">See the [instructions to configure group-based licensing for an Azure security group](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>