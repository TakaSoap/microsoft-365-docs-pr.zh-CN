---
title: 设置条件访问策略
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何要求进行 MFA 并为 Microsoft 365 for business 设置条件访问策略。
ms.openlocfilehash: 08a77615d6801eef52465c450c2559a9d786befb
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558270"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="e2866-103">需要多重身份验证并设置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="e2866-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="e2866-104">使用多重身份验证和条件访问策略来保护对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="e2866-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="e2866-105">这些都增加了额外的安全性。</span><span class="sxs-lookup"><span data-stu-id="e2866-105">These add substantial additional security.</span></span> <span data-ttu-id="e2866-106">Microsoft 提供一组针对所有客户推荐的基准条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="e2866-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="e2866-107">基准策略是一组预定义策略，可帮助组织抵御多种常见攻击。</span><span class="sxs-lookup"><span data-stu-id="e2866-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="e2866-108">这些常见攻击可能包括密码喷涂、重放和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="e2866-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="e2866-109">这些策略要求管理员和用户输入第二种形式的身份验证 (称为多重身份验证，或在满足特定条件时进行 MFA) 。</span><span class="sxs-lookup"><span data-stu-id="e2866-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="e2866-110">例如，如果组织中的某个用户尝试从不同的国家/地区或从未知设备登录到 Microsoft 365，则可能会认为该登录是危险的。</span><span class="sxs-lookup"><span data-stu-id="e2866-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="e2866-111">用户必须提供另一种形式的身份验证 (如指纹或代码) ，以证明其身份。</span><span class="sxs-lookup"><span data-stu-id="e2866-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="e2866-112">目前，基准策略包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="e2866-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="e2866-113">在 Microsoft 365 管理中心中设置：</span><span class="sxs-lookup"><span data-stu-id="e2866-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="e2866-114">**需要对管理员进行 MFA** -对最具特权的管理员角色（包括全局管理员）要求进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="e2866-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="e2866-115">**最终用户保护** —仅当登录存在风险时，才需要对用户进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="e2866-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="e2866-116">在 Azure Active Directory 门户中设置：</span><span class="sxs-lookup"><span data-stu-id="e2866-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="e2866-117">**阻止旧版身份验证** —较旧的客户端应用和一些新的应用程序不使用较新的、更安全的身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="e2866-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="e2866-118">这些较旧的应用程序可以绕过条件访问策略，并对您的环境进行未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="e2866-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="e2866-119">此策略阻止来自不支持条件访问的客户端的访问。</span><span class="sxs-lookup"><span data-stu-id="e2866-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="e2866-120">**需要进行服务管理的 MFA** -需要多重身份验证以访问管理工具，包括 Azure 门户 (在其中配置基准策略) 。</span><span class="sxs-lookup"><span data-stu-id="e2866-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="e2866-121">Microsoft 建议您启用所有这些基准策略。</span><span class="sxs-lookup"><span data-stu-id="e2866-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="e2866-122">启用这些策略后，系统将提示管理员和用户注册 Azure AD 多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="e2866-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multi-Factor authentication.</span></span>

<span data-ttu-id="e2866-123">有关这些策略的详细信息，请参阅 [什么是基准策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="e2866-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="e2866-124">需要使用 MFA</span><span class="sxs-lookup"><span data-stu-id="e2866-124">Require MFA</span></span>

<span data-ttu-id="e2866-125">若要要求所有用户使用第二种 ID 登录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2866-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="e2866-126">转到管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ，并选择 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="e2866-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="e2866-127">在 "安装程序" 页上，选择 "**创建登录更安全** 的卡片" 中的 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="e2866-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![制作登录更安全的卡。](../media/setupmfa.png)
3. <span data-ttu-id="e2866-129">在 "使登录更安全" 页上，选择 " **已启动**"。</span><span class="sxs-lookup"><span data-stu-id="e2866-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="e2866-130">在 "加强登录安全" 窗格中，选中 " **要求对管理员启用多重身份验证** " 旁边的复选框，并 **要求用户注册多重身份验证，并在检测到风险时阻止访问**。</span><span class="sxs-lookup"><span data-stu-id="e2866-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="e2866-131">确保在 "**查找用户**" 框中排除了来自 MFA 要求的 [紧急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)或 "中断玻璃" 管理帐户。</span><span class="sxs-lookup"><span data-stu-id="e2866-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![增强 "在安全中的安全" 页。](../media/requiremfa.png)

5. <span data-ttu-id="e2866-133">在页面底部选择 " **创建策略** "。</span><span class="sxs-lookup"><span data-stu-id="e2866-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="e2866-134">设置基准策略</span><span class="sxs-lookup"><span data-stu-id="e2866-134">Set up baseline policies</span></span>

1. <span data-ttu-id="e2866-135">转到 [azure 门户](https://portal.azure.com)，然后导航到 **azure Active Directory** \> **条件访问** 以创建 **新策略**。</span><span class="sxs-lookup"><span data-stu-id="e2866-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="e2866-136">请参阅以下针对每个策略的特定说明：</span><span class="sxs-lookup"><span data-stu-id="e2866-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="e2866-137">要求对管理员进行 MFA</span><span class="sxs-lookup"><span data-stu-id="e2866-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="e2866-138">要求对用户进行 MFA</span><span class="sxs-lookup"><span data-stu-id="e2866-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="e2866-139">阻止传统身份验证</span><span class="sxs-lookup"><span data-stu-id="e2866-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="e2866-140">需要进行服务管理的 MFA</span><span class="sxs-lookup"><span data-stu-id="e2866-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)
    
> [!NOTE]
> <span data-ttu-id="e2866-141">预览策略不再存在，用户将需要创建自己的策略。</span><span class="sxs-lookup"><span data-stu-id="e2866-141">Preview policies no longer exist and users will need to create their own policies.</span></span>


<span data-ttu-id="e2866-142">您可以设置额外的策略，如要求批准的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2866-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="e2866-143">有关详细信息，请参阅 [条件访问文档](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="e2866-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
