---
title: 从 Microsoft 云德国迁移的其他一般信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从 Microsoft (云) 德国移动到新的德国数据中心区域中的 Office 365 服务时，有关服务的其他常规信息。
ms.openlocfilehash: 6fa09165f8aaa68e0f9fc567d96a4e53baaa594e
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551778"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="63a4e-103">从 Microsoft 云德国迁移的其他一般信息</span><span class="sxs-lookup"><span data-stu-id="63a4e-103">Additional general information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="63a4e-104">以下各节提供有关服务、预备工作注意事项和客户体验的其他信息。</span><span class="sxs-lookup"><span data-stu-id="63a4e-104">The following sections provide additional information on services, pre-work considerations, and customer experience.</span></span>

## <a name="azure-active-directory"></a><span data-ttu-id="63a4e-105">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="63a4e-105">Azure Active Directory</span></span>

<span data-ttu-id="63a4e-106">若要完成从 Azure AD 云到 Azure 公共云的移动，我们建议在 OpenID Connect (OIDC) 终结点 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 开始报告商业云终结点时，将身份验证终结点、Azure Active Directory (azure AD) Graph 和 MS Graph 终结点更新为商业云的这些终结点。</span><span class="sxs-lookup"><span data-stu-id="63a4e-106">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="63a4e-107">**何时应进行此更改？**</span><span class="sxs-lookup"><span data-stu-id="63a4e-107">**When should I make this change?**</span></span>

<span data-ttu-id="63a4e-108">当你的租户完成从德国云到商业云的迁移时，你将在 Azure/Office 门户中收到通知。</span><span class="sxs-lookup"><span data-stu-id="63a4e-108">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="63a4e-109">接收此通知后，你有30天的时间来完成这些更新，以便你的应用继续适用于从 Azure 德国云迁移到 Azure 公有云的租户。</span><span class="sxs-lookup"><span data-stu-id="63a4e-109">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="63a4e-110">有三个用于更新您的登录证书颁发机构的前提条件：</span><span class="sxs-lookup"><span data-stu-id="63a4e-110">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="63a4e-111">租户的 OIDC 发现终结点 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 返回 AZURE AD 公共云终结点。</span><span class="sxs-lookup"><span data-stu-id="63a4e-111">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="63a4e-112">如果你的租户设置了联合身份验证，Active Directory 联合身份验证服务 (AD FS) 更新为与 Azure AD 公共同步。</span><span class="sxs-lookup"><span data-stu-id="63a4e-112">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="63a4e-113">您可以按照说明更新 Azure AD Connect 设置以进行此更改。</span><span class="sxs-lookup"><span data-stu-id="63a4e-113">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="63a4e-114">您的应用程序使用的资源应用程序（如果有）将被修改，以接受由 Azure AD 德国和 Azure AD 公共签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="63a4e-114">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="63a4e-115">**什么类型的应用程序？**</span><span class="sxs-lookup"><span data-stu-id="63a4e-115">**What kind of applications?**</span></span>

<span data-ttu-id="63a4e-116">应用程序可以是以下任一项：</span><span class="sxs-lookup"><span data-stu-id="63a4e-116">An application could be any of the following:</span></span>

- <span data-ttu-id="63a4e-117">单页面应用程序 (SPA) </span><span class="sxs-lookup"><span data-stu-id="63a4e-117">Single-page app (SPA)</span></span>
- <span data-ttu-id="63a4e-118">登录用户的 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="63a4e-118">Web app that signs in users</span></span>
- <span data-ttu-id="63a4e-119">调用 web Api 的 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="63a4e-119">Web app that calls web APIs</span></span>
- <span data-ttu-id="63a4e-120">受保护的 web API</span><span class="sxs-lookup"><span data-stu-id="63a4e-120">Protected web API</span></span>
- <span data-ttu-id="63a4e-121">调用 web Api 的 Web API</span><span class="sxs-lookup"><span data-stu-id="63a4e-121">Web API that calls web APIs</span></span>
- <span data-ttu-id="63a4e-122">桌面应用</span><span class="sxs-lookup"><span data-stu-id="63a4e-122">Desktop app</span></span>
- <span data-ttu-id="63a4e-123">守护程序应用</span><span class="sxs-lookup"><span data-stu-id="63a4e-123">Daemon app</span></span>
- <span data-ttu-id="63a4e-124">移动应用</span><span class="sxs-lookup"><span data-stu-id="63a4e-124">Mobile app</span></span>
 
