---
title: 了解用于自动保留或删除内容的保留策略和保留标签
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解有助于保留所需内容并删除不需要内容的保留策略和保留标签。
ms.openlocfilehash: 8d50e03827026100689d9b380570fa59c93e6d08
ms.sourcegitcommit: 5756896ad87e28fac20f7981eaaeacfb0c098254
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2020
ms.locfileid: "49730173"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="e6698-103">了解保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="e6698-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="e6698-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="e6698-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e6698-p101">对于大多数组织，数据量和数据复杂性每天都在增加 — 包括电子邮件、文档、即时消息等。有效管理或管理此类信息非常重要，因为要：</span><span class="sxs-lookup"><span data-stu-id="e6698-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="e6698-107">**主动遵守规定至少必须在一段时间内保留内容的行业法规和内部策略**：例如，《萨班斯-奥克斯利法案》规定，必须保留特定类型的内容七年。</span><span class="sxs-lookup"><span data-stu-id="e6698-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 

- <span data-ttu-id="e6698-108">**降低发生诉讼或出现安全漏洞的风险**：通过永久删除不再需要保留的旧内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="e6698-109">**帮助组织有效共享知识并提高敏捷性**：通过确保用户仅处理与自己相关的最新内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="e6698-110">你配置的保留设置可有助于实现所有这些目标。</span><span class="sxs-lookup"><span data-stu-id="e6698-110">Retention settings that you configure can help you achieve all these goals.</span></span> <span data-ttu-id="e6698-111">管理内容通常需要执行两项操作：</span><span class="sxs-lookup"><span data-stu-id="e6698-111">Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="e6698-112">**保留** 内容，这样除非保留期到期，否则无法永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="e6698-113">在保留期到期时永久 **删除** 内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    

<span data-ttu-id="e6698-114">通过这两项保留操作，可以配置保留设置来实现以下结果：</span><span class="sxs-lookup"><span data-stu-id="e6698-114">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="e6698-115">仅保留：永久或在指定的时间段内保留内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-115">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="e6698-116">仅删除：在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-116">Delete-only: Delete content after a specified period of time.</span></span>
- <span data-ttu-id="e6698-117">保留后删除：在指定的时间段内保留内容后删除内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-117">Retain and then delete: Retain content for a specified period of time and then delete it.</span></span>

<span data-ttu-id="e6698-118">这些保留设置应用于在适当位置上的内容，如果你出于合规性原因需要保留内容，它们可以为你节省创建和配置附加存储的额外开销。</span><span class="sxs-lookup"><span data-stu-id="e6698-118">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons.</span></span> <span data-ttu-id="e6698-119">另外，无需实现自定义流程来复制和同步此数据。</span><span class="sxs-lookup"><span data-stu-id="e6698-119">In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="e6698-120">保留设置如何应用于在适当位置上的内容</span><span class="sxs-lookup"><span data-stu-id="e6698-120">How retention settings work with content in place</span></span>

<span data-ttu-id="e6698-121">分配有保留设置的内容保留在它的原始位置上。</span><span class="sxs-lookup"><span data-stu-id="e6698-121">When content has retention settings assigned to it, that content remains in its original location.</span></span> <span data-ttu-id="e6698-122">用户可以继续处理自己的文档或邮件，就像什么都没有改变一样。</span><span class="sxs-lookup"><span data-stu-id="e6698-122">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="e6698-123">但如果他们编辑或删除了包含在保留策略中的内容，则会自动保留一份内容的副本。</span><span class="sxs-lookup"><span data-stu-id="e6698-123">But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained.</span></span>
  
- <span data-ttu-id="e6698-124">对于 SharePoint 和 OneDrive 网站：副本保留在 **保留** 库中。</span><span class="sxs-lookup"><span data-stu-id="e6698-124">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="e6698-125">对于 Exchange 邮箱：副本保留在“可恢复项”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e6698-125">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="e6698-126">对于 Teams 和 Yammer 消息：副本保留在 Exchange“**可恢复项**”文件夹内名为“**SubstrateHolds**”的隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e6698-126">For Teams and Yammer messages: The copy is retained in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="e6698-127">保留库占用的存储计入网站的存储配额。</span><span class="sxs-lookup"><span data-stu-id="e6698-127">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="e6698-128">在对 SharePoint 和 Microsoft 365 组使用保留设置时，可能需要增加存储空间。</span><span class="sxs-lookup"><span data-stu-id="e6698-128">You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="e6698-129">这些安全位置和保留的内容对大部分用户不可见。</span><span class="sxs-lookup"><span data-stu-id="e6698-129">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="e6698-130">在大多数情况下，用户甚至不需要知道他们的内容遵循保留设置。</span><span class="sxs-lookup"><span data-stu-id="e6698-130">In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="e6698-131">若要详细了解保留设置如何用于不同的工作负载，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="e6698-131">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="e6698-132">了解用于 SharePoint 和 OneDrive 的保留</span><span class="sxs-lookup"><span data-stu-id="e6698-132">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="e6698-133">了解用于 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="e6698-133">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="e6698-134">了解用于 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="e6698-134">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="e6698-135">了解用于 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="e6698-135">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="e6698-136">保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="e6698-136">Retention policies and retention labels</span></span>

<span data-ttu-id="e6698-137">可以使用保留策略和带有标签策略的保留标签来为内容分配保留设置。</span><span class="sxs-lookup"><span data-stu-id="e6698-137">You can use both retention policies and retention labels with label policies to assign your retention settings to content.</span></span> 

<span data-ttu-id="e6698-138">使用保留策略可以在网站或邮箱级别为内容分配相同的保留设置，使用保留标签可以在项（文件夹、文档、电子邮件）级别分配保留设置。</span><span class="sxs-lookup"><span data-stu-id="e6698-138">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="e6698-139">例如，如果某 SharePoint 网站中的所有文档都应保留 5 年，那么使用保留策略比将相同的保留标签应用于此网站中的所有文档更高效。</span><span class="sxs-lookup"><span data-stu-id="e6698-139">For example, if all documents in a SharePoint site should be retained for 5 years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site.</span></span> <span data-ttu-id="e6698-140">不过，如果此网站中的一些文档应保留 5 年，另一些文档应保留 10 年，那么保留策略就无法实现这一点。</span><span class="sxs-lookup"><span data-stu-id="e6698-140">However, if some documents in that site should be retained for 5 years and others retained for 10 years, a retention policy wouldn't be able to do this.</span></span> <span data-ttu-id="e6698-141">如果需要在项级别指定保留设置，请使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-141">When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="e6698-142">与保留策略不同，如果内容移动到 Microsoft 365 租户内的不同位置，保留标签的保留设置会随着内容移动而移动。</span><span class="sxs-lookup"><span data-stu-id="e6698-142">Unlike retention policies, retention settings from retention labels travel with the content if it’s moved to a different location within your Microsoft 365 tenant.</span></span> <span data-ttu-id="e6698-143">另外，保留标签具有保留策略不支持的以下功能：</span><span class="sxs-lookup"><span data-stu-id="e6698-143">In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="e6698-144">除了根据内容年限或上次修改时间计算保留期之外，还可以从内容被标记时或根据事件开始计算保留期。</span><span class="sxs-lookup"><span data-stu-id="e6698-144">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="e6698-145">使用[可训练的分类器](classifier-learn-about.md)来标识要标记的内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-145">Use [trainable classifiers](classifier-learn-about.md) to identify content to label.</span></span>

