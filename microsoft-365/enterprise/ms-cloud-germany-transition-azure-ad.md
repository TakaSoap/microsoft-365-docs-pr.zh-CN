---
title: 有关Azure Active Directory德国 Microsoft 云的迁移的其他详细信息
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
description: 摘要：从德国 Microsoft 云Azure Active Directory德国 microsoft 云 (迁移到新的德国数据中心) Office 365服务时的其他详细信息。
ms.openlocfilehash: 0e7abd68945a9b685a33c120ff1e92fda62b2c56
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362722"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="a10ba-103">有关Azure Active Directory德国 Microsoft 云的迁移的其他详细信息</span><span class="sxs-lookup"><span data-stu-id="a10ba-103">Additional Azure Active Directory information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="a10ba-104">若要完成从 Azure 德国云到 Azure 公共云的迁移，我们建议在 OpenID 连接 (OIDC) 终结点开始报告商业云终结点时，将应用程序的身份验证终结点、Azure Active Directory (Azure AD) Graph 和 MS Graph 终结点更新为商业云终结点。 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`</span><span class="sxs-lookup"><span data-stu-id="a10ba-104">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="a10ba-105">**何时应进行此更改？**</span><span class="sxs-lookup"><span data-stu-id="a10ba-105">**When should I make this change?**</span></span>

<span data-ttu-id="a10ba-106">当你的租户完成从德国云到商业云的迁移Office Azure/Office门户中，你将收到一条通知。</span><span class="sxs-lookup"><span data-stu-id="a10ba-106">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="a10ba-107">在收到此通知后 30 天内完成这些更新，以便应用继续适用于从 Azure Germany 云迁移到 Azure 公共云的租户。</span><span class="sxs-lookup"><span data-stu-id="a10ba-107">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="a10ba-108">更新登录权限有三个先决条件：</span><span class="sxs-lookup"><span data-stu-id="a10ba-108">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="a10ba-109">租户的 OIDC 发现终结点 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 返回 Azure AD 公共云终结点。</span><span class="sxs-lookup"><span data-stu-id="a10ba-109">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="a10ba-110">如果为租户设置了联合身份验证，Active Directory 联合身份验证服务 (AD FS) 更新为与 Azure AD Public 同步。</span><span class="sxs-lookup"><span data-stu-id="a10ba-110">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="a10ba-111">你可以按照说明更新 Azure AD 连接进行此更改的设置。</span><span class="sxs-lookup"><span data-stu-id="a10ba-111">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="a10ba-112">应用程序使用的资源应用程序（如果有）将修改为接受由 Azure AD Germany 和 Azure AD Public 签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="a10ba-112">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="a10ba-113">**哪种类型的应用程序？**</span><span class="sxs-lookup"><span data-stu-id="a10ba-113">**What kind of applications?**</span></span>

<span data-ttu-id="a10ba-114">应用程序可以是以下任一应用程序：</span><span class="sxs-lookup"><span data-stu-id="a10ba-114">An application could be any of the following:</span></span>