> [!NOTE] 
> <span data-ttu-id="63a4e-125">当应用程序切换为 `login.microsoftonline.com` 颁发机构使用时，令牌将由此新的颁发机构签名。</span><span class="sxs-lookup"><span data-stu-id="63a4e-125">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="63a4e-126">如果托管其他应用程序调用的任何资源应用程序，则需要允许进行宽松令牌验证。</span><span class="sxs-lookup"><span data-stu-id="63a4e-126">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="63a4e-127">这意味着您的应用程序需要允许由 Azure AD 德国和 Azure AD 公共云签署的令牌。</span><span class="sxs-lookup"><span data-stu-id="63a4e-127">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="63a4e-128">在所有调用您的服务的客户端应用程序完全迁移到 Azure AD 公共云之前，需要进行这种宽松令牌验证。</span><span class="sxs-lookup"><span data-stu-id="63a4e-128">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="63a4e-129">迁移之后，您的资源应用程序只需要接受由 Azure AD 公共云签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="63a4e-129">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="63a4e-130">**我需要更新哪些内容？**</span><span class="sxs-lookup"><span data-stu-id="63a4e-130">**What do I need to update?**</span></span>

1. <span data-ttu-id="63a4e-131">如果要托管 Azure 德国的应用程序，该应用程序用于对 Azure 德国或 Office 365 德国用户进行身份验证，请确保在 `https://login.microsoftonline.com` 身份验证上下文中将其用作证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="63a4e-131">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="63a4e-132">请参阅 Azure AD 身份验证上下文。</span><span class="sxs-lookup"><span data-stu-id="63a4e-132">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="63a4e-133">这既适用于对应用程序的身份验证，也适用于应用程序可能调用的任何 Api 的身份验证 (也就是说，Microsoft Graph、Azure AD Graph、Azure 资源管理器) 。</span><span class="sxs-lookup"><span data-stu-id="63a4e-133">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="63a4e-134">将 Azure AD Graph 终结点更新为 `https://graph.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="63a4e-134">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="63a4e-135">将 MS Graph 终结点更新为 `https://graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="63a4e-135">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="63a4e-136">更新任何德语云终结点 (例如 Exchange Online 和 SharePoint Online) 的应用程序，这些终结点将由应用程序用作公共云。</span><span class="sxs-lookup"><span data-stu-id="63a4e-136">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="63a4e-137">`AzurePublic` `AzureGermany` 在管理工具和脚本中 (更新环境参数，而不是) ：</span><span class="sxs-lookup"><span data-stu-id="63a4e-137">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - <span data-ttu-id="63a4e-138">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="63a4e-138">Azure PowerShell</span></span>
    - <span data-ttu-id="63a4e-139">Azure AD PowerShell (MSOnline) </span><span class="sxs-lookup"><span data-stu-id="63a4e-139">Azure AD PowerShell (MSOnline)</span></span>
    - <span data-ttu-id="63a4e-140">Azure AD PowerShell (AzureAD) </span><span class="sxs-lookup"><span data-stu-id="63a4e-140">Azure AD PowerShell (AzureAD)</span></span>
    - <span data-ttu-id="63a4e-141">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="63a4e-141">Azure CLI</span></span>
 
<span data-ttu-id="63a4e-142">**我发布的应用程序是什么？**</span><span class="sxs-lookup"><span data-stu-id="63a4e-142">**What about applications that I publish?**</span></span>

<span data-ttu-id="63a4e-143">如果发布的应用程序对您的租户之外的用户可用，则可能需要更改应用程序注册以确保连续性。</span><span class="sxs-lookup"><span data-stu-id="63a4e-143">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="63a4e-144">使用您的应用程序的其他租户可能会在不同的时间内移动，而不是您的租户。</span><span class="sxs-lookup"><span data-stu-id="63a4e-144">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="63a4e-145">若要确保它们永远不会失去对应用程序的访问权限，您需要同意将您的应用程序从 Azure 德国同步到 Azure 公用。</span><span class="sxs-lookup"><span data-stu-id="63a4e-145">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

### <a name="additional-considerations"></a><span data-ttu-id="63a4e-146">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="63a4e-146">Additional considerations</span></span>

