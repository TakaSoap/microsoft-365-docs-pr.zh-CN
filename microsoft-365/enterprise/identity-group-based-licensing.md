---
title: 第 12 步：设置自动授权
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
description: 理解并配置 Azure AD 组基于组的许可。
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865381"
---
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="38014-103">第 12 步：设置自动授权</span><span class="sxs-lookup"><span data-stu-id="38014-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="38014-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="38014-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="38014-p101">在此步骤中，将在 Azure AD 中配置安全组，以将许可证从一组订阅自动分配到组的所有成员。这被称为*基于组的许可*。如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或从该用户帐户中删除。</span><span class="sxs-lookup"><span data-stu-id="38014-p101">In Step 11, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as *group-based licensing*. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="38014-108">对于 Microsoft 365 企业版，将配置 Azure AD 安全组，以分配这两种许可证：</span><span class="sxs-lookup"><span data-stu-id="38014-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="38014-109">Office 365 企业版 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="38014-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="38014-110">企业移动性 + 安全性 (EMS) E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="38014-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="38014-p102">使用在步骤 2 中标识的组，查找包含该组中所有用户必须同时具有 Office 365 和 EMS 许可证的帐户列表的组。请确保对所有组成员具有足够的许可证。一旦许可证用完，将无法向新用户分配许可证，直到有可用的许可证为止。</span><span class="sxs-lookup"><span data-stu-id="38014-p102">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="38014-114">不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”\*\*。</span><span class="sxs-lookup"><span data-stu-id="38014-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="38014-115">有关更多信息，请参阅 [Azure Active Directory 中基于组的许可基础知识](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="38014-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="38014-116">请参阅[为 Azure 安全组配置基于组的许可的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="38014-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="38014-117">此步骤结果是：</span><span class="sxs-lookup"><span data-stu-id="38014-117">The results of this step are:</span></span>

- <span data-ttu-id="38014-118">已标识哪些安全组适用于基于组的许可。</span><span class="sxs-lookup"><span data-stu-id="38014-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="38014-119">已为基于组的许可配置了这些组。</span><span class="sxs-lookup"><span data-stu-id="38014-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="38014-121">测试实验室指南：自动化许可和组成员身份</span><span class="sxs-lookup"><span data-stu-id="38014-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="38014-122">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-group-license)。</span><span class="sxs-lookup"><span data-stu-id="38014-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="38014-123">后续步骤</span><span class="sxs-lookup"><span data-stu-id="38014-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="38014-124">监控租户和登录活动</span><span class="sxs-lookup"><span data-stu-id="38014-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

