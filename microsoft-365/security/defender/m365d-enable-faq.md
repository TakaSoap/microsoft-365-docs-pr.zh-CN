---
title: 打开 Defender 时Microsoft 365常见问题
description: 获取有关授权、权限、初始设置以及其他与启用 Defender 相关的产品和服务的最常见Microsoft 365解答
keywords: 常见问题， 常见问题， GCC， 入门， 启用 Microsoft 365 Defender， Microsoft 365 Defender， M365， 安全， 数据位置， 所需权限， 许可证资格， 设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933429"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="9dc2e-104">打开 Defender 时Microsoft 365常见问题</span><span class="sxs-lookup"><span data-stu-id="9dc2e-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9dc2e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9dc2e-105">**Applies to:**</span></span>
- <span data-ttu-id="9dc2e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9dc2e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9dc2e-107">阅读对有关启用[Microsoft 365 Defender](microsoft-365-defender.md)的最常见问题的回复，包括所需的许可证和权限、部署支持服务和初始设置。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="9dc2e-108">有关如何打开该服务的说明，请阅读打开 Microsoft 365 [Defender。](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="9dc2e-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="9dc2e-109">我并没有许可证Microsoft 365 E5许可证。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="9dc2e-110">我是否仍可以使用 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="9dc2e-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="9dc2e-111">具有以下非 E5 许可证的客户可以使用 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="9dc2e-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="9dc2e-112">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9dc2e-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="9dc2e-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="9dc2e-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="9dc2e-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9dc2e-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="9dc2e-115">Defender for Office 365 (计划 2)</span><span class="sxs-lookup"><span data-stu-id="9dc2e-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="9dc2e-116">有关受支持的许可证的完整列表， [请阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="9dc2e-117">是否需要安装或部署任何内容以开始使用 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="9dc2e-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="9dc2e-118">否，Microsoft 365 Defender 会合并Microsoft 365部署的安全服务的数据。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="9dc2e-119">启用后，事件、自动化和搜寻体验将开始在已部署产品范围内工作。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="9dc2e-120">如果未正确部署这些产品，Microsoft 365 Defender 将不会显示任何数据，并且无法执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="9dc2e-121">若要优化你的 Microsoft 365 Defender 体验，*我们建议部署所有* 受支持的Microsoft 365 [安全产品和服务](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="9dc2e-122">Defender Microsoft 365处理和存储我的数据的位置？</span><span class="sxs-lookup"><span data-stu-id="9dc2e-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="9dc2e-123">Microsoft 365Defender 会自动为处理和存储合并数据的数据中心选择一个最佳位置。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="9dc2e-124">如果你有适用于终结点的 Microsoft Defender，它将选择 Defender for Endpoint 所使用的相同位置。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="9dc2e-125">Microsoft Defender for Endpoint 在通过 Azure Defender (欧盟) 数据中心自动设置。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="9dc2e-126">Microsoft 365Defender 将在同一欧盟数据中心中自动为已预配 Microsoft Defender for Endpoint 的客户进行预配。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="9dc2e-127">数据中心位置显示在 Defender (Defender Microsoft 365 设置页面之前和之后设置 > Microsoft 365 **服务**) 。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="9dc2e-128">如果你希望使用另一个数据中心位置，请选择安全中心Microsoft 365需要帮助？"，联系 Microsoft 支持人员。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="9dc2e-129">在哪里可以访问 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="9dc2e-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="9dc2e-130">Microsoft 365Defender 在安全Microsoft 365可用。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="9dc2e-131">若要转到安全中心，请浏览到 URL [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="9dc2e-132">我需要哪些权限才能访问安全Microsoft 365 Defender Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="9dc2e-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="9dc2e-133">分配了以下 AD Azure Active Directory (AD) 的帐户可以访问Microsoft 365 Defender 功能和数据：</span><span class="sxs-lookup"><span data-stu-id="9dc2e-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="9dc2e-134">全局管理员</span><span class="sxs-lookup"><span data-stu-id="9dc2e-134">Global administrator</span></span>
- <span data-ttu-id="9dc2e-135">安全管理员</span><span class="sxs-lookup"><span data-stu-id="9dc2e-135">Security administrator</span></span>
- <span data-ttu-id="9dc2e-136">安全操作员</span><span class="sxs-lookup"><span data-stu-id="9dc2e-136">Security Operator</span></span>
- <span data-ttu-id="9dc2e-137">全局读取者</span><span class="sxs-lookup"><span data-stu-id="9dc2e-137">Global Reader</span></span>
- <span data-ttu-id="9dc2e-138">安全读取者</span><span class="sxs-lookup"><span data-stu-id="9dc2e-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="9dc2e-139">Microsoft Defender for Endpoint 中基于角色的访问控制设置会影响对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="9dc2e-140">有关详细信息，请阅读有关管理对[Microsoft 365 Defender 的访问权限](m365d-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="9dc2e-141">Defender 默认Microsoft 365什么时区？</span><span class="sxs-lookup"><span data-stu-id="9dc2e-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="9dc2e-142">默认情况下，Microsoft 365 Defender 以 UTC 时区显示时间信息。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="9dc2e-143">你可以更改此设置以使用本地时区。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="9dc2e-144">了解如何设置时区</span><span class="sxs-lookup"><span data-stu-id="9dc2e-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="9dc2e-145">如何了解有关 Defender Microsoft 365 UI 更新的信息？</span><span class="sxs-lookup"><span data-stu-id="9dc2e-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="9dc2e-146">Microsoft 会定期通过各种渠道提供相关信息，包括：</span><span class="sxs-lookup"><span data-stu-id="9dc2e-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="9dc2e-147">管理[中心](../../admin/manage/message-center.md)Microsoft 365中心</span><span class="sxs-lookup"><span data-stu-id="9dc2e-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="9dc2e-148">安全与Microsoft 365[技术&博客文章](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="9dc2e-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="9dc2e-149">打开预览功能，获取最新公开 [可用体验](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="9dc2e-150">Microsoft 365 Defender 是否适用于美国政府社区云 (GCC) 或GCC高？</span><span class="sxs-lookup"><span data-stu-id="9dc2e-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="9dc2e-151">目前不可用。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9dc2e-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="9dc2e-152">Related topics</span></span>

- [<span data-ttu-id="9dc2e-153">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="9dc2e-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="9dc2e-154">[打开 Microsoft 365 Defender](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="9dc2e-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="9dc2e-155">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="9dc2e-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="9dc2e-156">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="9dc2e-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="9dc2e-157">启用预览功能</span><span class="sxs-lookup"><span data-stu-id="9dc2e-157">Turn on preview features</span></span>](preview.md)
