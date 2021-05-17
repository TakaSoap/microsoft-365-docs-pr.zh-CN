---
title: Microsoft 365标识模型和Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: 了解如何使用仅云或混合标识模型Microsoft 365 Azure AD 用户标识服务。
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905700"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="91ea9-103">Microsoft 365标识模型和Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="91ea9-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="91ea9-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="91ea9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="91ea9-105">Microsoft 365使用 Azure Active Directory (Azure AD) （即 Microsoft 365 订阅中包含的基于云的用户标识和身份验证服务）来管理 Microsoft 365 的标识和身份验证。</span><span class="sxs-lookup"><span data-stu-id="91ea9-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="91ea9-106">正确配置标识基础结构对于管理Microsoft 365用户访问权限和权限至关重要。</span><span class="sxs-lookup"><span data-stu-id="91ea9-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="91ea9-107">开始之前，请观看此视频，以获取 Microsoft 365 身份模型和身份验证的概述。</span><span class="sxs-lookup"><span data-stu-id="91ea9-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="91ea9-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="91ea9-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="91ea9-109">第一个规划选择是Microsoft 365模型。</span><span class="sxs-lookup"><span data-stu-id="91ea9-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="91ea9-110">Microsoft 365标识模型</span><span class="sxs-lookup"><span data-stu-id="91ea9-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="91ea9-111">若要规划用户帐户，首先需要了解 Microsoft 365 中的两个标识模型。</span><span class="sxs-lookup"><span data-stu-id="91ea9-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="91ea9-112">只能在云中维护组织的标识，也可以维护本地 Active Directory 域服务 (AD DS) 标识，并使用它们在用户访问 Microsoft 365 云服务时进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="91ea9-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="91ea9-113">下面是两种类型的标识及其最佳匹配和优势。</span><span class="sxs-lookup"><span data-stu-id="91ea9-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="91ea9-114">属性</span><span class="sxs-lookup"><span data-stu-id="91ea9-114">Attribute</span></span> | <span data-ttu-id="91ea9-115">仅限云标识</span><span class="sxs-lookup"><span data-stu-id="91ea9-115">Cloud-only identity</span></span> | <span data-ttu-id="91ea9-116">混合标识</span><span class="sxs-lookup"><span data-stu-id="91ea9-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="91ea9-117">**定义**</span><span class="sxs-lookup"><span data-stu-id="91ea9-117">**Definition**</span></span> | <span data-ttu-id="91ea9-118">用户帐户仅存在于你的订阅的 Azure AD Microsoft 365中。</span><span class="sxs-lookup"><span data-stu-id="91ea9-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="91ea9-119">用户帐户存在于 AD DS 中，并且副本也在 Azure AD 租户中用于你的 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="91ea9-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="91ea9-120">Azure AD 中的用户帐户可能还包括已哈希 AD DS 用户帐户密码的哈希版本。</span><span class="sxs-lookup"><span data-stu-id="91ea9-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="91ea9-121">**如何Microsoft 365用户凭据进行身份验证**</span><span class="sxs-lookup"><span data-stu-id="91ea9-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="91ea9-122">你的订阅的 Azure AD Microsoft 365使用云标识帐户执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="91ea9-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="91ea9-123">你的订阅的 Azure AD Microsoft 365处理身份验证过程或将用户重定向到另一个标识提供程序。</span><span class="sxs-lookup"><span data-stu-id="91ea9-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="91ea9-124">**最适用于**</span><span class="sxs-lookup"><span data-stu-id="91ea9-124">**Best for**</span></span> | <span data-ttu-id="91ea9-125">没有或不需要本地 AD DS 的组织。</span><span class="sxs-lookup"><span data-stu-id="91ea9-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="91ea9-126">使用 AD DS 或其他标识提供程序的组织。</span><span class="sxs-lookup"><span data-stu-id="91ea9-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="91ea9-127">**最大优势**</span><span class="sxs-lookup"><span data-stu-id="91ea9-127">**Greatest benefit**</span></span> | <span data-ttu-id="91ea9-128">易于使用。</span><span class="sxs-lookup"><span data-stu-id="91ea9-128">Simple to use.</span></span> <span data-ttu-id="91ea9-129">无需额外的目录工具或服务器。</span><span class="sxs-lookup"><span data-stu-id="91ea9-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="91ea9-130">在访问本地或基于云的资源时，用户可以使用相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="91ea9-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="91ea9-131">仅限云标识</span><span class="sxs-lookup"><span data-stu-id="91ea9-131">Cloud-only identity</span></span>

