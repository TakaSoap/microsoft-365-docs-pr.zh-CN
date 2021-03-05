---
title: Microsoft 365 Defender 必备组件
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: afa5cd42545eddafb1d0ec1a6d88eb0903e07820
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454547"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="2f796-104">Microsoft 365 Defender 必备组件</span><span class="sxs-lookup"><span data-stu-id="2f796-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2f796-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2f796-105">**Applies to:**</span></span>
- <span data-ttu-id="2f796-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f796-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2f796-107">了解预配和使用 [Microsoft 365 Defender](microsoft-threat-protection.md)的许可和其他要求。</span><span class="sxs-lookup"><span data-stu-id="2f796-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2f796-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="2f796-108">Licensing requirements</span></span>
<span data-ttu-id="2f796-109">通过以下任一许可证，你无需额外付费即可访问 Microsoft 365 安全中心中的 Microsoft 365 Defender 功能：</span><span class="sxs-lookup"><span data-stu-id="2f796-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="2f796-110">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="2f796-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="2f796-111">Microsoft 365 E5 安全或 A5 安全</span><span class="sxs-lookup"><span data-stu-id="2f796-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="2f796-112">Windows 10 企业版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="2f796-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="2f796-113">企业移动性 + 安全性 (EMS) E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="2f796-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="2f796-114">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="2f796-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="2f796-115">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2f796-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2f796-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2f796-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="2f796-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2f796-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2f796-118">Defender for Office 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="2f796-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="2f796-119">有关详细信息，请参阅 [Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="2f796-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="2f796-120">还没有许可证？</span><span class="sxs-lookup"><span data-stu-id="2f796-120">Don't have license yet?</span></span> [<span data-ttu-id="2f796-121">试用或购买 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="2f796-121">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="2f796-122">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="2f796-122">Check your existing  licenses</span></span>
<span data-ttu-id="2f796-123">转到 Microsoft 365 管理中心 [ (admin.microsoft.com) ](https://admin.microsoft.com/) 查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="2f796-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="2f796-124">在管理中心，转到“计费” > “许可证”。</span><span class="sxs-lookup"><span data-stu-id="2f796-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="2f796-125">你需要在[Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 中分配"计费管理员"或"全局读者"角色，才能看到许可证信息。</span><span class="sxs-lookup"><span data-stu-id="2f796-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="2f796-126">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="2f796-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="2f796-127">所需权限</span><span class="sxs-lookup"><span data-stu-id="2f796-127">Required permissions</span></span>
<span data-ttu-id="2f796-128">你必须是 **Azure** Active Directory 中的全局管理员或安全管理员才能打开 Microsoft 365 Defender。 </span><span class="sxs-lookup"><span data-stu-id="2f796-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="2f796-129">有关使用 Microsoft 365 Defender 所需的角色列表以及如何控制对数据的访问权限的信息，请阅读有关管理对 [Microsoft 365 Defender](mtp-permissions.md)的访问的信息。</span><span class="sxs-lookup"><span data-stu-id="2f796-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="2f796-130">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="2f796-130">Browser requirements</span></span>
<span data-ttu-id="2f796-131">使用 Microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 Web 浏览器访问 Microsoft 365 安全中心中的 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="2f796-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="2f796-132">美国 GCC、GCC High 和其他美国政府机构的可用性</span><span class="sxs-lookup"><span data-stu-id="2f796-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="2f796-133">目前，Microsoft 365 Defender *不适用于* ：</span><span class="sxs-lookup"><span data-stu-id="2f796-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="2f796-134">美国政府社区云 (GCC) </span><span class="sxs-lookup"><span data-stu-id="2f796-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="2f796-135">美国政府社区云高 (GCC 高) </span><span class="sxs-lookup"><span data-stu-id="2f796-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="2f796-136">美国国防部</span><span class="sxs-lookup"><span data-stu-id="2f796-136">US Department of Defense</span></span>
- <span data-ttu-id="2f796-137">所有具有商业许可证的美国政府机构</span><span class="sxs-lookup"><span data-stu-id="2f796-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="2f796-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="2f796-138">Related topics</span></span>
- [<span data-ttu-id="2f796-139">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="2f796-139">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="2f796-140">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f796-140">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="2f796-141">管理访问和权限</span><span class="sxs-lookup"><span data-stu-id="2f796-141">Manage access and permissions</span></span>](mtp-permissions.md)
