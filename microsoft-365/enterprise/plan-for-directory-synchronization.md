---
title: 混合标识和目录同步Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: 介绍与 Microsoft 365 的目录同步、Active Directory 域服务清理Azure Active Directory 连接工具。
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927540"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="00f83-103">混合标识和目录同步Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00f83-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="00f83-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="00f83-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="00f83-105">混合标识模型和目录同步是采用混合标识的企业客户最常用的选择，具体取决于业务需求和技术Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="00f83-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="00f83-106">目录同步允许你管理 Active Directory 域服务 (AD DS) 中的标识，并且用户帐户、组和联系人的所有更新将同步到 Microsoft 365 订阅的 Azure Active Directory (Azure AD) 租户。</span><span class="sxs-lookup"><span data-stu-id="00f83-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="00f83-107">首次同步 AD DS 用户帐户时，不会自动为其分配 Microsoft 365 许可证，并且无法访问 Microsoft 365 服务，如电子邮件。</span><span class="sxs-lookup"><span data-stu-id="00f83-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="00f83-108">您必须先为其分配使用位置。</span><span class="sxs-lookup"><span data-stu-id="00f83-108">You must first assign them a usage location.</span></span> <span data-ttu-id="00f83-109">然后，通过组成员身份单独或动态地向这些用户帐户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="00f83-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="00f83-110">混合标识的身份验证</span><span class="sxs-lookup"><span data-stu-id="00f83-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="00f83-111">使用混合标识模型时有两种类型的身份验证：</span><span class="sxs-lookup"><span data-stu-id="00f83-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="00f83-112">托管身份验证</span><span class="sxs-lookup"><span data-stu-id="00f83-112">Managed authentication</span></span>

  <span data-ttu-id="00f83-113">Azure AD 使用本地存储的密码哈希版本处理身份验证过程，或将凭据发送到本地软件代理，以通过本地 AD DS 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="00f83-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="00f83-114">联合身份验证</span><span class="sxs-lookup"><span data-stu-id="00f83-114">Federated authentication</span></span>

  <span data-ttu-id="00f83-115">Azure AD 将请求身份验证的客户端计算机重定向到另一个标识提供程序。</span><span class="sxs-lookup"><span data-stu-id="00f83-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="00f83-116">托管身份验证</span><span class="sxs-lookup"><span data-stu-id="00f83-116">Managed authentication</span></span>

