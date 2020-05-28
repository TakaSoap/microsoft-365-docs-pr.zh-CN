---
title: 服务配额基础
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: 了解新的服务配额功能。
ms.openlocfilehash: c8c472fbf30bb898f9a10eca778ee7c668c8c388
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402410"
---
# <a name="allotment-basics"></a><span data-ttu-id="02b5a-103">服务配额基础</span><span class="sxs-lookup"><span data-stu-id="02b5a-103">Allotment basics</span></span>

<span data-ttu-id="02b5a-104">许可证分配允许您设置许可证限制，并将许可证分配的管理委派给您选择的产品和许可证限制。</span><span class="sxs-lookup"><span data-stu-id="02b5a-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="02b5a-105">服务配额使用基于组的许可将许可证分配给您的用户。</span><span class="sxs-lookup"><span data-stu-id="02b5a-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="02b5a-106">许可证限制提供了对为组中的用户分配多少个许可证而添加的控制。</span><span class="sxs-lookup"><span data-stu-id="02b5a-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="02b5a-107">因此，即使你的组中的用户数增加，你也可以确保你处于为你的服务配额设置的许可证限制内。</span><span class="sxs-lookup"><span data-stu-id="02b5a-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="02b5a-108">您还可以委派对您的服务配额的管理。</span><span class="sxs-lookup"><span data-stu-id="02b5a-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="02b5a-109">委派的配额分配所有者可以访问管理中心，但只能查看和管理他们拥有的服务配额中的许可证。</span><span class="sxs-lookup"><span data-stu-id="02b5a-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="02b5a-110">这提供了组织中的更精细的许可证管理委派。</span><span class="sxs-lookup"><span data-stu-id="02b5a-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02b5a-111">必备条件</span><span class="sxs-lookup"><span data-stu-id="02b5a-111">Prerequisites</span></span>

<span data-ttu-id="02b5a-112">您必须满足[基于组的许可](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)的许可要求。</span><span class="sxs-lookup"><span data-stu-id="02b5a-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="02b5a-113">您可以将服务配额用于用户可使用的任何产品：</span><span class="sxs-lookup"><span data-stu-id="02b5a-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="02b5a-114">Office 套件和独立产品</span><span class="sxs-lookup"><span data-stu-id="02b5a-114">Office suites and standalone products</span></span>
- <span data-ttu-id="02b5a-115">企业和移动产品</span><span class="sxs-lookup"><span data-stu-id="02b5a-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="02b5a-116">Dynamics 365 产品</span><span class="sxs-lookup"><span data-stu-id="02b5a-116">Dynamics 365 products</span></span>

<span data-ttu-id="02b5a-117">以下产品不能与服务配额一起使用：</span><span class="sxs-lookup"><span data-stu-id="02b5a-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="02b5a-118">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="02b5a-118">Microsoft Store apps</span></span>
- <span data-ttu-id="02b5a-119">永久软件或直接分配给用户的软件（如果没有涉及的许可证）。</span><span class="sxs-lookup"><span data-stu-id="02b5a-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="02b5a-120">Azure 资源</span><span class="sxs-lookup"><span data-stu-id="02b5a-120">Azure resources</span></span>

<span data-ttu-id="02b5a-121">您必须是全局或许可证管理员才能开始使用服务配额。</span><span class="sxs-lookup"><span data-stu-id="02b5a-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="02b5a-122">入门</span><span class="sxs-lookup"><span data-stu-id="02b5a-122">Getting started</span></span>

<span data-ttu-id="02b5a-123">仅在一小部分客户的私人预览版中提供服务配额功能。</span><span class="sxs-lookup"><span data-stu-id="02b5a-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="02b5a-124">如果你有兴趣加入，请填写以下表单： [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) 。</span><span class="sxs-lookup"><span data-stu-id="02b5a-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
