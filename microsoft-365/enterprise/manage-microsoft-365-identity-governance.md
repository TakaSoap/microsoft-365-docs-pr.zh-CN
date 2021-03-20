---
title: 管理 Microsoft 365 标识治理
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
description: 了解如何使用 Microsoft 365 标识治理功能。
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910950"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="bf0bd-103">管理 Microsoft 365 标识治理</span><span class="sxs-lookup"><span data-stu-id="bf0bd-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="bf0bd-104">标识治理的功能就是保护、监视和审核对关键资产的访问，同时确保员工高效工作。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="bf0bd-105">例如，借助标识治理，可以确保相应的用户有权访问正确的资源，并确定该访问权限是否随时间而变化。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="bf0bd-106">有关详细信息，请参阅 Azure [Active Directory ](/azure/active-directory/governance/identity-governance-overview) (Azure AD) 的此概述。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="bf0bd-107">设置 Azure AD 访问评审</span><span class="sxs-lookup"><span data-stu-id="bf0bd-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="bf0bd-108">Azure AD 访问评审允许你查看用户的访问权限，以确保只有合适的人员才能继续访问。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="bf0bd-109">例如：</span><span class="sxs-lookup"><span data-stu-id="bf0bd-109">For example:</span></span>

- <span data-ttu-id="bf0bd-110">当新员工加入组织时，需要确保他们有正确的访问权限以实现高效工作。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="bf0bd-111">当该员工换到其他团队、地点或部门时，需要确保根据需要删除对先前团队、位置或部门的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="bf0bd-112">当该员工或来宾离开组织时，需要确保删除其访问权限。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="bf0bd-113">如果组织需要接受安全审核以确定用户帐户是否拥有过多访问权限，这一点尤其重要，如果违反行业或地区法规，可能会导致罚款。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="bf0bd-114">有关详细信息，请参阅 [访问评审概述](/azure/active-directory/governance/access-reviews-overview)。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-114">For more information, see the [overview of access reviews](/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="bf0bd-115">请参阅以下文章，配置不同类型的访问评审：</span><span class="sxs-lookup"><span data-stu-id="bf0bd-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="bf0bd-116">组和应用</span><span class="sxs-lookup"><span data-stu-id="bf0bd-116">Groups and apps</span></span>](/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="bf0bd-117">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="bf0bd-117">Azure AD roles</span></span>](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="bf0bd-118">Azure 资源角色</span><span class="sxs-lookup"><span data-stu-id="bf0bd-118">Azure resource roles</span></span>](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="bf0bd-119">设置 Azure AD 权利管理</span><span class="sxs-lookup"><span data-stu-id="bf0bd-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="bf0bd-120">Wiht Azure AD 权利管理，可以通过自动执行访问请求工作流、访问分配、审阅和过期来大规模管理标识和访问生命周期。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="bf0bd-121">员工需要访问各种组、应用程序和网站才能执行他们的工作。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="bf0bd-122">管理此访问可能充满挑战，因为要求发生变化、添加了新应用程序，或者用户需要其他访问权限。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="bf0bd-123">与其他组织协作时，您可能不知道其他组织中的哪些人员需要访问组织的资源，外部用户将不知道组织正在使用哪些应用程序、组或网站。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="bf0bd-124">Azure AD 权利管理可帮助你更高效地管理内部和外部用户对组、应用程序和 SharePoint 网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="bf0bd-125">有关详细信息，请参阅 Azure [AD 权利管理概述](/azure/active-directory/governance/entitlement-management-overview)。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-125">For more information, see the [overview of Azure AD entitlement management](/azure/active-directory/governance/entitlement-management-overview).</span></span>