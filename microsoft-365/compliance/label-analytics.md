---
title: 使用标签分析查看标签使用情况
f1.keywords:
- CSH
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
ms.custom:
- seo-marvel-apr2020
description: 了解如何快速查看使用最多的保留标签和灵敏度标签及其应用位置。
ms.openlocfilehash: 89ccdce54b0d7e6146260037b8dcb085631b408e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817501"
---
# <a name="view-label-usage-with-label-analytics"></a><span data-ttu-id="582bf-103">使用标签分析查看标签使用情况</span><span class="sxs-lookup"><span data-stu-id="582bf-103">View label usage with label analytics</span></span>

<span data-ttu-id="582bf-104">创建保留标签和敏感度标签后，你将希望了解它们如何在租户中使用。</span><span class="sxs-lookup"><span data-stu-id="582bf-104">After you create your retention labels and sensitivity labels, you’ll want to see how they’re being used across your tenant.</span></span> <span data-ttu-id="582bf-105">借助 Microsoft 365 合规中心和 Microsoft 365 安全中心中的标签分析，你可以快速查看最常用的标签以及它们的应用位置。</span><span class="sxs-lookup"><span data-stu-id="582bf-105">With label analytics in the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly see which labels are used the most and where they’re being applied.</span></span>

<span data-ttu-id="582bf-106">例如，借助标签分析，你可以查看：</span><span class="sxs-lookup"><span data-stu-id="582bf-106">For example, with label analytics, you can view the:</span></span>

- <span data-ttu-id="582bf-107">应用于内容的保留标签和敏感度标签的总数。</span><span class="sxs-lookup"><span data-stu-id="582bf-107">Total number of retention labels and sensitivity labels applied to content.</span></span>
- <span data-ttu-id="582bf-108">顶部标签和每个标签应用次数的计数。</span><span class="sxs-lookup"><span data-stu-id="582bf-108">Top labels and the count of how many times each label was applied.</span></span>
- <span data-ttu-id="582bf-109">应用标签的位置和每个位置的计数。</span><span class="sxs-lookup"><span data-stu-id="582bf-109">Locations where labels are applied and the count for each location.</span></span>
- <span data-ttu-id="582bf-110">更改或删除其保留标签的文件和文件夹的计数。</span><span class="sxs-lookup"><span data-stu-id="582bf-110">Count for how many files and folders had their retention label changed or removed.</span></span>

