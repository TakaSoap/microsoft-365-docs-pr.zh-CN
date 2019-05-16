---
title: Microsoft 365 测试环境中传递身份验证的标识和设备访问先决条件
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
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况，其中内附传递身份验证的先决条件。
ms.openlocfilehash: b8c9ebefacf81293b553aecf8ead0a387c18758b
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073019"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="aef3c-103">Microsoft 365 测试环境中传递身份验证的标识和设备访问先决条件</span><span class="sxs-lookup"><span data-stu-id="aef3c-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="aef3c-104">[标识和设备访问配置](microsoft-365-policies-configurations.md)是一组配置和条件访问策略，用于保护对与 Azure Active Directory (Azure AD) 集成的所有服务的访问，包括 Microsoft 365 企业版中的 Office 365 和企业移动性 + 安全性 (EMS)。</span><span class="sxs-lookup"><span data-stu-id="aef3c-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="aef3c-105">本文介绍了可以如何配置 Microsoft 365 测试环境，以使其满足标识和设备访问的[传递身份验证先决条件配置](identity-access-prerequisites.md#prerequisites)要求。</span><span class="sxs-lookup"><span data-stu-id="aef3c-105">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="aef3c-106">此测试环境的设置分为以下八个阶段：</span><span class="sxs-lookup"><span data-stu-id="aef3c-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="aef3c-107">构建传递身份验证的模拟企业 Microsoft 365 测试环境</span><span class="sxs-lookup"><span data-stu-id="aef3c-107">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="aef3c-108">配置 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="aef3c-108">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="aef3c-109">配置命名位置</span><span class="sxs-lookup"><span data-stu-id="aef3c-109">Configure named locations</span></span>
4.  <span data-ttu-id="aef3c-110">配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="aef3c-110">Configure password writeback</span></span>
5.  <span data-ttu-id="aef3c-111">配置自助密码重置</span><span class="sxs-lookup"><span data-stu-id="aef3c-111">Configure self-service password reset</span></span>
6.  <span data-ttu-id="aef3c-112">配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="aef3c-112">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="aef3c-113">启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="aef3c-113">Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="aef3c-114">为 Exchange Online 和 Skype for Business Online 启用新式身份验证</span><span class="sxs-lookup"><span data-stu-id="aef3c-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="aef3c-115">阶段 1：构建传递身份验证的模拟企业 Microsoft 365 测试环境</span><span class="sxs-lookup"><span data-stu-id="aef3c-115">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="aef3c-116">按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="aef3c-116">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="aef3c-117">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="aef3c-117">Here is the resulting configuration.</span></span>

![采用传递身份验证的模拟企业测试环境](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="aef3c-119">阶段 2：配置 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="aef3c-119">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="aef3c-120">按照[“Azure AD 无缝单点登录”测试实验室指南的阶段 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="aef3c-120">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="aef3c-121">阶段 3：配置命名位置</span><span class="sxs-lookup"><span data-stu-id="aef3c-121">Phase 3: Configure named locations</span></span>

<span data-ttu-id="aef3c-122">首先，确定组织使用的公共 IP 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="aef3c-122">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="aef3c-123">接下来，按照[在 Azure Active Directory 中配置命名位置](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的说明将地址或地址范围添加为命名位置。</span><span class="sxs-lookup"><span data-stu-id="aef3c-123">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="aef3c-124">阶段 4：配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="aef3c-124">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="aef3c-125">接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="aef3c-125">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="aef3c-126">阶段 5：配置自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="aef3c-126">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="aef3c-127">接下来，按照[“密码重置”测试实验室指南的阶段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="aef3c-127">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="aef3c-128">为特定 Azure AD 组中的帐户启用密码重置时，请将这些帐户添加到**密码重置**组：</span><span class="sxs-lookup"><span data-stu-id="aef3c-128">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="aef3c-129">用户 2</span><span class="sxs-lookup"><span data-stu-id="aef3c-129">User: %2</span></span>
- <span data-ttu-id="aef3c-130">用户 3</span><span class="sxs-lookup"><span data-stu-id="aef3c-130">User Defined 3</span></span>
- <span data-ttu-id="aef3c-131">用户 4</span><span class="sxs-lookup"><span data-stu-id="aef3c-131">User: %4</span></span>
- <span data-ttu-id="aef3c-132">用户 5</span><span class="sxs-lookup"><span data-stu-id="aef3c-132">User 5</span></span>

<span data-ttu-id="aef3c-133">仅为用户 2 帐户测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="aef3c-133">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="aef3c-134">阶段 6：配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="aef3c-134">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="aef3c-135">按照以下用户帐户的[“多重身份验证”测试实验室指南的阶段 2 ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)中的说明操作：</span><span class="sxs-lookup"><span data-stu-id="aef3c-135">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="aef3c-136">用户 2</span><span class="sxs-lookup"><span data-stu-id="aef3c-136">User: %2</span></span>
- <span data-ttu-id="aef3c-137">用户 3</span><span class="sxs-lookup"><span data-stu-id="aef3c-137">User Defined 3</span></span>
- <span data-ttu-id="aef3c-138">用户 4</span><span class="sxs-lookup"><span data-stu-id="aef3c-138">User: %4</span></span>
- <span data-ttu-id="aef3c-139">用户 5</span><span class="sxs-lookup"><span data-stu-id="aef3c-139">User 5</span></span>

<span data-ttu-id="aef3c-140">仅为用户 2 帐户测试多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="aef3c-140">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="aef3c-141">阶段 7：启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="aef3c-141">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="aef3c-142">按照[“Azure AD Identity Protection”测试实验室指南的阶段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="aef3c-142">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="aef3c-143">阶段 8：启用 Exchange Online 和 Skype for Business Online 的新式身份验证</span><span class="sxs-lookup"><span data-stu-id="aef3c-143">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="aef3c-144">对于 Exchange Online，请按照[这些说明](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)操作。</span><span class="sxs-lookup"><span data-stu-id="aef3c-144">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="aef3c-145">对于 Skype for Business Online：</span><span class="sxs-lookup"><span data-stu-id="aef3c-145">Skype for Business Online</span></span>

1. <span data-ttu-id="aef3c-146">连接到 [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aef3c-146">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="aef3c-147">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="aef3c-147">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="aef3c-148">使用此命令验证更改是否成功。</span><span class="sxs-lookup"><span data-stu-id="aef3c-148">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="aef3c-149">结果是得到一个符合以下条件的测试环境：满足标识和设备访问的[传递身份验证先决条件配置](identity-access-prerequisites.md#prerequisites)要求。</span><span class="sxs-lookup"><span data-stu-id="aef3c-149">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="aef3c-150">后续步骤</span><span class="sxs-lookup"><span data-stu-id="aef3c-150">Next step</span></span>

<span data-ttu-id="aef3c-151">使用[常见标识和设备访问策略](identity-access-policies.md)配置基于这些先决条件构建的策略并保护标识和设备。</span><span class="sxs-lookup"><span data-stu-id="aef3c-151">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="aef3c-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aef3c-152">See also</span></span>

[<span data-ttu-id="aef3c-153">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="aef3c-153">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="aef3c-154">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="aef3c-154">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="aef3c-155">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="aef3c-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="aef3c-156">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="aef3c-156">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="aef3c-157">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="aef3c-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

