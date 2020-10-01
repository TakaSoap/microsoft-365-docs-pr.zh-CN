---
title: Microsoft 365 标识模型和 Azure Active Directory
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
description: 了解如何使用仅限云或混合标识模型在 Microsoft 365 中管理 Azure AD 用户标识服务。
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327947"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="56682-103">Microsoft 365 标识模型和 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="56682-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="56682-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="56682-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="56682-105">Microsoft 365 使用 Azure Active Directory (Azure AD) （一种基于云的用户标识和身份验证服务）包含在 Microsoft 365 订阅中，用于管理 Microsoft 365 的身份和身份验证。</span><span class="sxs-lookup"><span data-stu-id="56682-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="56682-106">正确配置您的身份基础结构对于管理您的组织的 Microsoft 365 用户访问和权限至关重要。</span><span class="sxs-lookup"><span data-stu-id="56682-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="56682-107">开始之前，请观看此视频，以获取 Microsoft 365 身份模型和身份验证的概述。</span><span class="sxs-lookup"><span data-stu-id="56682-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="56682-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="56682-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="56682-109">您的第一次规划选择是 Microsoft 365 身份模型。</span><span class="sxs-lookup"><span data-stu-id="56682-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="56682-110">Microsoft 365 标识模型</span><span class="sxs-lookup"><span data-stu-id="56682-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="56682-111">若要规划用户帐户，首先需要了解 Microsoft 365 中的两个标识模型。</span><span class="sxs-lookup"><span data-stu-id="56682-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="56682-112">您可以仅在云中维护组织的标识，也可以维护内部部署 Active Directory 域服务 (AD DS) 标识，并在用户访问 Microsoft 365 云服务时使用它们进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="56682-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="56682-113">下面是两种类型的标识及其最佳优势。</span><span class="sxs-lookup"><span data-stu-id="56682-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="56682-114">属性</span><span class="sxs-lookup"><span data-stu-id="56682-114">Attribute</span></span> | <span data-ttu-id="56682-115">仅限云标识</span><span class="sxs-lookup"><span data-stu-id="56682-115">Cloud-only identity</span></span> | <span data-ttu-id="56682-116">混合标识</span><span class="sxs-lookup"><span data-stu-id="56682-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="56682-117">**定义**</span><span class="sxs-lookup"><span data-stu-id="56682-117">**Definition**</span></span> | <span data-ttu-id="56682-118">用户帐户仅存在于适用于 Microsoft 365 订阅的 Azure AD 租户中。</span><span class="sxs-lookup"><span data-stu-id="56682-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="56682-119">用户帐户存在于 AD DS 中，并且副本也位于 Microsoft 365 订阅的 Azure AD 租户中。</span><span class="sxs-lookup"><span data-stu-id="56682-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="56682-120">Azure AD 中的用户帐户可能还包含已散列的 AD DS 用户帐户密码的哈希版本。</span><span class="sxs-lookup"><span data-stu-id="56682-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="56682-121">**Microsoft 365 如何对用户凭据进行身份验证**</span><span class="sxs-lookup"><span data-stu-id="56682-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="56682-122">Microsoft 365 订阅的 Azure AD 租户将使用云标识帐户执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="56682-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="56682-123">Microsoft 365 订阅的 Azure AD 租户可以处理身份验证过程，也可以将用户重定向到另一个标识提供程序。</span><span class="sxs-lookup"><span data-stu-id="56682-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="56682-124">**最适用于**</span><span class="sxs-lookup"><span data-stu-id="56682-124">**Best for**</span></span> | <span data-ttu-id="56682-125">不具有或不需要本地 AD DS 的组织。</span><span class="sxs-lookup"><span data-stu-id="56682-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="56682-126">使用 AD DS 或其他标识提供程序的组织。</span><span class="sxs-lookup"><span data-stu-id="56682-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="56682-127">**最大好处**</span><span class="sxs-lookup"><span data-stu-id="56682-127">**Greatest benefit**</span></span> | <span data-ttu-id="56682-128">易于使用。</span><span class="sxs-lookup"><span data-stu-id="56682-128">Simple to use.</span></span> <span data-ttu-id="56682-129">无需额外的目录工具或服务器。</span><span class="sxs-lookup"><span data-stu-id="56682-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="56682-130">在访问本地或基于云的资源时，用户可以使用相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="56682-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="56682-131">仅限云标识</span><span class="sxs-lookup"><span data-stu-id="56682-131">Cloud-only identity</span></span>

