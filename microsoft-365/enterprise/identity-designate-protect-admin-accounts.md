---
title: 第 2 步：保护全局管理员帐户
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
description: 了解管理员帐户并为其配置最大保护。
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866036"
---
# <a name="step-2-protect-global-administrator-accounts"></a><span data-ttu-id="b3bc1-103">第 2 步：保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="b3bc1-103">Step 2: Protect global administrator accounts</span></span>

<span data-ttu-id="b3bc1-104">*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b3bc1-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="b3bc1-p101">在此步骤中，将通过确保管理员帐户尽可能的安全，以帮助防止对组织的数字攻击。为此，你必须：</span><span class="sxs-lookup"><span data-stu-id="b3bc1-p101">In Step 5, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span>

- <span data-ttu-id="b3bc1-107">使用特别[强密码](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)创建专用全局管理员帐户，并在必要时使用它们。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-107">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="b3bc1-108">根据需要通过向 IT 人员的用户帐户分配特定管理员角色（如 Exchange 管理员或密码管理员）来执行日常管理。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-108">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="b3bc1-109">对于专用全局管理员帐户，还必须：</span><span class="sxs-lookup"><span data-stu-id="b3bc1-109">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="b3bc1-p102">在测试用户帐户上测试每个用户帐户或基于条件访问的多重身份验证 (MFA) 设置，以确保 MFA 能够正确并以可预见的方式工作。MFA 需要辅助形式的身份验证，如发送到智能手机的验证码。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="b3bc1-p103">为每个专用的 Office 365 全局管理员帐户配置 MFA，并使用组织中可用的最强形式的辅助身份验证。有关详细信息，请参阅[多重身份验证](identity-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md) for more information.</span></span>
2. <span data-ttu-id="b3bc1-p104">使用条件访问策略要求对全局管理员帐户进行 MFA。有关详细信息，请参阅[保护管理员帐户](identity-access-prerequisites.md#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="b3bc1-p105">使用 Office 365 云应用安全策略来监控全局管理员帐户活动。有关详细信息，请参阅[配置增强的 Office 365 安全性](infoprotect-configure-increased-security-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Information protection for Microsoft 365 Enterprise](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="b3bc1-118">有关配置的详细信息，请参阅[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-118">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="b3bc1-p106">组织应使用仅限云标识来创建特权帐户（如全局管理员），以便应对网络攻击等的紧急情况。有关详细信息，请参阅[在 Azure AD 中管理紧急访问管理帐户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="b3bc1-121">此步骤结果是：</span><span class="sxs-lookup"><span data-stu-id="b3bc1-121">The results of this step are:</span></span>

- <span data-ttu-id="b3bc1-p107">订阅中具有全局管理员角色的唯一用户帐户是一组新的专用全局管理员帐户。使用以下 Windows Azure AD V2 PowerShell 命令对此进行验证：</span><span class="sxs-lookup"><span data-stu-id="b3bc1-p107">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="b3bc1-124">所有管理订阅的其他日常用户帐户分配有与其工作职责相关联的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-124">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="b3bc1-125">有关安装 Azure AD V2 PowerShell 模块和登录的说明，请参阅[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-125">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b3bc1-127">测试实验室指南：保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="b3bc1-127">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="b3bc1-128">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-global-admin)。</span><span class="sxs-lookup"><span data-stu-id="b3bc1-128">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b3bc1-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b3bc1-129">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="b3bc1-130">设置按需全局管理员</span><span class="sxs-lookup"><span data-stu-id="b3bc1-130">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |

