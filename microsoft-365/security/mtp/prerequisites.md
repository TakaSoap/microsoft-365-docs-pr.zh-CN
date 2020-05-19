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
ms.openlocfilehash: 71e7b532e046015dd64e51fd422d276433d65b3a
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280530"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="c3df2-104">Microsoft 威胁防护先决条件</span><span class="sxs-lookup"><span data-stu-id="c3df2-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="c3df2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c3df2-105">**Applies to:**</span></span>
- <span data-ttu-id="c3df2-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="c3df2-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c3df2-107">了解有关设置和使用 Microsoft 威胁防护的许可、硬件和软件要求以及其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="c3df2-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="c3df2-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="c3df2-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="c3df2-109">从2020年5月12日开始，Microsoft 将逐步推出有关许可要求的新的优化体验，并[启用 Microsoft 威胁防护](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="c3df2-109">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="c3df2-110">在此期间的几周内，一些客户将开始查看对其门户体验所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c3df2-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="c3df2-111">有关新体验的信息已在本文中标记为 "**新体验**"。</span><span class="sxs-lookup"><span data-stu-id="c3df2-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="c3df2-112">若要使用 Microsoft 威胁防护，您需要一个许可证或许可证组合。</span><span class="sxs-lookup"><span data-stu-id="c3df2-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="c3df2-113">这些许可证或许可证组合使您可以访问 Microsoft 威胁防护功能，而无需额外付费。</span><span class="sxs-lookup"><span data-stu-id="c3df2-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="c3df2-114">单一许可证</span><span class="sxs-lookup"><span data-stu-id="c3df2-114">Single license</span></span>
<span data-ttu-id="c3df2-115">您可以使用以下许可证*之一*：</span><span class="sxs-lookup"><span data-stu-id="c3df2-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="c3df2-116">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="c3df2-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="c3df2-117">Microsoft 365 E5 Security or A5 Security</span><span class="sxs-lookup"><span data-stu-id="c3df2-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="c3df2-118">许可证组合</span><span class="sxs-lookup"><span data-stu-id="c3df2-118">Combination of licenses</span></span>
<span data-ttu-id="c3df2-119">您还可以将用于 E5 或 A5 订阅的许可证组合用于 Office 365、*企业移动性 + 安全性（EMS）* 和 Windows。</span><span class="sxs-lookup"><span data-stu-id="c3df2-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="c3df2-120">许可证组合必须包含以下*所有*许可证：</span><span class="sxs-lookup"><span data-stu-id="c3df2-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="c3df2-121">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="c3df2-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="c3df2-122">*企业移动性 + 安全性（EMS）* E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="c3df2-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="c3df2-123">Windows 10 企业版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="c3df2-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="c3df2-124">有关详细信息，请[查看 Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="c3df2-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="c3df2-125">还没有许可证？</span><span class="sxs-lookup"><span data-stu-id="c3df2-125">Don't have license yet?</span></span> [<span data-ttu-id="c3df2-126">试用或购买 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="c3df2-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="c3df2-127">**全新体验：** 从2020年5月12日开始，客户将逐渐收到此体验的更改。</span><span class="sxs-lookup"><span data-stu-id="c3df2-127">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="c3df2-128">对于具有全新体验的用户，启用 Microsoft 威胁防护的选项将适用于具有以下任意许可证的*所有*客户：</span><span class="sxs-lookup"><span data-stu-id="c3df2-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="c3df2-129">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="c3df2-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="c3df2-130">Microsoft 365 E5 Security or A5 Security</span><span class="sxs-lookup"><span data-stu-id="c3df2-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="c3df2-131">Windows 10 企业版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="c3df2-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="c3df2-132">企业移动性 + 安全性（EMS） E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="c3df2-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="c3df2-133">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="c3df2-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="c3df2-134">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="c3df2-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="c3df2-135">Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="c3df2-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="c3df2-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c3df2-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="c3df2-137">Office 365 高级威胁防护（计划 2）</span><span class="sxs-lookup"><span data-stu-id="c3df2-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="c3df2-138">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="c3df2-138">Check your existing  licenses</span></span>
<span data-ttu-id="c3df2-139">转到 Microsoft 365 管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="c3df2-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="c3df2-140">在管理中心，转到“计费”\*\*\*\* > “许可证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3df2-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="c3df2-141">您需要在[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)为**帐单管理员**或**全局读者**角色分配，以便能够查看许可证信息。</span><span class="sxs-lookup"><span data-stu-id="c3df2-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="c3df2-142">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="c3df2-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="c3df2-143">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="c3df2-143">Browser requirements</span></span>
<span data-ttu-id="c3df2-144">使用 microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 web 浏览器访问 microsoft 365 安全中心中的 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="c3df2-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="c3df2-145">对美国 GCC、GCC 高和其他美国政府机构的可用性</span><span class="sxs-lookup"><span data-stu-id="c3df2-145">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="c3df2-146">目前，Microsoft 威胁*防护不适用于*：</span><span class="sxs-lookup"><span data-stu-id="c3df2-146">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="c3df2-147">美国政府社区云（GCC）</span><span class="sxs-lookup"><span data-stu-id="c3df2-147">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="c3df2-148">美国政府社区云高（GCC 高）</span><span class="sxs-lookup"><span data-stu-id="c3df2-148">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="c3df2-149">美国国防部</span><span class="sxs-lookup"><span data-stu-id="c3df2-149">US Department of Defense</span></span>
- <span data-ttu-id="c3df2-150">拥有商业许可证的所有美国政府机构</span><span class="sxs-lookup"><span data-stu-id="c3df2-150">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3df2-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="c3df2-151">Related topics</span></span>
- [<span data-ttu-id="c3df2-152">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="c3df2-152">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="c3df2-153">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="c3df2-153">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
