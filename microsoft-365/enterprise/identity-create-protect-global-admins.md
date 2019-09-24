---
title: 步骤1：创建和保护全局管理员帐户
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
description: 全局管理员帐户需要特殊对待，以确保其免受凭据泄露的影响。
ms.openlocfilehash: a32781686cd972ca96f6bb08f31c15ede016c4cd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37075408"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="8a292-103">步骤1：创建和保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="8a292-103">Step 1: Create and protect your global admin accounts</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="8a292-104">保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="8a292-104">Protect global administrator accounts</span></span>

<span data-ttu-id="8a292-105">*这是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="8a292-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="8a292-106">在此部分中，将通过确保管理员帐户尽可能的安全，以帮助防止对组织的数字攻击。</span><span class="sxs-lookup"><span data-stu-id="8a292-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="8a292-107">为此，你必须：</span><span class="sxs-lookup"><span data-stu-id="8a292-107">To do this, you must:</span></span>

- <span data-ttu-id="8a292-108">使用[强密码](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)创建多个专用全局管理员帐户，并在必要时使用它们。</span><span class="sxs-lookup"><span data-stu-id="8a292-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="8a292-109">根据需要，通过向这些角色的其他专用帐户或 IT 人员的用户帐户分配特定管理员角色（如 Exchange 管理员或密码管理员）来执行日常管理。</span><span class="sxs-lookup"><span data-stu-id="8a292-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="8a292-110">对于专用全局管理员帐户，还必须：</span><span class="sxs-lookup"><span data-stu-id="8a292-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="8a292-111">在测试用户帐户上测试每个用户帐户或基于条件访问的 Azure 多因素身份验证 (MFA) 设置，以确保 MFA 能够正确并以可预见的方式工作。</span><span class="sxs-lookup"><span data-stu-id="8a292-111">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="8a292-112">MFA 需要辅助形式的身份验证，如发送到智能手机的验证码。</span><span class="sxs-lookup"><span data-stu-id="8a292-112">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="8a292-113">为需要进行 MFA 的全局管理员帐户创建和启用条件访问策略，并使用组织提供的最强大的辅助身份验证形式。</span><span class="sxs-lookup"><span data-stu-id="8a292-113">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="8a292-114">有关详细信息，请参阅 [Azure 多因素身份验证](identity-access-prerequisites.md#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="8a292-114">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="8a292-115">有关额外的保护，请参阅[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations)。</span><span class="sxs-lookup"><span data-stu-id="8a292-115">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="8a292-116">在网络攻击等紧急情况下，不受限方案的紧急帐户应为仅限云帐户。</span><span class="sxs-lookup"><span data-stu-id="8a292-116">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="8a292-117">你也可以拥有不是仅限云的全局管理员帐户（符合条件的或永久的）。</span><span class="sxs-lookup"><span data-stu-id="8a292-117">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="8a292-118">有关详细信息，请参阅[在 Azure AD 中管理紧急访问管理帐户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="8a292-118">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="8a292-119">此部分的结果是：</span><span class="sxs-lookup"><span data-stu-id="8a292-119">The results of this section are:</span></span>

