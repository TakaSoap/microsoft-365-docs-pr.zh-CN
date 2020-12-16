---
title: 从德国 Microsoft 云迁移的其他 Azure Active Directory 信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: 摘要：从德国 Microsoft 云 (德国 microsoft 云) 迁移到新的德国数据中心区域中的 Office 365 服务时的其他 Azure Active Directory 信息。
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688712"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="78cdc-103">从德国 Microsoft 云迁移的其他 Azure Active Directory 信息</span><span class="sxs-lookup"><span data-stu-id="78cdc-103">Additional Azure Active Directory information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="78cdc-104">若要完成从 Azure 德国云到 Azure 公共云的迁移，我们建议在 OpenID Connect (OIDC) 终结点开始报告商业云终结点时，将应用程序的身份验证终结点、Azure Active Directory (Azure AD) Graph 和 MS Graph 终结点更新为商业云终结点。 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`</span><span class="sxs-lookup"><span data-stu-id="78cdc-104">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="78cdc-105">**我应在何时进行此更改？**</span><span class="sxs-lookup"><span data-stu-id="78cdc-105">**When should I make this change?**</span></span>

<span data-ttu-id="78cdc-106">当你的租户完成从德国云到商业云的迁移时，你将在 Azure/Office 门户中收到通知。</span><span class="sxs-lookup"><span data-stu-id="78cdc-106">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="78cdc-107">在收到此通知后 30 天内完成这些更新，以便应用继续适用于从 Azure Germany 云迁移到 Azure 公共云的租户。</span><span class="sxs-lookup"><span data-stu-id="78cdc-107">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="78cdc-108">更新登录权限有三个先决条件：</span><span class="sxs-lookup"><span data-stu-id="78cdc-108">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="78cdc-109">租户的 OIDC 发现终结点 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 返回 Azure AD 公共云终结点。</span><span class="sxs-lookup"><span data-stu-id="78cdc-109">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="78cdc-110">如果为联合身份验证设置租户，Active Directory 联合身份验证服务 (AD FS) 更新为与 Azure AD Public 同步。</span><span class="sxs-lookup"><span data-stu-id="78cdc-110">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="78cdc-111">你可以按照说明更新 Azure AD Connect 设置以进行此更改。</span><span class="sxs-lookup"><span data-stu-id="78cdc-111">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="78cdc-112">应用程序使用的资源应用程序（如果有）将修改为接受由 Azure AD Germany 和 Azure AD Public 签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="78cdc-112">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="78cdc-113">**哪种类型的应用程序？**</span><span class="sxs-lookup"><span data-stu-id="78cdc-113">**What kind of applications?**</span></span>

<span data-ttu-id="78cdc-114">应用程序可以是以下任一应用程序：</span><span class="sxs-lookup"><span data-stu-id="78cdc-114">An application could be any of the following:</span></span>

