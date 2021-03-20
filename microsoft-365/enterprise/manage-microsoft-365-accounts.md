---
title: 管理 Microsoft 365 用户帐户
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
description: 了解如何管理 Microsoft 365 用户帐户。
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909558"
---
# <a name="manage-microsoft-365-user-accounts"></a><span data-ttu-id="bb36d-103">管理 Microsoft 365 用户帐户</span><span class="sxs-lookup"><span data-stu-id="bb36d-103">Manage Microsoft 365 user accounts</span></span>

<span data-ttu-id="bb36d-104">可以通过几种不同的方式管理 Microsoft 365 用户帐户，具体取决于你的配置。</span><span class="sxs-lookup"><span data-stu-id="bb36d-104">You can manage Microsoft 365 user accounts in several different ways, depending on your configuration.</span></span> <span data-ttu-id="bb36d-105">可以在 [Microsoft 365](../admin/add-users/index.yml)管理中心 [、PowerShell、Active](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)Directory 域服务 (AD DS) 或 Azure Active Directory (Azure AD) 管理门户中管理用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bb36d-105">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin portal.</span></span> 

<span data-ttu-id="bb36d-106">一旦购买 Microsoft 365，Microsoft 365 管理中心和 PowerShell 就可以用于管理帐户。</span><span class="sxs-lookup"><span data-stu-id="bb36d-106">As soon as you purchase Microsoft 365, the Microsoft 365 admin center and PowerShell can be used to manage accounts.</span></span> <span data-ttu-id="bb36d-107">管理云标识时，组织中的每个人都具有单独的用户帐户名称和密码。</span><span class="sxs-lookup"><span data-stu-id="bb36d-107">When managing cloud identities, every person in your organization has a separate user account name and password.</span></span> <span data-ttu-id="bb36d-108">如果你想要与本地基础结构集成，并且使用户帐户与 Microsoft 365 同步，可以使用 Azure AD Connect 为单一登录 (SSO) 功能提供标识和密码同步。</span><span class="sxs-lookup"><span data-stu-id="bb36d-108">If you want to integrate with your on-premises infrastructure and have user accounts synchronized with Microsoft 365, you can use Azure AD Connect to provide synchronization of identities and passwords for single sign-on (SSO) functionality.</span></span>
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a><span data-ttu-id="bb36d-109">规划用户帐户管理位置和方式</span><span class="sxs-lookup"><span data-stu-id="bb36d-109">Plan for where and how you will manage your user accounts</span></span>

<span data-ttu-id="bb36d-110">在哪里以及如何管理用户帐户取决于你要用于 Microsoft 365 的标识模型。</span><span class="sxs-lookup"><span data-stu-id="bb36d-110">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="bb36d-111">这两种整体模型是仅云模型和混合模型。</span><span class="sxs-lookup"><span data-stu-id="bb36d-111">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="bb36d-112">仅限云</span><span class="sxs-lookup"><span data-stu-id="bb36d-112">Cloud-only</span></span>

<span data-ttu-id="bb36d-113">在 Microsoft 365 管理中心创建和管理用户。</span><span class="sxs-lookup"><span data-stu-id="bb36d-113">You create and manage users in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bb36d-114">您还可以使用 PowerShell 或 Azure AD 管理中心。</span><span class="sxs-lookup"><span data-stu-id="bb36d-114">You can also use PowerShell or the Azure AD admin center.</span></span> 
    
### <a name="hybrid"></a><span data-ttu-id="bb36d-115">混合</span><span class="sxs-lookup"><span data-stu-id="bb36d-115">Hybrid</span></span>

<span data-ttu-id="bb36d-116">用户帐户从 AD DS 与 Microsoft 365 同步，因此必须使用本地 AD DS 工具管理用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bb36d-116">User accounts are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage user accounts.</span></span> 
    
## <a name="managing-accounts"></a><span data-ttu-id="bb36d-117">管理帐户</span><span class="sxs-lookup"><span data-stu-id="bb36d-117">Managing Accounts</span></span>

<span data-ttu-id="bb36d-118">在决定组织创建和管理帐户的方式时，请考虑以下要求：</span><span class="sxs-lookup"><span data-stu-id="bb36d-118">When deciding which way your organization will create and manage accounts, consider the following requirements:</span></span>
  
- <span data-ttu-id="bb36d-119">目录同步软件需要安装在本地环境的服务器上，以连接 Microsoft 365 和 AD DS 之间的标识。</span><span class="sxs-lookup"><span data-stu-id="bb36d-119">The directory synchronization software needs to be installed on servers within your on-premises environment to connect the identities between Microsoft 365 and your AD DS.</span></span>
    
