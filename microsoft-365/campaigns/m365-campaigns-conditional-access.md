---
title: 设置条件访问策略
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何要求进行 MFA 并为 Microsoft 365 商业版设置条件访问策略。
ms.openlocfilehash: 570edce03a68dad56c895e2484a5162496d7a3eb
ms.sourcegitcommit: 75b97d1ff617bc4b1b0ef9135dfe6a8842ea1b52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35772539"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="4e1ed-103">需要多重身份验证并设置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="4e1ed-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="4e1ed-104">使用多重身份验证和条件访问策略来保护对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="4e1ed-105">这些都增加了额外的安全性。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-105">These add substantial additional security.</span></span> <span data-ttu-id="4e1ed-106">Microsoft 提供一组针对所有客户推荐的基准条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="4e1ed-107">基准策略是一组预定义策略, 可帮助组织抵御多种常见攻击。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="4e1ed-108">这些常见攻击可能包括密码喷涂、重放和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="4e1ed-109">这些策略要求管理员和用户在满足特定条件时输入第二种形式的身份验证 (称为多重身份验证或 MFA)。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="4e1ed-110">例如, 如果组织中的某个用户尝试从不同的国家/地区或从未知设备登录到 Microsoft 365, 则可能会认为该登录是危险的。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="4e1ed-111">用户必须提供另一种形式的身份验证 (如指纹或代码) 来证明其身份。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="4e1ed-112">目前, 基准策略包括以下各项:</span><span class="sxs-lookup"><span data-stu-id="4e1ed-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="4e1ed-113">在 Microsoft 365 管理中心中设置:</span><span class="sxs-lookup"><span data-stu-id="4e1ed-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="4e1ed-114">**需要对管理员进行 MFA** -对最具特权的管理员角色 (包括全局管理员) 要求进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="4e1ed-115">**最终用户保护**—仅当登录存在风险时, 才需要对用户进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="4e1ed-116">在 Azure Active Directory 门户中设置:</span><span class="sxs-lookup"><span data-stu-id="4e1ed-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="4e1ed-117">**阻止旧版身份验证**—较旧的客户端应用和一些新的应用程序不使用较新的、更安全的身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="4e1ed-118">这些较旧的应用程序可以绕过条件访问策略, 并对您的环境进行未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="4e1ed-119">此策略阻止来自不支持条件访问的客户端的访问。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="4e1ed-120">**需要对服务管理进行 MFA** -需要多重身份验证以访问管理工具, 包括 Azure 门户 (在其中配置基准策略)。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="4e1ed-121">Microsoft 建议您启用所有这些基准策略。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="4e1ed-122">启用这些策略后, 系统将提示管理员和用户注册 Azure 多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="4e1ed-123">有关这些策略的详细信息, 请参阅[什么是基准策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="4e1ed-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="4e1ed-124">需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="4e1ed-124">Require MFA</span></span>

<span data-ttu-id="4e1ed-125">若要要求所有用户使用第二种 ID 登录, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="4e1ed-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="4e1ed-126">转到管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> , 并选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="4e1ed-127">在 "安装程序" 页上, 选择 "**创建登录更安全**的卡片" 中的 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![制作登录更安全的卡。](media/setupmfa.png)
3. <span data-ttu-id="4e1ed-129">在 "使登录更安全" 页上, 选择 "**已启动**"。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="4e1ed-130">在 "加强登录安全" 窗格中, 选中 "**要求对管理员使用多重身份验证**" 旁边的复选框, 并**要求用户注册多重身份验证, 并在检测到风险时阻止访问**。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-130">On the Strengthen sign-in security pane, check the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="4e1ed-131">确保在 "**查找用户**" 框中排除了来自 MFA 要求的[紧急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)或 "中断玻璃" 管理帐户。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![增强 "在安全中的安全" 页。](media/requiremfa.png)

5. <span data-ttu-id="4e1ed-133">在页面底部选择 "**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="4e1ed-134">设置基准策略</span><span class="sxs-lookup"><span data-stu-id="4e1ed-134">Set up baseline policies</span></span>

1. <span data-ttu-id="4e1ed-135">转到 " [azure 门户](https://portal.azure.com)", 然后导航到 " **azure Active Directory** \> **条件访问**"。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="4e1ed-136">基准策略在页面上列出, 您可以看到, 在完成 "[需要 mfa](#require-mfa)" 中的步骤后, "需要对管理员和最终用户进行 mfa" 功能已启用。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-136">The baseline policies are listed on the page, and you can see that Require MFA for admins and End user protection are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![列出用于条件访问的基准策略的页面。](media/casettings.png)
2. <span data-ttu-id="4e1ed-138">请参阅以下针对每个策略的特定说明:</span><span class="sxs-lookup"><span data-stu-id="4e1ed-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="4e1ed-139">要求对管理员进行 MFA</span><span class="sxs-lookup"><span data-stu-id="4e1ed-139">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)

       
    -   [<span data-ttu-id="4e1ed-140">要求对用户进行 MFA</span><span class="sxs-lookup"><span data-stu-id="4e1ed-140">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="4e1ed-141">阻止旧版身份验证</span><span class="sxs-lookup"><span data-stu-id="4e1ed-141">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="4e1ed-142">需要进行服务管理的 MFA</span><span class="sxs-lookup"><span data-stu-id="4e1ed-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="4e1ed-143">您可以设置额外的策略, 如要求批准的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="4e1ed-144">有关详细信息, 请参阅[条件访问文档](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="4e1ed-144">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>
