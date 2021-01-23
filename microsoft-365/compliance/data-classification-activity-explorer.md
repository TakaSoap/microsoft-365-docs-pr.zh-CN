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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 活动资源管理器通过查看和筛选用户对你的标记内容执行的操作来完善数据分类功能的功能。
ms.openlocfilehash: 6825c00373617011db28fa484f272086f887ea40
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921630"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="184cd-103">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="184cd-103">Get started with activity explorer</span></span>

<span data-ttu-id="184cd-104">数据分类概述和内容浏览器选项卡使你可以查看已发现和已标记的内容以及该内容的位置。</span><span class="sxs-lookup"><span data-stu-id="184cd-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="184cd-105">活动资源管理器通过允许你监视对已标记内容所执行的操作来完善此功能套件。</span><span class="sxs-lookup"><span data-stu-id="184cd-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="184cd-106">活动资源管理器提供历史视图。</span><span class="sxs-lookup"><span data-stu-id="184cd-106">Activity explorer provides a historical view.</span></span>

![占位符屏幕截图概述活动资源管理器](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="184cd-108">有 30 多种不同筛选器可供使用，其中有：</span><span class="sxs-lookup"><span data-stu-id="184cd-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="184cd-109">日期范围</span><span class="sxs-lookup"><span data-stu-id="184cd-109">date range</span></span>
- <span data-ttu-id="184cd-110">活动类型</span><span class="sxs-lookup"><span data-stu-id="184cd-110">activity type</span></span>
- <span data-ttu-id="184cd-111">位置</span><span class="sxs-lookup"><span data-stu-id="184cd-111">location</span></span>
- <span data-ttu-id="184cd-112">用户</span><span class="sxs-lookup"><span data-stu-id="184cd-112">user</span></span>
- <span data-ttu-id="184cd-113">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="184cd-113">sensitivity label</span></span>
- <span data-ttu-id="184cd-114">保留标签</span><span class="sxs-lookup"><span data-stu-id="184cd-114">retention label</span></span>
- <span data-ttu-id="184cd-115">文件路径</span><span class="sxs-lookup"><span data-stu-id="184cd-115">file path</span></span>
- <span data-ttu-id="184cd-116">DLP 策略</span><span class="sxs-lookup"><span data-stu-id="184cd-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="184cd-117">必备条件</span><span class="sxs-lookup"><span data-stu-id="184cd-117">Prerequisites</span></span>

<span data-ttu-id="184cd-118">访问和使用数据分类的每个帐户，都必须拥有从以下其中一个订阅向其分配的许可证：</span><span class="sxs-lookup"><span data-stu-id="184cd-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="184cd-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="184cd-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="184cd-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="184cd-120">Office 365 (E5)</span></span>
- <span data-ttu-id="184cd-121">高级合规性（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="184cd-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="184cd-122">高级威胁智能（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="184cd-122">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="184cd-123">Microsoft 365 E5/A5 信息保护和管控</span><span class="sxs-lookup"><span data-stu-id="184cd-123">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="184cd-124">Microsoft 365 E5/A5 合规</span><span class="sxs-lookup"><span data-stu-id="184cd-124">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="184cd-125">权限</span><span class="sxs-lookup"><span data-stu-id="184cd-125">Permissions</span></span>

 <span data-ttu-id="184cd-126">若要访问“活动资源管理器”选项卡，必须在其中任一角色或角色组中向帐户分配成员身份。</span><span class="sxs-lookup"><span data-stu-id="184cd-126">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="184cd-127">**Microsoft 365 角色组**</span><span class="sxs-lookup"><span data-stu-id="184cd-127">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="184cd-128">全局管理员</span><span class="sxs-lookup"><span data-stu-id="184cd-128">Global administrator</span></span>
- <span data-ttu-id="184cd-129">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="184cd-129">Compliance administrator</span></span>
- <span data-ttu-id="184cd-130">安全管理员</span><span class="sxs-lookup"><span data-stu-id="184cd-130">Security administrator</span></span>
- <span data-ttu-id="184cd-131">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="184cd-131">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="184cd-132">活动类型</span><span class="sxs-lookup"><span data-stu-id="184cd-132">Activity type</span></span>

<span data-ttu-id="184cd-133">Microsoft 365 监视和报告跨 SharePoint Online 和 OneDrive 和的活动类型，例如：</span><span class="sxs-lookup"><span data-stu-id="184cd-133">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="184cd-134">已应用的标签</span><span class="sxs-lookup"><span data-stu-id="184cd-134">label applied</span></span>
- <span data-ttu-id="184cd-135">已更改（已升级、已降级或已删除）的标签</span><span class="sxs-lookup"><span data-stu-id="184cd-135">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="184cd-136">自动标记模拟</span><span class="sxs-lookup"><span data-stu-id="184cd-136">auto-labeling simulation</span></span>

<span data-ttu-id="184cd-137">了解对敏感的已标记内容采取何种措施的价值在于，你可以查看已经实施的控件（例如[数据丢失防护策略](data-loss-prevention-policies.md)）是否有效。</span><span class="sxs-lookup"><span data-stu-id="184cd-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="184cd-138">如果无效，或者发现某项意外内容（如大量项目被标记为`highly confidential`并降级为`general`），则可管理各种策略并采取新操作来限制意外行为。</span><span class="sxs-lookup"><span data-stu-id="184cd-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="184cd-139">活动资源管理器当前不监视 Exchange Online 的保留活动。</span><span class="sxs-lookup"><span data-stu-id="184cd-139">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="184cd-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="184cd-140">See also</span></span>
- [<span data-ttu-id="184cd-141">了解敏感度标签</span><span class="sxs-lookup"><span data-stu-id="184cd-141">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="184cd-142">了解保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="184cd-142">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="184cd-143">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="184cd-143">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

