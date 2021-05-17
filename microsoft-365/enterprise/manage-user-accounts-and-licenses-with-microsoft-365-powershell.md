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
description: 了解如何使用 PowerShell Microsoft 365用户帐户、许可证和组。
ms.openlocfilehash: d3745b9365c67615efe32881408d1a717b8dbbed
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371532"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="37318-103">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="37318-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="37318-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="37318-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="37318-105">Microsoft 365管理员需要管理用户帐户、许可证和组。</span><span class="sxs-lookup"><span data-stu-id="37318-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="37318-106">尽管可以在管理中心内执行大部分Microsoft 365，但一些任务在 PowerShell 中更简单。</span><span class="sxs-lookup"><span data-stu-id="37318-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="37318-107">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="37318-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="37318-108">用户帐户</span><span class="sxs-lookup"><span data-stu-id="37318-108">User accounts</span></span>

- [<span data-ttu-id="37318-109">创建用户帐户</span><span class="sxs-lookup"><span data-stu-id="37318-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-110">查看用户帐户</span><span class="sxs-lookup"><span data-stu-id="37318-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-111">配置用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="37318-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-112">向用户帐户分配角色</span><span class="sxs-lookup"><span data-stu-id="37318-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-113">删除和还原用户帐户</span><span class="sxs-lookup"><span data-stu-id="37318-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-114">阻止用户帐户</span><span class="sxs-lookup"><span data-stu-id="37318-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-115">密码</span><span class="sxs-lookup"><span data-stu-id="37318-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="37318-116">许可证和服务</span><span class="sxs-lookup"><span data-stu-id="37318-116">Licenses and services</span></span>
- [<span data-ttu-id="37318-117">查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="37318-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-118">查看已授权和未授权用户</span><span class="sxs-lookup"><span data-stu-id="37318-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-119">向用户帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="37318-119">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-120">查看帐户许可证和服务详细信息</span><span class="sxs-lookup"><span data-stu-id="37318-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-121">禁止访问服务</span><span class="sxs-lookup"><span data-stu-id="37318-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="37318-122">禁止访问 Sway</span><span class="sxs-lookup"><span data-stu-id="37318-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="37318-123">在分配用户许可证时禁止访问服务</span><span class="sxs-lookup"><span data-stu-id="37318-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="37318-124">删除用户帐户的许可证</span><span class="sxs-lookup"><span data-stu-id="37318-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="37318-125">组</span><span class="sxs-lookup"><span data-stu-id="37318-125">Groups</span></span>
- [<span data-ttu-id="37318-126">管理安全组</span><span class="sxs-lookup"><span data-stu-id="37318-126">Manage security groups</span></span>](manage-security-groups-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-127">维护安全组成员身份</span><span class="sxs-lookup"><span data-stu-id="37318-127">Maintain security group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37318-128">管理 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="37318-128">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