<span data-ttu-id="582bf-111">可以在 [Microsoft 365 合规中心](https://compliance.microsoft.com/labelanalytics)或 [Microsoft 365 安全中心](https://security.microsoft.com/labelanalytics) > “**分类**” > “**标签分析**”中找到标签分析。</span><span class="sxs-lookup"><span data-stu-id="582bf-111">You can find label analytics in the [Microsoft 365 compliance center](https://compliance.microsoft.com/labelanalytics) or [Microsoft 365 security center](https://security.microsoft.com/labelanalytics) > **Classification** > **Label analytics**.</span></span>

![“标签分析”页](../media/label-analytics-page.png)

## <a name="sensitivity-label-usage"></a><span data-ttu-id="582bf-113">敏感度标签使用情况</span><span class="sxs-lookup"><span data-stu-id="582bf-113">Sensitivity label usage</span></span>

<span data-ttu-id="582bf-114">有关敏感度标签使用情况的数据是从 Azure 信息保护的报告中提取的 – 有关详细信息，请参阅 [Azure 信息保护的中央报告](https://docs.microsoft.com/azure/information-protection/reports-aip)。</span><span class="sxs-lookup"><span data-stu-id="582bf-114">The data on sensitivity label usage is pulled from the reports for Azure Information Protection – for more information, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="582bf-115">请注意，Azure 信息保护报告的[先决条件](/azure/information-protection/reports-aip#prerequisites)也适用于 Microsoft 365 合规中心和 Microsoft 365 安全中心中敏感度标签上的标签分析。</span><span class="sxs-lookup"><span data-stu-id="582bf-115">Note that the Azure Information Protection reports have [prerequisites](/azure/information-protection/reports-aip#prerequisites) that also apply to label analytics on sensitivity labels in the Microsoft 365 compliance center and Microsoft 365 security center.</span></span> <span data-ttu-id="582bf-116">例如，你需要包含 Log Analytics 的 Azure 订阅，因为这些报告是将信息保护审核事件从 Azure 信息保护客户端和扫描程序发送到基于 Azure Log Analytics 服务的集中位置的结果。</span><span class="sxs-lookup"><span data-stu-id="582bf-116">For example, you need an Azure subscription that includes the Log Analytics because these reports are a result of sending information protection audit events from Azure Information Protection clients and scanners to a centralized location based on Azure Log Analytics service.</span></span>

<span data-ttu-id="582bf-117">对于敏感度标签用使用情况法：</span><span class="sxs-lookup"><span data-stu-id="582bf-117">For sensitivity label usage:</span></span>

- <span data-ttu-id="582bf-118">该数据中没有延迟。</span><span class="sxs-lookup"><span data-stu-id="582bf-118">There is no latency in the data.</span></span> <span data-ttu-id="582bf-119">这是实时报告。</span><span class="sxs-lookup"><span data-stu-id="582bf-119">This is a real-time report.</span></span>
- <span data-ttu-id="582bf-120">若要查看每个顶部标签的计数，请指向条形图，然后阅读显示的工具提示。</span><span class="sxs-lookup"><span data-stu-id="582bf-120">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="582bf-121">该报告显示每个应用应用敏感度标签的位置（而每个位置都显示保留标签）。</span><span class="sxs-lookup"><span data-stu-id="582bf-121">The report shows where sensitivity labels are applied per app (whereas retention labels are shown per location).</span></span>

![敏感度标签使用情况报告](../media/sensitivity-label-usage-report.png)

## <a name="retention-label-usage"></a><span data-ttu-id="582bf-123">保留标签使用情况</span><span class="sxs-lookup"><span data-stu-id="582bf-123">Retention label usage</span></span>

<span data-ttu-id="582bf-124">此报告可快速查看顶部标签的内容及其应用位置。</span><span class="sxs-lookup"><span data-stu-id="582bf-124">This report shows a quick view of what the top labels are and where they’re applied.</span></span> <span data-ttu-id="582bf-125">有关如何标记 SharePoint 和 OneDrive 中内容的详细信息，请参阅[查看文档的标签活动](view-label-activity-for-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="582bf-125">For more detailed information on how content in SharePoint and OneDrive is labeled, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

<span data-ttu-id="582bf-126">对于保留标签使用情况：</span><span class="sxs-lookup"><span data-stu-id="582bf-126">For retention label usage:</span></span>

- <span data-ttu-id="582bf-127">数据每周汇总一次，因此数据最多可能需要 7 天才能显示在报告中。</span><span class="sxs-lookup"><span data-stu-id="582bf-127">Data is aggregated weekly, so it may take up to seven days for data to appear in the report.</span></span>
- <span data-ttu-id="582bf-128">若要查看每个顶部标签的计数，请指向条形图，然后阅读显示的工具提示。</span><span class="sxs-lookup"><span data-stu-id="582bf-128">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="582bf-129">该报告显示每个位置应用保留标签的位置（而每个应用都显示敏感度标签）。</span><span class="sxs-lookup"><span data-stu-id="582bf-129">The report shows where retention labels are applied per location (whereas sensitivity labels are shown per app).</span></span>
- <span data-ttu-id="582bf-130">对于保留标签，这是租户中所有时间数据的汇总；它没有筛选到特定的日期范围。</span><span class="sxs-lookup"><span data-stu-id="582bf-130">For retention labels, this is a summary of the all-time data in your tenant; it’s not filtered to a specific date range.</span></span> <span data-ttu-id="582bf-131">相比之下，[标签活动资源管理器](view-label-activity-for-documents.md)仅显示过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="582bf-131">By contrast, the [Label Activity Explorer](view-label-activity-for-documents.md) shows data from only the past 30 days.</span></span>

![保留标签使用情况报告](../media/retention-label-usage-report.png)

## <a name="view-all-content-with-a-specific-retention-label"></a><span data-ttu-id="582bf-133">查看具有特定保留标签的所有内容</span><span class="sxs-lookup"><span data-stu-id="582bf-133">View all content with a specific retention label</span></span>

<span data-ttu-id="582bf-134">从保留标签使用情况报告中，可以快速浏览应用了该标签的所有内容。</span><span class="sxs-lookup"><span data-stu-id="582bf-134">From the retention label usage report, you can quickly explore all content with that label applied.</span></span> <span data-ttu-id="582bf-135">（请注意，我们目前正在使用此功能，因此查看所有标记内容所需的步骤更少。）</span><span class="sxs-lookup"><span data-stu-id="582bf-135">(Note that we're currently working on this feature, so that it will take fewer steps to view all the labeled content.)</span></span>

<span data-ttu-id="582bf-136">首先，选择报告底部的“**查看详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="582bf-136">First, choose **View Details** at the bottom of the report.</span></span>

![保留标签使用情况报告底部的“查看详细信息”选项](../media/retention-label-usage-view-details.png)

<span data-ttu-id="582bf-138">然后在右侧窗格中选择保留标签 >“**查看项目**”。</span><span class="sxs-lookup"><span data-stu-id="582bf-138">Then choose a retention label > **Explore items** in the right pane.</span></span>

![右侧窗格中的“查看项目”选项](../media/retention-label-usage-explore-items.png)

<span data-ttu-id="582bf-140">对于该标签，可以选择“**活动**”选项卡以按位置查看具有该标签的项目数。</span><span class="sxs-lookup"><span data-stu-id="582bf-140">For that label, you can choose the **Activity** tab to view a count of items with that label by location.</span></span>

![保留标签的“活动”选项卡](../media/retention-label-usage-activity-tab.png)

<span data-ttu-id="582bf-142">也可以选择“**具有此标签的项目**”选项卡。然后可以深入了解特定位置：</span><span class="sxs-lookup"><span data-stu-id="582bf-142">You can also choose the **Items with this label** tab. Then you can drill into specific locations:</span></span>

- <span data-ttu-id="582bf-143">对于 Exchange Online，你会看到一个邮箱列表，其中包含每个邮箱中已标记项目的计数。</span><span class="sxs-lookup"><span data-stu-id="582bf-143">For Exchange Online, you see a list of mailboxes with the count of labeled items in each mailbox.</span></span>
- <span data-ttu-id="582bf-144">对于 SharePoint Online 和 OneDrive for Business，你会看到网站集和 OneDrive 帐户的列表，其中包含每个位置中已标记项目的计数。</span><span class="sxs-lookup"><span data-stu-id="582bf-144">For SharePoint Online and OneDrive for Business, you see a list of site collections and OneDrive accounts with the count of labeled items in each location.</span></span>

<span data-ttu-id="582bf-145">选择邮箱或站点集时，可以在该位置中查看具有该保留标签的项目的列表。</span><span class="sxs-lookup"><span data-stu-id="582bf-145">When you choose a mailbox or site collection, you can view a list of items with that retention label in that location.</span></span>

![具有此标签的项目，显示具有该保留标签的所有项目](../media/retention-label-usage-content-explorer.png)

## <a name="permissions"></a><span data-ttu-id="582bf-147">权限</span><span class="sxs-lookup"><span data-stu-id="582bf-147">Permissions</span></span>

<span data-ttu-id="582bf-148">若要查看标签分析，必须在 Azure Active Directory 中为你分配以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="582bf-148">To view label analytics, you must be assigned one of the following roles in Azure Active Directory:</span></span>

- <span data-ttu-id="582bf-149">全局管理员</span><span class="sxs-lookup"><span data-stu-id="582bf-149">Global administrator</span></span>
- <span data-ttu-id="582bf-150">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="582bf-150">Compliance administrator</span></span>
- <span data-ttu-id="582bf-151">安全管理员</span><span class="sxs-lookup"><span data-stu-id="582bf-151">Security administrator</span></span>
- <span data-ttu-id="582bf-152">安全读者</span><span class="sxs-lookup"><span data-stu-id="582bf-152">Security reader</span></span>

<span data-ttu-id="582bf-153">此外，请注意这些报告使用 Azure Monitor 将数据存储在组织拥有的 Log Analytics 工作区中。</span><span class="sxs-lookup"><span data-stu-id="582bf-153">In addition, note these reports use Azure Monitor to store the data in a Log Analytics workspace that your organization owns.</span></span> <span data-ttu-id="582bf-154">因此，应将用户作为读者添加到包含数据的 Azure 监视工作区 - 有关详细信息，请参阅 [Azure 信息保护分析所需的权限](https://docs.microsoft.com/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics)。</span><span class="sxs-lookup"><span data-stu-id="582bf-154">Therefore, the user should be added as a reader to the Azure Monitoring workspace that holds the data - for more information, see [Permissions required for Azure Information Protection analytics](https://docs.microsoft.com/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span></span>

