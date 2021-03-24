---
title: 在 Microsoft 365 安全中心管理对 Microsoft 365 Defender 数据的访问权限
description: 了解如何在 Microsoft 365 Defender 中管理对数据的权限
keywords: 访问, 权限, MTP, Microsoft 威胁防护, M365, 安全性, MCAS, MDATP, Cloud App Security, Microsoft Defender 高级威胁防护, 范围, 范围, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e1be2cf4d5510b2a31a61f848d7d99d6a6704d49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056546"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="d48ef-104">使用 Azure Active Directory 全局角色管理对 Microsoft 365 Defender 的访问权限</span><span class="sxs-lookup"><span data-stu-id="d48ef-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d48ef-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d48ef-105">**Applies to:**</span></span>
- <span data-ttu-id="d48ef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d48ef-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d48ef-107">有两种方法可以管理对 Microsoft 365 Defender 的访问权限</span><span class="sxs-lookup"><span data-stu-id="d48ef-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="d48ef-108">**全局 Azure Active Directory (AD) 角色**</span><span class="sxs-lookup"><span data-stu-id="d48ef-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="d48ef-109">**自定义角色访问**</span><span class="sxs-lookup"><span data-stu-id="d48ef-109">**Custom role access**</span></span>

<span data-ttu-id="d48ef-110">分配了以下全局 **Azure Active Directory (AD) 的帐户** 可以访问 Microsoft 365 Defender 功能和数据：</span><span class="sxs-lookup"><span data-stu-id="d48ef-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="d48ef-111">全局管理员</span><span class="sxs-lookup"><span data-stu-id="d48ef-111">Global administrator</span></span>
- <span data-ttu-id="d48ef-112">安全管理员</span><span class="sxs-lookup"><span data-stu-id="d48ef-112">Security administrator</span></span>
- <span data-ttu-id="d48ef-113">安全操作员</span><span class="sxs-lookup"><span data-stu-id="d48ef-113">Security Operator</span></span>
- <span data-ttu-id="d48ef-114">全局读取者</span><span class="sxs-lookup"><span data-stu-id="d48ef-114">Global Reader</span></span>
- <span data-ttu-id="d48ef-115">安全读取者</span><span class="sxs-lookup"><span data-stu-id="d48ef-115">Security Reader</span></span>

<span data-ttu-id="d48ef-116">若要查看具有这些角色的帐户，请[在 Microsoft 365 安全中心中查看权限](https://security.microsoft.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="d48ef-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="d48ef-117">**自定义角色** 访问是 Microsoft 365 Defender 中的一项新功能，允许你管理对 Microsoft Defender 365 中特定数据、任务和功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d48ef-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="d48ef-118">自定义角色提供比全局 Azure AD 角色更多的控制，从而仅为用户提供所需的访问权限以及所需的最小权限角色。</span><span class="sxs-lookup"><span data-stu-id="d48ef-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="d48ef-119">除了全局 Azure AD 角色之外，还可以创建自定义角色。</span><span class="sxs-lookup"><span data-stu-id="d48ef-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="d48ef-120">[详细了解自定义角色](custom-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d48ef-120">[Learn more about custom roles](custom-roles.md).</span></span>

> <span data-ttu-id="d48ef-121">![注意]本文仅适用于管理全局 Azure Active Directory 角色。</span><span class="sxs-lookup"><span data-stu-id="d48ef-121">![NOTE] This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="d48ef-122">有关使用基于自定义角色的访问控制的信息，请参阅基于 [角色的访问控制的自定义角色](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d48ef-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="d48ef-123">对功能的访问权限</span><span class="sxs-lookup"><span data-stu-id="d48ef-123">Access to functionality</span></span>
<span data-ttu-id="d48ef-124">对特定功能的访问权限由 [Azure AD 角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)确定。</span><span class="sxs-lookup"><span data-stu-id="d48ef-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="d48ef-125">如果需要访问要求你或你的用户组分配有新角色的特定功能，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="d48ef-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="d48ef-126">批准挂起的自动化任务</span><span class="sxs-lookup"><span data-stu-id="d48ef-126">Approve pending automated tasks</span></span>
<span data-ttu-id="d48ef-127">[自动调查和修复](m365d-autoir-actions.md)可以针对电子邮件、转发规则、文件、持久性机制和调查过程中找到的其他项目执行操作。</span><span class="sxs-lookup"><span data-stu-id="d48ef-127">[Automated investigation and remediation](m365d-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="d48ef-128">若要批准或拒绝需要显式审批的挂起操作，必须在 Microsoft 365 中分配特定角色。</span><span class="sxs-lookup"><span data-stu-id="d48ef-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="d48ef-129">若要了解详细信息，请参阅[操作中心权限](m365d-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="d48ef-129">To learn more, see [Action center permissions](m365d-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="d48ef-130">对数据的访问</span><span class="sxs-lookup"><span data-stu-id="d48ef-130">Access to data</span></span>
<span data-ttu-id="d48ef-131">可以使用在 Microsoft Defender 中为基于终结点角色的访问控制分配至用户组的范围控制对 Microsoft 365 Defender 数据 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="d48ef-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="d48ef-132">如果你的访问范围尚未确定为 Defender for Endpoint 中的一组特定设备，你将具有对 Microsoft 365 Defender 中数据的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="d48ef-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="d48ef-133">但是，在限定帐户范围后，你将只看到有关范围内的设备的数据。</span><span class="sxs-lookup"><span data-stu-id="d48ef-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="d48ef-134">例如，如果你仅属于具有 Microsoft Defender for Endpoint 角色的一个用户组，并且该用户组只获得对销售设备的访问权限，你将只看到有关 Microsoft 365 Defender 中销售设备的数据。</span><span class="sxs-lookup"><span data-stu-id="d48ef-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="d48ef-135">详细了解 Microsoft Defender for Endpoint 中的 RBAC 设置</span><span class="sxs-lookup"><span data-stu-id="d48ef-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="d48ef-136">Microsoft Cloud App Security 访问控制</span><span class="sxs-lookup"><span data-stu-id="d48ef-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="d48ef-137">在预览版中，Microsoft 365 Defender 不会基于 Cloud App Security 设置强制执行访问控制。</span><span class="sxs-lookup"><span data-stu-id="d48ef-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="d48ef-138">这些设置不会影响对 Microsoft 365 Defender 数据的访问。</span><span class="sxs-lookup"><span data-stu-id="d48ef-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d48ef-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="d48ef-139">Related topics</span></span>
- [<span data-ttu-id="d48ef-140">Microsoft 365 Defender 基于角色的访问控制中的自定义角色</span><span class="sxs-lookup"><span data-stu-id="d48ef-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="d48ef-141">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="d48ef-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="d48ef-142">适用于终结点 RBAC 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d48ef-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="d48ef-143">Cloud App Security 角色</span><span class="sxs-lookup"><span data-stu-id="d48ef-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)