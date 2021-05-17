---
title: 比较阻止访问的方法
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 了解如何在员工离开Microsoft 365时阻止对员工的访问权限。
ms.openlocfilehash: b913655065d4c57322aee6dc04e53f7a35cf5760
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399430"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="3fd73-103">比较阻止访问的方法</span><span class="sxs-lookup"><span data-stu-id="3fd73-103">Compare ways to block access</span></span>

<span data-ttu-id="3fd73-104">当员工离开组织时，如果条件好或坏，你需要阻止他们访问Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3fd73-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="3fd73-105">可通过以下几种方法实现此要求。</span><span class="sxs-lookup"><span data-stu-id="3fd73-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="3fd73-106">**阻止访问的方法**</span><span class="sxs-lookup"><span data-stu-id="3fd73-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="3fd73-107">**定义**</span><span class="sxs-lookup"><span data-stu-id="3fd73-107">**Definition**</span></span> <br/> |<span data-ttu-id="3fd73-108">**最佳做法**</span><span class="sxs-lookup"><span data-stu-id="3fd73-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="3fd73-109">阻止登录</span><span class="sxs-lookup"><span data-stu-id="3fd73-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="3fd73-110">阻止用户访问登录Microsoft 365一个方法就是将用户的登录状态更改为 **"已阻止登录"。**</span><span class="sxs-lookup"><span data-stu-id="3fd73-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="3fd73-111">这可以防止他们从计算机Microsoft 365登录电子邮件，尽管他们仍然可以查看以前下载或同步的电子邮件和文档。</span><span class="sxs-lookup"><span data-stu-id="3fd73-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="3fd73-112">如果你使用的是 Blackberry Enterprise 服务，也可以禁用其访问。</span><span class="sxs-lookup"><span data-stu-id="3fd73-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="3fd73-113">在员工计划离开组织或计划长期离开时使用。</span><span class="sxs-lookup"><span data-stu-id="3fd73-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="3fd73-114">重置用户密码</span><span class="sxs-lookup"><span data-stu-id="3fd73-114">Reset user password</span></span>  <br/> |<span data-ttu-id="3fd73-115">另一种防止用户访问Microsoft 365重置其密码。</span><span class="sxs-lookup"><span data-stu-id="3fd73-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="3fd73-116">这将阻止他们使用其帐户，尽管他们仍可查看以前下载或同步的电子邮件和文档。</span><span class="sxs-lookup"><span data-stu-id="3fd73-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="3fd73-117">然后，你可以以他们帐户登录，然后将密码更改为你选择的密码之一。</span><span class="sxs-lookup"><span data-stu-id="3fd73-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="3fd73-118">当员工突然永久离开，并且您觉得对业务数据有顾虑时，请使用 。</span><span class="sxs-lookup"><span data-stu-id="3fd73-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="3fd73-119">删除所有分配的许可证</span><span class="sxs-lookup"><span data-stu-id="3fd73-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="3fd73-120">另一个选项是删除Microsoft 365用户的任何许可证。</span><span class="sxs-lookup"><span data-stu-id="3fd73-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="3fd73-121">这将阻止他们使用应用程序和服务，如 Office 套件、Office Web 应用、Yammer和 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="3fd73-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="3fd73-122">他们仍可登录，但无法使用这些服务。</span><span class="sxs-lookup"><span data-stu-id="3fd73-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="3fd73-123">当您觉得此用户不再需要访问 Microsoft 365 中的特定功能时Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3fd73-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="3fd73-124">**重要提示：** 删除许可证后，用户邮箱将在 30 天后删除。</span><span class="sxs-lookup"><span data-stu-id="3fd73-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="3fd73-125">相关文章</span><span class="sxs-lookup"><span data-stu-id="3fd73-125">Related articles</span></span>

[<span data-ttu-id="3fd73-126">将用户从用户Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3fd73-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="3fd73-127">重置用户密码Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3fd73-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="3fd73-128">将许可证分配给企业Microsoft 365中的用户</span><span class="sxs-lookup"><span data-stu-id="3fd73-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="3fd73-129">在企业版中删除Microsoft 365许可证</span><span class="sxs-lookup"><span data-stu-id="3fd73-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

