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
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857175"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="bc83c-104">Microsoft 威胁防护先决条件</span><span class="sxs-lookup"><span data-stu-id="bc83c-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="bc83c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bc83c-105">**Applies to:**</span></span>
- <span data-ttu-id="bc83c-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="bc83c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="bc83c-107">了解有关设置和使用 Microsoft 威胁防护的许可、硬件和软件要求以及其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="bc83c-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="bc83c-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="bc83c-108">Licensing requirements</span></span>
<span data-ttu-id="bc83c-109">若要使用 Microsoft 威胁防护，您需要一个许可证或许可证组合。</span><span class="sxs-lookup"><span data-stu-id="bc83c-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span>

### <a name="single-license"></a><span data-ttu-id="bc83c-110">单一许可证</span><span class="sxs-lookup"><span data-stu-id="bc83c-110">Single license</span></span>
<span data-ttu-id="bc83c-111">您可以使用以下许可证*之一*：</span><span class="sxs-lookup"><span data-stu-id="bc83c-111">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="bc83c-112">Microsoft 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="bc83c-112">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="bc83c-113">Microsoft 365 E5 Security or A5 Security</span><span class="sxs-lookup"><span data-stu-id="bc83c-113">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="bc83c-114">许可证组合</span><span class="sxs-lookup"><span data-stu-id="bc83c-114">Combination of licenses</span></span>
<span data-ttu-id="bc83c-115">您还可以将用于 E5 或 A5 订阅的许可证组合用于 Office 365、*企业移动性 + 安全性（EMS）* 和 Windows。</span><span class="sxs-lookup"><span data-stu-id="bc83c-115">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="bc83c-116">许可证组合必须包含以下*所有*许可证：</span><span class="sxs-lookup"><span data-stu-id="bc83c-116">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="bc83c-117">Office 365 E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="bc83c-117">Office 365 E5 or A5</span></span>
- <span data-ttu-id="bc83c-118">*企业移动性 + 安全性（EMS）* E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="bc83c-118">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="bc83c-119">Windows E5 或 A5</span><span class="sxs-lookup"><span data-stu-id="bc83c-119">Windows E5 or A5</span></span>

<span data-ttu-id="bc83c-120">有关详细信息，请[查看 Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="bc83c-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="bc83c-121">还没有许可证？</span><span class="sxs-lookup"><span data-stu-id="bc83c-121">Don't have license yet?</span></span> [<span data-ttu-id="bc83c-122">试用或购买 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="bc83c-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="bc83c-123">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="bc83c-123">Check your existing  licenses</span></span>
<span data-ttu-id="bc83c-124">转到 Microsoft 365 管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="bc83c-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="bc83c-125">在管理中心，转到“计费”\*\*\*\* > “许可证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bc83c-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="bc83c-126">您需要在[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)为**帐单管理员**或**全局读者**角色分配，以便能够查看许可证信息。</span><span class="sxs-lookup"><span data-stu-id="bc83c-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="bc83c-127">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="bc83c-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="bc83c-128">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="bc83c-128">Browser requirements</span></span>
<span data-ttu-id="bc83c-129">使用 microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 web 浏览器访问 microsoft 365 安全中心中的 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="bc83c-129">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="bc83c-130">Microsoft 美国政府社区云和美国政府社区云高（GCC 高）客户的 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="bc83c-130">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="bc83c-131">目前，Microsoft 威胁防护不适用于美国 GCC 和 GCC 高级客户。</span><span class="sxs-lookup"><span data-stu-id="bc83c-131">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="bc83c-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="bc83c-132">Related topics</span></span>
- [<span data-ttu-id="bc83c-133">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="bc83c-133">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="bc83c-134">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="bc83c-134">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
