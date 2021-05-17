---
title: 第 3 步。 企业租户Microsoft 365的标识
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 为租户部署正确的标识Microsoft 365并强制执行强用户登录。
ms.openlocfilehash: 57e84b38715c4fbe29f9aa362e363663b0401f91
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052358"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="60980-104">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="60980-104">Step 3.</span></span> <span data-ttu-id="60980-105">企业租户Microsoft 365的标识</span><span class="sxs-lookup"><span data-stu-id="60980-105">Identity for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="60980-106">你的Microsoft 365租户包括一Azure Active Directory (Azure AD) 租户，用于管理登录的标识和身份验证。正确配置标识基础结构对于管理Microsoft 365用户访问权限和权限至关重要。</span><span class="sxs-lookup"><span data-stu-id="60980-106">Your Microsoft 365 tenant includes an Azure Active Directory (Azure AD) tenant to manage identities and authentication for sign-ins. Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

## <a name="cloud-only-vs-hybrid"></a><span data-ttu-id="60980-107">仅云与混合</span><span class="sxs-lookup"><span data-stu-id="60980-107">Cloud-only vs. hybrid</span></span>

<span data-ttu-id="60980-108">下面是两种类型的标识模型及其最佳匹配和优势。</span><span class="sxs-lookup"><span data-stu-id="60980-108">Here are the two types of identity models and their best fit and benefits.</span></span>


| <span data-ttu-id="60980-109">模型</span><span class="sxs-lookup"><span data-stu-id="60980-109">Model</span></span> | <span data-ttu-id="60980-110">说明</span><span class="sxs-lookup"><span data-stu-id="60980-110">Description</span></span> | <span data-ttu-id="60980-111">如何Microsoft 365用户凭据进行身份验证</span><span class="sxs-lookup"><span data-stu-id="60980-111">How Microsoft 365 authenticates user credentials</span></span> | <span data-ttu-id="60980-112">最适用于</span><span class="sxs-lookup"><span data-stu-id="60980-112">Best for</span></span> | <span data-ttu-id="60980-113">最大优势</span><span class="sxs-lookup"><span data-stu-id="60980-113">Greatest benefit</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="60980-114">仅限云</span><span class="sxs-lookup"><span data-stu-id="60980-114">Cloud-only</span></span> | <span data-ttu-id="60980-115">用户帐户仅存在于你的租户的 Azure AD Microsoft 365中。</span><span class="sxs-lookup"><span data-stu-id="60980-115">User account only exists in the Azure AD tenant for your Microsoft 365 tenant.</span></span> | <span data-ttu-id="60980-116">租户的 Azure AD Microsoft 365使用云标识帐户执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="60980-116">The Azure AD tenant for your Microsoft 365 tenant performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="60980-117">没有或不需要本地 AD DS 的组织。</span><span class="sxs-lookup"><span data-stu-id="60980-117">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="60980-118">易于使用。</span><span class="sxs-lookup"><span data-stu-id="60980-118">Simple to use.</span></span> <span data-ttu-id="60980-119">无需额外的目录工具或服务器。</span><span class="sxs-lookup"><span data-stu-id="60980-119">No extra directory tools or servers required.</span></span> |
| <span data-ttu-id="60980-120">混合</span><span class="sxs-lookup"><span data-stu-id="60980-120">Hybrid</span></span> |  <span data-ttu-id="60980-121">用户帐户存在于本地 Active Directory 域服务 (AD DS) 并且副本也位于 Microsoft 365 租户的 Azure AD 租户中。</span><span class="sxs-lookup"><span data-stu-id="60980-121">User account exists in your on-premises Active Directory Domain Services (AD DS) and a copy is also in the Azure AD tenant for your Microsoft 365 tenant.</span></span> <span data-ttu-id="60980-122">Azure AD 连接在本地服务器上运行，以将 AD DS 更改同步到 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="60980-122">Azure AD Connect runs on an on-premises server to synchronize AD DS changes to your Azure AD tenant.</span></span> <span data-ttu-id="60980-123">Azure AD 中的用户帐户可能还包括已哈希 AD DS 用户帐户密码的哈希版本。</span><span class="sxs-lookup"><span data-stu-id="60980-123">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> | <span data-ttu-id="60980-124">你的租户的 Azure AD Microsoft 365处理身份验证过程或将用户重定向到另一个标识提供程序。</span><span class="sxs-lookup"><span data-stu-id="60980-124">The Azure AD tenant for your Microsoft 365 tenant either handles the authentication process or redirects the user to another identity provider.</span></span> | <span data-ttu-id="60980-125">使用 AD DS 或其他标识提供程序的组织。</span><span class="sxs-lookup"><span data-stu-id="60980-125">Organizations using AD DS or another identity provider.</span></span> | <span data-ttu-id="60980-126">在访问本地或基于云的资源时，用户可以使用相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="60980-126">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||||

