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
search.appverid:
- MOE150
- MET150
description: 活动资源管理器通过查看和筛选用户对你的标记内容执行的操作来完善数据分类功能的功能。
ms.openlocfilehash: 5cb6a8dbfa570b3b0e0d1ce39648d12050d2af81
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327838"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="f454d-103">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="f454d-103">Get started with activity explorer</span></span>

<span data-ttu-id="f454d-104">数据分类概述和内容浏览器选项卡使你可以查看已发现和已标记的内容以及该内容的位置。</span><span class="sxs-lookup"><span data-stu-id="f454d-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="f454d-105">活动资源管理器通过允许你监视对已标记内容所执行的操作来完善此功能套件。</span><span class="sxs-lookup"><span data-stu-id="f454d-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="f454d-106">活动资源管理器提供历史视图。</span><span class="sxs-lookup"><span data-stu-id="f454d-106">Activity explorer provides a historical view.</span></span>

![占位符屏幕截图概述活动资源管理器](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="f454d-108">有 30 多种不同筛选器可供使用，其中有：</span><span class="sxs-lookup"><span data-stu-id="f454d-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="f454d-109">日期范围</span><span class="sxs-lookup"><span data-stu-id="f454d-109">date range</span></span>
- <span data-ttu-id="f454d-110">活动类型</span><span class="sxs-lookup"><span data-stu-id="f454d-110">activity type</span></span>
- <span data-ttu-id="f454d-111">位置</span><span class="sxs-lookup"><span data-stu-id="f454d-111">location</span></span>
- <span data-ttu-id="f454d-112">用户</span><span class="sxs-lookup"><span data-stu-id="f454d-112">user</span></span>
- <span data-ttu-id="f454d-113">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="f454d-113">sensitivity label</span></span>
- <span data-ttu-id="f454d-114">保留标签</span><span class="sxs-lookup"><span data-stu-id="f454d-114">retention label</span></span>
- <span data-ttu-id="f454d-115">文件路径</span><span class="sxs-lookup"><span data-stu-id="f454d-115">file path</span></span>
- <span data-ttu-id="f454d-116">DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f454d-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="f454d-117">必备条件</span><span class="sxs-lookup"><span data-stu-id="f454d-117">Prerequisites</span></span>

<span data-ttu-id="f454d-118">访问和使用数据分类的每个帐户，都必须拥有从以下其中一个订阅向其分配的许可证：</span><span class="sxs-lookup"><span data-stu-id="f454d-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="f454d-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="f454d-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="f454d-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="f454d-120">Office 365 (E5)</span></span>
- <span data-ttu-id="f454d-121">高级合规性（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="f454d-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="f454d-122">高级威胁智能（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="f454d-122">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="f454d-123">权限</span><span class="sxs-lookup"><span data-stu-id="f454d-123">Permissions</span></span>

 <span data-ttu-id="f454d-124">若要访问“活动资源管理器”选项卡，必须在其中任一角色或角色组中向帐户分配成员身份。</span><span class="sxs-lookup"><span data-stu-id="f454d-124">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="f454d-125">**Microsoft 365 角色组**</span><span class="sxs-lookup"><span data-stu-id="f454d-125">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="f454d-126">全局管理员</span><span class="sxs-lookup"><span data-stu-id="f454d-126">Global administrator</span></span>
- <span data-ttu-id="f454d-127">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="f454d-127">Compliance administrator</span></span>
- <span data-ttu-id="f454d-128">安全管理员</span><span class="sxs-lookup"><span data-stu-id="f454d-128">Security administrator</span></span>
- <span data-ttu-id="f454d-129">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="f454d-129">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="f454d-130">活动类型</span><span class="sxs-lookup"><span data-stu-id="f454d-130">Activity type</span></span>

<span data-ttu-id="f454d-131">Microsoft 365 监视和报告跨 SharePoint Online 和 OneDrive 和的活动类型，例如：</span><span class="sxs-lookup"><span data-stu-id="f454d-131">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="f454d-132">已应用的标签</span><span class="sxs-lookup"><span data-stu-id="f454d-132">label applied</span></span>
- <span data-ttu-id="f454d-133">已更改（已升级、已降级或已删除）的标签</span><span class="sxs-lookup"><span data-stu-id="f454d-133">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="f454d-134">自动标记模拟</span><span class="sxs-lookup"><span data-stu-id="f454d-134">auto-labeling simulation</span></span>

<span data-ttu-id="f454d-135">了解对敏感的已标记内容采取何种措施的价值在于，你可以查看已经实施的控件（例如[数据丢失防护策略](data-loss-prevention-policies.md)）是否有效。</span><span class="sxs-lookup"><span data-stu-id="f454d-135">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="f454d-136">如果无效，或者发现某项意外内容（如大量项目被标记为`highly confidential`并降级为`general`），则可管理各种策略并采取新操作来限制意外行为。</span><span class="sxs-lookup"><span data-stu-id="f454d-136">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="f454d-137">活动资源管理器当前不监视 Exchange Online 的保留活动。</span><span class="sxs-lookup"><span data-stu-id="f454d-137">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="f454d-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f454d-138">See also</span></span>
- [<span data-ttu-id="f454d-139">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="f454d-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="f454d-140">保留标签</span><span class="sxs-lookup"><span data-stu-id="f454d-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="f454d-141">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="f454d-141">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="f454d-142">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="f454d-142">Overview of retention policies</span></span>](retention-policies.md)
