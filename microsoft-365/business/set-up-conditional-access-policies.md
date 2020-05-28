---
title: 为 Microsoft 365 活动设置条件访问策略
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何设置 Microsoft 365 活动的条件访问策略，以增加额外的安全性。
ms.openlocfilehash: d7c9cfee2ef00e4ebe231a28ccca185c10f53c6b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403010"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="81d96-103">设置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="81d96-103">Set up conditional access policies</span></span>

<span data-ttu-id="81d96-104">[条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)策略添加了实实在在的额外安全性。</span><span class="sxs-lookup"><span data-stu-id="81d96-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="81d96-105">Microsoft 提供一组针对所有客户推荐的基准条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="81d96-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="81d96-106">基准策略是一组预定义策略，可帮助组织抵御多种常见攻击。</span><span class="sxs-lookup"><span data-stu-id="81d96-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="81d96-107">这些常见攻击可能包括密码喷涂、重放和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="81d96-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="81d96-108">这些策略要求管理员和用户在满足特定条件时输入第二种形式的身份验证（称为 "多重身份验证" 或 "MFA"）。</span><span class="sxs-lookup"><span data-stu-id="81d96-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="81d96-109">例如，如果用户从不同的国家/地区登录，则可能会认为登录是危险的，并且用户必须提供另一种形式的身份验证。</span><span class="sxs-lookup"><span data-stu-id="81d96-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="81d96-110">目前，基准策略包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="81d96-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="81d96-111">**要求对管理员** &ndash; 进行 MFA对最有特权的管理员角色（包括全局管理员）要求多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="81d96-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="81d96-112">**最终用户保护** &ndash;仅当登录存在风险时，才需要对用户进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="81d96-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="81d96-113">**阻止旧版身份验证** &ndash;较旧的客户端应用和一些新的应用程序不使用较新的、更安全的身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="81d96-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="81d96-114">这些较旧的应用程序可以绕过条件访问策略，并对您的环境进行未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="81d96-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="81d96-115">此策略阻止来自不支持条件访问的客户端的访问。</span><span class="sxs-lookup"><span data-stu-id="81d96-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="81d96-116">**需要进行服务管理** &ndash; 的 MFA需要多因素身份验证以访问管理工具，包括 Azure 门户（在其中配置基准策略）。</span><span class="sxs-lookup"><span data-stu-id="81d96-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="81d96-117">Microsoft 建议您启用所有这些基准策略。</span><span class="sxs-lookup"><span data-stu-id="81d96-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="81d96-118">启用这些策略后，系统将提示管理员和用户注册 Azure Multii 身份验证。</span><span class="sxs-lookup"><span data-stu-id="81d96-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="81d96-119">有关这些策略的详细信息，请参阅[什么是基准策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？</span><span class="sxs-lookup"><span data-stu-id="81d96-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="81d96-120">设置基准策略</span><span class="sxs-lookup"><span data-stu-id="81d96-120">Set up baseline policies</span></span>

1. <span data-ttu-id="81d96-121">转到 " [azure 门户](https://portal.azure.com)"，然后导航到 " **azure Active Directory** \> **条件访问**"。</span><span class="sxs-lookup"><span data-stu-id="81d96-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="81d96-122">页面上列出了基准策略。</span><span class="sxs-lookup"><span data-stu-id="81d96-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="81d96-123">![列出用于条件访问的基准策略的页面。](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="81d96-123">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="81d96-124">请参阅以下针对每个策略的特定说明：</span><span class="sxs-lookup"><span data-stu-id="81d96-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="81d96-125">要求对管理员进行 MFA</span><span class="sxs-lookup"><span data-stu-id="81d96-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="81d96-126">要求对用户进行 MFA</span><span class="sxs-lookup"><span data-stu-id="81d96-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="81d96-127">阻止传统身份验证</span><span class="sxs-lookup"><span data-stu-id="81d96-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="81d96-128">需要进行服务管理的 MFA</span><span class="sxs-lookup"><span data-stu-id="81d96-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="81d96-129">您可以设置许多其他策略，如要求批准的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="81d96-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="81d96-130">有关详细信息，请参阅[条件访问文档](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="81d96-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
