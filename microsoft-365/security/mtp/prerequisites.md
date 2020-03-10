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
ms.openlocfilehash: 3e18759387525ec600c24f74c96d6cddf206fc82
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42569037"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="a8e3e-104">Microsoft 威胁防护先决条件</span><span class="sxs-lookup"><span data-stu-id="a8e3e-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="a8e3e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a8e3e-105">**Applies to:**</span></span>
- <span data-ttu-id="a8e3e-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="a8e3e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a8e3e-107">了解有关设置和使用 Microsoft 威胁防护的许可、硬件和软件要求以及其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="a8e3e-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="a8e3e-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="a8e3e-108">Licensing requirements</span></span>
<span data-ttu-id="a8e3e-109">若要使用 Microsoft 威胁防护，您需要以下许可证或许可证组合*之一*：</span><span class="sxs-lookup"><span data-stu-id="a8e3e-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="a8e3e-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a8e3e-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="a8e3e-111">Microsoft 365 E5 安全版</span><span class="sxs-lookup"><span data-stu-id="a8e3e-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="a8e3e-112">Office 365 E5 和 "企业移动性 + 安全性 E5 （EMS E5）" 和 Windows E5</span><span class="sxs-lookup"><span data-stu-id="a8e3e-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="a8e3e-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="a8e3e-113">Microsoft 365 A5</span></span>

<span data-ttu-id="a8e3e-114">有关详细信息，请[查看 Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="a8e3e-114">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="a8e3e-115">还没有许可证？</span><span class="sxs-lookup"><span data-stu-id="a8e3e-115">Don't have license yet?</span></span> [<span data-ttu-id="a8e3e-116">试用或购买 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="a8e3e-116">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="a8e3e-117">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="a8e3e-117">Check your existing  licenses</span></span>
<span data-ttu-id="a8e3e-118">转到 Microsoft 365 管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="a8e3e-118">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="a8e3e-119">在管理中心，转到“计费”\*\*\*\* > “许可证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a8e3e-119">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="a8e3e-120">您需要在[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)为**帐单管理员**或**全局读者**角色分配，以便能够查看许可证信息。</span><span class="sxs-lookup"><span data-stu-id="a8e3e-120">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="a8e3e-121">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="a8e3e-121">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="a8e3e-122">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="a8e3e-122">Browser requirements</span></span>
<span data-ttu-id="a8e3e-123">使用 microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 web 浏览器访问 microsoft 365 安全中心中的 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="a8e3e-123">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a8e3e-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="a8e3e-124">Related topics</span></span>
- [<span data-ttu-id="a8e3e-125">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="a8e3e-125">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="a8e3e-126">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="a8e3e-126">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
