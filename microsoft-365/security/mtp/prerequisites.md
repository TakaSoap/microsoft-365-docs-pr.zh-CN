---
title: Microsoft 威胁防护先决条件
description: 了解有关 Microsoft 威胁防护的许可、硬件和软件要求以及其他配置设置
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
ms.openlocfilehash: f63c59403e84e79d1a4a5cf2b8a5544f5646781c
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773847"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="619e8-104">Microsoft 威胁防护先决条件</span><span class="sxs-lookup"><span data-stu-id="619e8-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="619e8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="619e8-105">**Applies to:**</span></span>
- <span data-ttu-id="619e8-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="619e8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="619e8-107">了解设置和使用[Microsoft 威胁防护](microsoft-threat-protection.md)的许可和其他要求。</span><span class="sxs-lookup"><span data-stu-id="619e8-107">Learn about licensing and other requirements for provisioning and using [Microsoft Threat Protection](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="619e8-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="619e8-108">Licensing requirements</span></span>
<span data-ttu-id="619e8-109">这些许可证中的任何一个都允许您访问 Microsoft 365 安全中心中的 Microsoft 威胁防护功能，而无需额外费用：</span><span class="sxs-lookup"><span data-stu-id="619e8-109">Any of these licenses gives you access to Microsoft Threat Protection features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="619e8-110">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="619e8-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="619e8-111">Microsoft 365 E5 Security or A5 Security</span><span class="sxs-lookup"><span data-stu-id="619e8-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="619e8-112">Windows 10 企业版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="619e8-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="619e8-113">企业移动性 + 安全性（EMS） E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="619e8-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="619e8-114">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="619e8-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="619e8-115">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="619e8-115">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="619e8-116">Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="619e8-116">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="619e8-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="619e8-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="619e8-118">Office 365 高级威胁防护（计划 2）</span><span class="sxs-lookup"><span data-stu-id="619e8-118">Office 365 Advanced Threat Protection (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="619e8-119">Office 365 试用版许可证目前不提供对 Microsoft 威胁防护的访问权限。</span><span class="sxs-lookup"><span data-stu-id="619e8-119">Trial licenses for Office 365 currently do not provide access to Microsoft Threat Protection.</span></span>

<span data-ttu-id="619e8-120">有关详细信息，请[查看 Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="619e8-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="619e8-121">还没有许可证？</span><span class="sxs-lookup"><span data-stu-id="619e8-121">Don't have license yet?</span></span> [<span data-ttu-id="619e8-122">试用或购买 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="619e8-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="619e8-123">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="619e8-123">Check your existing  licenses</span></span>
<span data-ttu-id="619e8-124">转到 Microsoft 365 管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="619e8-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="619e8-125">在管理中心，转到“计费”\*\*\*\* > “许可证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="619e8-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="619e8-126">您需要在[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)为**帐单管理员**或**全局读者**角色分配，以便能够查看许可证信息。</span><span class="sxs-lookup"><span data-stu-id="619e8-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="619e8-127">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="619e8-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="619e8-128">所需权限</span><span class="sxs-lookup"><span data-stu-id="619e8-128">Required permissions</span></span>
<span data-ttu-id="619e8-129">有关所需角色的列表以及如何对数据的访问进行管控，请阅读有关[管理 Microsoft 威胁防护的访问权限](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="619e8-129">For the list of required roles and how access to data is regulated, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="619e8-130">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="619e8-130">Browser requirements</span></span>
<span data-ttu-id="619e8-131">使用 microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 web 浏览器访问 microsoft 365 安全中心中的 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="619e8-131">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="619e8-132">对美国 GCC、GCC 高和其他美国政府机构的可用性</span><span class="sxs-lookup"><span data-stu-id="619e8-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="619e8-133">目前，Microsoft 威胁*防护不适用于*：</span><span class="sxs-lookup"><span data-stu-id="619e8-133">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="619e8-134">美国政府社区云（GCC）</span><span class="sxs-lookup"><span data-stu-id="619e8-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="619e8-135">美国政府社区云高（GCC 高）</span><span class="sxs-lookup"><span data-stu-id="619e8-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="619e8-136">美国国防部</span><span class="sxs-lookup"><span data-stu-id="619e8-136">US Department of Defense</span></span>
- <span data-ttu-id="619e8-137">拥有商业许可证的所有美国政府机构</span><span class="sxs-lookup"><span data-stu-id="619e8-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="619e8-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="619e8-138">Related topics</span></span>
- [<span data-ttu-id="619e8-139">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="619e8-139">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="619e8-140">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="619e8-140">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="619e8-141">管理访问权限和权限</span><span class="sxs-lookup"><span data-stu-id="619e8-141">Manage access and permissions</span></span>](mtp-permissions.md)
