---
title: Microsoft 365 企业版测试实验室指南
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 使用这些测试实验室指南为 Microsoft 365 企业版设置演示、概念验证或开发/测试环境。
ms.openlocfilehash: a006f549d0ac68562faee9c935df7f15161b2f12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909594"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="a8e47-103">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="a8e47-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="a8e47-104">*这同时适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="a8e47-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a8e47-p101">测试实验室指南 (TLG) 可帮助你快速了解 Microsoft 产品。它们提供了用于配置已简化但具有代表性的测试环境的说明性指南。可以在试用版或付费订阅期间使用这些环境进行演示、自定义或创建概念的复杂论证。</span><span class="sxs-lookup"><span data-stu-id="a8e47-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span>

<span data-ttu-id="a8e47-108">TTL 设计为模块化。</span><span class="sxs-lookup"><span data-stu-id="a8e47-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="a8e47-109">它们基于彼此构建，以创建更符合你的学习或测试配置需求的多个配置。</span><span class="sxs-lookup"><span data-stu-id="a8e47-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="a8e47-110">"我亲自构建，它可运行"的动手体验可帮助你了解新产品或方案的部署要求，以便你可以更好地规划在生产中托管它。</span><span class="sxs-lookup"><span data-stu-id="a8e47-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario, so that you can better plan for hosting it in production.</span></span>

<span data-ttu-id="a8e47-111">您还可以使用 TTL 创建具有代表性的环境来开发和测试应用程序，也称为开发/测试环境。</span><span class="sxs-lookup"><span data-stu-id="a8e47-111">You can also use TLGs to create representative environments to develop and test applications, also known as dev/test environments.</span></span>
  