<span data-ttu-id="91ea9-132">仅限云标识使用仅存在于 Azure AD 中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="91ea9-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="91ea9-133">仅云标识通常由没有本地服务器或使用 AD DS 管理本地标识的小组织使用。</span><span class="sxs-lookup"><span data-stu-id="91ea9-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="91ea9-134">以下是仅云标识的基本组件。</span><span class="sxs-lookup"><span data-stu-id="91ea9-134">Here are the basic components of cloud-only identity.</span></span>
 
![仅云标识的基本组件](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="91ea9-136">本地和远程 (联机) 用户使用其 Azure AD 用户帐户和密码访问 Microsoft 365 云服务。</span><span class="sxs-lookup"><span data-stu-id="91ea9-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="91ea9-137">Azure AD 根据其存储的用户帐户和密码对用户凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="91ea9-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="91ea9-138">管理</span><span class="sxs-lookup"><span data-stu-id="91ea9-138">Administration</span></span>
<span data-ttu-id="91ea9-139">由于用户帐户仅存储在 Azure AD 中，因此使用管理中心等工具管理Microsoft 365[云](../admin/add-users/index.yml)[Windows PowerShell。](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="91ea9-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](../admin/add-users/index.yml) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="91ea9-140">混合标识</span><span class="sxs-lookup"><span data-stu-id="91ea9-140">Hybrid identity</span></span>

<span data-ttu-id="91ea9-141">混合标识使用源自本地 AD DS 的帐户，并且其副本位于 Azure AD 租户的 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="91ea9-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="91ea9-142">但是，大多数更改仅单向流动。</span><span class="sxs-lookup"><span data-stu-id="91ea9-142">However, most changes only flow one way.</span></span> <span data-ttu-id="91ea9-143">对 AD DS 用户帐户所做的更改将同步到 Azure AD 中的副本。</span><span class="sxs-lookup"><span data-stu-id="91ea9-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="91ea9-144">但是，对 Azure AD 中基于云的帐户所做的更改（如新用户帐户）不会与 AD DS 同步。</span><span class="sxs-lookup"><span data-stu-id="91ea9-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="91ea9-145">Azure AD 连接提供持续的帐户同步。</span><span class="sxs-lookup"><span data-stu-id="91ea9-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="91ea9-146">它在本地服务器上运行，检查 AD DS 中的更改，将这些更改转发到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="91ea9-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="91ea9-147">Azure AD 连接 提供了筛选哪些帐户已同步以及是否同步用户密码的哈希版本（称为密码哈希同步 (PHS) ）。</span><span class="sxs-lookup"><span data-stu-id="91ea9-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="91ea9-148">实现混合标识时，本地 AD DS 是指帐户信息权威源。</span><span class="sxs-lookup"><span data-stu-id="91ea9-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="91ea9-149">这意味着你执行的管理任务大部分是本地的，然后同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="91ea9-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="91ea9-150">下面是混合标识的组件。</span><span class="sxs-lookup"><span data-stu-id="91ea9-150">Here are the components of hybrid identity.</span></span>

![混合标识的组件](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="91ea9-152">Azure AD 租户具有 AD DS 帐户的副本。</span><span class="sxs-lookup"><span data-stu-id="91ea9-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="91ea9-153">在此配置中，本地和远程用户访问 Microsoft 365对 Azure AD 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="91ea9-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="91ea9-154">你始终需要使用 Azure AD 连接同步混合标识的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="91ea9-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="91ea9-155">你需要在 Azure AD 中同步用户帐户才能执行许可证分配和组管理、配置权限以及涉及用户帐户的其他管理任务。</span><span class="sxs-lookup"><span data-stu-id="91ea9-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="91ea9-156">管理</span><span class="sxs-lookup"><span data-stu-id="91ea9-156">Administration</span></span>

<span data-ttu-id="91ea9-157">因为原始和权威用户帐户存储在本地 AD DS 中，所以使用管理 AD DS 时相同的工具管理标识。</span><span class="sxs-lookup"><span data-stu-id="91ea9-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="91ea9-158">在 Azure AD 中，Microsoft 365管理中心或 PowerShell Microsoft 365管理同步的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="91ea9-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="91ea9-159">后续步骤</span><span class="sxs-lookup"><span data-stu-id="91ea9-159">Next step</span></span>

<span data-ttu-id="91ea9-160">如果你需要仅云标识模型，请参阅仅 [云标识](cloud-only-identities.md)。</span><span class="sxs-lookup"><span data-stu-id="91ea9-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="91ea9-161">如果需要混合标识模型，请参阅混合 [标识](plan-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="91ea9-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="91ea9-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91ea9-162">See also</span></span>

[<span data-ttu-id="91ea9-163">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="91ea9-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)