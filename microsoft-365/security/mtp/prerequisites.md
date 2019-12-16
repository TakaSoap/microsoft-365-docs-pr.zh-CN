---
title: Microsoft 威胁防护先决条件
description: 了解有关 Microsoft 威胁防护的许可、硬件和软件要求以及其他配置设置
keywords: 要求, 先决条件, 硬件, 软件, 浏览器
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: b136dfcb11265e9ab19328d6ad0b3c515f7fc86f
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910846"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="6e095-104">Microsoft 威胁防护先决条件</span><span class="sxs-lookup"><span data-stu-id="6e095-104">Microsoft Threat Protection</span></span>

<span data-ttu-id="6e095-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6e095-105">**Applies to:**</span></span>
- <span data-ttu-id="6e095-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6e095-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="6e095-107">了解有关运行和使用 Microsoft 365 安全的许可、硬件和软件要求以及其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="6e095-107">Learn about the licensing, hardware and software requirements, and other configuration settings to run and use the Microsoft 365 security.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="6e095-108">许可要求</span><span class="sxs-lookup"><span data-stu-id="6e095-108">Licensing requirements</span></span>
<span data-ttu-id="6e095-109">Microsoft 365 安全需要以下许可证之一：</span><span class="sxs-lookup"><span data-stu-id="6e095-109">Microsoft 365 security requires one of the following licenses:</span></span>

- <span data-ttu-id="6e095-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6e095-110">Microsoft 365 E5</span></span> 
- <span data-ttu-id="6e095-111">Office 365 E5、企业移动性 + 安全性 E5 和 Windows E5</span><span class="sxs-lookup"><span data-stu-id="6e095-111">Office 365 E5, Enterprise Mobility + Security E5, and Windows E5</span></span>

<span data-ttu-id="6e095-112">可从 [Microsoft 365 企业版页面](https://www.microsoft.com/en-us/microsoft-365/enterprise)获取这些许可证。</span><span class="sxs-lookup"><span data-stu-id="6e095-112">You can acquire these licenses from the [Microsoft 365 enterprise page](https://www.microsoft.com/en-us/microsoft-365/enterprise).</span></span>

### <a name="check-your-existing--licenses"></a><span data-ttu-id="6e095-113">检查现有许可证</span><span class="sxs-lookup"><span data-stu-id="6e095-113">Check your existing  licenses</span></span>
<span data-ttu-id="6e095-114">转到位于 [admin.microsoft.com](https://admin.microsoft.com/) 的 Microsoft 365 管理中心查看现有许可证。</span><span class="sxs-lookup"><span data-stu-id="6e095-114">Go to Microsoft 365 admin center at [admin.microsoft.com](https://admin.microsoft.com/) to view your existing licenses.</span></span> <span data-ttu-id="6e095-115">在管理中心，转到“计费”\*\*\*\* > “许可证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6e095-115">In the admin center, go to **Billing** > **Licenses**.</span></span>

<span data-ttu-id="6e095-116">需要分配 [Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 中的**计费管理员**或**全局读取者**角色，才能查看许可信息。</span><span class="sxs-lookup"><span data-stu-id="6e095-116">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see licensing information.</span></span> <span data-ttu-id="6e095-117">如果遇到访问问题，请联系全局管理员。</span><span class="sxs-lookup"><span data-stu-id="6e095-117">If you encounter access problems, contact a global admin.</span></span>  

## <a name="browser-requirements"></a><span data-ttu-id="6e095-118">浏览器要求</span><span class="sxs-lookup"><span data-stu-id="6e095-118">Browser requirements</span></span>
<span data-ttu-id="6e095-119">可通过浏览器来访问 Microsoft 365 安全中心。</span><span class="sxs-lookup"><span data-stu-id="6e095-119">Access to Microsoft 365 security center is done through a browser.</span></span> <span data-ttu-id="6e095-120">支持 Internet Explorer 和 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="6e095-120">Internet Explorer and Microsoft Edge is supported.</span></span> <span data-ttu-id="6e095-121">还支持任何符合 HTML5 的浏览器。</span><span class="sxs-lookup"><span data-stu-id="6e095-121">Any HTML5 compliant browsers are also supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6e095-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="6e095-122">Related topics</span></span>
- [<span data-ttu-id="6e095-123">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="6e095-123">Microsoft Advanced Threat Protection</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="6e095-124">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6e095-124">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)