---
title: 使用基于角色的访问控制向用户授予精细Microsoft Defender 安全中心
description: 在安全操作内创建角色和组以授予对门户的访问权限。
keywords: rbac， role， based， access， control， groups， control， tier， aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055353"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="e99b8-104">使用基于角色的访问控制管理门户访问</span><span class="sxs-lookup"><span data-stu-id="e99b8-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e99b8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e99b8-105">**Applies to:**</span></span>
- <span data-ttu-id="e99b8-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e99b8-106">Azure Active Directory</span></span>
- <span data-ttu-id="e99b8-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="e99b8-107">Office 365</span></span>

> <span data-ttu-id="e99b8-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="e99b8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e99b8-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e99b8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="e99b8-110">使用基于角色的访问控制 (RBAC) ，可以在安全操作团队内创建角色和组，以授予对门户的适当访问权限。</span><span class="sxs-lookup"><span data-stu-id="e99b8-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="e99b8-111">根据你创建的角色和组，你可以精细控制有权访问门户的用户可以看到和执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="e99b8-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="e99b8-112">大型异地分布式安全操作团队通常采用基于层的模型来分配和授权对安全门户的访问。</span><span class="sxs-lookup"><span data-stu-id="e99b8-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="e99b8-113">典型的层包括以下三个级别：</span><span class="sxs-lookup"><span data-stu-id="e99b8-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="e99b8-114">层</span><span class="sxs-lookup"><span data-stu-id="e99b8-114">Tier</span></span> | <span data-ttu-id="e99b8-115">说明</span><span class="sxs-lookup"><span data-stu-id="e99b8-115">Description</span></span>
:---|:---
<span data-ttu-id="e99b8-116">第 1 层</span><span class="sxs-lookup"><span data-stu-id="e99b8-116">Tier 1</span></span> | <span data-ttu-id="e99b8-117">**本地安全运营团队/IT 团队**</span><span class="sxs-lookup"><span data-stu-id="e99b8-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="e99b8-118">此团队通常会会审并调查其地理位置中包含的警报，并上报至第 2 层（如果需要进行主动修正）。</span><span class="sxs-lookup"><span data-stu-id="e99b8-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="e99b8-119">第 2 层</span><span class="sxs-lookup"><span data-stu-id="e99b8-119">Tier 2</span></span> | <span data-ttu-id="e99b8-120">**区域安全运营团队**</span><span class="sxs-lookup"><span data-stu-id="e99b8-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="e99b8-121">此团队可以看到其区域的所有设备并执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="e99b8-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="e99b8-122">第 3 层</span><span class="sxs-lookup"><span data-stu-id="e99b8-122">Tier 3</span></span> | <span data-ttu-id="e99b8-123">**全局安全运营团队**</span><span class="sxs-lookup"><span data-stu-id="e99b8-123">**Global security operations team**</span></span> <br> <span data-ttu-id="e99b8-124">此团队由安全专家组成，有权从门户查看和执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="e99b8-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="e99b8-125">Defender for Endpoint RBAC 旨在支持你基于层或基于角色的选择模型，让你可以精细地控制哪些角色可以看到、他们可以访问的设备以及他们可以采取的操作。</span><span class="sxs-lookup"><span data-stu-id="e99b8-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="e99b8-126">RBAC 框架以以下控件为中心：</span><span class="sxs-lookup"><span data-stu-id="e99b8-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="e99b8-127">**控制谁可以采取特定操作**</span><span class="sxs-lookup"><span data-stu-id="e99b8-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="e99b8-128">创建自定义角色并控制他们可以通过粒度访问的 Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="e99b8-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="e99b8-129">**控制谁可以看到有关特定设备组的信息**</span><span class="sxs-lookup"><span data-stu-id="e99b8-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="e99b8-130">[按特定条件](machine-groups.md)（如名称、标记、域和其他条件）创建设备组，然后使用特定的 Azure AD Azure Active Directory (向) 授予角色访问权限。</span><span class="sxs-lookup"><span data-stu-id="e99b8-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="e99b8-131">若要实现基于角色的访问，你需要定义管理员角色、分配相应的权限，以及分配分配给这些角色的 Azure AD 用户组。</span><span class="sxs-lookup"><span data-stu-id="e99b8-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="e99b8-132">开始之前</span><span class="sxs-lookup"><span data-stu-id="e99b8-132">Before you begin</span></span>
<span data-ttu-id="e99b8-133">在使用 RBAC 之前，了解可以授予权限的角色以及启用 RBAC 的后果非常重要。</span><span class="sxs-lookup"><span data-stu-id="e99b8-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="e99b8-134">在启用该功能之前，你必须在 Azure AD 中拥有全局管理员角色或安全管理员角色，并且你的 Azure AD 组已准备好降低被锁定在门户外的风险，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="e99b8-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="e99b8-135">首次登录时Microsoft Defender 安全中心，将被授予完全访问权限或只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="e99b8-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="e99b8-136">完全访问权限授予在 Azure AD 中具有安全管理员或全局管理员角色的用户。</span><span class="sxs-lookup"><span data-stu-id="e99b8-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="e99b8-137">只读访问权限授予在 Azure AD 中具有安全读者角色的用户。</span><span class="sxs-lookup"><span data-stu-id="e99b8-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="e99b8-138">具有 Defender for Endpoint 全局管理员角色的用户可以不受限制地访问所有设备，无论其设备组关联和 Azure AD 用户组分配如何</span><span class="sxs-lookup"><span data-stu-id="e99b8-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="e99b8-139">最初，只有具有 Azure AD 全局管理员或安全管理员权限的用户才能在 Microsoft Defender 安全中心 中创建和分配角色，因此在 Azure AD 中准备好正确的组非常重要。</span><span class="sxs-lookup"><span data-stu-id="e99b8-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="e99b8-140">**启用基于角色的访问控制将导致具有只读权限的用户 (例如，分配给 Azure AD 安全读者角色) 的用户将失去访问权限，直到他们被分配到角色。**</span><span class="sxs-lookup"><span data-stu-id="e99b8-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="e99b8-141">具有管理员权限的用户将自动分配具有完整权限的默认内置 Defender 全局管理员角色 Defender。</span><span class="sxs-lookup"><span data-stu-id="e99b8-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="e99b8-142">选择使用 RBAC 后，可以将不是 Azure AD 全局管理员或安全管理员的其他用户分配到 Defender for Endpoint 全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="e99b8-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="e99b8-143">选择使用 RBAC 后，无法像首次登录门户时一样还原到初始角色。</span><span class="sxs-lookup"><span data-stu-id="e99b8-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="e99b8-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="e99b8-144">Related topic</span></span>
- [<span data-ttu-id="e99b8-145">在 Microsoft Defender for Endpoint 中创建和管理设备组</span><span class="sxs-lookup"><span data-stu-id="e99b8-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
