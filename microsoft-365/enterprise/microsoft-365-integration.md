---
title: Microsoft 365 与本地环境的集成
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
description: 在本文中，我们将了解如何将 Microsoft 365 与您现有的目录服务和本地环境集成。
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384883"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="8b75c-103">Microsoft 365 与本地环境的集成</span><span class="sxs-lookup"><span data-stu-id="8b75c-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="8b75c-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="8b75c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8b75c-105">可以将 Microsoft 365 与现有的本地 Active Directory 域服务集成 (AD DS) 以及 Exchange Server 的本地安装、Skype for Business Server 2015 或 SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="8b75c-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="8b75c-106">在集成 AD DS 时，您可以同步和管理这两个环境的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8b75c-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="8b75c-107">您还可以 (PHS) 或单一登录 (SSO) 添加密码哈希同步，以便用户可以使用其本地凭据登录到这两个环境。</span><span class="sxs-lookup"><span data-stu-id="8b75c-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="8b75c-108">当您与本地服务器产品集成时，将创建混合环境。</span><span class="sxs-lookup"><span data-stu-id="8b75c-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="8b75c-109">当您将用户或信息迁移到 Microsoft 365 时，混合环境可帮助您，也可以继续在本地使用某些用户或某些信息以及在云中使用一些信息。</span><span class="sxs-lookup"><span data-stu-id="8b75c-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="8b75c-110">有关混合环境的详细信息，请参阅 [混合云](../solutions/cloud-architecture-models.md#hybrid)。</span><span class="sxs-lookup"><span data-stu-id="8b75c-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="8b75c-111">您还可以在 Microsoft 365 管理中心中使用 Azure Active Directory (Azure AD) 顾问获取自定义设置指南 (您必须登录到 Microsoft 365) ：</span><span class="sxs-lookup"><span data-stu-id="8b75c-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="8b75c-112">Azure AD 安装指南</span><span class="sxs-lookup"><span data-stu-id="8b75c-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="8b75c-113">从你的组织的目录同步用户</span><span class="sxs-lookup"><span data-stu-id="8b75c-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="8b75c-114">Active Directory 联合身份验证服务 (AD FS) 部署顾问</span><span class="sxs-lookup"><span data-stu-id="8b75c-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="8b75c-115">准备工作</span><span class="sxs-lookup"><span data-stu-id="8b75c-115">Before you begin</span></span>

<span data-ttu-id="8b75c-116">在集成 Microsoft 365 和本地环境之前，还需要进行 [网络规划和性能调整](network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="8b75c-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="8b75c-117">您还需要了解可用的 [标识模型](about-microsoft-365-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="8b75c-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="8b75c-118">有关可用于管理 Microsoft 365 用户帐户的工具列表，请参阅 [管理 microsoft 365 帐户](manage-microsoft-365-accounts.md) 。</span><span class="sxs-lookup"><span data-stu-id="8b75c-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="8b75c-119">将 Microsoft 365 与 AD DS 集成</span><span class="sxs-lookup"><span data-stu-id="8b75c-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="8b75c-120">如果您在 AD DS 中有现有的用户帐户，则不需要在 Microsoft 365 中重新创建所有这些帐户，并且在环境之间引入差异或错误的风险。</span><span class="sxs-lookup"><span data-stu-id="8b75c-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="8b75c-121">目录同步可帮助您在本地和联机环境中镜像这些帐户。</span><span class="sxs-lookup"><span data-stu-id="8b75c-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="8b75c-122">通过目录同步，用户不必记住每个环境的新信息，也不必创建或更新帐户两次。</span><span class="sxs-lookup"><span data-stu-id="8b75c-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="8b75c-123">你将需要为 [本地目录准备](prepare-for-directory-synchronization.md) 目录同步。</span><span class="sxs-lookup"><span data-stu-id="8b75c-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![使用目录同步将本地和联机用户帐户信息保持同步](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="8b75c-125">如果您希望用户能够使用他们的本地凭据登录到 Microsoft 365，您还可以配置 SSO。</span><span class="sxs-lookup"><span data-stu-id="8b75c-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="8b75c-126">使用 SSO，Microsoft 365 配置为信任本地环境以进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="8b75c-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![使用单一登录，在本地和联机环境中都可以使用相同的帐户。](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="8b75c-128">使用或不使用密码哈希同步或不 (PTA 的传递身份验证的目录同步) </span><span class="sxs-lookup"><span data-stu-id="8b75c-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="8b75c-129">用户使用其用户帐户登录到本地环境， (域 \ 用户名) 。</span><span class="sxs-lookup"><span data-stu-id="8b75c-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="8b75c-130">当他们转到 Microsoft 365 时，他们必须使用其工作或学校帐户 (user@domain.com) 重新登录。</span><span class="sxs-lookup"><span data-stu-id="8b75c-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="8b75c-131">这两个环境中的用户名相同。</span><span class="sxs-lookup"><span data-stu-id="8b75c-131">The user name is the same in both environments.</span></span> <span data-ttu-id="8b75c-132">当您添加 PHS 或 PTA 时，用户对这两个环境都具有相同的密码，但在登录到 Microsoft 365 时将不得不再次提供这些凭据。</span><span class="sxs-lookup"><span data-stu-id="8b75c-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="8b75c-133">使用 PHS 的目录同步是最常用的目录同步。</span><span class="sxs-lookup"><span data-stu-id="8b75c-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="8b75c-134">若要设置目录同步，请使用 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="8b75c-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="8b75c-135">有关说明，请参阅 [Set up directory 同步 For Microsoft 365](set-up-directory-synchronization.md) 和 [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537)。</span><span class="sxs-lookup"><span data-stu-id="8b75c-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="8b75c-136">了解有关 [准备将目录同步到 Microsoft 365 的](prepare-for-directory-synchronization.md)详细信息。</span><span class="sxs-lookup"><span data-stu-id="8b75c-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="8b75c-137">使用 SSO 同步目录</span><span class="sxs-lookup"><span data-stu-id="8b75c-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="8b75c-138">用户使用其用户帐户登录到本地环境。</span><span class="sxs-lookup"><span data-stu-id="8b75c-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="8b75c-139">当他们转到 Microsoft 365 时，它们要么是自动登录，要么是使用它们在本地环境中使用的相同凭据登录 (域 \ 用户名) 。</span><span class="sxs-lookup"><span data-stu-id="8b75c-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="8b75c-140">若要设置 SSO，您还可以使用 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="8b75c-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="8b75c-141">有关说明，请参阅 [自定义安装的 AZURE AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430)。</span><span class="sxs-lookup"><span data-stu-id="8b75c-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="8b75c-142">有关详细信息，请参阅 [单一登录](https://go.microsoft.com/fwlink/p/?LinkId=698604)。</span><span class="sxs-lookup"><span data-stu-id="8b75c-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="8b75c-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="8b75c-143">Azure AD Connect</span></span>

<span data-ttu-id="8b75c-144">Azure AD Connect 替代了较早版本的身份集成工具，如 DirSync 和 Azure AD 同步。如果要从 Azure Active Directory 同步更新到 Azure AD Connect，请参阅 [升级说明](https://go.microsoft.com/fwlink/p/?LinkId=733240)。</span><span class="sxs-lookup"><span data-stu-id="8b75c-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="8b75c-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b75c-145">See also</span></span>

[<span data-ttu-id="8b75c-146">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="8b75c-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
