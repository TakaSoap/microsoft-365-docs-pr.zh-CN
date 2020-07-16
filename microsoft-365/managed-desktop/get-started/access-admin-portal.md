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
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146261"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="530eb-103">访问管理门户</span><span class="sxs-lookup"><span data-stu-id="530eb-103">Access the admin portal</span></span>

<span data-ttu-id="530eb-104">你的 Microsoft 托管桌面服务的网关是 Microsoft [Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="530eb-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="530eb-105">有关通常情况下使用和自定义 Azure 门户体验的详细信息，请参阅[azure 门户文档](https://docs.microsoft.com/azure/azure-portal/)。</span><span class="sxs-lookup"><span data-stu-id="530eb-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> 

<span data-ttu-id="530eb-106">您的管理帐户需要特定的权限才能访问 Microsoft 托管桌面管理门户。</span><span class="sxs-lookup"><span data-stu-id="530eb-106">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="530eb-107">通过使用基于角色的访问控制（RBAC），可以管理对组织中这些功能的管理员访问。</span><span class="sxs-lookup"><span data-stu-id="530eb-107">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="530eb-108">有关 Azure Active Directory 角色的详细信息，请参阅[Azure Active directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="530eb-108">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="530eb-109">为您的管理员用户帐户分配以下任何角色以确保访问：</span><span class="sxs-lookup"><span data-stu-id="530eb-109">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="530eb-110">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="530eb-110">Azure AD role</span></span>  |<span data-ttu-id="530eb-111">Microsoft 托管桌面权限</span><span class="sxs-lookup"><span data-stu-id="530eb-111">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="530eb-112">全局管理员</span><span class="sxs-lookup"><span data-stu-id="530eb-112">Global Administrator</span></span>     | <span data-ttu-id="530eb-113">具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有功能的**读取和写入权限**。</span><span class="sxs-lookup"><span data-stu-id="530eb-113">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="530eb-114">全局读取者</span><span class="sxs-lookup"><span data-stu-id="530eb-114">Global Reader</span></span>     | <span data-ttu-id="530eb-115">具有此角色的管理员将对 Microsoft 托管桌面管理门户中的所有功能具有**只读权限**。</span><span class="sxs-lookup"><span data-stu-id="530eb-115">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="530eb-116">Intune 服务管理员</span><span class="sxs-lookup"><span data-stu-id="530eb-116">Intune Service Administrator</span></span>     |  <span data-ttu-id="530eb-117">具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有功能的**读取和写入权限**。</span><span class="sxs-lookup"><span data-stu-id="530eb-117">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="530eb-118">服务支持管理员</span><span class="sxs-lookup"><span data-stu-id="530eb-118">Service Support Administrator</span></span>     | <span data-ttu-id="530eb-119">具有此角色的管理员将拥有对 Microsoft 托管桌面管理门户中所有功能的**读取和写入权限**。</span><span class="sxs-lookup"><span data-stu-id="530eb-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="530eb-120">只有全局管理员角色才具有在 Microsoft 托管桌面中*注册*组织所需的权限。</span><span class="sxs-lookup"><span data-stu-id="530eb-120">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="530eb-121">请注意，Azure Active Directory 角色将在各种 Microsoft 服务中提供用户帐户权限。</span><span class="sxs-lookup"><span data-stu-id="530eb-121">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="530eb-122">在 Microsoft 托管桌面完成注册后，应始终使用具有完成其他任务所需的*最少*权限的角色。</span><span class="sxs-lookup"><span data-stu-id="530eb-122">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="530eb-123">向管理员分配角色</span><span class="sxs-lookup"><span data-stu-id="530eb-123">Assigning roles to administrators</span></span>

<span data-ttu-id="530eb-124">如果你需要有关分配 Azure Active Directory 角色的帮助，请参阅[Azure Active directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="530eb-124">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
