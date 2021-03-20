---
title: Microsoft 365 测试环境中仅限云的标识和设备访问先决条件
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
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况，其中内附仅限云的身份验证的先决条件。
ms.openlocfilehash: 3e5a9ef1f610bf3dc6d23c9e584e179fb8ab9ca9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905136"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="51f91-103">Microsoft 365 测试环境中仅限云的标识和设备访问先决条件</span><span class="sxs-lookup"><span data-stu-id="51f91-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="51f91-104">*本测试实验室指南仅适用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="51f91-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="51f91-105">[标识和设备访问](../security/office-365-security/microsoft-365-policies-configurations.md) 配置是一组建议配置和条件访问策略，用于保护对与 Azure AD (Azure Active Directory 集成的所有服务) 。</span><span class="sxs-lookup"><span data-stu-id="51f91-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="51f91-106">本文介绍了如何配置 Microsoft 365 测试环境，使其满足标识和设备访问[仅限云的先决条件配置](../security/office-365-security/identity-access-prerequisites.md#prerequisites)的要求。</span><span class="sxs-lookup"><span data-stu-id="51f91-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="51f91-107">此测试环境的设置分为以下八个阶段：</span><span class="sxs-lookup"><span data-stu-id="51f91-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="51f91-108">构建轻量级测试环境</span><span class="sxs-lookup"><span data-stu-id="51f91-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="51f91-109">配置命名位置</span><span class="sxs-lookup"><span data-stu-id="51f91-109">Configure named locations</span></span>
3. <span data-ttu-id="51f91-110">配置自助密码重置</span><span class="sxs-lookup"><span data-stu-id="51f91-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="51f91-111">配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="51f91-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="51f91-112">启用已加入域的 Windows 计算机的自动设备注册</span><span class="sxs-lookup"><span data-stu-id="51f91-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="51f91-113">配置 Azure AD 密码保护</span><span class="sxs-lookup"><span data-stu-id="51f91-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="51f91-114">启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="51f91-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="51f91-115">为 Exchange Online 和 Skype for Business Online 启用新式身份验证</span><span class="sxs-lookup"><span data-stu-id="51f91-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="51f91-116">阶段 1：构建轻量级的 Microsoft 365 测试环境</span><span class="sxs-lookup"><span data-stu-id="51f91-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="51f91-117">按照[轻量级基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="51f91-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="51f91-118">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="51f91-118">Here is the resulting configuration.</span></span>

![轻量级 Microsoft 365 企业版测试环境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="51f91-120">阶段 2：配置命名位置</span><span class="sxs-lookup"><span data-stu-id="51f91-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="51f91-121">首先，确定组织使用的公共 IP 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="51f91-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="51f91-122">接下来，按照[在 Azure Active Directory 中配置命名位置](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的说明将地址或地址范围添加为命名位置。</span><span class="sxs-lookup"><span data-stu-id="51f91-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="51f91-123">阶段 3：配置自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="51f91-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="51f91-124">接下来，按照[“密码重置”测试实验室指南的阶段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="51f91-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="51f91-125">为特定 Azure AD 组中的帐户启用密码重置时，请将这些帐户添加到 **密码重置** 组：</span><span class="sxs-lookup"><span data-stu-id="51f91-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="51f91-126">用户 2</span><span class="sxs-lookup"><span data-stu-id="51f91-126">User 2</span></span>
- <span data-ttu-id="51f91-127">用户 3</span><span class="sxs-lookup"><span data-stu-id="51f91-127">User 3</span></span>
- <span data-ttu-id="51f91-128">用户 4</span><span class="sxs-lookup"><span data-stu-id="51f91-128">User 4</span></span>
- <span data-ttu-id="51f91-129">用户 5</span><span class="sxs-lookup"><span data-stu-id="51f91-129">User 5</span></span>

<span data-ttu-id="51f91-130">仅为用户 2 帐户测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="51f91-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="51f91-131">阶段 4：配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="51f91-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="51f91-132">按照以下用户帐户的[“多重身份验证”测试实验室指南的阶段 2 ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)中的说明操作：</span><span class="sxs-lookup"><span data-stu-id="51f91-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="51f91-133">用户 2</span><span class="sxs-lookup"><span data-stu-id="51f91-133">User 2</span></span>
- <span data-ttu-id="51f91-134">用户 3</span><span class="sxs-lookup"><span data-stu-id="51f91-134">User 3</span></span>
- <span data-ttu-id="51f91-135">用户 4</span><span class="sxs-lookup"><span data-stu-id="51f91-135">User 4</span></span>
- <span data-ttu-id="51f91-136">用户 5</span><span class="sxs-lookup"><span data-stu-id="51f91-136">User 5</span></span>

<span data-ttu-id="51f91-137">仅为用户 2 帐户测试多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="51f91-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="51f91-138">阶段 5：启用已加入域的 Windows 计算机的自动设备注册</span><span class="sxs-lookup"><span data-stu-id="51f91-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="51f91-139">按照 [以下说明](/azure/active-directory/devices/hybrid-azuread-join-plan) 启用已加入域的 Windows 计算机的自动设备注册。</span><span class="sxs-lookup"><span data-stu-id="51f91-139">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="51f91-140">阶段 6：配置 Azure AD 密码保护</span><span class="sxs-lookup"><span data-stu-id="51f91-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="51f91-141">按照 [以下说明](/azure/active-directory/authentication/concept-password-ban-bad) 阻止已知的弱密码及其变体。</span><span class="sxs-lookup"><span data-stu-id="51f91-141">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="51f91-142">阶段 7：启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="51f91-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="51f91-143">按照[“Azure AD Identity Protection”测试实验室指南的阶段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="51f91-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="51f91-144">阶段 8：启用 Exchange Online 和 Skype for Business Online 的新式身份验证</span><span class="sxs-lookup"><span data-stu-id="51f91-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="51f91-145">对于 Exchange Online，请按照[这些说明](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)操作。</span><span class="sxs-lookup"><span data-stu-id="51f91-145">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="51f91-146">对于 Skype for Business Online：</span><span class="sxs-lookup"><span data-stu-id="51f91-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="51f91-147">连接到 [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="51f91-147">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="51f91-148">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="51f91-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="51f91-149">使用此命令验证更改是否成功。</span><span class="sxs-lookup"><span data-stu-id="51f91-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="51f91-150">结果是测试环境满足标识和设备访问的仅云 [先决条件](../security/office-365-security/identity-access-prerequisites.md#prerequisites) 配置的要求。</span><span class="sxs-lookup"><span data-stu-id="51f91-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="51f91-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="51f91-151">Next step</span></span>

<span data-ttu-id="51f91-152">使用[常见标识和设备访问策略](../security/office-365-security/identity-access-policies.md)配置基于这些先决条件构建的策略并保护标识和设备。</span><span class="sxs-lookup"><span data-stu-id="51f91-152">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="51f91-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51f91-153">See also</span></span>

[<span data-ttu-id="51f91-154">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="51f91-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="51f91-155">标识路线图</span><span class="sxs-lookup"><span data-stu-id="51f91-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="51f91-156">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="51f91-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="51f91-157">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="51f91-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="51f91-158">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="51f91-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)