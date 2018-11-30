---
title: 第 15 步：设置动态组成员资格
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并根据帐户属性配置自动组成员身份。
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865915"
---
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="129ab-103">第 15 步：设置动态组成员资格</span><span class="sxs-lookup"><span data-stu-id="129ab-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="129ab-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="129ab-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="129ab-p101">在此步骤中，将创建一系列规则来为 Azure AD 组的成员自动添加或删除用户帐户。这就是*动态组成员身份*。这些规则将基于用户帐户属性，如部门或国家/地区。</span><span class="sxs-lookup"><span data-stu-id="129ab-p101">In Step 12, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as *dynamic group membership*. The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="129ab-108">下面是如何应用这些规则：</span><span class="sxs-lookup"><span data-stu-id="129ab-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="129ab-109">如果新用户帐户符合组的所有规则，则其会变为成员。</span><span class="sxs-lookup"><span data-stu-id="129ab-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="129ab-110">如果用户帐户不是组成员，但其属性更改，以便其匹配组的所有规则，则其会变为该组的成员。</span><span class="sxs-lookup"><span data-stu-id="129ab-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="129ab-111">如果用户帐户不匹配组的所有规则，则其不会添加到组。</span><span class="sxs-lookup"><span data-stu-id="129ab-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="129ab-112">如果用户帐户是组成员，但其属性更改，以便其不再匹配组的所有规则，则会从该组成员中将其删除。</span><span class="sxs-lookup"><span data-stu-id="129ab-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="129ab-p102">若要使用动态成员身份，则必须先确定有一组常用的用户帐户属性。例如，销售部门的所有成员都应在“销售 Azure AD”组中，根据用户帐户属性部门设置为“Sales”。</span><span class="sxs-lookup"><span data-stu-id="129ab-p102">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="129ab-115">请参阅[为动态 Azure AD 组创建并配置规则的说明](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="129ab-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="129ab-116">此步骤结果是：</span><span class="sxs-lookup"><span data-stu-id="129ab-116">The results of this step are:</span></span>

- <span data-ttu-id="129ab-117">可以为动态成员身份配置的 Azure AD 组集</span><span class="sxs-lookup"><span data-stu-id="129ab-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="129ab-118">每个动态组的规则集</span><span class="sxs-lookup"><span data-stu-id="129ab-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="129ab-120">测试实验室指南：自动化许可和组成员身份</span><span class="sxs-lookup"><span data-stu-id="129ab-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="129ab-121">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-dyn-groups)。</span><span class="sxs-lookup"><span data-stu-id="129ab-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="129ab-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="129ab-122">Next step</span></span>

[<span data-ttu-id="129ab-123">身份基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="129ab-123">Identity exit criteria</span></span>](identity-exit-criteria.md)
