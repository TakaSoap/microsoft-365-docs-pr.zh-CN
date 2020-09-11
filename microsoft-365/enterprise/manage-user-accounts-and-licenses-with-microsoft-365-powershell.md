---
title: 使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.openlocfilehash: 0c6ca6a4165b616097405a9de178c254aa489a3c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429982"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="2317b-103">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="2317b-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="2317b-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="2317b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2317b-105">Microsoft 365 管理员需要管理用户帐户、许可证和组。</span><span class="sxs-lookup"><span data-stu-id="2317b-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="2317b-106">虽然您可以在 Microsoft 365 管理中心执行这些任务中的大多数，但在 PowerShell 中有些任务更容易。</span><span class="sxs-lookup"><span data-stu-id="2317b-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="2317b-107">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="2317b-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="2317b-108">用户帐户</span><span class="sxs-lookup"><span data-stu-id="2317b-108">User accounts</span></span>

- [<span data-ttu-id="2317b-109">创建用户帐户</span><span class="sxs-lookup"><span data-stu-id="2317b-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-110">查看用户帐户</span><span class="sxs-lookup"><span data-stu-id="2317b-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-111">配置用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="2317b-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-112">向用户帐户分配角色</span><span class="sxs-lookup"><span data-stu-id="2317b-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-113">删除和还原用户帐户</span><span class="sxs-lookup"><span data-stu-id="2317b-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-114">阻止用户帐户</span><span class="sxs-lookup"><span data-stu-id="2317b-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="2317b-115">许可证和服务</span><span class="sxs-lookup"><span data-stu-id="2317b-115">Licenses and services</span></span>
- [<span data-ttu-id="2317b-116">查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="2317b-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-117">查看已授权和未授权用户</span><span class="sxs-lookup"><span data-stu-id="2317b-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-118">向用户帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="2317b-118">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-119">查看帐户许可证和服务详细信息</span><span class="sxs-lookup"><span data-stu-id="2317b-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-120">禁止访问服务</span><span class="sxs-lookup"><span data-stu-id="2317b-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="2317b-121">禁止访问 Sway</span><span class="sxs-lookup"><span data-stu-id="2317b-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="2317b-122">在分配用户许可证时禁止访问服务</span><span class="sxs-lookup"><span data-stu-id="2317b-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="2317b-123">删除用户帐户的许可证</span><span class="sxs-lookup"><span data-stu-id="2317b-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="2317b-124">组</span><span class="sxs-lookup"><span data-stu-id="2317b-124">Groups</span></span>
- [<span data-ttu-id="2317b-125">维护组成员身份</span><span class="sxs-lookup"><span data-stu-id="2317b-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="2317b-126">管理 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="2317b-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
