---
title: Microsoft 365 Defender 先决条件
description: 了解 Microsoft 365 Defender 的许可、硬件和软件要求以及其他配置设置
keywords: 要求、先决条件、硬件、软件、浏览器、MTP、M365、许可证、E5、A5、EMS、purchase
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844772"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="1d25f-104">Microsoft 365 Defender 先决条件</span><span class="sxs-lookup"><span data-stu-id="1d25f-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1d25f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1d25f-105">**Applies to:**</span></span>
- <span data-ttu-id="1d25f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d25f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1d25f-107">了解预配和使用 [Microsoft 365 Defender](microsoft-threat-protection.md)的许可和其他要求。</span><span class="sxs-lookup"><span data-stu-id="1d25f-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="1d25f-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="1d25f-108">Licensing requirements</span></span>
<span data-ttu-id="1d25f-109">这些许可证中的任何一个都允许您访问 Microsoft 365 安全中心中的 Microsoft 365 Defender 功能，而无需额外付费：</span><span class="sxs-lookup"><span data-stu-id="1d25f-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="1d25f-110">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="1d25f-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="1d25f-111">Microsoft 365 E5 Security or A5 Security</span><span class="sxs-lookup"><span data-stu-id="1d25f-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="1d25f-112">Windows 10 企业版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="1d25f-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="1d25f-113">企业移动性 + 安全性 (EMS) E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="1d25f-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="1d25f-114">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="1d25f-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="1d25f-115">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d25f-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="1d25f-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1d25f-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="1d25f-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1d25f-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1d25f-118">适用于 Office 的 Defender 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="1d25f-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="1d25f-119">Office 365 试用版许可证目前不提供对 Microsoft 365 Defender 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1d25f-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="1d25f-120">有关详细信息，请 [查看 Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="1d25f-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="1d25f-121">还没有许可证？</span><span class="sxs-lookup"><span data-stu-id="1d25f-121">Don't have license yet?</span></span> [<span data-ttu-id="1d25f-122">试用或购买 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="1d25f-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="1d25f-123">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="1d25f-123">Check your existing  licenses</span></span>
<span data-ttu-id="1d25f-124">转到 Microsoft 365 管理中心 ([admin.microsoft.com](https://admin.microsoft.com/)) 查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="1d25f-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="1d25f-125">在管理中心，转到“计费” > “许可证”。</span><span class="sxs-lookup"><span data-stu-id="1d25f-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="1d25f-126">您需要在 [AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)为 **帐单管理员** 或 **全局读者** 角色分配，以便能够查看许可证信息。</span><span class="sxs-lookup"><span data-stu-id="1d25f-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="1d25f-127">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="1d25f-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="1d25f-128">所需权限</span><span class="sxs-lookup"><span data-stu-id="1d25f-128">Required permissions</span></span>
<span data-ttu-id="1d25f-129">您必须是 **全局管理员** 或 Azure Active Directory 中的 **安全管理员** 才能打开 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="1d25f-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="1d25f-130">有关使用 Microsoft 365 Defender 所需的角色的列表，以及如何对数据访问进行管控的信息，请阅读 [管理对 Microsoft 365 Defender 的访问权限](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="1d25f-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="1d25f-131">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="1d25f-131">Browser requirements</span></span>
<span data-ttu-id="1d25f-132">使用 microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 web 浏览器访问 Microsoft 365 安全中心的 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="1d25f-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="1d25f-133">对美国 GCC、GCC 高和其他美国政府机构的可用性</span><span class="sxs-lookup"><span data-stu-id="1d25f-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="1d25f-134">目前，Microsoft 365 *Defender 不适用于* ：</span><span class="sxs-lookup"><span data-stu-id="1d25f-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="1d25f-135">美国政府社区云 (GCC) </span><span class="sxs-lookup"><span data-stu-id="1d25f-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="1d25f-136">美国政府社区云高 (GCC 高) </span><span class="sxs-lookup"><span data-stu-id="1d25f-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="1d25f-137">美国国防部</span><span class="sxs-lookup"><span data-stu-id="1d25f-137">US Department of Defense</span></span>
- <span data-ttu-id="1d25f-138">拥有商业许可证的所有美国政府机构</span><span class="sxs-lookup"><span data-stu-id="1d25f-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d25f-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="1d25f-139">Related topics</span></span>
- [<span data-ttu-id="1d25f-140">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="1d25f-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="1d25f-141">启用 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d25f-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="1d25f-142">管理访问权限和权限</span><span class="sxs-lookup"><span data-stu-id="1d25f-142">Manage access and permissions</span></span>](mtp-permissions.md)
