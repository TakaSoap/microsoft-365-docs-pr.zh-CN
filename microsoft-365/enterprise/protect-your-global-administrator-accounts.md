---
title: 保护你的Microsoft 365全局管理员帐户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: 本文提供有关保护全局管理员对订阅Microsoft 365的信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c929651f3e70a1aeef16cdf48d853d675820833
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926543"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="e5408-103">保护你的Microsoft 365全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="e5408-103">Protect your Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="e5408-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="e5408-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e5408-105">Microsoft 365订阅的安全泄露（包括信息获取和网络钓鱼攻击）通常是通过损害 Microsoft 365 管理员帐户的凭据而泄露的。</span><span class="sxs-lookup"><span data-stu-id="e5408-105">Security breaches of a Microsoft 365 subscription, including information harvesting and phishing attacks, are typically done by compromising the credentials of a Microsoft 365 global administrator account.</span></span> <span data-ttu-id="e5408-106">云中的安全是你与 Microsoft 之间的合作关系：</span><span class="sxs-lookup"><span data-stu-id="e5408-106">Security in the cloud is a partnership between you and Microsoft:</span></span>
  
- <span data-ttu-id="e5408-107">Microsoft 云服务基于信任和安全性而构建。</span><span class="sxs-lookup"><span data-stu-id="e5408-107">Microsoft cloud services are built on a foundation of trust and security.</span></span> <span data-ttu-id="e5408-108">Microsoft 提供了安全控件和功能，可帮助你保护数据和应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5408-108">Microsoft provides you security controls and capabilities to help you protect your data and applications.</span></span>
    
- <span data-ttu-id="e5408-109">你拥有你的数据和标识以及保护它们的责任、本地资源的安全性以及你控制的云组件的安全性。</span><span class="sxs-lookup"><span data-stu-id="e5408-109">You own your data and identities and the responsibility for protecting them, the security of your on-premises resources, and the security of cloud components you control.</span></span>
    
<span data-ttu-id="e5408-110">Microsoft 提供了可帮助保护组织的功能，但这些功能仅在你使用它们时有效。</span><span class="sxs-lookup"><span data-stu-id="e5408-110">Microsoft provides capabilities to help protect your organization, but they are effective only if you use them.</span></span> <span data-ttu-id="e5408-111">如果不使用它们，你很容易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="e5408-111">If you do not use them, you may be vulnerable to attack.</span></span> <span data-ttu-id="e5408-112">为了保护全局管理员帐户，Microsoft 可在此处帮助你提供详细说明，以：</span><span class="sxs-lookup"><span data-stu-id="e5408-112">To protect your global administrator accounts, Microsoft is here to help you with detailed instructions to:</span></span>
  
1. <span data-ttu-id="e5408-113">创建专用Microsoft 365全局管理员帐户，并仅在必要时使用它们。</span><span class="sxs-lookup"><span data-stu-id="e5408-113">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary.</span></span>
    
2. <span data-ttu-id="e5408-114">为专用全局管理员帐户Microsoft 365多重身份验证，并使用最强形式的辅助身份验证。</span><span class="sxs-lookup"><span data-stu-id="e5408-114">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts and use the strongest form of secondary authentication.</span></span>
    
> [!Note]
> <span data-ttu-id="e5408-115">尽管本文侧重于全局管理员帐户，但您应考虑是否应该以相同方式保护具有访问订阅中数据的广泛权限的其他帐户，例如电子数据展示管理员帐户或安全或合规性管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="e5408-115">Although this article is focused on global administrator accounts, you should consider whether additional accounts with wide-ranging permissions to access the data in your subscription, such as eDiscovery administrator or security or compliance administrator accounts, should be protected in the same way.</span></span> <br > <span data-ttu-id="e5408-116">可以在不添加任何许可证的情况下创建全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="e5408-116">A global administrator account can be created without adding any licenses.</span></span>
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a><span data-ttu-id="e5408-117">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="e5408-117">Step 1.</span></span> <span data-ttu-id="e5408-118">创建专用Microsoft 365全局管理员帐户，并在必要时使用它们</span><span class="sxs-lookup"><span data-stu-id="e5408-118">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary</span></span>

