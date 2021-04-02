---
title: 使用高级搜寻的共享查询
description: 使用预定义的以及共享的查询快速启动威胁搜寻。 与公众或组织共享查询。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 自定义检测， 架构， kusto， github 存储库， 我的查询， 共享查询
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
ms.openlocfilehash: 78a532167e4256e3453803f1a0b4a9e4875771cf
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499428"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="37c42-105">使用高级搜寻的共享查询</span><span class="sxs-lookup"><span data-stu-id="37c42-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37c42-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="37c42-106">**Applies to:**</span></span>
- [<span data-ttu-id="37c42-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="37c42-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="37c42-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="37c42-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="37c42-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="37c42-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="37c42-110">可以与同一个组织内的用户共享[高级搜寻](advanced-hunting-overview.md)查询。</span><span class="sxs-lookup"><span data-stu-id="37c42-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="37c42-111">还可以查找在 GitHub 上公开共享的查询。</span><span class="sxs-lookup"><span data-stu-id="37c42-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="37c42-112">借助这些查询，你可以快速追寻特定威胁搜寻方案，而无需从头开始编写查询。</span><span class="sxs-lookup"><span data-stu-id="37c42-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![共享查询的图像](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="37c42-114">保存、修改和共享查询</span><span class="sxs-lookup"><span data-stu-id="37c42-114">Save, modify, and share a query</span></span>
<span data-ttu-id="37c42-115">可以保存新的或已有的查询，以便只有你可以访问它，或将它与组织内的其他用户共享。</span><span class="sxs-lookup"><span data-stu-id="37c42-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="37c42-116">在"共享查询"或"我的查询"下键入新查询或 **加载现有查询**。</span><span class="sxs-lookup"><span data-stu-id="37c42-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="37c42-117">从 **保存** 选项 **中选择** 保存或另存为。</span><span class="sxs-lookup"><span data-stu-id="37c42-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="37c42-118">若要避免覆盖现有查询，请选择"**另存为"。**</span><span class="sxs-lookup"><span data-stu-id="37c42-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="37c42-119">输入查询的名称。</span><span class="sxs-lookup"><span data-stu-id="37c42-119">Enter a name for the query.</span></span>

   ![保存查询的图像](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="37c42-121">选择要将查询保存到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="37c42-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="37c42-122">**共享查询** - 与组织中所有用户共享</span><span class="sxs-lookup"><span data-stu-id="37c42-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="37c42-123">**我的查询** — 只有你可以访问</span><span class="sxs-lookup"><span data-stu-id="37c42-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="37c42-124">选择“保存”。</span><span class="sxs-lookup"><span data-stu-id="37c42-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="37c42-125">删除或重命名查询</span><span class="sxs-lookup"><span data-stu-id="37c42-125">Delete or rename a query</span></span>
1. <span data-ttu-id="37c42-126">右键单击要重命名或删除的查询。</span><span class="sxs-lookup"><span data-stu-id="37c42-126">Right-click on a query you want to rename or delete.</span></span>

    ![删除查询的图像](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="37c42-128">选择“删除”，并确认删除。</span><span class="sxs-lookup"><span data-stu-id="37c42-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="37c42-129">或者选择“重命名”，并为查询提供新名称。</span><span class="sxs-lookup"><span data-stu-id="37c42-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="37c42-130">创建指向查询的直接链接</span><span class="sxs-lookup"><span data-stu-id="37c42-130">Create a direct link to a query</span></span>
<span data-ttu-id="37c42-131">若要生成直接在高级搜寻查询编辑器中打开查询的链接，请完成查询并选择"**共享链接"。**</span><span class="sxs-lookup"><span data-stu-id="37c42-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="37c42-132">访问 GitHub 存储库中的查询</span><span class="sxs-lookup"><span data-stu-id="37c42-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="37c42-133">Microsoft 安全研究人员定期在[指定的 GitHub 公共存储库](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)中共享高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="37c42-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="37c42-134">此存储库可自行参与。</span><span class="sxs-lookup"><span data-stu-id="37c42-134">This repository is open to contributions.</span></span> <span data-ttu-id="37c42-135">[免费加入 GitHub](https://github.com/)，即可参与。</span><span class="sxs-lookup"><span data-stu-id="37c42-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="37c42-136">此外，Microsoft 研究人员还提供了高级搜寻查询，你可以使用它们查找与存在的威胁关联的活动和指示器。</span><span class="sxs-lookup"><span data-stu-id="37c42-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="37c42-137">将这些查询作为 Microsoft Defender 安全中心[威胁分析](threat-analytics.md)报告的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="37c42-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="37c42-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="37c42-138">Related topics</span></span>
- [<span data-ttu-id="37c42-139">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="37c42-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="37c42-140">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="37c42-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="37c42-141">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="37c42-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="37c42-142">了解架构</span><span class="sxs-lookup"><span data-stu-id="37c42-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="37c42-143">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="37c42-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="37c42-144">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="37c42-144">Custom detections overview</span></span>](overview-custom-detections.md)
