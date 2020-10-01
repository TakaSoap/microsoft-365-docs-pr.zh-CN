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
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327755"
---
# <a name="manage-microsoft-365-user-accounts"></a><span data-ttu-id="77165-103">管理 Microsoft 365 用户帐户</span><span class="sxs-lookup"><span data-stu-id="77165-103">Manage Microsoft 365 user accounts</span></span>

<span data-ttu-id="77165-104">您可以通过几种不同的方式管理 Microsoft 365 用户帐户，具体取决于您的配置。</span><span class="sxs-lookup"><span data-stu-id="77165-104">You can manage Microsoft 365 user accounts in several different ways, depending on your configuration.</span></span> <span data-ttu-id="77165-105">你可以在 Active Directory 域服务 (AD DS) 中或在 Azure Active Directory (Azure AD) 管理门户中管理 [Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)、 [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)、active directory 域服务中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="77165-105">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin portal.</span></span> 

<span data-ttu-id="77165-106">一旦购买 Microsoft 365，Microsoft 365 管理中心和 PowerShell 便可用于管理帐户。</span><span class="sxs-lookup"><span data-stu-id="77165-106">As soon as you purchase Microsoft 365, the Microsoft 365 admin center and PowerShell can be used to manage accounts.</span></span> <span data-ttu-id="77165-107">管理云身份时，组织中的每个人都有单独的用户帐户名和密码。</span><span class="sxs-lookup"><span data-stu-id="77165-107">When managing cloud identities, every person in your organization has a separate user account name and password.</span></span> <span data-ttu-id="77165-108">如果要与本地基础结构集成并将用户帐户与 Microsoft 365 同步，可以使用 Azure AD Connect 为单一登录 (SSO) 功能提供标识和密码的同步。</span><span class="sxs-lookup"><span data-stu-id="77165-108">If you want to integrate with your on-premises infrastructure and have user accounts synchronized with Microsoft 365, you can use Azure AD Connect to provide synchronization of identities and passwords for single sign-on (SSO) functionality.</span></span>
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a><span data-ttu-id="77165-109">规划将管理用户帐户的位置和方式</span><span class="sxs-lookup"><span data-stu-id="77165-109">Plan for where and how you will manage your user accounts</span></span>

<span data-ttu-id="77165-110">如何管理用户帐户的位置和方式取决于要用于 Microsoft 365 的标识模型。</span><span class="sxs-lookup"><span data-stu-id="77165-110">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="77165-111">这两个整体模型为仅云和混合模式。</span><span class="sxs-lookup"><span data-stu-id="77165-111">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="77165-112">仅限云</span><span class="sxs-lookup"><span data-stu-id="77165-112">Cloud-only</span></span>

<span data-ttu-id="77165-113">在 Microsoft 365 管理中心中创建和管理用户。</span><span class="sxs-lookup"><span data-stu-id="77165-113">You create and manage users in the Microsoft 365 admin center.</span></span> <span data-ttu-id="77165-114">您还可以使用 PowerShell 或 Azure AD 管理中心。</span><span class="sxs-lookup"><span data-stu-id="77165-114">You can also use PowerShell or the Azure AD admin center.</span></span> 
    
### <a name="hybrid"></a><span data-ttu-id="77165-115">混合</span><span class="sxs-lookup"><span data-stu-id="77165-115">Hybrid</span></span>

<span data-ttu-id="77165-116">用户帐户与 AD DS 中的 Microsoft 365 同步，因此您必须使用内部部署 AD DS 工具来管理用户帐户。</span><span class="sxs-lookup"><span data-stu-id="77165-116">User accounts are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage user accounts.</span></span> 
    
## <a name="managing-accounts"></a><span data-ttu-id="77165-117">管理帐户</span><span class="sxs-lookup"><span data-stu-id="77165-117">Managing Accounts</span></span>

<span data-ttu-id="77165-118">在决定您的组织创建和管理帐户的方式时，请考虑以下要求：</span><span class="sxs-lookup"><span data-stu-id="77165-118">When deciding which way your organization will create and manage accounts, consider the following requirements:</span></span>
  
- <span data-ttu-id="77165-119">目录同步软件需要安装在本地环境中的服务器上，以连接 Microsoft 365 和 AD DS 之间的标识。</span><span class="sxs-lookup"><span data-stu-id="77165-119">The directory synchronization software needs to be installed on servers within your on-premises environment to connect the identities between Microsoft 365 and your AD DS.</span></span>
    
- <span data-ttu-id="77165-120">任何目录同步选项（包括 SSO 选项）都要求 AD DS 属性满足标准。</span><span class="sxs-lookup"><span data-stu-id="77165-120">Any directory synchronization option, including SSO options, requires that your AD DS attributes meet standards.</span></span> <span data-ttu-id="77165-121">[准备目录同步到 Microsoft 365](prepare-for-directory-synchronization.md)中描述了在目录中使用的属性和清除 (（如果有任何) 需要）的具体说明。</span><span class="sxs-lookup"><span data-stu-id="77165-121">The specifics of what attributes are used in your directory and what cleanup (if any) is needed are described in [Prepare for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span> 
    
- <span data-ttu-id="77165-122">规划如何创建 Microsoft 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="77165-122">Plan how you are going to create Microsoft 365 accounts.</span></span>
    
<span data-ttu-id="77165-123">下表列出了不同的帐户管理工具。</span><span class="sxs-lookup"><span data-stu-id="77165-123">The following table lists the different account management tools.</span></span>
    
|<span data-ttu-id="77165-124">工具</span><span class="sxs-lookup"><span data-stu-id="77165-124">Tool</span></span>|<span data-ttu-id="77165-125">注释</span><span class="sxs-lookup"><span data-stu-id="77165-125">Notes</span></span>|
|:-----|:-----|
|<span data-ttu-id="77165-126">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="77165-126">Microsoft 365 admin center</span></span>  <br/> |[<span data-ttu-id="77165-127">单独或批量添加用户</span><span class="sxs-lookup"><span data-stu-id="77165-127">Add users individually or in bulk</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  <span data-ttu-id="77165-128">提供一个简单的 web 界面来添加和更改用户帐户。</span><span class="sxs-lookup"><span data-stu-id="77165-128">Provides a simple web interface to add and change user accounts.</span></span>  <br/>  <span data-ttu-id="77165-129">如果启用了目录同步，则无法用于更改用户 (位置和许可证分配可以设置) 。</span><span class="sxs-lookup"><span data-stu-id="77165-129">Can't be used to change users if directory synchronization is enabled (location and license assignment can be set).</span></span>  <br/>  <span data-ttu-id="77165-130">不能与 SSO 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="77165-130">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="77165-131">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77165-131">Windows PowerShell</span></span>  <br/> |[<span data-ttu-id="77165-132">使用 Windows PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="77165-132">Manage Microsoft 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  <span data-ttu-id="77165-133">允许您使用 Windows PowerShell 脚本在批量用户中添加用户。</span><span class="sxs-lookup"><span data-stu-id="77165-133">Allows you to add users in bulk users by using a Windows PowerShell script.</span></span>  <br/>  <span data-ttu-id="77165-134">可用于将位置和许可证分配给帐户，而不考虑帐户的创建方式。</span><span class="sxs-lookup"><span data-stu-id="77165-134">Can be used to assign location and licenses to accounts, regardless of how the accounts are created.</span></span>  <br/> |
|<span data-ttu-id="77165-135">批量导入</span><span class="sxs-lookup"><span data-stu-id="77165-135">Bulk import</span></span>  <br/> |[<span data-ttu-id="77165-136">同时添加多个用户</span><span class="sxs-lookup"><span data-stu-id="77165-136">Add several users at the same time</span></span>](add-several-users-at-the-same-time.md) <br/>  <span data-ttu-id="77165-137">允许您导入 CSV 文件以将一组用户添加到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="77165-137">Allows you to import a CSV file to add a group of users to Microsoft 365.</span></span>  <br/>  <span data-ttu-id="77165-138">不能与 SSO 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="77165-138">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="77165-139">Azure AD</span><span class="sxs-lookup"><span data-stu-id="77165-139">Azure AD</span></span>  <br/> |<span data-ttu-id="77165-140">你可以使用 Microsoft 365 订阅获取 Azure AD 的免费版本。</span><span class="sxs-lookup"><span data-stu-id="77165-140">You get a free edition of Azure AD with your Microsoft 365 subscription.</span></span> <span data-ttu-id="77165-141">您可以为云用户执行自助密码重置等功能，并使用免费版本自定义登录和访问面板页。</span><span class="sxs-lookup"><span data-stu-id="77165-141">You can perform functions like self-service password reset for cloud users, and customization of the Sign-in and Access Panel pages by using the free edition.</span></span> <span data-ttu-id="77165-142">若要获取增强的功能，您可以升级到基本版本、Azure AD 高级 P1 或 Azure AD Premium P2。</span><span class="sxs-lookup"><span data-stu-id="77165-142">To get enhanced functionality, you can upgrade to the basic edition, Azure AD Premium P1, or Azure AD Premium P2.</span></span> <span data-ttu-id="77165-143">有关支持的功能的列表，请参阅 [AZURE AD 版本](https://go.microsoft.com/fwlink/p/?LinkId=698465) 。</span><span class="sxs-lookup"><span data-stu-id="77165-143">See [Azure AD editions](https://go.microsoft.com/fwlink/p/?LinkId=698465) for the list of supported features.</span></span>  <br/> |
|<span data-ttu-id="77165-144">目录同步</span><span class="sxs-lookup"><span data-stu-id="77165-144">Directory synchronization</span></span>  <br/> |[<span data-ttu-id="77165-145">将本地标识与 Azure AD 集成</span><span class="sxs-lookup"><span data-stu-id="77165-145">Integrating your on-premises identities with Azure AD</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  <span data-ttu-id="77165-146">对于使用或不使用密码同步进行目录同步，请将 [AZURE AD Connect 与 express 设置结合](https://go.microsoft.com/fwlink/p/?LinkID=698537)使用。</span><span class="sxs-lookup"><span data-stu-id="77165-146">For directory synchronization with or without password synchronization, use [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkID=698537).</span></span>  <br/>  <span data-ttu-id="77165-147">对于多个林和 SSO 选项，请使用 [自定义安装的 AZURE AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430)。</span><span class="sxs-lookup"><span data-stu-id="77165-147">For multiple forests and SSO options, use [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>  <br/>  <span data-ttu-id="77165-148">提供启用 SSO 所需的基础结构。</span><span class="sxs-lookup"><span data-stu-id="77165-148">Provides the infrastructure that's necessary to enable SSO.</span></span>  <br/>  <span data-ttu-id="77165-149">对许多混合方案（如暂存迁移和混合 Exchange）是必需的</span><span class="sxs-lookup"><span data-stu-id="77165-149">Required for many hybrid scenarios such as staged migration and hybrid Exchange</span></span>  <br/>  <span data-ttu-id="77165-150">从 AD DS 同步安全和启用邮件的组。</span><span class="sxs-lookup"><span data-stu-id="77165-150">Synchronizes security and mail-enabled groups from your AD DS.</span></span>  <br/> |
|||
   
- <span data-ttu-id="77165-151">无论您打算如何将用户帐户添加到 Microsoft 365，您都需要管理多个帐户功能，例如分配许可证、指定位置等。</span><span class="sxs-lookup"><span data-stu-id="77165-151">Regardless of how you intend to add the user accounts to Microsoft 365, you need to manage several account features, such as assigning licenses, specifying location, and so on.</span></span> <span data-ttu-id="77165-152">可以从 Microsoft 365 管理中心对这些功能进行管理，也可以 [使用 PowerShell 创建用户帐户](https://go.microsoft.com/fwlink/p/?LinkId=717083)。</span><span class="sxs-lookup"><span data-stu-id="77165-152">These features can be managed long-term from the Microsoft 365 admin center or you can also [create user accounts with PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).</span></span>
    
    <span data-ttu-id="77165-153">如果选择通过管理中心添加和管理所有用户，您将指定位置，并在创建 Microsoft 365 帐户的同时分配许可证。</span><span class="sxs-lookup"><span data-stu-id="77165-153">If you choose to add and manage all your users through the admin center, you will specify the location and assign licenses at the same time as creating the Microsoft 365 account.</span></span> <span data-ttu-id="77165-154">因此，不需要进行大量规划。</span><span class="sxs-lookup"><span data-stu-id="77165-154">As a result, not much planning is required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="77165-155">在 Microsoft 365 中创建帐户，而不向 SharePoint Online 分配许可证 (，例如) 意味着帐户所有者可以查看 Microsoft 365 中心，但不能访问公司订阅中的任何服务。</span><span class="sxs-lookup"><span data-stu-id="77165-155">Creating accounts in Microsoft 365 without assigning a license (to SharePoint Online, for example) means that the account owner can view the Microsoft 365 center but can't access any of the services within your company's subscription.</span></span> <span data-ttu-id="77165-156">分配位置和许可证后，帐户将复制到您分配的服务或服务。</span><span class="sxs-lookup"><span data-stu-id="77165-156">After you assign a location and the license, the account is replicated to the service or services that you assigned.</span></span> <span data-ttu-id="77165-157">用户可以登录到其帐户并使用您分配给他们的服务。</span><span class="sxs-lookup"><span data-stu-id="77165-157">The user can sign in to their account and use the services that you assigned to them.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="77165-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77165-158">See also</span></span>

[<span data-ttu-id="77165-159">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="77165-159">Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users)

[<span data-ttu-id="77165-160">PowerShell</span><span class="sxs-lookup"><span data-stu-id="77165-160">PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
