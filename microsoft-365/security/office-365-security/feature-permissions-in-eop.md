---
title: EOP 中的功能权限
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 执行管理 Microsoft Exchange Online Protection (EOP) 的任务所需的权限根据正在管理的功能的不同而不同。
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638114"
---
# <a name="feature-permissions-in-eop"></a><span data-ttu-id="c3319-103">EOP 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="c3319-103">Feature permissions in EOP</span></span>

<span data-ttu-id="c3319-104">执行管理 Exchange Online Protection （EOP）的任务所需的权限视所管理的功能而变化。</span><span class="sxs-lookup"><span data-stu-id="c3319-104">The permissions required to perform tasks to manage Exchange Online Protection (EOP) vary depending on the feature you are managing.</span></span>

<span data-ttu-id="c3319-105">若要设置 EOP，您必须是全局管理员或 Exchange 公司管理员（组织管理角色组）。</span><span class="sxs-lookup"><span data-stu-id="c3319-105">To set up EOP, you must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span>

## <a name="exchange-online-protection-permissions"></a><span data-ttu-id="c3319-106">Exchange Online Protection 权限</span><span class="sxs-lookup"><span data-stu-id="c3319-106">Exchange Online Protection permissions</span></span>

<span data-ttu-id="c3319-p101">要找到管理 EOP 功能所需的权限，请参考下表：如果某个功能列出多个角色组，则您只需要被分配到其中一个角色组就可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="c3319-p101">To find out what permissions you need to manage EOP features, see the following table. If a feature lists more than one role group, you only need to be assigned one of the role groups to use the feature.</span></span>

|<span data-ttu-id="c3319-109">**功能**</span><span class="sxs-lookup"><span data-stu-id="c3319-109">**Feature**</span></span>|<span data-ttu-id="c3319-110">**所需的权限**</span><span class="sxs-lookup"><span data-stu-id="c3319-110">**Permissions required**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c3319-111">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="c3319-111">Anti-malware</span></span>|<span data-ttu-id="c3319-112">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-112">Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-113">安全管理</span><span class="sxs-lookup"><span data-stu-id="c3319-113">Hygiene Management</span></span>|
|<span data-ttu-id="c3319-114">反垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="c3319-114">Anti-spam</span></span>|<span data-ttu-id="c3319-115">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-115">Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-116">安全管理</span><span class="sxs-lookup"><span data-stu-id="c3319-116">Hygiene Management</span></span>|
|<span data-ttu-id="c3319-117">邮件流规则</span><span class="sxs-lookup"><span data-stu-id="c3319-117">Mail flow rules</span></span>|<span data-ttu-id="c3319-118">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-118">Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-119">记录管理</span><span class="sxs-lookup"><span data-stu-id="c3319-119">Records Management</span></span>|
|<span data-ttu-id="c3319-120">域</span><span class="sxs-lookup"><span data-stu-id="c3319-120">Domains</span></span>|<span data-ttu-id="c3319-121">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-121">Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-122">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-122">View-Only Organization Management</span></span>|
|<span data-ttu-id="c3319-123">高级威胁防护 (ATP)</span><span class="sxs-lookup"><span data-stu-id="c3319-123">Advanced Threat Protection (ATP)</span></span>|<span data-ttu-id="c3319-124">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-124">Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-125">安全管理</span><span class="sxs-lookup"><span data-stu-id="c3319-125">Hygiene Management</span></span>|
|<span data-ttu-id="c3319-126">Microsoft 365 连接器</span><span class="sxs-lookup"><span data-stu-id="c3319-126">Microsoft 365 connectors</span></span>|<span data-ttu-id="c3319-127">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-127">Organization Management</span></span>|
|<span data-ttu-id="c3319-128">邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="c3319-128">Message trace</span></span>|<span data-ttu-id="c3319-129">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-129">Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-130">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-130">View-Only Organization Management</span></span>|
|<span data-ttu-id="c3319-131">组织配置</span><span class="sxs-lookup"><span data-stu-id="c3319-131">Organization configuration</span></span>|<span data-ttu-id="c3319-132">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-132">Organization Management</span></span>|
|<span data-ttu-id="c3319-133">隔离</span><span class="sxs-lookup"><span data-stu-id="c3319-133">Quarantine</span></span>|<span data-ttu-id="c3319-134">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-134">Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-135">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-135">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-136">安全管理</span><span class="sxs-lookup"><span data-stu-id="c3319-136">Hygiene Management</span></span>|
|<span data-ttu-id="c3319-137">用户、联系人和角色组</span><span class="sxs-lookup"><span data-stu-id="c3319-137">Users, Contacts, and Role Groups</span></span>|<span data-ttu-id="c3319-138">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-138">Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-139">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-139">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-140">安全管理</span><span class="sxs-lookup"><span data-stu-id="c3319-140">Hygiene Management</span></span>|
|<span data-ttu-id="c3319-141">通讯组和安全组</span><span class="sxs-lookup"><span data-stu-id="c3319-141">Distribution Groups and Security Groups</span></span>|<span data-ttu-id="c3319-142">组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-142">Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-143">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="c3319-143">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="c3319-144">安全管理</span><span class="sxs-lookup"><span data-stu-id="c3319-144">Hygiene Management</span></span>|
|<span data-ttu-id="c3319-145">查看报告</span><span class="sxs-lookup"><span data-stu-id="c3319-145">View reports</span></span>|<span data-ttu-id="c3319-146">组织管理：访问邮件保护报告。</span><span class="sxs-lookup"><span data-stu-id="c3319-146">Organization Management: Access to mail protection reports.</span></span> <br/><br/> <span data-ttu-id="c3319-147">仅查看收件人：访问邮件保护报告。</span><span class="sxs-lookup"><span data-stu-id="c3319-147">View-Only Recipients: Access to mail protection reports.</span></span>  <br/><br/> <span data-ttu-id="c3319-148">合规性管理：访问邮件保护报告和数据丢失防护（DLP）报告（如果你的订阅具有 DLP 功能）。</span><span class="sxs-lookup"><span data-stu-id="c3319-148">Compliance Management: Access to mail protection reports and Data Loss Prevention (DLP) reports (if your subscription has DLP capabilities).</span></span>|
