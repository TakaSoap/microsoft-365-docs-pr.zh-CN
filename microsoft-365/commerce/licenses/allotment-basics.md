---
title: 分配基础知识
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: 了解新的分配功能。
ms.openlocfilehash: 62df346def3fd2577568916d2d668ca50542bdbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911610"
---
# <a name="allotment-basics"></a><span data-ttu-id="60b20-103">分配基础知识</span><span class="sxs-lookup"><span data-stu-id="60b20-103">Allotment basics</span></span>

<span data-ttu-id="60b20-104">通过许可证分配，你可以将许可证限制和许可证分配的委派管理仅委派给选择的产品和许可证限制。</span><span class="sxs-lookup"><span data-stu-id="60b20-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="60b20-105">分配使用基于组的许可向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="60b20-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="60b20-106">许可证限制可增加对分配给组中用户的许可证数的控制。</span><span class="sxs-lookup"><span data-stu-id="60b20-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="60b20-107">因此，即使你的组中用户数量增加，你也可以确保你符合你为分配设置的许可证限制。</span><span class="sxs-lookup"><span data-stu-id="60b20-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="60b20-108">您还可以委派对分配的管理。</span><span class="sxs-lookup"><span data-stu-id="60b20-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="60b20-109">委派的分配所有者获取对管理中心的访问权限，但只能查看和管理他们拥有的所有分配中的许可证。</span><span class="sxs-lookup"><span data-stu-id="60b20-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="60b20-110">这将在组织中更精细地委派许可证管理。</span><span class="sxs-lookup"><span data-stu-id="60b20-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60b20-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="60b20-111">Prerequisites</span></span>

<span data-ttu-id="60b20-112">必须满足基于组的许可 [的许可要求](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="60b20-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="60b20-113">可以将分配与提供给用户的任何产品一同使用：</span><span class="sxs-lookup"><span data-stu-id="60b20-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="60b20-114">Office 套件和独立产品</span><span class="sxs-lookup"><span data-stu-id="60b20-114">Office suites and standalone products</span></span>
- <span data-ttu-id="60b20-115">企业版和移动版产品</span><span class="sxs-lookup"><span data-stu-id="60b20-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="60b20-116">Dynamics 365 产品</span><span class="sxs-lookup"><span data-stu-id="60b20-116">Dynamics 365 products</span></span>

<span data-ttu-id="60b20-117">以下产品不能与分配一同使用：</span><span class="sxs-lookup"><span data-stu-id="60b20-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="60b20-118">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="60b20-118">Microsoft Store apps</span></span>
- <span data-ttu-id="60b20-119">永久软件，或直接分配给用户的软件（如果涉及任何许可证）。</span><span class="sxs-lookup"><span data-stu-id="60b20-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="60b20-120">Azure 资源</span><span class="sxs-lookup"><span data-stu-id="60b20-120">Azure resources</span></span>

<span data-ttu-id="60b20-121">你必须是全局管理员或许可证管理员才能开始分配。</span><span class="sxs-lookup"><span data-stu-id="60b20-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="60b20-122">入门</span><span class="sxs-lookup"><span data-stu-id="60b20-122">Getting started</span></span>

<span data-ttu-id="60b20-123">分配功能在专用预览版中仅对少数客户可用。</span><span class="sxs-lookup"><span data-stu-id="60b20-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="60b20-124">如果你对加入感兴趣，请填写此表单 [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) ：。</span><span class="sxs-lookup"><span data-stu-id="60b20-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>