- [<span data-ttu-id="78cdc-115">SPA 应用程序的单页 (应用程序) </span><span class="sxs-lookup"><span data-stu-id="78cdc-115">Single-page app (SPA)</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="78cdc-116">登录用户的 Web 应用</span><span class="sxs-lookup"><span data-stu-id="78cdc-116">Web app that signs in users</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="78cdc-117">调用 Web API 的 Web 应用</span><span class="sxs-lookup"><span data-stu-id="78cdc-117">Web app that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="78cdc-118">受保护的 Web API</span><span class="sxs-lookup"><span data-stu-id="78cdc-118">Protected web API</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="78cdc-119">调用 Web API 的 Web API</span><span class="sxs-lookup"><span data-stu-id="78cdc-119">Web API that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="78cdc-120">桌面应用</span><span class="sxs-lookup"><span data-stu-id="78cdc-120">Desktop app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="78cdc-121">守护程序应用</span><span class="sxs-lookup"><span data-stu-id="78cdc-121">Daemon app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="78cdc-122">移动应用</span><span class="sxs-lookup"><span data-stu-id="78cdc-122">Mobile app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="78cdc-123">当应用程序切换到使用作为你的颁发机构时，此新颁发机构 `login.microsoftonline.com` 将签署令牌。</span><span class="sxs-lookup"><span data-stu-id="78cdc-123">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="78cdc-124">如果托管其他应用调用的任何资源应用程序，则需要允许 lax 令牌验证。</span><span class="sxs-lookup"><span data-stu-id="78cdc-124">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="78cdc-125">这意味着你的应用需要允许由 Azure AD Germany 和 Azure AD 公共云签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="78cdc-125">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="78cdc-126">在调用你的服务的所有客户端应用程序完全迁移到 Azure AD 公共云之前，需要此淡出令牌验证。</span><span class="sxs-lookup"><span data-stu-id="78cdc-126">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="78cdc-127">迁移后，你的资源应用程序只需接受 Azure AD 公共云签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="78cdc-127">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="78cdc-128">**我需要更新哪些内容？**</span><span class="sxs-lookup"><span data-stu-id="78cdc-128">**What do I need to update?**</span></span>

1. <span data-ttu-id="78cdc-129">如果你正在 Azure Germany 中托管用于对 Azure Germany 或 Office 365 Germany 用户进行身份验证的应用程序，请确保在身份验证上下文中用作 `https://login.microsoftonline.com` 颁发机构。</span><span class="sxs-lookup"><span data-stu-id="78cdc-129">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="78cdc-130">请参阅 Azure AD 身份验证上下文。</span><span class="sxs-lookup"><span data-stu-id="78cdc-130">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="78cdc-131">这既适用于对应用程序的身份验证，也适用于对应用程序可能调用 (（即 Microsoft Graph、Azure AD Graph、Azure Resource Manager) ）的任何 API 的身份验证。</span><span class="sxs-lookup"><span data-stu-id="78cdc-131">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="78cdc-132">将 Azure AD Graph 终结点更新为 `https://graph.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="78cdc-132">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="78cdc-133">将 MS Graph 终结点更新为 `https://graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="78cdc-133">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="78cdc-134">将应用程序使用的任何德国 (（如 Exchange Online 和 SharePoint Online) 的终结点）更新为公共云终结点。</span><span class="sxs-lookup"><span data-stu-id="78cdc-134">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="78cdc-135">更新要更新的环境 `AzurePublic` 参数 (而不是) 管理工具和脚本中的 `AzureGermany` 参数：</span><span class="sxs-lookup"><span data-stu-id="78cdc-135">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="78cdc-136">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="78cdc-136">Azure PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [<span data-ttu-id="78cdc-137">Azure AD PowerShell (MSOnline) </span><span class="sxs-lookup"><span data-stu-id="78cdc-137">Azure AD PowerShell (MSOnline)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [<span data-ttu-id="78cdc-138">Azure AD PowerShell (AzureAD) </span><span class="sxs-lookup"><span data-stu-id="78cdc-138">Azure AD PowerShell (AzureAD)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [<span data-ttu-id="78cdc-139">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="78cdc-139">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
<span data-ttu-id="78cdc-140">**我发布的应用程序如何？**</span><span class="sxs-lookup"><span data-stu-id="78cdc-140">**What about applications that I publish?**</span></span>

<span data-ttu-id="78cdc-141">如果发布可供租户外部用户使用的应用程序，可能需要更改应用程序注册以确保连续性。</span><span class="sxs-lookup"><span data-stu-id="78cdc-141">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="78cdc-142">使用应用程序的其他租户的移动时间可能不同于租户。</span><span class="sxs-lookup"><span data-stu-id="78cdc-142">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="78cdc-143">若要确保他们永远不会失去对应用程序的访问权限，你将需要同意将应用从 Azure Germany 同步到 Azure 公共。</span><span class="sxs-lookup"><span data-stu-id="78cdc-143">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="78cdc-144">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="78cdc-144">Additional considerations</span></span>

<span data-ttu-id="78cdc-145">以下是 Azure AD 的一些其他注意事项：</span><span class="sxs-lookup"><span data-stu-id="78cdc-145">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="78cdc-146">对于联合身份验证：</span><span class="sxs-lookup"><span data-stu-id="78cdc-146">For federated authentication:</span></span>

  - <span data-ttu-id="78cdc-147">在租户转换过程中，不得创建、升级或降级联合域。</span><span class="sxs-lookup"><span data-stu-id="78cdc-147">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="78cdc-148">在租户完全完成迁移后， (Azure AD 服务) ，可以恢复管理联合域。</span><span class="sxs-lookup"><span data-stu-id="78cdc-148">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="78cdc-149">如果将联合身份验证与 Active Directory 联合身份验证服务 (AD FS) 一起使用，则不应更改在迁移期间用于本地 Active Directory 域服务 (AD DS) 的所有身份验证的颁发者 URI。</span><span class="sxs-lookup"><span data-stu-id="78cdc-149">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="78cdc-150">更改颁发者 URI 将导致域中用户的身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="78cdc-150">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="78cdc-151">颁发者 URI 可以直接在 AD FS 中更改，或在域从托管转换为联合时更改，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="78cdc-151">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="78cdc-152">Microsoft 建议客户不要在要迁移的 Azure AD 租户中添加、删除或转换联合域。</span><span class="sxs-lookup"><span data-stu-id="78cdc-152">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="78cdc-153">在迁移完成之后，可更改颁发者 URI。</span><span class="sxs-lookup"><span data-stu-id="78cdc-153">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="78cdc-154">对于网络：</span><span class="sxs-lookup"><span data-stu-id="78cdc-154">For networking:</span></span>

  - <span data-ttu-id="78cdc-155">创建以 IPv6 命名的网络在 Azure 门户中不起作用 `http://portal.microsoftazure.de/` 。</span><span class="sxs-lookup"><span data-stu-id="78cdc-155">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="78cdc-156">使用 Azure 门户创建 `https://portal.azure.com` 以 IPv6 命名的网络。</span><span class="sxs-lookup"><span data-stu-id="78cdc-156">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="78cdc-157">无法从 Microsoft 云德国门户为 Azure 多重身份验证创建受信任的 IP 地址范围 (MFA) 服务设置。</span><span class="sxs-lookup"><span data-stu-id="78cdc-157">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="78cdc-158">使用适用于 Office 365 服务的 Azure AD 门户创建 Azure MFA 受信任 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="78cdc-158">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="78cdc-159">对于条件访问：</span><span class="sxs-lookup"><span data-stu-id="78cdc-159">For Conditional Access:</span></span> 

  - <span data-ttu-id="78cdc-160">在完成 [Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 迁移阶段之后完成迁移到 Office 365 服务 (以下授予控制的条件访问策略) ：</span><span class="sxs-lookup"><span data-stu-id="78cdc-160">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="78cdc-161">需要兼容设备</span><span class="sxs-lookup"><span data-stu-id="78cdc-161">Require Compliant Device</span></span>
    - <span data-ttu-id="78cdc-162">需要批准的应用</span><span class="sxs-lookup"><span data-stu-id="78cdc-162">Require Approved App</span></span>
    - <span data-ttu-id="78cdc-163">需要应用保护策略</span><span class="sxs-lookup"><span data-stu-id="78cdc-163">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="78cdc-164">条件访问策略接口会针对为租户启用安全默认值（即使禁用该接口时）发出警告，并且租户已存在条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="78cdc-164">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="78cdc-165">应忽略警告或使用 Office 365 服务门户管理条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="78cdc-165">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="78cdc-166">租户迁移完成后，仅针对全球终结点支持 Intune 方案，包括所有 Office 工作负载迁移。</span><span class="sxs-lookup"><span data-stu-id="78cdc-166">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="78cdc-167">对 MFA 请求使用移动应用通知方法的 Microsoft 云德国用户会看到用户的 ObjectId (GUID) ，而不是 Microsoft Authenticator 应用中的用户主体名称 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="78cdc-167">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="78cdc-168">完成 Azure AD 租户迁移并托管在 Office 365 服务中后，新的 Microsoft Authenticator 激活将显示用户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="78cdc-168">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="78cdc-169">现有 Microsoft Authenticator 帐户将继续显示用户 ObjectId，但它们将继续用于移动应用通知。</span><span class="sxs-lookup"><span data-stu-id="78cdc-169">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="78cdc-170">对于在 2019 年 10 月 22 日之后创建的租户，当租户迁移到 Office 365 服务时，可能会为租户自动启用安全默认值。</span><span class="sxs-lookup"><span data-stu-id="78cdc-170">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="78cdc-171">租户管理员可以选择保持启用安全默认值并注册 MFA，也可以禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="78cdc-171">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="78cdc-172">有关详细信息，请参阅"[禁用安全默认值"。](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="78cdc-172">For more information, see [Disabling security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="78cdc-173">由于 Office 365 服务中推出启用安全默认值的功能，因此在迁移期间未自动启用的组织将来仍可以自动注册。</span><span class="sxs-lookup"><span data-stu-id="78cdc-173">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="78cdc-174">选择显式禁用或启用安全默认值的管理员可以通过更新 Azure Active Directory > **属性下的功能来这样做**。</span><span class="sxs-lookup"><span data-stu-id="78cdc-174">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="78cdc-175">在管理员显式启用该功能后，它将不会自动启用。</span><span class="sxs-lookup"><span data-stu-id="78cdc-175">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="78cdc-176">租户迁移后，将在 Office 365 Germany 门户和 Office 365 门户中显示有关 Azure AD Connect 版本的警告。</span><span class="sxs-lookup"><span data-stu-id="78cdc-176">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="78cdc-177">如果迁移完成后版本警告不再显示警告，可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="78cdc-177">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="78cdc-178">如果在迁移之前或之后在任一门户中出现警告，则必须更新 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="78cdc-178">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="78cdc-179">警告消息显示："我们检测到你正在使用过时的目录同步工具。</span><span class="sxs-lookup"><span data-stu-id="78cdc-179">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="78cdc-180">我们建议你转到 Microsoft 下载中心，获取最新版本的 Azure AD Connect。"</span><span class="sxs-lookup"><span data-stu-id="78cdc-180">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="more-information"></a><span data-ttu-id="78cdc-181">更多信息</span><span class="sxs-lookup"><span data-stu-id="78cdc-181">More information</span></span>

<span data-ttu-id="78cdc-182">入门：</span><span class="sxs-lookup"><span data-stu-id="78cdc-182">Getting started:</span></span>

- [<span data-ttu-id="78cdc-183">从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务</span><span class="sxs-lookup"><span data-stu-id="78cdc-183">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="78cdc-184">德国 Microsoft 云迁移助手</span><span class="sxs-lookup"><span data-stu-id="78cdc-184">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="78cdc-185">如何选择加入迁移</span><span class="sxs-lookup"><span data-stu-id="78cdc-185">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="78cdc-186">迁移期间客户体验</span><span class="sxs-lookup"><span data-stu-id="78cdc-186">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="78cdc-187">在转换过程中移动：</span><span class="sxs-lookup"><span data-stu-id="78cdc-187">Moving through the transition:</span></span>

- [<span data-ttu-id="78cdc-188">迁移阶段操作和影响</span><span class="sxs-lookup"><span data-stu-id="78cdc-188">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="78cdc-189">其他预工作</span><span class="sxs-lookup"><span data-stu-id="78cdc-189">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="78cdc-190">Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。</span><span class="sxs-lookup"><span data-stu-id="78cdc-190">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="78cdc-191">云应用：</span><span class="sxs-lookup"><span data-stu-id="78cdc-191">Cloud apps:</span></span>

- [<span data-ttu-id="78cdc-192">Dynamics 365 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="78cdc-192">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="78cdc-193">Power BI 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="78cdc-193">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="78cdc-194">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="78cdc-194">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
