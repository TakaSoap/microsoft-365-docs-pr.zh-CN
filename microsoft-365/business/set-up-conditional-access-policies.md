---
title: 为 Microsoft 365 活动设置条件访问策略
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何为 Microsoft 365 市场活动设置条件访问策略。
ms.openlocfilehash: dbb5231032d2faef0a7ecb2734226b34290c70bf
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288607"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="c6073-103">设置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="c6073-103">Set up conditional access policies</span></span>

<span data-ttu-id="c6073-104">[条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)策略添加 substancial 其他安全性。</span><span class="sxs-lookup"><span data-stu-id="c6073-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substancial additional security.</span></span> <span data-ttu-id="c6073-105">Microsoft 提供一组针对所有客户推荐的基准条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="c6073-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="c6073-106">基准策略是一组预定义策略，可帮助组织抵御多种常见攻击。</span><span class="sxs-lookup"><span data-stu-id="c6073-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="c6073-107">这些常见攻击可能包括密码喷涂、重放和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="c6073-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="c6073-108">这些策略要求管理员和用户在满足特定条件时输入第二种形式的身份验证（称为 "多重身份验证" 或 "MFA"）。</span><span class="sxs-lookup"><span data-stu-id="c6073-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="c6073-109">例如，如果用户从不同的国家/地区登录，则可能会认为登录是危险的，并且用户必须提供另一种形式的身份验证。</span><span class="sxs-lookup"><span data-stu-id="c6073-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="c6073-110">目前，基准策略包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="c6073-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="c6073-111">**需要对管理员进行 MFA** -对最具特权的管理员角色（包括全局管理员）要求进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="c6073-111">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="c6073-112">**最终用户保护**—仅当登录存在风险时，才需要对用户进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="c6073-112">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="c6073-113">**阻止旧版身份验证**—较旧的客户端应用和一些新的应用程序不使用较新的、更安全的身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="c6073-113">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="c6073-114">这些较旧的应用程序可以绕过条件访问策略，并对您的环境进行未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="c6073-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="c6073-115">此策略阻止来自不支持条件访问的客户端的访问。</span><span class="sxs-lookup"><span data-stu-id="c6073-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="c6073-116">**需要对服务管理进行 MFA** -需要多重身份验证以访问管理工具，包括 Azure 门户（在其中配置基准策略）。</span><span class="sxs-lookup"><span data-stu-id="c6073-116">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="c6073-117">Microsoft 建议您启用所有这些基准策略。</span><span class="sxs-lookup"><span data-stu-id="c6073-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="c6073-118">启用这些策略后，系统将提示管理员和用户注册 Azure Multii 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c6073-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="c6073-119">有关这些策略的详细信息，请参阅[什么是基准策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="c6073-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="c6073-120">设置基准策略</span><span class="sxs-lookup"><span data-stu-id="c6073-120">Set up baseline policies</span></span>

1. <span data-ttu-id="c6073-121">转到 " [azure 门户](https://portal.azure.com)"，然后导航到 " **azure Active Directory** \> **条件访问**"。</span><span class="sxs-lookup"><span data-stu-id="c6073-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="c6073-122">页面上列出了基准策略。</span><span class="sxs-lookup"><span data-stu-id="c6073-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="c6073-123">![列出用于条件访问的基准策略的页面。](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="c6073-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="c6073-124">请参阅以下针对每个策略的特定说明：</span><span class="sxs-lookup"><span data-stu-id="c6073-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="c6073-125">要求对管理员进行 MFA</span><span class="sxs-lookup"><span data-stu-id="c6073-125">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="c6073-126">要求对用户进行 MFA</span><span class="sxs-lookup"><span data-stu-id="c6073-126">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="c6073-127">阻止旧版身份验证</span><span class="sxs-lookup"><span data-stu-id="c6073-127">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="c6073-128">需要进行服务管理的 MFA</span><span class="sxs-lookup"><span data-stu-id="c6073-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="c6073-129">您可以设置许多其他策略，如要求批准的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6073-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="c6073-130">有关详细信息，请参阅[条件访问文档](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="c6073-130">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>