<span data-ttu-id="63a4e-147">下面是 Azure AD 的一些其他注意事项：</span><span class="sxs-lookup"><span data-stu-id="63a4e-147">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="63a4e-148">对于联合身份验证：</span><span class="sxs-lookup"><span data-stu-id="63a4e-148">For federated authentication:</span></span>

  - <span data-ttu-id="63a4e-149">在租户转换过程中，不能创建、升级或降级联合域。</span><span class="sxs-lookup"><span data-stu-id="63a4e-149">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="63a4e-150">在迁移到 Azure AD 服务完成之后 (租户完全完成) ，可以恢复管理联合域。</span><span class="sxs-lookup"><span data-stu-id="63a4e-150">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="63a4e-151">如果使用的是 Active Directory 联合身份验证服务 (AD FS) 的联合身份验证，则不应更改用于在迁移过程中将内部部署 Active Directory 域服务 (AD DS) 的所有身份验证所使用的颁发者 Uri。</span><span class="sxs-lookup"><span data-stu-id="63a4e-151">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="63a4e-152">更改颁发者 Uri 将导致域中用户的身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="63a4e-152">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="63a4e-153">颁发者 Uri 可以直接在 AD FS 中更改，也可以在将域从托管转换为联合时进行更改，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="63a4e-153">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="63a4e-154">Microsoft 建议客户不要在要迁移的 Azure AD 租户中添加、删除或转换联合域。</span><span class="sxs-lookup"><span data-stu-id="63a4e-154">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="63a4e-155">在迁移完全完成后，可以更改颁发者 Uri。</span><span class="sxs-lookup"><span data-stu-id="63a4e-155">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="63a4e-156">对于网络：</span><span class="sxs-lookup"><span data-stu-id="63a4e-156">For networking:</span></span>

  - <span data-ttu-id="63a4e-157">创建 IPv6 命名的网络在 Azure 门户中不起作用 `http://portal.microsoftazure.de/` 。</span><span class="sxs-lookup"><span data-stu-id="63a4e-157">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="63a4e-158">在上使用 Azure 门户 `https://portal.azure.com` 创建以 IPv6 命名的网络。</span><span class="sxs-lookup"><span data-stu-id="63a4e-158">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="63a4e-159">无法在 Microsoft 云德国门户中为 Azure 多重身份验证 (MFA) 服务设置创建受信任的 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="63a4e-159">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="63a4e-160">使用适用于 Office 365 服务的 Azure AD 门户创建 Azure MFA 受信任 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="63a4e-160">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="63a4e-161">对于条件访问：</span><span class="sxs-lookup"><span data-stu-id="63a4e-161">For Conditional Access:</span></span> 

  - <span data-ttu-id="63a4e-162">在完成 Office 365 服务的迁移之后 (的条件访问策略不受支持，直到结束 [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 迁移阶段) ：</span><span class="sxs-lookup"><span data-stu-id="63a4e-162">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="63a4e-163">需要合规设备</span><span class="sxs-lookup"><span data-stu-id="63a4e-163">Require Compliant Device</span></span>
    - <span data-ttu-id="63a4e-164">需要批准的应用程序</span><span class="sxs-lookup"><span data-stu-id="63a4e-164">Require Approved App</span></span>
    - <span data-ttu-id="63a4e-165">需要应用保护策略</span><span class="sxs-lookup"><span data-stu-id="63a4e-165">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="63a4e-166">条件访问策略接口提供了有关启用了租户的安全默认设置的错误警告，即使该租户已禁用，以及租户的条件访问策略已存在。</span><span class="sxs-lookup"><span data-stu-id="63a4e-166">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="63a4e-167">应忽略警告或使用 Office 365 服务门户来管理条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="63a4e-167">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="63a4e-168">仅在完成租户迁移之后（包括所有 office 工作负载迁移）对全球终结点支持 Intune 方案。</span><span class="sxs-lookup"><span data-stu-id="63a4e-168">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="63a4e-169">Microsoft 云德国使用移动应用程序通知方法进行 MFA 请求的用户可以看到用户的 ObjectId (GUID) ，而不是在 Microsoft 身份验证应用程序中的用户主体名称 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="63a4e-169">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="63a4e-170">在 Azure AD 租户的迁移完成且托管在 Office 365 服务中之后，新的 Microsoft 身份验证器激活将显示用户的 Upn。</span><span class="sxs-lookup"><span data-stu-id="63a4e-170">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="63a4e-171">现有的 Microsoft 身份验证器帐户将继续显示用户 ObjectId，但它们将继续适用于移动应用程序通知。</span><span class="sxs-lookup"><span data-stu-id="63a4e-171">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="63a4e-172">对于在22月 22 2019 日之后创建的租户，在将租户迁移到 Office 365 服务时，可能会为租户自动启用安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="63a4e-172">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="63a4e-173">租户管理员可以选择保持启用安全默认设置并注册进行 MFA，也可以禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="63a4e-173">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="63a4e-174">有关详细信息，请参阅 [禁用安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="63a4e-174">For more information, see [Disabling security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="63a4e-175">在迁移过程中不自动启用的组织在将来可能仍会自动注册，因为启用安全默认设置的功能将在 Office 365 服务中推出。</span><span class="sxs-lookup"><span data-stu-id="63a4e-175">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="63a4e-176">选择显式禁用或启用安全默认设置的管理员可能通过在 " **Azure Active Directory > 属性**" 下更新功能来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="63a4e-176">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="63a4e-177">在管理员显式启用了该功能后，将不会自动启用该功能。</span><span class="sxs-lookup"><span data-stu-id="63a4e-177">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="63a4e-178">只要租户处于迁移中，就会出现有关 Office 365 德国门户中的 Azure AD Connect 版本以及 Office 365 门户中的版本的警告。</span><span class="sxs-lookup"><span data-stu-id="63a4e-178">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="63a4e-179">如果在迁移完成后版本警告不再显示警告，则可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="63a4e-179">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="63a4e-180">在任何一个门户中，如果有警告（在迁移之前或之后），则必须更新 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="63a4e-180">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="63a4e-181">警告消息提示： "我们检测到你使用的是过时的目录同步工具。</span><span class="sxs-lookup"><span data-stu-id="63a4e-181">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="63a4e-182">我们建议您转到 Microsoft 下载中心以获取最新版本的 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="63a4e-182">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="exchange-online"></a><span data-ttu-id="63a4e-183">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="63a4e-183">Exchange Online</span></span> 

- <span data-ttu-id="63a4e-184">`myaccount.msft.com` 仅在切换 Office 365 后才会运行。</span><span class="sxs-lookup"><span data-stu-id="63a4e-184">`myaccount.msft.com` will only work after the cutover of Office 365.</span></span> <span data-ttu-id="63a4e-185">在此之前，链接将产生 "出现错误" 的错误消息。</span><span class="sxs-lookup"><span data-stu-id="63a4e-185">Links will produce "something went wrong" error messages until that time.</span></span>

- <span data-ttu-id="63a4e-186">在其他环境中访问共享邮箱的 Outlook Web App 用户 (例如，德国环境中的用户访问全局环境中的共享邮箱) 将再次提示进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="63a4e-186">Users of Outlook Web App that access a shared mailbox in the other environment (for example, a user in the Germany environment accesses a shared mailbox in the global environment) will be prompted to authenticate a second time.</span></span> <span data-ttu-id="63a4e-187">用户必须先进行身份验证并在中访问其邮箱 `outlook.office.de` ，然后才能打开中的共享邮箱 `outlook.office365.com` 。</span><span class="sxs-lookup"><span data-stu-id="63a4e-187">The user must first authenticate and access their mailbox in `outlook.office.de`, then open the shared mailbox that is in `outlook.office365.com`.</span></span> <span data-ttu-id="63a4e-188">他们需要在访问其他服务中托管的共享资源时第二次进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="63a4e-188">They'll need to authenticate a second time when accessing the shared resources that are hosted in the other service.</span></span>

- <span data-ttu-id="63a4e-189">对于现有的 Microsoft 云德国客户或转换中的客户，当使用文件 > 信息将共享邮箱添加到 Outlook 中时 **> 添加帐户**，查看日历权限可能会失败 (Outlook 客户端尝试使用 Rest API `https://outlook.office.de/api/v2.0/Me/Calendars` 。 ) 要添加帐户以查看日历权限的客户可以添加注册表项，如在 [outlook 中共享日历的用户体验更改](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 中所述，以确保此操作将成功。</span><span class="sxs-lookup"><span data-stu-id="63a4e-189">For existing Microsoft Cloud Deutschland customers or those in transition, when a shared mailbox is added to Outlook by using **File > Info > Add Account**, viewing calendar permissions may fail (the Outlook client attempts to use the Rest API `https://outlook.office.de/api/v2.0/Me/Calendars`.) Customers who want to add an account to view calendar permissions can add the registry key as described in [User experience changes for sharing a calendar in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) to ensure this action will succeed.</span></span> <span data-ttu-id="63a4e-190">可以使用组策略在整个组织范围内部署此注册表项。</span><span class="sxs-lookup"><span data-stu-id="63a4e-190">This registry key can be deployed organization-wide by using Group Policy.</span></span>

- <span data-ttu-id="63a4e-191">在迁移阶段，使用 PowerShell cmdlet **new-migrationendpoint**、 **new-migrationendpoint** 和 **MigrationsServerAvailability** 可能会导致代理) 上的错误 (错误。</span><span class="sxs-lookup"><span data-stu-id="63a4e-191">During the migration phase, using the PowerShell cmdlets **New-migrationEndpoint**, **Set-MigrationEndpoint**, and **Test-MigrationsServerAvailability** can result in errors (error on proxy).</span></span> <span data-ttu-id="63a4e-192">如果仲裁邮箱已迁移到全球但不是管理员邮箱，则会发生这种情况，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="63a4e-192">This happens when the arbitration mailbox has migrated to worldwide but the admin mailbox hasn't or vice-versa.</span></span> <span data-ttu-id="63a4e-193">若要解决此问题，在创建租户 PowerShell 会话时，请将仲裁邮箱用作 **ConnectionUri** 中的路由提示。</span><span class="sxs-lookup"><span data-stu-id="63a4e-193">To resolve this, while creating the tenant PowerShell session, use the arbitration mailbox as the routing hint in the **ConnectionUri**.</span></span> <span data-ttu-id="63a4e-194">例如：`New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`</span><span class="sxs-lookup"><span data-stu-id="63a4e-194">For example: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`</span></span>

- <span data-ttu-id="63a4e-195">如果您使用的是 Exchange Online 混合：</span><span class="sxs-lookup"><span data-stu-id="63a4e-195">If you're using Exchange Online hybrid:</span></span>

    - <span data-ttu-id="63a4e-196">您必须重新运行 "混合配置" 向导 (HCW) 以在转换之前更新 Microsoft 云德国的本地配置，然后在对 Office 365 服务进行清理时重新运行 HCW。</span><span class="sxs-lookup"><span data-stu-id="63a4e-196">You must rerun the Hybrid Configuration wizard (HCW) to update on-premises configuration against Microsoft Cloud Deutschland before the transition, and rerun the HCW upon cleanup against the Office 365 services.</span></span> <span data-ttu-id="63a4e-197">如果使用自定义域，则可能需要其他 DNS 更新。</span><span class="sxs-lookup"><span data-stu-id="63a4e-197">Additional DNS updates may be required if you use custom domains.</span></span>

<span data-ttu-id="63a4e-198">若要详细了解在此工作负载的迁移阶段中所需的操作或关于管理或使用的影响，请查看 [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md#exchange-online)的 Exchange Online 部分。</span><span class="sxs-lookup"><span data-stu-id="63a4e-198">For more information about actions that are required during the migration phase of this workload or about the impact to administration or usage, review the Exchange Online section of [Migration phases actions and impacts](ms-cloud-germany-transition-phases.md#exchange-online).</span></span>

## <a name="office-services"></a><span data-ttu-id="63a4e-199">Office 服务</span><span class="sxs-lookup"><span data-stu-id="63a4e-199">Office Services</span></span>

<span data-ttu-id="63a4e-200">Office 中最近使用的 (MRU) 服务是从德国服务切换到 Office 365 服务（而不是迁移）的。</span><span class="sxs-lookup"><span data-stu-id="63a4e-200">The most recently used (MRU) service in Office is a cutover from the Germany service to Office 365 services, not a migration.</span></span> <span data-ttu-id="63a4e-201">从 Office.com 门户迁移后，只有来自 Office 365 服务端的 MRU 链接才会可见。</span><span class="sxs-lookup"><span data-stu-id="63a4e-201">Only MRU links from the Office 365 services side will be visible after migration from the Office.com portal.</span></span> <span data-ttu-id="63a4e-202">来自德国服务的 MRU 链接在 Office 365 服务中不会显示为 MRU 链接。</span><span class="sxs-lookup"><span data-stu-id="63a4e-202">MRU links from the Germany service aren't visible as MRU links in Office 365 services.</span></span> <span data-ttu-id="63a4e-203">在 Office 365 中，只有完成租户迁移后，才能访问 MRU 链接。</span><span class="sxs-lookup"><span data-stu-id="63a4e-203">In Office 365, MRU links are accessible only after the tenant migration is complete.</span></span>

## <a name="sharepoint-online-and-onedrive"></a><span data-ttu-id="63a4e-204">SharePoint Online 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="63a4e-204">SharePoint Online and OneDrive</span></span>

- <span data-ttu-id="63a4e-205">在将 SharePoint Online 迁移到德国区域之后，会重新生成数据索引。</span><span class="sxs-lookup"><span data-stu-id="63a4e-205">Upon completion of the SharePoint Online migration to the German region, data indexes are rebuilt.</span></span> <span data-ttu-id="63a4e-206">因索引编制完成时，依赖搜索索引的功能可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="63a4e-206">Features that are dependent on search indexes may be affected while reindexing completes.</span></span>

- <span data-ttu-id="63a4e-207">如果您的组织仍在使用 SharePoint 2010 工作流，则在2021年12月31日之后，它们将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="63a4e-207">If your organization still uses SharePoint 2010 workflows, they'll no longer function after December 31, 2021.</span></span> <span data-ttu-id="63a4e-208">默认情况下，SharePoint 2013 工作流仍受支持，但对于从 2020 1 月1日开始的新租户为默认禁用。</span><span class="sxs-lookup"><span data-stu-id="63a4e-208">SharePoint 2013 workflows will remain supported, although turned off by default for new tenants starting on November 1, 2020.</span></span> <span data-ttu-id="63a4e-209">完成到 SharePoint Online 服务的迁移后，我们建议您移动到 "电源自动化" 或其他受支持的解决方案。</span><span class="sxs-lookup"><span data-stu-id="63a4e-209">After migration to the SharePoint Online service is complete, we recommend that you to move to Power Automate or other supported solutions.</span></span>

- <span data-ttu-id="63a4e-210">在将 OneDrive 迁移到德语区域完成后，将重建数据索引。</span><span class="sxs-lookup"><span data-stu-id="63a4e-210">Upon completion of the OneDrive migration to the German region, data indexes are rebuilt.</span></span> <span data-ttu-id="63a4e-211">在重建索引过程中，依赖搜索索引的功能可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="63a4e-211">Features that depend on search indexes may be affected while reindexing is in progress.</span></span>


## <a name="more-information"></a><span data-ttu-id="63a4e-212">详细信息</span><span class="sxs-lookup"><span data-stu-id="63a4e-212">More information</span></span>

<span data-ttu-id="63a4e-213">入门：</span><span class="sxs-lookup"><span data-stu-id="63a4e-213">Getting started:</span></span>

- [<span data-ttu-id="63a4e-214">从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务</span><span class="sxs-lookup"><span data-stu-id="63a4e-214">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="63a4e-215">德国 Microsoft 云迁移助手</span><span class="sxs-lookup"><span data-stu-id="63a4e-215">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="63a4e-216">如何选择加入迁移</span><span class="sxs-lookup"><span data-stu-id="63a4e-216">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="63a4e-217">迁移过程中的客户体验</span><span class="sxs-lookup"><span data-stu-id="63a4e-217">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="63a4e-218">在转换中移动：</span><span class="sxs-lookup"><span data-stu-id="63a4e-218">Moving through the transition:</span></span>

- [<span data-ttu-id="63a4e-219">迁移阶段的操作和影响</span><span class="sxs-lookup"><span data-stu-id="63a4e-219">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="63a4e-220">其他预备工作</span><span class="sxs-lookup"><span data-stu-id="63a4e-220">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="63a4e-221">[服务](ms-cloud-germany-transition-add-general.md)、[设备](ms-cloud-germany-transition-add-devices.md)、[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他信息。</span><span class="sxs-lookup"><span data-stu-id="63a4e-221">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="63a4e-222">云应用：</span><span class="sxs-lookup"><span data-stu-id="63a4e-222">Cloud apps:</span></span>

- [<span data-ttu-id="63a4e-223">Dynamics 365 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="63a4e-223">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="63a4e-224">Power BI 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="63a4e-224">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="63a4e-225">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="63a4e-225">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
