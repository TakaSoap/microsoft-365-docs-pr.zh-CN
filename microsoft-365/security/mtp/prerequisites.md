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
ms.openlocfilehash: ef26a2ebc25d7f55e7dc22347d85767dab970536
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372050"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="98b16-104">Microsoft 威胁防护先决条件</span><span class="sxs-lookup"><span data-stu-id="98b16-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="98b16-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="98b16-105">**Applies to:**</span></span>
- <span data-ttu-id="98b16-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="98b16-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="98b16-107">了解有关设置和使用 Microsoft 威胁防护的许可、硬件和软件要求以及其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="98b16-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="98b16-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="98b16-108">Licensing requirements</span></span>
<span data-ttu-id="98b16-109">若要使用 Microsoft 威胁防护，您需要以下许可证或许可证组合*之一*：</span><span class="sxs-lookup"><span data-stu-id="98b16-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="98b16-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="98b16-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="98b16-111">Microsoft 365 E5 安全版</span><span class="sxs-lookup"><span data-stu-id="98b16-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="98b16-112">Office 365 E5 和 "企业移动性 + 安全性 E5 （EMS E5）" 和 Windows E5</span><span class="sxs-lookup"><span data-stu-id="98b16-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="98b16-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="98b16-113">Microsoft 365 A5</span></span>
- <span data-ttu-id="98b16-114">Microsoft 365 A5 安全性</span><span class="sxs-lookup"><span data-stu-id="98b16-114">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="98b16-115">Office 365 A5 和 "Enterprise 可移动性 + Security A5 （EMS A5）" 和 Windows A5</span><span class="sxs-lookup"><span data-stu-id="98b16-115">Office 365 A5 and "Enterprise Mobility + Security A5 (EMS A5)" and Windows A5</span></span>

<span data-ttu-id="98b16-116">有关详细信息，请[查看 Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="98b16-116">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="98b16-117">还没有许可证？</span><span class="sxs-lookup"><span data-stu-id="98b16-117">Don't have license yet?</span></span> [<span data-ttu-id="98b16-118">试用或购买 Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="98b16-118">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="98b16-119">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="98b16-119">Check your existing  licenses</span></span>
<span data-ttu-id="98b16-120">转到 Microsoft 365 管理中心（[admin.microsoft.com](https://admin.microsoft.com/)）以查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="98b16-120">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="98b16-121">在管理中心，转到“计费”\*\*\*\* > “许可证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="98b16-121">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="98b16-122">您需要在[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)为**帐单管理员**或**全局读者**角色分配，以便能够查看许可证信息。</span><span class="sxs-lookup"><span data-stu-id="98b16-122">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="98b16-123">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="98b16-123">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="98b16-124">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="98b16-124">Browser requirements</span></span>
<span data-ttu-id="98b16-125">使用 microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 web 浏览器访问 microsoft 365 安全中心中的 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="98b16-125">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="98b16-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="98b16-126">Related topics</span></span>
- [<span data-ttu-id="98b16-127">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="98b16-127">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="98b16-128">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="98b16-128">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
