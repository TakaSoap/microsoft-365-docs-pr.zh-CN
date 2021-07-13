---
title: Microsoft 365 Lighthouse租户列表概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，请了解租户列表。
ms.openlocfilehash: 05c6bf6c1b9529d05fac04c2d5c43802280cfbc9
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395024"
---
# <a name="microsoft-365-lighthouse-tenant-list-overview"></a><span data-ttu-id="e35ae-103">Microsoft 365 Lighthouse租户列表概述</span><span class="sxs-lookup"><span data-stu-id="e35ae-103">Microsoft 365 Lighthouse tenant list overview</span></span>

> [!NOTE]
> <span data-ttu-id="e35ae-104">本文中所述的功能在预览版中，可能会更改，并且仅对满足要求 [的合作伙伴可用](m365-lighthouse-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e35ae-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="e35ae-105">如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="e35ae-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="e35ae-106">"Microsoft 365 Lighthouse租户"列表提供你与不同租户有合约的见解，包括相对于租户的租户Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="e35ae-106">The Microsoft 365 Lighthouse tenant list provides insights into the different tenants you have a contract with, including tenant onboarding status relative to Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="e35ae-107">租户列表还允许你标记租户，以在整个 Microsoft 365 Lighthouse 中提供不同的筛选器，并向下钻取以了解有关给定租户及其部署计划状态的信息。</span><span class="sxs-lookup"><span data-stu-id="e35ae-107">The tenant list also lets you tag tenants to provide different filters throughout Microsoft 365 Lighthouse, and drill down to learn more about a given tenant and the status of their deployment plan.</span></span>

<span data-ttu-id="e35ae-108">租户满足载入Microsoft 365 Lighthouse [后](m365-lighthouse-requirements.md)，其状态 **将在租户列表中** 显示为"活动"。</span><span class="sxs-lookup"><span data-stu-id="e35ae-108">After your tenants meet the [Microsoft 365 Lighthouse onboarding requirements](m365-lighthouse-requirements.md), their status will show as **Active** in the tenant list.</span></span>

<span data-ttu-id="e35ae-109">若要访问租户列表中的Microsoft 365 Lighthouse，请选择左侧导航窗格中的"租户"以打开"租户"页面。</span><span class="sxs-lookup"><span data-stu-id="e35ae-109">To access the tenant list in Microsoft 365 Lighthouse, select **Tenants** in the left navigation pane to open the Tenants page.</span></span>

## <a name="tenant-status"></a><span data-ttu-id="e35ae-110">租户状态</span><span class="sxs-lookup"><span data-stu-id="e35ae-110">Tenant status</span></span>

<span data-ttu-id="e35ae-111">下表显示了不同的状态消息及其含义。</span><span class="sxs-lookup"><span data-stu-id="e35ae-111">The following table shows the different status messages and their meaning.</span></span><br><br>

| <span data-ttu-id="e35ae-112">状态消息</span><span class="sxs-lookup"><span data-stu-id="e35ae-112">Status message</span></span> | <span data-ttu-id="e35ae-113">说明</span><span class="sxs-lookup"><span data-stu-id="e35ae-113">Description</span></span> |
|--|--|
| <span data-ttu-id="e35ae-114">活动</span><span class="sxs-lookup"><span data-stu-id="e35ae-114">Active</span></span> | <span data-ttu-id="e35ae-115">载入和数据流已启动。</span><span class="sxs-lookup"><span data-stu-id="e35ae-115">Onboarding and data flow has started.</span></span> |
| <span data-ttu-id="e35ae-116">进程内</span><span class="sxs-lookup"><span data-stu-id="e35ae-116">In process</span></span> | <span data-ttu-id="e35ae-117">租户已发现，但尚未完全载入。</span><span class="sxs-lookup"><span data-stu-id="e35ae-117">Tenant discovered, but not fully onboarded.</span></span> |
| <span data-ttu-id="e35ae-118">不符合条件的 DAP</span><span class="sxs-lookup"><span data-stu-id="e35ae-118">Ineligible, DAP</span></span> | <span data-ttu-id="e35ae-119">需要 DAP (委派) 权限。</span><span class="sxs-lookup"><span data-stu-id="e35ae-119">Delegated Admin Privileges (DAP) setup is required.</span></span> |
| <span data-ttu-id="e35ae-120">不符合资格的用户计数</span><span class="sxs-lookup"><span data-stu-id="e35ae-120">Ineligible, user count</span></span> | <span data-ttu-id="e35ae-121">租户具有的用户数多于允许的用户数。</span><span class="sxs-lookup"><span data-stu-id="e35ae-121">Tenant has more users than allowed.</span></span> |
| <span data-ttu-id="e35ae-122">不符合资格的许可证</span><span class="sxs-lookup"><span data-stu-id="e35ae-122">Ineligible, license</span></span> | <span data-ttu-id="e35ae-123">租户没有所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="e35ae-123">Tenant does not have required license.</span></span> |
| <span data-ttu-id="e35ae-124">非活动</span><span class="sxs-lookup"><span data-stu-id="e35ae-124">Inactive</span></span> | <span data-ttu-id="e35ae-125">租户不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="e35ae-125">Tenant is no longer active.</span></span> |

<span data-ttu-id="e35ae-126">停用租户后，在用户完成停用过程Microsoft 365 Lighthouse无法对租户采取措施。</span><span class="sxs-lookup"><span data-stu-id="e35ae-126">Once you inactivate a tenant, you can't take action on the tenant while Microsoft 365 Lighthouse completes the inactivation process.</span></span> <span data-ttu-id="e35ae-127">停用可能需要 48 小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="e35ae-127">It may take up to 48 hours for inactivation to complete.</span></span>

<span data-ttu-id="e35ae-128">如果决定重新激活租户，可能需要 48 小时才能重新显示数据。</span><span class="sxs-lookup"><span data-stu-id="e35ae-128">If you decide to reactivate a tenant, it may take up to 48 hours for data to reappear.</span></span>

## <a name="tenant-tags"></a><span data-ttu-id="e35ae-129">租户标记</span><span class="sxs-lookup"><span data-stu-id="e35ae-129">Tenant tags</span></span>

<span data-ttu-id="e35ae-130">可以在客户租户内使用自定义标签Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="e35ae-130">You can tag your customer tenants with a custom label within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="e35ae-131">这些标记可用于组织租户，还可以帮助您轻松筛选可供相关客户租户集使用的现有视图和见解。</span><span class="sxs-lookup"><span data-stu-id="e35ae-131">These tags can be used to organize your tenants and can also help you easily filter the existing views and insights available to relevant sets of customer tenants.</span></span> <span data-ttu-id="e35ae-132">还可以从"租户"页面管理标记及其分配到的租户。</span><span class="sxs-lookup"><span data-stu-id="e35ae-132">You can also manage your tags and which tenants they're assigned to from the Tenants page.</span></span>

## <a name="related-content"></a><span data-ttu-id="e35ae-133">相关内容</span><span class="sxs-lookup"><span data-stu-id="e35ae-133">Related content</span></span>

<span data-ttu-id="e35ae-134">[本文Microsoft 365 Lighthouse (](m365-lighthouse-requirements.md)的要求) </span><span class="sxs-lookup"><span data-stu-id="e35ae-134">[Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (article)</span></span>\
<span data-ttu-id="e35ae-135">[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="e35ae-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>