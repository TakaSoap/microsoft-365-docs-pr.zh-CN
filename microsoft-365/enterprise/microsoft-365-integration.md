---
title: Microsoft 365与本地环境集成
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: 本文将了解如何将Microsoft 365目录服务和本地环境集成。
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923962"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="89985-103">Microsoft 365与本地环境集成</span><span class="sxs-lookup"><span data-stu-id="89985-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="89985-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="89985-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="89985-105">您可以将 Microsoft 365 与现有本地 Active Directory 域服务 (AD DS) 以及 Exchange Server、Skype for Business Server 2015 或 SharePoint Server 本地安装集成。</span><span class="sxs-lookup"><span data-stu-id="89985-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="89985-106">集成 AD DS 时，可以同步和管理两种环境的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="89985-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="89985-107">您还可以将密码哈希同步 (PHS) 或单一登录 (SSO) 以便用户可以使用其本地凭据登录到这两个环境。</span><span class="sxs-lookup"><span data-stu-id="89985-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="89985-108">与本地服务器产品集成时，将创建混合环境。</span><span class="sxs-lookup"><span data-stu-id="89985-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="89985-109">混合环境可以帮助你将用户或信息迁移到 Microsoft 365，或者你可以继续拥有一些用户或本地的一些信息，还有一些信息位于云中。</span><span class="sxs-lookup"><span data-stu-id="89985-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="89985-110">有关混合环境详细信息，请参阅 [混合云](../solutions/cloud-architecture-models.md#hybrid)。</span><span class="sxs-lookup"><span data-stu-id="89985-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="89985-111">此外，还可使用 Azure Active Directory (Azure AD) 顾问，在 Microsoft 365 管理中心中 (你必须登录到 Microsoft 365) ：</span><span class="sxs-lookup"><span data-stu-id="89985-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="89985-112">Azure AD 设置指南</span><span class="sxs-lookup"><span data-stu-id="89985-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="89985-113">从组织目录中同步用户</span><span class="sxs-lookup"><span data-stu-id="89985-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="89985-114">Active Directory 联合身份验证服务 (AD FS) 顾问</span><span class="sxs-lookup"><span data-stu-id="89985-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="89985-115">开始之前</span><span class="sxs-lookup"><span data-stu-id="89985-115">Before you begin</span></span>

<span data-ttu-id="89985-116">在集成Microsoft 365和本地环境之前，还需要执行[网络规划和性能调整](network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="89985-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="89985-117">你还需要了解可用的 [标识模型](about-microsoft-365-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="89985-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="89985-118">有关[可用于Microsoft 365](manage-microsoft-365-accounts.md)用户帐户的工具列表，请参阅管理Microsoft 365帐户。</span><span class="sxs-lookup"><span data-stu-id="89985-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="89985-119">将Microsoft 365 AD DS 集成</span><span class="sxs-lookup"><span data-stu-id="89985-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="89985-120">如果 AD DS 中已有用户帐户，则不希望在 Microsoft 365 中重新创建所有这些帐户，并且存在在环境之间引入差异或错误的风险。</span><span class="sxs-lookup"><span data-stu-id="89985-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="89985-121">目录同步可帮助你在内部部署和联机环境之间镜像这些帐户。</span><span class="sxs-lookup"><span data-stu-id="89985-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="89985-122">使用目录同步，用户不必记住每个环境的新信息，也不必创建或更新帐户两次。</span><span class="sxs-lookup"><span data-stu-id="89985-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="89985-123">您需要准备 [本地目录进行](prepare-for-directory-synchronization.md) 目录同步。</span><span class="sxs-lookup"><span data-stu-id="89985-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![使用目录同步使本地和联机用户帐户信息保持同步](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="89985-125">如果希望用户能够使用本地凭据Microsoft 365登录，还可以配置 SSO。</span><span class="sxs-lookup"><span data-stu-id="89985-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="89985-126">使用 SSO，Microsoft 365配置为信任本地环境进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="89985-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![使用单一登录，可在本地和联机环境中使用同一帐户](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="89985-128">包含或不带密码哈希同步的目录同步或 PTA (传递) </span><span class="sxs-lookup"><span data-stu-id="89985-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="89985-129">用户使用其用户帐户登录本地环境， (域\用户名) 。</span><span class="sxs-lookup"><span data-stu-id="89985-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="89985-130">当他们转到Microsoft 365时，必须使用工作或学校帐户登录 (user@domain.com) 。</span><span class="sxs-lookup"><span data-stu-id="89985-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="89985-131">用户名在这两种环境中是相同的。</span><span class="sxs-lookup"><span data-stu-id="89985-131">The user name is the same in both environments.</span></span> <span data-ttu-id="89985-132">当你添加 PHS 或 PTA 时，用户对两个环境具有相同的密码，但在登录到 MICROSOFT 365 时，必须再次提供这些Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="89985-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="89985-133">与 PHS 的目录同步是最常用的目录同步。</span><span class="sxs-lookup"><span data-stu-id="89985-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="89985-134">若要设置目录同步，请使用 Azure AD 连接。</span><span class="sxs-lookup"><span data-stu-id="89985-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="89985-135">有关说明，请参阅使用快速设置 为[Microsoft 365](set-up-directory-synchronization.md) [和 Azure AD 连接设置目录同步](/azure/active-directory/hybrid/how-to-connect-install-express)。</span><span class="sxs-lookup"><span data-stu-id="89985-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="89985-136">了解有关准备[与目录同步Microsoft 365。](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="89985-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="89985-137">与 SSO 的目录同步</span><span class="sxs-lookup"><span data-stu-id="89985-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="89985-138">用户使用其用户帐户登录到其本地环境。</span><span class="sxs-lookup"><span data-stu-id="89985-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="89985-139">当他们转到Microsoft 365时，他们要么自动登录，要么使用用于本地环境的相同凭据登录 (域\用户名) 。</span><span class="sxs-lookup"><span data-stu-id="89985-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="89985-140">若要设置 SSO，你还可使用 Azure AD 连接。</span><span class="sxs-lookup"><span data-stu-id="89985-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="89985-141">有关说明，请参阅[Azure AD 连接 的自定义安装](/azure/active-directory/hybrid/how-to-connect-install-custom)。</span><span class="sxs-lookup"><span data-stu-id="89985-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="89985-142">有关详细信息，请参阅 [单一登录](/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="89985-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="89985-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="89985-143">Azure AD Connect</span></span>

<span data-ttu-id="89985-144">Azure AD 连接替代了旧版标识集成工具，如 DirSync 和 Azure AD Sync。如果你想要从 Azure Active Directory 同步到 Azure AD 连接，请参阅[升级说明](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started)。</span><span class="sxs-lookup"><span data-stu-id="89985-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="89985-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89985-145">See also</span></span>

[<span data-ttu-id="89985-146">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="89985-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)