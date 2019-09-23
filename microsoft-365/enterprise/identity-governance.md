---
title: 步骤 7：配置标识治理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 租户的标识治理。
ms.openlocfilehash: 1c0eab574e5436dd0c88a0b46d1916281bcf0577
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047355"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="0516d-103">步骤 7：配置标识治理</span><span class="sxs-lookup"><span data-stu-id="0516d-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="0516d-104">标识治理的功能就是保护、监视和审核对关键资产的访问，同时确保员工高效工作。</span><span class="sxs-lookup"><span data-stu-id="0516d-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="0516d-105">例如，借助标识治理，可以确保相应的用户有权访问正确的资源，并确定该访问权限是否随时间而变化。</span><span class="sxs-lookup"><span data-stu-id="0516d-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="0516d-106">有关 Azure Active Directory (Azure AD) 标识治理的更多信息，请参阅](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)本文[。</span><span class="sxs-lookup"><span data-stu-id="0516d-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="0516d-107">设置 Azure AD 访问评审</span><span class="sxs-lookup"><span data-stu-id="0516d-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="0516d-108">*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="0516d-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0516d-109">在此步骤中，将设置 Azure AD 访问评审，以便查看用户的访问权限，以确保只有合适的人员才能继续访问。</span><span class="sxs-lookup"><span data-stu-id="0516d-109">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="0516d-110">例如：</span><span class="sxs-lookup"><span data-stu-id="0516d-110">For example:</span></span>

- <span data-ttu-id="0516d-111">当新员工加入组织时，需要确保他们有正确的访问权限以实现高效工作。</span><span class="sxs-lookup"><span data-stu-id="0516d-111">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="0516d-112">当该员工换到其他团队、地点或部门时，需要确保根据需要删除对先前团队、位置或部门的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0516d-112">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="0516d-113">当该员工或来宾离开组织时，需要确保删除其访问权限。</span><span class="sxs-lookup"><span data-stu-id="0516d-113">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="0516d-114">如果组织需要接受安全审核以确定用户帐户是否拥有过多访问权限，这一点尤其重要，如果违反行业或地区法规，可能会导致罚款。</span><span class="sxs-lookup"><span data-stu-id="0516d-114">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="0516d-115">有关 Azure AD 访问评审的更多信息，请参阅[本文](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)。</span><span class="sxs-lookup"><span data-stu-id="0516d-115">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="0516d-116">请参阅以下文章，配置不同类型的访问评审：</span><span class="sxs-lookup"><span data-stu-id="0516d-116">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="0516d-117">组和应用</span><span class="sxs-lookup"><span data-stu-id="0516d-117">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="0516d-118">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="0516d-118">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="0516d-119">Azure 资源角色</span><span class="sxs-lookup"><span data-stu-id="0516d-119">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="0516d-120">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="0516d-120">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="0516d-121">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0516d-121">Next step</span></span>

[<span data-ttu-id="0516d-122">身份基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="0516d-122">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

