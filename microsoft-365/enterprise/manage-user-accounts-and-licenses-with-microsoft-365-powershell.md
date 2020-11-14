---
title: 使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/13/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: 了解如何使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组。
ms.openlocfilehash: ec60fcfe3c3d2c0e26cb2cca6a56741067d154c0
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073121"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="bf0fd-103">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="bf0fd-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="bf0fd-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="bf0fd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bf0fd-105">Microsoft 365 管理员需要管理用户帐户、许可证和组。</span><span class="sxs-lookup"><span data-stu-id="bf0fd-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="bf0fd-106">虽然您可以在 Microsoft 365 管理中心执行这些任务中的大多数，但在 PowerShell 中有些任务更容易。</span><span class="sxs-lookup"><span data-stu-id="bf0fd-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="bf0fd-107">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="bf0fd-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="bf0fd-108">用户帐户</span><span class="sxs-lookup"><span data-stu-id="bf0fd-108">User accounts</span></span>

- [<span data-ttu-id="bf0fd-109">创建用户帐户</span><span class="sxs-lookup"><span data-stu-id="bf0fd-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-110">查看用户帐户</span><span class="sxs-lookup"><span data-stu-id="bf0fd-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-111">配置用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="bf0fd-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-112">向用户帐户分配角色</span><span class="sxs-lookup"><span data-stu-id="bf0fd-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-113">删除和还原用户帐户</span><span class="sxs-lookup"><span data-stu-id="bf0fd-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-114">阻止用户帐户</span><span class="sxs-lookup"><span data-stu-id="bf0fd-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-115">密码</span><span class="sxs-lookup"><span data-stu-id="bf0fd-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="bf0fd-116">许可证和服务</span><span class="sxs-lookup"><span data-stu-id="bf0fd-116">Licenses and services</span></span>
- [<span data-ttu-id="bf0fd-117">查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="bf0fd-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-118">查看已授权和未授权用户</span><span class="sxs-lookup"><span data-stu-id="bf0fd-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-119">向用户帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="bf0fd-119">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-120">查看帐户许可证和服务详细信息</span><span class="sxs-lookup"><span data-stu-id="bf0fd-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-121">禁止访问服务</span><span class="sxs-lookup"><span data-stu-id="bf0fd-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="bf0fd-122">禁止访问 Sway</span><span class="sxs-lookup"><span data-stu-id="bf0fd-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="bf0fd-123">在分配用户许可证时禁止访问服务</span><span class="sxs-lookup"><span data-stu-id="bf0fd-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="bf0fd-124">删除用户帐户的许可证</span><span class="sxs-lookup"><span data-stu-id="bf0fd-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="bf0fd-125">组</span><span class="sxs-lookup"><span data-stu-id="bf0fd-125">Groups</span></span>
- [<span data-ttu-id="bf0fd-126">维护组成员身份</span><span class="sxs-lookup"><span data-stu-id="bf0fd-126">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="bf0fd-127">管理 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="bf0fd-127">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
