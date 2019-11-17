---
title: Microsoft 365 测试环境中密码哈希同步的标识和设备访问先决条件
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建 Microsoft 365 环境以测试标识和设备访问，含密码哈希同步身份验证的先决条件。
ms.openlocfilehash: d5feddd7ddddd0ad8891873a654627a0e7ba4fa3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673348"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="82caf-103">Microsoft 365 测试环境中密码哈希同步的标识和设备访问先决条件</span><span class="sxs-lookup"><span data-stu-id="82caf-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="82caf-104">*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="82caf-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="82caf-105">[标识和设备访问配置](microsoft-365-policies-configurations.md)是一组配置和条件访问策略，用于保护对与 Azure Active Directory (Azure AD) 集成的所有服务的访问，包括 Microsoft 365 企业版中的 Office 365 和企业移动性 + 安全性 (EMS)。</span><span class="sxs-lookup"><span data-stu-id="82caf-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="82caf-106">本文介绍如何配置 Microsoft 365 测试环境，使其满足 [Active Directory 和用于标识和设备访问的密码哈希同步先决条件配置](identity-access-prerequisites.md#prerequisites)的要求。</span><span class="sxs-lookup"><span data-stu-id="82caf-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="82caf-107">此测试环境的设置分为以下八个阶段：</span><span class="sxs-lookup"><span data-stu-id="82caf-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="82caf-108">创建密码哈希同步的测试环境的模拟企业配置</span><span class="sxs-lookup"><span data-stu-id="82caf-108">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="82caf-109">配置 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="82caf-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="82caf-110">配置命名位置</span><span class="sxs-lookup"><span data-stu-id="82caf-110">Configure named locations</span></span>
4.  <span data-ttu-id="82caf-111">配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="82caf-111">Configure password writeback</span></span>
5.  <span data-ttu-id="82caf-112">为所有用户帐户配置自助密码重置</span><span class="sxs-lookup"><span data-stu-id="82caf-112">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="82caf-113">为所有用户帐户配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="82caf-113">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="82caf-114">启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="82caf-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="82caf-115">启用 Exchange Online 和 Skype for Business Online 的新式身份验证</span><span class="sxs-lookup"><span data-stu-id="82caf-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="82caf-116">阶段 1：构建密码哈希同步的 Microsoft 365 测试环境的模拟企业配置</span><span class="sxs-lookup"><span data-stu-id="82caf-116">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="82caf-117">按照[密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="82caf-117">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="82caf-118">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="82caf-118">Here is the resulting configuration.</span></span>

![使用密码哈希同步测试环境的模拟企业配置](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="82caf-120">阶段 2：配置 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="82caf-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="82caf-121">按照[“Azure AD 无缝单点登录”测试实验室指南的阶段 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="82caf-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="82caf-122">阶段 3：配置命名位置</span><span class="sxs-lookup"><span data-stu-id="82caf-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="82caf-123">首先，确定组织使用的公共 IP 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="82caf-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="82caf-124">接下来，按照[在 Azure Active Directory 中配置命名位置](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的说明将地址或地址范围添加为命名位置。</span><span class="sxs-lookup"><span data-stu-id="82caf-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="82caf-125">阶段 4：配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="82caf-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="82caf-126">接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="82caf-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="82caf-127">阶段 5：配置自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="82caf-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="82caf-128">接下来，按照[“密码重置”测试实验室指南的阶段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="82caf-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="82caf-129">为特定 Azure AD 组中的帐户启用密码重置时，请将这些帐户添加到**密码重置**组：</span><span class="sxs-lookup"><span data-stu-id="82caf-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="82caf-130">用户 2</span><span class="sxs-lookup"><span data-stu-id="82caf-130">User 2</span></span>
- <span data-ttu-id="82caf-131">用户 3</span><span class="sxs-lookup"><span data-stu-id="82caf-131">User 3</span></span>
- <span data-ttu-id="82caf-132">用户 4</span><span class="sxs-lookup"><span data-stu-id="82caf-132">User 4</span></span>
- <span data-ttu-id="82caf-133">用户 5</span><span class="sxs-lookup"><span data-stu-id="82caf-133">User 5</span></span>

<span data-ttu-id="82caf-134">仅为用户 2 帐户测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="82caf-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="82caf-135">阶段 6：配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="82caf-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="82caf-136">按照以下用户帐户的[“多重身份验证”测试实验室指南的阶段 2 ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)中的说明操作：</span><span class="sxs-lookup"><span data-stu-id="82caf-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="82caf-137">用户 2</span><span class="sxs-lookup"><span data-stu-id="82caf-137">User 2</span></span>
- <span data-ttu-id="82caf-138">用户 3</span><span class="sxs-lookup"><span data-stu-id="82caf-138">User 3</span></span>
- <span data-ttu-id="82caf-139">用户 4</span><span class="sxs-lookup"><span data-stu-id="82caf-139">User 4</span></span>
- <span data-ttu-id="82caf-140">用户 5</span><span class="sxs-lookup"><span data-stu-id="82caf-140">User 5</span></span>

<span data-ttu-id="82caf-141">仅为用户 2 帐户测试多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="82caf-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="82caf-142">阶段 7：启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="82caf-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="82caf-143">按照[“Azure AD Identity Protection”测试实验室指南的阶段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="82caf-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="82caf-144">阶段 8：启用 Exchange Online 和 Skype for Business Online 的新式身份验证</span><span class="sxs-lookup"><span data-stu-id="82caf-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="82caf-145">对于 Exchange Online，请按照[这些说明](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)操作。</span><span class="sxs-lookup"><span data-stu-id="82caf-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="82caf-146">对于 Skype for Business Online：</span><span class="sxs-lookup"><span data-stu-id="82caf-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="82caf-147">连接到 [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="82caf-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="82caf-148">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="82caf-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="82caf-149">使用此命令验证更改是否成功。</span><span class="sxs-lookup"><span data-stu-id="82caf-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="82caf-150">结果是满足 [Active Directory 和用于标识和设备访问的密码哈希同步先决条件配置](identity-access-prerequisites.md#prerequisites)的要求的环境。</span><span class="sxs-lookup"><span data-stu-id="82caf-150">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="82caf-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="82caf-151">Next step</span></span>

<span data-ttu-id="82caf-152">使用[常见标识和设备访问策略](identity-access-policies.md)配置基于这些先决条件构建的策略并保护标识和设备。</span><span class="sxs-lookup"><span data-stu-id="82caf-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="82caf-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82caf-153">See also</span></span>

[<span data-ttu-id="82caf-154">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="82caf-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="82caf-155">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="82caf-155">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="82caf-156">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="82caf-156">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="82caf-157">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="82caf-157">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="82caf-158">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="82caf-158">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
