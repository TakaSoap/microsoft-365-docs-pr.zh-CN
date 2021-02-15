---
title: Microsoft 365 测试环境中传递身份验证的标识和设备访问先决条件
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
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况，其中内附传递身份验证的先决条件。
ms.openlocfilehash: 71ba116ee45f031b156934e0924a0c3d460110d5
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233758"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="1e305-103">Microsoft 365 测试环境中传递身份验证的标识和设备访问先决条件</span><span class="sxs-lookup"><span data-stu-id="1e305-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="1e305-104">*本测试实验室指南仅适用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="1e305-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="1e305-105">[标识](../security/office-365-security/microsoft-365-policies-configurations.md) 和设备访问配置是一组配置和条件访问策略，用于保护对 Microsoft 365 企业版中与 Azure Active Directory (Azure AD) 集成的所有服务的访问。</span><span class="sxs-lookup"><span data-stu-id="1e305-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="1e305-106">本文介绍了可以如何配置 Microsoft 365 测试环境，以使其满足标识和设备访问的[传递身份验证先决条件配置](../security/office-365-security/identity-access-prerequisites.md#prerequisites)要求。</span><span class="sxs-lookup"><span data-stu-id="1e305-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="1e305-107">设置此测试环境有十个阶段：</span><span class="sxs-lookup"><span data-stu-id="1e305-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="1e305-108">构建传递身份验证的模拟企业 Microsoft 365 测试环境</span><span class="sxs-lookup"><span data-stu-id="1e305-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2. <span data-ttu-id="1e305-109">配置 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="1e305-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="1e305-110">配置命名位置</span><span class="sxs-lookup"><span data-stu-id="1e305-110">Configure named locations</span></span>
4. <span data-ttu-id="1e305-111">配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="1e305-111">Configure password writeback</span></span>
5. <span data-ttu-id="1e305-112">配置自助密码重置</span><span class="sxs-lookup"><span data-stu-id="1e305-112">Configure self-service password reset</span></span>
6. <span data-ttu-id="1e305-113">配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="1e305-113">Configure multifactor authentication</span></span>
7. <span data-ttu-id="1e305-114">启用已加入域的 Windows 计算机的自动设备注册</span><span class="sxs-lookup"><span data-stu-id="1e305-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="1e305-115">配置 Azure AD 密码保护</span><span class="sxs-lookup"><span data-stu-id="1e305-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="1e305-116">启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="1e305-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="1e305-117">为 Exchange Online 和 Skype for Business Online 启用新式身份验证</span><span class="sxs-lookup"><span data-stu-id="1e305-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="1e305-118">阶段 1：构建传递身份验证的模拟企业 Microsoft 365 测试环境</span><span class="sxs-lookup"><span data-stu-id="1e305-118">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="1e305-119">按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="1e305-119">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="1e305-120">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="1e305-120">Here is the resulting configuration.</span></span>

![采用传递身份验证的模拟企业测试环境](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="1e305-122">阶段 2：配置 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="1e305-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="1e305-123">按照[“Azure AD 无缝单点登录”测试实验室指南的阶段 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="1e305-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="1e305-124">阶段 3：配置命名位置</span><span class="sxs-lookup"><span data-stu-id="1e305-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="1e305-125">首先，确定组织使用的公共 IP 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="1e305-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="1e305-126">接下来，按照[在 Azure Active Directory 中配置命名位置](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的说明将地址或地址范围添加为命名位置。</span><span class="sxs-lookup"><span data-stu-id="1e305-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="1e305-127">阶段 4：配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="1e305-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="1e305-128">接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="1e305-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="1e305-129">阶段 5：配置自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="1e305-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="1e305-130">接下来，按照[“密码重置”测试实验室指南的阶段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="1e305-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="1e305-131">为特定 Azure AD 组中的帐户启用密码重置时，请将这些帐户添加到 **密码重置** 组：</span><span class="sxs-lookup"><span data-stu-id="1e305-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="1e305-132">用户 2</span><span class="sxs-lookup"><span data-stu-id="1e305-132">User 2</span></span>
- <span data-ttu-id="1e305-133">用户 3</span><span class="sxs-lookup"><span data-stu-id="1e305-133">User 3</span></span>
- <span data-ttu-id="1e305-134">用户 4</span><span class="sxs-lookup"><span data-stu-id="1e305-134">User 4</span></span>
- <span data-ttu-id="1e305-135">用户 5</span><span class="sxs-lookup"><span data-stu-id="1e305-135">User 5</span></span>

<span data-ttu-id="1e305-136">仅为用户 2 帐户测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="1e305-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="1e305-137">阶段 6：配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="1e305-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="1e305-138">按照以下用户帐户的[“多重身份验证”测试实验室指南的阶段 2 ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)中的说明操作：</span><span class="sxs-lookup"><span data-stu-id="1e305-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="1e305-139">用户 2</span><span class="sxs-lookup"><span data-stu-id="1e305-139">User 2</span></span>
- <span data-ttu-id="1e305-140">用户 3</span><span class="sxs-lookup"><span data-stu-id="1e305-140">User 3</span></span>
- <span data-ttu-id="1e305-141">用户 4</span><span class="sxs-lookup"><span data-stu-id="1e305-141">User 4</span></span>
- <span data-ttu-id="1e305-142">用户 5</span><span class="sxs-lookup"><span data-stu-id="1e305-142">User 5</span></span>

<span data-ttu-id="1e305-143">仅为用户 2 帐户测试多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="1e305-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="1e305-144">阶段 7：启用已加入域的 Windows 计算机的自动设备注册</span><span class="sxs-lookup"><span data-stu-id="1e305-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="1e305-145">按照 [以下说明](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) 启用已加入域的 Windows 计算机的自动设备注册。</span><span class="sxs-lookup"><span data-stu-id="1e305-145">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="1e305-146">第 8 阶段：配置 Azure AD 密码保护</span><span class="sxs-lookup"><span data-stu-id="1e305-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="1e305-147">按照 [以下说明](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) 阻止已知的弱密码及其变体。</span><span class="sxs-lookup"><span data-stu-id="1e305-147">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="1e305-148">第 9 阶段：启用 Azure AD 标识保护</span><span class="sxs-lookup"><span data-stu-id="1e305-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="1e305-149">按照[“Azure AD Identity Protection”测试实验室指南的阶段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="1e305-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="1e305-150">第 10 阶段：为 Exchange Online 和 Skype for Business Online 启用新式验证</span><span class="sxs-lookup"><span data-stu-id="1e305-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="1e305-151">对于 Exchange Online，请按照[这些说明](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)操作。</span><span class="sxs-lookup"><span data-stu-id="1e305-151">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="1e305-152">对于 Skype for Business Online：</span><span class="sxs-lookup"><span data-stu-id="1e305-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="1e305-153">连接到 [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1e305-153">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="1e305-154">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1e305-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="1e305-155">使用此命令验证更改是否成功。</span><span class="sxs-lookup"><span data-stu-id="1e305-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="1e305-156">结果是得到一个符合以下条件的测试环境：满足标识和设备访问的[传递身份验证先决条件配置](../security/office-365-security/identity-access-prerequisites.md#prerequisites)要求。</span><span class="sxs-lookup"><span data-stu-id="1e305-156">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="1e305-157">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1e305-157">Next step</span></span>

<span data-ttu-id="1e305-158">使用[常见标识和设备访问策略](identity-access-policies.md)配置基于这些先决条件构建的策略并保护标识和设备。</span><span class="sxs-lookup"><span data-stu-id="1e305-158">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e305-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e305-159">See also</span></span>

[<span data-ttu-id="1e305-160">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="1e305-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="1e305-161">标识路线图</span><span class="sxs-lookup"><span data-stu-id="1e305-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="1e305-162">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="1e305-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1e305-163">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="1e305-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1e305-164">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="1e305-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