<span data-ttu-id="56682-132">仅限云的标识使用仅存在于 Azure AD 中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="56682-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="56682-133">仅限云标识通常由没有本地服务器或不使用 AD DS 来管理本地标识的小型组织使用。</span><span class="sxs-lookup"><span data-stu-id="56682-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="56682-134">下面是仅限云身份的基本组件。</span><span class="sxs-lookup"><span data-stu-id="56682-134">Here are the basic components of cloud-only identity.</span></span>
 
![仅限云标识的基本组件](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="56682-136">内部部署和远程 (联机) 用户使用其 Azure AD 用户帐户和密码来访问 Microsoft 365 云服务。</span><span class="sxs-lookup"><span data-stu-id="56682-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="56682-137">Azure AD 根据其存储用户帐户和密码对用户凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="56682-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="56682-138">管理</span><span class="sxs-lookup"><span data-stu-id="56682-138">Administration</span></span>
<span data-ttu-id="56682-139">由于用户帐户仅存储在 Azure AD 中，因此可使用 [Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/add-users/) 和 [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)等工具管理云标识。</span><span class="sxs-lookup"><span data-stu-id="56682-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="56682-140">混合标识</span><span class="sxs-lookup"><span data-stu-id="56682-140">Hybrid identity</span></span>

<span data-ttu-id="56682-141">混合标识使用源自内部部署 AD DS 的帐户，并在 Microsoft 365 订阅的 Azure AD 租户中拥有副本。</span><span class="sxs-lookup"><span data-stu-id="56682-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="56682-142">但是，大多数更改仅以单向方式流动。</span><span class="sxs-lookup"><span data-stu-id="56682-142">However, most changes only flow one way.</span></span> <span data-ttu-id="56682-143">对 AD DS 用户帐户所做的更改将同步到其在 Azure AD 中的副本。</span><span class="sxs-lookup"><span data-stu-id="56682-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="56682-144">但是，在 Azure AD 中对基于云的帐户所做的更改（例如，新用户帐户）不会与 AD DS 同步。</span><span class="sxs-lookup"><span data-stu-id="56682-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="56682-145">Azure AD Connect 提供了持续的帐户同步。</span><span class="sxs-lookup"><span data-stu-id="56682-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="56682-146">它在本地服务器上运行，检查 AD DS 中的更改，并将这些更改转发到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="56682-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="56682-147">Azure AD Connect 提供了筛选要同步的帐户以及是否同步哈希版本的用户密码（称为密码哈希同步 (PHS) ）的功能。</span><span class="sxs-lookup"><span data-stu-id="56682-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="56682-148">在实现混合标识时，内部部署 AD DS 是帐户信息的权威源。</span><span class="sxs-lookup"><span data-stu-id="56682-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="56682-149">这意味着您在内部部署中经常执行管理任务，这些任务随后将同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="56682-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="56682-150">下面是混合标识的组件。</span><span class="sxs-lookup"><span data-stu-id="56682-150">Here are the components of hybrid identity.</span></span>

![混合标识的组件](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="56682-152">Azure AD 租户具有 AD DS 帐户的副本。</span><span class="sxs-lookup"><span data-stu-id="56682-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="56682-153">在此配置中，本地用户和远程用户都在访问 Microsoft 365 云服务，并针对 Azure AD 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="56682-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="56682-154">始终需要使用 Azure AD Connect 为混合标识同步用户帐户。</span><span class="sxs-lookup"><span data-stu-id="56682-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="56682-155">您需要在 Azure AD 中同步用户帐户，才能执行许可证分配和组管理、配置权限以及其他涉及用户帐户的管理任务。</span><span class="sxs-lookup"><span data-stu-id="56682-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="56682-156">管理</span><span class="sxs-lookup"><span data-stu-id="56682-156">Administration</span></span>

<span data-ttu-id="56682-157">由于原始和权威用户帐户存储在内部部署 AD DS 中，因此您可以在管理 AD DS 时使用相同的工具管理您的标识。</span><span class="sxs-lookup"><span data-stu-id="56682-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="56682-158">您不使用 microsoft 365 管理中心或 PowerShell for Microsoft 365 管理 Azure AD 中的同步用户帐户。</span><span class="sxs-lookup"><span data-stu-id="56682-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="56682-159">后续步骤</span><span class="sxs-lookup"><span data-stu-id="56682-159">Next step</span></span>

<span data-ttu-id="56682-160">如果您需要仅限云的标识模型，请参阅 [仅限云标识](cloud-only-identities.md)。</span><span class="sxs-lookup"><span data-stu-id="56682-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="56682-161">如果需要混合标识模型，请参阅 [混合标识](plan-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="56682-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="56682-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56682-162">See also</span></span>

[<span data-ttu-id="56682-163">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="56682-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
