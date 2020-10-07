---
title: 管理 Microsoft 365 身份管理
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
description: 了解如何使用 Microsoft 365 身份管理功能。
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370342"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="d0de7-103">管理 Microsoft 365 身份管理</span><span class="sxs-lookup"><span data-stu-id="d0de7-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="d0de7-104">标识治理的功能就是保护、监视和审核对关键资产的访问，同时确保员工高效工作。</span><span class="sxs-lookup"><span data-stu-id="d0de7-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="d0de7-105">例如，借助标识治理，可以确保相应的用户有权访问正确的资源，并确定该访问权限是否随时间而变化。</span><span class="sxs-lookup"><span data-stu-id="d0de7-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="d0de7-106">有关详细信息，请参阅 [Azure Active Directory (AZURE AD) 的身份管理概述 ](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)。</span><span class="sxs-lookup"><span data-stu-id="d0de7-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="d0de7-107">设置 Azure AD 访问评审</span><span class="sxs-lookup"><span data-stu-id="d0de7-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="d0de7-108">Azure AD 访问审查允许您查看用户的访问权限，以确保只有合适的人继续访问。</span><span class="sxs-lookup"><span data-stu-id="d0de7-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="d0de7-109">例如：</span><span class="sxs-lookup"><span data-stu-id="d0de7-109">For example:</span></span>

- <span data-ttu-id="d0de7-110">当新员工加入组织时，需要确保他们有正确的访问权限以实现高效工作。</span><span class="sxs-lookup"><span data-stu-id="d0de7-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="d0de7-111">当该员工换到其他团队、地点或部门时，需要确保根据需要删除对先前团队、位置或部门的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d0de7-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="d0de7-112">当该员工或来宾离开组织时，需要确保删除其访问权限。</span><span class="sxs-lookup"><span data-stu-id="d0de7-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="d0de7-113">如果组织需要接受安全审核以确定用户帐户是否拥有过多访问权限，这一点尤其重要，如果违反行业或地区法规，可能会导致罚款。</span><span class="sxs-lookup"><span data-stu-id="d0de7-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="d0de7-114">有关详细信息，请参阅 [访问审核概述](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)。</span><span class="sxs-lookup"><span data-stu-id="d0de7-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="d0de7-115">请参阅以下文章，配置不同类型的访问评审：</span><span class="sxs-lookup"><span data-stu-id="d0de7-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="d0de7-116">组和应用</span><span class="sxs-lookup"><span data-stu-id="d0de7-116">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="d0de7-117">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="d0de7-117">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="d0de7-118">Azure 资源角色</span><span class="sxs-lookup"><span data-stu-id="d0de7-118">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="d0de7-119">设置 Azure AD 权限管理</span><span class="sxs-lookup"><span data-stu-id="d0de7-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="d0de7-120">Wiht Azure AD 权限管理，可以通过自动执行访问请求工作流、访问分配、查看和到期情况来管理标识和访问生命周期的规模。</span><span class="sxs-lookup"><span data-stu-id="d0de7-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="d0de7-121">你的员工需要访问各种组、应用程序和网站，以执行其作业。</span><span class="sxs-lookup"><span data-stu-id="d0de7-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="d0de7-122">管理此访问可能会非常困难，因为要求更改、添加新应用程序或用户需要其他访问权限。</span><span class="sxs-lookup"><span data-stu-id="d0de7-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="d0de7-123">当与其他组织进行协作时，您可能不知道其他组织中的哪些人需要访问您组织的资源，而外部用户将不知道您的组织使用的应用程序、组或站点。</span><span class="sxs-lookup"><span data-stu-id="d0de7-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="d0de7-124">Azure AD 权限管理可帮助您更有效地管理内部和外部用户对组、应用程序和 SharePoint 网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d0de7-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="d0de7-125">有关详细信息，请参阅 [AZURE AD 权限管理的概述](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)。</span><span class="sxs-lookup"><span data-stu-id="d0de7-125">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