- <span data-ttu-id="8a292-120">订阅中唯一具备全局管理员角色的用户帐户是专用全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="8a292-120">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="8a292-121">使用以下 Azure Active Directory PowerShell Graph 命令验证这部分：</span><span class="sxs-lookup"><span data-stu-id="8a292-121">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="8a292-122">所有管理订阅服务的其他用户帐户分配有与其工作职责相关联的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="8a292-122">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="8a292-123">有关安装 Azure Active Directory PowerShell Graph 模块和登录的说明，请参阅[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8a292-123">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="8a292-125">若要在测试实验室环境中练习此配置，请参阅[保护全局管理员帐户测试实验室指南](protect-global-administrator-accounts-microsoft-365-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="8a292-125">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="8a292-126">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-global-admin)。</span><span class="sxs-lookup"><span data-stu-id="8a292-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="8a292-127">设置按需管理员</span><span class="sxs-lookup"><span data-stu-id="8a292-127">Set up on-demand global administrators</span></span>

<span data-ttu-id="8a292-128">*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="8a292-128">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="8a292-129">在此部分中，将安装 Azure AD Privileged Identity Management (PIM)，以减少管理员帐户易受恶意用户攻击的时间。</span><span class="sxs-lookup"><span data-stu-id="8a292-129">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="8a292-130">PIM 将在必要时按需、实时分配管理员角色。</span><span class="sxs-lookup"><span data-stu-id="8a292-130">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="8a292-131">管理员帐户将成为符合条件的管理员，而不再是永久管理员。</span><span class="sxs-lookup"><span data-stu-id="8a292-131">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="8a292-132">有人需要管理员角色时，才会激活它。</span><span class="sxs-lookup"><span data-stu-id="8a292-132">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="8a292-133">然后完成激活过程，以将管理员角色在特定时间内添加到管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="8a292-133">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="8a292-134">当时间到期后，PIM 会从管理员帐户中删除管理员角色。</span><span class="sxs-lookup"><span data-stu-id="8a292-134">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="8a292-135">可从 Microsoft 365 企业版 E5 包含的 Azure Active Directory Premium P2 中获取 PIM。</span><span class="sxs-lookup"><span data-stu-id="8a292-135">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span> <span data-ttu-id="8a292-136">或者，可以为管理员帐户单独购买 Azure Active Directory Premium P2 许可证。</span><span class="sxs-lookup"><span data-stu-id="8a292-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="8a292-137">若要为 Azure AD 租户和管理员帐户启用 Azure PIM，请参阅 [PIM 配置步骤](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。</span><span class="sxs-lookup"><span data-stu-id="8a292-137">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="8a292-138">可参阅[确保 Azure AD 中混合部署和云部署的特权访问安全性](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)来制定全面的路线图，以确保特权访问能够防止网络攻击者。</span><span class="sxs-lookup"><span data-stu-id="8a292-138">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="8a292-139">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pim)。</span><span class="sxs-lookup"><span data-stu-id="8a292-139">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="8a292-140">特权访问管理</span><span class="sxs-lookup"><span data-stu-id="8a292-140">Privileged access management</span></span>

<span data-ttu-id="8a292-p109">Office 365 租户中的特权访问管理可通过配置相应策略来实现，这些策略会为基于任务的活动指定实时访问权限。这种管理可为组织提供保护，防止他人使用具有长期敏感数据访问权限或关键配置设置访问权限的现有特权访问帐户。例如，你可以配置一个特权访问管理策略，要求必须经过显示审批才能访问和更改 Office 365 租户中的组织邮箱设置。</span><span class="sxs-lookup"><span data-stu-id="8a292-p109">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="8a292-p110">在此步骤中，你将在 Office 365 租户中启用特权访问管理并配置特权访问策略，这些策略可为基于任务对组织的 Office 365 数据和配置设置进行的访问提供额外的安全性。若要开始在 Office 365 组织中使用特权访问，需要执行三个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="8a292-p110">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="8a292-146">创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="8a292-146">Creating an approver's group</span></span>
- <span data-ttu-id="8a292-147">启用特权访问</span><span class="sxs-lookup"><span data-stu-id="8a292-147">Enabling privileged access</span></span>
- <span data-ttu-id="8a292-148">创建审批策略</span><span class="sxs-lookup"><span data-stu-id="8a292-148">Creating approval policies</span></span>

<span data-ttu-id="8a292-p111">配置完成后，特权访问管理可帮助组织实现零长期特权并针对这类长期管理访问权限造成的漏洞提供一个防御层。特权访问要求必须经过审批才能执行定义了相关审批策略的任务。用户如果需要执行某个审批策略中包含的任务，则必须提出请求并成功通过访问权限审批，以便获得执行该策略中定义的任务所需的权限。</span><span class="sxs-lookup"><span data-stu-id="8a292-p111">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="8a292-152">若要启用 Office 365 特权访问管理，请参阅[配置 Office 365 中的特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题。</span><span class="sxs-lookup"><span data-stu-id="8a292-152">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="8a292-153">有关详细信息，请参阅 [Office 365 中的特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)主题。</span><span class="sxs-lookup"><span data-stu-id="8a292-153">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="8a292-155">若要在测试实验室环境中练习此配置，请参阅[特权访问管理测试实验室指南](privileged-access-microsoft-365-enterprise-dev-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="8a292-155">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="8a292-156">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-pam)。</span><span class="sxs-lookup"><span data-stu-id="8a292-156">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8a292-157">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8a292-157">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="8a292-158">保护密码安全</span><span class="sxs-lookup"><span data-stu-id="8a292-158">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

