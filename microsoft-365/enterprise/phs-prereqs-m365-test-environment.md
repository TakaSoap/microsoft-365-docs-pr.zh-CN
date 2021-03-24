---
title: Microsoft 365 测试环境中密码哈希同步的标识和设备访问先决条件
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建 Microsoft 365 环境以测试标识和设备访问，含密码哈希同步身份验证的先决条件。
ms.openlocfilehash: 2ca83b6ab715a752d3d9620af631263eb5d84fa3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051242"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="6c554-103">Microsoft 365 测试环境中密码哈希同步的标识和设备访问先决条件</span><span class="sxs-lookup"><span data-stu-id="6c554-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="6c554-104">*本测试实验室指南仅适用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="6c554-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6c554-105">[](../security/defender-365-security/microsoft-365-policies-configurations.md)标识和设备访问配置是一组配置和条件访问策略，用于保护对 Microsoft 365 企业版中与 Azure Active Directory (Azure AD) 集成的所有服务的访问。</span><span class="sxs-lookup"><span data-stu-id="6c554-105">[Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="6c554-106">本文介绍如何配置 Microsoft 365 测试环境，该环境满足标识和设备访问的混合密码哈希 [同步](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) 身份验证先决条件配置的要求。</span><span class="sxs-lookup"><span data-stu-id="6c554-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [hybrid with password hash sync authentication prerequisite configuration](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="6c554-107">设置此测试环境有 10 个阶段：</span><span class="sxs-lookup"><span data-stu-id="6c554-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="6c554-108">创建密码哈希同步的测试环境的模拟企业配置</span><span class="sxs-lookup"><span data-stu-id="6c554-108">Create a simulated enterprise with password hash sync test environment</span></span>
2. <span data-ttu-id="6c554-109">配置 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="6c554-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="6c554-110">配置命名位置</span><span class="sxs-lookup"><span data-stu-id="6c554-110">Configure named locations</span></span>
4. <span data-ttu-id="6c554-111">配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="6c554-111">Configure password writeback</span></span>
5. <span data-ttu-id="6c554-112">为所有用户帐户配置自助密码重置</span><span class="sxs-lookup"><span data-stu-id="6c554-112">Configure self-service password reset for all user accounts</span></span>
6. <span data-ttu-id="6c554-113">为所有用户帐户配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="6c554-113">Configure multifactor authentication for all user accounts</span></span>
7. <span data-ttu-id="6c554-114">启用已加入域的 Windows 计算机的自动设备注册</span><span class="sxs-lookup"><span data-stu-id="6c554-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="6c554-115">配置 Azure AD 密码保护</span><span class="sxs-lookup"><span data-stu-id="6c554-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="6c554-116">启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="6c554-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="6c554-117">启用 Exchange Online 和 Skype for Business Online 的新式身份验证</span><span class="sxs-lookup"><span data-stu-id="6c554-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="6c554-118">阶段 1：构建密码哈希同步的 Microsoft 365 测试环境的模拟企业配置</span><span class="sxs-lookup"><span data-stu-id="6c554-118">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="6c554-119">按照密码哈希 [同步测试实验室指南](password-hash-sync-m365-ent-test-environment.md) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="6c554-119">Follow the instructions in [the password hash synchronization](password-hash-sync-m365-ent-test-environment.md) Test Lab Guide.</span></span>
<span data-ttu-id="6c554-120">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="6c554-120">Here is the resulting configuration.</span></span>

![使用密码哈希同步测试环境的模拟企业配置](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="6c554-122">阶段 2：配置 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="6c554-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="6c554-123">按照[“Azure AD 无缝单点登录”测试实验室指南的阶段 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="6c554-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="6c554-124">阶段 3：配置命名位置</span><span class="sxs-lookup"><span data-stu-id="6c554-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="6c554-125">首先，确定组织使用的公共 IP 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="6c554-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="6c554-126">接下来，按照[在 Azure Active Directory 中配置命名位置](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的说明将地址或地址范围添加为命名位置。</span><span class="sxs-lookup"><span data-stu-id="6c554-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="6c554-127">阶段 4：配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="6c554-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="6c554-128">接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="6c554-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="6c554-129">阶段 5：配置自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="6c554-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="6c554-130">接下来，按照[“密码重置”测试实验室指南的阶段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="6c554-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="6c554-131">为特定 Azure AD 组中的帐户启用密码重置时，请将这些帐户添加到 **密码重置** 组：</span><span class="sxs-lookup"><span data-stu-id="6c554-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="6c554-132">用户 2</span><span class="sxs-lookup"><span data-stu-id="6c554-132">User 2</span></span>
- <span data-ttu-id="6c554-133">用户 3</span><span class="sxs-lookup"><span data-stu-id="6c554-133">User 3</span></span>
- <span data-ttu-id="6c554-134">用户 4</span><span class="sxs-lookup"><span data-stu-id="6c554-134">User 4</span></span>
- <span data-ttu-id="6c554-135">用户 5</span><span class="sxs-lookup"><span data-stu-id="6c554-135">User 5</span></span>

<span data-ttu-id="6c554-136">仅为用户 2 帐户测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="6c554-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="6c554-137">阶段 6：配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="6c554-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="6c554-138">按照以下用户帐户的[“多重身份验证”测试实验室指南的阶段 2 ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)中的说明操作：</span><span class="sxs-lookup"><span data-stu-id="6c554-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="6c554-139">用户 2</span><span class="sxs-lookup"><span data-stu-id="6c554-139">User 2</span></span>
- <span data-ttu-id="6c554-140">用户 3</span><span class="sxs-lookup"><span data-stu-id="6c554-140">User 3</span></span>
- <span data-ttu-id="6c554-141">用户 4</span><span class="sxs-lookup"><span data-stu-id="6c554-141">User 4</span></span>
- <span data-ttu-id="6c554-142">用户 5</span><span class="sxs-lookup"><span data-stu-id="6c554-142">User 5</span></span>

<span data-ttu-id="6c554-143">仅为用户 2 帐户测试多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="6c554-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="6c554-144">阶段 7：启用已加入域的 Windows 计算机的自动设备注册</span><span class="sxs-lookup"><span data-stu-id="6c554-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="6c554-145">按照 [以下说明](/azure/active-directory/devices/hybrid-azuread-join-plan) 启用已加入域的 Windows 计算机的自动设备注册。</span><span class="sxs-lookup"><span data-stu-id="6c554-145">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="6c554-146">第 8 阶段：配置 Azure AD 密码保护</span><span class="sxs-lookup"><span data-stu-id="6c554-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="6c554-147">按照 [以下说明](/azure/active-directory/authentication/concept-password-ban-bad) 阻止已知的弱密码及其变体。</span><span class="sxs-lookup"><span data-stu-id="6c554-147">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="6c554-148">第 9 阶段：启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="6c554-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="6c554-149">按照[“Azure AD Identity Protection”测试实验室指南的阶段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="6c554-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="6c554-150">第 10 阶段：为 Exchange Online 和 Skype for Business Online 启用新式验证</span><span class="sxs-lookup"><span data-stu-id="6c554-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="6c554-151">对于 Exchange Online，请按照[这些说明](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)操作。</span><span class="sxs-lookup"><span data-stu-id="6c554-151">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="6c554-152">对于 Skype for Business Online：</span><span class="sxs-lookup"><span data-stu-id="6c554-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="6c554-153">连接到 [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6c554-153">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="6c554-154">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="6c554-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="6c554-155">使用此命令验证更改是否成功。</span><span class="sxs-lookup"><span data-stu-id="6c554-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="6c554-156">结果是满足 [Active Directory 和用于标识和设备访问的密码哈希同步先决条件配置](../security/defender-365-security/identity-access-prerequisites.md#prerequisites)的要求的环境。</span><span class="sxs-lookup"><span data-stu-id="6c554-156">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="6c554-157">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6c554-157">Next step</span></span>

<span data-ttu-id="6c554-158">使用[常见标识和设备访问策略](../security/defender-365-security/identity-access-policies.md)配置基于这些先决条件构建的策略并保护标识和设备。</span><span class="sxs-lookup"><span data-stu-id="6c554-158">Use [Common identity and device access policies](../security/defender-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c554-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c554-159">See also</span></span>

[<span data-ttu-id="6c554-160">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="6c554-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="6c554-161">标识路线图</span><span class="sxs-lookup"><span data-stu-id="6c554-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="6c554-162">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="6c554-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6c554-163">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="6c554-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6c554-164">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="6c554-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
