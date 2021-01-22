---
title: 在 Microsoft 365 安全中心管理对 Microsoft 365 Defender 数据的访问权限
description: 了解如何在 Microsoft 365 Defender 中管理数据权限
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930134"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="016ed-104">管理对 Microsoft 365 Defender 的访问权限</span><span class="sxs-lookup"><span data-stu-id="016ed-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="016ed-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="016ed-105">**Applies to:**</span></span>
- <span data-ttu-id="016ed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="016ed-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="016ed-107">分配了以下 Azure Active Directory (AD) 帐户可以访问 Microsoft 365 Defender 功能和数据：</span><span class="sxs-lookup"><span data-stu-id="016ed-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="016ed-108">全局管理员</span><span class="sxs-lookup"><span data-stu-id="016ed-108">Global administrator</span></span>
- <span data-ttu-id="016ed-109">安全管理员</span><span class="sxs-lookup"><span data-stu-id="016ed-109">Security administrator</span></span>
- <span data-ttu-id="016ed-110">安全操作员</span><span class="sxs-lookup"><span data-stu-id="016ed-110">Security Operator</span></span>
- <span data-ttu-id="016ed-111">全局读取者</span><span class="sxs-lookup"><span data-stu-id="016ed-111">Global Reader</span></span>
- <span data-ttu-id="016ed-112">安全读取者</span><span class="sxs-lookup"><span data-stu-id="016ed-112">Security Reader</span></span>

<span data-ttu-id="016ed-113">若要查看具有这些角色的帐户，请[在 Microsoft 365 安全中心中查看权限](https://security.microsoft.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="016ed-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="016ed-114">对功能的访问权限</span><span class="sxs-lookup"><span data-stu-id="016ed-114">Access to functionality</span></span>
<span data-ttu-id="016ed-115">对特定功能的访问权限由 [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)确定。</span><span class="sxs-lookup"><span data-stu-id="016ed-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="016ed-116">如果需要访问要求你或你的用户组分配有新角色的特定功能，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="016ed-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="016ed-117">批准挂起的自动化任务</span><span class="sxs-lookup"><span data-stu-id="016ed-117">Approve pending automated tasks</span></span>
<span data-ttu-id="016ed-118">[自动调查和修复](mtp-autoir-actions.md)可以针对电子邮件、转发规则、文件、持久性机制和调查过程中找到的其他项目执行操作。</span><span class="sxs-lookup"><span data-stu-id="016ed-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="016ed-119">若要批准或拒绝需要显式审批的挂起操作，必须在 Microsoft 365 中分配特定角色。</span><span class="sxs-lookup"><span data-stu-id="016ed-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="016ed-120">若要了解详细信息，请参阅[操作中心权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="016ed-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="016ed-121">对数据的访问</span><span class="sxs-lookup"><span data-stu-id="016ed-121">Access to data</span></span>
<span data-ttu-id="016ed-122">可以使用分配给 Microsoft Defender 中用户组的作用域控制对 Microsoft 365 Defender 数据的访问权限，该范围适用于基于终结点角色的访问控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="016ed-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="016ed-123">如果你的访问范围尚未确定为 Defender for Endpoint 中的一组特定设备，你将具有对 Microsoft 365 Defender 中数据的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="016ed-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="016ed-124">但是，在限定帐户范围后，你将只看到有关范围内的设备的数据。</span><span class="sxs-lookup"><span data-stu-id="016ed-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="016ed-125">例如，如果你仅属于具有 Microsoft Defender for Endpoint 角色的一个用户组，并且该用户组仅有权访问销售设备，你将只看到有关 Microsoft 365 Defender 中销售设备的数据。</span><span class="sxs-lookup"><span data-stu-id="016ed-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="016ed-126">了解有关 Microsoft Defender for Endpoint 中的 RBAC 设置</span><span class="sxs-lookup"><span data-stu-id="016ed-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="016ed-127">Microsoft Cloud App Security 访问控制</span><span class="sxs-lookup"><span data-stu-id="016ed-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="016ed-128">在预览版中，Microsoft 365 Defender 不会基于云应用安全设置强制实施访问控制。</span><span class="sxs-lookup"><span data-stu-id="016ed-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="016ed-129">这些设置不会影响对 Microsoft 365 Defender 数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="016ed-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="016ed-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="016ed-130">Related topics</span></span>

- [<span data-ttu-id="016ed-131">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="016ed-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="016ed-132">适用于终结点 RBAC 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="016ed-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="016ed-133">Cloud App Security 角色</span><span class="sxs-lookup"><span data-stu-id="016ed-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
