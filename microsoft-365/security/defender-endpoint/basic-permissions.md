---
title: 使用基本权限访问Microsoft Defender 安全中心
description: 了解如何使用基本权限访问 Microsoft Defender for Endpoint 门户。
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
ms.technology: mde
ms.openlocfilehash: 2d022e903111c498d6f3b7411857748fcb637b64
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844654"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="268db-104">使用基本权限访问门户</span><span class="sxs-lookup"><span data-stu-id="268db-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="268db-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="268db-105">**Applies to:**</span></span>
- <span data-ttu-id="268db-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="268db-106">Azure Active Directory</span></span>
- [<span data-ttu-id="268db-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="268db-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="268db-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="268db-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="268db-109">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="268db-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="268db-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="268db-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="268db-111">请参阅下面的说明以使用基本权限管理。</span><span class="sxs-lookup"><span data-stu-id="268db-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="268db-112">可以使用以下任一解决方案：</span><span class="sxs-lookup"><span data-stu-id="268db-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="268db-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="268db-113">Azure PowerShell</span></span>
- <span data-ttu-id="268db-114">Azure 门户</span><span class="sxs-lookup"><span data-stu-id="268db-114">Azure portal</span></span>

<span data-ttu-id="268db-115">若要精细控制权限， [请切换到基于角色的访问控制](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="268db-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="268db-116">使用资源分配Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="268db-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="268db-117">您可以向用户分配以下权限级别之一：</span><span class="sxs-lookup"><span data-stu-id="268db-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="268db-118">可读写 (完全访问权限) </span><span class="sxs-lookup"><span data-stu-id="268db-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="268db-119">只读访问</span><span class="sxs-lookup"><span data-stu-id="268db-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="268db-120">准备工作</span><span class="sxs-lookup"><span data-stu-id="268db-120">Before you begin</span></span>

- <span data-ttu-id="268db-121">安装 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="268db-121">Install Azure PowerShell.</span></span> <span data-ttu-id="268db-122">有关详细信息，请参阅如何安装和配置[Azure PowerShell。](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)</span><span class="sxs-lookup"><span data-stu-id="268db-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="268db-123">需要在提升的命令行中运行 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="268db-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="268db-124">连接文件Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="268db-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="268db-125">有关详细信息，请参阅[连接-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="268db-125">For more information, see [Connect-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="268db-126">**完全访问权限**</span><span class="sxs-lookup"><span data-stu-id="268db-126">**Full access**</span></span> <br>
<span data-ttu-id="268db-127">具有完全访问权限的用户可以登录、查看所有系统信息并解决警报、提交文件进行深入分析以及下载载入程序包。</span><span class="sxs-lookup"><span data-stu-id="268db-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="268db-128">分配完全访问权限需要将用户添加到"安全管理员"或"全局管理员"AAD 内置角色。</span><span class="sxs-lookup"><span data-stu-id="268db-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="268db-129">**只读访问**</span><span class="sxs-lookup"><span data-stu-id="268db-129">**Read-only access**</span></span> <br>
<span data-ttu-id="268db-130">具有只读访问权限的用户可以登录、查看所有警报和相关信息。</span><span class="sxs-lookup"><span data-stu-id="268db-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="268db-131">他们将不能更改警报状态、提交文件进行深入分析或执行任何状态更改操作。</span><span class="sxs-lookup"><span data-stu-id="268db-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="268db-132">分配只读访问权限需要将用户添加到"安全读者"Azure AD 内置角色。</span><span class="sxs-lookup"><span data-stu-id="268db-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="268db-133">使用以下步骤分配安全角色：</span><span class="sxs-lookup"><span data-stu-id="268db-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="268db-134">对于 **读取和写入** 权限，请通过使用以下命令将用户分配给安全管理员角色：</span><span class="sxs-lookup"><span data-stu-id="268db-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="268db-135">对于 **只读访问权限** ，请通过使用以下命令将用户分配给安全读者角色：</span><span class="sxs-lookup"><span data-stu-id="268db-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="268db-136">有关详细信息，请参阅使用 Azure Active Directory 添加[或删除Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="268db-136">For more information, see [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="268db-137">使用 Azure 门户分配用户访问权限</span><span class="sxs-lookup"><span data-stu-id="268db-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="268db-138">有关详细信息，请参阅 Assign [administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="268db-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="268db-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="268db-139">Related topic</span></span>

- [<span data-ttu-id="268db-140">使用 RBAC 管理门户访问</span><span class="sxs-lookup"><span data-stu-id="268db-140">Manage portal access using RBAC</span></span>](rbac.md)
