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
ms.openlocfilehash: 9337bddd87dd24d42b4d06fe77225901701cbdee
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149174"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="1fca5-103">了解保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="1fca5-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="1fca5-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="1fca5-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="1fca5-p101">如果在 Teams 中看到保留策略相关消息或对应用中的保留标签存疑，请联系 IT 部门，了解有关如何配置保留策略和保留标签的信息。同时，以下文章可能有帮助：</span><span class="sxs-lookup"><span data-stu-id="1fca5-p101">If you're seeing messages about retention policies in Teams or have questions about retention labels in your apps, contact your IT department for information about how they have been configured for you. In the meantime, you might find the following articles helpful:</span></span>
> -  [<span data-ttu-id="1fca5-107">有关保留策略的 Teams 消息</span><span class="sxs-lookup"><span data-stu-id="1fca5-107">Teams messages about retention policies</span></span>](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)
> - [<span data-ttu-id="1fca5-108">对 SharePoint 或 OneDrive 中的文件应用保留标签</span><span class="sxs-lookup"><span data-stu-id="1fca5-108">Apply retention labels to files in SharePoint or OneDrive</span></span>](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df)
>
> <span data-ttu-id="1fca5-109">本页上的信息适用于出于合规性原因可创建保留策略和保留标签的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="1fca5-109">The information on this page is for IT administrators who can create retention policies and retention labels for compliance reasons.</span></span>

<span data-ttu-id="1fca5-p102">对于大多数组织，数据量和数据复杂性每天都在增加 — 包括电子邮件、文档、即时消息等。有效管理或管理此类信息非常重要，因为要：</span><span class="sxs-lookup"><span data-stu-id="1fca5-p102">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>

- <span data-ttu-id="1fca5-112">**主动遵守规定至少必须在一段时间内保留内容的行业法规和内部策略**：例如，《萨班斯-奥克斯利法案》规定，必须保留特定类型的内容七年。</span><span class="sxs-lookup"><span data-stu-id="1fca5-112">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span>

- <span data-ttu-id="1fca5-113">**降低发生诉讼或出现安全漏洞的风险**：通过永久删除不再需要保留的旧内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-113">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span>

- <span data-ttu-id="1fca5-114">**帮助组织有效共享知识并提高敏捷性**：通过确保用户仅处理与自己相关的最新内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-114">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span>

<span data-ttu-id="1fca5-115">你配置的保留设置可以帮助你实现这些目标。</span><span class="sxs-lookup"><span data-stu-id="1fca5-115">Retention settings that you configure can help you achieve these goals.</span></span> <span data-ttu-id="1fca5-116">管理内容通常需要执行两项操作：</span><span class="sxs-lookup"><span data-stu-id="1fca5-116">Managing content commonly requires two actions:</span></span>

| <span data-ttu-id="1fca5-117">操作</span><span class="sxs-lookup"><span data-stu-id="1fca5-117">Action</span></span>| <span data-ttu-id="1fca5-118">用途</span><span class="sxs-lookup"><span data-stu-id="1fca5-118">Purpose</span></span> |
|:-----|:-----|
|<span data-ttu-id="1fca5-119">保留内容</span><span class="sxs-lookup"><span data-stu-id="1fca5-119">Retain content</span></span> | <span data-ttu-id="1fca5-120">防止永久删除并保持可用于电子数据展示</span><span class="sxs-lookup"><span data-stu-id="1fca5-120">Prevent permanent deletion and remain available for eDiscovery</span></span> |
|<span data-ttu-id="1fca5-121">删除内容</span><span class="sxs-lookup"><span data-stu-id="1fca5-121">Delete content</span></span> | <span data-ttu-id="1fca5-122">从组织中永久删除内容</span><span class="sxs-lookup"><span data-stu-id="1fca5-122">Permanently delete content from your organization</span></span>|

<span data-ttu-id="1fca5-123">通过这两项保留操作，可以配置保留设置来实现以下结果：</span><span class="sxs-lookup"><span data-stu-id="1fca5-123">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="1fca5-124">仅保留：永久或在指定的时间段内保留内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-124">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="1fca5-125">仅删除：在指定的时间段后永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-125">Delete-only: Permanently delete content after a specified period of time.</span></span>
- <span data-ttu-id="1fca5-126">保留后删除：在指定的时间段内保留内容后永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-126">Retain and then delete: Retain content for a specified period of time and then permanently delete it.</span></span>

<span data-ttu-id="1fca5-127">这些保留设置应用于在适当位置上的内容，如果你出于合规性原因需要保留内容，它们可以为你节省创建和配置附加存储的额外开销。</span><span class="sxs-lookup"><span data-stu-id="1fca5-127">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons.</span></span> <span data-ttu-id="1fca5-128">另外，无需实现自定义流程来复制和同步此数据。</span><span class="sxs-lookup"><span data-stu-id="1fca5-128">In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

<span data-ttu-id="1fca5-129">使用以下各节了解有关保留策略和保留标签如何工作、何时使用以及它们如何相互补充的更多信息。</span><span class="sxs-lookup"><span data-stu-id="1fca5-129">Use the following sections to learn more about how retention policies and retention labels work, when to use them, and how they supplement each other.</span></span> <span data-ttu-id="1fca5-130">但是，如果你已准备好开始为某些常见情况部署保留设置，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-130">But if you're ready to get started and deploy retention settings for some common scenarios, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="1fca5-131">保留设置如何应用于在适当位置上的内容</span><span class="sxs-lookup"><span data-stu-id="1fca5-131">How retention settings work with content in place</span></span>

<span data-ttu-id="1fca5-p106">分配有保留设置的内容保留在它的原始位置上。用户可以继续使用其文档或邮件，就像没有发生任何变动一样。但如果他们编辑或删除了包含在保留策略中的内容，则会自动保留一份内容的副本。</span><span class="sxs-lookup"><span data-stu-id="1fca5-p106">When content has retention settings assigned to it, that content remains in its original location. People can continue to work with their documents or mail as if nothing's changed. But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained.</span></span>
  
- <span data-ttu-id="1fca5-135">对于 SharePoint 和 OneDrive 网站：副本保留在 **保留** 库中。</span><span class="sxs-lookup"><span data-stu-id="1fca5-135">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="1fca5-136">对于 Exchange 邮箱：副本保留在“可恢复项”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1fca5-136">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="1fca5-137">对于 Teams 和 Yammer 消息：副本保留在 Exchange“**可恢复项**”文件夹内名为“**SubstrateHolds**”的隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1fca5-137">For Teams and Yammer messages: The copy is retained in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="1fca5-138">保留库占用的存储计入网站的存储配额。</span><span class="sxs-lookup"><span data-stu-id="1fca5-138">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="1fca5-139">在对 SharePoint 和 Microsoft 365 组使用保留设置时，可能需要增加存储空间。</span><span class="sxs-lookup"><span data-stu-id="1fca5-139">You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="1fca5-140">这些安全位置和保留的内容对大部分用户不可见。</span><span class="sxs-lookup"><span data-stu-id="1fca5-140">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="1fca5-141">在大多数情况下，用户甚至不需要知道他们的内容遵循保留设置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-141">In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="1fca5-142">若要详细了解保留设置如何用于不同的工作负载，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="1fca5-142">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="1fca5-143">了解用于 SharePoint 和 OneDrive 的保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-143">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="1fca5-144">了解用于 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-144">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="1fca5-145">了解用于 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-145">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="1fca5-146">了解用于 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-146">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="1fca5-147">保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="1fca5-147">Retention policies and retention labels</span></span>

<span data-ttu-id="1fca5-148">若要将保留设置分配到内容，请使用 **保留策略** 和 **带有标签策略的保留标签**。</span><span class="sxs-lookup"><span data-stu-id="1fca5-148">To assign your retention settings to content, use **retention policies** and **retention labels with label policies**.</span></span> <span data-ttu-id="1fca5-149">可以使用其中一种方法，也可以组合使用。</span><span class="sxs-lookup"><span data-stu-id="1fca5-149">You can use just one of these methods, or combine them.</span></span>

<span data-ttu-id="1fca5-150">使用保留策略可以在网站或邮箱级别为内容分配相同的保留设置，使用保留标签可以在项（文件夹、文档、电子邮件）级别分配保留设置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-150">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="1fca5-151">例如，如果某 SharePoint 网站中的所有文档都应保留 5 年，那么使用保留策略比将相同的保留标签应用于此网站中的所有文档更高效。</span><span class="sxs-lookup"><span data-stu-id="1fca5-151">For example, if all documents in a SharePoint site should be retained for 5 years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site.</span></span> <span data-ttu-id="1fca5-152">不过，如果此网站中的一些文档应保留 5 年，另一些文档应保留 10 年，那么保留策略就无法实现这一点。</span><span class="sxs-lookup"><span data-stu-id="1fca5-152">However, if some documents in that site should be retained for 5 years and others retained for 10 years, a retention policy wouldn't be able to do this.</span></span> <span data-ttu-id="1fca5-153">如果需要在项级别指定保留设置，请使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-153">When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="1fca5-154">与保留策略不同，如果内容移动到 Microsoft 365 租户内的不同位置，保留标签的保留设置会随着内容移动而移动。</span><span class="sxs-lookup"><span data-stu-id="1fca5-154">Unlike retention policies, retention settings from retention labels travel with the content if it’s moved to a different location within your Microsoft 365 tenant.</span></span> <span data-ttu-id="1fca5-155">另外，保留标签具有保留策略不支持的以下功能：</span><span class="sxs-lookup"><span data-stu-id="1fca5-155">In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="1fca5-156">除了根据内容年限或上次修改时间计算保留期之外，还可以从内容被标记时或根据事件开始计算保留期。</span><span class="sxs-lookup"><span data-stu-id="1fca5-156">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="1fca5-157">使用[可训练的分类器](classifier-learn-about.md)来标识要标记的内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-157">Use [trainable classifiers](classifier-learn-about.md) to identify content to label.</span></span>

