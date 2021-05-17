---
title: 活动资源管理器入门
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 活动资源管理器通过查看和筛选用户对你的标记内容执行的操作来完善数据分类功能的功能。
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114004"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="fef14-103">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="fef14-103">Get started with activity explorer</span></span>

<span data-ttu-id="fef14-104">通过[数据分类概述](data-classification-overview.md)[和内容](data-classification-content-explorer.md)资源管理器选项卡，您可以了解已发现和标记的内容以及该内容位于何处。</span><span class="sxs-lookup"><span data-stu-id="fef14-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="fef14-105">活动资源管理器通过允许你监视对已标记内容所执行的操作来完善此功能套件。</span><span class="sxs-lookup"><span data-stu-id="fef14-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="fef14-106">活动资源管理器提供已标记内容上活动的历史视图。</span><span class="sxs-lookup"><span data-stu-id="fef14-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="fef14-107">活动信息收集自活动Microsoft 365统一审核日志，在活动资源管理器 UI 中转换和提供。</span><span class="sxs-lookup"><span data-stu-id="fef14-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![占位符屏幕截图概述活动资源管理器](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="fef14-109">有 30 多种不同筛选器可供使用，其中有：</span><span class="sxs-lookup"><span data-stu-id="fef14-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="fef14-110">日期范围</span><span class="sxs-lookup"><span data-stu-id="fef14-110">date range</span></span>
- <span data-ttu-id="fef14-111">活动类型</span><span class="sxs-lookup"><span data-stu-id="fef14-111">activity type</span></span>
- <span data-ttu-id="fef14-112">位置</span><span class="sxs-lookup"><span data-stu-id="fef14-112">location</span></span>
- <span data-ttu-id="fef14-113">用户</span><span class="sxs-lookup"><span data-stu-id="fef14-113">user</span></span>
- <span data-ttu-id="fef14-114">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="fef14-114">sensitivity label</span></span>
- <span data-ttu-id="fef14-115">保留标签</span><span class="sxs-lookup"><span data-stu-id="fef14-115">retention label</span></span>
- <span data-ttu-id="fef14-116">文件路径</span><span class="sxs-lookup"><span data-stu-id="fef14-116">file path</span></span>
- <span data-ttu-id="fef14-117">DLP 策略</span><span class="sxs-lookup"><span data-stu-id="fef14-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="fef14-118">必备条件</span><span class="sxs-lookup"><span data-stu-id="fef14-118">Prerequisites</span></span>

<span data-ttu-id="fef14-119">访问和使用数据分类的每个帐户，都必须拥有从以下其中一个订阅向其分配的许可证：</span><span class="sxs-lookup"><span data-stu-id="fef14-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="fef14-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="fef14-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="fef14-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="fef14-121">Office 365 (E5)</span></span>
- <span data-ttu-id="fef14-122">高级合规性（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="fef14-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="fef14-123">高级威胁智能（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="fef14-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="fef14-124">Microsoft 365 E5/A5 信息保护和管控</span><span class="sxs-lookup"><span data-stu-id="fef14-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="fef14-125">Microsoft 365 E5/A5 合规</span><span class="sxs-lookup"><span data-stu-id="fef14-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="fef14-126">权限</span><span class="sxs-lookup"><span data-stu-id="fef14-126">Permissions</span></span>

 <span data-ttu-id="fef14-127">若要获取对活动资源管理器选项卡的访问权限，必须为帐户显式分配这些角色组中任何一个的成员身份或明确授予该角色。</span><span class="sxs-lookup"><span data-stu-id="fef14-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="fef14-128">**Microsoft 365 角色组**</span><span class="sxs-lookup"><span data-stu-id="fef14-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="fef14-129">全局管理员</span><span class="sxs-lookup"><span data-stu-id="fef14-129">Global administrator</span></span>
- <span data-ttu-id="fef14-130">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="fef14-130">Compliance administrator</span></span>
- <span data-ttu-id="fef14-131">安全管理员</span><span class="sxs-lookup"><span data-stu-id="fef14-131">Security administrator</span></span>
- <span data-ttu-id="fef14-132">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="fef14-132">Compliance data administrator</span></span>

<span data-ttu-id="fef14-133">**Microsoft 365角色**</span><span class="sxs-lookup"><span data-stu-id="fef14-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="fef14-134">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="fef14-134">Compliance administrator</span></span>
- <span data-ttu-id="fef14-135">安全管理员</span><span class="sxs-lookup"><span data-stu-id="fef14-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="fef14-136">活动类型</span><span class="sxs-lookup"><span data-stu-id="fef14-136">Activity types</span></span>

<span data-ttu-id="fef14-137">活动资源管理器从多个活动源的审核日志中收集活动信息。</span><span class="sxs-lookup"><span data-stu-id="fef14-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="fef14-138">有关哪些标签活动可用于活动资源管理器的更多详细信息，请参阅活动资源管理器中可用的标签 [事件](data-classification-activity-explorer-available-events.md)。</span><span class="sxs-lookup"><span data-stu-id="fef14-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="fef14-139"> Office 本机应用程序、Azure 信息保护外接程序、SharePoint Online 中的敏感度标签活动和保留标签活动Exchange Online (仅) 和 OneDrive。 </span><span class="sxs-lookup"><span data-stu-id="fef14-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="fef14-140">示例如下：</span><span class="sxs-lookup"><span data-stu-id="fef14-140">Some examples are:</span></span>

- <span data-ttu-id="fef14-141">已应用的标签</span><span class="sxs-lookup"><span data-stu-id="fef14-141">label applied</span></span>
- <span data-ttu-id="fef14-142">已更改（已升级、已降级或已删除）的标签</span><span class="sxs-lookup"><span data-stu-id="fef14-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="fef14-143">自动标记模拟</span><span class="sxs-lookup"><span data-stu-id="fef14-143">auto-labeling simulation</span></span>
- <span data-ttu-id="fef14-144">文件读取</span><span class="sxs-lookup"><span data-stu-id="fef14-144">file read</span></span> 

<span data-ttu-id="fef14-145">**Azure 信息保护 (AIP) 扫描程序和 AIP 客户端**</span><span class="sxs-lookup"><span data-stu-id="fef14-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="fef14-146">已应用保护</span><span class="sxs-lookup"><span data-stu-id="fef14-146">protection applied</span></span>
- <span data-ttu-id="fef14-147">保护已更改</span><span class="sxs-lookup"><span data-stu-id="fef14-147">protection changed</span></span>
- <span data-ttu-id="fef14-148">已删除保护</span><span class="sxs-lookup"><span data-stu-id="fef14-148">protection removed</span></span>
- <span data-ttu-id="fef14-149">发现的文件</span><span class="sxs-lookup"><span data-stu-id="fef14-149">files discovered</span></span> 

<span data-ttu-id="fef14-150">活动资源管理器还通过终结点数据丢失防护 (**DLP**) 收集来自 Exchange Online、SharePoint Online、OneDrive、Teams 聊天和频道 (预览) 、本地 SharePoint 文件夹和库以及本地文件共享以及 Windows 10 设备的 **DLP** 策略匹配事件。</span><span class="sxs-lookup"><span data-stu-id="fef14-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="fef14-151">设备中的一Windows 10事件包括文件：</span><span class="sxs-lookup"><span data-stu-id="fef14-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="fef14-152">deletions</span><span class="sxs-lookup"><span data-stu-id="fef14-152">deletions</span></span>
- <span data-ttu-id="fef14-153">creations</span><span class="sxs-lookup"><span data-stu-id="fef14-153">creations</span></span>
- <span data-ttu-id="fef14-154">复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="fef14-154">copied to clipboard</span></span>
- <span data-ttu-id="fef14-155">修改内容</span><span class="sxs-lookup"><span data-stu-id="fef14-155">modified</span></span>
- <span data-ttu-id="fef14-156">阅读</span><span class="sxs-lookup"><span data-stu-id="fef14-156">read</span></span>
- <span data-ttu-id="fef14-157">已打印</span><span class="sxs-lookup"><span data-stu-id="fef14-157">printed</span></span>
- <span data-ttu-id="fef14-158">已重命名</span><span class="sxs-lookup"><span data-stu-id="fef14-158">renamed</span></span>
- <span data-ttu-id="fef14-159">复制到网络共享</span><span class="sxs-lookup"><span data-stu-id="fef14-159">copied to network share</span></span>
- <span data-ttu-id="fef14-160">由不允许的应用访问</span><span class="sxs-lookup"><span data-stu-id="fef14-160">accessed by unallowed app</span></span> 

<span data-ttu-id="fef14-161">了解对敏感标记内容采取的操作的价值是，你可以看到已放置的控件（如数据丢失防护）是否有效。 [](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="fef14-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="fef14-162">如果无效，或者发现某项意外内容（如大量项目被标记为`highly confidential`并降级为`general`），则可管理各种策略并采取新操作来限制意外行为。</span><span class="sxs-lookup"><span data-stu-id="fef14-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="fef14-163">活动资源管理器当前不监视 Exchange Online 的保留活动。</span><span class="sxs-lookup"><span data-stu-id="fef14-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="fef14-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fef14-164">See also</span></span>

- [<span data-ttu-id="fef14-165">了解敏感度标签</span><span class="sxs-lookup"><span data-stu-id="fef14-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="fef14-166">了解保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="fef14-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="fef14-167">了解敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="fef14-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="fef14-168">了解数据分类。</span><span class="sxs-lookup"><span data-stu-id="fef14-168">Learn about data classification</span></span>](data-classification-overview.md)
