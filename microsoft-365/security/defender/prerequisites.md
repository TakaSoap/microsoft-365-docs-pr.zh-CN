---
title: Microsoft 365 Defender 先决条件
description: 了解 Microsoft 365 Defender 的许可、硬件和软件要求以及其他配置设置
keywords: 要求， 先决条件， 硬件， 软件， 浏览器， MTP， M365， 许可证， E5， A5， EMS， 购买
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f9904ecb5b9ab0a0f634903a5dc0ee3049d06b38
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056079"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="6622f-104">Microsoft 365 Defender 先决条件</span><span class="sxs-lookup"><span data-stu-id="6622f-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6622f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6622f-105">**Applies to:**</span></span>
- <span data-ttu-id="6622f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6622f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6622f-107">了解有关预配和使用 [Microsoft 365 Defender](microsoft-365-defender.md)的许可和其他要求。</span><span class="sxs-lookup"><span data-stu-id="6622f-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-365-defender.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="6622f-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="6622f-108">Licensing requirements</span></span>
<span data-ttu-id="6622f-109">通过以下任一许可证，你无需额外付费即可访问 Microsoft 365 安全中心中的 Microsoft 365 Defender 功能：</span><span class="sxs-lookup"><span data-stu-id="6622f-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="6622f-110">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="6622f-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="6622f-111">Microsoft 365 E5 安全或 A5 安全</span><span class="sxs-lookup"><span data-stu-id="6622f-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="6622f-112">Windows 10 企业版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="6622f-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="6622f-113">企业移动性 + 安全性 (EMS) E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="6622f-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="6622f-114">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="6622f-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="6622f-115">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6622f-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="6622f-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="6622f-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="6622f-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6622f-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6622f-118">Defender for Office 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="6622f-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="6622f-119">有关详细信息，请参阅 [Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="6622f-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="6622f-120">还没有许可证？</span><span class="sxs-lookup"><span data-stu-id="6622f-120">Don't have license yet?</span></span> [<span data-ttu-id="6622f-121">试用或购买 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="6622f-121">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="6622f-122">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="6622f-122">Check your existing  licenses</span></span>
<span data-ttu-id="6622f-123">转到 Microsoft 365 管理中心 [ (admin.microsoft.com) ](https://admin.microsoft.com/) 查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="6622f-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="6622f-124">在管理中心，转到“计费” > “许可证”。</span><span class="sxs-lookup"><span data-stu-id="6622f-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="6622f-125">你需要分配有[Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的帐单管理员或全局读者角色，才能查看许可证信息。 </span><span class="sxs-lookup"><span data-stu-id="6622f-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="6622f-126">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="6622f-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="6622f-127">所需权限</span><span class="sxs-lookup"><span data-stu-id="6622f-127">Required permissions</span></span>
<span data-ttu-id="6622f-128">你必须是 **Azure** Active Directory 中的全局管理员或安全管理员才能启用 Microsoft 365 Defender。 </span><span class="sxs-lookup"><span data-stu-id="6622f-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="6622f-129">有关使用 Microsoft 365 Defender 所需的角色列表以及如何控制对数据的访问权限的信息，请阅读有关管理对 [Microsoft 365 Defender 的访问权限](m365d-permissions.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="6622f-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="6622f-130">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="6622f-130">Browser requirements</span></span>
<span data-ttu-id="6622f-131">使用 Microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 Web 浏览器访问 Microsoft 365 安全中心中的 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="6622f-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="6622f-132">可在美国 GCC、GCC High 和其他美国政府机构使用</span><span class="sxs-lookup"><span data-stu-id="6622f-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="6622f-133">目前，Microsoft 365 Defender *不可用于* ：</span><span class="sxs-lookup"><span data-stu-id="6622f-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="6622f-134">美国政府社区云 (GCC) </span><span class="sxs-lookup"><span data-stu-id="6622f-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="6622f-135">美国政府社区云高 (GCC 高) </span><span class="sxs-lookup"><span data-stu-id="6622f-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="6622f-136">美国国防部</span><span class="sxs-lookup"><span data-stu-id="6622f-136">US Department of Defense</span></span>
- <span data-ttu-id="6622f-137">所有拥有商业许可证的美国政府机构</span><span class="sxs-lookup"><span data-stu-id="6622f-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="6622f-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="6622f-138">Related topics</span></span>
- [<span data-ttu-id="6622f-139">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="6622f-139">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="6622f-140">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6622f-140">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="6622f-141">管理访问和权限</span><span class="sxs-lookup"><span data-stu-id="6622f-141">Manage access and permissions</span></span>](m365d-permissions.md)
