---
title: 在 Microsoft 365 安全中心中管理对 Microsoft 威胁防护数据的访问权限
description: 了解如何管理对 Microsoft 威胁防护数据的访问权限
keywords: 访问, 权限, MTP, Microsoft 威胁防护, M365, 安全性, MCAS, MDATP, Cloud App Security, Microsoft Defender 高级威胁防护, 范围, 范围, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: df4450271b7cbbd1862b86cbed295c88c168d66d
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910850"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="80aa2-104">管理对 Microsoft 威胁防护的访问权限</span><span class="sxs-lookup"><span data-stu-id="80aa2-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="80aa2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="80aa2-105">**Applies to:**</span></span>
- <span data-ttu-id="80aa2-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="80aa2-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="80aa2-107">分配了以下 Azure Active Directory (AD) 角色的帐户可以访问 Microsoft 威胁防护功能和数据：</span><span class="sxs-lookup"><span data-stu-id="80aa2-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="80aa2-108">全局管理员</span><span class="sxs-lookup"><span data-stu-id="80aa2-108">Global administrator</span></span>
- <span data-ttu-id="80aa2-109">安全管理员</span><span class="sxs-lookup"><span data-stu-id="80aa2-109">Security administrator</span></span>
- <span data-ttu-id="80aa2-110">安全操作员</span><span class="sxs-lookup"><span data-stu-id="80aa2-110">Security operator</span></span>
- <span data-ttu-id="80aa2-111">全局读取者</span><span class="sxs-lookup"><span data-stu-id="80aa2-111">Global Reader</span></span>
- <span data-ttu-id="80aa2-112">安全读取者</span><span class="sxs-lookup"><span data-stu-id="80aa2-112">Security reader</span></span>

<span data-ttu-id="80aa2-113">若要查看具有这些角色的帐户，请[在 Microsoft 365 安全中心中查看权限](https://security.microsoft.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="80aa2-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="80aa2-114">对功能的访问权限</span><span class="sxs-lookup"><span data-stu-id="80aa2-114">Access to SharePoint data and functionality</span></span>
<span data-ttu-id="80aa2-115">对特定功能的访问权限由 [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)确定。</span><span class="sxs-lookup"><span data-stu-id="80aa2-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="80aa2-116">如果需要访问要求你或你的用户组分配有新角色的特定功能，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="80aa2-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="80aa2-117">批准挂起的自动化任务</span><span class="sxs-lookup"><span data-stu-id="80aa2-117">Approve pending automated tasks</span></span>
<span data-ttu-id="80aa2-118">[自动调查和修复](mtp-autoir-actions.md)可以针对电子邮件、转发规则、文件、持久性机制和调查过程中找到的其他项目执行操作。</span><span class="sxs-lookup"><span data-stu-id="80aa2-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="80aa2-119">若要批准或拒绝需要显式审批的挂起操作，必须在 Microsoft 365 中分配特定角色。</span><span class="sxs-lookup"><span data-stu-id="80aa2-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="80aa2-120">若要了解详细信息，请参阅[操作中心权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="80aa2-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="80aa2-121">对数据的访问</span><span class="sxs-lookup"><span data-stu-id="80aa2-121">Access to non-Microsoft data sources</span></span>
<span data-ttu-id="80aa2-122">可以使用为 Microsoft Defender ATP 基于角色的访问控制 (RBAC) 中的用户组分配的范围控制对 Microsoft 威胁防护数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="80aa2-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="80aa2-123">如果你的访问权限未限定于 Microsoft Defender ATP 中的一组特定设备，则你将具有对 Microsoft 威胁防护数据的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="80aa2-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="80aa2-124">但是，在限定帐户范围后，你将只看到有关范围内的设备的数据。</span><span class="sxs-lookup"><span data-stu-id="80aa2-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="80aa2-125">例如，如果你仅属于一个具有 Microsoft Defender ATP 角色的用户组，并且该用户组已被授予仅对销售设备的访问权限，则你将只看到有关 Microsoft 威胁防护中的销售设备的数据。</span><span class="sxs-lookup"><span data-stu-id="80aa2-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="80aa2-126">详细了解 Microsoft Defender ATP 中的 RBAC 设置</span><span class="sxs-lookup"><span data-stu-id="80aa2-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="80aa2-127">Microsoft Cloud App Security 访问控制</span><span class="sxs-lookup"><span data-stu-id="80aa2-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="80aa2-128">在预览过程中，Microsoft 威胁防护不会基于 Cloud App Security 设置强制实施访问控制。</span><span class="sxs-lookup"><span data-stu-id="80aa2-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="80aa2-129">这些设置不会影响对 Microsoft 威胁防护数据的访问。</span><span class="sxs-lookup"><span data-stu-id="80aa2-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="80aa2-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="80aa2-130">Related topics</span></span>

- [<span data-ttu-id="80aa2-131">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="80aa2-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="80aa2-132">Microsoft Defender ATP RBAC</span><span class="sxs-lookup"><span data-stu-id="80aa2-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="80aa2-133">Cloud App Security 角色</span><span class="sxs-lookup"><span data-stu-id="80aa2-133">Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)