<span data-ttu-id="e5408-119">只有相对较少的管理任务（如向用户帐户分配角色）需要全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="e5408-119">There are relatively few administrative tasks, such as assigning roles to user accounts, that require global administrator privileges.</span></span> <span data-ttu-id="e5408-120">因此，不要使用已分配有全局管理员角色的日常用户帐户，而是执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e5408-120">Therefore, instead of using everyday user accounts that have been assigned the global admin role, do these steps:</span></span>
  
1. <span data-ttu-id="e5408-121">确定已分配全局管理员角色的用户帐户集。</span><span class="sxs-lookup"><span data-stu-id="e5408-121">Determine the set of user accounts that have been assigned the global admin role.</span></span> <span data-ttu-id="e5408-122">可以在管理中心或以下 Azure (Active Microsoft 365 Azure AD) Directory PowerShell for Graph 命令进行此操作：</span><span class="sxs-lookup"><span data-stu-id="e5408-122">You can do this in the Microsoft 365 admin center or with the following Azure Active (Azure AD) Directory PowerShell for Graph command:</span></span>
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. <span data-ttu-id="e5408-123">使用已Microsoft 365全局管理员角色的用户帐户登录你的订阅。</span><span class="sxs-lookup"><span data-stu-id="e5408-123">Sign into your Microsoft 365 subscription with a user account that has been assigned the global admin role.</span></span>
    
3. <span data-ttu-id="e5408-124">最多创建四个专用全局管理员用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e5408-124">Create up to a maximum of four dedicated global administrator user accounts.</span></span> <span data-ttu-id="e5408-125">**使用长于 12 个字符的强密码。**</span><span class="sxs-lookup"><span data-stu-id="e5408-125">**Use strong passwords at least 12 characters long.**</span></span> <span data-ttu-id="e5408-126">有关详细信息 [，请参阅创建](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 强密码。</span><span class="sxs-lookup"><span data-stu-id="e5408-126">See [Create a strong password](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) for more information.</span></span> <span data-ttu-id="e5408-127">将新帐户的密码存储在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="e5408-127">Store the passwords for the new accounts in a secure location.</span></span> 
    
4. <span data-ttu-id="e5408-128">将全局管理员角色分配给每个新的专用全局管理员用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e5408-128">Assign the global admin role to each of the new dedicated global administrator user accounts.</span></span>
    
5. <span data-ttu-id="e5408-129">注销Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e5408-129">Sign out of Microsoft 365.</span></span>
    
6. <span data-ttu-id="e5408-130">使用新的专用全局管理员用户帐户之一登录。</span><span class="sxs-lookup"><span data-stu-id="e5408-130">Sign in with one of the new dedicated global administrator user accounts.</span></span>
    
7. <span data-ttu-id="e5408-131">对于在步骤 1 中分配了全局管理员角色的每个现有用户帐户：</span><span class="sxs-lookup"><span data-stu-id="e5408-131">For each existing user account that had been assigned the global admin role from step 1:</span></span>
    
  - <span data-ttu-id="e5408-132">删除全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="e5408-132">Remove the global admin role.</span></span>
    
  - <span data-ttu-id="e5408-133">将管理员角色分配给适合该用户的工作职能和责任的帐户。</span><span class="sxs-lookup"><span data-stu-id="e5408-133">Assign admin roles to the account that are appropriate to that user's job function and responsibility.</span></span> <span data-ttu-id="e5408-134">有关管理员角色中各种管理员角色Microsoft 365，请参阅关于[管理员角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="e5408-134">For more information about various admin roles in Microsoft 365, see [About admin roles](/office365/admin/add-users/about-admin-roles).</span></span>
    
8. <span data-ttu-id="e5408-135">注销Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e5408-135">Sign out of Microsoft 365.</span></span>
    
<span data-ttu-id="e5408-136">结果应为：</span><span class="sxs-lookup"><span data-stu-id="e5408-136">The results should be:</span></span>
  
- <span data-ttu-id="e5408-137">订阅中唯一具备全局管理员角色的用户帐户是一组新的专用全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="e5408-137">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="e5408-138">通过以下 PowerShell 命令验证这一点：</span><span class="sxs-lookup"><span data-stu-id="e5408-138">Verify this with the following PowerShell command:</span></span>
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- <span data-ttu-id="e5408-139">所有管理订阅的其他日常用户帐户分配有与其工作职责相关联的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="e5408-139">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>
    
