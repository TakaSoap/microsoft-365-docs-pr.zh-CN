---
title: 步骤 2：保护你的特权标识
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解管理员帐户并为其配置最大保护。
ms.openlocfilehash: 8a1d232ffc0242766d79b2e4884582f3b5524d22
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074052"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="bd1c4-103">步骤 2：保护你的特权标识</span><span class="sxs-lookup"><span data-stu-id="bd1c4-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="bd1c4-104">保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="bd1c4-104">Protect global administrator accounts</span></span>

<span data-ttu-id="bd1c4-105">*这是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="bd1c4-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="bd1c4-106">在此部分中，将通过确保管理员帐户尽可能的安全，以帮助防止对组织的数字攻击。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="bd1c4-107">为此，你必须：</span><span class="sxs-lookup"><span data-stu-id="bd1c4-107">To do this, you must:</span></span>

- <span data-ttu-id="bd1c4-108">使用特别[强密码](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)创建专用全局管理员帐户，并在必要时使用它们。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="bd1c4-109">根据需要通过向 IT 人员的用户帐户分配特定管理员角色（如 Exchange 管理员或密码管理员）来执行日常管理。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="bd1c4-110">对于专用全局管理员帐户，还必须：</span><span class="sxs-lookup"><span data-stu-id="bd1c4-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="bd1c4-p102">在测试用户帐户上测试每个用户帐户或基于条件访问的多重身份验证 (MFA) 设置，以确保 MFA 能够正确并以可预见的方式工作。MFA 需要辅助形式的身份验证，如发送到智能手机的验证码。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="bd1c4-p103">为每个专用的 Office 365 全局管理员帐户配置 MFA，并使用组织中可用的最强形式的辅助身份验证。有关详细信息，请参阅[多重身份验证](identity-multi-factor-authentication.md#identity-mfa)。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) for more information.</span></span>
2. <span data-ttu-id="bd1c4-p104">使用条件访问策略要求对全局管理员帐户进行 MFA。有关详细信息，请参阅[保护管理员帐户](identity-access-prerequisites.md#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="bd1c4-117">有关配置的详细信息，请参阅[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-117">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="bd1c4-p105">组织应使用仅限云标识来创建特权帐户（如全局管理员），以便应对网络攻击等的紧急情况。有关详细信息，请参阅[在 Azure AD 中管理紧急访问管理帐户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-p105">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="bd1c4-120">此部分的结果是：</span><span class="sxs-lookup"><span data-stu-id="bd1c4-120">The results of this section are:</span></span>

- <span data-ttu-id="bd1c4-121">订阅中唯一具备全局管理员角色的用户帐户是一组新的专用全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-121">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="bd1c4-122">使用 Azure Active Directory PowerShell Graph 命令验证这部分：</span><span class="sxs-lookup"><span data-stu-id="bd1c4-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="bd1c4-123">所有管理订阅的其他日常用户帐户分配有与其工作职责相关联的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-123">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="bd1c4-124">有关安装 Azure Active Directory PowerShell Graph 模块和登录的说明，请参阅[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="bd1c4-126">测试实验室指南：保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="bd1c4-126">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="bd1c4-127">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-global-admin)。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="bd1c4-128">设置按需全局管理员</span><span class="sxs-lookup"><span data-stu-id="bd1c4-128">Set up on-demand global administrators</span></span>

<span data-ttu-id="bd1c4-129">*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="bd1c4-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="bd1c4-130">在此部分中，将安装 Azure AD Privileged Identity Management (PIM)，以减少全局管理员帐户易受恶意用户攻击的时间。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="bd1c4-131">PIM 将在必要时按需、实时分配全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-131">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="bd1c4-p108">全局管理员帐户成为符合条件的管理员，而不再是永久管理员。有人需要全局管理员角色时，才会激活它。然后完成激活过程，以将全局管理员角色在特定时间内添加到全局管理员帐户。当时间到期后，PIM 会从全局管理员帐户删除全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-p108">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="bd1c4-p109">可从 Microsoft 365 Enterprise E5 包含的 Azure Active Directory Premium P2 中获取 PIM。或者可以为全局管理员帐户单独购买 Azure Active Directory Premium P2 许可证。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-p109">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="bd1c4-138">若要为 Azure AD 租户和全局管理员帐户启用 Azure PIM，请参阅 [PIM 配置步骤](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-138">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="bd1c4-139">可参阅[确保 Azure AD 中混合部署和云部署的特权访问安全性](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)来制定全面的路线图，以确保特权访问能够防止网络攻击者。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="bd1c4-140">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pim)。</span><span class="sxs-lookup"><span data-stu-id="bd1c4-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="bd1c4-141">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bd1c4-141">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="bd1c4-142">配置混合标识</span><span class="sxs-lookup"><span data-stu-id="bd1c4-142">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

