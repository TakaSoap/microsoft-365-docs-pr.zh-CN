---
title: 步骤 7：配置标识治理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 租户的标识治理。
ms.openlocfilehash: d9a9a63f46230a07b35052a3b02231f7b5315d9e
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302919"
---
# <a name="step-6-configure-identity-governance"></a><span data-ttu-id="4525e-103">步骤 6：配置标识治理</span><span class="sxs-lookup"><span data-stu-id="4525e-103">Step 6: Configure identity governance</span></span>

![第 2 阶段 - 标识](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="4525e-105">标识治理的功能就是保护、监视和审核对关键资产的访问，同时确保员工高效工作。</span><span class="sxs-lookup"><span data-stu-id="4525e-105">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="4525e-106">例如，借助标识治理，可以确保相应的用户有权访问正确的资源，并确定该访问权限是否随时间而变化。</span><span class="sxs-lookup"><span data-stu-id="4525e-106">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="4525e-107">有关 Azure Active Directory (Azure AD) 标识治理的更多信息，请参阅[本文](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)。</span><span class="sxs-lookup"><span data-stu-id="4525e-107">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="4525e-108">*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="4525e-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="4525e-109">设置 Azure AD 访问评审</span><span class="sxs-lookup"><span data-stu-id="4525e-109">Set up Azure AD access reviews</span></span>

<span data-ttu-id="4525e-110">*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="4525e-110">*This is optional and only applies to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4525e-111">在此步骤中，将设置 Azure AD 访问评审，以便查看用户的访问权限，以确保只有合适的人员才能继续访问。</span><span class="sxs-lookup"><span data-stu-id="4525e-111">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="4525e-112">例如：</span><span class="sxs-lookup"><span data-stu-id="4525e-112">For example:</span></span>

- <span data-ttu-id="4525e-113">当新员工加入组织时，需要确保他们有正确的访问权限以实现高效工作。</span><span class="sxs-lookup"><span data-stu-id="4525e-113">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="4525e-114">当该员工换到其他团队、地点或部门时，需要确保根据需要删除对先前团队、位置或部门的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4525e-114">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="4525e-115">当该员工或来宾离开组织时，需要确保删除其访问权限。</span><span class="sxs-lookup"><span data-stu-id="4525e-115">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="4525e-116">如果组织需要接受安全审核以确定用户帐户是否拥有过多访问权限，这一点尤其重要，如果违反行业或地区法规，可能会导致罚款。</span><span class="sxs-lookup"><span data-stu-id="4525e-116">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="4525e-117">有关 Azure AD 访问评审的更多信息，请参阅[本文](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)。</span><span class="sxs-lookup"><span data-stu-id="4525e-117">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="4525e-118">Azure AD Privileged Identity Management (PIM) 提供用于保护 Azure AD、Azure 和其他 Microsoft 云服务中的资源访问权限的其他定制控制措施。</span><span class="sxs-lookup"><span data-stu-id="4525e-118">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="4525e-119">Azure AD PIM 提供了一套全面的治理控件，以帮助保护公司的资源（如目录、Office 365 和 Azure 资源角色）的安全。</span><span class="sxs-lookup"><span data-stu-id="4525e-119">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="4525e-120">与处理其他形式的访问权限一样，组织可以使用访问评审来针对充当管理员角色的所有用户配置定期的访问权限重新认证。</span><span class="sxs-lookup"><span data-stu-id="4525e-120">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="4525e-121">Azure AD PIM 仅适用于 Microsoft 365 企业版的 E5 版本。</span><span class="sxs-lookup"><span data-stu-id="4525e-121">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="4525e-122">请参阅以下文章，配置不同类型的访问评审：</span><span class="sxs-lookup"><span data-stu-id="4525e-122">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="4525e-123">组和应用</span><span class="sxs-lookup"><span data-stu-id="4525e-123">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="4525e-124">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="4525e-124">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="4525e-125">Azure 资源角色</span><span class="sxs-lookup"><span data-stu-id="4525e-125">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="4525e-126">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="4525e-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="4525e-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4525e-127">Next step</span></span>

[<span data-ttu-id="4525e-128">身份基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="4525e-128">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