<span data-ttu-id="e5408-140">从现在起，您仅对需要全局管理员权限的任务使用专用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e5408-140">From this moment onward, you sign in with the dedicated global administrator accounts only for tasks that require global administrator privileges.</span></span> <span data-ttu-id="e5408-141">所有其他Microsoft 365管理必须通过向用户帐户分配其他管理角色完成。</span><span class="sxs-lookup"><span data-stu-id="e5408-141">All other Microsoft 365 administration must be done by assigning other administration roles to user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5408-142">这确实需要其他步骤才能作为日常用户帐户进行注销，然后使用专用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e5408-142">This does require additional steps to sign out as your everyday user account and sign in with a dedicated global administrator account.</span></span> <span data-ttu-id="e5408-143">但是，只需偶尔对全局管理员操作执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e5408-143">But this only needs to be done occasionally for global administrator operations.</span></span> <span data-ttu-id="e5408-144">请注意，在全局管理员帐户Microsoft 365后恢复你的订阅需要执行很多步骤。</span><span class="sxs-lookup"><span data-stu-id="e5408-144">Consider that recovering your Microsoft 365 subscription after a global administrator account breach requires a lot more steps.</span></span>
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="e5408-145">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="e5408-145">Step 2.</span></span> <span data-ttu-id="e5408-146">为专用全局管理员帐户Microsoft 365多重身份验证</span><span class="sxs-lookup"><span data-stu-id="e5408-146">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="e5408-147">MFA (多重) 需要帐户名称和密码之外的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e5408-147">Multi-factor authentication (MFA) requires additional information beyond the account name and password.</span></span> <span data-ttu-id="e5408-148">Microsoft 365支持以下其他验证方法：</span><span class="sxs-lookup"><span data-stu-id="e5408-148">Microsoft 365 supports these additional verification methods:</span></span>
  
- <span data-ttu-id="e5408-149">Microsoft Authenticator 应用</span><span class="sxs-lookup"><span data-stu-id="e5408-149">The Microsoft Authenticator app</span></span>

- <span data-ttu-id="e5408-150">电话联络</span><span class="sxs-lookup"><span data-stu-id="e5408-150">A phone call</span></span>
    
- <span data-ttu-id="e5408-151">通过短信发送的随机生成的验证码</span><span class="sxs-lookup"><span data-stu-id="e5408-151">A randomly generated verification code sent through a text message</span></span>
    
- <span data-ttu-id="e5408-152">智能卡（虚拟或物理）</span><span class="sxs-lookup"><span data-stu-id="e5408-152">A smart card (virtual or physical)</span></span>
    
- <span data-ttu-id="e5408-153">生物识别设备</span><span class="sxs-lookup"><span data-stu-id="e5408-153">A biometric device</span></span>
    