- <span data-ttu-id="e6698-146">为 SharePoint 文档应用默认标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-146">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="e6698-147">支持[处置评审](disposition-reviews.md) ，以在永久删除内容前评审内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-147">Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="e6698-148">将内容标记为[记录](records-management.md#records)作为标签设置的一部分，并对在保留期结束时删除的内容始终都有 [处置证明](disposition.md#disposition-of-records) 。</span><span class="sxs-lookup"><span data-stu-id="e6698-148">Mark the content as a [record](records-management.md#records) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="e6698-149">保留策略</span><span class="sxs-lookup"><span data-stu-id="e6698-149">Retention policies</span></span>

<span data-ttu-id="e6698-150">可以将保留策略应用于以下位置：</span><span class="sxs-lookup"><span data-stu-id="e6698-150">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="e6698-151">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="e6698-151">Exchange email</span></span>
- <span data-ttu-id="e6698-152">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="e6698-152">SharePoint site</span></span>
- <span data-ttu-id="e6698-153">OneDrive 账户</span><span class="sxs-lookup"><span data-stu-id="e6698-153">OneDrive accounts</span></span>
- <span data-ttu-id="e6698-154">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="e6698-154">Microsoft 365 Groups</span></span>
- <span data-ttu-id="e6698-155">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e6698-155">Skype for Business</span></span>
- <span data-ttu-id="e6698-156">Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="e6698-156">Exchange public folders</span></span>
- <span data-ttu-id="e6698-157">Teams 通道消息</span><span class="sxs-lookup"><span data-stu-id="e6698-157">Teams channel messages</span></span>
- <span data-ttu-id="e6698-158">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="e6698-158">Teams chats</span></span>
- <span data-ttu-id="e6698-159">yammer 社区消息</span><span class="sxs-lookup"><span data-stu-id="e6698-159">Yammer community messages</span></span>
- <span data-ttu-id="e6698-160">Yammer 私信</span><span class="sxs-lookup"><span data-stu-id="e6698-160">Yammer private messages</span></span>

<span data-ttu-id="e6698-161">可以非常高效地将一个策略应用于多个位置，也可以应用于特定的位置或用户。</span><span class="sxs-lookup"><span data-stu-id="e6698-161">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>

<span data-ttu-id="e6698-162">对于保留期的开始，你可以选择内容创建的时间，或者上次修改内容的时间（仅支持文件和 SharePoint、OneDrive 和 Microsoft 365 组位置）。</span><span class="sxs-lookup"><span data-stu-id="e6698-162">For the start of the retention period, you can choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups locations, when the content was last modified.</span></span>

<span data-ttu-id="e6698-163">项目从保留策略所指定的容器中继承保留设置。</span><span class="sxs-lookup"><span data-stu-id="e6698-163">Items inherit the retention settings from their container specified in the retention policy.</span></span> <span data-ttu-id="e6698-164">如果当策略配置为保留内容之后将它们移动到该容器之外，则该项目的副本将保留在工作负载的安全位置。</span><span class="sxs-lookup"><span data-stu-id="e6698-164">If they are then moved outside that container when the policy is configured to retain content, a copy of that item is retained in the workload's secured location.</span></span> <span data-ttu-id="e6698-165">然而，保留设置不会随着内容在新的位置而一起移动。</span><span class="sxs-lookup"><span data-stu-id="e6698-165">However, the retention settings don't travel with the content in its new location.</span></span> <span data-ttu-id="e6698-166">如果需要，请使用保留标签而不是保留策略。</span><span class="sxs-lookup"><span data-stu-id="e6698-166">If that's required, use retention labels instead of retention policies.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="e6698-167">保留标签</span><span class="sxs-lookup"><span data-stu-id="e6698-167">Retention labels</span></span>

<span data-ttu-id="e6698-168">对于需要不同保留设置的不同类型的内容，可以使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-168">Use retention labels for different types of content that require different retention settings.</span></span> <span data-ttu-id="e6698-169">例如：</span><span class="sxs-lookup"><span data-stu-id="e6698-169">For example:</span></span>
  
- <span data-ttu-id="e6698-170">至少必须保留一段时间的税务表单。</span><span class="sxs-lookup"><span data-stu-id="e6698-170">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="e6698-171">达到特定年限后必须永久删除的新闻材料。</span><span class="sxs-lookup"><span data-stu-id="e6698-171">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="e6698-172">必须在保留一段时间后永久删除的竞争性研究。</span><span class="sxs-lookup"><span data-stu-id="e6698-172">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="e6698-173">必须标记为记录以免被编辑或删除的工作签证。</span><span class="sxs-lookup"><span data-stu-id="e6698-173">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="e6698-174">在所有这些情况下，可以使用保留标签在项（文档或电子邮件）级别应用保留设置来实现管理控制。</span><span class="sxs-lookup"><span data-stu-id="e6698-174">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="e6698-175">使用保留标签，你可以：</span><span class="sxs-lookup"><span data-stu-id="e6698-175">With retention labels, you can:</span></span>
  
- <span data-ttu-id="e6698-176">**允许组织中的人员将保留标签手动应用于** Outlook 和 Outlook 网页版、OneDrive、SharePoint​​ 和 Microsoft 365 组中的内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-176">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups.</span></span> <span data-ttu-id="e6698-177">用户通常最了解自己处理的内容的类型，因此他们可以对内容进行分类，并应用适当的保留设置。</span><span class="sxs-lookup"><span data-stu-id="e6698-177">Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="e6698-178">**将保留标签自动应用于** 符合特定条件的内容，如内容包含：</span><span class="sxs-lookup"><span data-stu-id="e6698-178">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="e6698-179">特定类型敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e6698-179">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="e6698-180">与所创建的查询匹配的特定关键字。</span><span class="sxs-lookup"><span data-stu-id="e6698-180">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="e6698-181">可训练分类器的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="e6698-181">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="e6698-182">**从内容被标记时开始计算保留期**，适用于 SharePoint 网站和 OneDrive 帐户中的文档，以及除日历项外的电子邮件项。</span><span class="sxs-lookup"><span data-stu-id="e6698-182">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items.</span></span> <span data-ttu-id="e6698-183">如果你将具有此配置的保留标签应用于日历项，保留期从日历项发送时开始计算。</span><span class="sxs-lookup"><span data-stu-id="e6698-183">If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="e6698-184">**从事件发生时开始计算保留期**，如员工离开组织或合同到期。</span><span class="sxs-lookup"><span data-stu-id="e6698-184">**Start the retention period when an event occurs**, such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="e6698-185">**将默认保留标签应用于 SharePoint 中的文档库、文件夹或文档集**，以让存储在该位置的所有文档都继承默认保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-185">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="e6698-186">此外，保留标签支持跨 Microsoft 365 应用和服务对电子邮件和文档实施[记录管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="e6698-186">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services.</span></span> <span data-ttu-id="e6698-187">可使用保留标签将项目标记为记录。</span><span class="sxs-lookup"><span data-stu-id="e6698-187">You can use a retention label to mark items as a record.</span></span> <span data-ttu-id="e6698-188">如果发生这种情况，而内容仍保留在 Microsoft 365 中，则标签会对内容进行进一步的限制，这可能是监管原因所致。</span><span class="sxs-lookup"><span data-stu-id="e6698-188">When this happens and the content remains in Microsoft 365, the label places further restrictions on the content that might be needed for regulatory reasons.</span></span> <span data-ttu-id="e6698-189">有关详细信息，请参阅[比较对允许或阻止的操作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="e6698-189">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

<span data-ttu-id="e6698-190">如果内容被移动到 Microsoft 365 之外，则保留标签将不会继续存在，这一点与[敏感度标签](sensitivity-labels.md)是不同的。</span><span class="sxs-lookup"><span data-stu-id="e6698-190">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="e6698-191">租户支持的保留标签数没有限制。</span><span class="sxs-lookup"><span data-stu-id="e6698-191">There is no limit to the number of retention labels that are supported for a tenant.</span></span> <span data-ttu-id="e6698-192">但是，租户支持的最大策略数为 10,000，其中包括应用标签的策略（保留标签策略和自动应用保留策略）以及保留策略。</span><span class="sxs-lookup"><span data-stu-id="e6698-192">However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="e6698-193">对内容分类但不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="e6698-193">Classifying content without applying any actions</span></span>

<span data-ttu-id="e6698-194">虽然保留标签的主要用途是保留或删除内容，但也可以在使用保留标签时不启用任何保留或其他操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-194">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions.</span></span> <span data-ttu-id="e6698-195">在这种情况下，可以简单地将保留标签用作文本标签，而不强制执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-195">In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="e6698-196">例如，可以创建并应用名为“稍后评审”且不含任何操作的保留标签，稍后使用此标签来查找相应内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-196">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![将设置标记为仅分类](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="e6698-198">将保留标签用作 DLP 策略中的条件</span><span class="sxs-lookup"><span data-stu-id="e6698-198">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="e6698-199">对于 SharePoint 中的文档，可以将保留标签指定为数据丢失防护 (DLP) 策略中的条件。</span><span class="sxs-lookup"><span data-stu-id="e6698-199">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint.</span></span> <span data-ttu-id="e6698-200">例如，配置一个 DLP 策略，以防在组织外部共享应用了指定保留标签的文档。</span><span class="sxs-lookup"><span data-stu-id="e6698-200">For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="e6698-201">有关详细信息，请参阅[将保留标签用作 DLP 策略中的条件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="e6698-201">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="e6698-202">保留标签和应用它们的策略</span><span class="sxs-lookup"><span data-stu-id="e6698-202">Retention labels and policies that apply them</span></span>

<span data-ttu-id="e6698-203">保留标签是独立的可重用的构建基块。</span><span class="sxs-lookup"><span data-stu-id="e6698-203">Retention labels are independent, reusable building blocks.</span></span> <span data-ttu-id="e6698-204">保留标签策略的主要目的是对一组保留标签进行分组，并指定要显示标签的位置。</span><span class="sxs-lookup"><span data-stu-id="e6698-204">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span> <span data-ttu-id="e6698-205">然后，管理员和用户可以将这些标签应用于这些位置中的内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-205">Then, admins and users can apply those labels to content in those locations.</span></span>
  
![标签、标签策略和位置的关系图](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
<span data-ttu-id="e6698-207">在你发布保留标签后，它们包含在保留标签策略中，以供管理员和用户选择：</span><span class="sxs-lookup"><span data-stu-id="e6698-207">When you publish retention labels, they're included in a retention label policy that make them available for admins and users to select:</span></span>

- <span data-ttu-id="e6698-208">一个保留标签可以包含在多个保留标签策略中。</span><span class="sxs-lookup"><span data-stu-id="e6698-208">A single retention label can be included in many retention label policies.</span></span>

- <span data-ttu-id="e6698-209">保留标签策略指定了保留标签的发布位置。</span><span class="sxs-lookup"><span data-stu-id="e6698-209">Retention label policies specify the locations to publish the retention labels.</span></span>

- <span data-ttu-id="e6698-210">一个位置也可以包含在多个保留标签策略中。</span><span class="sxs-lookup"><span data-stu-id="e6698-210">A single location can also be included in many retention label policies.</span></span>

<span data-ttu-id="e6698-211">除了保留标签策略之外，还可以创建一个或多个自动应用策略，每个策略都有一个保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-211">In addition to retention label policies, you can also create one or more auto-apply policies, each with a single retention label.</span></span> <span data-ttu-id="e6698-212">如果使用此策略，当满足你在策略中指定的条件时，保留标签就会自动应用。</span><span class="sxs-lookup"><span data-stu-id="e6698-212">With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span>

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="e6698-213">保留标签策略和位置</span><span class="sxs-lookup"><span data-stu-id="e6698-213">Retention label policies and locations</span></span>

<span data-ttu-id="e6698-214">不同类型的保留标签可发布到不同位置，具体视保留标签用途而定。</span><span class="sxs-lookup"><span data-stu-id="e6698-214">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="e6698-215">如果保留标签是…</span><span class="sxs-lookup"><span data-stu-id="e6698-215">If the retention label is…</span></span> | <span data-ttu-id="e6698-216">可以将标签策略应用于…</span><span class="sxs-lookup"><span data-stu-id="e6698-216">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="e6698-217">发布给管理员和最终用户</span><span class="sxs-lookup"><span data-stu-id="e6698-217">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="e6698-218">Exchange、SharePoint、OneDrive、Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="e6698-218">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="e6698-219">根据敏感信息类型或可训练的分类器自动应用</span><span class="sxs-lookup"><span data-stu-id="e6698-219">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="e6698-220">Exchange（仅全部邮箱）、SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="e6698-220">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="e6698-221">根据查询自动应用</span><span class="sxs-lookup"><span data-stu-id="e6698-221">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="e6698-222">Exchange、SharePoint、OneDrive、Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="e6698-222">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="e6698-223">在 Exchange 中，自动应用保留标签只会应用于新发送的邮件（传输中的数据），而不是应用于邮箱中当前的所有项（静态数据）。</span><span class="sxs-lookup"><span data-stu-id="e6698-223">In Exchange, auto-apply retention labels are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="e6698-224">此外，用于敏感信息类型和可训练的分类器的自动应用保留标签应用于所有邮箱；你无法选择特定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e6698-224">Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="e6698-225">Exchange 公用文件夹、Skype、Teams 和 Yammer 消息不支持保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-225">Exchange public folders, Skype, Teams and Yammer messages do not support retention labels.</span></span> <span data-ttu-id="e6698-226">若要保留并从这些位置中删除内容，请改用保留策略。</span><span class="sxs-lookup"><span data-stu-id="e6698-226">To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="e6698-227">一次只能分配一个保留标签</span><span class="sxs-lookup"><span data-stu-id="e6698-227">Only one retention label at a time</span></span>

<span data-ttu-id="e6698-228">电子邮件或文档一次只能应用有一个保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-228">An email or document can have only a single retention label applied to it at a time.</span></span> <span data-ttu-id="e6698-229">保留标签可以由最终用户或管理员[手动](create-apply-retention-labels.md#manually-apply-retention-labels)应用，也可以使用以下任一方法自动应用：</span><span class="sxs-lookup"><span data-stu-id="e6698-229">A retention label can be applied [manually](create-apply-retention-labels.md#manually-apply-retention-labels) by an end user or admin, or automatically by using any of the following methods:</span></span>

- [<span data-ttu-id="e6698-230">自动应用标签策略</span><span class="sxs-lookup"><span data-stu-id="e6698-230">Auto-apply label policy</span></span>](apply-retention-labels-automatically.md)
- [<span data-ttu-id="e6698-231">Microsoft SharePoint Syntex 中的文档理解模型</span><span class="sxs-lookup"><span data-stu-id="e6698-231">Document understanding model for SharePoint Syntex</span></span>](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- <span data-ttu-id="e6698-232">[SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) 或 [Outlook 的默认标签](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="e6698-232">[Default label for SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) or [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>
- [<span data-ttu-id="e6698-233">Outlook 规则</span><span class="sxs-lookup"><span data-stu-id="e6698-233">Outlook rules</span></span>](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

<span data-ttu-id="e6698-234">对于标准保留标签（它们不会将项目标记为[记录或监管记录](records-management.md#records)）：</span><span class="sxs-lookup"><span data-stu-id="e6698-234">For standard retention labels (they don't mark items as a [record or regulatory record](records-management.md#records)):</span></span>

- <span data-ttu-id="e6698-235">管理员和最终用户可以手动更改或删除应用于内容的现有保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-235">Admins and end users can manually change or remove an existing retention label that's applied on content.</span></span> 

- <span data-ttu-id="e6698-236">当内容已应用保留标签时，现有标签不会自动删除或替换为另一个保留标签，但有一个可能的例外：现有标签已作为默认标签应用。</span><span class="sxs-lookup"><span data-stu-id="e6698-236">When content already has a retention label applied, the existing label won't be automatically removed or replaced by another retention label with one possible exception: The existing label was applied as a default label.</span></span>
    
    <span data-ttu-id="e6698-237">有关使用默认标签应用标签行为的详细信息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e6698-237">For more information about the label behavior when it's applied by using a default label:</span></span>
    - <span data-ttu-id="e6698-238">SharePoint 的默认标签：[对 SharePoint 使用默认标签时的标签行为](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="e6698-238">Default label for SharePoint: [Label behavior when you use a default label for SharePoint](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span></span>
    - <span data-ttu-id="e6698-239">Outlook 的默认标签：[将默认保留标签应用于 Outlook 文件夹](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="e6698-239">Default label for Outlook: [Applying a default retention label to an Outlook folder](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>

- <span data-ttu-id="e6698-240">如果有多个自动应用标签策略可以应用保留标签，并且内容满足多个策略的条件，则应用最旧的自动应用标签策略（按创建日期）的保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-240">If there are multiple auto-apply label policies that could apply a retention label, and content meets the conditions of multiple policies, the retention label for the oldest auto-apply label policy (by date created) is applied.</span></span>

<span data-ttu-id="e6698-241">当保留标签将项目标记为记录或管理记录时，这些标签不会自动更改。</span><span class="sxs-lookup"><span data-stu-id="e6698-241">When retention labels mark items as a record or a regulatory record, these labels are never automatically changed.</span></span> <span data-ttu-id="e6698-242">只有容器的管理员才能手动更改或删除将项目标记为记录而不是管理记录的保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-242">Only admins for the container can manually change or remove retention labels that mark items as a record, but not regulatory records.</span></span> <span data-ttu-id="e6698-243">有关详细信息，请参阅[比较对允许或阻止的操作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="e6698-243">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

#### <a name="monitoring-retention-labels"></a><span data-ttu-id="e6698-244">监视保留标签</span><span class="sxs-lookup"><span data-stu-id="e6698-244">Monitoring retention labels</span></span>

<span data-ttu-id="e6698-245">在 Microsoft 365 合规中心，使用 **“数据分类”** > **“概述”** 来监视保留标签在租户中的使用方式，并确定已标记项目的位置。</span><span class="sxs-lookup"><span data-stu-id="e6698-245">From the Microsoft 365 compliance center, use **Data classification** > **Overview** to monitor how your retention labels are being used in your tenant, and identify where your labeled items are located.</span></span> <span data-ttu-id="e6698-246">有关详细信息（包括重要先决条件），请参阅[了解你的数据 - 数据分类概述](data-classification-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e6698-246">For more information, including important prerequisites, see [Know your data - data classification overview](data-classification-overview.md).</span></span>

<span data-ttu-id="e6698-247">然后，你可以通过使用[内容资源管理器](data-classification-content-explorer.md)和[活动资源管理器](data-classification-activity-explorer.md)来深入了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="e6698-247">You can then drill down into details by using [content explorer](data-classification-content-explorer.md) and [activity explorer](data-classification-activity-explorer.md).</span></span>

> [!TIP]
><span data-ttu-id="e6698-248">请考虑使用其他的一些数据分类见解（如可训练分类器和敏感信息类型），帮助你识别可能需要保留或删除的内容，或者作为记录进行管理的内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-248">Consider using some of the other data classification insights, such as trainable classifiers and sensitive info types, to help you identify content that you might need to retain or delete, or manage as records.</span></span>

<span data-ttu-id="e6698-249">Office 365 安全与合规中心的保留标签概述信息与 **“信息管理政策”** > **“仪表板”** 中的概述信息相同，更加详细的信息可以在 **“信息管理政策”** > **“标签活动资源管理器”** 中找到。</span><span class="sxs-lookup"><span data-stu-id="e6698-249">The Office 365 Security & Compliance Center has the equivalent overview information for retention labels from **Information governance** > **Dashboard**, and more detailed information from **Information governance** > **Label activity explorer**.</span></span> <span data-ttu-id="e6698-250">有关从较旧版本的管理中心监视保留标签的更多信息，请参阅以下文档：</span><span class="sxs-lookup"><span data-stu-id="e6698-250">For more information about monitoring retention labels from this older admin center, see the following documentation:</span></span>
- [<span data-ttu-id="e6698-251">查看数据管理报告</span><span class="sxs-lookup"><span data-stu-id="e6698-251">View the data governance reports</span></span>](view-the-data-governance-reports.md)
- [<span data-ttu-id="e6698-252">使用标签分析查看标签使用情况</span><span class="sxs-lookup"><span data-stu-id="e6698-252">View label usage with label analytics</span></span>](label-analytics.md)
- [<span data-ttu-id="e6698-253">查看文档的标签活动</span><span class="sxs-lookup"><span data-stu-id="e6698-253">View label activity for documents</span></span>](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a><span data-ttu-id="e6698-254">使用“内容搜索”来查找所有带有特定保留标签的内容</span><span class="sxs-lookup"><span data-stu-id="e6698-254">Using Content Search to find all content with a specific retention label</span></span>

<span data-ttu-id="e6698-255">在将保留标签应用到内容后（无论是由用户应用还是自动应用），你都可以通过内容搜索来查找已经应用特定保留标签的所有项目。</span><span class="sxs-lookup"><span data-stu-id="e6698-255">After retention labels are applied to content, either by users or auto-applied, you can use content search to find all items that have a specific retention label applied.</span></span>

<span data-ttu-id="e6698-256">创建内容搜索时，选择“**保留标签**”条件，然后输入完整的保留标签名称或标签名称的一部分，并使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e6698-256">When you create a content search, choose the **Retention label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="e6698-257">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="e6698-257">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![保留标签条件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="e6698-259">比较保留策略和保留标签的功能</span><span class="sxs-lookup"><span data-stu-id="e6698-259">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="e6698-260">请使用下表来帮助你根据功能确定是使用保留策略还是保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-260">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="e6698-261">功能</span><span class="sxs-lookup"><span data-stu-id="e6698-261">Capability</span></span>|<span data-ttu-id="e6698-262">保留策略</span><span class="sxs-lookup"><span data-stu-id="e6698-262">Retention policy</span></span> |<span data-ttu-id="e6698-263">保留标签</span><span class="sxs-lookup"><span data-stu-id="e6698-263">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6698-264">保留设置可以是“保留后删除”、“仅保留”或“仅删除”</span><span class="sxs-lookup"><span data-stu-id="e6698-264">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="e6698-265">是</span><span class="sxs-lookup"><span data-stu-id="e6698-265">Yes</span></span> |<span data-ttu-id="e6698-266">是</span><span class="sxs-lookup"><span data-stu-id="e6698-266">Yes</span></span> |
|<span data-ttu-id="e6698-267">支持的工作负载：</span><span class="sxs-lookup"><span data-stu-id="e6698-267">Workloads supported:</span></span> <br /><span data-ttu-id="e6698-268">- Exchange</span><span class="sxs-lookup"><span data-stu-id="e6698-268">- Exchange</span></span> <br /><span data-ttu-id="e6698-269">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="e6698-269">- SharePoint</span></span> <br /><span data-ttu-id="e6698-270">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="e6698-270">- OneDrive</span></span> <br /><span data-ttu-id="e6698-271">- Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="e6698-271">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="e6698-272">- Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e6698-272">- Skype for Business</span></span> <br /><span data-ttu-id="e6698-273">- Teams</span><span class="sxs-lookup"><span data-stu-id="e6698-273">- Teams</span></span><br /><span data-ttu-id="e6698-274">- Yammer</span><span class="sxs-lookup"><span data-stu-id="e6698-274">- Yammer</span></span>|<br /> <span data-ttu-id="e6698-275">是</span><span class="sxs-lookup"><span data-stu-id="e6698-275">Yes</span></span> <br /> <span data-ttu-id="e6698-276">是</span><span class="sxs-lookup"><span data-stu-id="e6698-276">Yes</span></span> <br /> <span data-ttu-id="e6698-277">是</span><span class="sxs-lookup"><span data-stu-id="e6698-277">Yes</span></span> <br /> <span data-ttu-id="e6698-278">是</span><span class="sxs-lookup"><span data-stu-id="e6698-278">Yes</span></span> <br /> <span data-ttu-id="e6698-279">是</span><span class="sxs-lookup"><span data-stu-id="e6698-279">Yes</span></span> <br /> <span data-ttu-id="e6698-280">是</span><span class="sxs-lookup"><span data-stu-id="e6698-280">Yes</span></span> <br /> <span data-ttu-id="e6698-281">是</span><span class="sxs-lookup"><span data-stu-id="e6698-281">Yes</span></span> | <br /> <span data-ttu-id="e6698-282">是，但公用文件夹除外</span><span class="sxs-lookup"><span data-stu-id="e6698-282">Yes, except public folders</span></span> <br /> <span data-ttu-id="e6698-283">是</span><span class="sxs-lookup"><span data-stu-id="e6698-283">Yes</span></span> <br /> <span data-ttu-id="e6698-284">是</span><span class="sxs-lookup"><span data-stu-id="e6698-284">Yes</span></span> <br /> <span data-ttu-id="e6698-285">是</span><span class="sxs-lookup"><span data-stu-id="e6698-285">Yes</span></span> <br /> <span data-ttu-id="e6698-286">否</span><span class="sxs-lookup"><span data-stu-id="e6698-286">No</span></span> <br /> <span data-ttu-id="e6698-287">否</span><span class="sxs-lookup"><span data-stu-id="e6698-287">No</span></span> <br /> <span data-ttu-id="e6698-288">否</span><span class="sxs-lookup"><span data-stu-id="e6698-288">No</span></span> |
|<span data-ttu-id="e6698-289">自动应用保留</span><span class="sxs-lookup"><span data-stu-id="e6698-289">Retention applied automatically</span></span> | <span data-ttu-id="e6698-290">是</span><span class="sxs-lookup"><span data-stu-id="e6698-290">Yes</span></span> | <span data-ttu-id="e6698-291">是</span><span class="sxs-lookup"><span data-stu-id="e6698-291">Yes</span></span> |
|<span data-ttu-id="e6698-292">基于条件应用保留</span><span class="sxs-lookup"><span data-stu-id="e6698-292">Retention applied based on conditions</span></span> <br /> <span data-ttu-id="e6698-293">- 敏感信息类型、KQL 查询、可训练的分类器</span><span class="sxs-lookup"><span data-stu-id="e6698-293">- sensitive info types, KQL queries and keywords, trainable classifiers</span></span>| <span data-ttu-id="e6698-294">否</span><span class="sxs-lookup"><span data-stu-id="e6698-294">No</span></span> | <span data-ttu-id="e6698-295">是</span><span class="sxs-lookup"><span data-stu-id="e6698-295">Yes</span></span> |
|<span data-ttu-id="e6698-296">手动应用保留</span><span class="sxs-lookup"><span data-stu-id="e6698-296">Retention applied manually</span></span> | <span data-ttu-id="e6698-297">否</span><span class="sxs-lookup"><span data-stu-id="e6698-297">No</span></span> | <span data-ttu-id="e6698-298">是</span><span class="sxs-lookup"><span data-stu-id="e6698-298">Yes</span></span> |
|<span data-ttu-id="e6698-299">对最终用户显示 UI</span><span class="sxs-lookup"><span data-stu-id="e6698-299">UI presence for end users</span></span> | <span data-ttu-id="e6698-300">否</span><span class="sxs-lookup"><span data-stu-id="e6698-300">No</span></span> | <span data-ttu-id="e6698-301">是</span><span class="sxs-lookup"><span data-stu-id="e6698-301">Yes</span></span> |
|<span data-ttu-id="e6698-302">在内容移动时仍继续应用在内容上</span><span class="sxs-lookup"><span data-stu-id="e6698-302">Persists if the content is moved</span></span> | <span data-ttu-id="e6698-303">否</span><span class="sxs-lookup"><span data-stu-id="e6698-303">No</span></span> | <span data-ttu-id="e6698-304">是，在您的 Microsoft 365 租户中</span><span class="sxs-lookup"><span data-stu-id="e6698-304">Yes, within your Microsoft 365 tenant</span></span> |
|<span data-ttu-id="e6698-305">将项声明为记录</span><span class="sxs-lookup"><span data-stu-id="e6698-305">Declare item as a record</span></span>| <span data-ttu-id="e6698-306">否</span><span class="sxs-lookup"><span data-stu-id="e6698-306">No</span></span> | <span data-ttu-id="e6698-307">是</span><span class="sxs-lookup"><span data-stu-id="e6698-307">Yes</span></span> |
|<span data-ttu-id="e6698-308">从内容被标记或事件发生时开始计算保留期</span><span class="sxs-lookup"><span data-stu-id="e6698-308">Start the retention period when labeled or based on an event</span></span> | <span data-ttu-id="e6698-309">否</span><span class="sxs-lookup"><span data-stu-id="e6698-309">No</span></span> | <span data-ttu-id="e6698-310">是</span><span class="sxs-lookup"><span data-stu-id="e6698-310">Yes</span></span> |
|<span data-ttu-id="e6698-311">处置评审</span><span class="sxs-lookup"><span data-stu-id="e6698-311">Disposition review</span></span> | <span data-ttu-id="e6698-312">否</span><span class="sxs-lookup"><span data-stu-id="e6698-312">No</span></span>| <span data-ttu-id="e6698-313">是</span><span class="sxs-lookup"><span data-stu-id="e6698-313">Yes</span></span> |
|<span data-ttu-id="e6698-314">最长 7 年的处置证明</span><span class="sxs-lookup"><span data-stu-id="e6698-314">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="e6698-315">否</span><span class="sxs-lookup"><span data-stu-id="e6698-315">No</span></span> |<span data-ttu-id="e6698-316">是，当项被声明为记录时</span><span class="sxs-lookup"><span data-stu-id="e6698-316">Yes, when item is declared a record</span></span>|
|<span data-ttu-id="e6698-317">审核管理员活动</span><span class="sxs-lookup"><span data-stu-id="e6698-317">Audit admin activities</span></span>| <span data-ttu-id="e6698-318">是</span><span class="sxs-lookup"><span data-stu-id="e6698-318">Yes</span></span> | <span data-ttu-id="e6698-319">是</span><span class="sxs-lookup"><span data-stu-id="e6698-319">Yes</span></span>|
|<span data-ttu-id="e6698-320">识别遵循保留设置的项：</span><span class="sxs-lookup"><span data-stu-id="e6698-320">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="e6698-321">- 内容搜索</span><span class="sxs-lookup"><span data-stu-id="e6698-321">- Content Search</span></span> <br /> <span data-ttu-id="e6698-322">- 数据分类页、内容资源管理器、活动资源管理器</span><span class="sxs-lookup"><span data-stu-id="e6698-322">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="e6698-323">否</span><span class="sxs-lookup"><span data-stu-id="e6698-323">No</span></span> <br /> <span data-ttu-id="e6698-324">否</span><span class="sxs-lookup"><span data-stu-id="e6698-324">No</span></span> | <br /> <span data-ttu-id="e6698-325">必需</span><span class="sxs-lookup"><span data-stu-id="e6698-325">Yes</span></span> <br /> <span data-ttu-id="e6698-326">是</span><span class="sxs-lookup"><span data-stu-id="e6698-326">Yes</span></span>|

<span data-ttu-id="e6698-327">请注意，可以同时将保留策略和保留标签用作互补的保留方法。</span><span class="sxs-lookup"><span data-stu-id="e6698-327">Note that you can use both retention policies and retention labels as complementary retention methods.</span></span> <span data-ttu-id="e6698-328">例如：</span><span class="sxs-lookup"><span data-stu-id="e6698-328">For example:</span></span>

1. <span data-ttu-id="e6698-329">你创建并配置一个保留策略，以便在自最后一次修改内容起 5 年后自动删除内容，同时你将此策略应用于所有 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="e6698-329">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="e6698-330">你创建并配置一个保留标签来永久保留内容，同时你将此标签添加到发布到所有 OneDrive 帐户的标签策略中。</span><span class="sxs-lookup"><span data-stu-id="e6698-330">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="e6698-331">你向用户解释如何将此标签手动应用于特定文档，这些文档应排除在 5 年未修改后自动删除范围之外。</span><span class="sxs-lookup"><span data-stu-id="e6698-331">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="e6698-332">若要详细了解保留策略和保留标签是如何协同工作的，以及如何确定它们的合并结果，请参阅下一部分，其中介绍了保留原则和优先级。</span><span class="sxs-lookup"><span data-stu-id="e6698-332">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="e6698-333">保留原则或优先级</span><span class="sxs-lookup"><span data-stu-id="e6698-333">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="e6698-334">与保留标签不同，您可以对同一内容应用多个保留策略。</span><span class="sxs-lookup"><span data-stu-id="e6698-334">Unlike retention labels, you can apply more than one retention policy to the same content.</span></span> <span data-ttu-id="e6698-335">每个保留策略都可以导致保留操作和删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-335">Each retention policy can result in a retain action and a delete action.</span></span> <span data-ttu-id="e6698-336">此外，该商品还可能受到保留标签上的这些措施的约束。</span><span class="sxs-lookup"><span data-stu-id="e6698-336">Additionally, that item could also be subject to these actions from a retention label.</span></span>

<span data-ttu-id="e6698-337">在这种情况下，当项目可以经受可能彼此冲突的多个保留设置时，确定结果的优先顺序是什么？</span><span class="sxs-lookup"><span data-stu-id="e6698-337">In this scenario, when items can be subject to multiple retention settings that could conflict with one another, what takes precedence to determine the outcome?</span></span>

<span data-ttu-id="e6698-338">结果不是赢得单个保留策略或单个保留标签的结果，而是保留项目多长时间（如果适用）以及删除项目的时间（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="e6698-338">The outcome isn't which single retention policy or single retention label wins, but how long an item is retained (if applicable) and when an item is deleted (if applicable).</span></span> <span data-ttu-id="e6698-339">这两个操作是根据应用于项目的所有保留设置彼此独立计算的。</span><span class="sxs-lookup"><span data-stu-id="e6698-339">These two actions are calculated independently from each other, from all the retention settings applied to an item.</span></span>

<span data-ttu-id="e6698-340">例如，一个项目可能要受一个已配置为仅删除操作的保留策略的约束，而另一个则要配置为保留然后删除的保留策略。</span><span class="sxs-lookup"><span data-stu-id="e6698-340">For example, an item might be subject to one retention policy that is configured for a delete-only action, and another retention policy that is configured to retain and then delete.</span></span> <span data-ttu-id="e6698-341">因此，此项只有一个保留操作和两个删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-341">Consequently, this item has just one retain action but two delete actions.</span></span> <span data-ttu-id="e6698-342">保留和删除操作可能彼此冲突，并且这两个删除操作的日期可能冲突。</span><span class="sxs-lookup"><span data-stu-id="e6698-342">The retention and deletion actions could be in conflict with one another and the two deletion actions might have a conflicting date.</span></span> <span data-ttu-id="e6698-343">为了得出结果，你必须运用保留原则。</span><span class="sxs-lookup"><span data-stu-id="e6698-343">To work out the outcome, you must apply the principles of retention.</span></span>

<span data-ttu-id="e6698-344">概括来说，可以确定的是，保留始终优先于删除，然后是最长保留期胜出。</span><span class="sxs-lookup"><span data-stu-id="e6698-344">At a high level, you can be assured that retention always takes precedence over deletion, and the longest retention period wins.</span></span> <span data-ttu-id="e6698-345">这两个简单的规则总是决定一个项目将保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="e6698-345">These two simple rules always decide how long an item will be retained.</span></span>

<span data-ttu-id="e6698-346">还有其他一些因素决定何时删除项目，其中包括保留标签中的删除操作始终优先于保留策略中的删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-346">There are a few more factors that determine when an item will be deleted, which include the delete action from a retention label always takes precedence over the delete action from a retention policy.</span></span>

<span data-ttu-id="e6698-347">使用以下流程了解单个项目的保留和删除结果，其中每个级别从上到下都充当冲突平局。</span><span class="sxs-lookup"><span data-stu-id="e6698-347">Use the following flow to understand the retention and deletion outcomes for a single item, where each level acts as a tie-breaker for conflicts, from top to bottom.</span></span> <span data-ttu-id="e6698-348">如果结果由第一个级别决定，由于没有进一步冲突，则不需要再前进到下一个级别，等等。</span><span class="sxs-lookup"><span data-stu-id="e6698-348">If the outcome is determined by the first level because there are no further conflicts, there's no need to progress to the next level, and so on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6698-349">如果您使用的是保留标签：在使用此流程确定同一项目上多个保留设置的结果之前，请确保您知道[应用了哪个保留标签](#only-one-retention-label-at-a-time)。</span><span class="sxs-lookup"><span data-stu-id="e6698-349">If you are using retention labels: Before using this flow to determine the outcome of multiple retention settings on the same item, make sure you know [which retention label is applied](#only-one-retention-label-at-a-time).</span></span>

![保留原则关系图](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="e6698-351">有关四种不同级别的说明：</span><span class="sxs-lookup"><span data-stu-id="e6698-351">Explanation for the four different levels:</span></span>
  
1. <span data-ttu-id="e6698-352">**保留优先于删除。**</span><span class="sxs-lookup"><span data-stu-id="e6698-352">**Retention wins over deletion.**</span></span> <span data-ttu-id="e6698-353">当内容也具有保留设置以保留它时，它不会被永久删除。</span><span class="sxs-lookup"><span data-stu-id="e6698-353">Content won't be permanently deleted when it also has retention settings to retain it.</span></span>  
    
    <span data-ttu-id="e6698-354">示例：电子邮件必须遵循Exchange的保留策略，该策略配置为在三年后删除项目，并且还应用了保留标签，该标签被配置为可以保留项目五年。</span><span class="sxs-lookup"><span data-stu-id="e6698-354">Example: An email message is subject to a retention policy for Exchange that is configured to delete items after three years and it also has a retention label applied that is configured to retain items for five years.</span></span>
    
    <span data-ttu-id="e6698-355">电子邮件将保留五年，因为此保留操作优先于删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-355">The email message is retained for five years because this retention action takes precedence over deletion.</span></span> <span data-ttu-id="e6698-356">由于推迟了删除操作，该电子邮件在五年结束时被删除。</span><span class="sxs-lookup"><span data-stu-id="e6698-356">The email message is deleted at the end of the five years because of the deferred delete action.</span></span>

2. <span data-ttu-id="e6698-357">**优选最长的保留期。**</span><span class="sxs-lookup"><span data-stu-id="e6698-357">**The longest retention period wins.**</span></span> <span data-ttu-id="e6698-358">如果内容遵循多个在不同时间段内保留内容的保留设置，内容会一直保留到最长保留期结束。</span><span class="sxs-lookup"><span data-stu-id="e6698-358">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
    <span data-ttu-id="e6698-359">示例：Marketing SharePoint网站中的文档受两个保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="e6698-359">Example: Documents in the Marketing SharePoint site are subject to two retention policies.</span></span> <span data-ttu-id="e6698-360">为所有SharePoint网站配置第一个保留策略，以将项目保留五年。</span><span class="sxs-lookup"><span data-stu-id="e6698-360">The first retention policy is configured for all SharePoint sites to retain items for five years.</span></span> <span data-ttu-id="e6698-361">为特定的SharePoint网站配置第二个保留策略，以将项目保留十年。</span><span class="sxs-lookup"><span data-stu-id="e6698-361">The second retention policy is configured for specific SharePoint sites to retain items for ten years.</span></span>
    
    <span data-ttu-id="e6698-362">该Marketing SharePoint网站中的文档将保留十年，因为这是最长的保留期。</span><span class="sxs-lookup"><span data-stu-id="e6698-362">Documents in this Marketing SharePoint site are retained for ten years because that's the longest retention period.</span></span>

3. <span data-ttu-id="e6698-363">**显式包含优先于隐式包含。**</span><span class="sxs-lookup"><span data-stu-id="e6698-363">**Explicit wins over implicit.**</span></span> <span data-ttu-id="e6698-364">适用于确定何时删除项目：</span><span class="sxs-lookup"><span data-stu-id="e6698-364">Applicable to determine when items will be deleted:</span></span> 
    
    1. <span data-ttu-id="e6698-365">与保留策略相比，保留标签（无论如何应用）都提供了显式保留，因为保留设置将应用于单个项目，而不是从容器隐式分配。</span><span class="sxs-lookup"><span data-stu-id="e6698-365">A retention label (however it was applied) provides explicit retention in comparison with retention policies, because the retention settings are applied to an individual item rather than implicitly assigned from a container.</span></span> <span data-ttu-id="e6698-366">这意味着从保留标签删除操作始终优先于从任何保留策略删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-366">This means that a delete action from a retention label always takes precedence over a delete action from any retention policy.</span></span>
        
        <span data-ttu-id="e6698-367">示例：文档受两个保留策略的约束，删除策略分别为5年和10年，以及保留标签的删除策略为7年。</span><span class="sxs-lookup"><span data-stu-id="e6698-367">Example: A document is subject to two retention policies that have a delete action of five years and ten years respectively, and also a retention label that has a delete action of seven years.</span></span>
        
        <span data-ttu-id="e6698-368">七年后删除文档，因为保留标签的删除操作具有优先权。</span><span class="sxs-lookup"><span data-stu-id="e6698-368">The document is deleted after seven years because the delete action from the retention label takes precedence.</span></span>
    
    2. <span data-ttu-id="e6698-369">仅当具有保留策略时：如果某个位置的保留策略的作用域是使用包含配置（例如Exchange电子邮件的特定用户），则该保留策略优先于同一位置的无范围保留策略。</span><span class="sxs-lookup"><span data-stu-id="e6698-369">When you have retention policies only: If a retention policy for a location is scoped to use an include configuration (such as specific users for Exchange email) that retention policy takes precedence over unscoped retention policies for the same location.</span></span>
        
        <span data-ttu-id="e6698-370">不受限制的保留策略是在不指定特定实例的情况下选择位置的位置。</span><span class="sxs-lookup"><span data-stu-id="e6698-370">An unscoped retention policy is where a location is selected without specifying specific instances.</span></span> <span data-ttu-id="e6698-371">例如，**Exchange电子邮件** 和默认设置 **“所有收件人”** 是不受范围限制的保留策略。</span><span class="sxs-lookup"><span data-stu-id="e6698-371">For example, **Exchange email** and the default setting of **All recipients** is an unscoped retention policy.</span></span> <span data-ttu-id="e6698-372">或者，**SharePoint网站** 和 **“所有网站”** 的默认设置。</span><span class="sxs-lookup"><span data-stu-id="e6698-372">Or, **SharePoint sites** and the default setting of **All sites**.</span></span> <span data-ttu-id="e6698-373">在对保留策略进行范围划分时，它们在此级别具有相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="e6698-373">When retention policies are scoped, they have equal precedence at this level.</span></span>
        
        <span data-ttu-id="e6698-374">示例1：电子邮件受两个保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="e6698-374">Example 1: An email message is subject to two retention policies.</span></span> <span data-ttu-id="e6698-375">第一个保留策略不受范围限制，并在十年后删除项目。</span><span class="sxs-lookup"><span data-stu-id="e6698-375">The first retention policy is unscoped and deletes items after ten years.</span></span> <span data-ttu-id="e6698-376">第二个保留策略适用于特定邮箱，并在五年后删除项目。</span><span class="sxs-lookup"><span data-stu-id="e6698-376">The second retention policy is scoped to specific mailboxes and deletes items after five years.</span></span>
        
        <span data-ttu-id="e6698-377">五年后将删除电子邮件，因为有范围的保留策略中的删除操作优先于无范围的保留策略。</span><span class="sxs-lookup"><span data-stu-id="e6698-377">The email message is deleted after five years because the deletion action from the scoped retention policy takes precedence over the unscoped retention policy.</span></span>
        
        <span data-ttu-id="e6698-378">示例2：用户的OneDrive帐户中的文档受两个保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="e6698-378">Example 2: A document in a user's OneDrive account is subject to two retention policies.</span></span> <span data-ttu-id="e6698-379">第一个保留策略的范围包括该用户的OneDrive帐户，并在10年后执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-379">The first retention policy is scoped to include this user's OneDrive account and has a delete action after 10 years.</span></span> <span data-ttu-id="e6698-380">第二个保留策略的范围包括该用户的OneDrive帐户，并且七年后将执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-380">The second retention policy is scoped to include this user's OneDrive account and has a delete action after seven years.</span></span>
        
        <span data-ttu-id="e6698-381">由于两个保留策略都已确定范围，因此无法在此级别确定何时删除此文档。</span><span class="sxs-lookup"><span data-stu-id="e6698-381">When this document will be deleted can't be determined at this level because both retention policies are scoped.</span></span>

4. <span data-ttu-id="e6698-382">**最短删除期优先。**</span><span class="sxs-lookup"><span data-stu-id="e6698-382">**The shortest deletion period wins.**</span></span> <span data-ttu-id="e6698-383">适用于确定何时从保留策略中删除项目以及从上一级别无法解决结果：在最短保留期结束时删除内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-383">Applicable to determine when items will be deleted from retention policies and the outcome couldn't be resolved from the previous level: Content is deleted at the end of the shortest retention period.</span></span>
    
    <span data-ttu-id="e6698-384">示例：用户的OneDrive帐户中的文档受两个保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="e6698-384">Example: A document in a user's OneDrive account is subject to two retention policies.</span></span> <span data-ttu-id="e6698-385">第一个保留策略的范围包括该用户的OneDrive帐户，并在10年后执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-385">The first retention policy is scoped to include this user's OneDrive account and has a delete action after 10 years.</span></span> <span data-ttu-id="e6698-386">第二个保留策略的范围包括该用户的OneDrive帐户，并且七年后将执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-386">The second retention policy is scoped to include this user's OneDrive account and has a delete action after seven years.</span></span>
    
    <span data-ttu-id="e6698-387">七年后将删除此文档，因为这是这两个范围的保留策略的最短保留期。</span><span class="sxs-lookup"><span data-stu-id="e6698-387">This document will be deleted after seven years because that's the shortest retention period for these two scoped retention policies.</span></span>

<span data-ttu-id="e6698-388">请注意，受到电子数据展示保留的项目也属于保留的第一原则； 它们不能被任何保留策略或保留标签删除。</span><span class="sxs-lookup"><span data-stu-id="e6698-388">Note that items subject to eDiscovery hold also fall under the first principle of retention; they cannot be deleted by any retention policy or retention label.</span></span> <span data-ttu-id="e6698-389">解除保留后，保留原则将继续适用于它们。</span><span class="sxs-lookup"><span data-stu-id="e6698-389">When that hold is released, the principles of retention continue to apply to them.</span></span> <span data-ttu-id="e6698-390">例如，它们然后可能会受到未期满的保留期限或推迟的删除操作。</span><span class="sxs-lookup"><span data-stu-id="e6698-390">For example, they could then be subject to an unexpired retention period or a deferred delete action.</span></span>

<span data-ttu-id="e6698-391">结合了保留和删除操作的更复杂的示例：</span><span class="sxs-lookup"><span data-stu-id="e6698-391">More complex examples that combine retain and delete actions:</span></span>

1. <span data-ttu-id="e6698-392">一个项目已应用以下保留设置：</span><span class="sxs-lookup"><span data-stu-id="e6698-392">An item has the following retention settings applied to it:</span></span>
    
    - <span data-ttu-id="e6698-393">五年后只能删除的保留政策</span><span class="sxs-lookup"><span data-stu-id="e6698-393">A retention policy for delete-only after five years</span></span>
    - <span data-ttu-id="e6698-394">保留政策，保留三年然后删除</span><span class="sxs-lookup"><span data-stu-id="e6698-394">A retention policy that retains for three years and then deletes</span></span>
    - <span data-ttu-id="e6698-395">仅保留七年的保留标签</span><span class="sxs-lookup"><span data-stu-id="e6698-395">A retention label that retains-only for seven years</span></span>
    
    <span data-ttu-id="e6698-396">**结果**：该项目保留7年，因为保留优先于删除，并且7年是最长的保留期。</span><span class="sxs-lookup"><span data-stu-id="e6698-396">**Outcome**: The item is retained for seven years because retention takes precedence over deletion and seven years is the longest retention period.</span></span> <span data-ttu-id="e6698-397">在此保留期结束时，由于在保留项目时推迟了对保留策略的删除操作，因此删除了该项目。</span><span class="sxs-lookup"><span data-stu-id="e6698-397">At the end of this retention period, the item is deleted because of the delete action from the retention policies that was deferred while the item was retained.</span></span>
    
    <span data-ttu-id="e6698-398">尽管两种保留策略的删除操作日期不同，但是最早可以删除的项目是最长保留期（比两个删除日期长）的结束。</span><span class="sxs-lookup"><span data-stu-id="e6698-398">Although the two retention policies have different dates for the delete actions, the earliest the item can be deleted is at the end of the longest retention period, which is longer than both deletion dates.</span></span> <span data-ttu-id="e6698-399">在本示例中，删除日期没有冲突需要解决，因此所有冲突都在第二个级别解决。</span><span class="sxs-lookup"><span data-stu-id="e6698-399">In this example, there is no conflict to resolve for the deletion dates so all conflicts are resolved by the second level.</span></span>

2.  <span data-ttu-id="e6698-400">一个项目已应用以下保留设置：</span><span class="sxs-lookup"><span data-stu-id="e6698-400">An item has the following retention settings applied to it:</span></span>
    
    - <span data-ttu-id="e6698-401">不受限制的保留策略，仅在十年后删除</span><span class="sxs-lookup"><span data-stu-id="e6698-401">An unscoped retention policy that deletes-only after ten years</span></span>
    - <span data-ttu-id="e6698-402">有范围的保留策略，可以保留五年然后删除</span><span class="sxs-lookup"><span data-stu-id="e6698-402">A scoped retention policy that retains for five years and then deletes</span></span>
    - <span data-ttu-id="e6698-403">保留标签，保留三年，然后删除</span><span class="sxs-lookup"><span data-stu-id="e6698-403">A retention label that retains for three years and then deletes</span></span>
    
    <span data-ttu-id="e6698-404">**结果**：该项目将保留五年，因为这是最长的保留期。</span><span class="sxs-lookup"><span data-stu-id="e6698-404">**Outcome**: The item is retained for five years because that's the longest retention period.</span></span> <span data-ttu-id="e6698-405">在该保留期结束时，由于从保留标签时推迟了三年的保留标签删除操作，删除了该项目。</span><span class="sxs-lookup"><span data-stu-id="e6698-405">At the end of that retention period, the item is deleted because of the delete action of three years from the retention label that was deferred while the item was retained.</span></span> <span data-ttu-id="e6698-406">从保留标签中删除优先于从所有保留策略中删除。</span><span class="sxs-lookup"><span data-stu-id="e6698-406">Deletion from retention labels takes precedence over deletion from all retention policies.</span></span> <span data-ttu-id="e6698-407">在此示例中，所有冲突都由第三个级别解决。</span><span class="sxs-lookup"><span data-stu-id="e6698-407">In this example, all conflicts are resolved by the third level.</span></span>

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a><span data-ttu-id="e6698-408">使用保存锁来限制对策略的更改</span><span class="sxs-lookup"><span data-stu-id="e6698-408">Use Preservation Lock to restrict changes to policies</span></span>

<span data-ttu-id="e6698-409">某些组织可能需要遵从由监管机构定义的规则，如美国证券交易委员会 (SEC) 规则 17a-4，该规则要求在启用保留策略之后，不得关闭该策略或降低其限制。</span><span class="sxs-lookup"><span data-stu-id="e6698-409">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a policy for retention is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="e6698-410">保存锁可确保组织符合此类监管要求，因为它可以锁定保留策略或保留标签策略，因此任何人（包括管理员）都无法关闭该策略、删除该策略或降低其限制性。</span><span class="sxs-lookup"><span data-stu-id="e6698-410">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy or retention label policy so that no one—including an administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="e6698-411">在创建保留策略或保留标签策略后应用保存锁。</span><span class="sxs-lookup"><span data-stu-id="e6698-411">You apply Preservation Lock after the retention policy or retention label policy is created.</span></span> <span data-ttu-id="e6698-412">有关更多信息和说明，请参阅 [使用保存锁来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="e6698-412">For more information and instructions, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="releasing-a-policy-for-retention"></a><span data-ttu-id="e6698-413">发布保留策略</span><span class="sxs-lookup"><span data-stu-id="e6698-413">Releasing a policy for retention</span></span>

<span data-ttu-id="e6698-414">如果你的保留策略没有保留锁，你可以随时删除你的策略，这将有效地关闭之前应用的保留设置。</span><span class="sxs-lookup"><span data-stu-id="e6698-414">Providing your policies for retention don't have a Preservation Lock, you can delete your policies at any time, which effectively turns off the previously applied retention settings.</span></span> <span data-ttu-id="e6698-415">你也可以保留该策略，但将位置状态更改为关闭。</span><span class="sxs-lookup"><span data-stu-id="e6698-415">You can also keep the policy but change the location status to off.</span></span>
 
<span data-ttu-id="e6698-416">当你执行上述任一操作时，保留在保存库中的任何 SharePoint 或 OneDrive 内容都不会立即永久删除。</span><span class="sxs-lookup"><span data-stu-id="e6698-416">When you do either of these actions, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="e6698-417">相反，为了防止意外的数据丢失，我们设置了 30 天的宽限期。在此期间，相应策略的内容不会在保留库中到期，所以你可以根据需要从其中还原任何内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-417">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="e6698-418">此外，在宽限期内无法手动删除此内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-418">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="e6698-419">你可以在宽限期内将位置状态更改为启用，并且不会删除该策略的内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-419">You can change the location status back to on during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="e6698-420">SharePoint 和 OneDrive 中的此 30 天宽限期对应于 Exchange 中的 30 天延迟保留。</span><span class="sxs-lookup"><span data-stu-id="e6698-420">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="e6698-421">有关详细信息，请参阅[管理延迟保留的邮箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。</span><span class="sxs-lookup"><span data-stu-id="e6698-421">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="auditing-retention-configuration"></a><span data-ttu-id="e6698-422">审核保留配置</span><span class="sxs-lookup"><span data-stu-id="e6698-422">Auditing retention configuration</span></span>

<span data-ttu-id="e6698-423">[启用审核后](turn-audit-log-search-on-or-off.md)，管理员针对保留政策和保留标签的操作会被保存到审核日志中。</span><span class="sxs-lookup"><span data-stu-id="e6698-423">Administrator actions for retention policies and retention labels are saved to the audit log when [auditing is enabled](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="e6698-424">例如，创建、配置或删除保留政策或标签时会创建审核事件。</span><span class="sxs-lookup"><span data-stu-id="e6698-424">For example, an audit event is created when a retention policy or label is created, configured, or deleted.</span></span> <span data-ttu-id="e6698-425">如需完整的列表，请参阅[保留策略和保留标签活动](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。</span><span class="sxs-lookup"><span data-stu-id="e6698-425">For the full list, see [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="e6698-426">用于保留策略和保留标签的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e6698-426">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="e6698-427">若要使用保留 cmdlet，必须先[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e6698-427">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="e6698-428">然后，使用以下任何 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e6698-428">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="e6698-429">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e6698-429">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="e6698-430">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e6698-430">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="e6698-431">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e6698-431">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="e6698-432">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="e6698-432">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="e6698-433">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="e6698-433">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="e6698-434">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="e6698-434">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="e6698-435">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e6698-435">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="e6698-436">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e6698-436">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="e6698-437">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e6698-437">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="e6698-438">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="e6698-438">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="e6698-439">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e6698-439">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="e6698-440">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e6698-440">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="e6698-441">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e6698-441">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="e6698-442">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="e6698-442">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a><span data-ttu-id="e6698-443">何时使用保留策略和保留标签或电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="e6698-443">When to use retention policies and retention labels or eDiscovery holds</span></span>

<span data-ttu-id="e6698-444">虽然保留设置和[电子文件展示案列创建的保留](create-ediscovery-holds.md)都可以防止数据被永久删除，它们是针对不同情况设计的。</span><span class="sxs-lookup"><span data-stu-id="e6698-444">Although retention settings and [holds that you create with an eDiscovery case](create-ediscovery-holds.md) can both prevent data from being permanently deleted, they are designed for different scenarios.</span></span> <span data-ttu-id="e6698-445">为了帮助你了解差异并决定使用哪个，请使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="e6698-445">To help you understand the differences and decide which to use, use the following guidance:</span></span>

- <span data-ttu-id="e6698-446">在保留策略和保留标签中指定的保留设置旨在用于长期信息管理策略，以保留或删除符合法规要求的数据。</span><span class="sxs-lookup"><span data-stu-id="e6698-446">Retention settings that you specify in retention policies and retention labels are designed for a long-term information governance strategy to retain or delete data for compliance requirements.</span></span> <span data-ttu-id="e6698-447">通常范围很广，主要重点是位置和内容，而不是单个用户。</span><span class="sxs-lookup"><span data-stu-id="e6698-447">The scope is usually broad with the main focus being the location and content rather than individual users.</span></span> <span data-ttu-id="e6698-448">保留期的开始和结束是可配置的，可以选择自动删除内容，无需其他管理员干预。</span><span class="sxs-lookup"><span data-stu-id="e6698-448">The start and end of the retention period is configurable, with the option to automatically delete content without additional administrator intervention.</span></span>

- <span data-ttu-id="e6698-449">电子数据展示保留（核心电子数据展示或高级电子数据展示案例）的设计期限有限，可以保存数据以进行法律调查。</span><span class="sxs-lookup"><span data-stu-id="e6698-449">Holds for eDiscovery (either Core eDiscovery or Advanced eDiscovery cases) are designed for a limited duration to preserve data for a legal investigation.</span></span> <span data-ttu-id="e6698-450">范围是特定的，重点是已识别用户拥有的内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-450">The scope is specific with the focus being content owned by identified users.</span></span> <span data-ttu-id="e6698-451">保留期的开始和结束是不可配置的，但取决于单个管理员的操作，如果保留被释放，则无法选择自动删除内容。</span><span class="sxs-lookup"><span data-stu-id="e6698-451">The start and end of the preservation period isn't configurable but dependent on individual administrator actions, without an option to automatically delete content when the hold is released.</span></span>

<span data-ttu-id="e6698-452">比较保留与电子数据展示保留的摘要：</span><span class="sxs-lookup"><span data-stu-id="e6698-452">Summary to compare retention with holds:</span></span>

|<span data-ttu-id="e6698-453">注意事项</span><span class="sxs-lookup"><span data-stu-id="e6698-453">Consideration</span></span>|<span data-ttu-id="e6698-454">保留</span><span class="sxs-lookup"><span data-stu-id="e6698-454">Retention</span></span> |<span data-ttu-id="e6698-455">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="e6698-455">eDiscovery holds</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6698-456">业务需求：</span><span class="sxs-lookup"><span data-stu-id="e6698-456">Business need:</span></span> |<span data-ttu-id="e6698-457">合规性</span><span class="sxs-lookup"><span data-stu-id="e6698-457">Compliance</span></span> |<span data-ttu-id="e6698-458">法律</span><span class="sxs-lookup"><span data-stu-id="e6698-458">Legal</span></span> |
|<span data-ttu-id="e6698-459">时间范围：</span><span class="sxs-lookup"><span data-stu-id="e6698-459">Time scope:</span></span> |<span data-ttu-id="e6698-460">长期</span><span class="sxs-lookup"><span data-stu-id="e6698-460">Long-term</span></span> |<span data-ttu-id="e6698-461">短期</span><span class="sxs-lookup"><span data-stu-id="e6698-461">Short-term</span></span> |
|<span data-ttu-id="e6698-462">焦点：</span><span class="sxs-lookup"><span data-stu-id="e6698-462">Focus:</span></span> |<span data-ttu-id="e6698-463">广泛、基于内容</span><span class="sxs-lookup"><span data-stu-id="e6698-463">Broad, content-based</span></span> |<span data-ttu-id="e6698-464">特定、基于用户</span><span class="sxs-lookup"><span data-stu-id="e6698-464">Specific, user-based</span></span> |
|<span data-ttu-id="e6698-465">开始和结束日期可配置：</span><span class="sxs-lookup"><span data-stu-id="e6698-465">Start and end date configurable:</span></span> |<span data-ttu-id="e6698-466">是</span><span class="sxs-lookup"><span data-stu-id="e6698-466">Yes</span></span> |<span data-ttu-id="e6698-467">否</span><span class="sxs-lookup"><span data-stu-id="e6698-467">No</span></span> |
|<span data-ttu-id="e6698-468">内容删除：</span><span class="sxs-lookup"><span data-stu-id="e6698-468">Content deletion:</span></span> |<span data-ttu-id="e6698-469">是（可选）</span><span class="sxs-lookup"><span data-stu-id="e6698-469">Yes (optional)</span></span> |<span data-ttu-id="e6698-470">否</span><span class="sxs-lookup"><span data-stu-id="e6698-470">No</span></span> |
|<span data-ttu-id="e6698-471">管理开销：</span><span class="sxs-lookup"><span data-stu-id="e6698-471">Administrative overheads:</span></span> |<span data-ttu-id="e6698-472">低</span><span class="sxs-lookup"><span data-stu-id="e6698-472">Low</span></span> |<span data-ttu-id="e6698-473">高</span><span class="sxs-lookup"><span data-stu-id="e6698-473">High</span></span> |

<span data-ttu-id="e6698-474">如果内容遵循保留设置和电子数据展示保留，则保存电子数据展示保留的内容始终具有优先权。</span><span class="sxs-lookup"><span data-stu-id="e6698-474">If content is subject to both retention settings and an eDiscovery hold, preserving content for the eDiscovery hold always takes precedence.</span></span> <span data-ttu-id="e6698-475">这样，[保留原则](#the-principles-of-retention-or-what-takes-precedence)扩展到电子数据展示保留，因为它们保留数据，直到管理员手动释放保留为止。</span><span class="sxs-lookup"><span data-stu-id="e6698-475">In this way, the [principles of retention](#the-principles-of-retention-or-what-takes-precedence) expand to eDiscovery holds because they preserve data until an administrator manually releases the hold.</span></span> <span data-ttu-id="e6698-476">但是，尽管有此优先顺序，但不要将电子数据展示保留用于长期信息治理。</span><span class="sxs-lookup"><span data-stu-id="e6698-476">However, despite this precedence, don't use eDiscovery holds for long-term information governance.</span></span> <span data-ttu-id="e6698-477">如果担心自动删除数据，则可以将保留设置配置为永久保留项目，或将[处置审查](disposition.md#disposition-reviews)与保留标签一起使用。</span><span class="sxs-lookup"><span data-stu-id="e6698-477">If you are concerned about automatic deletion of data, you can configure retention settings to retain items forever, or use [disposition review](disposition.md#disposition-reviews) with retention labels.</span></span>

<span data-ttu-id="e6698-478">如果你使用的是旧的电子数据展示工具来保留数据，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="e6698-478">If you are using older eDiscovery tools to preserve data, see the following resources:</span></span>

- <span data-ttu-id="e6698-479">Exchange:</span><span class="sxs-lookup"><span data-stu-id="e6698-479">Exchange:</span></span> 
    - [<span data-ttu-id="e6698-480">就地保留和诉讼保留</span><span class="sxs-lookup"><span data-stu-id="e6698-480">In-Place Hold and Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=846124)
    - [<span data-ttu-id="e6698-481">如何识别为 Exchange Online 邮箱设置的保留类型</span><span class="sxs-lookup"><span data-stu-id="e6698-481">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)

- <span data-ttu-id="e6698-482">SharePoint 和 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="e6698-482">SharePoint and OneDrive:</span></span> 
    - [<span data-ttu-id="e6698-483">在电子数据展示中心将内容添加到事例并将源就地保留</span><span class="sxs-lookup"><span data-stu-id="e6698-483">Add content to a case and place sources on hold in the eDiscovery Center</span></span>](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)

- [<span data-ttu-id="e6698-484">旧版电子数据展示工具的停用</span><span class="sxs-lookup"><span data-stu-id="e6698-484">Retirement of legacy eDiscovery tools</span></span>](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="e6698-485">使用保留策略和保留标签，而不是旧功能</span><span class="sxs-lookup"><span data-stu-id="e6698-485">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="e6698-486">如果需要在 Microsoft 365 中主动保留或删除内容来实现信息管理，建议使用保留策略和保留标签，而不是以下旧功能。</span><span class="sxs-lookup"><span data-stu-id="e6698-486">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span>

<span data-ttu-id="e6698-487">如果当前使用这些旧功能，可以继续将它们与保留策略和保留标签并行使用。</span><span class="sxs-lookup"><span data-stu-id="e6698-487">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="e6698-488">但我们建议今后使用保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="e6698-488">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="e6698-489">它们为你提供了在 Microsoft 365 中集中管理内容保留和删除的单一机制。</span><span class="sxs-lookup"><span data-stu-id="e6698-489">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="e6698-490">**Exchange Online 中的早期功能：**</span><span class="sxs-lookup"><span data-stu-id="e6698-490">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="e6698-491">[保留标记和保留策略](https://go.microsoft.com/fwlink/?linkid=846125)，亦称为[邮件传递记录管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="e6698-491">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>

<span data-ttu-id="e6698-492">**SharePoint 和 OneDrive 中的早期功能：**</span><span class="sxs-lookup"><span data-stu-id="e6698-492">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="e6698-493">[文档删除策略](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff)（仅删除）</span><span class="sxs-lookup"><span data-stu-id="e6698-493">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="e6698-494">[配置就地记录管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a)（仅限保留）</span><span class="sxs-lookup"><span data-stu-id="e6698-494">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="e6698-495">[使用网站关闭和删除策略](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="e6698-495">[Use policies for site closure and deletion](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="e6698-496">[信息管理策略](intro-to-info-mgmt-policies.md)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="e6698-496">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="e6698-497">如果已将 SharePoint 网站配置为应用保留列表或库的内容的内容类型策略或信息管理策略，则这些策略会在保留策略生效时被忽略。</span><span class="sxs-lookup"><span data-stu-id="e6698-497">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="e6698-498">相关信息</span><span class="sxs-lookup"><span data-stu-id="e6698-498">Related information</span></span>

- [<span data-ttu-id="e6698-499">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="e6698-499">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="e6698-500">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="e6698-500">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="e6698-501">有助于你满足信息治理和记录管理监管要求的资源</span><span class="sxs-lookup"><span data-stu-id="e6698-501">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)

## <a name="configuration-guidance"></a><span data-ttu-id="e6698-502">配置指南</span><span class="sxs-lookup"><span data-stu-id="e6698-502">Configuration guidance</span></span>

<span data-ttu-id="e6698-503">如果已准备好创建保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e6698-503">If you are ready to create retention policies, see [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="e6698-504">若要创建和应用保留标签，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e6698-504">To create and apply retention labels:</span></span>
- [<span data-ttu-id="e6698-505">创建保留标签并在应用中应用它们</span><span class="sxs-lookup"><span data-stu-id="e6698-505">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="e6698-506">自动向内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="e6698-506">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

