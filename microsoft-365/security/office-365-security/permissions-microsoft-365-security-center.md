---
title: Microsoft 365 Defender 门户中的权限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 管理员可以了解如何在 Microsoft 365 Defender 门户中管理与安全相关的所有任务的权限。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4ed1d90bdc6e222d44179a77e9617d05909a4258
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926459"
---
# <a name="permissions-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="6562c-103">Microsoft 365 Defender 门户中的权限</span><span class="sxs-lookup"><span data-stu-id="6562c-103">Permissions in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6562c-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="6562c-104">**Applies to**</span></span>
- [<span data-ttu-id="6562c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6562c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6562c-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="6562c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6562c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6562c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6562c-108">需要管理跨所有 Microsoft 365 服务的安全方案。</span><span class="sxs-lookup"><span data-stu-id="6562c-108">You need to manage security scenarios that span all the Microsoft 365 services.</span></span> <span data-ttu-id="6562c-109">并且你需要灵活地向组织 IT 组中的正确人员授予正确的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="6562c-109">And you need the flexibility to give the right admin permissions to the right people in your organization.</span></span>

<span data-ttu-id="6562c-110">Microsoft 365 Defender 门户 (<https://security.microsoft.com>) 支持为在 Microsoft 365 中执行安全任务的用户直接管理权限。</span><span class="sxs-lookup"><span data-stu-id="6562c-110">The Microsoft 365 Defender portal at <https://security.microsoft.com> supports directly managing permissions for users who perform security tasks in Microsoft 365.</span></span> <span data-ttu-id="6562c-111">通过使用 Microsoft 365 Defender 门户管理权限，你可以集中管理与安全相关的所有任务的权限。</span><span class="sxs-lookup"><span data-stu-id="6562c-111">By using the Microsoft 365 Defender portal to manage permissions, you can manage permissions centrally for all tasks related to security.</span></span>

<span data-ttu-id="6562c-112">若要在 Microsoft 365 Defender 门户中管理权限，请转到“**权限和角色**”或 <https://security.microsoft.com/securitypermissions>。</span><span class="sxs-lookup"><span data-stu-id="6562c-112">To manage permissions in the Microsoft 365 Defender portal, go to **Permissions & roles** or <https://security.microsoft.com/securitypermissions>.</span></span> <span data-ttu-id="6562c-113">你需要是 Microsoft 365 Defender 门户中的 **全局管理员** 或“**组织管理**”角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="6562c-113">You need to be a **global administrator** or a member of the **Organization Management** role group in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="6562c-114">具体而言，“**角色管理**”角色允许用户在 Microsoft 365 Defender 门户中查看、创建和修改角色组，默认情况下，该角色仅分配给“**组织管理**”角色组。</span><span class="sxs-lookup"><span data-stu-id="6562c-114">Specifically, the **Role Management** role allows users to view, create, and modify role groups in the Microsoft 365 Defender portal, and by default, that role is assigned only to the **Organization Management** role group.</span></span>

> [!NOTE]
> <span data-ttu-id="6562c-115">有关 Microsoft 365 合规中心中的权限的信息，请参阅 [Microsoft 365 合规中心中的权限](../../compliance/microsoft-365-compliance-center-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="6562c-115">For information about permissions in the Microsoft 365 compliance center, see [Permissions in the Microsoft 365 compliance center](../../compliance/microsoft-365-compliance-center-permissions.md).</span></span>

## <a name="relationship-of-members-roles-and-role-groups"></a><span data-ttu-id="6562c-116">成员、角色和角色组之间的关系</span><span class="sxs-lookup"><span data-stu-id="6562c-116">Relationship of members, roles, and role groups</span></span>

<span data-ttu-id="6562c-117">Microsoft 365 Defender 门户中的权限以基于角色的访问控制 (RBAC) 权限模型为基础。</span><span class="sxs-lookup"><span data-stu-id="6562c-117">Permissions in the Microsoft 365 Defender portal are based on the role-based access control (RBAC) permissions model.</span></span> <span data-ttu-id="6562c-118">RBAC 与大多数 Microsoft 365 服务使用的权限模型相同，因此如果你熟悉这些服务中的权限结构，那么将非常熟悉如何在 Microsoft 365 Defender 门户中授予权限。</span><span class="sxs-lookup"><span data-stu-id="6562c-118">RBAC is the same permissions model that's used by most Microsoft 365 services, so if you're familiar with the permission structure in these services, granting permissions in the Microsoft 365 Defender portal will be very familiar.</span></span>

<span data-ttu-id="6562c-119">**角色** 授予执行一组任务的权限。</span><span class="sxs-lookup"><span data-stu-id="6562c-119">A **role** grants the permissions to do a set of tasks.</span></span>

<span data-ttu-id="6562c-120">**角色组** 是一组允许人们在 Microsoft 365 Defender 门户中完成工作的角色。</span><span class="sxs-lookup"><span data-stu-id="6562c-120">A **role group** is a set of roles that lets people do their jobs in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="6562c-121">例如，攻击模拟器管理员角色组包括攻击模拟器管理员角色，以创建和管理攻击模拟培训的所有方面。</span><span class="sxs-lookup"><span data-stu-id="6562c-121">For example, the Attack Simulator Administrators role group includes the Attack Simulator Admin role to create and manage all aspects of attack simulation training.</span></span>

<span data-ttu-id="6562c-122">Microsoft 365 Defender 门户包括你需要分配的最常见任务和功能的默认角色组。</span><span class="sxs-lookup"><span data-stu-id="6562c-122">The Microsoft 365 Defender portal includes default role groups for the most common tasks and functions that you'll need to assign.</span></span> <span data-ttu-id="6562c-123">通常，我们建议你只需将单个用户作为 **成员** 添加到默认角色组。</span><span class="sxs-lookup"><span data-stu-id="6562c-123">Generally, we recommend simply adding individual users as **members** to the default role groups.</span></span>

![显示角色组与角色和成员之间关系的图表](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="6562c-125">Microsoft 365 Defender 门户中的角色和角色组</span><span class="sxs-lookup"><span data-stu-id="6562c-125">Roles and role groups in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="6562c-126">Microsoft 365 Defender 门户中的“**权限和角色**”提供了以下类型的角色和角色组：</span><span class="sxs-lookup"><span data-stu-id="6562c-126">The following types of roles and role groups are available in **Permissions & roles** in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="6562c-127">**Azure AD 角色**：可以查看角色和分配的用户，但无法在 Microsoft 365 Defender 门户中直接管理它们。</span><span class="sxs-lookup"><span data-stu-id="6562c-127">**Azure AD roles**: You can view the roles and assigned users, but you can't manage them directly in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="6562c-128">Azure AD 角色是为 **所有** Microsoft 365 服务分配权限的中心角色。</span><span class="sxs-lookup"><span data-stu-id="6562c-128">Azure AD roles are central roles that assign permissions for **all** Microsoft 365 services.</span></span>

- <span data-ttu-id="6562c-129">**电子邮件和协作角色**：这些角色组与安全与合规中心中可用的角色组相同，但可以直接在 Microsoft 365 Defender 门户中管理它们。</span><span class="sxs-lookup"><span data-stu-id="6562c-129">**Email & collaboration roles**: These are the same role groups that are available in the Security & Compliance Center, but you can manage them directly in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="6562c-130">在此处分配的权限特定于 Microsoft 365 Defender 门户、Microsoft 365 合规中心和安全与合规性中心，不包括其他 Microsoft 365 工作负载所需的所有权限。</span><span class="sxs-lookup"><span data-stu-id="6562c-130">The permissions that you assign here are specific to the Microsoft 365 Defender portal, the Microsoft 365 compliance center, and the Security & Compliance Center, and don't cover all of the permissions that are needed in other Microsoft 365 workloads.</span></span>

![Microsoft 365 Defender 门户中的权限和角色页面](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="6562c-132">Microsoft 365 Defender 门户中的 Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="6562c-132">Azure AD roles in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="6562c-133">转到 **电子邮件和协作角色** \> **权限和角色** \> **Azure AD 角色** \> **角色** （或直接发送到 <https://security.microsoft.com/aadpermissions>），你将看到本部分中介绍的 Azure AD 角色。</span><span class="sxs-lookup"><span data-stu-id="6562c-133">When you go **Email & collaboration roles** \> **Permissions & roles** \> **Azure AD roles** \> **Roles** (or directly to <https://security.microsoft.com/aadpermissions>) you'll see the Azure AD roles that are described in this section.</span></span>

<span data-ttu-id="6562c-134">选择某个角色时，会显示一个包含角色说明和用户分配的详细信息飞出。</span><span class="sxs-lookup"><span data-stu-id="6562c-134">When you select a role, a details flyout that contains the description of the role and the user assignments appears.</span></span> <span data-ttu-id="6562c-135">但是要管理这些分配，您需要在详细信息弹出按钮中单击 **管理 Azure AD 中的成员**。</span><span class="sxs-lookup"><span data-stu-id="6562c-135">But to manage those assignments, you need to click **Manage members in Azure AD** in the details flyout.</span></span>

![链接以管理 Azure Active Directory 中的权限](../../media/permissions-manage-in-azure-ad-link.png)

<span data-ttu-id="6562c-137">有关详细信息，请参阅[查看和分配 Azure Active Directory 中的管理员角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="6562c-137">For more information, see [View and assign administrator roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<br>

****

|<span data-ttu-id="6562c-138">角色</span><span class="sxs-lookup"><span data-stu-id="6562c-138">Role</span></span>|<span data-ttu-id="6562c-139">说明</span><span class="sxs-lookup"><span data-stu-id="6562c-139">Description</span></span>|
|---|---|
|<span data-ttu-id="6562c-140">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="6562c-140">**Global administrator**</span></span>|<span data-ttu-id="6562c-141">访问所有 Microsoft 365 服务中的所有管理功能的权限。</span><span class="sxs-lookup"><span data-stu-id="6562c-141">Access to all administrative features in all Microsoft 365 services.</span></span> <span data-ttu-id="6562c-142">只有全局管理员才能分配其他管理员角色。</span><span class="sxs-lookup"><span data-stu-id="6562c-142">Only global administrators can assign other administrator roles.</span></span> <span data-ttu-id="6562c-143">更多信息，请参阅[全局管理员/公司管理员](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)。</span><span class="sxs-lookup"><span data-stu-id="6562c-143">For more information, see [Global Administrator / Company Administrator](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).</span></span>|
|<span data-ttu-id="6562c-144">**合规性数据管理员**</span><span class="sxs-lookup"><span data-stu-id="6562c-144">**Compliance data administrator**</span></span>|<span data-ttu-id="6562c-145">在 Microsoft 365 中跟踪组织的数据，确保数据受到保护，并深入了解任何问题以帮助缓解风险。</span><span class="sxs-lookup"><span data-stu-id="6562c-145">Keep track of your organization's data across Microsoft 365, make sure it's protected, and get insights into any issues to help mitigate risks.</span></span> <span data-ttu-id="6562c-146">有关详细信息，请参阅[合规性数据管理员](/azure/active-directory/roles/permissions-reference#compliance-data-administrator)。</span><span class="sxs-lookup"><span data-stu-id="6562c-146">For more information, see [Compliance Data Administrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).</span></span>|
|<span data-ttu-id="6562c-147">**合规性管理员**</span><span class="sxs-lookup"><span data-stu-id="6562c-147">**Compliance administrator**</span></span>|<span data-ttu-id="6562c-148">帮助组织遵守任何法规要求，管理电子数据展示案例，并维护 Microsoft 365 位置、标识和应用中的数据治理策略。</span><span class="sxs-lookup"><span data-stu-id="6562c-148">Help your organization stay compliant with any regulatory requirements, manage eDiscovery cases, and maintain data governance policies across Microsoft 365 locations, identities, and apps.</span></span> <span data-ttu-id="6562c-149">有关详细信息，请参阅[合规性管理员](/azure/active-directory/roles/permissions-reference#compliance-administrator)。</span><span class="sxs-lookup"><span data-stu-id="6562c-149">For more information, see [Compliance Administrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).</span></span>|
|<span data-ttu-id="6562c-150">**安全操作员**</span><span class="sxs-lookup"><span data-stu-id="6562c-150">**Security operator**</span></span>|<span data-ttu-id="6562c-151">查看、调查和响应对 Microsoft 365 用户、设备和内容的活动威胁。</span><span class="sxs-lookup"><span data-stu-id="6562c-151">View, investigate, and respond to active threats to your Microsoft 365 users, devices, and content.</span></span> <span data-ttu-id="6562c-152">有关详细信息，请参阅[安全操作员](/azure/active-directory/roles/permissions-reference#security-operator)。</span><span class="sxs-lookup"><span data-stu-id="6562c-152">For more information, see [Security Operator](/azure/active-directory/roles/permissions-reference#security-operator).</span></span>|
|<span data-ttu-id="6562c-153">**安全信息读取者**</span><span class="sxs-lookup"><span data-stu-id="6562c-153">**Security reader**</span></span>|<span data-ttu-id="6562c-154">查看和调查对 Microsoft 365 用户、设备和内容的活动威胁，但（不同于安全操作员）他们无权采取措施来进行响应。</span><span class="sxs-lookup"><span data-stu-id="6562c-154">View and investigate active threats to your Microsoft 365 users, devices, and content, but (unlike the Security operator) they do not have permissions to respond by taking action.</span></span> <span data-ttu-id="6562c-155">有关详细信息，请参阅[安全信息读取者](/azure/active-directory/roles/permissions-reference#security-reader)。</span><span class="sxs-lookup"><span data-stu-id="6562c-155">For more information, see [Security Reader](/azure/active-directory/roles/permissions-reference#security-reader).</span></span>|
|<span data-ttu-id="6562c-156">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="6562c-156">**Security administrator**</span></span>|<span data-ttu-id="6562c-157">通过管理安全策略、查看 Microsoft 365 产品中的安全分析和报告以及及时了解威胁形势来控制组织的总体安全。</span><span class="sxs-lookup"><span data-stu-id="6562c-157">Control your organization's overall security by managing security policies, reviewing security analytics and reports across Microsoft 365 products, and staying up-to-speed on the threat landscape.</span></span> <span data-ttu-id="6562c-158">有关详细信息，请参阅[安全管理员](/azure/active-directory/roles/permissions-reference#security-administrator)。</span><span class="sxs-lookup"><span data-stu-id="6562c-158">For more information, see [Security Administrator](/azure/active-directory/roles/permissions-reference#security-administrator).</span></span>|
|<span data-ttu-id="6562c-159">**全局读取者**</span><span class="sxs-lookup"><span data-stu-id="6562c-159">**Global reader**</span></span>|<span data-ttu-id="6562c-160">只读版本的 **全局管理员** 角色。</span><span class="sxs-lookup"><span data-stu-id="6562c-160">The read-only version of the **Global administrator** role.</span></span> <span data-ttu-id="6562c-161">查看 Microsoft 365 中所有设置和管理信息。</span><span class="sxs-lookup"><span data-stu-id="6562c-161">View all settings and administrative information across Microsoft 365.</span></span> <span data-ttu-id="6562c-162">有关详细信息，请参阅 [全局信息读取者](/azure/active-directory/roles/permissions-reference#global-reader)。</span><span class="sxs-lookup"><span data-stu-id="6562c-162">For more information, see [Global Reader](/azure/active-directory/roles/permissions-reference#global-reader).</span></span>|
|<span data-ttu-id="6562c-163">**攻击模拟管理员**</span><span class="sxs-lookup"><span data-stu-id="6562c-163">**Attack simulation administrator**</span></span>|<span data-ttu-id="6562c-164">创建和管理 [攻击模拟](attack-simulation-training.md) 创建、启动/安排模拟以及审查模拟结果的各个方面。</span><span class="sxs-lookup"><span data-stu-id="6562c-164">Create and manage all aspects of [attack simulation](attack-simulation-training.md) creation, launch/scheduling of a simulation, and the review of simulation results.</span></span> <span data-ttu-id="6562c-165">有关详细信息，请参阅 [攻击模拟管理员](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)。</span><span class="sxs-lookup"><span data-stu-id="6562c-165">For more information, see [Attack Simulation Administrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).</span></span>|
|<span data-ttu-id="6562c-166">**攻击有效负载作者**</span><span class="sxs-lookup"><span data-stu-id="6562c-166">**Attack payload author**</span></span>|<span data-ttu-id="6562c-167">创建攻击负载，但不真正开始或计划其目标。</span><span class="sxs-lookup"><span data-stu-id="6562c-167">Create attack payloads but not actually launch or schedule them.</span></span> <span data-ttu-id="6562c-168">有关详细信息，请参阅[攻击有效负载作者](/azure/active-directory/roles/permissions-reference#attack-payload-author)。</span><span class="sxs-lookup"><span data-stu-id="6562c-168">For more information, see [Attack Payload Author](/azure/active-directory/roles/permissions-reference#attack-payload-author).</span></span>|
|

### <a name="email--collaboration-roles-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="6562c-169">Microsoft 365 Defender 门户中的电子邮件和协作角色</span><span class="sxs-lookup"><span data-stu-id="6562c-169">Email & collaboration roles in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="6562c-170">转到 **电子邮件和协作角色** \> **权限和角色** \> **电子邮件和协作角色** \> **角色** （或直接发送到 <https://security.microsoft.com/emailandcollabpermissions>），你将看到安全与合规中心中可用的相同角色组。</span><span class="sxs-lookup"><span data-stu-id="6562c-170">When you go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles** (or directly to <https://security.microsoft.com/emailandcollabpermissions>) you'll see the same role groups that are available in the Security & Compliance Center.</span></span>

<span data-ttu-id="6562c-171">有关这些角色组的完整信息，请参阅 [安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="6562c-171">For complete information about these role groups, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

#### <a name="modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="6562c-172">在 Microsoft 365 Defender 门户中修改电子邮件和协作角色成员资格</span><span class="sxs-lookup"><span data-stu-id="6562c-172">Modify Email & collaboration role membership in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="6562c-173">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作角色**”\>“**权限和角色**”\>“**电子邮件和协作角色**”\>“**角色**”。</span><span class="sxs-lookup"><span data-stu-id="6562c-173">In the Microsoft 365 Defender portal, go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles**.</span></span>

2. <span data-ttu-id="6562c-174">在打开的 **权限** 页面中，从列表中选择要修改的角色组。</span><span class="sxs-lookup"><span data-stu-id="6562c-174">In the **Permissions** page that opens, select the role group that you want to modify from the list.</span></span> <span data-ttu-id="6562c-175">你可以单击列标题 **名称** 以按名称对列表进行排序，也可以单击 **搜索** ![搜索"图标](../../media/m365-cc-sc-search-icon.png) 以查找角色组。</span><span class="sxs-lookup"><span data-stu-id="6562c-175">You can click on the **Name** column header to sort the list by name, or you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find the role group.</span></span>

3. <span data-ttu-id="6562c-176">在显示的角色组详细信息飞出中，单击 **成员** 部分中的 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="6562c-176">In the role group details flyout that appears, click **Edit** in the **Members** section.</span></span>

4. <span data-ttu-id="6562c-177">在出现的 **“编辑选择成员”** 页面中，请执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="6562c-177">In the **Editing choose members** page that appears, do one of the following steps:</span></span>
   - <span data-ttu-id="6562c-178">如果没有角色组成员，请单击 **选择成员**。</span><span class="sxs-lookup"><span data-stu-id="6562c-178">If there are no role group members, click **Choose members**.</span></span>
   - <span data-ttu-id="6562c-179">如果已有角色组成员，请单击 **"编辑"**</span><span class="sxs-lookup"><span data-stu-id="6562c-179">If there are existing role group members, click **Edit**</span></span>

5. <span data-ttu-id="6562c-180">在出现的 **“选择成员”** 弹出按钮中，执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="6562c-180">In the **Choose members** flyout that appears, do one of the following steps:</span></span>

   - <span data-ttu-id="6562c-181">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6562c-181">Click **Add**.</span></span> <span data-ttu-id="6562c-182">在显示的用户列表中，选择一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="6562c-182">In the list of users that appears, select one or more users.</span></span> <span data-ttu-id="6562c-183">或者，可以单击 **搜索** ![搜索图标](../../media/m365-cc-sc-search-icon.png) 查找和选择用户。</span><span class="sxs-lookup"><span data-stu-id="6562c-183">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select users.</span></span>

     <span data-ttu-id="6562c-184">选中要添加的用户后，单击 **"添加"**。</span><span class="sxs-lookup"><span data-stu-id="6562c-184">When you've selected the users that you want to add, click **Add**.</span></span>

   - <span data-ttu-id="6562c-185">单击 **“移除”**。</span><span class="sxs-lookup"><span data-stu-id="6562c-185">Click **Remove**.</span></span> <span data-ttu-id="6562c-186">选择一个或多个现有成员。</span><span class="sxs-lookup"><span data-stu-id="6562c-186">Select one or more of the existing members.</span></span> <span data-ttu-id="6562c-187">或者，可以单击 **搜索** ![搜索图标](../../media/m365-cc-sc-search-icon.png) 查找和选择用户。</span><span class="sxs-lookup"><span data-stu-id="6562c-187">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select members.</span></span>

     <span data-ttu-id="6562c-188">选中要删除的用户后，单击 **"删除"**。</span><span class="sxs-lookup"><span data-stu-id="6562c-188">When you've selected the users that you want to remove, click **Remove**.</span></span>

6. <span data-ttu-id="6562c-189">返回 **“选择成员”** 弹出按钮，单击 **完成**。</span><span class="sxs-lookup"><span data-stu-id="6562c-189">Back on the **Choose members** flyout, click **Done**.</span></span>

7. <span data-ttu-id="6562c-190">返回 **编辑选择成员** 页面，点击 **保存**。</span><span class="sxs-lookup"><span data-stu-id="6562c-190">Back on the **Editing choose members** page, click **Save**.</span></span>

8. <span data-ttu-id="6562c-191">返回角色组详细信息浮出控件，单击 **完成**。</span><span class="sxs-lookup"><span data-stu-id="6562c-191">Back on the role group details flyout, click **Done**.</span></span>
