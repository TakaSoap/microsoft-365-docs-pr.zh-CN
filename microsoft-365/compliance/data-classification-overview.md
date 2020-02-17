---
title: 数据分类入门（预览）
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
description: 借助数据分类仪表板，你可以了解组织中已发现和分类了多少敏感数据。
ms.openlocfilehash: 76c1199fa3842428900db197f15728c116f778b9
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076377"
---
# <a name="data-classification-overview-preview"></a><span data-ttu-id="dbbc8-103">数据分类概述（预览）</span><span class="sxs-lookup"><span data-stu-id="dbbc8-103">Data classification overview (preview)</span></span>

<span data-ttu-id="dbbc8-104">作为 Microsoft 365 管理员或合规性管理员，你可以评估并标记组织中的内容，以便控制其去向，随时随地提供保护，并确保根据组织的需要保留和删除该内容。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according your your organizations needs.</span></span> <span data-ttu-id="dbbc8-105">你可以通过应用[敏感度标签](sensitivity-labels.md)、[保留标签](labels.md)和敏感信息类型分类来实现这一目标。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](labels.md), and sensitive information type classification.</span></span> <span data-ttu-id="dbbc8-106">可通过多种方法进行发现、评估和标记，但最终的结果是，你可能拥有大量的文档和电子邮件，它们使用其中一个或两个标签进行了标记和分类。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large numbers of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="dbbc8-107">应用保留标签和敏感度标签后，你希望了解如何在租户中使用这些标签以及对这些项目所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-107">After you apply  your retention labels and sensitivity labels, you’ll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="dbbc8-108">数据分类页面提供了对内容主体的可见性，具体如下：</span><span class="sxs-lookup"><span data-stu-id="dbbc8-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="dbbc8-109">已分类为敏感信息类型的项目数量以及这些分类是什么</span><span class="sxs-lookup"><span data-stu-id="dbbc8-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="dbbc8-110">Microsoft 365 和 Azure 信息保护中应用最多的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="dbbc8-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="dbbc8-111">应用最多的保留标签</span><span class="sxs-lookup"><span data-stu-id="dbbc8-111">the top applied retention labels</span></span>
- <span data-ttu-id="dbbc8-112">用户对敏感内容所执行的操作的摘要</span><span class="sxs-lookup"><span data-stu-id="dbbc8-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="dbbc8-113">敏感数据和已保留数据的位置</span><span class="sxs-lookup"><span data-stu-id="dbbc8-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="dbbc8-114">可以在“**Microsoft 365 合规中心**”或“**Microsoft 365 安全中心**” > “**分类**” > “**数据分类**”中找到数据分类。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-114">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="dbbc8-115">内容中的最常用敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="dbbc8-115">Sensitive information types used most in your content</span></span>

