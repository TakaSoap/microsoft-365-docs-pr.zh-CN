---
title: 在高级电子数据展示中设置用户和案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '了解如何配置用户角色、创建事例以及将用户分配给高级电子数据展示中的案例。  '
ms.openlocfilehash: 5c82ad8b630974d3afeb1928f8dd229ffb0dc36a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636066"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="8a128-103">在高级电子数据展示中设置用户和案例（经典）</span><span class="sxs-lookup"><span data-stu-id="8a128-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="8a128-104">本主题介绍如何为高级电子数据展示（经典）设置用户和案例。</span><span class="sxs-lookup"><span data-stu-id="8a128-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8a128-105">随着我们继续在较新版本的高级电子数据展示中进行投资，我们宣布退休了高级电子数据展示，也称为*高级电子数据展示（经典）* 或*高级电子数据展示 v1.0 1.0*。</span><span class="sxs-lookup"><span data-stu-id="8a128-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="8a128-106">如果仍在使用高级电子数据展示 v1.0，请尽快切换到[高级电子数据展示 v2.0](overview-ediscovery-20.md)（也称为 *Microsoft 365 中的高级电子数据展示解决方案*）。</span><span class="sxs-lookup"><span data-stu-id="8a128-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="8a128-107">高级电子数据展示 2.0 不仅包含高级电子数据展示 v1.0 中提供的类似功能，还提供了许多新功能，如保管人管理、沟通管理和审阅集。</span><span class="sxs-lookup"><span data-stu-id="8a128-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="8a128-108">若要了解停用高级电子数据展示 v1.0 的详细信息，请参阅[停用旧式电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。</span><span class="sxs-lookup"><span data-stu-id="8a128-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="8a128-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="8a128-109">Prerequisites</span></span>

<span data-ttu-id="8a128-110">在高级电子数据展示中设置事例和用户之前，需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="8a128-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="8a128-111">若要使用高级电子数据展示分析用户的数据，必须为用户（数据管理员）分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="8a128-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="8a128-112">或者，可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。</span><span class="sxs-lookup"><span data-stu-id="8a128-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="8a128-113">分配给案例并使用高级电子数据展示分析数据的管理员和合规性监察官不需要 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="8a128-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="8a128-114">您必须是安全&amp;合规中心中的电子数据展示管理器角色组的成员，才能创建电子数据展示事例并向其添加成员。</span><span class="sxs-lookup"><span data-stu-id="8a128-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="8a128-115">若要将自己添加到安全&amp;合规中心中的电子数据展示管理器角色组，您必须是组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="8a128-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="8a128-116">如果您不是全局管理员，则必须要求全局管理员将您添加到电子数据展示管理器角色组。</span><span class="sxs-lookup"><span data-stu-id="8a128-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="8a128-117">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="8a128-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="8a128-118">Microsoft 365 安全&amp;合规中心中的权限</span><span class="sxs-lookup"><span data-stu-id="8a128-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="8a128-119">在 Microsoft 365 安全&amp;合规中心中分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="8a128-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="8a128-120">步骤1：为用户分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="8a128-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="8a128-121">第一步是为用户分配安全&amp;合规性中心中的要求权限，以便可以将其添加为电子数据展示事例的成员。</span><span class="sxs-lookup"><span data-stu-id="8a128-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="8a128-122">在安全&amp;合规中心中将用户添加为案例的成员后，他们将能够在高级电子数据展示中访问此案例。</span><span class="sxs-lookup"><span data-stu-id="8a128-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="8a128-123">若要向用户分配必要的权限，以便可以将其添加为电子数据展示事例的成员，请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的第1步。</span><span class="sxs-lookup"><span data-stu-id="8a128-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="8a128-124">步骤2：创建电子数据展示事例并添加成员</span><span class="sxs-lookup"><span data-stu-id="8a128-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="8a128-125">下一步是在安全&amp;合规中心中创建新的电子数据展示事例并添加成员。</span><span class="sxs-lookup"><span data-stu-id="8a128-125">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="8a128-126">然后，这种情况的成员将能够访问高级电子数据展示中的案例。</span><span class="sxs-lookup"><span data-stu-id="8a128-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="8a128-127">若要创建新的电子数据展示事例，请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例中的](ediscovery-cases.md#step-2-create-a-new-case)步骤2。</span><span class="sxs-lookup"><span data-stu-id="8a128-127">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="8a128-128">若要将成员添加到电子数据展示事例，请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例中的](ediscovery-cases.md#step-3-add-members-to-a-case)步骤3</span><span class="sxs-lookup"><span data-stu-id="8a128-128">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="8a128-129">步骤3：在高级电子数据展示中进行案例</span><span class="sxs-lookup"><span data-stu-id="8a128-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="8a128-130">创建电子数据展示事例并添加成员后，您（或任何情况的成员）可以在高级电子数据展示中访问相应的事例。</span><span class="sxs-lookup"><span data-stu-id="8a128-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="8a128-131">若要在高级电子数据展示中访问事例，请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例中的](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)第8步。</span><span class="sxs-lookup"><span data-stu-id="8a128-131">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a128-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a128-132">See also</span></span>

[<span data-ttu-id="8a128-133">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="8a128-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8a128-134">准备数据</span><span class="sxs-lookup"><span data-stu-id="8a128-134">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