- [<span data-ttu-id="a10ba-115">SPA 应用程序 (单页) </span><span class="sxs-lookup"><span data-stu-id="a10ba-115">Single-page app (SPA)</span></span>](/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="a10ba-116">登录用户的 Web 应用</span><span class="sxs-lookup"><span data-stu-id="a10ba-116">Web app that signs in users</span></span>](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="a10ba-117">调用 Web API 的 Web 应用</span><span class="sxs-lookup"><span data-stu-id="a10ba-117">Web app that calls web APIs</span></span>](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="a10ba-118">受保护的 Web API</span><span class="sxs-lookup"><span data-stu-id="a10ba-118">Protected web API</span></span>](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="a10ba-119">调用 Web API 的 Web API</span><span class="sxs-lookup"><span data-stu-id="a10ba-119">Web API that calls web APIs</span></span>](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="a10ba-120">桌面应用</span><span class="sxs-lookup"><span data-stu-id="a10ba-120">Desktop app</span></span>](/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="a10ba-121">守护程序应用</span><span class="sxs-lookup"><span data-stu-id="a10ba-121">Daemon app</span></span>](/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="a10ba-122">移动应用</span><span class="sxs-lookup"><span data-stu-id="a10ba-122">Mobile app</span></span>](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="a10ba-123">当应用程序切换到使用 作为颁发机构时，此新颁发机构 `login.microsoftonline.com` 将签署令牌。</span><span class="sxs-lookup"><span data-stu-id="a10ba-123">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="a10ba-124">如果你托管了其他应用程序调用的任何资源应用程序，则需要允许令牌验证。</span><span class="sxs-lookup"><span data-stu-id="a10ba-124">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="a10ba-125">这意味着你的应用需要允许由 Azure AD Germany 和 Azure AD 公共云签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="a10ba-125">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="a10ba-126">在调用你的服务的所有客户端应用程序完全迁移到 Azure AD 公共云之前，需要此令牌验证。</span><span class="sxs-lookup"><span data-stu-id="a10ba-126">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="a10ba-127">迁移后，你的资源应用程序只需接受 Azure AD 公共云签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="a10ba-127">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="a10ba-128">**我需要更新哪些内容？**</span><span class="sxs-lookup"><span data-stu-id="a10ba-128">**What do I need to update?**</span></span>

1. <span data-ttu-id="a10ba-129">如果你要在德国 Azure 中托管用于对 Azure 德国或 Office 365用户进行身份验证的应用程序，请确保在身份验证上下文中用作 `https://login.microsoftonline.com` 颁发机构。</span><span class="sxs-lookup"><span data-stu-id="a10ba-129">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="a10ba-130">请参阅 Azure AD 身份验证上下文。</span><span class="sxs-lookup"><span data-stu-id="a10ba-130">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="a10ba-131">这既适用于对应用程序的身份验证，也适用于应用程序可能调用 (的任何 API 的身份验证，即 Microsoft Graph、Azure AD Graph、Azure 资源管理器) 。</span><span class="sxs-lookup"><span data-stu-id="a10ba-131">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="a10ba-132">将 Azure AD Graph 终结点更新为 `https://graph.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="a10ba-132">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="a10ba-133">将 MS Graph 终结点更新为 `https://graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="a10ba-133">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="a10ba-134">将任何德国云终结点 (，如 Exchange Online 和 SharePoint Online) ，应用程序使用它们作为公共云终结点。</span><span class="sxs-lookup"><span data-stu-id="a10ba-134">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="a10ba-135">更新要更新的环境 `AzurePublic` (，) `AzureGermany` 管理工具和脚本中更新这些参数：</span><span class="sxs-lookup"><span data-stu-id="a10ba-135">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="a10ba-136">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="a10ba-136">Azure PowerShell</span></span>](/powershell/azure/install-az-ps)
    - [<span data-ttu-id="a10ba-137">Azure AD PowerShell (MSOnline) </span><span class="sxs-lookup"><span data-stu-id="a10ba-137">Azure AD PowerShell (MSOnline)</span></span>](/powershell/azure/active-directory/overview)
    - [<span data-ttu-id="a10ba-138">Azure AD PowerShell (AzureAD) </span><span class="sxs-lookup"><span data-stu-id="a10ba-138">Azure AD PowerShell (AzureAD)</span></span>](/powershell/azure/active-directory/install-adv2)
    - [<span data-ttu-id="a10ba-139">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="a10ba-139">Azure CLI</span></span>](/cli/azure/install-azure-cli)
 
<span data-ttu-id="a10ba-140">**我发布的应用程序呢？**</span><span class="sxs-lookup"><span data-stu-id="a10ba-140">**What about applications that I publish?**</span></span>

<span data-ttu-id="a10ba-141">如果发布可供租户外部用户使用的应用程序，可能需要更改应用程序注册以确保连续性。</span><span class="sxs-lookup"><span data-stu-id="a10ba-141">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="a10ba-142">使用应用程序的其他租户可能在与租户不同的时间移动。</span><span class="sxs-lookup"><span data-stu-id="a10ba-142">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="a10ba-143">若要确保用户不会丢失对应用程序的访问权限，你将需要同意将应用从 Azure 德国同步到 Azure 公共。</span><span class="sxs-lookup"><span data-stu-id="a10ba-143">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

<span data-ttu-id="a10ba-144">**在迁移期间添加新的多租户应用程序如何？**</span><span class="sxs-lookup"><span data-stu-id="a10ba-144">**What about adding new multi-tenant applications during migration?**</span></span>

<span data-ttu-id="a10ba-145">如果要使用由另一个组织发布的新应用程序 (多租户应用程序) 你将在迁移过程（第 2 阶段至第 9 阶段）期间 (限制你添加该应用程序) 。</span><span class="sxs-lookup"><span data-stu-id="a10ba-145">If you want to consume a new application that is published by another organization (multi-tenant application) you will be restricted from adding that application during the migration process (phases 2 through phase 9).</span></span>  <span data-ttu-id="a10ba-146">当你的组织完成第 9 阶段并完全转换到 Azure 公共实例时，你可以执行此任务。</span><span class="sxs-lookup"><span data-stu-id="a10ba-146">You may execute this task when your organization completes phase 9 and is fully transitioned to the Azure public instance.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="a10ba-147">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="a10ba-147">Additional considerations</span></span>

<span data-ttu-id="a10ba-148">下面是 Azure AD 的一些其他注意事项：</span><span class="sxs-lookup"><span data-stu-id="a10ba-148">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="a10ba-149">对于联合身份验证：</span><span class="sxs-lookup"><span data-stu-id="a10ba-149">For federated authentication:</span></span>

  - <span data-ttu-id="a10ba-150">在租户转换过程中，不得创建、升级或降级联合域。</span><span class="sxs-lookup"><span data-stu-id="a10ba-150">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="a10ba-151">在租户完全完成迁移 (Azure AD 服务) ，可以恢复管理联盟域。</span><span class="sxs-lookup"><span data-stu-id="a10ba-151">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="a10ba-152">如果对 Active Directory 联合身份验证服务 (AD FS) 使用联合身份验证，则不应对用于迁移期间本地 Active Directory 域服务 (AD DS) 的所有身份验证的颁发者 URI 进行更改。</span><span class="sxs-lookup"><span data-stu-id="a10ba-152">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="a10ba-153">更改颁发者 URI 将导致域中用户的身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="a10ba-153">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="a10ba-154">颁发者 URI 可以直接在 AD FS 中更改，或在将域从托管域转换为联盟域时更改，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a10ba-154">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="a10ba-155">Microsoft 建议客户不要在要迁移的 Azure AD 租户中添加、删除或转换联合域。</span><span class="sxs-lookup"><span data-stu-id="a10ba-155">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="a10ba-156">完全完成迁移后，可更改颁发者 URI。</span><span class="sxs-lookup"><span data-stu-id="a10ba-156">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="a10ba-157">对于网络：</span><span class="sxs-lookup"><span data-stu-id="a10ba-157">For networking:</span></span>

  - <span data-ttu-id="a10ba-158">创建以 IPv6 命名的网络在 Azure 门户中不起作用 `http://portal.microsoftazure.de/` 。</span><span class="sxs-lookup"><span data-stu-id="a10ba-158">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="a10ba-159">使用 Azure 门户 ，创建 `https://portal.azure.com` 以 IPv6 命名的网络。</span><span class="sxs-lookup"><span data-stu-id="a10ba-159">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="a10ba-160">无法从 Microsoft 云德国门户为 Azure 多重身份验证创建受信任的 IP 地址 (MFA) 服务设置。</span><span class="sxs-lookup"><span data-stu-id="a10ba-160">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="a10ba-161">使用 Azure AD 门户创建Office 365 Azure MFA 受信任 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="a10ba-161">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="a10ba-162">对于条件访问：</span><span class="sxs-lookup"><span data-stu-id="a10ba-162">For Conditional Access:</span></span> 

  - <span data-ttu-id="a10ba-163">在最终完成[Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized)迁移阶段完成后，Office 365服务 (以下授予控制的条件访问策略) ：</span><span class="sxs-lookup"><span data-stu-id="a10ba-163">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="a10ba-164">需要兼容设备</span><span class="sxs-lookup"><span data-stu-id="a10ba-164">Require Compliant Device</span></span>
    - <span data-ttu-id="a10ba-165">需要批准的应用</span><span class="sxs-lookup"><span data-stu-id="a10ba-165">Require Approved App</span></span>
    - <span data-ttu-id="a10ba-166">需要应用保护策略</span><span class="sxs-lookup"><span data-stu-id="a10ba-166">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="a10ba-167">条件访问策略接口会针对为租户启用安全默认值（即使已禁用）以及租户已存在的条件访问策略，提供一个假警告。</span><span class="sxs-lookup"><span data-stu-id="a10ba-167">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="a10ba-168">应忽略警告或使用 Office 365门户管理条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="a10ba-168">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="a10ba-169">租户迁移完成后，仅针对全球终结点支持 Intune 方案，包括所有 Office 工作负载迁移。</span><span class="sxs-lookup"><span data-stu-id="a10ba-169">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="a10ba-170">对 MFA 请求使用移动应用通知方法的 Microsoft 云德国用户会看到用户的 ObjectId (GUID) 而不是 Microsoft Authenticator 应用中的用户主体名称 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="a10ba-170">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="a10ba-171">完成 Azure AD 租户的迁移并托管在 Office 365 服务中后，新的 Microsoft Authenticator 激活将显示用户的 UPN。</span><span class="sxs-lookup"><span data-stu-id="a10ba-171">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="a10ba-172">现有Microsoft Authenticator帐户将继续显示用户 ObjectId，但它们将继续用于移动应用通知。</span><span class="sxs-lookup"><span data-stu-id="a10ba-172">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="a10ba-173">对于在 2019 年 10 月 22 日之后创建的租户，当租户迁移到 Office 365 服务时，可能会为租户自动启用安全默认值。</span><span class="sxs-lookup"><span data-stu-id="a10ba-173">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="a10ba-174">租户管理员可以选择保持启用安全默认值并注册 MFA，也可以禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="a10ba-174">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="a10ba-175">有关详细信息，请参阅 [禁用安全默认值](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="a10ba-175">For more information, see [Disabling security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="a10ba-176">迁移期间未自动启用的组织将来可能仍可以自动注册，因为启用安全默认值的功能在 Office 365 服务中推出。</span><span class="sxs-lookup"><span data-stu-id="a10ba-176">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="a10ba-177">选择显式禁用或启用安全默认值的管理员可以通过更新"属性"下的"Azure Active Directory >**来这样做**。</span><span class="sxs-lookup"><span data-stu-id="a10ba-177">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="a10ba-178">在管理员显式启用该功能后，它将不会自动启用。</span><span class="sxs-lookup"><span data-stu-id="a10ba-178">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="a10ba-179">租户迁移后，将在 Office 365 Germany 门户和 Office 365 门户中显示有关 Azure AD 连接 版本的警告。</span><span class="sxs-lookup"><span data-stu-id="a10ba-179">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="a10ba-180">如果迁移完成后版本警告不再显示警告，可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="a10ba-180">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="a10ba-181">如果在迁移之前或之后在任一门户中出现警告，则必须连接 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="a10ba-181">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="a10ba-182">警告消息显示："我们检测到你正在使用过时的目录同步工具。</span><span class="sxs-lookup"><span data-stu-id="a10ba-182">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="a10ba-183">我们建议你转到 Microsoft 下载中心，获取最新版 Azure AD 连接。"</span><span class="sxs-lookup"><span data-stu-id="a10ba-183">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="more-information"></a><span data-ttu-id="a10ba-184">更多信息</span><span class="sxs-lookup"><span data-stu-id="a10ba-184">More information</span></span>

<span data-ttu-id="a10ba-185">入门：</span><span class="sxs-lookup"><span data-stu-id="a10ba-185">Getting started:</span></span>

- [<span data-ttu-id="a10ba-186">从德国 Microsoft 云迁移到Office 365新的德国数据中心区域提供服务</span><span class="sxs-lookup"><span data-stu-id="a10ba-186">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="a10ba-187">德国 Microsoft 云迁移助手</span><span class="sxs-lookup"><span data-stu-id="a10ba-187">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="a10ba-188">如何选择加入迁移</span><span class="sxs-lookup"><span data-stu-id="a10ba-188">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="a10ba-189">迁移期间客户体验</span><span class="sxs-lookup"><span data-stu-id="a10ba-189">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="a10ba-190">在转换过程中移动：</span><span class="sxs-lookup"><span data-stu-id="a10ba-190">Moving through the transition:</span></span>

- [<span data-ttu-id="a10ba-191">迁移阶段操作和影响</span><span class="sxs-lookup"><span data-stu-id="a10ba-191">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="a10ba-192">其他前期工作</span><span class="sxs-lookup"><span data-stu-id="a10ba-192">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="a10ba-193">Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。</span><span class="sxs-lookup"><span data-stu-id="a10ba-193">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="a10ba-194">云应用：</span><span class="sxs-lookup"><span data-stu-id="a10ba-194">Cloud apps:</span></span>

- [<span data-ttu-id="a10ba-195">Dynamics 365 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="a10ba-195">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="a10ba-196">Power BI 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="a10ba-196">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="a10ba-197">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="a10ba-197">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
