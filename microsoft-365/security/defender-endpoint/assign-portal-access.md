---
title: 向用户分配Microsoft Defender 安全中心
description: 分配对 Microsoft Defender 终结点门户的读取和写入或只读访问权限。
keywords: 分配用户角色， 分配读取和写入访问权限， 分配只读访问权限， 用户， 用户角色， 角色
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164745"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="3c63a-104">向用户分配Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="3c63a-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3c63a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3c63a-105">**Applies to:**</span></span>
- <span data-ttu-id="3c63a-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3c63a-106">Azure Active Directory</span></span>
- <span data-ttu-id="3c63a-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="3c63a-107">Office 365</span></span>
- [<span data-ttu-id="3c63a-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3c63a-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3c63a-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c63a-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="3c63a-110">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="3c63a-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3c63a-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3c63a-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="3c63a-112">Defender for Endpoint 支持两种权限管理方法：</span><span class="sxs-lookup"><span data-stu-id="3c63a-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="3c63a-113">**基本权限管理**：将权限设置为完全访问或只读。</span><span class="sxs-lookup"><span data-stu-id="3c63a-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="3c63a-114">基于角色的访问控制 **(RBAC) ：** 通过定义角色、将 Azure AD 用户组分配给角色以及向用户组授予对设备组的访问权限来设置粒度权限。</span><span class="sxs-lookup"><span data-stu-id="3c63a-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="3c63a-115">有关 RBAC 详细信息，请参阅使用基于角色的访问控制管理 [门户访问](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="3c63a-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3c63a-116">如果已分配基本权限，可以随时切换到 RBAC。</span><span class="sxs-lookup"><span data-stu-id="3c63a-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="3c63a-117">进行切换之前，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="3c63a-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="3c63a-118">具有完全访问权限的用户 (Azure AD) 中分配了全局管理员或安全管理员目录角色的用户将自动分配有默认的 Defender for Endpoint 管理员角色，该角色也具有完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="3c63a-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="3c63a-119">切换到 RBAC 后，可以将其他 Azure AD 用户组分配给 Defender for Endpoint 管理员角色。</span><span class="sxs-lookup"><span data-stu-id="3c63a-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="3c63a-120">只有分配到 Defender for Endpoint 管理员角色的用户才能使用 RBAC 管理权限。</span><span class="sxs-lookup"><span data-stu-id="3c63a-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="3c63a-121">具有只读访问权限的用户 (安全读者) 分配角色之前，将失去对门户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3c63a-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="3c63a-122">请注意，在 RBAC 下只能为 Azure AD 用户组分配角色。</span><span class="sxs-lookup"><span data-stu-id="3c63a-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="3c63a-123">切换到 RBAC 后，将无法切换回使用基本权限管理。</span><span class="sxs-lookup"><span data-stu-id="3c63a-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c63a-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="3c63a-124">Related topics</span></span>

- [<span data-ttu-id="3c63a-125">使用基本权限访问门户</span><span class="sxs-lookup"><span data-stu-id="3c63a-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="3c63a-126">使用 RBAC 管理门户访问</span><span class="sxs-lookup"><span data-stu-id="3c63a-126">Manage portal access using RBAC</span></span>](rbac.md)
