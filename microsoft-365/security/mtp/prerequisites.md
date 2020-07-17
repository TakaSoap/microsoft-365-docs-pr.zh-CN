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
ms.openlocfilehash: c64adf870d3669b983e11093196f59c82b1f59e0
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844902"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="f9434-104">Microsoft 威胁防护先决条件</span><span class="sxs-lookup"><span data-stu-id="f9434-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="f9434-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f9434-105">**Applies to:**</span></span>
- <span data-ttu-id="f9434-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f9434-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f9434-107">了解设置和使用[Microsoft 威胁防护](microsoft-threat-protection.md)的许可和其他要求。</span><span class="sxs-lookup"><span data-stu-id="f9434-107">Learn about licensing and other requirements for provisioning and using [Microsoft Threat Protection](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="f9434-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="f9434-108">Licensing requirements</span></span>
<span data-ttu-id="f9434-109">这些许可证中的任何一个都允许您访问 Microsoft 365 安全中心中的 Microsoft 威胁防护功能，而无需额外费用：</span><span class="sxs-lookup"><span data-stu-id="f9434-109">Any of these licenses gives you access to Microsoft Threat Protection features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="f9434-110">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="f9434-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="f9434-111">Microsoft 365 E5 Security or A5 Security</span><span class="sxs-lookup"><span data-stu-id="f9434-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="f9434-112">Windows 10 企业版 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="f9434-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="f9434-113">企业移动性 + 安全性（EMS） E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="f9434-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="f9434-114">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="f9434-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="f9434-115">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="f9434-115">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="f9434-116">Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="f9434-116">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="f9434-117">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="f9434-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f9434-118">Office 365 高级威胁防护（计划 2）</span><span class="sxs-lookup"><span data-stu-id="f9434-118">Office 365 Advanced Threat Protection (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="f9434-119">Office 365 试用版许可证目前不提供对 Microsoft 威胁防护的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f9434-119">Trial licenses for Office 365 currently do not provide access to Microsoft Threat Protection.</span></span>

<span data-ttu-id="f9434-120">有关详细信息，请[查看 Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="f9434-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="f9434-121">还没有许可证？</span><span class="sxs-lookup"><span data-stu-id="f9434-121">Don't have license yet?</span></span> [<span data-ttu-id="f9434-122">试用或购买 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="f9434-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="f9434-123">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="f9434-123">Check your existing  licenses</span></span>
<span data-ttu-id="f9434-124">转到 Microsoft 365 管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="f9434-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="f9434-125">在管理中心，转到“计费”\*\*\*\* > “许可证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9434-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="f9434-126">您需要在[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)为**帐单管理员**或**全局读者**角色分配，以便能够查看许可证信息。</span><span class="sxs-lookup"><span data-stu-id="f9434-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="f9434-127">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="f9434-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="f9434-128">所需权限</span><span class="sxs-lookup"><span data-stu-id="f9434-128">Required permissions</span></span>
<span data-ttu-id="f9434-129">您必须是**全局管理员**或 Azure Active Directory 中的**安全管理员**才能打开 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="f9434-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> <span data-ttu-id="f9434-130">有关使用 Microsoft 威胁防护所需角色的列表，以及如何对数据访问进行管控的信息，请阅读[管理 Microsoft 威胁防护的访问权限](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f9434-130">For the list of roles required to use Microsoft Threat Protection and information on how access to data is regulated, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="f9434-131">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="f9434-131">Browser requirements</span></span>
<span data-ttu-id="f9434-132">使用 microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 web 浏览器访问 microsoft 365 安全中心中的 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="f9434-132">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="f9434-133">对美国 GCC、GCC 高和其他美国政府机构的可用性</span><span class="sxs-lookup"><span data-stu-id="f9434-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="f9434-134">目前，Microsoft 威胁*防护不适用于*：</span><span class="sxs-lookup"><span data-stu-id="f9434-134">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="f9434-135">美国政府社区云（GCC）</span><span class="sxs-lookup"><span data-stu-id="f9434-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="f9434-136">美国政府社区云高（GCC 高）</span><span class="sxs-lookup"><span data-stu-id="f9434-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="f9434-137">美国国防部</span><span class="sxs-lookup"><span data-stu-id="f9434-137">US Department of Defense</span></span>
- <span data-ttu-id="f9434-138">拥有商业许可证的所有美国政府机构</span><span class="sxs-lookup"><span data-stu-id="f9434-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9434-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="f9434-139">Related topics</span></span>
- [<span data-ttu-id="f9434-140">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="f9434-140">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="f9434-141">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f9434-141">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="f9434-142">管理访问权限和权限</span><span class="sxs-lookup"><span data-stu-id="f9434-142">Manage access and permissions</span></span>](mtp-permissions.md)
