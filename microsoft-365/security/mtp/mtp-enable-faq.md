---
title: 启用 Microsoft 365 Defender 时的常见问题
description: 获取有关许可、权限、初始设置以及与启用 Microsoft 365 Defender 相关的其他产品和服务的最常见提问的答案
keywords: 常见问题解答、FAQ、GCC、入门、启用 MTP、Microsoft 威胁防护、M365、security、data location、必需权限、许可证资格、设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920486"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="db43a-104">启用 Microsoft 365 Defender 时的常见问题</span><span class="sxs-lookup"><span data-stu-id="db43a-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="db43a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="db43a-105">**Applies to:**</span></span>
- <span data-ttu-id="db43a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db43a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="db43a-107">阅读有关启用 [Microsoft 365 Defender](microsoft-threat-protection.md)的最常见问题的答复，包括所需的许可证和权限、部署支持服务和初始设置。</span><span class="sxs-lookup"><span data-stu-id="db43a-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="db43a-108">有关如何启用服务的说明，请 [参阅启用 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="db43a-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="db43a-109">我没有 Microsoft 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="db43a-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="db43a-110">我是否可以继续使用 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="db43a-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="db43a-111">具有以下非 E5 许可证的客户可以使用 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="db43a-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="db43a-112">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="db43a-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="db43a-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="db43a-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="db43a-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="db43a-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="db43a-115">适用于 Office 的 Defender 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="db43a-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="db43a-116">若要获取受支持的许可证的完整列表，请 [阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="db43a-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="db43a-117">我是否需要安装或部署任何内容以开始使用 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="db43a-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="db43a-118">否，Microsoft 365 Defender 将从已部署的 Microsoft 365 安全服务中合并数据。</span><span class="sxs-lookup"><span data-stu-id="db43a-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="db43a-119">一旦将其打开，事件、自动化和搜寻体验将在已部署产品的范围内开始工作。</span><span class="sxs-lookup"><span data-stu-id="db43a-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="db43a-120">如果未正确部署这些产品，Microsoft 365 Defender 将不会显示任何数据，并且无法执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="db43a-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="db43a-121">为了优化你的 Microsoft 365 Defender 体验，我们建议部署 *所有* 支持的 [microsoft 365 安全产品和服务](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="db43a-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="db43a-122">Microsoft 365 Defender 处理和存储我的数据的位置是什么？</span><span class="sxs-lookup"><span data-stu-id="db43a-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="db43a-123">Microsoft 365 Defender 自动为数据中心选择一个用于处理和存储统一数据的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="db43a-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="db43a-124">如果你有 Microsoft Defender for Endpoint，则会选择用于终结点的 Defender 的相同位置。</span><span class="sxs-lookup"><span data-stu-id="db43a-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="db43a-125">Microsoft Defender for Endpoint 在欧洲联合 (EU 通过 Azure Defender 打开时自动设置) 数据中心。</span><span class="sxs-lookup"><span data-stu-id="db43a-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="db43a-126">对于已通过这种方式为 Microsoft Defender for Endpoint 设置的客户，microsoft 365 Defender 将自动在相同的欧盟数据中心中预配。</span><span class="sxs-lookup"><span data-stu-id="db43a-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="db43a-127">在 microsoft 365 Defender ( **设置 > microsoft 365 defender** ) 中设置服务之前和之后，将显示数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="db43a-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="db43a-128">如果您更愿意使用其他数据中心位置，请在 Microsoft 365 安全中心中选择 **"需要帮助？** " 以联系 microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="db43a-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="db43a-129">在哪里可以访问 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="db43a-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="db43a-130">Microsoft 365 Defender 在 Microsoft 365 安全中心中提供。</span><span class="sxs-lookup"><span data-stu-id="db43a-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="db43a-131">若要转到安全中心，请浏览到 URL [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="db43a-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="db43a-132">在 Microsoft 365 安全中心访问 Microsoft 365 Defender 需要什么权限？</span><span class="sxs-lookup"><span data-stu-id="db43a-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="db43a-133">分配了以下 Azure Active Directory (AD) 角色的帐户可以访问 Microsoft 365 Defender 功能和数据：</span><span class="sxs-lookup"><span data-stu-id="db43a-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="db43a-134">全局管理员</span><span class="sxs-lookup"><span data-stu-id="db43a-134">Global administrator</span></span>
- <span data-ttu-id="db43a-135">安全管理员</span><span class="sxs-lookup"><span data-stu-id="db43a-135">Security administrator</span></span>
- <span data-ttu-id="db43a-136">安全操作员</span><span class="sxs-lookup"><span data-stu-id="db43a-136">Security Operator</span></span>
- <span data-ttu-id="db43a-137">全局读取者</span><span class="sxs-lookup"><span data-stu-id="db43a-137">Global Reader</span></span>
- <span data-ttu-id="db43a-138">安全读取者</span><span class="sxs-lookup"><span data-stu-id="db43a-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="db43a-139">Microsoft Defender for Endpoint 中基于角色的访问控制设置会影响对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="db43a-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="db43a-140">有关详细信息，请参阅 [管理对 Microsoft 365 Defender 的访问](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="db43a-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="db43a-141">Microsoft 365 Defender 的默认设置是什么时区？</span><span class="sxs-lookup"><span data-stu-id="db43a-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="db43a-142">默认情况下，Microsoft 365 Defender 在 UTC 时区中显示时间信息。</span><span class="sxs-lookup"><span data-stu-id="db43a-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="db43a-143">您可以将此设置更改为使用本地时区。</span><span class="sxs-lookup"><span data-stu-id="db43a-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="db43a-144">了解有关设置时区的信息</span><span class="sxs-lookup"><span data-stu-id="db43a-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="db43a-145">如何才能了解新的 Microsoft 365 Defender 功能和 UI 更新？</span><span class="sxs-lookup"><span data-stu-id="db43a-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="db43a-146">Microsoft 定期通过各种渠道提供信息，包括：</span><span class="sxs-lookup"><span data-stu-id="db43a-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="db43a-147">Microsoft 365 管理中心中的[邮件中心](../../admin/manage/message-center.md)</span><span class="sxs-lookup"><span data-stu-id="db43a-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="db43a-148">[Microsoft 365 security & 合规性技术社区](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)中的 Blogposts</span><span class="sxs-lookup"><span data-stu-id="db43a-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="db43a-149">通过打开 [预览功能](preview.md)获取最新的公开体验。</span><span class="sxs-lookup"><span data-stu-id="db43a-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="db43a-150">Microsoft 365 Defender 是否适用于美国政府社区云 (GCC) 或 GCC 高版？</span><span class="sxs-lookup"><span data-stu-id="db43a-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="db43a-151">目前不可用。</span><span class="sxs-lookup"><span data-stu-id="db43a-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="db43a-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="db43a-152">Related topics</span></span>

- [<span data-ttu-id="db43a-153">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="db43a-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="db43a-154">[打开 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="db43a-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="db43a-155">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="db43a-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="db43a-156">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="db43a-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="db43a-157">启用预览功能</span><span class="sxs-lookup"><span data-stu-id="db43a-157">Turn on preview features</span></span>](preview.md)