<span data-ttu-id="dbbc8-116">Microsoft 365 附带了许多敏感信息类型的定义，例如包含社会安全号码或信用卡号的项目。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-116">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="dbbc8-117">有关敏感信息类型的详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-117">For more information on sensitive information types, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="dbbc8-118">敏感信息类型卡片显示了在整个组织中找到并标记的最常用敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-118">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![最常用敏感信息类型](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="dbbc8-120">若要了解任何给定分类类别中的项目数量，请将鼠标悬停在该类别的栏上。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-120">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![最常用敏感信息类型悬停详细信息](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="dbbc8-122">如果卡片上显示消息“找不到包含敏感信息的数据”。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-122">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="dbbc8-123">这表示你的组织中没有任何项目归类为敏感信息类型，也没有对任何项目进行爬网。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-123">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="dbbc8-124">要开始使用标签，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dbbc8-124">To get started with labels, see:</span></span>
>- [<span data-ttu-id="dbbc8-125">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="dbbc8-125">Sensitivity labels</span></span>](sensitivity-labels.md)
>- [<span data-ttu-id="dbbc8-126">保留标签</span><span class="sxs-lookup"><span data-stu-id="dbbc8-126">Retention labels</span></span>](labels.md)
>- [<span data-ttu-id="dbbc8-127">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="dbbc8-127">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="dbbc8-128">应用于内容的最常用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="dbbc8-128">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="dbbc8-129">通过 Microsoft 365 或 Azure 信息保护 (AIP) 将敏感度标签应用于项目时，会出现两种情况：</span><span class="sxs-lookup"><span data-stu-id="dbbc8-129">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="dbbc8-130">指示项目对组织的价值的标记已嵌入到文档中，可随时随地进行跟踪</span><span class="sxs-lookup"><span data-stu-id="dbbc8-130">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="dbbc8-131">标记的存在将实现各种保护行为，例如强制性水印或加密。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-131">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="dbbc8-132">如果启用了终结点保护，你甚至还可阻止项目脱离组织控制。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-132">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="dbbc8-133">有关敏感度标签的详细信息，请参阅[了解敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-133">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="dbbc8-134">必须为 SharePoint 和 OneDrive 中的文件启用灵敏度标签，以使相应的数据出现在数据分类页面中。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-134">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="dbbc8-135">有关详细信息，请参阅[启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-135">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="dbbc8-136">敏感度标签卡片按敏感度级别显示项目（电子邮件或文档）的数量。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-136">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![按敏感度标签分类占位符屏幕快照对内容进行细分](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="dbbc8-138">如果尚未创建或发布任何敏感度标签，或者任何内容均未应用敏感度标签，则此卡片将显示消息“未检测到任何敏感度标签”。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-138">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="dbbc8-139">要开始使用标签，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dbbc8-139">To get started with labels, see:</span></span>
>- <span data-ttu-id="dbbc8-140">[敏感度标签](sensitivity-labels.md)或[配置 Azure 信息保护策略](https://docs.microsoft.com/azure/information-protection/configure-policy)（对于 AIP）</span><span class="sxs-lookup"><span data-stu-id="dbbc8-140">[sensitivity labels](sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="dbbc8-141">应用于内容的最常用保留标签</span><span class="sxs-lookup"><span data-stu-id="dbbc8-141">Top retention labels applied to content</span></span>

<span data-ttu-id="dbbc8-142">保留标签用于管理组织中的内容的处置方式。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-142">Retention labels are used to manage the disposition of content in your organization.</span></span> <span data-ttu-id="dbbc8-143">应用后，它们可用于控制在删除文档之前将其保留多长时间，是否应在删除之前对其进行评审，保留期何时到期或是否应将其标记为永远无法删除的记录。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-143">When applied, they can be used to control how long a document will be kept before deletion, whether it should be reviewed prior to deletion, when it's retention period expires, or whether it should be marked as a record which can never be deleted.</span></span> <span data-ttu-id="dbbc8-144">有关详细信息，请参阅[保留标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-144">For more information see, [Overview of retention labels](labels.md).</span></span>

<span data-ttu-id="dbbc8-145">“应用最多的保留标签”卡片显示具有给定保留标签的项目数量。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-145">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![应用最多的保留标签占位符屏幕快照](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="dbbc8-147">如果此卡片显示消息“未检测到任何保留标签”，则表示尚未创建或发布任何保留标签，或者任何内容均未应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-147">If this card displays the message, "No retention labels detected, it means you haven't created or published any retention  labels or no content has had a retention label applied.</span></span> <span data-ttu-id="dbbc8-148">要开始使用保留标签，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dbbc8-148">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="dbbc8-149">保留标签概述</span><span class="sxs-lookup"><span data-stu-id="dbbc8-149">Overview of retention labels</span></span>](labels.md)

## <a name="top-activities-detected"></a><span data-ttu-id="dbbc8-150">检测到的热门活动</span><span class="sxs-lookup"><span data-stu-id="dbbc8-150">Top activities detected</span></span>

<span data-ttu-id="dbbc8-151">此卡片提供用户对具有敏感度标签的项目执行的最常见操作的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-151">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="dbbc8-152">可使用[活动资源管理器](data-classification-activity-explorer.md)深入了解 Microsoft 365 对位于 Windows 10 终结点上的已标记内容进行跟踪的八种不同活动。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-152">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="dbbc8-153">如果此卡片显示消息“未检测到任何活动”，则表示未对文件执行任何操作，或者未启用用户和管理员审核功能。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-153">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="dbbc8-154">若要打开审核日志，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dbbc8-154">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="dbbc8-155">在安全与合规中心搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="dbbc8-155">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="dbbc8-156">按位置列出的敏感度和保留标签数据</span><span class="sxs-lookup"><span data-stu-id="dbbc8-156">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="dbbc8-157">数据分类报告的重点是让用户了解具有标签的项目数量及其位置。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-157">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="dbbc8-158">通过这些卡片，你可以了解在 Exchange、SharePoint 和 OneDrive 等应用中具有标签的项目数量。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-158">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="dbbc8-159">如果此卡片显示消息“未检测到任何位置”，则表示尚未创建或发布任何敏感度标签，或者任何内容均未应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="dbbc8-159">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="dbbc8-160">若要开始使用敏感度标签，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dbbc8-160">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="dbbc8-161">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="dbbc8-161">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="dbbc8-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbbc8-162">See also</span></span>

- [<span data-ttu-id="dbbc8-163">查看标签活动（预览）</span><span class="sxs-lookup"><span data-stu-id="dbbc8-163">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="dbbc8-164">查看已应用标签的内容（预览）</span><span class="sxs-lookup"><span data-stu-id="dbbc8-164">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="dbbc8-165">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="dbbc8-165">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="dbbc8-166">保留标签</span><span class="sxs-lookup"><span data-stu-id="dbbc8-166">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="dbbc8-167">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="dbbc8-167">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="dbbc8-168">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="dbbc8-168">Overview of retention policies</span></span>](retention-policies.md)
