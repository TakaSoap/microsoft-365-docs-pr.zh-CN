---
title: 步骤 14：允许用户创建和管理自己的组
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
description: 了解并配置 Azure AD 自助服务组管理。
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865728"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="48514-103">步骤 14：允许用户创建和管理自己的组</span><span class="sxs-lookup"><span data-stu-id="48514-103">Step 14: Allow users to create and manage their own groups</span></span>

<span data-ttu-id="48514-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="48514-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="48514-p101">在此步骤中，将标识可由组所有者而不是 IT 管理员来管理的 Azure Active Directory (AD) 组。此功能称为*自助服务组管理*，允许未分配管理角色的组所有者创建和管理安全组。</span><span class="sxs-lookup"><span data-stu-id="48514-p101">In Step 14, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="48514-p102">用户可以请求安全组中的成员身份，该请求将转到组所有者而不是 IT 管理员。这可将组成员身份的日常控制委托给团队、项目或业务所有者，他们了解组的商业用途，可更好地管理其成员身份。</span><span class="sxs-lookup"><span data-stu-id="48514-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="48514-p103">自助服务组管理仅适用于 Azure AD 安全和 Office 365 组。不适用于启用邮件的组、通讯组列表或已从本地 Windows Server Active Directory (AD) 同步的任何组。</span><span class="sxs-lookup"><span data-stu-id="48514-p103">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="48514-111">有关详细信息，请参阅[配置 Azure AD 组进行自助服务管理的说明](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。</span><span class="sxs-lookup"><span data-stu-id="48514-111">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="48514-112">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-self-service-groups)。</span><span class="sxs-lookup"><span data-stu-id="48514-112">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="48514-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="48514-113">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="48514-114">设置动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="48514-114">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |
