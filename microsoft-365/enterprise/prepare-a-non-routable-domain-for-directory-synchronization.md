---
title: 准备不可路由域以进行目录同步
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
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: 了解在将非可路由域与本地用户帐户同步之前，与 Microsoft 365 租户同步时要执行哪些操作。
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780328"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="84c2b-103">准备不可路由域以进行目录同步</span><span class="sxs-lookup"><span data-stu-id="84c2b-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="84c2b-104">将本地目录与 Microsoft 365 同步时，你必须在 Azure Active Directory (Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="84c2b-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="84c2b-105">仅同步 () Active Directory 域服务 (AD DS) 的用户主体名称。</span><span class="sxs-lookup"><span data-stu-id="84c2b-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="84c2b-106">但是，任何包含不可路由域的 UPN（如".local" (示例：billa@contoso.local) ）都将同步到 .onmicrosoft.com 域 (示例：billa@contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="84c2b-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="84c2b-107">如果当前对 AD DS 中的用户帐户使用".local"域，建议将其更改为使用已验证的域（如 billa@contoso.com）以便与 Microsoft 365 域正确同步。</span><span class="sxs-lookup"><span data-stu-id="84c2b-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="84c2b-108">如果我只有".local"本地域，该做什么？</span><span class="sxs-lookup"><span data-stu-id="84c2b-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="84c2b-109">使用 Azure AD Connect 将 AD DS 同步到 Microsoft 365 租户的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="84c2b-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="84c2b-110">有关详细信息，请参阅将本地 [标识与 Azure AD 集成](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad)。</span><span class="sxs-lookup"><span data-stu-id="84c2b-110">For more information, see [Integrating your on-premises identities with Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="84c2b-111">Azure AD Connect 可同步用户的 UPN 和密码，以便用户可以使用他们在本地使用的相同凭据登录。</span><span class="sxs-lookup"><span data-stu-id="84c2b-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="84c2b-112">但是，Azure AD Connect 仅将用户同步到 Microsoft 365 验证的域。</span><span class="sxs-lookup"><span data-stu-id="84c2b-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="84c2b-113">这意味着该域也由 Azure AD 进行验证，因为 Microsoft 365 标识由 Azure AD 管理。</span><span class="sxs-lookup"><span data-stu-id="84c2b-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="84c2b-114">换句话说，域必须是有效的 Internet 域， (.com、.org、.net、.us) 。</span><span class="sxs-lookup"><span data-stu-id="84c2b-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="84c2b-115">如果内部 AD DS 仅使用不可路由的域 (例如，".local") ，则这不可能与 Microsoft 365 租户的已验证域匹配。</span><span class="sxs-lookup"><span data-stu-id="84c2b-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="84c2b-116">可以通过更改本地 AD DS 中的主域或添加一个或多个 UPN 后缀来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="84c2b-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="84c2b-117">更改主域</span><span class="sxs-lookup"><span data-stu-id="84c2b-117">Change your primary domain</span></span>

<span data-ttu-id="84c2b-118">将主域更改为你在 Microsoft 365 中验证的域，例如contoso.com。</span><span class="sxs-lookup"><span data-stu-id="84c2b-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="84c2b-119">然后，将具有域 contoso.local 的每个用户更新为contoso.com。</span><span class="sxs-lookup"><span data-stu-id="84c2b-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="84c2b-120">但是，这是一个非常涉及的过程，下一节将介绍一个更简单的解决方案。</span><span class="sxs-lookup"><span data-stu-id="84c2b-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="84c2b-121">添加 UPN 后缀并更新用户</span><span class="sxs-lookup"><span data-stu-id="84c2b-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="84c2b-122">可以通过在 AD DS 中注册新的 UPN 后缀，以匹配在 Microsoft 365 中验证的域 (或域) 解决".local"问题。</span><span class="sxs-lookup"><span data-stu-id="84c2b-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="84c2b-123">注册新后缀后，更新用户 UPN 以将".local"替换为新域名，例如，使用户帐户看起来像billa@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="84c2b-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="84c2b-124">更新 UPN 以使用已验证域后，即可将本地 AD DS 与 Microsoft 365 同步。</span><span class="sxs-lookup"><span data-stu-id="84c2b-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="84c2b-125">步骤 1：添加新的 UPN 后缀\*\*</span><span class="sxs-lookup"><span data-stu-id="84c2b-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="84c2b-126">在 AD DS 域控制器上，在服务器管理器中选择"**工具** \> **Active Directory 域和信任"。**</span><span class="sxs-lookup"><span data-stu-id="84c2b-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="84c2b-127">**或者，如果你没有Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="84c2b-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="84c2b-128">按 **Windows 键 + R** 打开 **"** 运行"对话框，然后在 Domain.msc 中键入，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="84c2b-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![选择"Active Directory 域和信任"。](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="84c2b-130">在 **"Active Directory 域和信任"** 窗口中，右键单击 **"Active Directory** 域和信任"，然后选择"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="84c2b-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![右键单击"Active Directory 域和信任"，然后选择"属性"](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="84c2b-132">在 **"UPN** 后缀"选项卡上的"备用 **UPN** 后缀"框中，键入新的 UPN 后缀，然后选择"添加 \> **应用"。**</span><span class="sxs-lookup"><span data-stu-id="84c2b-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![添加新的 UPN 后缀](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="84c2b-134">添加 **后缀** 后，选择"确定"。</span><span class="sxs-lookup"><span data-stu-id="84c2b-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="84c2b-135">步骤 2：更改现有用户的 UPN 后缀</span><span class="sxs-lookup"><span data-stu-id="84c2b-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="84c2b-136">在 AD DS 域控制器上，在服务器管理器中选择"**工具** \> **Active Directory 用户和计算机"。**</span><span class="sxs-lookup"><span data-stu-id="84c2b-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="84c2b-137">**或者，如果你没有Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="84c2b-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="84c2b-138">按 **Windows 键 + R** 打开 **"** 运行"对话框，然后在 Dsa.msc 中键入，然后单击" **确定"**</span><span class="sxs-lookup"><span data-stu-id="84c2b-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="84c2b-139">选择用户，右键单击，然后选择"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="84c2b-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="84c2b-140">在 **"帐户**"选项卡上的 UPN 后缀下拉列表中，选择新的 UPN 后缀，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="84c2b-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![为用户添加新的 UPN 后缀](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="84c2b-142">为每个用户完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="84c2b-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="84c2b-143">使用 PowerShell 更改所有用户的 UPN 后缀</span><span class="sxs-lookup"><span data-stu-id="84c2b-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="84c2b-144">如果有很多要更新的用户帐户，则使用 PowerShell 会更容易。</span><span class="sxs-lookup"><span data-stu-id="84c2b-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="84c2b-145">以下示例使用 cmdlet [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) 和 [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) 将所有 contoso.local 后缀contoso.com AD DS 中。</span><span class="sxs-lookup"><span data-stu-id="84c2b-145">The following example uses the cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) and [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="84c2b-146">例如，可以运行以下 PowerShell 命令，将所有 contoso.local 后缀更新为contoso.com：</span><span class="sxs-lookup"><span data-stu-id="84c2b-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="84c2b-147">请参阅 [Active Directory Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=624314) 模块，了解有关在 AD DS Windows PowerShell应用程序功能。</span><span class="sxs-lookup"><span data-stu-id="84c2b-147">See [Active Directory Windows PowerShell module](https://go.microsoft.com/fwlink/p/?LinkId=624314) to learn more about using Windows PowerShell in AD DS.</span></span> 