- <span data-ttu-id="bb36d-120">任何目录同步选项（包括 SSO 选项）都要求 AD DS 属性符合标准。</span><span class="sxs-lookup"><span data-stu-id="bb36d-120">Any directory synchronization option, including SSO options, requires that your AD DS attributes meet standards.</span></span> <span data-ttu-id="bb36d-121">准备与 [Microsoft 365](prepare-for-directory-synchronization.md)进行目录同步中介绍了目录中使用的属性和 (（如果需要任何) ）的清理方法。</span><span class="sxs-lookup"><span data-stu-id="bb36d-121">The specifics of what attributes are used in your directory and what cleanup (if any) is needed are described in [Prepare for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span> 
    
- <span data-ttu-id="bb36d-122">规划如何创建 Microsoft 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="bb36d-122">Plan how you are going to create Microsoft 365 accounts.</span></span>
    
<span data-ttu-id="bb36d-123">下表列出了不同的帐户管理工具。</span><span class="sxs-lookup"><span data-stu-id="bb36d-123">The following table lists the different account management tools.</span></span>
    
|<span data-ttu-id="bb36d-124">工具</span><span class="sxs-lookup"><span data-stu-id="bb36d-124">Tool</span></span>|<span data-ttu-id="bb36d-125">备注</span><span class="sxs-lookup"><span data-stu-id="bb36d-125">Notes</span></span>|
|:-----|:-----|
|<span data-ttu-id="bb36d-126">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="bb36d-126">Microsoft 365 admin center</span></span>  <br/> |[<span data-ttu-id="bb36d-127">单独或批量添加用户</span><span class="sxs-lookup"><span data-stu-id="bb36d-127">Add users individually or in bulk</span></span>](../admin/add-users/add-users.md) <br/>  <span data-ttu-id="bb36d-128">提供用于添加和更改用户帐户的简单 Web 界面。</span><span class="sxs-lookup"><span data-stu-id="bb36d-128">Provides a simple web interface to add and change user accounts.</span></span>  <br/>  <span data-ttu-id="bb36d-129">如果启用了目录同步，则不能用于更改用户 (且可以将许可证分配设置为) 。</span><span class="sxs-lookup"><span data-stu-id="bb36d-129">Can't be used to change users if directory synchronization is enabled (location and license assignment can be set).</span></span>  <br/>  <span data-ttu-id="bb36d-130">不能与 SSO 选项一同使用。</span><span class="sxs-lookup"><span data-stu-id="bb36d-130">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="bb36d-131">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb36d-131">Windows PowerShell</span></span>  <br/> |[<span data-ttu-id="bb36d-132">使用 Microsoft 365 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb36d-132">Manage Microsoft 365 with Windows PowerShell</span></span>](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  <span data-ttu-id="bb36d-133">允许您使用自定义脚本批量添加Windows PowerShell用户。</span><span class="sxs-lookup"><span data-stu-id="bb36d-133">Allows you to add users in bulk users by using a Windows PowerShell script.</span></span>  <br/>  <span data-ttu-id="bb36d-134">可用于向帐户分配位置和许可证，而不考虑帐户的创建方式。</span><span class="sxs-lookup"><span data-stu-id="bb36d-134">Can be used to assign location and licenses to accounts, regardless of how the accounts are created.</span></span>  <br/> |
|<span data-ttu-id="bb36d-135">批量导入</span><span class="sxs-lookup"><span data-stu-id="bb36d-135">Bulk import</span></span>  <br/> |[<span data-ttu-id="bb36d-136">同时添加多个用户</span><span class="sxs-lookup"><span data-stu-id="bb36d-136">Add several users at the same time</span></span>](add-several-users-at-the-same-time.md) <br/>  <span data-ttu-id="bb36d-137">允许你导入 CSV 文件以将一组用户添加到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bb36d-137">Allows you to import a CSV file to add a group of users to Microsoft 365.</span></span>  <br/>  <span data-ttu-id="bb36d-138">不能与 SSO 选项一同使用。</span><span class="sxs-lookup"><span data-stu-id="bb36d-138">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="bb36d-139">Azure AD</span><span class="sxs-lookup"><span data-stu-id="bb36d-139">Azure AD</span></span>  <br/> |<span data-ttu-id="bb36d-140">通过 Microsoft 365 订阅，可获取 Azure AD 的免费版本。</span><span class="sxs-lookup"><span data-stu-id="bb36d-140">You get a free edition of Azure AD with your Microsoft 365 subscription.</span></span> <span data-ttu-id="bb36d-141">你可以执行一些功能，如为云用户重置自助服务密码，以及使用免费版本自定义登录和访问面板页面。</span><span class="sxs-lookup"><span data-stu-id="bb36d-141">You can perform functions like self-service password reset for cloud users, and customization of the Sign-in and Access Panel pages by using the free edition.</span></span> <span data-ttu-id="bb36d-142">若要获取增强功能，可以升级到基本版本 Azure AD Premium P1 或 Azure AD Premium P2。</span><span class="sxs-lookup"><span data-stu-id="bb36d-142">To get enhanced functionality, you can upgrade to the basic edition, Azure AD Premium P1, or Azure AD Premium P2.</span></span> <span data-ttu-id="bb36d-143">有关 [支持的功能列表，请参阅 Azure AD](/azure/active-directory/fundamentals/active-directory-whatis) 版本。</span><span class="sxs-lookup"><span data-stu-id="bb36d-143">See [Azure AD editions](/azure/active-directory/fundamentals/active-directory-whatis) for the list of supported features.</span></span>  <br/> |
|<span data-ttu-id="bb36d-144">目录同步</span><span class="sxs-lookup"><span data-stu-id="bb36d-144">Directory synchronization</span></span>  <br/> |[<span data-ttu-id="bb36d-145">将本地标识与 Azure AD 集成</span><span class="sxs-lookup"><span data-stu-id="bb36d-145">Integrating your on-premises identities with Azure AD</span></span>](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  <span data-ttu-id="bb36d-146">对于与密码同步或不使用密码同步的目录同步，请将 [Azure AD Connect 与快速设置一同使用](/azure/active-directory/hybrid/how-to-connect-install-express)。</span><span class="sxs-lookup"><span data-stu-id="bb36d-146">For directory synchronization with or without password synchronization, use [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>  <br/>  <span data-ttu-id="bb36d-147">对于多个林和 SSO 选项，请使用 [Azure AD Connect 的自定义安装](/azure/active-directory/hybrid/how-to-connect-install-custom)。</span><span class="sxs-lookup"><span data-stu-id="bb36d-147">For multiple forests and SSO options, use [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>  <br/>  <span data-ttu-id="bb36d-148">提供启用 SSO 所需的基础结构。</span><span class="sxs-lookup"><span data-stu-id="bb36d-148">Provides the infrastructure that's necessary to enable SSO.</span></span>  <br/>  <span data-ttu-id="bb36d-149">对于很多混合方案（如分步迁移和混合 Exchange）来说是必需的</span><span class="sxs-lookup"><span data-stu-id="bb36d-149">Required for many hybrid scenarios such as staged migration and hybrid Exchange</span></span>  <br/>  <span data-ttu-id="bb36d-150">从 AD DS 同步安全和启用邮件的组。</span><span class="sxs-lookup"><span data-stu-id="bb36d-150">Synchronizes security and mail-enabled groups from your AD DS.</span></span>  <br/> |
|||
   
- <span data-ttu-id="bb36d-151">无论你打算如何向 Microsoft 365 添加用户帐户，都需要管理多个帐户功能，例如分配许可证、指定位置等。</span><span class="sxs-lookup"><span data-stu-id="bb36d-151">Regardless of how you intend to add the user accounts to Microsoft 365, you need to manage several account features, such as assigning licenses, specifying location, and so on.</span></span> <span data-ttu-id="bb36d-152">可以从 Microsoft 365 管理中心长期管理这些功能，或者您也可以使用 [PowerShell 创建用户帐户](./create-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bb36d-152">These features can be managed long-term from the Microsoft 365 admin center or you can also [create user accounts with PowerShell](./create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
    <span data-ttu-id="bb36d-153">如果选择通过管理中心添加和管理所有用户，你将在创建 Microsoft 365 帐户的同时指定位置并分配许可证。</span><span class="sxs-lookup"><span data-stu-id="bb36d-153">If you choose to add and manage all your users through the admin center, you will specify the location and assign licenses at the same time as creating the Microsoft 365 account.</span></span> <span data-ttu-id="bb36d-154">因此，不需要进行太多规划。</span><span class="sxs-lookup"><span data-stu-id="bb36d-154">As a result, not much planning is required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb36d-155">在不向 SharePoint Online 分配许可证 (的情况下在 Microsoft 365 创建帐户，例如) 意味着帐户所有者可以查看 Microsoft 365 中心，但不能访问公司订阅内的任何服务。</span><span class="sxs-lookup"><span data-stu-id="bb36d-155">Creating accounts in Microsoft 365 without assigning a license (to SharePoint Online, for example) means that the account owner can view the Microsoft 365 center but can't access any of the services within your company's subscription.</span></span> <span data-ttu-id="bb36d-156">分配位置和许可证后，该帐户将复制到你分配的一个或多个服务。</span><span class="sxs-lookup"><span data-stu-id="bb36d-156">After you assign a location and the license, the account is replicated to the service or services that you assigned.</span></span> <span data-ttu-id="bb36d-157">用户可以登录到其帐户并使用你分配给他们的服务。</span><span class="sxs-lookup"><span data-stu-id="bb36d-157">The user can sign in to their account and use the services that you assigned to them.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bb36d-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb36d-158">See also</span></span>

[<span data-ttu-id="bb36d-159">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="bb36d-159">Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)

[<span data-ttu-id="bb36d-160">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb36d-160">PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)