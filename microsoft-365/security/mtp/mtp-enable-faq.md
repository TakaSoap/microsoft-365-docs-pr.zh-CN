---
title: 启用 Microsoft 威胁防护时的常见问题
description: 获取有关许可、权限、初始设置以及与启用 Microsoft 威胁防护相关的其他产品和服务的最常见询问性问题的答案。
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
ms.openlocfilehash: 9dcfeb5616afc8953e862d6d1a542d694582b157
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "44845057"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="7f510-104">启用 Microsoft 威胁防护时的常见问题</span><span class="sxs-lookup"><span data-stu-id="7f510-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

<span data-ttu-id="7f510-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7f510-105">**Applies to:**</span></span>
- <span data-ttu-id="7f510-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="7f510-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7f510-107">阅读有关启用[Microsoft 威胁防护](microsoft-threat-protection.md)的最常见问题的解答，包括所需的许可证和权限、部署支持服务和初始设置。</span><span class="sxs-lookup"><span data-stu-id="7f510-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="7f510-108">有关如何启用服务的说明，请[参阅启用 Microsoft 威胁防护](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="7f510-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="7f510-109">我没有 Microsoft 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="7f510-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="7f510-110">我仍可以使用 Microsoft 威胁防护吗？</span><span class="sxs-lookup"><span data-stu-id="7f510-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="7f510-111">具有以下非 E5 许可证的客户可以使用 Microsoft 威胁防护：</span><span class="sxs-lookup"><span data-stu-id="7f510-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="7f510-112">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="7f510-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="7f510-113">Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="7f510-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="7f510-114">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="7f510-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="7f510-115">Office 365 高级威胁防护（计划 2）</span><span class="sxs-lookup"><span data-stu-id="7f510-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="7f510-116">若要获取受支持的许可证的完整列表，请[阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="7f510-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="7f510-117">我是否需要安装或部署任何内容以开始使用 Microsoft 威胁防护？</span><span class="sxs-lookup"><span data-stu-id="7f510-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="7f510-118">否，Microsoft 威胁防护功能将来自您已部署的 Microsoft 365 安全服务中的数据进行合并。</span><span class="sxs-lookup"><span data-stu-id="7f510-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="7f510-119">一旦将其打开，事件、自动化和搜寻体验将在已部署产品的范围内开始工作。</span><span class="sxs-lookup"><span data-stu-id="7f510-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="7f510-120">如果这些产品均未正确部署，则 Microsoft 威胁防护不会显示任何数据，也不能执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="7f510-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="7f510-121">为了优化你的 Microsoft 威胁防护体验，我们建议部署*所有*受支持的[microsoft 365 安全产品和服务](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7f510-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="7f510-122">Microsoft 威胁防护过程和存储我的数据在哪里？</span><span class="sxs-lookup"><span data-stu-id="7f510-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="7f510-123">Microsoft 威胁防护会自动为数据中心选择一个用于处理和存储统一数据的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="7f510-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="7f510-124">如果你有 Microsoft Defender ATP，它将选择 Microsoft Defender ATP 使用的相同位置。</span><span class="sxs-lookup"><span data-stu-id="7f510-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="7f510-125">在通过 Azure 安全中心启用欧盟（EU）数据中心时，Microsoft Defender ATP 将自动设置。</span><span class="sxs-lookup"><span data-stu-id="7f510-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="7f510-126">对于已使用此方式预配 Microsoft Defender ATP 的客户，microsoft 威胁防护将自动在同一 EU 数据中心中进行设置。</span><span class="sxs-lookup"><span data-stu-id="7f510-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="7f510-127">在 Microsoft 威胁防护（**设置 > Microsoft 威胁防护**）的 "设置" 页中设置服务之前和之后，将显示数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="7f510-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="7f510-128">如果您更愿意使用其他数据中心位置，请在 Microsoft 365 安全中心中选择 **"需要帮助？** " 以联系 microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="7f510-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="7f510-129">在哪里可以访问 Microsoft 威胁防护？</span><span class="sxs-lookup"><span data-stu-id="7f510-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="7f510-130">Microsoft 365 安全中心提供 microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="7f510-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="7f510-131">若要转到安全中心，请浏览到 URL [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="7f510-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="7f510-132">在 Microsoft 365 安全中心中访问 Microsoft 威胁防护需要什么权限？</span><span class="sxs-lookup"><span data-stu-id="7f510-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="7f510-133">分配了以下 Azure Active Directory (AD) 角色的帐户可以访问 Microsoft 威胁防护功能和数据：</span><span class="sxs-lookup"><span data-stu-id="7f510-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="7f510-134">全局管理员</span><span class="sxs-lookup"><span data-stu-id="7f510-134">Global administrator</span></span>
- <span data-ttu-id="7f510-135">安全管理员</span><span class="sxs-lookup"><span data-stu-id="7f510-135">Security administrator</span></span>
- <span data-ttu-id="7f510-136">安全操作员</span><span class="sxs-lookup"><span data-stu-id="7f510-136">Security Operator</span></span>
- <span data-ttu-id="7f510-137">全局读取者</span><span class="sxs-lookup"><span data-stu-id="7f510-137">Global Reader</span></span>
- <span data-ttu-id="7f510-138">安全读取者</span><span class="sxs-lookup"><span data-stu-id="7f510-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="7f510-139">Microsoft Defender ATP 中基于角色的访问控制设置会影响对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="7f510-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="7f510-140">有关详细信息，请参阅[管理对 Microsoft 威胁防护的访问](mtp-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="7f510-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="7f510-141">Microsoft 威胁防护默认为什么时区？</span><span class="sxs-lookup"><span data-stu-id="7f510-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="7f510-142">默认情况下，Microsoft 威胁防护会在 UTC 时区中显示时间信息。</span><span class="sxs-lookup"><span data-stu-id="7f510-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="7f510-143">您可以将此设置更改为使用本地时区。</span><span class="sxs-lookup"><span data-stu-id="7f510-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="7f510-144">了解有关设置时区的信息</span><span class="sxs-lookup"><span data-stu-id="7f510-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="7f510-145">如何才能了解新的 Microsoft 威胁防护功能和 UI 更新？</span><span class="sxs-lookup"><span data-stu-id="7f510-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="7f510-146">Microsoft 定期通过各种渠道提供信息，包括：</span><span class="sxs-lookup"><span data-stu-id="7f510-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="7f510-147">Microsoft 365 管理中心中的[邮件中心](../../admin/manage/message-center.md)</span><span class="sxs-lookup"><span data-stu-id="7f510-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="7f510-148">[Microsoft 365 security & 合规性技术社区](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)中的 Blogposts</span><span class="sxs-lookup"><span data-stu-id="7f510-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="7f510-149">通过打开[预览功能](preview.md)获取最新的公开体验。</span><span class="sxs-lookup"><span data-stu-id="7f510-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="7f510-150">Microsoft 威胁防护是否可供美国政府社区云（GCC）或 GCC High使用？</span><span class="sxs-lookup"><span data-stu-id="7f510-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="7f510-151">目前不可用。</span><span class="sxs-lookup"><span data-stu-id="7f510-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7f510-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="7f510-152">Related topics</span></span>

- [<span data-ttu-id="7f510-153">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="7f510-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="7f510-154">[启用 Microsoft 威胁防护](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="7f510-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="7f510-155">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="7f510-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="7f510-156">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="7f510-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="7f510-157">打开预览功能</span><span class="sxs-lookup"><span data-stu-id="7f510-157">Turn on preview features</span></span>](preview.md)