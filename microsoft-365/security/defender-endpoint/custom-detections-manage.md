---
title: 在 Microsoft Defender ATP 中查看和管理自定义检测规则
ms.reviewer: ''
description: 了解如何查看和管理自定义检测规则
keywords: 自定义检测， 查看， 管理， 警报， 编辑， 按需运行， 检测规则， 高级搜寻， 智能寻线， 查询， 响应操作， mdatp， microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498757"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="8108f-104">查看和管理自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="8108f-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8108f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8108f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8108f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8108f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8108f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8108f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8108f-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="8108f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8108f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8108f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8108f-110">管理现有的 [自定义检测规则](custom-detection-rules.md) ，以确保它们有效地找到威胁并采取措施。</span><span class="sxs-lookup"><span data-stu-id="8108f-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="8108f-111">了解如何查看规则列表、检查其以前的运行，并查看它们触发的警报。</span><span class="sxs-lookup"><span data-stu-id="8108f-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="8108f-112">您还可以按需运行规则并对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="8108f-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="8108f-113">所需权限</span><span class="sxs-lookup"><span data-stu-id="8108f-113">Required permissions</span></span>

<span data-ttu-id="8108f-114">若要创建或管理自定义检测， [你的](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) 角色需要具有 **管理安全设置** 权限。</span><span class="sxs-lookup"><span data-stu-id="8108f-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="8108f-115">查看现有规则</span><span class="sxs-lookup"><span data-stu-id="8108f-115">View existing rules</span></span>

<span data-ttu-id="8108f-116">若要查看所有现有的自定义检测规则，**请导航到**"设置""  >  **自定义检测"。**</span><span class="sxs-lookup"><span data-stu-id="8108f-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="8108f-117">该页列出了包含以下运行信息的所有规则：</span><span class="sxs-lookup"><span data-stu-id="8108f-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="8108f-118">**上次运行**- 上次运行规则以检查查询匹配并生成警报时</span><span class="sxs-lookup"><span data-stu-id="8108f-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="8108f-119">**上次运行状态**— 规则是否成功运行</span><span class="sxs-lookup"><span data-stu-id="8108f-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="8108f-120">**下一** 次运行 - 下一个计划运行</span><span class="sxs-lookup"><span data-stu-id="8108f-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="8108f-121">**状态**— 规则是已打开还是关闭</span><span class="sxs-lookup"><span data-stu-id="8108f-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="8108f-122">查看规则详细信息、修改规则并运行规则</span><span class="sxs-lookup"><span data-stu-id="8108f-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="8108f-123">若要查看有关自定义检测规则的综合信息，请从设置自定义检测中的规则  >  **列表中选择规则的名称**。</span><span class="sxs-lookup"><span data-stu-id="8108f-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="8108f-124">有关所选规则的页面将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="8108f-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="8108f-125">有关规则的常规信息，包括警报的详细信息、运行状态和范围</span><span class="sxs-lookup"><span data-stu-id="8108f-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="8108f-126">触发的警报列表</span><span class="sxs-lookup"><span data-stu-id="8108f-126">List of triggered alerts</span></span>
- <span data-ttu-id="8108f-127">触发的操作列表</span><span class="sxs-lookup"><span data-stu-id="8108f-127">List of triggered actions</span></span>

<span data-ttu-id="8108f-128">![自定义检测规则页](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="8108f-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="8108f-129">*自定义检测规则页*</span><span class="sxs-lookup"><span data-stu-id="8108f-129">*Custom detection rule page*</span></span>

<span data-ttu-id="8108f-130">您还可以从此页对规则执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8108f-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="8108f-131">**运行** 立即运行规则。</span><span class="sxs-lookup"><span data-stu-id="8108f-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="8108f-132">此操作还会重置下次运行的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8108f-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="8108f-133">**编辑** 在不更改查询的情况下修改规则</span><span class="sxs-lookup"><span data-stu-id="8108f-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="8108f-134">**修改查询**— 在高级搜寻中编辑查询</span><span class="sxs-lookup"><span data-stu-id="8108f-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="8108f-135">**打开**  / **关闭**- 启用规则或阻止其运行</span><span class="sxs-lookup"><span data-stu-id="8108f-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="8108f-136">**删除**- 关闭并删除规则</span><span class="sxs-lookup"><span data-stu-id="8108f-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="8108f-137">若要快速查看信息并针对表中的项目采取操作，请使用表格左侧的选择列 [&#10003;] 。</span><span class="sxs-lookup"><span data-stu-id="8108f-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8108f-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="8108f-138">Related topics</span></span>
- [<span data-ttu-id="8108f-139">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="8108f-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="8108f-140">创建检测规则</span><span class="sxs-lookup"><span data-stu-id="8108f-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="8108f-141">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="8108f-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8108f-142">查看和组织警报</span><span class="sxs-lookup"><span data-stu-id="8108f-142">View and organize alerts</span></span>](alerts-queue.md)
