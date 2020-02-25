---
title: 比较阻止访问 Office 365 的方法
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 了解当员工离开你的组织时，如何阻止对 Office 365 的访问。
ms.openlocfilehash: 3aafef37a43747557ef9a3fcda8ffe0fe3713717
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252464"
---
# <a name="compare-ways-to-block-access-to-office-365"></a><span data-ttu-id="4ec66-103">比较阻止访问 Office 365 的方法</span><span class="sxs-lookup"><span data-stu-id="4ec66-103">Compare ways to block access to Office 365</span></span>

<span data-ttu-id="4ec66-104">当员工离开你的组织时，如果有好的条款或糟糕，你需要阻止其访问 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4ec66-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Office 365.</span></span> <span data-ttu-id="4ec66-105">下面是可以执行此操作的几种方法。</span><span class="sxs-lookup"><span data-stu-id="4ec66-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="4ec66-106">**阻止访问的方法**</span><span class="sxs-lookup"><span data-stu-id="4ec66-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="4ec66-107">**定义**</span><span class="sxs-lookup"><span data-stu-id="4ec66-107">**Definition**</span></span> <br/> |<span data-ttu-id="4ec66-108">**最佳实践**</span><span class="sxs-lookup"><span data-stu-id="4ec66-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="4ec66-109">阻止登录</span><span class="sxs-lookup"><span data-stu-id="4ec66-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="4ec66-110">阻止用户访问 Office 365 的一种方法是将其登录状态更改为 **"已阻止登录"**。</span><span class="sxs-lookup"><span data-stu-id="4ec66-110">One way to block a user from accessing Office 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="4ec66-111">这样，他们就可以阻止他们的计算机和移动设备登录到 Office 365，尽管他们仍可以查看以前下载或同步的电子邮件和文档。</span><span class="sxs-lookup"><span data-stu-id="4ec66-111">This prevents them from signing into Office 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="4ec66-112">如果您使用的是 Blackberry 企业服务，则还可以禁用其访问。</span><span class="sxs-lookup"><span data-stu-id="4ec66-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="4ec66-113">当员工计划离开组织或计划进行长期请假时使用。</span><span class="sxs-lookup"><span data-stu-id="4ec66-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="4ec66-114">重置用户密码</span><span class="sxs-lookup"><span data-stu-id="4ec66-114">Reset user password</span></span>  <br/> |<span data-ttu-id="4ec66-115">阻止用户访问 Office 365 的另一种方法是重置其密码。</span><span class="sxs-lookup"><span data-stu-id="4ec66-115">Another way to prevent a user from accessing Office 365 is to reset their password.</span></span> <span data-ttu-id="4ec66-116">这样，他们仍可以查看以前下载或同步的电子邮件和文档，但不能使用其帐户。</span><span class="sxs-lookup"><span data-stu-id="4ec66-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="4ec66-117">然后，您可以将其登录并将密码更改为您选择的一个。</span><span class="sxs-lookup"><span data-stu-id="4ec66-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="4ec66-118">在员工突然且永久退出时使用，并且您认为业务数据有问题。</span><span class="sxs-lookup"><span data-stu-id="4ec66-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="4ec66-119">删除所有分配的许可证</span><span class="sxs-lookup"><span data-stu-id="4ec66-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="4ec66-120">另一种方法是删除分配给用户的任何 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="4ec66-120">Another option is to remove any Office 365 licenses assigned to the user.</span></span> <span data-ttu-id="4ec66-121">这样可以防止用户使用应用程序和服务，如 Office 套件、适用于 web 的 Office 应用程序、Yammer 和 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="4ec66-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="4ec66-122">他们仍可以登录但不能使用这些服务。</span><span class="sxs-lookup"><span data-stu-id="4ec66-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="4ec66-123">当您认为此用户不再需要访问 Office 365 中的特定功能时，请使用此功能。</span><span class="sxs-lookup"><span data-stu-id="4ec66-123">Use when you feel this user no longer needs access to specific features in Office 365.</span></span>  <br/> <br> <span data-ttu-id="4ec66-124">**重要说明：** 删除许可证时，将在30天内删除用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="4ec66-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="4ec66-125">相关文章</span><span class="sxs-lookup"><span data-stu-id="4ec66-125">Related articles</span></span>

[<span data-ttu-id="4ec66-126">分离从 Office 365 中的用户</span><span class="sxs-lookup"><span data-stu-id="4ec66-126">Offboard a user from Office 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="4ec66-127">在 Office 365 中重置用户密码</span><span class="sxs-lookup"><span data-stu-id="4ec66-127">Reset a user's password in Office 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="4ec66-128">在 Office 365 商业版中向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="4ec66-128">Assign licenses to users in Office 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="4ec66-129">在 Office 365 商业版中删除用户许可证</span><span class="sxs-lookup"><span data-stu-id="4ec66-129">Remove licenses from users in Office 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