- <span data-ttu-id="1fca5-158">为 SharePoint 文档应用默认标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-158">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="1fca5-159">支持[处置评审](./disposition.md) ，以在永久删除内容前评审内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-159">Support [disposition review](./disposition.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="1fca5-160">将内容标记为[记录](records-management.md#records)作为标签设置的一部分，并对在保留期结束时删除的内容始终都有 [处置证明](disposition.md#disposition-of-records) 。</span><span class="sxs-lookup"><span data-stu-id="1fca5-160">Mark the content as a [record](records-management.md#records) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="1fca5-161">保留策略</span><span class="sxs-lookup"><span data-stu-id="1fca5-161">Retention policies</span></span>

<span data-ttu-id="1fca5-162">可以将保留策略应用于以下位置：</span><span class="sxs-lookup"><span data-stu-id="1fca5-162">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="1fca5-163">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="1fca5-163">Exchange email</span></span>
- <span data-ttu-id="1fca5-164">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="1fca5-164">SharePoint site</span></span>
- <span data-ttu-id="1fca5-165">OneDrive 账户</span><span class="sxs-lookup"><span data-stu-id="1fca5-165">OneDrive accounts</span></span>
- <span data-ttu-id="1fca5-166">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="1fca5-166">Microsoft 365 Groups</span></span>
- <span data-ttu-id="1fca5-167">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1fca5-167">Skype for Business</span></span>
- <span data-ttu-id="1fca5-168">Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="1fca5-168">Exchange public folders</span></span>
- <span data-ttu-id="1fca5-169">Teams 通道消息</span><span class="sxs-lookup"><span data-stu-id="1fca5-169">Teams channel messages</span></span>
- <span data-ttu-id="1fca5-170">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="1fca5-170">Teams chats</span></span>
- <span data-ttu-id="1fca5-171">yammer 社区消息</span><span class="sxs-lookup"><span data-stu-id="1fca5-171">Yammer community messages</span></span>
- <span data-ttu-id="1fca5-172">Yammer 用户消息</span><span class="sxs-lookup"><span data-stu-id="1fca5-172">Yammer user messages</span></span>

<span data-ttu-id="1fca5-173">可以非常高效地将一个策略应用于多个位置，也可以应用于特定的位置或用户。</span><span class="sxs-lookup"><span data-stu-id="1fca5-173">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>

<span data-ttu-id="1fca5-174">对于保留期的开始，你可以选择内容创建的时间，或者上次修改内容的时间（仅支持文件和 SharePoint、OneDrive 和 Microsoft 365 组位置）。</span><span class="sxs-lookup"><span data-stu-id="1fca5-174">For the start of the retention period, you can choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups locations, when the content was last modified.</span></span>

<span data-ttu-id="1fca5-175">项目从保留策略所指定的容器中继承保留设置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-175">Items inherit the retention settings from their container specified in the retention policy.</span></span> <span data-ttu-id="1fca5-176">如果当策略配置为保留内容之后将它们移动到该容器之外，则该项目的副本将保留在工作负载的安全位置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-176">If they are then moved outside that container when the policy is configured to retain content, a copy of that item is retained in the workload's secured location.</span></span> <span data-ttu-id="1fca5-177">然而，保留设置不会随着内容在新的位置而一起移动。</span><span class="sxs-lookup"><span data-stu-id="1fca5-177">However, the retention settings don't travel with the content in its new location.</span></span> <span data-ttu-id="1fca5-178">如果需要，请使用保留标签而不是保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-178">If that's required, use retention labels instead of retention policies.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="1fca5-179">保留标签</span><span class="sxs-lookup"><span data-stu-id="1fca5-179">Retention labels</span></span>

<span data-ttu-id="1fca5-p113">对于需要不同保留设置的不同类型的内容，可以使用保留标签。例如：</span><span class="sxs-lookup"><span data-stu-id="1fca5-p113">Use retention labels for different types of content that require different retention settings. For example:</span></span>
  
- <span data-ttu-id="1fca5-182">至少必须保留一段时间的税务表单。</span><span class="sxs-lookup"><span data-stu-id="1fca5-182">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="1fca5-183">达到特定年限后必须永久删除的新闻材料。</span><span class="sxs-lookup"><span data-stu-id="1fca5-183">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="1fca5-184">必须在保留一段时间后永久删除的竞争性研究。</span><span class="sxs-lookup"><span data-stu-id="1fca5-184">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="1fca5-185">必须标记为记录以免被编辑或删除的工作签证。</span><span class="sxs-lookup"><span data-stu-id="1fca5-185">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="1fca5-186">在所有这些情况下，可以使用保留标签在项（文档或电子邮件）级别应用保留设置来实现管理控制。</span><span class="sxs-lookup"><span data-stu-id="1fca5-186">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="1fca5-187">使用保留标签，你可以：</span><span class="sxs-lookup"><span data-stu-id="1fca5-187">With retention labels, you can:</span></span>
  
- <span data-ttu-id="1fca5-188">**允许组织中的人员将保留标签手动应用于** Outlook 和 Outlook 网页版、OneDrive、SharePoint​​ 和 Microsoft 365 组中的内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-188">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups.</span></span> <span data-ttu-id="1fca5-189">用户通常最了解自己处理的内容的类型，因此他们可以对内容进行分类，并应用适当的保留设置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-189">Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="1fca5-190">**将保留标签自动应用于** 符合特定条件的内容，如内容包含：</span><span class="sxs-lookup"><span data-stu-id="1fca5-190">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="1fca5-191">特定类型敏感信息。</span><span class="sxs-lookup"><span data-stu-id="1fca5-191">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="1fca5-192">与所创建的查询匹配的特定关键字。</span><span class="sxs-lookup"><span data-stu-id="1fca5-192">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="1fca5-193">可训练分类器的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="1fca5-193">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="1fca5-194">**从内容被标记时开始计算保留期**，适用于 SharePoint 网站和 OneDrive 帐户中的文档，以及除日历项外的电子邮件项。</span><span class="sxs-lookup"><span data-stu-id="1fca5-194">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items.</span></span> <span data-ttu-id="1fca5-195">如果你将具有此配置的保留标签应用于日历项，保留期从日历项发送时开始计算。</span><span class="sxs-lookup"><span data-stu-id="1fca5-195">If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="1fca5-196">**从事件发生时开始计算保留期**，如员工离开组织或合同到期。</span><span class="sxs-lookup"><span data-stu-id="1fca5-196">**Start the retention period when an event occurs**, such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="1fca5-197">**将默认保留标签应用于 SharePoint 中的文档库、文件夹或文档集**，以让存储在该位置的所有文档都继承默认保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-197">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="1fca5-198">此外，保留标签支持跨 Microsoft 365 应用和服务对电子邮件和文档实施[记录管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-198">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services.</span></span> <span data-ttu-id="1fca5-199">可使用保留标签将项目标记为记录。</span><span class="sxs-lookup"><span data-stu-id="1fca5-199">You can use a retention label to mark items as a record.</span></span> <span data-ttu-id="1fca5-200">如果发生这种情况，而内容仍保留在 Microsoft 365 中，则标签会对内容进行进一步的限制，这可能是监管原因所致。</span><span class="sxs-lookup"><span data-stu-id="1fca5-200">When this happens and the content remains in Microsoft 365, the label places further restrictions on the content that might be needed for regulatory reasons.</span></span> <span data-ttu-id="1fca5-201">有关详细信息，请参阅[比较对允许或阻止的操作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-201">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

<span data-ttu-id="1fca5-202">如果内容被移动到 Microsoft 365 之外，则保留标签将不会继续存在，这一点与[敏感度标签](sensitivity-labels.md)是不同的。</span><span class="sxs-lookup"><span data-stu-id="1fca5-202">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="1fca5-p117">租户支持的保留标签数没有限制。但是，租户支持的最大策略数为 10,000，其中包括应用标签的策略（保留标签策略和自动应用保留策略）以及保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-p117">There is no limit to the number of retention labels that are supported for a tenant. However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="1fca5-205">对内容分类但不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="1fca5-205">Classifying content without applying any actions</span></span>

<span data-ttu-id="1fca5-206">虽然保留标签的主要用途是保留或删除内容，但也可以在使用保留标签时不启用任何保留或其他操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-206">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions.</span></span> <span data-ttu-id="1fca5-207">在这种情况下，可以简单地将保留标签用作文本标签，而不强制执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-207">In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="1fca5-208">例如，可以创建并应用名为“稍后评审”且不含任何操作的保留标签，稍后使用此标签来查找相应内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-208">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![将设置标记为仅分类](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="1fca5-210">将保留标签用作 DLP 策略中的条件</span><span class="sxs-lookup"><span data-stu-id="1fca5-210">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="1fca5-211">对于 SharePoint 中的文档，可以将保留标签指定为数据丢失防护 (DLP) 策略中的条件。</span><span class="sxs-lookup"><span data-stu-id="1fca5-211">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint.</span></span> <span data-ttu-id="1fca5-212">例如，配置一个 DLP 策略，以防在组织外部共享应用了指定保留标签的文档。</span><span class="sxs-lookup"><span data-stu-id="1fca5-212">For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="1fca5-213">有关详细信息，请参阅[将保留标签用作 DLP 策略中的条件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-213">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="1fca5-214">保留标签和应用它们的策略</span><span class="sxs-lookup"><span data-stu-id="1fca5-214">Retention labels and policies that apply them</span></span>

<span data-ttu-id="1fca5-215">在你发布保留标签后，它们将包含在 **保留标签策略** 中，以便管理员和用户将其应用至内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-215">When you publish retention labels, they're included in a **retention label policy** that makes them available for admins and users to apply to content.</span></span> <span data-ttu-id="1fca5-216">如下图所示：</span><span class="sxs-lookup"><span data-stu-id="1fca5-216">As the following diagram shows:</span></span>

1. <span data-ttu-id="1fca5-217">一个保留标签可包含在多个保留标签策略中。</span><span class="sxs-lookup"><span data-stu-id="1fca5-217">A single retention label can be included in multiple retention label policies.</span></span>

2. <span data-ttu-id="1fca5-218">保留标签策略指定了保留标签的发布位置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-218">Retention label policies specify the locations to publish the retention labels.</span></span> <span data-ttu-id="1fca5-219">同一位置可包含在多个保留标签策略中。</span><span class="sxs-lookup"><span data-stu-id="1fca5-219">The same location can be included in multiple retention label policies.</span></span>

![如何将保留标签添加到为其指定位置的标签策略](../media/retention-labels-and-policies.png)

<span data-ttu-id="1fca5-221">你还可以创建一个或多个 **自动应用保留标签策略**，其中每个策略都有一个保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-221">You can also create one or more **auto-apply retention label policies**, each with a single retention label.</span></span> <span data-ttu-id="1fca5-222">如果使用此策略，当满足你在策略中指定的条件时，保留标签就会自动应用。</span><span class="sxs-lookup"><span data-stu-id="1fca5-222">With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span>

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="1fca5-223">保留标签策略和位置</span><span class="sxs-lookup"><span data-stu-id="1fca5-223">Retention label policies and locations</span></span>

<span data-ttu-id="1fca5-224">不同类型的保留标签可发布到不同位置，具体视保留标签用途而定。</span><span class="sxs-lookup"><span data-stu-id="1fca5-224">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="1fca5-225">如果保留标签是…</span><span class="sxs-lookup"><span data-stu-id="1fca5-225">If the retention label is…</span></span> | <span data-ttu-id="1fca5-226">可以将标签策略应用于…</span><span class="sxs-lookup"><span data-stu-id="1fca5-226">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="1fca5-227">发布给管理员和最终用户</span><span class="sxs-lookup"><span data-stu-id="1fca5-227">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="1fca5-228">Exchange、SharePoint、OneDrive、Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="1fca5-228">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="1fca5-229">根据敏感信息类型或可训练的分类器自动应用</span><span class="sxs-lookup"><span data-stu-id="1fca5-229">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="1fca5-230">Exchange（仅全部邮箱）、SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="1fca5-230">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="1fca5-231">根据查询自动应用</span><span class="sxs-lookup"><span data-stu-id="1fca5-231">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="1fca5-232">Exchange、SharePoint、OneDrive、Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="1fca5-232">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="1fca5-p123">在 Exchange 中，自动应用保留标签仅应用于新发送的邮件（传输中的数据），而不是邮箱中当前的所有邮件（其余数据）。此外，对敏感信息类型和可培训的分类器自动应用保留标签适用于所有邮箱;你无法选择特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fca5-p123">In Exchange, retention labels that you auto-apply are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest). Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="1fca5-235">Exchange 公用文件夹、Skype、Teams 和 Yammer 消息不支持保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-235">Exchange public folders, Skype, Teams and Yammer messages do not support retention labels.</span></span> <span data-ttu-id="1fca5-236">若要保留并从这些位置中删除内容，请改用保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-236">To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="1fca5-237">一次只能分配一个保留标签</span><span class="sxs-lookup"><span data-stu-id="1fca5-237">Only one retention label at a time</span></span>

<span data-ttu-id="1fca5-238">电子邮件或文档一次只能应用有一个保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-238">An email or document can have only a single retention label applied to it at a time.</span></span> <span data-ttu-id="1fca5-239">保留标签可以由最终用户或管理员[手动](create-apply-retention-labels.md#manually-apply-retention-labels)应用，也可以使用以下任一方法自动应用：</span><span class="sxs-lookup"><span data-stu-id="1fca5-239">A retention label can be applied [manually](create-apply-retention-labels.md#manually-apply-retention-labels) by an end user or admin, or automatically by using any of the following methods:</span></span>

- [<span data-ttu-id="1fca5-240">自动应用标签策略</span><span class="sxs-lookup"><span data-stu-id="1fca5-240">Auto-apply label policy</span></span>](apply-retention-labels-automatically.md)
- [<span data-ttu-id="1fca5-241">Microsoft SharePoint Syntex 中的文档理解模型</span><span class="sxs-lookup"><span data-stu-id="1fca5-241">Document understanding model for SharePoint Syntex</span></span>](../contentunderstanding/apply-a-retention-label-to-a-model.md)
- <span data-ttu-id="1fca5-242">[SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) 或 [Outlook 的默认标签](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="1fca5-242">[Default label for SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) or [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>
- [<span data-ttu-id="1fca5-243">Outlook 规则</span><span class="sxs-lookup"><span data-stu-id="1fca5-243">Outlook rules</span></span>](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

<span data-ttu-id="1fca5-244">对于标准保留标签（它们不会将项目标记为[记录或监管记录](records-management.md#records)）：</span><span class="sxs-lookup"><span data-stu-id="1fca5-244">For standard retention labels (they don't mark items as a [record or regulatory record](records-management.md#records)):</span></span>

- <span data-ttu-id="1fca5-245">管理员和最终用户可以手动更改或删除应用于内容的现有保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-245">Admins and end users can manually change or remove an existing retention label that's applied on content.</span></span> 

- <span data-ttu-id="1fca5-246">当内容已应用保留标签时，现有标签不会自动删除或替换为另一个保留标签，但有一个可能的例外：现有标签已作为默认标签应用。</span><span class="sxs-lookup"><span data-stu-id="1fca5-246">When content already has a retention label applied, the existing label won't be automatically removed or replaced by another retention label with one possible exception: The existing label was applied as a default label.</span></span>
    
    <span data-ttu-id="1fca5-247">有关使用默认标签应用标签行为的详细信息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1fca5-247">For more information about the label behavior when it's applied by using a default label:</span></span>
    - <span data-ttu-id="1fca5-248">SharePoint 的默认标签：[对 SharePoint 使用默认标签时的标签行为](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="1fca5-248">Default label for SharePoint: [Label behavior when you use a default label for SharePoint](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span></span>
    - <span data-ttu-id="1fca5-249">Outlook 的默认标签：[将默认保留标签应用于 Outlook 文件夹](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="1fca5-249">Default label for Outlook: [Applying a default retention label to an Outlook folder](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>

- <span data-ttu-id="1fca5-250">如果有多个自动应用标签策略可以应用保留标签，并且内容满足多个策略的条件，则应用最旧的自动应用标签策略（按创建日期）的保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-250">If there are multiple auto-apply label policies that could apply a retention label, and content meets the conditions of multiple policies, the retention label for the oldest auto-apply label policy (by date created) is applied.</span></span>

<span data-ttu-id="1fca5-251">当保留标签将项目标记为记录或管理记录时，这些标签不会自动更改。</span><span class="sxs-lookup"><span data-stu-id="1fca5-251">When retention labels mark items as a record or a regulatory record, these labels are never automatically changed.</span></span> <span data-ttu-id="1fca5-252">只有容器的管理员才能手动更改或删除将项目标记为记录而不是管理记录的保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-252">Only admins for the container can manually change or remove retention labels that mark items as a record, but not regulatory records.</span></span> <span data-ttu-id="1fca5-253">有关详细信息，请参阅[比较对允许或阻止的操作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-253">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

#### <a name="monitoring-retention-labels"></a><span data-ttu-id="1fca5-254">监视保留标签</span><span class="sxs-lookup"><span data-stu-id="1fca5-254">Monitoring retention labels</span></span>

<span data-ttu-id="1fca5-255">从 Microsoft 365 合规中心选择“**数据分类**”和“**概述**”页面来监视保留标签在租户中的使用方式，并确定已标记项目的位置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-255">From the Microsoft 365 compliance center, select **Data classification** and the **Overview** page to monitor how your retention labels are being used in your tenant, and identify where your labeled items are located.</span></span> <span data-ttu-id="1fca5-256">有关包括重要先决条件在内的详细信息，请参阅 [了解数据分类](data-classification-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-256">For more information, including important prerequisites, see [Learn about data classification](data-classification-overview.md).</span></span>

<span data-ttu-id="1fca5-257">然后，你可以通过使用[内容资源管理器](data-classification-content-explorer.md)和[活动资源管理器](data-classification-activity-explorer.md)来深入了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="1fca5-257">You can then drill down into details by using [content explorer](data-classification-content-explorer.md) and [activity explorer](data-classification-activity-explorer.md).</span></span>

> [!TIP]
><span data-ttu-id="1fca5-258">请考虑使用其他的一些数据分类见解（如可训练分类器和敏感信息类型），帮助你识别可能需要保留或删除的内容，或者作为记录进行管理的内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-258">Consider using some of the other data classification insights, such as trainable classifiers and sensitive info types, to help you identify content that you might need to retain or delete, or manage as records.</span></span>

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a><span data-ttu-id="1fca5-259">使用“内容搜索”来查找所有带有特定保留标签的内容</span><span class="sxs-lookup"><span data-stu-id="1fca5-259">Using Content Search to find all content with a specific retention label</span></span>

<span data-ttu-id="1fca5-260">在将保留标签应用到内容后（无论是由用户应用还是自动应用），你都可以通过内容搜索来查找已经应用特定保留标签的所有项目。</span><span class="sxs-lookup"><span data-stu-id="1fca5-260">After retention labels are applied to content, either by users or auto-applied, you can use content search to find all items that have a specific retention label applied.</span></span>

<span data-ttu-id="1fca5-261">创建内容搜索时，选择“**保留标签**”条件，然后输入完整的保留标签名称或标签名称的一部分，并使用通配符。</span><span class="sxs-lookup"><span data-stu-id="1fca5-261">When you create a content search, choose the **Retention label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="1fca5-262">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-262">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![保留标签条件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="1fca5-264">比较保留策略和保留标签的功能</span><span class="sxs-lookup"><span data-stu-id="1fca5-264">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="1fca5-265">请使用下表来帮助你根据功能确定是使用保留策略还是保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-265">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="1fca5-266">功能</span><span class="sxs-lookup"><span data-stu-id="1fca5-266">Capability</span></span>|<span data-ttu-id="1fca5-267">保留策略</span><span class="sxs-lookup"><span data-stu-id="1fca5-267">Retention policy</span></span> |<span data-ttu-id="1fca5-268">保留标签</span><span class="sxs-lookup"><span data-stu-id="1fca5-268">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1fca5-269">保留设置可以是“保留后删除”、“仅保留”或“仅删除”</span><span class="sxs-lookup"><span data-stu-id="1fca5-269">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="1fca5-270">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-270">Yes</span></span> |<span data-ttu-id="1fca5-271">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-271">Yes</span></span> |
|<span data-ttu-id="1fca5-272">支持的工作负载：</span><span class="sxs-lookup"><span data-stu-id="1fca5-272">Workloads supported:</span></span> <br /><span data-ttu-id="1fca5-273">- Exchange</span><span class="sxs-lookup"><span data-stu-id="1fca5-273">- Exchange</span></span> <br /><span data-ttu-id="1fca5-274">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="1fca5-274">- SharePoint</span></span> <br /><span data-ttu-id="1fca5-275">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="1fca5-275">- OneDrive</span></span> <br /><span data-ttu-id="1fca5-276">- Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="1fca5-276">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="1fca5-277">- Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1fca5-277">- Skype for Business</span></span> <br /><span data-ttu-id="1fca5-278">- Teams</span><span class="sxs-lookup"><span data-stu-id="1fca5-278">- Teams</span></span><br /><span data-ttu-id="1fca5-279">- Yammer</span><span class="sxs-lookup"><span data-stu-id="1fca5-279">- Yammer</span></span>|<br /> <span data-ttu-id="1fca5-280">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-280">Yes</span></span> <br /> <span data-ttu-id="1fca5-281">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-281">Yes</span></span> <br /> <span data-ttu-id="1fca5-282">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-282">Yes</span></span> <br /> <span data-ttu-id="1fca5-283">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-283">Yes</span></span> <br /> <span data-ttu-id="1fca5-284">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-284">Yes</span></span> <br /> <span data-ttu-id="1fca5-285">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-285">Yes</span></span> <br /> <span data-ttu-id="1fca5-286">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-286">Yes</span></span> | <br /> <span data-ttu-id="1fca5-287">是，但公用文件夹除外</span><span class="sxs-lookup"><span data-stu-id="1fca5-287">Yes, except public folders</span></span> <br /> <span data-ttu-id="1fca5-288">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-288">Yes</span></span> <br /> <span data-ttu-id="1fca5-289">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-289">Yes</span></span> <br /> <span data-ttu-id="1fca5-290">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-290">Yes</span></span> <br /> <span data-ttu-id="1fca5-291">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-291">No</span></span> <br /> <span data-ttu-id="1fca5-292">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-292">No</span></span> <br /> <span data-ttu-id="1fca5-293">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-293">No</span></span> |
|<span data-ttu-id="1fca5-294">自动应用保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-294">Retention applied automatically</span></span> | <span data-ttu-id="1fca5-295">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-295">Yes</span></span> | <span data-ttu-id="1fca5-296">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-296">Yes</span></span> |
|<span data-ttu-id="1fca5-297">基于条件应用保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-297">Retention applied based on conditions</span></span> <br /> <span data-ttu-id="1fca5-298">- 敏感信息类型、KQL 查询、可训练的分类器</span><span class="sxs-lookup"><span data-stu-id="1fca5-298">- sensitive info types, KQL queries and keywords, trainable classifiers</span></span>| <span data-ttu-id="1fca5-299">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-299">No</span></span> | <span data-ttu-id="1fca5-300">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-300">Yes</span></span> |
|<span data-ttu-id="1fca5-301">手动应用保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-301">Retention applied manually</span></span> | <span data-ttu-id="1fca5-302">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-302">No</span></span> | <span data-ttu-id="1fca5-303">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-303">Yes</span></span> |
|<span data-ttu-id="1fca5-304">对最终用户显示 UI</span><span class="sxs-lookup"><span data-stu-id="1fca5-304">UI presence for end users</span></span> | <span data-ttu-id="1fca5-305">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-305">No</span></span> | <span data-ttu-id="1fca5-306">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-306">Yes</span></span> |
|<span data-ttu-id="1fca5-307">在内容移动时仍继续应用在内容上</span><span class="sxs-lookup"><span data-stu-id="1fca5-307">Persists if the content is moved</span></span> | <span data-ttu-id="1fca5-308">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-308">No</span></span> | <span data-ttu-id="1fca5-309">是，在您的 Microsoft 365 租户中</span><span class="sxs-lookup"><span data-stu-id="1fca5-309">Yes, within your Microsoft 365 tenant</span></span> |
|<span data-ttu-id="1fca5-310">将项声明为记录</span><span class="sxs-lookup"><span data-stu-id="1fca5-310">Declare item as a record</span></span>| <span data-ttu-id="1fca5-311">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-311">No</span></span> | <span data-ttu-id="1fca5-312">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-312">Yes</span></span> |
|<span data-ttu-id="1fca5-313">从内容被标记或事件发生时开始计算保留期</span><span class="sxs-lookup"><span data-stu-id="1fca5-313">Start the retention period when labeled or based on an event</span></span> | <span data-ttu-id="1fca5-314">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-314">No</span></span> | <span data-ttu-id="1fca5-315">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-315">Yes</span></span> |
|<span data-ttu-id="1fca5-316">处置评审</span><span class="sxs-lookup"><span data-stu-id="1fca5-316">Disposition review</span></span> | <span data-ttu-id="1fca5-317">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-317">No</span></span>| <span data-ttu-id="1fca5-318">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-318">Yes</span></span> |
|<span data-ttu-id="1fca5-319">最长 7 年的处置证明</span><span class="sxs-lookup"><span data-stu-id="1fca5-319">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="1fca5-320">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-320">No</span></span> |<span data-ttu-id="1fca5-321">是，使用处置评审或项目被标记为记录时</span><span class="sxs-lookup"><span data-stu-id="1fca5-321">Yes, when you use disposition review or item is marked a record</span></span>|
|<span data-ttu-id="1fca5-322">审核管理员活动</span><span class="sxs-lookup"><span data-stu-id="1fca5-322">Audit admin activities</span></span>| <span data-ttu-id="1fca5-323">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-323">Yes</span></span> | <span data-ttu-id="1fca5-324">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-324">Yes</span></span>|
|<span data-ttu-id="1fca5-325">审核保留操作</span><span class="sxs-lookup"><span data-stu-id="1fca5-325">Audit retention actions</span></span>| <span data-ttu-id="1fca5-326">不支持</span><span class="sxs-lookup"><span data-stu-id="1fca5-326">No</span></span> | <span data-ttu-id="1fca5-327">是的 <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1fca5-327">Yes <sup>\*</sup></span></span> |
|<span data-ttu-id="1fca5-328">识别遵循保留设置的项：</span><span class="sxs-lookup"><span data-stu-id="1fca5-328">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="1fca5-329">- 内容搜索</span><span class="sxs-lookup"><span data-stu-id="1fca5-329">- Content Search</span></span> <br /> <span data-ttu-id="1fca5-330">- 数据分类页、内容资源管理器、活动资源管理器</span><span class="sxs-lookup"><span data-stu-id="1fca5-330">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="1fca5-331">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-331">No</span></span> <br /> <span data-ttu-id="1fca5-332">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-332">No</span></span> | <br /> <span data-ttu-id="1fca5-333">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-333">Yes</span></span> <br /> <span data-ttu-id="1fca5-334">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-334">Yes</span></span>|

<span data-ttu-id="1fca5-335">**脚注：**</span><span class="sxs-lookup"><span data-stu-id="1fca5-335">**Footnote:**</span></span>

<span data-ttu-id="1fca5-336"><sup>\*</sup> 对于不将内容标记为记录或法规记录的保留标签，审核事件仅限于 SharePoint 中的项或OneDrive 应用、更改或删除标签时。</span><span class="sxs-lookup"><span data-stu-id="1fca5-336"><sup>\*</sup> For retention labels that don't mark the content as a record or regulatory record, auditing events are limited to when an item in SharePoint or OneDrive has a label applied, changed, or removed.</span></span> <span data-ttu-id="1fca5-337">有关保留标签的审核详细信息，请参阅此页上的[审核保留操作](#auditing-retention-actions)部分。</span><span class="sxs-lookup"><span data-stu-id="1fca5-337">For auditing details for retention labels, see the [Auditing retention actions](#auditing-retention-actions) section on this page.</span></span>

### <a name="combining-retention-policies-and-retention-labels"></a><span data-ttu-id="1fca5-338">组合保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="1fca5-338">Combining retention policies and retention labels</span></span>

<span data-ttu-id="1fca5-339">无需选择仅使用保留策略还是仅使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-339">You don't have to choose between using retention policies only or retention labels only.</span></span> <span data-ttu-id="1fca5-340">这两种方法可以一起使用，实际上可以相互补充，以获得更全面的解决方案。</span><span class="sxs-lookup"><span data-stu-id="1fca5-340">Both methods can be used together and in fact, complementary each other for a more comprehensive solution.</span></span> <span data-ttu-id="1fca5-341">例如：</span><span class="sxs-lookup"><span data-stu-id="1fca5-341">For example:</span></span>

1. <span data-ttu-id="1fca5-342">你创建并配置一个保留策略，以便在自最后一次修改内容起 5 年后自动删除内容，同时你将此策略应用于所有 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="1fca5-342">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="1fca5-343">你创建并配置一个保留标签来永久保留内容，同时你将此标签添加到发布到所有 OneDrive 帐户的标签策略中。</span><span class="sxs-lookup"><span data-stu-id="1fca5-343">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="1fca5-344">你向用户解释如何将此标签手动应用于特定文档，这些文档应排除在 5 年未修改后自动删除范围之外。</span><span class="sxs-lookup"><span data-stu-id="1fca5-344">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="1fca5-345">若要详细了解保留策略和保留标签是如何协同工作的，以及如何确定它们的合并结果，请参阅下一部分，其中介绍了保留原则和优先级。</span><span class="sxs-lookup"><span data-stu-id="1fca5-345">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="1fca5-346">保留原则或优先级</span><span class="sxs-lookup"><span data-stu-id="1fca5-346">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="1fca5-347">与保留标签不同，您可以对同一内容应用多个保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-347">Unlike retention labels, you can apply more than one retention policy to the same content.</span></span> <span data-ttu-id="1fca5-348">每个保留策略都可以导致保留操作和删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-348">Each retention policy can result in a retain action and a delete action.</span></span> <span data-ttu-id="1fca5-349">此外，该商品还可能受到保留标签上的这些措施的约束。</span><span class="sxs-lookup"><span data-stu-id="1fca5-349">Additionally, that item could also be subject to these actions from a retention label.</span></span>

<span data-ttu-id="1fca5-350">在这种情况下，当项目可以经受可能彼此冲突的多个保留设置时，确定结果的优先顺序是什么？</span><span class="sxs-lookup"><span data-stu-id="1fca5-350">In this scenario, when items can be subject to multiple retention settings that could conflict with one another, what takes precedence to determine the outcome?</span></span>

<span data-ttu-id="1fca5-351">结果不是赢得单个保留策略或单个保留标签的结果，而是保留项目多长时间（如果适用）以及删除项目的时间（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="1fca5-351">The outcome isn't which single retention policy or single retention label wins, but how long an item is retained (if applicable) and when an item is deleted (if applicable).</span></span> <span data-ttu-id="1fca5-352">这两个操作是根据应用于项目的所有保留设置彼此独立计算的。</span><span class="sxs-lookup"><span data-stu-id="1fca5-352">These two actions are calculated independently from each other, from all the retention settings applied to an item.</span></span>

<span data-ttu-id="1fca5-353">例如，一个项目可能要受一个已配置为仅删除操作的保留策略的约束，而另一个则要配置为保留然后删除的保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-353">For example, an item might be subject to one retention policy that is configured for a delete-only action, and another retention policy that is configured to retain and then delete.</span></span> <span data-ttu-id="1fca5-354">因此，此项只有一个保留操作和两个删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-354">Consequently, this item has just one retain action but two delete actions.</span></span> <span data-ttu-id="1fca5-355">保留和删除操作可能彼此冲突，并且这两个删除操作的日期可能冲突。</span><span class="sxs-lookup"><span data-stu-id="1fca5-355">The retention and deletion actions could be in conflict with one another and the two deletion actions might have a conflicting date.</span></span> <span data-ttu-id="1fca5-356">保留原则说明了该结果。</span><span class="sxs-lookup"><span data-stu-id="1fca5-356">The principles of retention explain the outcome.</span></span>

<span data-ttu-id="1fca5-357">概括来说，可以确定的是，保留始终优先于永久性删除，然后是最长保留期胜出。</span><span class="sxs-lookup"><span data-stu-id="1fca5-357">At a high level, you can be assured that retention always takes precedence over permanent deletion, and the longest retention period wins.</span></span> <span data-ttu-id="1fca5-358">这两个简单的规则总是决定一个项目将保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="1fca5-358">These two simple rules always decide how long an item will be retained.</span></span>

<span data-ttu-id="1fca5-359">还有其他一些因素决定何时永久性删除项目，其中包括保留标签中的删除操作始终优先于保留策略中的删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-359">There are a few more factors that determine when an item will be permanently deleted, which include the delete action from a retention label always takes precedence over the delete action from a retention policy.</span></span>

<span data-ttu-id="1fca5-360">使用以下流程了解单个项目的保留和删除结果，其中每个级别从上到下都充当冲突平局。</span><span class="sxs-lookup"><span data-stu-id="1fca5-360">Use the following flow to understand the retention and deletion outcomes for a single item, where each level acts as a tie-breaker for conflicts, from top to bottom.</span></span> <span data-ttu-id="1fca5-361">如果结果由第一个级别决定，由于没有进一步冲突，则不需要再前进到下一个级别，等等。</span><span class="sxs-lookup"><span data-stu-id="1fca5-361">If the outcome is determined by the first level because there are no further conflicts, there's no need to progress to the next level, and so on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fca5-362">如果您使用的是保留标签：在使用此流程确定同一项目上多个保留设置的结果之前，请确保您知道[应用了哪个保留标签](#only-one-retention-label-at-a-time)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-362">If you are using retention labels: Before using this flow to determine the outcome of multiple retention settings on the same item, make sure you know [which retention label is applied](#only-one-retention-label-at-a-time).</span></span>

![保留原则关系图](../media/principles-of-retention.png)
  
<span data-ttu-id="1fca5-364">有关四种不同原则的说明：</span><span class="sxs-lookup"><span data-stu-id="1fca5-364">Explanation for the four different principles:</span></span>
  
1. <span data-ttu-id="1fca5-365">**保留优先于删除。**</span><span class="sxs-lookup"><span data-stu-id="1fca5-365">**Retention wins over deletion.**</span></span> <span data-ttu-id="1fca5-366">当内容也具有保留设置以保留它时，它不会被永久删除。</span><span class="sxs-lookup"><span data-stu-id="1fca5-366">Content won't be permanently deleted when it also has retention settings to retain it.</span></span> <span data-ttu-id="1fca5-367">虽然这一原则确保了内容因合规原因而保留，但删除过程仍会启动，并可能从用户视图中删除内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-367">While this principle ensures that content is preserved for compliance reasons, the delete process is still initiated and can remove the content from user view and searches.</span></span> <span data-ttu-id="1fca5-368">例如在 SharePoint 中，文件从原来的文件夹移到了保藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1fca5-368">For SharePoint, for example, a document moves from the original folder to the Preservation Holds folder.</span></span> <span data-ttu-id="1fca5-369">但是，已挂起永久删除。</span><span class="sxs-lookup"><span data-stu-id="1fca5-369">However, permanent deletion is suspended.</span></span> <span data-ttu-id="1fca5-370">关于内容如何保存以及保存在哪里的更多信息，请使用以下每个工作负载的链接：</span><span class="sxs-lookup"><span data-stu-id="1fca5-370">For more information about how and where content is retained, use the following links for each workload:</span></span>
    
    - [<span data-ttu-id="1fca5-371">用于 SharePoint 和 OneDrive 的保留的工作原理</span><span class="sxs-lookup"><span data-stu-id="1fca5-371">How retention works for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive)
    - [<span data-ttu-id="1fca5-372">用于 Microsoft Teams 的保留工作原理</span><span class="sxs-lookup"><span data-stu-id="1fca5-372">How retention works with Microsoft Teams</span></span>](retention-policies-teams.md#how-retention-works-with-microsoft-teams)
    - [<span data-ttu-id="1fca5-373">用于 Yammer 的保留的工作原理</span><span class="sxs-lookup"><span data-stu-id="1fca5-373">How retention works with Yammer</span></span>](retention-policies-yammer.md#how-retention-works-with-yammer)
    - [<span data-ttu-id="1fca5-374">用于 Exchange 的保留的工作原理</span><span class="sxs-lookup"><span data-stu-id="1fca5-374">How retention works for Exchange</span></span>](retention-policies-exchange.md#how-retention-works-for-exchange)
    
    <span data-ttu-id="1fca5-375">示例：电子邮件必须遵循Exchange的保留策略，该策略配置为在三年后删除项目，并且还应用了保留标签，该标签被配置为可以保留项目五年。</span><span class="sxs-lookup"><span data-stu-id="1fca5-375">Example: An email message is subject to a retention policy for Exchange that is configured to delete items after three years and it also has a retention label applied that is configured to retain items for five years.</span></span>
    
    <span data-ttu-id="1fca5-376">电子邮件将保留五年，因为此保留操作优先于删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-376">The email message is retained for five years because this retention action takes precedence over deletion.</span></span> <span data-ttu-id="1fca5-377">由于保留操作生效时暂停的删除操作，电子邮件在五年到期时被永久删除。</span><span class="sxs-lookup"><span data-stu-id="1fca5-377">The email message is permanently deleted at the end of the five years because of the delete action that was suspended while the retention action was in effect.</span></span>

2. <span data-ttu-id="1fca5-378">**优选最长的保留期。**</span><span class="sxs-lookup"><span data-stu-id="1fca5-378">**The longest retention period wins.**</span></span> <span data-ttu-id="1fca5-379">如果内容遵循多个在不同时间段内保留内容的保留设置，内容会一直保留到最长保留期结束。</span><span class="sxs-lookup"><span data-stu-id="1fca5-379">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
    <span data-ttu-id="1fca5-380">示例：Marketing SharePoint网站中的文档受两个保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="1fca5-380">Example: Documents in the Marketing SharePoint site are subject to two retention policies.</span></span> <span data-ttu-id="1fca5-381">为所有SharePoint网站配置第一个保留策略，以将项目保留五年。</span><span class="sxs-lookup"><span data-stu-id="1fca5-381">The first retention policy is configured for all SharePoint sites to retain items for five years.</span></span> <span data-ttu-id="1fca5-382">为特定的SharePoint网站配置第二个保留策略，以将项目保留十年。</span><span class="sxs-lookup"><span data-stu-id="1fca5-382">The second retention policy is configured for specific SharePoint sites to retain items for ten years.</span></span>
    
    <span data-ttu-id="1fca5-383">该Marketing SharePoint网站中的文档将保留十年，因为这是最长的保留期。</span><span class="sxs-lookup"><span data-stu-id="1fca5-383">Documents in this Marketing SharePoint site are retained for ten years because that's the longest retention period.</span></span>

3. <span data-ttu-id="1fca5-384">**显式删除优先于隐式删除。**</span><span class="sxs-lookup"><span data-stu-id="1fca5-384">**Explicit wins over implicit for deletions.**</span></span> <span data-ttu-id="1fca5-385">现在保留冲突已经解决，只有删除冲突仍然存在：</span><span class="sxs-lookup"><span data-stu-id="1fca5-385">With conflicts now resolved for retention, only conflicts for deletions remain:</span></span> 
    
    1. <span data-ttu-id="1fca5-386">与保留策略相比，保留标签（无论如何应用）都提供了显式保留，因为保留设置将应用于单个项目，而不是从容器隐式分配。</span><span class="sxs-lookup"><span data-stu-id="1fca5-386">A retention label (however it was applied) provides explicit retention in comparison with retention policies, because the retention settings are applied to an individual item rather than implicitly assigned from a container.</span></span> <span data-ttu-id="1fca5-387">这意味着从保留标签删除操作始终优先于从任何保留策略删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-387">This means that a delete action from a retention label always takes precedence over a delete action from any retention policy.</span></span>
        
        <span data-ttu-id="1fca5-388">示例：文档受两个保留策略的约束，删除策略分别为5年和10年，以及保留标签的删除策略为7年。</span><span class="sxs-lookup"><span data-stu-id="1fca5-388">Example: A document is subject to two retention policies that have a delete action of five years and ten years respectively, and also a retention label that has a delete action of seven years.</span></span>
        
        <span data-ttu-id="1fca5-389">七年后将永久性删除该文件，因为保留标签中的删除操作具有优先权。</span><span class="sxs-lookup"><span data-stu-id="1fca5-389">The document is permanently deleted after seven years because the delete action from the retention label takes precedence.</span></span>
    
    2. <span data-ttu-id="1fca5-390">仅当具有保留策略时：如果某个位置的保留策略的作用域是使用包含配置（例如Exchange电子邮件的特定用户），则该保留策略优先于同一位置的无范围保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-390">When you have retention policies only: If a retention policy for a location is scoped to use an include configuration (such as specific users for Exchange email) that retention policy takes precedence over unscoped retention policies for the same location.</span></span>
        
        <span data-ttu-id="1fca5-391">不受限制的保留策略是在不指定特定实例的情况下选择位置的位置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-391">An unscoped retention policy is where a location is selected without specifying specific instances.</span></span> <span data-ttu-id="1fca5-392">例如，**Exchange电子邮件** 和默认设置 **“所有收件人”** 是不受范围限制的保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-392">For example, **Exchange email** and the default setting of **All recipients** is an unscoped retention policy.</span></span> <span data-ttu-id="1fca5-393">或者，**SharePoint网站** 和 **“所有网站”** 的默认设置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-393">Or, **SharePoint sites** and the default setting of **All sites**.</span></span> <span data-ttu-id="1fca5-394">在对保留策略进行范围划分时，它们在此级别具有相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="1fca5-394">When retention policies are scoped, they have equal precedence at this level.</span></span>
        
        <span data-ttu-id="1fca5-395">示例1：电子邮件受两个保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="1fca5-395">Example 1: An email message is subject to two retention policies.</span></span> <span data-ttu-id="1fca5-396">第一个保留策略不受范围限制，并在十年后删除项目。</span><span class="sxs-lookup"><span data-stu-id="1fca5-396">The first retention policy is unscoped and deletes items after ten years.</span></span> <span data-ttu-id="1fca5-397">第二个保留策略适用于特定邮箱，并在五年后删除项目。</span><span class="sxs-lookup"><span data-stu-id="1fca5-397">The second retention policy is scoped to specific mailboxes and deletes items after five years.</span></span>
        
        <span data-ttu-id="1fca5-398">五年后将永久性删除电子邮件，因为有范围的保留策略中的删除操作优先于无范围的保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-398">The email message is permanently deleted after five years because the deletion action from the scoped retention policy takes precedence over the unscoped retention policy.</span></span>
        
        <span data-ttu-id="1fca5-399">示例2：用户的OneDrive帐户中的文档受两个保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="1fca5-399">Example 2: A document in a user's OneDrive account is subject to two retention policies.</span></span> <span data-ttu-id="1fca5-400">第一个保留策略的范围包括该用户的OneDrive帐户，并在10年后执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-400">The first retention policy is scoped to include this user's OneDrive account and has a delete action after 10 years.</span></span> <span data-ttu-id="1fca5-401">第二个保留策略的范围包括该用户的OneDrive帐户，并且七年后将执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-401">The second retention policy is scoped to include this user's OneDrive account and has a delete action after seven years.</span></span>
        
        <span data-ttu-id="1fca5-402">由于两个保留策略都已确定范围，因此无法在此级别确定何时永久性删除此文档。</span><span class="sxs-lookup"><span data-stu-id="1fca5-402">When this document will be permanently deleted can't be determined at this level because both retention policies are scoped.</span></span>

4. <span data-ttu-id="1fca5-403">**最短删除期优先。**</span><span class="sxs-lookup"><span data-stu-id="1fca5-403">**The shortest deletion period wins.**</span></span> <span data-ttu-id="1fca5-404">适用于确定何时从保留策略中删除项目以及从上一级别无法解决结果：在最短保留期结束时永久性删除内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-404">Applicable to determine when items will be deleted from retention policies and the outcome couldn't be resolved from the previous level: Content is permanently deleted at the end of the shortest retention period.</span></span>
    
    <span data-ttu-id="1fca5-405">示例：用户的OneDrive帐户中的文档受两个保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="1fca5-405">Example: A document in a user's OneDrive account is subject to two retention policies.</span></span> <span data-ttu-id="1fca5-406">第一个保留策略的范围包括该用户的OneDrive帐户，并在10年后执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-406">The first retention policy is scoped to include this user's OneDrive account and has a delete action after 10 years.</span></span> <span data-ttu-id="1fca5-407">第二个保留策略的范围包括该用户的OneDrive帐户，并且七年后将执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-407">The second retention policy is scoped to include this user's OneDrive account and has a delete action after seven years.</span></span>
    
    <span data-ttu-id="1fca5-408">七年后将永久性删除此文档，因为这是这两个范围的保留策略的最短保留期。</span><span class="sxs-lookup"><span data-stu-id="1fca5-408">This document will be permanently deleted after seven years because that's the shortest retention period for these two scoped retention policies.</span></span>

<span data-ttu-id="1fca5-409">请注意，受到电子数据展示保留的项目也属于保留的第一原则；任何保留策略或保留标签都不能永久性删除它们。</span><span class="sxs-lookup"><span data-stu-id="1fca5-409">Note that items subject to eDiscovery hold also fall under the first principle of retention; they cannot be permanently deleted by any retention policy or retention label.</span></span> <span data-ttu-id="1fca5-410">解除保留后，保留原则将继续适用于它们。</span><span class="sxs-lookup"><span data-stu-id="1fca5-410">When that hold is released, the principles of retention continue to apply to them.</span></span> <span data-ttu-id="1fca5-411">例如，它们然后可能会受到未期满的保留期限或删除操作。</span><span class="sxs-lookup"><span data-stu-id="1fca5-411">For example, they could then be subject to an unexpired retention period or a delete action.</span></span>

<span data-ttu-id="1fca5-412">结合了保留和删除操作的更复杂的示例：</span><span class="sxs-lookup"><span data-stu-id="1fca5-412">More complex examples that combine retain and delete actions:</span></span>

1. <span data-ttu-id="1fca5-413">一个项目已应用以下保留设置：</span><span class="sxs-lookup"><span data-stu-id="1fca5-413">An item has the following retention settings applied to it:</span></span>
    
    - <span data-ttu-id="1fca5-414">五年后只能删除的保留政策</span><span class="sxs-lookup"><span data-stu-id="1fca5-414">A retention policy for delete-only after five years</span></span>
    - <span data-ttu-id="1fca5-415">保留政策，保留三年然后删除</span><span class="sxs-lookup"><span data-stu-id="1fca5-415">A retention policy that retains for three years and then deletes</span></span>
    - <span data-ttu-id="1fca5-416">仅保留七年的保留标签</span><span class="sxs-lookup"><span data-stu-id="1fca5-416">A retention label that retains-only for seven years</span></span>
    
    <span data-ttu-id="1fca5-417">**结果**：该项目保留7年，因为保留优先于删除，并且7年是最长的保留期。</span><span class="sxs-lookup"><span data-stu-id="1fca5-417">**Outcome**: The item is retained for seven years because retention takes precedence over deletion and seven years is the longest retention period.</span></span> <span data-ttu-id="1fca5-418">在此保留期结束时，由于保留政策的删除操作，该项目将永久性删除。</span><span class="sxs-lookup"><span data-stu-id="1fca5-418">At the end of this retention period, the item is permanently deleted because of the delete action from the retention policies.</span></span>
    
    <span data-ttu-id="1fca5-419">尽管两种保留策略的删除操作日期不同，但是最早可以永久性删除的项目是最长保留期（比两个删除日期长）的结束。</span><span class="sxs-lookup"><span data-stu-id="1fca5-419">Although the two retention policies have different dates for the delete actions, the earliest the item can be permanently deleted is at the end of the longest retention period, which is longer than both deletion dates.</span></span> 

2.  <span data-ttu-id="1fca5-420">一个项目已应用以下保留设置：</span><span class="sxs-lookup"><span data-stu-id="1fca5-420">An item has the following retention settings applied to it:</span></span>
    
    - <span data-ttu-id="1fca5-421">不受限制的保留策略，仅在十年后删除</span><span class="sxs-lookup"><span data-stu-id="1fca5-421">An unscoped retention policy that deletes-only after ten years</span></span>
    - <span data-ttu-id="1fca5-422">有范围的保留策略，可以保留五年然后删除</span><span class="sxs-lookup"><span data-stu-id="1fca5-422">A scoped retention policy that retains for five years and then deletes</span></span>
    - <span data-ttu-id="1fca5-423">保留标签，保留三年，然后删除</span><span class="sxs-lookup"><span data-stu-id="1fca5-423">A retention label that retains for three years and then deletes</span></span>
    
    <span data-ttu-id="1fca5-424">**结果**：该项目将保留五年，因为这是最长的保留期。</span><span class="sxs-lookup"><span data-stu-id="1fca5-424">**Outcome**: The item is retained for five years because that's the longest retention period.</span></span> <span data-ttu-id="1fca5-425">在该保留期结束时，由于保留标签三年的删除操作，该项目将永久性删除。</span><span class="sxs-lookup"><span data-stu-id="1fca5-425">At the end of that retention period, the item is permanently deleted because of the delete action of three years from the retention label.</span></span> <span data-ttu-id="1fca5-426">从保留标签中删除优先于从所有保留策略中删除。</span><span class="sxs-lookup"><span data-stu-id="1fca5-426">Deletion from retention labels takes precedence over deletion from all retention policies.</span></span> <span data-ttu-id="1fca5-427">在此示例中，所有冲突都由第三个级别解决。</span><span class="sxs-lookup"><span data-stu-id="1fca5-427">In this example, all conflicts are resolved by the third level.</span></span>

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a><span data-ttu-id="1fca5-428">使用保存锁来限制对策略的更改</span><span class="sxs-lookup"><span data-stu-id="1fca5-428">Use Preservation Lock to restrict changes to policies</span></span>

<span data-ttu-id="1fca5-429">某些组织可能需要遵从由监管机构定义的规则，如美国证券交易委员会 (SEC) 规则 17a-4，该规则要求在启用保留策略之后，不得关闭该策略或降低其限制。</span><span class="sxs-lookup"><span data-stu-id="1fca5-429">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a policy for retention is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="1fca5-430">保存锁可确保组织符合此类监管要求，因为它可以锁定保留策略或保留标签策略，因此任何人（包括管理员）都无法关闭该策略、删除该策略或降低其限制性。</span><span class="sxs-lookup"><span data-stu-id="1fca5-430">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy or retention label policy so that no one—including an administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="1fca5-431">在创建保留策略或保留标签策略后应用保存锁。</span><span class="sxs-lookup"><span data-stu-id="1fca5-431">You apply Preservation Lock after the retention policy or retention label policy is created.</span></span> <span data-ttu-id="1fca5-432">有关更多信息和说明，请参阅 [使用保存锁来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-432">For more information and instructions, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="releasing-a-policy-for-retention"></a><span data-ttu-id="1fca5-433">发布保留策略</span><span class="sxs-lookup"><span data-stu-id="1fca5-433">Releasing a policy for retention</span></span>

<span data-ttu-id="1fca5-434">如果你的保留策略没有保留锁，你可以随时删除你的策略，这将有效地关闭之前应用的保留设置。</span><span class="sxs-lookup"><span data-stu-id="1fca5-434">Providing your policies for retention don't have a Preservation Lock, you can delete your policies at any time, which effectively turns off the previously applied retention settings.</span></span> <span data-ttu-id="1fca5-435">你也可以保留该策略，但将位置状态更改为关闭，或禁用该策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-435">You can also keep the policy, but change the location status to off, or disable the policy.</span></span> <span data-ttu-id="1fca5-436">如果策略配置为包含 SharePoint 的特定网站或 OneDrive 帐户，则还可以编辑该策略以删除其中一个或多个条目，以发布这些网站或帐户的策略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-436">If your policy is configured to include specific sites for SharePoint or accounts for OneDrive, you can also edit the policy to remove one or more of these entries to release the policy for those sites or accounts.</span></span>
 
<span data-ttu-id="1fca5-437">执行上述任一操作时，任何受策略保留限制的 SharePoint 或 OneDrive 内容将继续保留 30 天，以防止意外丢失数据。</span><span class="sxs-lookup"><span data-stu-id="1fca5-437">When you do any of these actions, any SharePoint or OneDrive content that's subject to retention from the policy continues to be retained for 30 days to prevent inadvertent data loss.</span></span> <span data-ttu-id="1fca5-438">在此 30 天宽限期内，将仍然保留已删除的文件（文件继续添加到保留库），但定期清理保留库的计时器作业将为这些作业暂停，以便必要时可还原这些文件。</span><span class="sxs-lookup"><span data-stu-id="1fca5-438">During this 30-day grace period deleted files are still retained (files continue to be added to the Preservation Hold library), but the timer job that periodically cleans up the Preservation Hold library is suspended for these files so you can restore them if necessary.</span></span>

<span data-ttu-id="1fca5-439">此 30 天宽限期的例外情况是当更新策略以排除 SharePoint 的一个或多个网站或 OneDrive 帐户时；在这种情况下，计时器作业会删除保留库中这些位置的文件，而不会延迟 30 天。</span><span class="sxs-lookup"><span data-stu-id="1fca5-439">An exception to this 30-day grace period is when you update the policy to exclude one or more sites for SharePoint or accounts for OneDrive; in this case, the timer job deletes files for these locations in the Preservation Hold library without the 30-day delay.</span></span>

<span data-ttu-id="1fca5-440">有关保留库详细信息，请参阅 [如何为 SharePoint 和 OneDrive 应用设置](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-440">For more information about the Preservation Hold library, see [How retention works for SharePoint and OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span></span>

<span data-ttu-id="1fca5-441">由于宽限期内的行为，如果在30天内重新启用该策略或将位置状态更改为开启，策略将在这段时间内恢复，而不会有任何永久性数据丢失。</span><span class="sxs-lookup"><span data-stu-id="1fca5-441">Because of the behavior during the grace period, if you re-enable the policy or change the location status back to on within 30 days, the policy resumes without any permanent data loss during this time.</span></span>

## <a name="auditing-retention-configuration-and-actions"></a><span data-ttu-id="1fca5-442">审核保留配置和操作</span><span class="sxs-lookup"><span data-stu-id="1fca5-442">Auditing retention configuration and actions</span></span>

<span data-ttu-id="1fca5-443">[启用审核](turn-audit-log-search-on-or-off.md)时，管理配置（保留策略和保留标签）和保留操作（仅限保留标签）均支持保留审核事件。</span><span class="sxs-lookup"><span data-stu-id="1fca5-443">When [auditing is enabled](turn-audit-log-search-on-or-off.md), auditing events for retention are supported for both administration configuration (retention policies and retention labels) and retention actions (retention labels only).</span></span>

### <a name="auditing-retention-configuration"></a><span data-ttu-id="1fca5-444">审核保留配置</span><span class="sxs-lookup"><span data-stu-id="1fca5-444">Auditing retention configuration</span></span>

<span data-ttu-id="1fca5-445">创建、重新配置或删除保留策略或标签时，保留策略和保留标签的管理员配置将记录为审核事件。</span><span class="sxs-lookup"><span data-stu-id="1fca5-445">Administrator configuration for retention policies and retention labels are logged as auditing events when a retention policy or label is created, reconfigured, or deleted.</span></span>

<span data-ttu-id="1fca5-446">如需审核时间的完整列表，请参阅[保留策略和保留标签活动](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-446">For the full list of auditing events, see [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).</span></span>

### <a name="auditing-retention-actions"></a><span data-ttu-id="1fca5-447">审核保留操作</span><span class="sxs-lookup"><span data-stu-id="1fca5-447">Auditing retention actions</span></span>

<span data-ttu-id="1fca5-448">记录为审核事件的保留操作仅适用于保留标签，不适用于保留策略：</span><span class="sxs-lookup"><span data-stu-id="1fca5-448">Retention actions that are logged as auditing events are available only for retention labels and not for retention policies:</span></span>

- <span data-ttu-id="1fca5-449">在 SharePoint 或 OneDrive 的项中应用、更改或删除保留标签时：</span><span class="sxs-lookup"><span data-stu-id="1fca5-449">When a retention label is applied, changed, or removed from an item in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="1fca5-450">从 **文件和页面活动**，选择 **已更改文件保留标签**。</span><span class="sxs-lookup"><span data-stu-id="1fca5-450">From **File and page activities**, select **Changed retention label for a file**</span></span> 

- <span data-ttu-id="1fca5-451">当 SharePoint 中标记的项标记为记录，并且用户将其解锁或锁定时：</span><span class="sxs-lookup"><span data-stu-id="1fca5-451">When a labeled item in SharePoint is marked as a record, and it is unlocked or locked by a user:</span></span>
    - <span data-ttu-id="1fca5-452">从 **文件和页面活动**，选择 **已更改记录状态为解锁** 和 **更改记录状态为锁定**。</span><span class="sxs-lookup"><span data-stu-id="1fca5-452">From **File and page activities**, select **Changed record status to unlocked** and **Changed record status to locked**</span></span>

- <span data-ttu-id="1fca5-453">将内容标记为记录或法规记录的保留标签应用于 Exchange 中的项时：</span><span class="sxs-lookup"><span data-stu-id="1fca5-453">When a retention label that marks content as a record or regulatory record is applied to an item in Exchange:</span></span>
    - <span data-ttu-id="1fca5-454">从 **Exchange 邮箱活动中**，选择 **已标记消息为记录**</span><span class="sxs-lookup"><span data-stu-id="1fca5-454">From **Exchange mailbox activities**, select **Labeled message as a record**</span></span>

- <span data-ttu-id="1fca5-455">当 SharePoint，OneDrive 或 Exchange 中标记的项标记为记录或法规记录，并将其永久删除时：</span><span class="sxs-lookup"><span data-stu-id="1fca5-455">When a labeled item in SharePoint, OneDrive, or Exchange is marked as a record or regulatory record, and it is permanently deleted:</span></span>
    - <span data-ttu-id="1fca5-456">从 **文件和页面活动**，选择 **已删除标记为记录的文件**</span><span class="sxs-lookup"><span data-stu-id="1fca5-456">From **File and page activities**, select **Deleted file marked as a record**</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="1fca5-457">用于保留策略和保留标签的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="1fca5-457">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="1fca5-458">若要使用保留 cmdlet，必须先[连接到 Office 365 安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-458">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="1fca5-459">然后，使用以下任何 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1fca5-459">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="1fca5-460">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="1fca5-460">Get-ComplianceTag</span></span>](/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="1fca5-461">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="1fca5-461">New-ComplianceTag</span></span>](/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="1fca5-462">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="1fca5-462">Remove-ComplianceTag</span></span>](/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="1fca5-463">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="1fca5-463">Set-ComplianceTag</span></span>](/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="1fca5-464">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="1fca5-464">Enable-ComplianceTagStorage</span></span>](/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="1fca5-465">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="1fca5-465">Get-ComplianceTagStorage</span></span>](/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="1fca5-466">Get-RecordReviewNotificationTemplateConfig</span><span class="sxs-lookup"><span data-stu-id="1fca5-466">Get-RecordReviewNotificationTemplateConfig</span></span>](/powershell/module/exchange/get-recordreviewnotificationtemplateconfig)

- [<span data-ttu-id="1fca5-467">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="1fca5-467">Get-RetentionCompliancePolicy</span></span>](/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="1fca5-468">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="1fca5-468">New-RetentionCompliancePolicy</span></span>](/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="1fca5-469">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="1fca5-469">Remove-RetentionCompliancePolicy</span></span>](/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="1fca5-470">Set-RecordReviewNotificationTemplateConfig</span><span class="sxs-lookup"><span data-stu-id="1fca5-470">Set-RecordReviewNotificationTemplateConfig</span></span>](/powershell/module/exchange/set-recordreviewnotificationtemplateconfig )

- [<span data-ttu-id="1fca5-471">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="1fca5-471">Set-RetentionCompliancePolicy</span></span>](/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="1fca5-472">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="1fca5-472">Get-RetentionComplianceRule</span></span>](/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="1fca5-473">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="1fca5-473">New-RetentionComplianceRule</span></span>](/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="1fca5-474">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="1fca5-474">Remove-RetentionComplianceRule</span></span>](/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="1fca5-475">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="1fca5-475">Set-RetentionComplianceRule</span></span>](/powershell/module/exchange/set-retentioncompliancerule)


## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a><span data-ttu-id="1fca5-476">何时使用保留策略和保留标签或电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-476">When to use retention policies and retention labels or eDiscovery holds</span></span>

<span data-ttu-id="1fca5-477">虽然保留设置和[电子文件展示案列创建的保留](create-ediscovery-holds.md)都可以防止数据被永久删除，它们是针对不同情况设计的。</span><span class="sxs-lookup"><span data-stu-id="1fca5-477">Although retention settings and [holds that you create with an eDiscovery case](create-ediscovery-holds.md) can both prevent data from being permanently deleted, they are designed for different scenarios.</span></span> <span data-ttu-id="1fca5-478">为了帮助你了解差异并决定使用哪个，请使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="1fca5-478">To help you understand the differences and decide which to use, use the following guidance:</span></span>

- <span data-ttu-id="1fca5-479">在保留策略和保留标签中指定的保留设置旨在用于长期信息管理策略，以保留或删除符合法规要求的数据。</span><span class="sxs-lookup"><span data-stu-id="1fca5-479">Retention settings that you specify in retention policies and retention labels are designed for a long-term information governance strategy to retain or delete data for compliance requirements.</span></span> <span data-ttu-id="1fca5-480">通常范围很广，主要重点是位置和内容，而不是单个用户。</span><span class="sxs-lookup"><span data-stu-id="1fca5-480">The scope is usually broad with the main focus being the location and content rather than individual users.</span></span> <span data-ttu-id="1fca5-481">保留期的开始和结束是可配置的，可以选择自动删除内容，无需其他管理员干预。</span><span class="sxs-lookup"><span data-stu-id="1fca5-481">The start and end of the retention period is configurable, with the option to automatically delete content without additional administrator intervention.</span></span>

- <span data-ttu-id="1fca5-482">电子数据展示保留（核心电子数据展示或高级电子数据展示案例）的设计期限有限，可以保存数据以进行法律调查。</span><span class="sxs-lookup"><span data-stu-id="1fca5-482">Holds for eDiscovery (either Core eDiscovery or Advanced eDiscovery cases) are designed for a limited duration to preserve data for a legal investigation.</span></span> <span data-ttu-id="1fca5-483">范围是特定的，重点是已识别用户拥有的内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-483">The scope is specific with the focus being content owned by identified users.</span></span> <span data-ttu-id="1fca5-484">保留期的开始和结束是不可配置的，但取决于单个管理员的操作，如果保留被释放，则无法选择自动删除内容。</span><span class="sxs-lookup"><span data-stu-id="1fca5-484">The start and end of the preservation period isn't configurable but dependent on individual administrator actions, without an option to automatically delete content when the hold is released.</span></span>

<span data-ttu-id="1fca5-485">比较保留与电子数据展示保留的摘要：</span><span class="sxs-lookup"><span data-stu-id="1fca5-485">Summary to compare retention with holds:</span></span>

|<span data-ttu-id="1fca5-486">注意事项</span><span class="sxs-lookup"><span data-stu-id="1fca5-486">Consideration</span></span>|<span data-ttu-id="1fca5-487">保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-487">Retention</span></span> |<span data-ttu-id="1fca5-488">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-488">eDiscovery holds</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1fca5-489">业务需求：</span><span class="sxs-lookup"><span data-stu-id="1fca5-489">Business need:</span></span> |<span data-ttu-id="1fca5-490">合规性</span><span class="sxs-lookup"><span data-stu-id="1fca5-490">Compliance</span></span> |<span data-ttu-id="1fca5-491">法律</span><span class="sxs-lookup"><span data-stu-id="1fca5-491">Legal</span></span> |
|<span data-ttu-id="1fca5-492">时间范围：</span><span class="sxs-lookup"><span data-stu-id="1fca5-492">Time scope:</span></span> |<span data-ttu-id="1fca5-493">长期</span><span class="sxs-lookup"><span data-stu-id="1fca5-493">Long-term</span></span> |<span data-ttu-id="1fca5-494">短期</span><span class="sxs-lookup"><span data-stu-id="1fca5-494">Short-term</span></span> |
|<span data-ttu-id="1fca5-495">焦点：</span><span class="sxs-lookup"><span data-stu-id="1fca5-495">Focus:</span></span> |<span data-ttu-id="1fca5-496">广泛、基于内容</span><span class="sxs-lookup"><span data-stu-id="1fca5-496">Broad, content-based</span></span> |<span data-ttu-id="1fca5-497">特定、基于用户</span><span class="sxs-lookup"><span data-stu-id="1fca5-497">Specific, user-based</span></span> |
|<span data-ttu-id="1fca5-498">开始和结束日期可配置：</span><span class="sxs-lookup"><span data-stu-id="1fca5-498">Start and end date configurable:</span></span> |<span data-ttu-id="1fca5-499">是</span><span class="sxs-lookup"><span data-stu-id="1fca5-499">Yes</span></span> |<span data-ttu-id="1fca5-500">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-500">No</span></span> |
|<span data-ttu-id="1fca5-501">内容删除：</span><span class="sxs-lookup"><span data-stu-id="1fca5-501">Content deletion:</span></span> |<span data-ttu-id="1fca5-502">是（可选）</span><span class="sxs-lookup"><span data-stu-id="1fca5-502">Yes (optional)</span></span> |<span data-ttu-id="1fca5-503">否</span><span class="sxs-lookup"><span data-stu-id="1fca5-503">No</span></span> |
|<span data-ttu-id="1fca5-504">管理开销：</span><span class="sxs-lookup"><span data-stu-id="1fca5-504">Administrative overheads:</span></span> |<span data-ttu-id="1fca5-505">低</span><span class="sxs-lookup"><span data-stu-id="1fca5-505">Low</span></span> |<span data-ttu-id="1fca5-506">高</span><span class="sxs-lookup"><span data-stu-id="1fca5-506">High</span></span> |

<span data-ttu-id="1fca5-507">如果内容遵循保留设置和电子数据展示保留，则保存电子数据展示保留的内容始终具有优先权。</span><span class="sxs-lookup"><span data-stu-id="1fca5-507">If content is subject to both retention settings and an eDiscovery hold, preserving content for the eDiscovery hold always takes precedence.</span></span> <span data-ttu-id="1fca5-508">这样，[保留原则](#the-principles-of-retention-or-what-takes-precedence)扩展到电子数据展示保留，因为它们保留数据，直到管理员手动释放保留为止。</span><span class="sxs-lookup"><span data-stu-id="1fca5-508">In this way, the [principles of retention](#the-principles-of-retention-or-what-takes-precedence) expand to eDiscovery holds because they preserve data until an administrator manually releases the hold.</span></span> <span data-ttu-id="1fca5-509">但是，尽管有此优先顺序，但不要将电子数据展示保留用于长期信息治理。</span><span class="sxs-lookup"><span data-stu-id="1fca5-509">However, despite this precedence, don't use eDiscovery holds for long-term information governance.</span></span> <span data-ttu-id="1fca5-510">如果担心自动删除数据，则可以将保留设置配置为永久保留项目，或将[处置审查](disposition.md#disposition-reviews)与保留标签一起使用。</span><span class="sxs-lookup"><span data-stu-id="1fca5-510">If you are concerned about automatic deletion of data, you can configure retention settings to retain items forever, or use [disposition review](disposition.md#disposition-reviews) with retention labels.</span></span>

<span data-ttu-id="1fca5-511">如果你使用的是旧的电子数据展示工具来保留数据，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="1fca5-511">If you are using older eDiscovery tools to preserve data, see the following resources:</span></span>

- <span data-ttu-id="1fca5-512">Exchange:</span><span class="sxs-lookup"><span data-stu-id="1fca5-512">Exchange:</span></span> 
    - [<span data-ttu-id="1fca5-513">就地保留和诉讼保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-513">In-Place Hold and Litigation Hold</span></span>](/exchange/security-and-compliance/in-place-and-litigation-holds)
    - [<span data-ttu-id="1fca5-514">如何识别为 Exchange Online 邮箱设置的保留类型</span><span class="sxs-lookup"><span data-stu-id="1fca5-514">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](./identify-a-hold-on-an-exchange-online-mailbox.md)

- <span data-ttu-id="1fca5-515">SharePoint 和 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="1fca5-515">SharePoint and OneDrive:</span></span> 
    - [<span data-ttu-id="1fca5-516">在电子数据展示中心将内容添加到事例并将源就地保留</span><span class="sxs-lookup"><span data-stu-id="1fca5-516">Add content to a case and place sources on hold in the eDiscovery Center</span></span>](/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)

- [<span data-ttu-id="1fca5-517">旧版电子数据展示工具的停用</span><span class="sxs-lookup"><span data-stu-id="1fca5-517">Retirement of legacy eDiscovery tools</span></span>](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="1fca5-518">使用保留策略和保留标签，而不是旧功能</span><span class="sxs-lookup"><span data-stu-id="1fca5-518">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="1fca5-519">如果需要在 Microsoft 365 中主动保留或删除内容来实现信息管理，建议使用保留策略和保留标签，而不是以下旧功能。</span><span class="sxs-lookup"><span data-stu-id="1fca5-519">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span>

<span data-ttu-id="1fca5-520">如果当前使用这些旧功能，可以继续将它们与保留策略和保留标签并行使用。</span><span class="sxs-lookup"><span data-stu-id="1fca5-520">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="1fca5-521">但我们建议今后使用保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="1fca5-521">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="1fca5-522">它们为你提供了在 Microsoft 365 中集中管理内容保留和删除的单一机制。</span><span class="sxs-lookup"><span data-stu-id="1fca5-522">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="1fca5-523">**Exchange Online 中的早期功能：**</span><span class="sxs-lookup"><span data-stu-id="1fca5-523">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="1fca5-524">[保留标记和保留策略](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)，亦称为[邮件传递记录管理 (MRM)](/exchange/security-and-compliance/messaging-records-management/messaging-records-management)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="1fca5-524">[Retention tags and retention policies](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies), also known as [messaging records management (MRM)](/exchange/security-and-compliance/messaging-records-management/messaging-records-management) (deletion only)</span></span>

<span data-ttu-id="1fca5-525">**SharePoint 和 OneDrive 中的早期功能：**</span><span class="sxs-lookup"><span data-stu-id="1fca5-525">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="1fca5-526">[文档删除策略](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff)（仅删除）</span><span class="sxs-lookup"><span data-stu-id="1fca5-526">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="1fca5-527">[配置就地记录管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a)（仅限保留）</span><span class="sxs-lookup"><span data-stu-id="1fca5-527">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="1fca5-528">[使用网站关闭和删除策略](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="1fca5-528">[Use policies for site closure and deletion](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span>
    
- <span data-ttu-id="1fca5-529">[信息管理策略](intro-to-info-mgmt-policies.md)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="1fca5-529">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="1fca5-530">如果已将 SharePoint 网站配置为应用保留列表或库的内容的内容类型策略或信息管理策略，则这些策略会在保留策略生效时被忽略。</span><span class="sxs-lookup"><span data-stu-id="1fca5-530">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="1fca5-531">相关信息</span><span class="sxs-lookup"><span data-stu-id="1fca5-531">Related information</span></span>

- [<span data-ttu-id="1fca5-532">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="1fca5-532">SharePoint Online Limits</span></span>](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="1fca5-533">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="1fca5-533">Limits and specifications for Microsoft Teams</span></span>](/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="1fca5-534">有助于你满足信息治理和记录管理监管要求的资源</span><span class="sxs-lookup"><span data-stu-id="1fca5-534">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)

## <a name="configuration-guidance"></a><span data-ttu-id="1fca5-535">配置指南</span><span class="sxs-lookup"><span data-stu-id="1fca5-535">Configuration guidance</span></span>

<span data-ttu-id="1fca5-536">请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="1fca5-536">See [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span> <span data-ttu-id="1fca5-537">本文提供了有关订阅、权限的信息，以及保留方案的端到端配置指南链接。</span><span class="sxs-lookup"><span data-stu-id="1fca5-537">This article has information about subscriptions, permissions, and links to end-to-end configuration guidance for retention scenarios.</span></span>