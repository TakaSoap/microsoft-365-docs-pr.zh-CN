---
title: 访问管理门户
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 420cdaabb607eacf0d7a7109827fe5437e2f999c
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530219"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="cc0e7-103">访问管理门户</span><span class="sxs-lookup"><span data-stu-id="cc0e7-103">Access the admin portal</span></span>

<span data-ttu-id="cc0e7-104">你的 Microsoft 托管桌面服务的网关是 Microsoft [Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="cc0e7-105">有关通常情况下使用和自定义 Azure 门户体验的详细信息，请参阅[azure 门户文档](https://docs.microsoft.com/azure/azure-portal/)。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> <span data-ttu-id="cc0e7-106">在预览中，您还可以在[Microsoft 终结点管理器](https://endpoint.microsoft.com/)中找到 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-106">Available in preview now, you can also find Microsoft Managed Desktop in the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="cc0e7-107">如果你不熟悉此门户的设备管理功能，请参阅[Microsoft 终结点管理器文档](https://docs.microsoft.com/mem/)。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-107">If you are unfamiliar with the capabilities of this portal for device management see the [Microsoft Endpoint Manager documentation](https://docs.microsoft.com/mem/).</span></span>

<span data-ttu-id="cc0e7-108">您的管理帐户需要特定的权限才能访问 Microsoft 托管桌面管理门户。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-108">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="cc0e7-109">通过使用基于角色的访问控制（RBAC），可以管理对组织中这些功能的管理员访问。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-109">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="cc0e7-110">有关 Azure Active Directory 角色的详细信息，请参阅[Azure Active directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-110">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="cc0e7-111">为您的管理员用户帐户分配以下任何角色以确保访问：</span><span class="sxs-lookup"><span data-stu-id="cc0e7-111">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="cc0e7-112">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="cc0e7-112">Azure AD role</span></span>  |<span data-ttu-id="cc0e7-113">Microsoft 托管桌面权限</span><span class="sxs-lookup"><span data-stu-id="cc0e7-113">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="cc0e7-114">全局管理员</span><span class="sxs-lookup"><span data-stu-id="cc0e7-114">Global Administrator</span></span>     | <span data-ttu-id="cc0e7-115">具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有功能的**读取和写入权限**。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-115">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="cc0e7-116">全局读取者</span><span class="sxs-lookup"><span data-stu-id="cc0e7-116">Global Reader</span></span>     | <span data-ttu-id="cc0e7-117">具有此角色的管理员将对 Microsoft 托管桌面管理门户中的所有功能具有**只读权限**。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-117">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="cc0e7-118">Intune 服务管理员</span><span class="sxs-lookup"><span data-stu-id="cc0e7-118">Intune Service Administrator</span></span>     |  <span data-ttu-id="cc0e7-119">具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有功能的**读取和写入权限**。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="cc0e7-120">服务支持管理员</span><span class="sxs-lookup"><span data-stu-id="cc0e7-120">Service Support Administrator</span></span>     | <span data-ttu-id="cc0e7-121">具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有功能的**读取和写入权限**。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-121">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="cc0e7-122">只有全局管理员角色才具有在 Microsoft 托管桌面中*注册*组织所需的权限。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-122">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="cc0e7-123">请注意，Azure Active Directory 角色将在各种 Microsoft 服务中提供用户帐户权限。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-123">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="cc0e7-124">在 Microsoft 托管桌面完成注册后，应始终使用具有完成其他任务所需的*最少*权限的角色。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-124">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="cc0e7-125">向管理员分配角色</span><span class="sxs-lookup"><span data-stu-id="cc0e7-125">Assigning roles to administrators</span></span>

<span data-ttu-id="cc0e7-126">如果你需要有关分配 Azure Active Directory 角色的帮助，请参阅[Azure Active directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="cc0e7-126">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
