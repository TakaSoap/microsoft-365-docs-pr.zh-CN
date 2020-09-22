---
title: 使用 Microsoft 威胁防护高级搜寻的共享查询
description: 使用预定义的以及共享的查询快速启动威胁搜寻。 与公众或组织共享查询。
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、架构、kusto、github 存储库、我的查询、共享查询
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.openlocfilehash: 3682044ab100d396719e3b7ffe5a6331852d0d55
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201215"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="7dd37-105">使用高级搜寻的共享查询</span><span class="sxs-lookup"><span data-stu-id="7dd37-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7dd37-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7dd37-106">**Applies to:**</span></span>
- <span data-ttu-id="7dd37-107">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="7dd37-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="7dd37-108">可以与同一个组织内的用户共享[高级搜寻](advanced-hunting-overview.md)查询。</span><span class="sxs-lookup"><span data-stu-id="7dd37-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="7dd37-109">还可以查找在 GitHub 上公开共享的查询。</span><span class="sxs-lookup"><span data-stu-id="7dd37-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="7dd37-110">借助这些查询，你可以快速追寻特定威胁搜寻方案，而无需从头开始编写查询。</span><span class="sxs-lookup"><span data-stu-id="7dd37-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![共享查询的图像](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="7dd37-112">保存、修改和共享查询</span><span class="sxs-lookup"><span data-stu-id="7dd37-112">Save, modify, and share a query</span></span>
<span data-ttu-id="7dd37-113">可以保存新的或已有的查询，以便只有你可以访问它，或将它与组织内的其他用户共享。</span><span class="sxs-lookup"><span data-stu-id="7dd37-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="7dd37-114">创建或修改查询。</span><span class="sxs-lookup"><span data-stu-id="7dd37-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="7dd37-115">单击“保存查询”下拉按钮，并选择“另存为”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7dd37-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="7dd37-116">输入查询的名称。</span><span class="sxs-lookup"><span data-stu-id="7dd37-116">Enter a name for the query.</span></span> 

   ![保存查询的图像](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="7dd37-118">选择要将查询保存到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="7dd37-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="7dd37-119">**共享查询** — 与组织内的所有用户共享</span><span class="sxs-lookup"><span data-stu-id="7dd37-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="7dd37-120">**我的查询** — 只有你可以访问</span><span class="sxs-lookup"><span data-stu-id="7dd37-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="7dd37-121">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7dd37-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="7dd37-122">删除或重命名查询</span><span class="sxs-lookup"><span data-stu-id="7dd37-122">Delete or rename a query</span></span>
1. <span data-ttu-id="7dd37-123">右键单击要重命名或删除的查询。</span><span class="sxs-lookup"><span data-stu-id="7dd37-123">Right-click on a query you want to rename or delete.</span></span>

    ![删除查询的图像](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="7dd37-125">选择“删除”，并确认删除。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7dd37-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="7dd37-126">或者选择“重命名”，并为查询提供新名称。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7dd37-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="7dd37-127">创建指向查询的直接链接</span><span class="sxs-lookup"><span data-stu-id="7dd37-127">Create a direct link to a query</span></span>
<span data-ttu-id="7dd37-128">若要生成直接在高级搜寻查询编辑器中打开您的查询的链接，请先完成查询，然后选择 " **共享链接**"。</span><span class="sxs-lookup"><span data-stu-id="7dd37-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="7dd37-129">访问 GitHub 存储库中的查询</span><span class="sxs-lookup"><span data-stu-id="7dd37-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="7dd37-130">Microsoft 安全研究人员定期在[指定的 GitHub 公共存储库](https://aka.ms/hunting-queries)中共享高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="7dd37-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="7dd37-131">此存储库可自行参与。</span><span class="sxs-lookup"><span data-stu-id="7dd37-131">This repository is open to contributions.</span></span> <span data-ttu-id="7dd37-132">[免费加入 GitHub](https://github.com/)，即可参与。</span><span class="sxs-lookup"><span data-stu-id="7dd37-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="7dd37-133">此外，Microsoft 研究人员还提供了高级搜寻查询，你可以使用它们查找与存在的威胁关联的活动和指示器。</span><span class="sxs-lookup"><span data-stu-id="7dd37-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="7dd37-134">将这些查询作为 Microsoft Defender 安全中心[威胁分析](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)报告的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="7dd37-134">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7dd37-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="7dd37-135">Related topics</span></span>
- [<span data-ttu-id="7dd37-136">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="7dd37-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7dd37-137">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="7dd37-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7dd37-138">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="7dd37-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="7dd37-139">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="7dd37-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7dd37-140">了解架构</span><span class="sxs-lookup"><span data-stu-id="7dd37-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7dd37-141">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="7dd37-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