<span data-ttu-id="60980-127">以下是仅云标识的基本组件。</span><span class="sxs-lookup"><span data-stu-id="60980-127">Here are the basic components of cloud-only identity.</span></span>
 
![仅云标识的基本组件](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="60980-129">在此图中，本地和远程用户使用其租户的 Azure AD 租户中的帐户Microsoft 365登录。</span><span class="sxs-lookup"><span data-stu-id="60980-129">In this illustration, on-premises and remote users sign in with accounts in the Azure AD tenant of their Microsoft 365 tenant.</span></span>

<span data-ttu-id="60980-130">下面是混合标识的基本组件。</span><span class="sxs-lookup"><span data-stu-id="60980-130">Here are the basic components of hybrid identity.</span></span>

![混合标识的基本组件](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="60980-132">在此图中，本地和远程用户使用 Azure AD 租户中已复制自其本地 AD DS 的帐户登录到 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="60980-132">In this illustration, on-premises and remote users sign in to their Microsoft 365 tenant with accounts in the Azure AD tenant that have been copied from their on-premises AD DS.</span></span>

## <a name="synchronizing-your-on-premises-ad-ds"></a><span data-ttu-id="60980-133">同步本地 AD DS</span><span class="sxs-lookup"><span data-stu-id="60980-133">Synchronizing your on-premises AD DS</span></span>

<span data-ttu-id="60980-134">混合标识模型和目录同步是采用混合标识的企业客户最常用的选择，具体取决于业务需求和技术Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="60980-134">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="60980-135">目录同步允许你管理 AD DS 中的标识，并且用户帐户、组和联系人的所有更新都同步到 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="60980-135">Directory synchronization allows you to manage identities in your AD DS and all updates to user accounts, groups, and contacts are synchronized to the Azure AD tenant of your Microsoft 365 tenant.</span></span>

>[!Note]
><span data-ttu-id="60980-136">首次同步 AD DS 用户帐户时，不会自动为其分配 Microsoft 365 许可证，并且无法访问 Microsoft 365 服务，如电子邮件。</span><span class="sxs-lookup"><span data-stu-id="60980-136">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="60980-137">您必须先为其分配使用位置。</span><span class="sxs-lookup"><span data-stu-id="60980-137">You must first assign them a usage location.</span></span> <span data-ttu-id="60980-138">然后，通过组成员身份单独或动态地向这些用户帐户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="60980-138">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

<span data-ttu-id="60980-139">下面是使用混合标识模型时两种类型的身份验证。</span><span class="sxs-lookup"><span data-stu-id="60980-139">Here are the two types of authentication when using the hybrid identity model.</span></span>

| <span data-ttu-id="60980-140">身份验证类型</span><span class="sxs-lookup"><span data-stu-id="60980-140">Authentication type</span></span> | <span data-ttu-id="60980-141">说明</span><span class="sxs-lookup"><span data-stu-id="60980-141">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="60980-142">托管身份验证</span><span class="sxs-lookup"><span data-stu-id="60980-142">Managed authentication</span></span> | <span data-ttu-id="60980-143">Azure AD 使用本地存储的密码哈希版本处理身份验证过程，或将凭据发送到本地软件代理，以通过本地 AD DS 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="60980-143">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span> <br> <br>  <span data-ttu-id="60980-144">托管身份验证有两种类型：密码哈希同步 (PHS) PTA (传递) 。</span><span class="sxs-lookup"><span data-stu-id="60980-144">There are two types of managed authentication: Password hash synchronization (PHS) and Pass-through authentication (PTA).</span></span> <span data-ttu-id="60980-145">借助 PHS，Azure AD 本身执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="60980-145">With PHS, Azure AD performs the authentication itself.</span></span> <span data-ttu-id="60980-146">借助 PTA，Azure AD 使 AD DS 执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="60980-146">With PTA, Azure AD has AD DS perform the authentication.</span></span> |
| <span data-ttu-id="60980-147">联合身份验证</span><span class="sxs-lookup"><span data-stu-id="60980-147">Federated authentication</span></span> | <span data-ttu-id="60980-148">Azure AD 将请求身份验证的客户端计算机重定向到另一个标识提供程序。</span><span class="sxs-lookup"><span data-stu-id="60980-148">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span> |
|  |  |

<span data-ttu-id="60980-149">有关详细信息 [，请参阅选择正确的](/azure/active-directory/hybrid/choose-ad-authn) 身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="60980-149">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>

## <a name="enforcing-strong-sign-ins"></a><span data-ttu-id="60980-150">强制执行强登录</span><span class="sxs-lookup"><span data-stu-id="60980-150">Enforcing strong sign-ins</span></span>

<span data-ttu-id="60980-151">若要提高用户登录的安全性，请使用下表中的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="60980-151">To increase the security of user sign-ins, use the features and capabilities in the following table.</span></span>

| <span data-ttu-id="60980-152">功能</span><span class="sxs-lookup"><span data-stu-id="60980-152">Capability</span></span> | <span data-ttu-id="60980-153">说明</span><span class="sxs-lookup"><span data-stu-id="60980-153">Description</span></span> | <span data-ttu-id="60980-154">详细信息</span><span class="sxs-lookup"><span data-stu-id="60980-154">More information</span></span> | <span data-ttu-id="60980-155">许可要求</span><span class="sxs-lookup"><span data-stu-id="60980-155">Licensing requirements</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="60980-156">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="60980-156">Windows Hello for Business</span></span> | <span data-ttu-id="60980-157">在设备上登录时，使用强双因素身份验证Windows密码。</span><span class="sxs-lookup"><span data-stu-id="60980-157">Replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="60980-158">这两个因素是一种与设备和生物识别或 PIN 相关联的新型用户凭据。</span><span class="sxs-lookup"><span data-stu-id="60980-158">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span> | [<span data-ttu-id="60980-159">Windows Hello 企业版概述</span><span class="sxs-lookup"><span data-stu-id="60980-159">Windows Hello for Business Overview</span></span>](/windows/security/identity-protection/hello-for-business/hello-overview) | <span data-ttu-id="60980-160">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="60980-160">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="60980-161">Azure AD 密码保护</span><span class="sxs-lookup"><span data-stu-id="60980-161">Azure AD Password Protection</span></span> | <span data-ttu-id="60980-162">检测并阻止已知的弱密码及其变体，还可以阻止特定于您的组织的其他弱术语。</span><span class="sxs-lookup"><span data-stu-id="60980-162">Detects and blocks known weak passwords and their variants and can also block additional weak terms that are specific to your organization.</span></span> | [<span data-ttu-id="60980-163">配置 Azure AD 密码保护</span><span class="sxs-lookup"><span data-stu-id="60980-163">Configure Azure AD password protection</span></span>](/azure/active-directory/authentication/concept-password-ban-bad) | <span data-ttu-id="60980-164">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="60980-164">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="60980-165">使用多重身份验证 (MFA)</span><span class="sxs-lookup"><span data-stu-id="60980-165">Use multi-factor authentication (MFA)</span></span> | <span data-ttu-id="60980-166">MFA 要求用户登录需要除用户帐户密码之外的其他验证，例如使用智能手机应用进行验证或发送到智能手机的短信。</span><span class="sxs-lookup"><span data-stu-id="60980-166">MFA requires that user sign-ins be subject to an additional verification beyond the user account password, such as verification with a smartphone app or a text message sent to a smartphone.</span></span> <span data-ttu-id="60980-167">有关 [用户](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) 如何设置 MFA 的说明，请参阅此视频。</span><span class="sxs-lookup"><span data-stu-id="60980-167">See [this video](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) for instructions on how users set up MFA.</span></span> | [<span data-ttu-id="60980-168">适用于企业的 Microsoft 365 MFA</span><span class="sxs-lookup"><span data-stu-id="60980-168">MFA for Microsoft 365 for enterprise</span></span>](../enterprise/microsoft-365-secure-sign-in.md#mfa) | <span data-ttu-id="60980-169">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="60980-169">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="60980-170">标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="60980-170">Identity and device access configurations</span></span> | <span data-ttu-id="60980-171">设置策略，其中包括建议的先决条件功能及其设置，以及条件访问、Intune 和 Azure AD Identity Protection 策略，这些策略确定是否应授予给定访问请求以及应在哪些条件下授予。</span><span class="sxs-lookup"><span data-stu-id="60980-171">Settings and policies that consist of recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span>  | [<span data-ttu-id="60980-172">标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="60980-172">Identity and device access configurations</span></span>](../security/defender-365-security/microsoft-365-policies-configurations.md) | <span data-ttu-id="60980-173">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="60980-173">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="60980-174">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="60980-174">Azure AD Identity Protection</span></span> | <span data-ttu-id="60980-175">防止凭据泄露，攻击者可确定用户帐户名和密码，以访问组织的云服务和数据。</span><span class="sxs-lookup"><span data-stu-id="60980-175">Protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> | [<span data-ttu-id="60980-176">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="60980-176">Azure AD Identity Protection</span></span>](/azure/active-directory/active-directory-identityprotection) | <span data-ttu-id="60980-177">Microsoft 365 E5或Microsoft 365 E3 Identity &威胁防护加载项的加载项</span><span class="sxs-lookup"><span data-stu-id="60980-177">Microsoft 365 E5 or Microsoft 365 E3 with the Identity & Threat Protection add-on</span></span> |
|  |  |  |



## <a name="results-of-step-3"></a><span data-ttu-id="60980-178">步骤 3 的结果</span><span class="sxs-lookup"><span data-stu-id="60980-178">Results of Step 3</span></span>

<span data-ttu-id="60980-179">对于你的租户Microsoft 365标识，你已确定：</span><span class="sxs-lookup"><span data-stu-id="60980-179">For identity for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="60980-180">要使用哪种标识模型。</span><span class="sxs-lookup"><span data-stu-id="60980-180">Which identity model to use.</span></span>
- <span data-ttu-id="60980-181">如何强制执行强用户和设备访问。</span><span class="sxs-lookup"><span data-stu-id="60980-181">How you will enforce strong user and device access.</span></span>

<span data-ttu-id="60980-182">下面是一个突出显示了新混合标识元素的租户示例。</span><span class="sxs-lookup"><span data-stu-id="60980-182">Here is an example a tenant with the new hybrid identity elements highlighted.</span></span>

![租户的混合标识示例](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

<span data-ttu-id="60980-184">在此图中，租户具有：</span><span class="sxs-lookup"><span data-stu-id="60980-184">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="60980-185">使用 DirSync 服务器和 Azure AD 租户与 Azure AD 租户同步的 AD DS 连接。</span><span class="sxs-lookup"><span data-stu-id="60980-185">An AD DS forest that is being synchronized with the Azure AD tenant using a DirSync server and Azure AD Connect.</span></span>
- <span data-ttu-id="60980-186">AD DS 用户帐户和 AD DS 林中其他对象的副本。</span><span class="sxs-lookup"><span data-stu-id="60980-186">A copy of the AD DS user accounts and other objects from the AD DS forest.</span></span>
- <span data-ttu-id="60980-187">一组条件访问策略，用于基于用户帐户强制实施安全用户登录和访问。</span><span class="sxs-lookup"><span data-stu-id="60980-187">A set of Conditional Access policies to enforce secure user sign-ins and access based on the user account.</span></span> 

## <a name="ongoing-maintenance-for-identity"></a><span data-ttu-id="60980-188">持续维护标识</span><span class="sxs-lookup"><span data-stu-id="60980-188">Ongoing maintenance for identity</span></span>

<span data-ttu-id="60980-189">您可能需要持续：</span><span class="sxs-lookup"><span data-stu-id="60980-189">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="60980-190">添加或修改用户帐户和组。</span><span class="sxs-lookup"><span data-stu-id="60980-190">Add or modify user accounts and groups.</span></span> <span data-ttu-id="60980-191">对于仅云标识，使用 Azure AD 工具（如管理中心或 PowerShell）Microsoft 365基于云的用户和组。</span><span class="sxs-lookup"><span data-stu-id="60980-191">For cloud-only identity, you maintain your cloud-based users and groups with Azure AD tools such as the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="60980-192">对于混合标识，使用 AD DS 工具维护本地用户和组。</span><span class="sxs-lookup"><span data-stu-id="60980-192">For hybrid identity, you maintain your on-premises users and groups with AD DS tools.</span></span>
- <span data-ttu-id="60980-193">添加或修改标识和设备访问配置，以强制实施登录安全要求。</span><span class="sxs-lookup"><span data-stu-id="60980-193">Add or modify your identity and device access configuration to enforce sign-in security requirements.</span></span>

## <a name="next-step"></a><span data-ttu-id="60980-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="60980-194">Next step</span></span>

<span data-ttu-id="60980-195">[![步骤 4.迁移本地部署Office服务器和数据](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span><span class="sxs-lookup"><span data-stu-id="60980-195">[![Step 4. Migrate your on-premises Office servers and data](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span></span>

<span data-ttu-id="60980-196">继续[迁移，](tenant-management-migration.md)将本地Office服务器及其数据迁移到Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="60980-196">Continue with [migration](tenant-management-migration.md) to migrate your on-premises Office servers and their data to Microsoft 365.</span></span>