<span data-ttu-id="00f83-117">有两种类型的托管身份验证：</span><span class="sxs-lookup"><span data-stu-id="00f83-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="00f83-118">PHS (密码哈希) </span><span class="sxs-lookup"><span data-stu-id="00f83-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="00f83-119">Azure AD 执行身份验证本身。</span><span class="sxs-lookup"><span data-stu-id="00f83-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="00f83-120">直通身份验证 (PTA)</span><span class="sxs-lookup"><span data-stu-id="00f83-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="00f83-121">Azure AD 具有 AD DS 来执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="00f83-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="00f83-122">PHS (密码哈希) </span><span class="sxs-lookup"><span data-stu-id="00f83-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="00f83-123">借助 PHS，你可以将 AD DS 用户帐户Microsoft 365并在本地管理用户。</span><span class="sxs-lookup"><span data-stu-id="00f83-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="00f83-124">用户密码哈希从 AD DS 同步到 Azure AD，以便用户在本地和云中具有相同的密码。</span><span class="sxs-lookup"><span data-stu-id="00f83-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="00f83-125">这是在 Azure AD 中启用 AD DS 标识身份验证的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="00f83-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![PHS (密码哈希) ](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="00f83-127">当在本地更改或重置密码时，新的密码哈希将同步到 Azure AD，以便你的用户始终可以针对云资源和本地资源使用相同的密码。</span><span class="sxs-lookup"><span data-stu-id="00f83-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="00f83-128">用户密码从不发送到 Azure AD 或以纯文本存储在 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="00f83-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="00f83-129">Azure AD 的一些高级功能（如 Identity Protection）需要 PHS，而不考虑选择哪种身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="00f83-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="00f83-130">有关详细信息 [，请参阅选择正确的](/azure/active-directory/hybrid/choose-ad-authn) 身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="00f83-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="00f83-131">直通身份验证 (PTA)</span><span class="sxs-lookup"><span data-stu-id="00f83-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="00f83-132">PTA 使用一个或多个本地服务器上运行的软件代理，为 Azure AD 身份验证服务提供简单的密码验证，以直接使用 AD DS 验证用户。</span><span class="sxs-lookup"><span data-stu-id="00f83-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="00f83-133">借助 PTA，你可以将 AD DS 用户帐户Microsoft 365本地管理用户。</span><span class="sxs-lookup"><span data-stu-id="00f83-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![直通身份验证 (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="00f83-135">PTA 允许用户使用本地帐户和密码登录本地Microsoft 365和本地资源和应用程序。</span><span class="sxs-lookup"><span data-stu-id="00f83-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="00f83-136">此配置直接针对本地 AD DS 验证用户密码，而无需在 Azure AD 中存储密码哈希。</span><span class="sxs-lookup"><span data-stu-id="00f83-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="00f83-137">PTA 还适用于具有立即强制执行本地用户帐户状态、密码策略和登录时间的安全要求的组织。</span><span class="sxs-lookup"><span data-stu-id="00f83-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="00f83-138">有关详细信息 [，请参阅选择正确的](/azure/active-directory/hybrid/choose-ad-authn) 身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="00f83-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="00f83-139">联合身份验证</span><span class="sxs-lookup"><span data-stu-id="00f83-139">Federated authentication</span></span>

<span data-ttu-id="00f83-140">联合身份验证主要用于身份验证要求更复杂的大型企业组织。</span><span class="sxs-lookup"><span data-stu-id="00f83-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="00f83-141">AD DS 标识与Microsoft 365同步，并且用户帐户在本地进行管理。</span><span class="sxs-lookup"><span data-stu-id="00f83-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="00f83-142">使用联合身份验证，用户在本地和云中具有相同的密码，他们不需要再次登录，Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="00f83-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="00f83-143">联合身份验证可以支持其他身份验证要求，如基于智能卡的身份验证或第三方多重身份验证，当组织具有 Azure AD 不支持的身份验证要求时，通常需要此要求。</span><span class="sxs-lookup"><span data-stu-id="00f83-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="00f83-144">有关详细信息 [，请参阅选择正确的](/azure/active-directory/hybrid/choose-ad-authn) 身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="00f83-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="00f83-145">第三方身份验证和标识提供程序</span><span class="sxs-lookup"><span data-stu-id="00f83-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="00f83-146">本地目录对象可以同步到Microsoft 365并且云资源访问主要由 IdP (第三方标识) 。</span><span class="sxs-lookup"><span data-stu-id="00f83-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="00f83-147">如果组织使用第三方联合解决方案，可以使用该解决方案为 Microsoft 365配置登录，但第三方联合解决方案与 Azure AD 兼容。</span><span class="sxs-lookup"><span data-stu-id="00f83-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="00f83-148">有关详细信息，请参阅 [Azure AD 联合兼容性](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) 列表。</span><span class="sxs-lookup"><span data-stu-id="00f83-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="00f83-149">AD DS 准备</span><span class="sxs-lookup"><span data-stu-id="00f83-149">AD DS Preparation</span></span>

<span data-ttu-id="00f83-150">为了帮助确保使用同步无缝Microsoft 365，必须在开始部署目录同步Microsoft 365 AD DS 林。</span><span class="sxs-lookup"><span data-stu-id="00f83-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="00f83-151">目录准备应专注于以下任务：</span><span class="sxs-lookup"><span data-stu-id="00f83-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="00f83-152">删除重复 **的 proxyAddress** 和 **userPrincipalName** 属性。</span><span class="sxs-lookup"><span data-stu-id="00f83-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="00f83-153">使用有效的 **userPrincipalName** 属性更新空和无效的 **userPrincipalName** 属性。</span><span class="sxs-lookup"><span data-stu-id="00f83-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="00f83-154">删除 **givenName、surname** **( sn** ) 、sAMAccountName、displayName、mail、proxyAddresses、mailNickname 和 **userPrincipalName** 属性中的无效和问题字符。    </span><span class="sxs-lookup"><span data-stu-id="00f83-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="00f83-155">有关准备属性的详细信息，请参阅由同步工具同步Azure Active Directory[列表](https://go.microsoft.com/fwlink/p/?LinkId=396719)。</span><span class="sxs-lookup"><span data-stu-id="00f83-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="00f83-156">这些属性与 Azure AD 要同步连接相同。</span><span class="sxs-lookup"><span data-stu-id="00f83-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="00f83-157">多林部署注意事项</span><span class="sxs-lookup"><span data-stu-id="00f83-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="00f83-158">对于多个林和 SSO 选项，请使用[Azure AD](/azure/active-directory/hybrid/how-to-connect-install-custom)自定义连接。</span><span class="sxs-lookup"><span data-stu-id="00f83-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="00f83-159">如果您的组织具有多个用于身份验证的林 (登录) ，我们强烈建议您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="00f83-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="00f83-160">**请考虑合并林。**</span><span class="sxs-lookup"><span data-stu-id="00f83-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="00f83-161">通常，维护多个林需要更多开销。</span><span class="sxs-lookup"><span data-stu-id="00f83-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="00f83-162">除非贵组织的安全约束规定需要单独的林，否则请考虑简化您的本地环境。</span><span class="sxs-lookup"><span data-stu-id="00f83-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="00f83-163">**仅在主登录林中使用。**</span><span class="sxs-lookup"><span data-stu-id="00f83-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="00f83-164">请考虑仅在Microsoft 365登录林中部署客户端，以初始部署Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="00f83-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="00f83-165">如果无法合并多林 AD DS 部署或正在使用其他目录服务来管理标识，则可以通过 Microsoft 或合作伙伴的帮助进行同步。</span><span class="sxs-lookup"><span data-stu-id="00f83-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="00f83-166">有关详细信息[，请参阅 Azure AD 连接](/azure/active-directory/hybrid/plan-connect-topologies)拓扑。</span><span class="sxs-lookup"><span data-stu-id="00f83-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="00f83-167">依赖于目录同步的功能</span><span class="sxs-lookup"><span data-stu-id="00f83-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="00f83-168">以下特性和功能需要目录同步：</span><span class="sxs-lookup"><span data-stu-id="00f83-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="00f83-169">Azure AD 无缝单Sign-On (SSO) </span><span class="sxs-lookup"><span data-stu-id="00f83-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="00f83-170">Skype共存</span><span class="sxs-lookup"><span data-stu-id="00f83-170">Skype coexistence</span></span>
- <span data-ttu-id="00f83-171">Exchange混合部署，包括：</span><span class="sxs-lookup"><span data-stu-id="00f83-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="00f83-172">在内部部署环境和 (环境) 之间使用 GAL Exchange全局地址Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="00f83-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="00f83-173">同步不同邮件系统中的 GAL 信息。</span><span class="sxs-lookup"><span data-stu-id="00f83-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="00f83-174">能够向服务产品中添加用户并从Microsoft 365中删除用户。</span><span class="sxs-lookup"><span data-stu-id="00f83-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="00f83-175">这要求：</span><span class="sxs-lookup"><span data-stu-id="00f83-175">This requires the following:</span></span>
  - <span data-ttu-id="00f83-176">在目录同步设置过程中必须配置双向同步。</span><span class="sxs-lookup"><span data-stu-id="00f83-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="00f83-177">默认情况下，目录同步工具仅将目录信息写入云。</span><span class="sxs-lookup"><span data-stu-id="00f83-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="00f83-178">配置双向同步时，将启用写回功能，以便从云中复制有限数量的对象属性，然后将这些属性写回本地 AD DS。</span><span class="sxs-lookup"><span data-stu-id="00f83-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="00f83-179">回写也称为混合Exchange模式。</span><span class="sxs-lookup"><span data-stu-id="00f83-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="00f83-180">内部部署Exchange混合部署</span><span class="sxs-lookup"><span data-stu-id="00f83-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="00f83-181">将一些用户邮箱移动到 Microsoft 365将其他用户邮箱保留在本地的能力。</span><span class="sxs-lookup"><span data-stu-id="00f83-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="00f83-182">保险箱将本地发件人和阻止的发件人复制到Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="00f83-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="00f83-183">基本委托和代表发送电子邮件功能。</span><span class="sxs-lookup"><span data-stu-id="00f83-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="00f83-184">你拥有集成的本地智能卡或多重身份验证解决方案。</span><span class="sxs-lookup"><span data-stu-id="00f83-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="00f83-185">同步照片、缩略图、会议室和安全组</span><span class="sxs-lookup"><span data-stu-id="00f83-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="00f83-186">后续步骤</span><span class="sxs-lookup"><span data-stu-id="00f83-186">Next step</span></span>

<span data-ttu-id="00f83-187">准备好部署混合标识时，请参阅 [准备目录同步](prepare-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="00f83-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
