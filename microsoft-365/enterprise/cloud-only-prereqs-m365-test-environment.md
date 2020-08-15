---
title: Microsoft 365 测试环境中仅限云的标识和设备访问先决条件
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况，其中内附仅限云的身份验证的先决条件。
ms.openlocfilehash: a8025a2543a53a229be13d19c246165fe88ad433
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685780"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="78011-103">Microsoft 365 测试环境中仅限云的标识和设备访问先决条件</span><span class="sxs-lookup"><span data-stu-id="78011-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="78011-104">*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="78011-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="78011-105">[标识和设备访问配置](microsoft-365-policies-configurations.md) 是一组配置和条件访问策略，用于保护与 Azure Active Directory (azure AD) 集成的所有服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="78011-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="78011-106">本文介绍了如何配置 Microsoft 365 测试环境，使其满足标识和设备访问[仅限云的先决条件配置](identity-access-prerequisites.md#prerequisites)的要求。</span><span class="sxs-lookup"><span data-stu-id="78011-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="78011-107">此测试环境的设置分为下面 7 个阶段：</span><span class="sxs-lookup"><span data-stu-id="78011-107">There are seven phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="78011-108">构建轻量级测试环境</span><span class="sxs-lookup"><span data-stu-id="78011-108">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="78011-109">配置命名位置</span><span class="sxs-lookup"><span data-stu-id="78011-109">Configure named locations</span></span>
3.  <span data-ttu-id="78011-110">配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="78011-110">Configure password writeback</span></span>
4.  <span data-ttu-id="78011-111">配置自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="78011-111">Configure self-service password resets</span></span>
5.  <span data-ttu-id="78011-112">配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="78011-112">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="78011-113">启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="78011-113">Enable Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="78011-114">为 Exchange Online 和 Skype for Business Online 启用新式身份验证</span><span class="sxs-lookup"><span data-stu-id="78011-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="78011-115">阶段 1：构建轻量级的 Microsoft 365 测试环境</span><span class="sxs-lookup"><span data-stu-id="78011-115">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="78011-116">按照[轻量级基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="78011-116">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="78011-117">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="78011-117">Here is the resulting configuration.</span></span>

![轻量级 Microsoft 365 企业版测试环境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="78011-119">阶段 2：配置命名位置</span><span class="sxs-lookup"><span data-stu-id="78011-119">Phase 2: Configure named locations</span></span>

<span data-ttu-id="78011-120">首先，确定组织使用的公共 IP 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="78011-120">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="78011-121">接下来，按照[在 Azure Active Directory 中配置命名位置](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的说明将地址或地址范围添加为命名位置。</span><span class="sxs-lookup"><span data-stu-id="78011-121">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="78011-122">阶段 3：配置密码写回服务</span><span class="sxs-lookup"><span data-stu-id="78011-122">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="78011-123">接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="78011-123">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="78011-124">阶段 4：配置自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="78011-124">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="78011-125">接下来，按照[“密码重置”测试实验室指南的阶段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="78011-125">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="78011-126">为特定 Azure AD 组中的帐户启用密码重置时，请将这些帐户添加到**密码重置**组：</span><span class="sxs-lookup"><span data-stu-id="78011-126">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="78011-127">用户 2</span><span class="sxs-lookup"><span data-stu-id="78011-127">User 2</span></span>
- <span data-ttu-id="78011-128">用户 3</span><span class="sxs-lookup"><span data-stu-id="78011-128">User 3</span></span>
- <span data-ttu-id="78011-129">用户 4</span><span class="sxs-lookup"><span data-stu-id="78011-129">User 4</span></span>
- <span data-ttu-id="78011-130">用户 5</span><span class="sxs-lookup"><span data-stu-id="78011-130">User 5</span></span>

<span data-ttu-id="78011-131">仅为用户 2 帐户测试密码重置。</span><span class="sxs-lookup"><span data-stu-id="78011-131">Test password reset only for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="78011-132">阶段 5：配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="78011-132">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="78011-133">按照以下用户帐户的[“多重身份验证”测试实验室指南的阶段 2 ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)中的说明操作：</span><span class="sxs-lookup"><span data-stu-id="78011-133">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="78011-134">用户 2</span><span class="sxs-lookup"><span data-stu-id="78011-134">User 2</span></span>
- <span data-ttu-id="78011-135">用户 3</span><span class="sxs-lookup"><span data-stu-id="78011-135">User 3</span></span>
- <span data-ttu-id="78011-136">用户 4</span><span class="sxs-lookup"><span data-stu-id="78011-136">User 4</span></span>
- <span data-ttu-id="78011-137">用户 5</span><span class="sxs-lookup"><span data-stu-id="78011-137">User 5</span></span>

<span data-ttu-id="78011-138">仅为用户 2 帐户测试多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="78011-138">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="78011-139">阶段 6：启用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="78011-139">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="78011-140">按照[“Azure AD Identity Protection”测试实验室指南的阶段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="78011-140">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="78011-141">阶段 7：为 Exchange Online 和 Skype for Business Online 启用新式身份验证</span><span class="sxs-lookup"><span data-stu-id="78011-141">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="78011-142">对于 Exchange Online，请按照[这些说明](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)操作。</span><span class="sxs-lookup"><span data-stu-id="78011-142">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="78011-143">对于 Skype for Business Online：</span><span class="sxs-lookup"><span data-stu-id="78011-143">For Skype for Business Online:</span></span>

1. <span data-ttu-id="78011-144">连接到 [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="78011-144">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="78011-145">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="78011-145">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="78011-146">使用此命令验证更改是否成功。</span><span class="sxs-lookup"><span data-stu-id="78011-146">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="78011-147">结果是一个测试环境，它满足标识和设备访问[仅限云的先决条件配置](identity-access-prerequisites.md#prerequisites)的要求。</span><span class="sxs-lookup"><span data-stu-id="78011-147">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="78011-148">下一步</span><span class="sxs-lookup"><span data-stu-id="78011-148">Next step</span></span>

<span data-ttu-id="78011-149">使用[常见标识和设备访问策略](identity-access-policies.md)配置基于这些先决条件构建的策略并保护标识和设备。</span><span class="sxs-lookup"><span data-stu-id="78011-149">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="78011-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78011-150">See also</span></span>

[<span data-ttu-id="78011-151">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="78011-151">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="78011-152">标识路线图</span><span class="sxs-lookup"><span data-stu-id="78011-152">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="78011-153">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="78011-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="78011-154">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="78011-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="78011-155">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="78011-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