![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="a8e47-113">有关 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观地图，请展开下图或转到 Microsoft [365 企业版测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="a8e47-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, expand the following graphic or go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

<span data-ttu-id="a8e47-114">[![Microsoft 365 企业版测试实验室指南堆栈](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="a8e47-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="a8e47-115">基本配置</span><span class="sxs-lookup"><span data-stu-id="a8e47-115">Base configuration</span></span>

<span data-ttu-id="a8e47-116">首先，为 [Microsoft 365 企业版创建测试环境](/microsoft-365-enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="a8e47-116">First, create a test environment for [Microsoft 365 for enterprise](/microsoft-365-enterprise/).</span></span> <span data-ttu-id="a8e47-117">可以创建两种不同类型的基本配置：</span><span class="sxs-lookup"><span data-stu-id="a8e47-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="a8e47-118">[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md) - 当你想要在仅云环境中配置和演示 Microsoft 365 企业版特性和功能（不包括任何本地组件）时，可使用此配置。</span><span class="sxs-lookup"><span data-stu-id="a8e47-118">[Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="a8e47-119">模拟企业[基础](simulated-ent-base-configuration-microsoft-365-enterprise.md)配置 - 在混合云环境中配置和演示 Microsoft 365 企业版特性和功能时使用此配置，该环境使用 Active Directory 域服务 (AD DS) 域等本地组件。</span><span class="sxs-lookup"><span data-stu-id="a8e47-119">[Simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="a8e47-120">此外，还可通过不将 Microsoft 365 E5 许可证添加到试用版或产品测试环境中，来创建 Office 365 E5 的测试环境。</span><span class="sxs-lookup"><span data-stu-id="a8e47-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="a8e47-121">标识</span><span class="sxs-lookup"><span data-stu-id="a8e47-121">Identity</span></span>

<span data-ttu-id="a8e47-122">若要演示与标识相关的特性和功能，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a8e47-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="a8e47-123">密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="a8e47-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="a8e47-124">启用和测试来自 AD DS 域控制器的基于密码哈希的目录同步。</span><span class="sxs-lookup"><span data-stu-id="a8e47-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="a8e47-125">传递身份验证</span><span class="sxs-lookup"><span data-stu-id="a8e47-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="a8e47-126">启用和测试到 AD DS 域控制器的传递身份验证。</span><span class="sxs-lookup"><span data-stu-id="a8e47-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="a8e47-127">联合身份验证</span><span class="sxs-lookup"><span data-stu-id="a8e47-127">Federated authentication</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   <span data-ttu-id="a8e47-128">启用和测试到 AD DS 域控制器的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="a8e47-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="a8e47-129">Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="a8e47-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="a8e47-130">使用 AD DS 域控制器启用 (Azure AD 无缝单一登录) 无缝 SSO 登录。</span><span class="sxs-lookup"><span data-stu-id="a8e47-130">Enable and test Azure AD Seamless Single Sign-on (Seamless SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="a8e47-131">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="a8e47-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="a8e47-132">为特定用户帐户启用并测试基于智能手机的多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="a8e47-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="a8e47-133">保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="a8e47-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   <span data-ttu-id="a8e47-134">通过条件访问策略锁定全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="a8e47-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="a8e47-135">密码写回</span><span class="sxs-lookup"><span data-stu-id="a8e47-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="a8e47-136">使用密码写回来从 Azure AD 更改 AD DS 用户帐户上的密码。</span><span class="sxs-lookup"><span data-stu-id="a8e47-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="a8e47-137">密码重置</span><span class="sxs-lookup"><span data-stu-id="a8e47-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="a8e47-138">使用自助服务密码重置重置密码。</span><span class="sxs-lookup"><span data-stu-id="a8e47-138">Use self-service password reset to reset your password.</span></span>

- [<span data-ttu-id="a8e47-139">自动许可和组成员身份</span><span class="sxs-lookup"><span data-stu-id="a8e47-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="a8e47-140">借助自动许可和动态组成员身份，使新帐户管理变得前所未有的容易。</span><span class="sxs-lookup"><span data-stu-id="a8e47-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="a8e47-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="a8e47-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="a8e47-142">扫描当前用户帐户以发现漏洞。</span><span class="sxs-lookup"><span data-stu-id="a8e47-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="a8e47-143">标识和设备访问</span><span class="sxs-lookup"><span data-stu-id="a8e47-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="a8e47-144">创建用于测试推荐的标识和设备访问配置以及条件访问策略的环境。</span><span class="sxs-lookup"><span data-stu-id="a8e47-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="a8e47-145">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="a8e47-145">Mobile device management</span></span>

<span data-ttu-id="a8e47-146">若要演示与移动设备管理相关的特性和功能，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a8e47-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="a8e47-147">设备符合性策略</span><span class="sxs-lookup"><span data-stu-id="a8e47-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="a8e47-148">为 Windows 10 设备创建用户组和设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="a8e47-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="a8e47-149">注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="a8e47-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="a8e47-150">注册 iOS 或 Android 设备，并对其进行远程管理。</span><span class="sxs-lookup"><span data-stu-id="a8e47-150">Enroll iOS or Android devices and manage them remotely.</span></span>

## <a name="information-protection"></a><span data-ttu-id="a8e47-151">信息保护</span><span class="sxs-lookup"><span data-stu-id="a8e47-151">Information protection</span></span>

<span data-ttu-id="a8e47-152">若要演示与信息保护相关的特性和功能，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a8e47-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="a8e47-153">增强的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="a8e47-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="a8e47-154">配置可提高 Microsoft 365 安全性的设置，并调查内置安全工具。</span><span class="sxs-lookup"><span data-stu-id="a8e47-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="a8e47-155">数据分类</span><span class="sxs-lookup"><span data-stu-id="a8e47-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="a8e47-156">配置标签，并将标签应用于 SharePoint Online 团队网站中的文档。</span><span class="sxs-lookup"><span data-stu-id="a8e47-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="a8e47-157">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="a8e47-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="a8e47-158">配置 Privileged Access Management，以便实时访问组织中提升的特权任务。</span><span class="sxs-lookup"><span data-stu-id="a8e47-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>