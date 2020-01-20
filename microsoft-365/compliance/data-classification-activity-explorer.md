---
title: 使用数据分类活动资源管理器
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 活动资源管理器通过查看和筛选用户对你的标记内容执行的操作来完善数据分类功能的功能。
ms.openlocfilehash: ab80de0e1be3a164da8414ef3791fb9717bcc190
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233693"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="a3668-103">查看关于标记的内容的活动（预览版）</span><span class="sxs-lookup"><span data-stu-id="a3668-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="a3668-104">数据分类概述和内容浏览器选项卡使你可以查看已发现和已标记的内容以及该内容的位置。</span><span class="sxs-lookup"><span data-stu-id="a3668-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="a3668-105">活动资源管理器通过允许你监视对已标记内容所执行的操作来完善此功能套件。</span><span class="sxs-lookup"><span data-stu-id="a3668-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="a3668-106">活动资源管理器提供历史视图。</span><span class="sxs-lookup"><span data-stu-id="a3668-106">Activity explorer provides a historical view.</span></span>

![占位符屏幕截图概述活动资源管理器](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="a3668-108">可通过以下方式筛选数据：</span><span class="sxs-lookup"><span data-stu-id="a3668-108">You can filter the data by:</span></span>

- <span data-ttu-id="a3668-109">日期范围</span><span class="sxs-lookup"><span data-stu-id="a3668-109">date range</span></span>
- <span data-ttu-id="a3668-110">活动类型</span><span class="sxs-lookup"><span data-stu-id="a3668-110">activity type</span></span>
- <span data-ttu-id="a3668-111">位置</span><span class="sxs-lookup"><span data-stu-id="a3668-111">location</span></span>
- <span data-ttu-id="a3668-112">用户</span><span class="sxs-lookup"><span data-stu-id="a3668-112">user</span></span>
- <span data-ttu-id="a3668-113">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="a3668-113">sensitivity label</span></span>
- <span data-ttu-id="a3668-114">保留标签</span><span class="sxs-lookup"><span data-stu-id="a3668-114">retention label</span></span>


<span data-ttu-id="a3668-115">可以以列表或条形图的形式查看数据。</span><span class="sxs-lookup"><span data-stu-id="a3668-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a3668-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="a3668-116">Prerequisites</span></span>

<span data-ttu-id="a3668-117">访问和使用活动资源管理器的每个帐户，都必须拥有从以下之一订阅向其分配的许可证：</span><span class="sxs-lookup"><span data-stu-id="a3668-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="a3668-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a3668-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="a3668-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a3668-119">Office 365 E5</span></span>
- <span data-ttu-id="a3668-120">高级合规性（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="a3668-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="a3668-121">高级威胁智能（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="a3668-121">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="a3668-122">高级威胁防护（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="a3668-122">Advanced Threat Protection (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="a3668-123">活动类型</span><span class="sxs-lookup"><span data-stu-id="a3668-123">Activity type</span></span>

<span data-ttu-id="a3668-124">Microsoft 365 监视和报告跨 SharePoint Online、OneDrive 和终结点的 12 种活动类型。</span><span class="sxs-lookup"><span data-stu-id="a3668-124">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="a3668-125">终结点是运行 Windows 10 的用户设备。</span><span class="sxs-lookup"><span data-stu-id="a3668-125">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="a3668-126">已创建文件</span><span class="sxs-lookup"><span data-stu-id="a3668-126">File created</span></span>
- <span data-ttu-id="a3668-127">已修改文件</span><span class="sxs-lookup"><span data-stu-id="a3668-127">File modified</span></span>
- <span data-ttu-id="a3668-128">已重命名文件</span><span class="sxs-lookup"><span data-stu-id="a3668-128">File renamed</span></span>
- <span data-ttu-id="a3668-129">已复制到云的文件</span><span class="sxs-lookup"><span data-stu-id="a3668-129">File copied to cloud</span></span>
- <span data-ttu-id="a3668-130">不允许应用访问的文件</span><span class="sxs-lookup"><span data-stu-id="a3668-130">File accessed by unallowed app</span></span>
- <span data-ttu-id="a3668-131">已打印的文件</span><span class="sxs-lookup"><span data-stu-id="a3668-131">File printed</span></span>
- <span data-ttu-id="a3668-132">已复制到可移动媒体的文件</span><span class="sxs-lookup"><span data-stu-id="a3668-132">File copied to removable media</span></span>
- <span data-ttu-id="a3668-133">已复制到网络共享的文件</span><span class="sxs-lookup"><span data-stu-id="a3668-133">File copied to network share</span></span>
- <span data-ttu-id="a3668-134">已读文件</span><span class="sxs-lookup"><span data-stu-id="a3668-134">File read</span></span>
- <span data-ttu-id="a3668-135">已复制到剪贴板的文件</span><span class="sxs-lookup"><span data-stu-id="a3668-135">file copied to clipboard</span></span>
- <span data-ttu-id="a3668-136">已应用的标签</span><span class="sxs-lookup"><span data-stu-id="a3668-136">Label applied</span></span>
- <span data-ttu-id="a3668-137">已更改（已升级、已降级或已删除）的标签</span><span class="sxs-lookup"><span data-stu-id="a3668-137">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="a3668-138">了解对敏感的已标记内容采取何种措施的价值在于，你可以查看已经实施的控件（例如[数据丢失防护策略](data-loss-prevention-policies.md)）是否有效。</span><span class="sxs-lookup"><span data-stu-id="a3668-138">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="a3668-139">如果无效，或者发现某项意外内容（如大量项目被标记为`highly confidential`并降级为`general`），则可管理各种策略并采取新操作来限制意外行为。</span><span class="sxs-lookup"><span data-stu-id="a3668-139">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="a3668-140">设置筛选器后，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a3668-140">Once your filters are set, you can:</span></span>

- <span data-ttu-id="a3668-141">将鼠标悬停在条形图的某一部分，可查看属于该类别“![鼠标悬停在的活动资源管理器](media/data-classification-activity-explorer-hover-over-2.png)”的项目数。</span><span class="sxs-lookup"><span data-stu-id="a3668-141">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="a3668-142">导出数据</span><span class="sxs-lookup"><span data-stu-id="a3668-142">export the data</span></span>
- <span data-ttu-id="a3668-143">从列表中选择任何给定项，并在弹出菜单中查看操作的详细信息</span><span class="sxs-lookup"><span data-stu-id="a3668-143">select any given item from the list and view the details of the action in the fly-out</span></span>

![活动资源管理器详细信息弹出菜单](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="a3668-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3668-145">See also</span></span>
- [<span data-ttu-id="a3668-146">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="a3668-146">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a3668-147">保留标签</span><span class="sxs-lookup"><span data-stu-id="a3668-147">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="a3668-148">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="a3668-148">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="a3668-149">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="a3668-149">Overview of retention policies</span></span>](retention-policies.md)