>[!Note]
><span data-ttu-id="e5408-154">对于必须遵守美国国家标准和技术协会 (NIST) 标准的组织，限制使用电话呼叫或基于短信的其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="e5408-154">For organizations that must adhere to National Institute of Standards and Technology (NIST) standards, the use of a phone call or text message-based additional verification methods are restricted.</span></span> <span data-ttu-id="e5408-155">单击此处 [了解](https://pages.nist.gov/800-63-FAQ/#q-b01) 详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5408-155">Click [here](https://pages.nist.gov/800-63-FAQ/#q-b01) for the details.</span></span>
>

<span data-ttu-id="e5408-156">如果你是使用仅存储在云 (仅云标识模型) 中的用户帐户的小型企业，请设置 MFA，以使用每个专用全局管理员帐户发送到智能手机的电话呼叫或短信验证码来配置[MFA。](/office365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="e5408-156">If you are a small business that is using user accounts stored only in the cloud (the cloud-only identity model), [set up MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) to configure MFA using a phone call or a text message verification code sent to a smart phone for each dedicated global administrator account.</span></span>
    
<span data-ttu-id="e5408-157">如果你是使用混合标识模型Microsoft 365大型组织，则具有更多验证选项。</span><span class="sxs-lookup"><span data-stu-id="e5408-157">If you are a larger organization that is using a Microsoft 365 hybrid identity model, you have more verification options.</span></span> <span data-ttu-id="e5408-158">如果已设置安全基础结构，以使用更强大的辅助身份验证方法，请设置 [MFA，](../admin/security-and-compliance/set-up-multi-factor-authentication.md) 并为每个专用全局管理员帐户配置适当的验证方法。</span><span class="sxs-lookup"><span data-stu-id="e5408-158">If you have the security infrastructure already in place for a stronger secondary authentication method, [set up MFA](../admin/security-and-compliance/set-up-multi-factor-authentication.md) and configure each dedicated global administrator account for the appropriate verification method.</span></span>
  
<span data-ttu-id="e5408-159">如果所需的更强的验证方法的安全基础结构未就位且无法用于 Microsoft 365 MFA，我们强烈建议你使用 Microsoft Authenticator 应用、电话呼叫或发送到全局管理员帐户的智能手机的短信验证代码来配置具有 MFA 的专用全局管理员帐户，作为临时安全措施。</span><span class="sxs-lookup"><span data-stu-id="e5408-159">If the security infrastructure for the desired stronger verification method is not in place and functioning for Microsoft 365 MFA, we strongly recommend that you configure dedicated global administrator accounts with MFA using the Microsoft Authenticator app, a phone call, or a text message verification code sent to a smart phone for your global administrator accounts as an interim security measure.</span></span> <span data-ttu-id="e5408-160">请不要离开专用全局管理员帐户，而不使用 MFA 提供的其他保护。</span><span class="sxs-lookup"><span data-stu-id="e5408-160">Do not leave your dedicated global administrator accounts without the additional protection provided by MFA.</span></span>
  
<span data-ttu-id="e5408-161">有关详细信息，请参阅[MFA for Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="e5408-161">For more information, see [MFA for Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md).</span></span>
  
<span data-ttu-id="e5408-162">若要通过 MFA Microsoft 365 PowerShell 连接到服务，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e5408-162">To connect to Microsoft 365 services with MFA and PowerShell, see these articles:</span></span>

- [<span data-ttu-id="e5408-163">适用于用户帐户Microsoft 365组和许可证的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5408-163">PowerShell for Microsoft 365 for user accounts, groups, and licenses</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="e5408-164">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e5408-164">Microsoft Teams</span></span>](/microsoftteams/teams-powershell-install)
- [<span data-ttu-id="e5408-165">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e5408-165">Exchange Online</span></span>](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [<span data-ttu-id="e5408-166">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5408-166">SharePoint Online</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [<span data-ttu-id="e5408-167">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e5408-167">Skype for Business Online</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a><span data-ttu-id="e5408-168">企业组织的其他保护</span><span class="sxs-lookup"><span data-stu-id="e5408-168">Additional protections for enterprise organizations</span></span>

<span data-ttu-id="e5408-169">使用这些附加方法可确保全局管理员帐户以及使用该帐户执行的配置尽可能安全。</span><span class="sxs-lookup"><span data-stu-id="e5408-169">Use these additional methods to ensure that your global administrator account, and the configuration that you perform using it, are as secure as possible.</span></span>
  
### <a name="privileged-access-workstation"></a><span data-ttu-id="e5408-170">特权访问工作站</span><span class="sxs-lookup"><span data-stu-id="e5408-170">Privileged access workstation</span></span>

<span data-ttu-id="e5408-171">为确保执行高特权任务尽可能安全，请使用 PRIVILEGED 访问工作站 (PAW) 。</span><span class="sxs-lookup"><span data-stu-id="e5408-171">To ensure that the execution of highly privileged tasks is as secure as possible, use a privileged access workstation (PAW).</span></span> <span data-ttu-id="e5408-172">PAW 是仅用于敏感配置任务的专用计算机，例如Microsoft 365全局管理员帐户的专用配置。</span><span class="sxs-lookup"><span data-stu-id="e5408-172">A PAW is a dedicated computer that is only used for sensitive configuration tasks, such as Microsoft 365 configuration that requires a global administrator account.</span></span> <span data-ttu-id="e5408-173">由于此计算机不每天用于 Internet 浏览或电子邮件，因此可以更好地防范 Internet 攻击和威胁。</span><span class="sxs-lookup"><span data-stu-id="e5408-173">Because this computer is not used daily for Internet browsing or email, it is better protected from Internet attacks and threats.</span></span>
  
<span data-ttu-id="e5408-174">有关如何设置 PAW 的说明，请参阅 [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices) 。</span><span class="sxs-lookup"><span data-stu-id="e5408-174">For instructions on how to set up a PAW, see [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices).</span></span>

<span data-ttu-id="e5408-175">若要为 Azure AD 租户和管理员帐户启用 Azure PIM，请参阅 [PIM 配置步骤](/azure/active-directory/active-directory-privileged-identity-management-configure)。</span><span class="sxs-lookup"><span data-stu-id="e5408-175">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="e5408-176">可参阅[确保 Azure AD 中混合部署和云部署的特权访问安全性](/azure/active-directory/admin-roles-best-practices)来制定全面的路线图，以确保特权访问能够防止网络攻击者。</span><span class="sxs-lookup"><span data-stu-id="e5408-176">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](/azure/active-directory/admin-roles-best-practices).</span></span>

### <a name="azure-ad-privileged-identity-management"></a><span data-ttu-id="e5408-177">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="e5408-177">Azure AD Privileged Identity Management</span></span>

<span data-ttu-id="e5408-178">无需将全局管理员帐户永久分配给 全局管理员角色，可以使用 Azure AD Privileged Identity Management (PIM) 按需、实时分配 全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="e5408-178">Rather than having your global administrator accounts be permanently assigned the global administrator role, you can use Azure AD Privileged Identity Management (PIM) to enable on-demand, just-in-time assignment of the global administrator role when it is needed.</span></span>
  
<span data-ttu-id="e5408-179">全局管理员帐户从永久管理员转到符合条件的管理员。</span><span class="sxs-lookup"><span data-stu-id="e5408-179">Your global administrator accounts go from being permanent admins to eligible admins.</span></span> <span data-ttu-id="e5408-180">在全局管理员角色用户需要之前，该邮箱处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="e5408-180">The global administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="e5408-181">然后完成激活过程，将全局管理员角色预先确定的时间添加到全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="e5408-181">You then complete an activation process to add the global administrator role to the global administrator account for a predetermined amount of time.</span></span> <span data-ttu-id="e5408-182">当时间到期时，PIM 会从全局全局管理员角色中删除该密码。</span><span class="sxs-lookup"><span data-stu-id="e5408-182">When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>
  
<span data-ttu-id="e5408-183">使用 PIM 和此过程可显著减少全局管理员帐户易受恶意用户攻击和使用的时间。</span><span class="sxs-lookup"><span data-stu-id="e5408-183">Using PIM and this process significantly reduces the amount of time that your global administrator accounts are vulnerable to attack and use by malicious users.</span></span>

<span data-ttu-id="e5408-184">可从 Microsoft 365 E5 包含的 Azure Active Directory Premium P2 中获取 PIM。</span><span class="sxs-lookup"><span data-stu-id="e5408-184">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="e5408-185">或者，可以为管理员帐户单独购买 Azure Active Directory Premium P2 许可证。</span><span class="sxs-lookup"><span data-stu-id="e5408-185">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>
  
<span data-ttu-id="e5408-186">有关详细信息，请参阅[Azure AD Privileged Identity Management。](/azure/active-directory/active-directory-privileged-identity-management-configure)</span><span class="sxs-lookup"><span data-stu-id="e5408-186">For more information, see [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>
  

### <a name="privileged-access-management"></a><span data-ttu-id="e5408-187">特权访问管理</span><span class="sxs-lookup"><span data-stu-id="e5408-187">Privileged access management</span></span>

<span data-ttu-id="e5408-p121">租户中的特权访问管理可通过配置相应策略来实现，这些策略会为基于任务的活动指定实时访问权限。这种管理可为组织提供保护，防止他人使用具有长期敏感数据访问权限或关键配置设置访问权限的现有特权访问帐户。例如，你可以配置一个特权访问管理策略，要求必须经过显示审批才能访问和更改租户中的组织邮箱设置。</span><span class="sxs-lookup"><span data-stu-id="e5408-p121">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="e5408-p122">在此步骤中，你将在租户中启用特权访问管理并配置特权访问策略，这些策略可为基于任务对组织的数据和配置设置进行的访问提供额外的安全性。要开始在组织中使用特权访问，需要执行三个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="e5408-p122">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization. There are three basic steps to get started with privileged access in your organization:</span></span>

- <span data-ttu-id="e5408-193">创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="e5408-193">Creating an approver's group</span></span>
- <span data-ttu-id="e5408-194">启用特权访问</span><span class="sxs-lookup"><span data-stu-id="e5408-194">Enabling privileged access</span></span>
- <span data-ttu-id="e5408-195">创建审批策略</span><span class="sxs-lookup"><span data-stu-id="e5408-195">Creating approval policies</span></span>

<span data-ttu-id="e5408-196">利用特权访问管理，组织可以零长期特权运行，并提供一层防御因此类长期管理访问权限引发的漏洞。</span><span class="sxs-lookup"><span data-stu-id="e5408-196">Privileged access management enables your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="e5408-197">特权访问需要批准，以执行已定义关联审批策略的任何任务。</span><span class="sxs-lookup"><span data-stu-id="e5408-197">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="e5408-198">需要执行审批策略中包含的任务的用户必须请求并被授予访问权限审批。</span><span class="sxs-lookup"><span data-stu-id="e5408-198">Users needing to execute tasks included in the approval policy must request and be granted access approval.</span></span>

<span data-ttu-id="e5408-199">若要启用特权访问管理，请参阅配置 [特权访问管理](/office365/securitycompliance/privileged-access-management-configuration)。</span><span class="sxs-lookup"><span data-stu-id="e5408-199">To enable privileged access management, see [Configure privileged access management](/office365/securitycompliance/privileged-access-management-configuration).</span></span>

<span data-ttu-id="e5408-200">有关详细信息，请参阅 [Privileged access management](/office365/securitycompliance/privileged-access-management-overview)。</span><span class="sxs-lookup"><span data-stu-id="e5408-200">For more information, see [Privileged access management](/office365/securitycompliance/privileged-access-management-overview).</span></span>

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a><span data-ttu-id="e5408-201">SIEM 安全信息和事件 (SIEM) 软件进行Microsoft 365日志记录</span><span class="sxs-lookup"><span data-stu-id="e5408-201">Security information and event management (SIEM) software for Microsoft 365 logging</span></span>

<span data-ttu-id="e5408-202">在服务器上运行的 SIEM 软件对由应用程序和网络硬件创建的安全警报和事件执行实时分析。</span><span class="sxs-lookup"><span data-stu-id="e5408-202">SIEM software run on a server performs real-time analysis of security alerts and events created by applications and network hardware.</span></span> <span data-ttu-id="e5408-203">若要允许 SIEM 服务器在其分析和Microsoft 365功能中包括安全警报和事件，请将 Azure AD 集成到 SEIM 中。</span><span class="sxs-lookup"><span data-stu-id="e5408-203">To allow your SIEM server to include Microsoft 365 security alerts and events in its analysis and reporting functions, integrate Azure AD into you SEIM.</span></span> <span data-ttu-id="e5408-204">请参阅[Azure 日志集成](/azure/security/security-azure-log-integration-overview)简介。</span><span class="sxs-lookup"><span data-stu-id="e5408-204">See [Introduction to Azure Log Integration](/azure/security/security-azure-log-integration-overview).</span></span>

## <a name="next-step"></a><span data-ttu-id="e5408-205">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e5408-205">Next step</span></span>

<span data-ttu-id="e5408-206">如果要为订阅设置标识Microsoft 365，请参阅：</span><span class="sxs-lookup"><span data-stu-id="e5408-206">If you're setting up identity for your Microsoft 365 subscription, see:</span></span>

- <span data-ttu-id="e5408-207">[使用仅](cloud-only-identities.md) 云标识时仅云标识</span><span class="sxs-lookup"><span data-stu-id="e5408-207">[Cloud-only identities](cloud-only-identities.md) if you're using cloud-only identity</span></span>
- <span data-ttu-id="e5408-208">[使用混合标识时](prepare-for-directory-synchronization.md) 准备目录同步</span><span class="sxs-lookup"><span data-stu-id="e5408-208">[Prepare for directory synchronization](prepare-for-directory-synchronization.md) if you're using hybrid identity</span></span>

  
## <a name="see-also"></a><span data-ttu-id="e5408-209">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5408-209">See also</span></span>

[<span data-ttu-id="e5408-210">Microsoft 365安全路线图</span><span class="sxs-lookup"><span data-stu-id="e5408-210">Microsoft 365 security roadmap</span></span>](/office365/securitycompliance/security-roadmap)