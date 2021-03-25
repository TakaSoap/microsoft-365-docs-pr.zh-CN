---
title: 委派管理常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 管理员可以查看有关 Microsoft 365 中针对 Microsoft 合作伙伴和经销商的委派管理任务的常见问题和解答。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82fa70a8025f67610032ba59368bc74789b60f84
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203663"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="6efd6-103">委派管理常见问题解答</span><span class="sxs-lookup"><span data-stu-id="6efd6-103">Delegated administration FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6efd6-104">本文提供有关 Microsoft 365 中针对 Microsoft 合作伙伴和经销商的委派管理任务的常见问题和解答。</span><span class="sxs-lookup"><span data-stu-id="6efd6-104">This article provides frequently asked questions and answers about delegated administration tasks in Microsoft 365 for Microsoft partners and resellers.</span></span> <span data-ttu-id="6efd6-105">委派管理包括管理 Exchange Online Protection (EOP) 公司的其他租户 (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="6efd6-105">Delegated administration includes the ability to manage Exchange Online Protection (EOP) settings for other tenants (companies).</span></span>

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a><span data-ttu-id="6efd6-106">我是经销商，需要管理我的客户租户。</span><span class="sxs-lookup"><span data-stu-id="6efd6-106">I'm a reseller and I need to manage my customer tenants.</span></span> <span data-ttu-id="6efd6-107">这如何工作？</span><span class="sxs-lookup"><span data-stu-id="6efd6-107">How does this work?</span></span>

<span data-ttu-id="6efd6-108">如果你是 Microsoft 合作伙伴或经销商，并且已注册成为 Microsoft 顾问，可以在客户的 Microsoft 365 组织中请求委派管理功能。 </span><span class="sxs-lookup"><span data-stu-id="6efd6-108">If you're a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request _delegated administration_ capabilities in your customer's Microsoft 365 organization.</span></span>

<span data-ttu-id="6efd6-109">委派管理允许你管理 Microsoft 365 (包括 EOP 设置) 就像你是该组织内的管理员一样。</span><span class="sxs-lookup"><span data-stu-id="6efd6-109">Delegated administration allows you to manage Microsoft 365  (including EOP settings) as if you were an admin within that organization.</span></span> <span data-ttu-id="6efd6-110">下面列出了配置委派管理的步骤：</span><span class="sxs-lookup"><span data-stu-id="6efd6-110">The steps to configure delegated administration are described in the following list:</span></span>

1. <span data-ttu-id="6efd6-111">注册成为 [Microsoft Office 365 顾问](https://partner.microsoft.com/?cloudbenefits)。</span><span class="sxs-lookup"><span data-stu-id="6efd6-111">Sign up to be a [Microsoft Office 365 Advisor](https://partner.microsoft.com/?cloudbenefits).</span></span>

2. <span data-ttu-id="6efd6-112">注册委派管理。</span><span class="sxs-lookup"><span data-stu-id="6efd6-112">Sign up for delegated administration.</span></span> <span data-ttu-id="6efd6-113">在你开始管理客户的租户之前，他们必须授权你成为委派管理员。</span><span class="sxs-lookup"><span data-stu-id="6efd6-113">Before you can start administering a customer's tenant, they must authorize you as a delegated administrator.</span></span> <span data-ttu-id="6efd6-114">若要获得其批准，您 [首先会向这些用户发送委派管理产品/服务](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。</span><span class="sxs-lookup"><span data-stu-id="6efd6-114">To obtain their approval, you first [send them an offer for delegated administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> <span data-ttu-id="6efd6-115">还可以在以后为客户提供委派管理。</span><span class="sxs-lookup"><span data-stu-id="6efd6-115">You can also offer delegated administration to your customer at a later time.</span></span>

3. <span data-ttu-id="6efd6-116">使用添加、更改或删除订阅顾问合作伙伴 中的步骤创建 [委派管理员帐户](../../admin/misc/add-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="6efd6-116">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](../../admin/misc/add-partner.md).</span></span>

<span data-ttu-id="6efd6-117">访问 [合作伙伴：建立业务和管理合作伙伴订阅](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) ，详细了解如何设置委派管理。</span><span class="sxs-lookup"><span data-stu-id="6efd6-117">Visit [Partners: Build your business and administer partner subscription](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up delegated administration.</span></span>

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a><span data-ttu-id="6efd6-118">我是客户，不是经销商。</span><span class="sxs-lookup"><span data-stu-id="6efd6-118">I'm a customer, not a reseller.</span></span> <span data-ttu-id="6efd6-119">如何为我的子模板设置委派管理员？</span><span class="sxs-lookup"><span data-stu-id="6efd6-119">How can set up delegated administrator for my subtenants?</span></span>

<span data-ttu-id="6efd6-120">委派管理仅适用于经销商和合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="6efd6-120">Delegated administration is only available for resellers and partners.</span></span> <span data-ttu-id="6efd6-121">但是，有一个示例 PowerShell 脚本可帮助您将策略应用到公司或 (的) 。</span><span class="sxs-lookup"><span data-stu-id="6efd6-121">However, there's a sample PowerShell script that will help you apply policies to your subtenants (companies).</span></span> <span data-ttu-id="6efd6-122">有关详细信息，请参阅将 [EOP 设置应用到多个租户的示例脚本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="6efd6-122">For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a><span data-ttu-id="6efd6-123">能否阻止下级管理员修改我的策略？</span><span class="sxs-lookup"><span data-stu-id="6efd6-123">Can I prevent my subtenant admin from modifying my policy?</span></span>

<span data-ttu-id="6efd6-124">不正确。</span><span class="sxs-lookup"><span data-stu-id="6efd6-124">No.</span></span> <span data-ttu-id="6efd6-125">Microsoft 365 当前没有此功能。</span><span class="sxs-lookup"><span data-stu-id="6efd6-125">Microsoft 365 does not currently have this capability.</span></span>

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a><span data-ttu-id="6efd6-126">我能否获得我的所有子模板的合并报告？</span><span class="sxs-lookup"><span data-stu-id="6efd6-126">Can I get consolidated reporting across all of my subtenants?</span></span>

<span data-ttu-id="6efd6-127">Microsoft 365 管理中心报告中未提供你管理的公司的合并报告。</span><span class="sxs-lookup"><span data-stu-id="6efd6-127">Consolidated reporting across the companies you manage isn't available in Microsoft 365 admin center reports.</span></span> <span data-ttu-id="6efd6-128">但是，可以使用 [Microsoft Graph](/graph/overview)获取报告。</span><span class="sxs-lookup"><span data-stu-id="6efd6-128">However, you can get reports by using [Microsoft Graph](/graph/overview).</span></span>