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
ms.openlocfilehash: 386be1201b30e6b0e7a46c9de47dd6cf2fc4b53c
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412801"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="dc257-103">在高级电子数据展示中设置用户和案例（经典）</span><span class="sxs-lookup"><span data-stu-id="dc257-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="dc257-104">本主题介绍如何为高级电子数据展示（经典）设置用户和案例。</span><span class="sxs-lookup"><span data-stu-id="dc257-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dc257-105">当我们继续对较新版本的高级电子数据展示进行投资时，我们将宣布停用高级电子数据展示（也称为*高级电子数据展示（经典）* 或*高级电子数据展示 v1.0*）。</span><span class="sxs-lookup"><span data-stu-id="dc257-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="dc257-106">如果仍在使用高级电子数据展示 v1.0，请尽快切换到[高级电子数据展示 v2.0](overview-ediscovery-20.md)（也称为 *Microsoft 365 中的高级电子数据展示解决方案*）。</span><span class="sxs-lookup"><span data-stu-id="dc257-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="dc257-107">高级电子数据展示 2.0 不仅包含高级电子数据展示 v1.0 中提供的类似功能，还提供了许多新功能，如保管人管理、沟通管理和审阅集。</span><span class="sxs-lookup"><span data-stu-id="dc257-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="dc257-108">若要了解停用高级电子数据展示 v1.0 的详细信息，请参阅[停用旧式电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。</span><span class="sxs-lookup"><span data-stu-id="dc257-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="dc257-109">必备条件</span><span class="sxs-lookup"><span data-stu-id="dc257-109">Prerequisites</span></span>

<span data-ttu-id="dc257-110">在高级电子数据展示中设置事例和用户之前，需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="dc257-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="dc257-111">若要使用高级电子数据展示分析用户的数据，必须为用户（数据管理员）分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="dc257-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="dc257-112">或者，可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。</span><span class="sxs-lookup"><span data-stu-id="dc257-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="dc257-113">分配给案例并使用高级电子数据展示分析数据的管理员和合规性监察官不需要 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="dc257-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="dc257-114">您必须是安全合规中心中的电子数据展示管理器角色组的成员， &amp; 才能创建电子数据展示事例并向其添加成员。</span><span class="sxs-lookup"><span data-stu-id="dc257-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="dc257-115">若要将自己添加到安全合规中心中的电子数据展示管理器角色组 &amp; ，您必须是组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="dc257-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="dc257-116">如果您不是全局管理员，则必须要求全局管理员将您添加到电子数据展示管理器角色组。</span><span class="sxs-lookup"><span data-stu-id="dc257-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="dc257-117">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dc257-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="dc257-118">Microsoft 365 安全合规中心中的权限 &amp;</span><span class="sxs-lookup"><span data-stu-id="dc257-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="dc257-119">在 Microsoft 365 安全合规中心中分配电子数据展示权限 &amp;</span><span class="sxs-lookup"><span data-stu-id="dc257-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="dc257-120">步骤1：为用户分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="dc257-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="dc257-121">第一步是为用户分配安全合规性中心中的要求权限， &amp; 以便可以将其添加为电子数据展示事例的成员。</span><span class="sxs-lookup"><span data-stu-id="dc257-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="dc257-122">在安全合规中心中将用户添加为案例的成员后 &amp; ，他们将能够在高级电子数据展示中访问此案例。</span><span class="sxs-lookup"><span data-stu-id="dc257-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="dc257-123">若要向用户分配必要的权限，以便可以将其添加为电子数据展示事例的成员，请参阅[Microsoft 365 安全 &amp; 合规性中心中的电子数据展示事例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的第1步。</span><span class="sxs-lookup"><span data-stu-id="dc257-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="dc257-124">步骤2：创建电子数据展示事例并添加成员</span><span class="sxs-lookup"><span data-stu-id="dc257-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="dc257-125">下一步是在安全 & 合规性中心和添加成员中创建新的电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="dc257-125">The next step is to create a new eDiscovery case in the Security & Compliance Center and add members.</span></span> <span data-ttu-id="dc257-126">然后，这种情况的成员将能够访问高级电子数据展示中的案例。</span><span class="sxs-lookup"><span data-stu-id="dc257-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="dc257-127">若要创建新的电子数据展示事例，请参阅[Core eDiscovery 入门](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)中的步骤3。</span><span class="sxs-lookup"><span data-stu-id="dc257-127">To create a new eDiscovery case, see Step 3 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span></span>

2. <span data-ttu-id="dc257-128">若要将成员添加到电子数据展示事例，请参阅[核心电子数据展示入门](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)中的步骤4</span><span class="sxs-lookup"><span data-stu-id="dc257-128">To add members to an eDiscovery case, see Step 4 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span></span>

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="dc257-129">步骤3：在高级电子数据展示中进行案例</span><span class="sxs-lookup"><span data-stu-id="dc257-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="dc257-130">创建电子数据展示事例并添加成员后，您（或任何情况的成员）可以在高级电子数据展示中访问相应的事例。</span><span class="sxs-lookup"><span data-stu-id="dc257-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="dc257-131">若要在高级电子数据展示中访问事例，请参阅[高级电子数据展示中的访问案例](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="dc257-131">To access a case in Advanced eDiscovery, see [Accessing a case in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc257-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc257-132">See also</span></span>

[<span data-ttu-id="dc257-133">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="dc257-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="dc257-134">为高级电子数据展示准备数据（经典）</span><span class="sxs-lookup"><span data-stu-id="dc257-134">Preparing data for Advanced eDiscovery (classic)</span></span>](prepare-data-for-advanced-ediscovery.md)
 