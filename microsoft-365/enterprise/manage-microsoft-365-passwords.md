---
title: 管理 Microsoft 365 用户帐户密码
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 了解如何管理 Microsoft 365 用户帐户密码。
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905088"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="b5918-103">管理 Microsoft 365 用户帐户密码</span><span class="sxs-lookup"><span data-stu-id="b5918-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="b5918-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="b5918-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b5918-105">可以通过几种不同的方式管理 Microsoft 365 用户帐户密码，具体取决于标识配置。</span><span class="sxs-lookup"><span data-stu-id="b5918-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="b5918-106">可以在 [Microsoft 365](../admin/add-users/index.yml)管理中心、Active Directory 域服务 (AD DS) 或 Azure Active Directory (Azure AD) 管理中心管理用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b5918-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="b5918-107">规划管理用户帐户密码的去向和方式</span><span class="sxs-lookup"><span data-stu-id="b5918-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="b5918-108">在哪里以及如何管理用户帐户取决于你要用于 Microsoft 365 的标识模型。</span><span class="sxs-lookup"><span data-stu-id="b5918-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="b5918-109">这两种模型是仅云模型和混合模型。</span><span class="sxs-lookup"><span data-stu-id="b5918-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="b5918-110">仅限云</span><span class="sxs-lookup"><span data-stu-id="b5918-110">Cloud-only</span></span>

<span data-ttu-id="b5918-111">在中管理用户帐户密码：</span><span class="sxs-lookup"><span data-stu-id="b5918-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="b5918-112">Microsoft 365 管理员中心</span><span class="sxs-lookup"><span data-stu-id="b5918-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- <span data-ttu-id="b5918-113">Azure AD 管理中心</span><span class="sxs-lookup"><span data-stu-id="b5918-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="b5918-114">混合</span><span class="sxs-lookup"><span data-stu-id="b5918-114">Hybrid</span></span>

<span data-ttu-id="b5918-115">使用混合标识，密码存储在 AD DS 中，因此必须使用本地 AD DS 工具管理用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="b5918-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="b5918-116">即使使用密码哈希同步 (PHS) （其中 Azure AD 在 AD DS 中存储已哈希版本的哈希版本）时，你和用户也必须在 AD DS 中管理其密码。</span><span class="sxs-lookup"><span data-stu-id="b5918-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="b5918-117">使用 [密码写回](#pw_writeback)，你的用户可以通过 Azure AD 更改其 AD DS 密码。</span><span class="sxs-lookup"><span data-stu-id="b5918-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="b5918-118">防止密码错误</span><span class="sxs-lookup"><span data-stu-id="b5918-118">Prevent bad passwords</span></span>

<span data-ttu-id="b5918-119">所有用户都应使用 [Microsoft 的密码指南](https://www.microsoft.com/research/publication/password-guidance)来创建用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="b5918-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="b5918-120">若要防止用户创建易于确定的密码，请使用 Azure AD 密码保护，该功能同时使用全局阻止密码列表和你指定的可选的自定义禁止密码列表。</span><span class="sxs-lookup"><span data-stu-id="b5918-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="b5918-121">例如，你可以指定特定于贵组织的术语，例如：</span><span class="sxs-lookup"><span data-stu-id="b5918-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="b5918-122">品牌名称</span><span class="sxs-lookup"><span data-stu-id="b5918-122">Brand names</span></span>
- <span data-ttu-id="b5918-123">产品名称</span><span class="sxs-lookup"><span data-stu-id="b5918-123">Product names</span></span>
- <span data-ttu-id="b5918-124">位置（例如公司总部）</span><span class="sxs-lookup"><span data-stu-id="b5918-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="b5918-125">特定于公司的内部条款</span><span class="sxs-lookup"><span data-stu-id="b5918-125">Company-specific internal terms</span></span>
- <span data-ttu-id="b5918-126">具有特定公司含义的缩写</span><span class="sxs-lookup"><span data-stu-id="b5918-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="b5918-127">你可以禁止云 [中和](/azure/active-directory/authentication/concept-password-ban-bad) 本地 [AD DS 中的错误密码](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)。</span><span class="sxs-lookup"><span data-stu-id="b5918-127">You can ban bad passwords [in the cloud](/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="b5918-128">简化用户登录</span><span class="sxs-lookup"><span data-stu-id="b5918-128">Simplify user sign-in</span></span>

<span data-ttu-id="b5918-129">Azure AD 无缝单一 Sign-On (Azure AD 无缝 SSO) 可与 PHS 和 Pass-Through 身份验证 (PTA) 一起运行，以允许你的用户登录到使用 Azure AD 用户帐户的服务，而无需键入其密码，在许多情况下，也无需键入其用户名。</span><span class="sxs-lookup"><span data-stu-id="b5918-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="b5918-130">这可使用户更方便地访问基于云的应用程序（如 Office 365）而无需任何额外的本地组件（如联合身份验证服务器）。</span><span class="sxs-lookup"><span data-stu-id="b5918-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="b5918-131">将使用 Azure AD Connect 工具配置 Azure AD 无缝 SSO。</span><span class="sxs-lookup"><span data-stu-id="b5918-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="b5918-132">请参阅[配置 Azure AD 无缝 SSO 说明](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。</span><span class="sxs-lookup"><span data-stu-id="b5918-132">See the [instructions to configure Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="b5918-133">简化 AD DS 的密码更新</span><span class="sxs-lookup"><span data-stu-id="b5918-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="b5918-134">通过密码写回，你可以允许用户通过 Azure AD 重置其密码，然后复制到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="b5918-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="b5918-135">用户无需访问其本地 AD DS 来更新其密码。</span><span class="sxs-lookup"><span data-stu-id="b5918-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="b5918-136">这非常适用于对本地网络没有远程访问连接的漫游或远程用户。</span><span class="sxs-lookup"><span data-stu-id="b5918-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="b5918-137">需要密码写回才可充分利用 Azure AD 标识保护功能，例如，当检测到高风险的帐户泄露时要求用户更改其本地密码。</span><span class="sxs-lookup"><span data-stu-id="b5918-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="b5918-138">有关其他信息和配置说明，请参阅 [Azure AD SSPR 密码写回](/azure/active-directory/active-directory-passwords-writeback)。</span><span class="sxs-lookup"><span data-stu-id="b5918-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="b5918-p108">升级到最新版本的 Azure AD Connect，以确保即时获取最佳体验和新功能。有关详细信息，请参阅 [Azure AD Connect 自定义安装](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。</span><span class="sxs-lookup"><span data-stu-id="b5918-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="b5918-141">简化密码重置</span><span class="sxs-lookup"><span data-stu-id="b5918-141">Simplify password resets</span></span>

<span data-ttu-id="b5918-142">SSPR (自助服务密码重置) 允许用户重置或解锁其密码或帐户。</span><span class="sxs-lookup"><span data-stu-id="b5918-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="b5918-143">为提醒你避免误用或滥用，可以使用详细报告，跟踪用户访问系统的时间，并进行通知。</span><span class="sxs-lookup"><span data-stu-id="b5918-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="b5918-144">必须先启用 [密码写回](#pw_writeback) ，然后才能部署密码重置。</span><span class="sxs-lookup"><span data-stu-id="b5918-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="b5918-145">请参阅[推出密码重置说明](/azure/active-directory/authentication/howto-sspr-deployment)。</span><span class="sxs-lookup"><span data-stu-id="b5918-145">See the [instructions to roll out password reset](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>