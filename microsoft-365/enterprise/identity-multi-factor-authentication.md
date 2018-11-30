---
title: 第 5 步：设置多重身份验证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并为用户帐户配置多重身份验证。
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865883"
---
# <a name="step-5-set-up-multi-factor-authentication"></a><span data-ttu-id="a7ba6-103">第 5 步：设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="a7ba6-103">Step 5: Set up multi-factor authentication</span></span>

<span data-ttu-id="a7ba6-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="a7ba6-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="a7ba6-p101">在此步骤中，你将设置多重身份验证 (MFA)，以将第二层安全添加到用户登录和交易。用户正确输入其密码后，MFA 需要其他验证方法。如果没有 MFA，密码就是唯一的验证方法。密码的问题是许多密码容易被攻击者猜出，或者在不知情的情况共享给不受信任方。</span><span class="sxs-lookup"><span data-stu-id="a7ba6-p101">In Step 7, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="a7ba6-109">使用 MFA，第二层安全可以是：</span><span class="sxs-lookup"><span data-stu-id="a7ba6-109">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="a7ba6-110">不易被欺骗或者复制的个人和受信任设备，如智能手机。</span><span class="sxs-lookup"><span data-stu-id="a7ba6-110">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="a7ba6-111">生物识别属性，如指纹。</span><span class="sxs-lookup"><span data-stu-id="a7ba6-111">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="a7ba6-p102">将基于每个用户帐户启用 MFA 并配置辅助身份验证方法。请确保用户知道已启用 MFA，以便他们理解（如强制使用智能手机进行登录）要求并可以成功登录。</span><span class="sxs-lookup"><span data-stu-id="a7ba6-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements (such as mandatory use of a smart phone to sign in) and can sign in successfully.</span></span>

<span data-ttu-id="a7ba6-114">有关详细信息，请参阅 [Office 365 部署的多重身份验证计划](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)。</span><span class="sxs-lookup"><span data-stu-id="a7ba6-114">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span></span>

<span data-ttu-id="a7ba6-115">若要配置多重身份验证，[为 Office 365 用户设置多重身份验证](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。</span><span class="sxs-lookup"><span data-stu-id="a7ba6-115">To configure multifactor authentication, [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

<span data-ttu-id="a7ba6-p103">可以通过条件访问策略要求 MFA。例如，可以配置一个策略，以在身份验证被确定为中级或高级风险时需要 MFA。有关详细信息，请参阅[常见标识和设备访问策略](identity-access-policies.md#require-mfa-based-on-sign-in-risk)。</span><span class="sxs-lookup"><span data-stu-id="a7ba6-p103">You can also require MFA with conditional access policies. For example, you can configure a policy that required MFA when the authentication is determined to be of medium or high risk. For more information, see [Step 2: Configure conditional access policy settings](identity-access-policies.md#require-mfa-based-on-sign-in-risk) in the Information Protection phase.</span></span>

>[!Note]
><span data-ttu-id="a7ba6-p104">在某些应用程序（如 Microsoft Office 2010 或更低版本和 Apple Mail）中，不能使用 MFA。若要使用这些应用，则需要使用“应用密码”代替传统密码。应用密码可使应用绕过 MFA 并继续工作。若要了解有关应用密码的详细信息，请参阅[为 Office 365 创建应用密码](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)。</span><span class="sxs-lookup"><span data-stu-id="a7ba6-p104">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a7ba6-124">测试实验室指南：多重身份验证</span><span class="sxs-lookup"><span data-stu-id="a7ba6-124">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="a7ba6-125">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-mfa)。</span><span class="sxs-lookup"><span data-stu-id="a7ba6-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a7ba6-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a7ba6-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="a7ba6-127">防止凭据泄露</span><span class="sxs-lookup"><span data-stu-id="a7ba6-127">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |

