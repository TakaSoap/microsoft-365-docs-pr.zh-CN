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
ms.openlocfilehash: 50bbe9d80b7b0a1b9fa346fd6e5abc8971dadcfb
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804755"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="45576-103">了解保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="45576-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="45576-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="45576-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="45576-p101">对于大多数组织，数据量和数据复杂性每天都在增加 — 包括电子邮件、文档、即时消息等。有效管理或管理此类信息非常重要，因为要：</span><span class="sxs-lookup"><span data-stu-id="45576-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="45576-107">**主动遵守规定至少必须在一段时间内保留内容的行业法规和内部策略** ：例如，《萨班斯-奥克斯利法案》规定，必须保留特定类型的内容七年。</span><span class="sxs-lookup"><span data-stu-id="45576-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 

- <span data-ttu-id="45576-108">**降低发生诉讼或出现安全漏洞的风险** ：通过永久删除不再需要保留的旧内容。</span><span class="sxs-lookup"><span data-stu-id="45576-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="45576-109">**帮助组织有效共享知识并提高敏捷性** ：通过确保用户仅处理与自己相关的最新内容。</span><span class="sxs-lookup"><span data-stu-id="45576-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="45576-110">你配置的保留设置可有助于实现所有这些目标。</span><span class="sxs-lookup"><span data-stu-id="45576-110">Retention settings that you configure can help you achieve all these goals.</span></span> <span data-ttu-id="45576-111">管理内容通常需要执行两项操作：</span><span class="sxs-lookup"><span data-stu-id="45576-111">Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="45576-112">**保留** 内容，这样除非保留期到期，否则无法永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="45576-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="45576-113">在保留期到期时永久 **删除** 内容。</span><span class="sxs-lookup"><span data-stu-id="45576-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    

<span data-ttu-id="45576-114">通过这两项保留操作，可以配置保留设置来实现以下结果：</span><span class="sxs-lookup"><span data-stu-id="45576-114">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="45576-115">仅保留：永久或在指定的时间段内保留内容。</span><span class="sxs-lookup"><span data-stu-id="45576-115">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="45576-116">仅删除：在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="45576-116">Delete-only: Delete content after a specified period of time.</span></span>
- <span data-ttu-id="45576-117">保留后删除：在指定的时间段内保留内容后删除内容。</span><span class="sxs-lookup"><span data-stu-id="45576-117">Retain and then delete: Retain content for a specified period of time and then delete it.</span></span>

<span data-ttu-id="45576-118">这些保留设置应用于在适当位置上的内容，如果你出于合规性原因需要保留内容，它们可以为你节省创建和配置附加存储的额外开销。</span><span class="sxs-lookup"><span data-stu-id="45576-118">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons.</span></span> <span data-ttu-id="45576-119">另外，无需实现自定义流程来复制和同步此数据。</span><span class="sxs-lookup"><span data-stu-id="45576-119">In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="45576-120">保留设置如何应用于在适当位置上的内容</span><span class="sxs-lookup"><span data-stu-id="45576-120">How retention settings work with content in place</span></span>

<span data-ttu-id="45576-121">分配有保留设置的内容保留在它的原始位置上。</span><span class="sxs-lookup"><span data-stu-id="45576-121">When content has retention settings assigned to it, that content remains in its original location.</span></span> <span data-ttu-id="45576-122">用户可以继续处理自己的文档或邮件，就像什么都没有改变一样。</span><span class="sxs-lookup"><span data-stu-id="45576-122">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="45576-123">不过，如果用户编辑或删除包含在保留策略中的内容，则会自动保留内容的副本，与在应用保留设置时存在的内容一样。</span><span class="sxs-lookup"><span data-stu-id="45576-123">But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained as it existed when you applied the retention settings.</span></span>
  
- <span data-ttu-id="45576-124">对于 SharePoint 和 OneDrive 网站：副本保留在 **保留** 库中。</span><span class="sxs-lookup"><span data-stu-id="45576-124">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="45576-125">对于 Exchange 邮箱：副本保留在“可恢复项”  文件夹中。</span><span class="sxs-lookup"><span data-stu-id="45576-125">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="45576-126">对于 Teams 和 Yammer 消息：副本保留在 Exchange“ **可恢复项** ”文件夹内名为“ **SubstrateHolds** ”的隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="45576-126">For Teams and Yammer messages: The copy is retained in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="45576-127">保留库占用的存储计入网站的存储配额。</span><span class="sxs-lookup"><span data-stu-id="45576-127">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="45576-128">在对 SharePoint 和 Microsoft 365 组使用保留设置时，可能需要增加存储空间。</span><span class="sxs-lookup"><span data-stu-id="45576-128">You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="45576-129">这些安全位置和保留的内容对大部分用户不可见。</span><span class="sxs-lookup"><span data-stu-id="45576-129">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="45576-130">在大多数情况下，用户甚至不需要知道他们的内容遵循保留设置。</span><span class="sxs-lookup"><span data-stu-id="45576-130">In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="45576-131">若要详细了解保留设置如何用于不同的工作负载，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="45576-131">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="45576-132">了解用于 SharePoint 和 OneDrive 的保留</span><span class="sxs-lookup"><span data-stu-id="45576-132">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="45576-133">了解用于 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="45576-133">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="45576-134">了解用于 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="45576-134">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="45576-135">了解用于 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="45576-135">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="45576-136">保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="45576-136">Retention policies and retention labels</span></span>

<span data-ttu-id="45576-137">可以同时使用保留策略和保留标签来向内容分配保留设置。</span><span class="sxs-lookup"><span data-stu-id="45576-137">You can use both retention policies and retention labels to assign your retention settings to content.</span></span> 

<span data-ttu-id="45576-138">使用保留策略可以在网站或邮箱级别为内容分配相同的保留设置，使用保留标签可以在项（文件夹、文档、电子邮件）级别分配保留设置。</span><span class="sxs-lookup"><span data-stu-id="45576-138">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="45576-139">例如，如果某 SharePoint 网站中的所有文档都应保留 5 年，那么使用保留策略比将相同的保留标签应用于此网站中的所有文档更高效。</span><span class="sxs-lookup"><span data-stu-id="45576-139">For example, if all documents in a SharePoint site should be retained for 5 years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site.</span></span> <span data-ttu-id="45576-140">不过，如果此网站中的一些文档应保留 5 年，另一些文档应保留 10 年，那么保留策略就无法实现这一点。</span><span class="sxs-lookup"><span data-stu-id="45576-140">However, if some documents in that site should be retained for 5 years and others retained for 10 years, a retention policy wouldn't be able to do this.</span></span> <span data-ttu-id="45576-141">如果需要在项级别指定保留设置，请使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-141">When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="45576-142">与保留策略不同，如果内容被复制或移动到不同的 Microsoft 365 位置，保留标签的保留设置仍继续应用在内容上。</span><span class="sxs-lookup"><span data-stu-id="45576-142">Unlike retention policies, retention settings from retention labels persist with the content if it’s copied or moved to a different Microsoft 365 location.</span></span> <span data-ttu-id="45576-143">另外，保留标签具有保留策略不支持的以下功能：</span><span class="sxs-lookup"><span data-stu-id="45576-143">In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="45576-144">除了根据内容年限或上次修改时间计算保留期之外，还可以从内容被标记时或根据事件开始计算保留期。</span><span class="sxs-lookup"><span data-stu-id="45576-144">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="45576-145">使用[可训练的分类器](classifier-learn-about.md)来标识要标记的内容。</span><span class="sxs-lookup"><span data-stu-id="45576-145">Use [trainable classifiers](classifier-learn-about.md) to identify content to label.</span></span>

- <span data-ttu-id="45576-146">为 SharePoint 文档应用默认标签。</span><span class="sxs-lookup"><span data-stu-id="45576-146">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="45576-147">支持[处置评审](disposition-reviews.md) ，以在永久删除内容前评审内容。</span><span class="sxs-lookup"><span data-stu-id="45576-147">Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="45576-148">将内容标记为[记录](records-management.md#records)作为标签设置的一部分，并对在保留期结束时删除的内容始终都有 [处置证明](disposition.md#disposition-of-records) 。</span><span class="sxs-lookup"><span data-stu-id="45576-148">Mark the content as a [record](records-management.md#records) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="45576-149">保留策略</span><span class="sxs-lookup"><span data-stu-id="45576-149">Retention policies</span></span>

<span data-ttu-id="45576-150">可以将保留策略应用于以下位置：</span><span class="sxs-lookup"><span data-stu-id="45576-150">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="45576-151">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="45576-151">Exchange email</span></span>
- <span data-ttu-id="45576-152">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="45576-152">SharePoint site</span></span>
- <span data-ttu-id="45576-153">OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="45576-153">OneDrive accounts</span></span>
- <span data-ttu-id="45576-154">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="45576-154">Microsoft 365 groups</span></span>
- <span data-ttu-id="45576-155">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="45576-155">Skype for Business</span></span>
- <span data-ttu-id="45576-156">Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="45576-156">Exchange public folders</span></span>
- <span data-ttu-id="45576-157">Teams 通道消息</span><span class="sxs-lookup"><span data-stu-id="45576-157">Teams channel messages</span></span>
- <span data-ttu-id="45576-158">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="45576-158">Teams chats</span></span>
- <span data-ttu-id="45576-159">yammer 社区消息</span><span class="sxs-lookup"><span data-stu-id="45576-159">Yammer community messages</span></span>
- <span data-ttu-id="45576-160">Yammer 私信</span><span class="sxs-lookup"><span data-stu-id="45576-160">Yammer private messages</span></span>

<span data-ttu-id="45576-161">可以非常高效地将一个策略应用于多个位置，也可以应用于特定的位置或用户。</span><span class="sxs-lookup"><span data-stu-id="45576-161">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>
    
<span data-ttu-id="45576-162">还可以将策略应用于所有内容，或应用于满足特定条件（如包含关键字或[敏感信息类型](sensitive-information-type-entity-definitions.md)）的内容。</span><span class="sxs-lookup"><span data-stu-id="45576-162">You can also apply a policy to all content or to content when it meets specific conditions, such as content that contains keywords or [sensitive information types](sensitive-information-type-entity-definitions.md).</span></span>

#### <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a><span data-ttu-id="45576-163">使用保留锁定遵从合规性要求</span><span class="sxs-lookup"><span data-stu-id="45576-163">Use Preservation Lock to comply with regulatory requirements</span></span>

<span data-ttu-id="45576-164">某些组织可能需要遵从由监管机构定义的规则，如美国证券交易委员会 (SEC) 规则 17a-4，这要求在某个保留策略启用后，不得关闭该策略或减少其限制。</span><span class="sxs-lookup"><span data-stu-id="45576-164">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="45576-165">保留锁定可确保组织符合此类法规要求，因为它可以锁定保留策略，这样包括管理员在内的任何人都无法禁用策略、删除策略或减少对策略的限制。</span><span class="sxs-lookup"><span data-stu-id="45576-165">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy so that no one—including the administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="45576-166">锁定某个保留策略后：</span><span class="sxs-lookup"><span data-stu-id="45576-166">When a retention policy is locked:</span></span>

- <span data-ttu-id="45576-167">任何人都无法关闭它</span><span class="sxs-lookup"><span data-stu-id="45576-167">No one can turn it off</span></span>
- <span data-ttu-id="45576-168">可以添加位置，但不能删除位置</span><span class="sxs-lookup"><span data-stu-id="45576-168">Locations can be added but not removed</span></span>
- <span data-ttu-id="45576-169">无法在保留期内修改或删除受策略制约的内容</span><span class="sxs-lookup"><span data-stu-id="45576-169">Content subject to the policy can't be modified or deleted during the retention period</span></span>
- <span data-ttu-id="45576-170">可以延长保留期，但不能缩短保留期</span><span class="sxs-lookup"><span data-stu-id="45576-170">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="45576-171">总而言之，锁定的保留策略可以增加或扩展锁定的策略，但不能减少或关闭策略。</span><span class="sxs-lookup"><span data-stu-id="45576-171">In summary, a locked retention policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="45576-172">在锁定保留策略之前，请务必了解这样做的影响，并确认组织是否需要这样做来遵守法规要求。</span><span class="sxs-lookup"><span data-stu-id="45576-172">Before you lock a retention policy, it's critical that you understand the impact and confirm whether it's required for your organization to meet regulatory requirements.</span></span> <span data-ttu-id="45576-173">在应用保留锁定后，管理员便无法禁用或删除保留策略。</span><span class="sxs-lookup"><span data-stu-id="45576-173">Administrators won't be able to disable or delete a retention policy after the preservation lock is applied.</span></span>

<span data-ttu-id="45576-174">通过使用 PowerShell，在创建保留策略后应用保留锁定。</span><span class="sxs-lookup"><span data-stu-id="45576-174">You apply Preservation Lock after the retention policy is created, by using PowerShell.</span></span> <span data-ttu-id="45576-175">说明已经包含在[创建和配置保留策略](create-retention-policies.md)中。</span><span class="sxs-lookup"><span data-stu-id="45576-175">Instructions are included in [Create and configure retention policies](create-retention-policies.md).</span></span>

#### <a name="releasing-a-retention-policy"></a><span data-ttu-id="45576-176">解除保留策略</span><span class="sxs-lookup"><span data-stu-id="45576-176">Releasing a retention policy</span></span>

<span data-ttu-id="45576-177">若保留策略没有保留锁定，则可随时关闭或删除它。</span><span class="sxs-lookup"><span data-stu-id="45576-177">Providing your retention policy doesn't have a Preservation Lock, you can turn off or delete a retention policy at any time.</span></span> 

<span data-ttu-id="45576-178">当你这样做时，任何被保留在保留库中的 SharePoint 或 OneDrive 内容都不会立即遭永久删除。</span><span class="sxs-lookup"><span data-stu-id="45576-178">When you do so, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="45576-179">相反，为了防止意外的数据丢失，我们设置了 30 天的宽限期。在此期间，相应策略的内容不会在保留库中到期，所以你可以根据需要从其中还原任何内容。</span><span class="sxs-lookup"><span data-stu-id="45576-179">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="45576-180">此外，在宽限期内无法手动删除此内容。</span><span class="sxs-lookup"><span data-stu-id="45576-180">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="45576-181">可在宽限期内重新启用保留策略，相应策略的任何内容都不会遭删除。</span><span class="sxs-lookup"><span data-stu-id="45576-181">You can turn on the retention policy again during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="45576-182">SharePoint 和 OneDrive 中的此 30 天宽限期对应于 Exchange 中的 30 天延迟保留。</span><span class="sxs-lookup"><span data-stu-id="45576-182">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="45576-183">有关详细信息，请参阅[管理延迟保留的邮箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。</span><span class="sxs-lookup"><span data-stu-id="45576-183">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="45576-184">保留标签</span><span class="sxs-lookup"><span data-stu-id="45576-184">Retention labels</span></span>

<span data-ttu-id="45576-185">对于需要不同保留设置的不同类型的内容，可以使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-185">Use retention labels for different types of content that require different retention settings.</span></span> <span data-ttu-id="45576-186">例如：</span><span class="sxs-lookup"><span data-stu-id="45576-186">For example:</span></span>
  
- <span data-ttu-id="45576-187">至少必须保留一段时间的税务表单。</span><span class="sxs-lookup"><span data-stu-id="45576-187">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="45576-188">达到特定年限后必须永久删除的新闻材料。</span><span class="sxs-lookup"><span data-stu-id="45576-188">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="45576-189">必须在保留一段时间后永久删除的竞争性研究。</span><span class="sxs-lookup"><span data-stu-id="45576-189">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="45576-190">必须标记为记录以免被编辑或删除的工作签证。</span><span class="sxs-lookup"><span data-stu-id="45576-190">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="45576-191">在所有这些情况下，可以使用保留标签在项（文档或电子邮件）级别应用保留设置来实现管理控制。</span><span class="sxs-lookup"><span data-stu-id="45576-191">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="45576-192">使用保留标签，你可以：</span><span class="sxs-lookup"><span data-stu-id="45576-192">With retention labels, you can:</span></span>
  
- <span data-ttu-id="45576-193">**允许组织中的人员将保留标签手动应用于** Outlook 和 Outlook 网页版、OneDrive、SharePoint​​ 和 Microsoft 365 组中的内容。</span><span class="sxs-lookup"><span data-stu-id="45576-193">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups.</span></span> <span data-ttu-id="45576-194">用户通常最了解自己处理的内容的类型，因此他们可以对内容进行分类，并应用适当的保留设置。</span><span class="sxs-lookup"><span data-stu-id="45576-194">Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="45576-195">**将保留标签自动应用于** 符合特定条件的内容，如内容包含：</span><span class="sxs-lookup"><span data-stu-id="45576-195">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="45576-196">特定类型敏感信息。</span><span class="sxs-lookup"><span data-stu-id="45576-196">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="45576-197">与所创建的查询匹配的特定关键字。</span><span class="sxs-lookup"><span data-stu-id="45576-197">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="45576-198">可训练分类器的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="45576-198">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="45576-199">**从内容被标记时开始计算保留期** ，适用于 SharePoint 网站和 OneDrive 帐户中的文档，以及除日历项外的电子邮件项。</span><span class="sxs-lookup"><span data-stu-id="45576-199">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items.</span></span> <span data-ttu-id="45576-200">如果你将具有此配置的保留标签应用于日历项，保留期从日历项发送时开始计算。</span><span class="sxs-lookup"><span data-stu-id="45576-200">If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="45576-201">**从事件发生时开始计算保留期** ，如员工离开组织或合同到期。</span><span class="sxs-lookup"><span data-stu-id="45576-201">**Start the retention period when an event occurs** , such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="45576-202">**将默认保留标签应用于 SharePoint 中的文档库、文件夹或文档集** ，以让存储在该位置的所有文档都继承默认保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-202">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="45576-203">此外，保留标签支持跨 Microsoft 365 应用和服务对电子邮件和文档实施[记录管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="45576-203">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services.</span></span> <span data-ttu-id="45576-204">可使用保留标签将项目标记为记录。</span><span class="sxs-lookup"><span data-stu-id="45576-204">You can use a retention label to mark items as a record.</span></span> <span data-ttu-id="45576-205">如果发生这种情况，而内容仍保留在 Microsoft 365 中，则标签会对内容进行进一步的限制，这可能是监管原因所致。</span><span class="sxs-lookup"><span data-stu-id="45576-205">When this happens and the content remains in Microsoft 365, the label places further restrictions on the content that might be needed for regulatory reasons.</span></span> <span data-ttu-id="45576-206">有关详细信息，请参阅[比较对允许或阻止的操作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="45576-206">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

<span data-ttu-id="45576-207">如果内容被移动到 Microsoft 365 之外，则保留标签将不会继续存在，这一点与[敏感度标签](sensitivity-labels.md)是不同的。</span><span class="sxs-lookup"><span data-stu-id="45576-207">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="45576-208">租户支持的保留标签数没有限制。</span><span class="sxs-lookup"><span data-stu-id="45576-208">There is no limit to the number of retention labels that are supported for a tenant.</span></span> <span data-ttu-id="45576-209">但是，租户支持的最大策略数为 10,000，其中包括应用标签的策略（保留标签策略和自动应用保留策略）以及保留策略。</span><span class="sxs-lookup"><span data-stu-id="45576-209">However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="45576-210">对内容分类但不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="45576-210">Classifying content without applying any actions</span></span>

<span data-ttu-id="45576-211">虽然保留标签的主要用途是保留或删除内容，但也可以在使用保留标签时不启用任何保留或其他操作。</span><span class="sxs-lookup"><span data-stu-id="45576-211">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions.</span></span> <span data-ttu-id="45576-212">在这种情况下，可以简单地将保留标签用作文本标签，而不强制执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="45576-212">In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="45576-213">例如，可以创建并应用名为“稍后评审”且不含任何操作的保留标签，稍后使用此标签来查找相应内容。</span><span class="sxs-lookup"><span data-stu-id="45576-213">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![将设置标记为仅分类](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="45576-215">将保留标签用作 DLP 策略中的条件</span><span class="sxs-lookup"><span data-stu-id="45576-215">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="45576-216">对于 SharePoint 中的文档，可以将保留标签指定为数据丢失防护 (DLP) 策略中的条件。</span><span class="sxs-lookup"><span data-stu-id="45576-216">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint.</span></span> <span data-ttu-id="45576-217">例如，配置一个 DLP 策略，以防在组织外部共享应用了指定保留标签的文档。</span><span class="sxs-lookup"><span data-stu-id="45576-217">For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="45576-218">有关详细信息，请参阅[将保留标签用作 DLP 策略中的条件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="45576-218">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="45576-219">保留标签和应用它们的策略</span><span class="sxs-lookup"><span data-stu-id="45576-219">Retention labels and policies that apply them</span></span>

<span data-ttu-id="45576-220">保留标签是独立的可重用的构建基块。</span><span class="sxs-lookup"><span data-stu-id="45576-220">Retention labels are independent, reusable building blocks.</span></span> <span data-ttu-id="45576-221">保留标签策略的主要目的是对一组保留标签进行分组，并指定要显示标签的位置。</span><span class="sxs-lookup"><span data-stu-id="45576-221">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span> <span data-ttu-id="45576-222">然后，管理员和用户可以将这些标签应用于这些位置中的内容。</span><span class="sxs-lookup"><span data-stu-id="45576-222">Then, admins and users can apply those labels to content in those locations.</span></span>
  
![标签、标签策略和位置的关系图](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
<span data-ttu-id="45576-224">在你发布保留标签后，它们包含在保留标签策略中，以供管理员和用户选择：</span><span class="sxs-lookup"><span data-stu-id="45576-224">When you publish retention labels, they're included in a retention label policy that make them available for admins and users to select:</span></span>

- <span data-ttu-id="45576-225">一个保留标签可以包含在多个保留标签策略中。</span><span class="sxs-lookup"><span data-stu-id="45576-225">A single retention label can be included in many retention label policies.</span></span>

- <span data-ttu-id="45576-226">保留标签策略指定了保留标签的发布位置。</span><span class="sxs-lookup"><span data-stu-id="45576-226">Retention label policies specify the locations to publish the retention labels.</span></span>

- <span data-ttu-id="45576-227">一个位置也可以包含在多个保留标签策略中。</span><span class="sxs-lookup"><span data-stu-id="45576-227">A single location can also be included in many retention label policies.</span></span>

<span data-ttu-id="45576-228">除了保留标签策略之外，还可以创建一个或多个自动应用策略，每个策略都有一个保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-228">In addition to retention label policies, you can also create one or more auto-apply policies, each with a single retention label.</span></span> <span data-ttu-id="45576-229">如果使用此策略，当满足你在策略中指定的条件时，保留标签就会自动应用。</span><span class="sxs-lookup"><span data-stu-id="45576-229">With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span> 

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="45576-230">保留标签策略和位置</span><span class="sxs-lookup"><span data-stu-id="45576-230">Retention label policies and locations</span></span>

<span data-ttu-id="45576-231">不同类型的保留标签可发布到不同位置，具体视保留标签用途而定。</span><span class="sxs-lookup"><span data-stu-id="45576-231">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="45576-232">如果保留标签是…</span><span class="sxs-lookup"><span data-stu-id="45576-232">If the retention label is…</span></span> | <span data-ttu-id="45576-233">可以将标签策略应用于…</span><span class="sxs-lookup"><span data-stu-id="45576-233">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="45576-234">发布给管理员和最终用户</span><span class="sxs-lookup"><span data-stu-id="45576-234">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="45576-235">Exchange、SharePoint、OneDrive、Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="45576-235">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="45576-236">根据敏感信息类型或可训练的分类器自动应用</span><span class="sxs-lookup"><span data-stu-id="45576-236">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="45576-237">Exchange（仅全部邮箱）、SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="45576-237">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="45576-238">根据查询自动应用</span><span class="sxs-lookup"><span data-stu-id="45576-238">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="45576-239">Exchange、SharePoint、OneDrive、Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="45576-239">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="45576-240">在 Exchange 中，自动应用保留标签只会应用于新发送的邮件（传输中的数据），而不是应用于邮箱中当前的所有项（静态数据）。</span><span class="sxs-lookup"><span data-stu-id="45576-240">In Exchange, auto-apply retention labels are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="45576-241">此外，用于敏感信息类型和可训练的分类器的自动应用保留标签应用于所有邮箱；你无法选择特定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="45576-241">Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="45576-242">Exchange 公用文件夹、Skype、Teams 和 Yammer 消息不支持保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-242">Exchange public folders, Skype, Teams and Yammer messages do not support retention labels.</span></span> <span data-ttu-id="45576-243">若要保留并从这些位置中删除内容，请改用保留策略。</span><span class="sxs-lookup"><span data-stu-id="45576-243">To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="45576-244">一次只能分配一个保留标签</span><span class="sxs-lookup"><span data-stu-id="45576-244">Only one retention label at a time</span></span>

<span data-ttu-id="45576-245">电子邮件或文档一次只能分配有一个保留标签：</span><span class="sxs-lookup"><span data-stu-id="45576-245">An email or document can have only a single retention label assigned to it at a time:</span></span>
  
- <span data-ttu-id="45576-246">对于管理员或最终用户手动分配的保留标签，用户可删除或更改所分配的保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-246">For retention labels assigned manually by admins or end users, people can remove or change the retention label that's assigned.</span></span>
    
- <span data-ttu-id="45576-247">如果内容已分配有自动应用标签，可以将此标签替换为发布的保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-247">If content has an auto-apply label assigned, this label can be replaced by a published retention label.</span></span>
    
- <span data-ttu-id="45576-248">如果内容已分配有发布的保留标签，无法将此标签替换为自动应用标签。</span><span class="sxs-lookup"><span data-stu-id="45576-248">If content has a published retention label assigned, an auto-apply label cannot replace it.</span></span>
    
- <span data-ttu-id="45576-249">若有多个规则要分配自动应用标签，且内容满足多个规则的条件，那么分配的是最早的（按创建日期）规则的保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-249">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule (by date created) is assigned.</span></span>
    
<span data-ttu-id="45576-250">若要了解如何以及为何应用一个保留标签（而非另一个），则了解显式分配标签和隐式分配标签之间的差异非常有用：</span><span class="sxs-lookup"><span data-stu-id="45576-250">To understand how and why one retention label is applied rather than another, it's helpful to understand the difference between explicitly assign a label, and implicitly assigned a label:</span></span>

- <span data-ttu-id="45576-251">通过标签策略应用的保留标签是显式分配的</span><span class="sxs-lookup"><span data-stu-id="45576-251">Retention labels applied from a label policy are explicitly assigned</span></span>
- <span data-ttu-id="45576-252">通过自动应用策略自动应用的保留标签是隐式分配的</span><span class="sxs-lookup"><span data-stu-id="45576-252">Retention labels applied automatically from an auto-apply policy are implicitly assigned</span></span>

<span data-ttu-id="45576-253">显式分配的保留标签优先于隐式分配的保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-253">An explicitly assigned retention label takes precedence over an implicitly assigned retention label.</span></span> <span data-ttu-id="45576-254">有关详细信息，请参阅本页上的[保留原则或优先性是什么？](retention.md#the-principles-of-retention-or-what-takes-precedence)部分。</span><span class="sxs-lookup"><span data-stu-id="45576-254">For more information, see the [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) section on this page.</span></span>

<span data-ttu-id="45576-255">对于 SharePoint，当您为 SharePoint 库、文件夹或文档集中的所有内容配置默认标签时，也可以隐式分配保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-255">For SharePoint, retention labels can also be implicitly assigned when you configure a default label for all content in a SharePoint library, folder, or document set.</span></span> <span data-ttu-id="45576-256">在这种情况下，自动应用标签优先于默认标签，但若要完全了解使用默认标签时的所有结果，请参阅[将默认保留标签应用于 SharePoint 库、文件夹或文档集中的所有内容](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)部分中的信息。</span><span class="sxs-lookup"><span data-stu-id="45576-256">For this scenario, an auto-applied label takes precedence over a default label, but to fully understand all outcomes when you use a default label, see the information in the [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) section.</span></span> 

#### <a name="monitoring-retention-labels"></a><span data-ttu-id="45576-257">监视保留标签</span><span class="sxs-lookup"><span data-stu-id="45576-257">Monitoring retention labels</span></span>

<span data-ttu-id="45576-258">在 Microsoft 365 合规中心，使用 **“数据分类”** > **“概述”** 来监视保留标签在租户中的使用方式，并确定已标记项目的位置。</span><span class="sxs-lookup"><span data-stu-id="45576-258">From the Microsoft 365 compliance center, use **Data classification** > **Overview** to monitor how your retention labels are being used in your tenant, and identify where your labeled items are located.</span></span> <span data-ttu-id="45576-259">有关详细信息（包括重要先决条件），请参阅[了解你的数据 - 数据分类概述](data-classification-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="45576-259">For more information, including important prerequisites, see [Know your data - data classification overview](data-classification-overview.md).</span></span>

<span data-ttu-id="45576-260">然后，你可以通过使用[内容资源管理器](data-classification-content-explorer.md)和[活动资源管理器](data-classification-activity-explorer.md)来深入了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="45576-260">You can then drill down into details by using [content explorer](data-classification-content-explorer.md) and [activity explorer](data-classification-activity-explorer.md).</span></span>

> [!TIP]
><span data-ttu-id="45576-261">请考虑使用其他的一些数据分类见解（如可训练分类器和敏感信息类型），帮助你识别可能需要保留或删除的内容，或者作为记录进行管理的内容。</span><span class="sxs-lookup"><span data-stu-id="45576-261">Consider using some of the other data classification insights, such as trainable classifiers and sensitive info types, to help you identify content that you might need to retain or delete, or manage as records.</span></span>

<span data-ttu-id="45576-262">Office 365 安全与合规中心的保留标签概述信息与 **“信息管理政策”** > **“仪表板”** 中的概述信息相同，更加详细的信息可以在 **“信息管理政策”** > **“标签活动资源管理器”** 中找到。</span><span class="sxs-lookup"><span data-stu-id="45576-262">The Office 365 Security & Compliance Center has the equivalent overview information for retention labels from **Information governance** > **Dashboard** , and more detailed information from **Information governance** > **Label activity explorer** .</span></span> <span data-ttu-id="45576-263">有关从较旧版本的管理中心监视保留标签的更多信息，请参阅以下文档：</span><span class="sxs-lookup"><span data-stu-id="45576-263">For more information about monitoring retention labels from this older admin center, see the following documentation:</span></span>
- [<span data-ttu-id="45576-264">查看数据管理报告</span><span class="sxs-lookup"><span data-stu-id="45576-264">View the data governance reports</span></span>](view-the-data-governance-reports.md)
- [<span data-ttu-id="45576-265">使用标签分析查看标签使用情况</span><span class="sxs-lookup"><span data-stu-id="45576-265">View label usage with label analytics</span></span>](label-analytics.md)
- [<span data-ttu-id="45576-266">查看文档的标签活动</span><span class="sxs-lookup"><span data-stu-id="45576-266">View label activity for documents</span></span>](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a><span data-ttu-id="45576-267">使用“内容搜索”来查找所有带有特定保留标签的内容</span><span class="sxs-lookup"><span data-stu-id="45576-267">Using Content Search to find all content with a specific retention label</span></span>

<span data-ttu-id="45576-268">在将保留标签应用到内容后（无论是由用户应用还是自动应用），你都可以通过内容搜索来查找已经应用特定保留标签的所有项目。</span><span class="sxs-lookup"><span data-stu-id="45576-268">After retention labels are applied to content, either by users or auto-applied, you can use content search to find all items that have a specific retention label applied.</span></span>

<span data-ttu-id="45576-269">创建内容搜索时，选择“ **保留标签** ”条件，然后输入完整的保留标签名称或标签名称的一部分，并使用通配符。</span><span class="sxs-lookup"><span data-stu-id="45576-269">When you create a content search, choose the **Retention label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="45576-270">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="45576-270">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![保留标签条件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="45576-272">比较保留策略和保留标签的功能</span><span class="sxs-lookup"><span data-stu-id="45576-272">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="45576-273">请使用下表来帮助你根据功能确定是使用保留策略还是保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-273">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="45576-274">功能</span><span class="sxs-lookup"><span data-stu-id="45576-274">Capability</span></span>|<span data-ttu-id="45576-275">保留策略</span><span class="sxs-lookup"><span data-stu-id="45576-275">Retention policy</span></span> |<span data-ttu-id="45576-276">保留标签</span><span class="sxs-lookup"><span data-stu-id="45576-276">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45576-277">保留设置可以是“保留后删除”、“仅保留”或“仅删除”</span><span class="sxs-lookup"><span data-stu-id="45576-277">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="45576-278">是</span><span class="sxs-lookup"><span data-stu-id="45576-278">Yes</span></span> |<span data-ttu-id="45576-279">是</span><span class="sxs-lookup"><span data-stu-id="45576-279">Yes</span></span> |
|<span data-ttu-id="45576-280">支持的工作负载：</span><span class="sxs-lookup"><span data-stu-id="45576-280">Workloads supported:</span></span> <br /><span data-ttu-id="45576-281">- Exchange</span><span class="sxs-lookup"><span data-stu-id="45576-281">- Exchange</span></span> <br /><span data-ttu-id="45576-282">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="45576-282">- SharePoint</span></span> <br /><span data-ttu-id="45576-283">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="45576-283">- OneDrive</span></span> <br /><span data-ttu-id="45576-284">- Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="45576-284">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="45576-285">- Skype for Business</span><span class="sxs-lookup"><span data-stu-id="45576-285">- Skype for Business</span></span> <br /><span data-ttu-id="45576-286">- Teams</span><span class="sxs-lookup"><span data-stu-id="45576-286">- Teams</span></span><br /><span data-ttu-id="45576-287">- Yammer</span><span class="sxs-lookup"><span data-stu-id="45576-287">- Yammer</span></span>|<br /> <span data-ttu-id="45576-288">是</span><span class="sxs-lookup"><span data-stu-id="45576-288">Yes</span></span> <br /> <span data-ttu-id="45576-289">是</span><span class="sxs-lookup"><span data-stu-id="45576-289">Yes</span></span> <br /> <span data-ttu-id="45576-290">是</span><span class="sxs-lookup"><span data-stu-id="45576-290">Yes</span></span> <br /> <span data-ttu-id="45576-291">是</span><span class="sxs-lookup"><span data-stu-id="45576-291">Yes</span></span> <br /> <span data-ttu-id="45576-292">是</span><span class="sxs-lookup"><span data-stu-id="45576-292">Yes</span></span> <br /> <span data-ttu-id="45576-293">是</span><span class="sxs-lookup"><span data-stu-id="45576-293">Yes</span></span> | <br /> <span data-ttu-id="45576-294">是，但公用文件夹除外</span><span class="sxs-lookup"><span data-stu-id="45576-294">Yes, except public folders</span></span> <br /> <span data-ttu-id="45576-295">是</span><span class="sxs-lookup"><span data-stu-id="45576-295">Yes</span></span> <br /> <span data-ttu-id="45576-296">是</span><span class="sxs-lookup"><span data-stu-id="45576-296">Yes</span></span> <br /> <span data-ttu-id="45576-297">是</span><span class="sxs-lookup"><span data-stu-id="45576-297">Yes</span></span> <br /> <span data-ttu-id="45576-298">否</span><span class="sxs-lookup"><span data-stu-id="45576-298">No</span></span> <br /> <span data-ttu-id="45576-299">否</span><span class="sxs-lookup"><span data-stu-id="45576-299">No</span></span> <br /> <span data-ttu-id="45576-300">否</span><span class="sxs-lookup"><span data-stu-id="45576-300">No</span></span> |
|<span data-ttu-id="45576-301">自动应用保留</span><span class="sxs-lookup"><span data-stu-id="45576-301">Retention applied automatically</span></span> | <span data-ttu-id="45576-302">是</span><span class="sxs-lookup"><span data-stu-id="45576-302">Yes</span></span> | <span data-ttu-id="45576-303">是</span><span class="sxs-lookup"><span data-stu-id="45576-303">Yes</span></span> |
|<span data-ttu-id="45576-304">基于条件应用保留</span><span class="sxs-lookup"><span data-stu-id="45576-304">Retention applied based on conditions</span></span> <br /> <span data-ttu-id="45576-305">- 敏感信息类型、KQL 查询、可训练的分类器</span><span class="sxs-lookup"><span data-stu-id="45576-305">- sensitive info types, KQL queries, trainable classifiers</span></span>| <span data-ttu-id="45576-306">否</span><span class="sxs-lookup"><span data-stu-id="45576-306">No</span></span> | <span data-ttu-id="45576-307">是</span><span class="sxs-lookup"><span data-stu-id="45576-307">Yes</span></span> |
|<span data-ttu-id="45576-308">手动应用保留</span><span class="sxs-lookup"><span data-stu-id="45576-308">Retention applied manually</span></span> | <span data-ttu-id="45576-309">否</span><span class="sxs-lookup"><span data-stu-id="45576-309">No</span></span> | <span data-ttu-id="45576-310">是</span><span class="sxs-lookup"><span data-stu-id="45576-310">Yes</span></span> |
|<span data-ttu-id="45576-311">对最终用户显示 UI</span><span class="sxs-lookup"><span data-stu-id="45576-311">UI presence for end users</span></span> | <span data-ttu-id="45576-312">否</span><span class="sxs-lookup"><span data-stu-id="45576-312">No</span></span> | <span data-ttu-id="45576-313">是</span><span class="sxs-lookup"><span data-stu-id="45576-313">Yes</span></span> |
|<span data-ttu-id="45576-314">在内容移动时仍继续应用在内容上</span><span class="sxs-lookup"><span data-stu-id="45576-314">Persists if the content is moved</span></span> | <span data-ttu-id="45576-315">否</span><span class="sxs-lookup"><span data-stu-id="45576-315">No</span></span> | <span data-ttu-id="45576-316">是，在您的 Microsoft 365 租户中</span><span class="sxs-lookup"><span data-stu-id="45576-316">Yes, within your Microsoft 365 tenant</span></span> |
|<span data-ttu-id="45576-317">将项声明为记录</span><span class="sxs-lookup"><span data-stu-id="45576-317">Declare item as a record</span></span>| <span data-ttu-id="45576-318">否</span><span class="sxs-lookup"><span data-stu-id="45576-318">No</span></span> | <span data-ttu-id="45576-319">是</span><span class="sxs-lookup"><span data-stu-id="45576-319">Yes</span></span> |
|<span data-ttu-id="45576-320">保留期的开始时间：</span><span class="sxs-lookup"><span data-stu-id="45576-320">Start the retention period:</span></span> <br /> <span data-ttu-id="45576-321">- 创建或最后修改项目时</span><span class="sxs-lookup"><span data-stu-id="45576-321">- When items were created or last modified</span></span><br /> <span data-ttu-id="45576-322">- 标记或基于事件时</span><span class="sxs-lookup"><span data-stu-id="45576-322">- When labeled or based on an event</span></span> | <br /><span data-ttu-id="45576-323">是</span><span class="sxs-lookup"><span data-stu-id="45576-323">Yes</span></span> <br /><span data-ttu-id="45576-324">否</span><span class="sxs-lookup"><span data-stu-id="45576-324">No</span></span> | <br /><span data-ttu-id="45576-325">是</span><span class="sxs-lookup"><span data-stu-id="45576-325">Yes</span></span> <br /> <span data-ttu-id="45576-326">是</span><span class="sxs-lookup"><span data-stu-id="45576-326">Yes</span></span> |
|<span data-ttu-id="45576-327">处置评审</span><span class="sxs-lookup"><span data-stu-id="45576-327">Disposition review</span></span> | <span data-ttu-id="45576-328">否</span><span class="sxs-lookup"><span data-stu-id="45576-328">No</span></span>| <span data-ttu-id="45576-329">是</span><span class="sxs-lookup"><span data-stu-id="45576-329">Yes</span></span> |
|<span data-ttu-id="45576-330">最长 7 年的处置证明</span><span class="sxs-lookup"><span data-stu-id="45576-330">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="45576-331">否</span><span class="sxs-lookup"><span data-stu-id="45576-331">No</span></span> |<span data-ttu-id="45576-332">是，当项被声明为记录时</span><span class="sxs-lookup"><span data-stu-id="45576-332">Yes, when item is declared a record</span></span>|
|<span data-ttu-id="45576-333">审核管理员活动</span><span class="sxs-lookup"><span data-stu-id="45576-333">Audit admin activities</span></span>| <span data-ttu-id="45576-334">是</span><span class="sxs-lookup"><span data-stu-id="45576-334">Yes</span></span> | <span data-ttu-id="45576-335">是</span><span class="sxs-lookup"><span data-stu-id="45576-335">Yes</span></span>|
|<span data-ttu-id="45576-336">识别遵循保留设置的项：</span><span class="sxs-lookup"><span data-stu-id="45576-336">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="45576-337">- 内容搜索</span><span class="sxs-lookup"><span data-stu-id="45576-337">- Content Search</span></span> <br /> <span data-ttu-id="45576-338">- 数据分类页、内容资源管理器、活动资源管理器</span><span class="sxs-lookup"><span data-stu-id="45576-338">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="45576-339">否</span><span class="sxs-lookup"><span data-stu-id="45576-339">No</span></span> <br /> <span data-ttu-id="45576-340">否</span><span class="sxs-lookup"><span data-stu-id="45576-340">No</span></span> | <br /> <span data-ttu-id="45576-341">是</span><span class="sxs-lookup"><span data-stu-id="45576-341">Yes</span></span> <br /> <span data-ttu-id="45576-342">是</span><span class="sxs-lookup"><span data-stu-id="45576-342">Yes</span></span>|

<span data-ttu-id="45576-343">请注意，可以同时将保留策略和保留标签用作互补的保留方法。</span><span class="sxs-lookup"><span data-stu-id="45576-343">Note that you can use both retention policies and retention labels as complementary retention methods.</span></span> <span data-ttu-id="45576-344">例如：</span><span class="sxs-lookup"><span data-stu-id="45576-344">For example:</span></span>

1. <span data-ttu-id="45576-345">你创建并配置一个保留策略，以便在自最后一次修改内容起 5 年后自动删除内容，同时你将此策略应用于所有 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="45576-345">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="45576-346">你创建并配置一个保留标签来永久保留内容，同时你将此标签添加到发布到所有 OneDrive 帐户的标签策略中。</span><span class="sxs-lookup"><span data-stu-id="45576-346">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="45576-347">你向用户解释如何将此标签手动应用于特定文档，这些文档应排除在 5 年未修改后自动删除范围之外。</span><span class="sxs-lookup"><span data-stu-id="45576-347">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="45576-348">若要详细了解保留策略和保留标签是如何协同工作的，以及如何确定它们的合并结果，请参阅下一部分，其中介绍了保留原则和优先级。</span><span class="sxs-lookup"><span data-stu-id="45576-348">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="45576-349">保留原则或优先级</span><span class="sxs-lookup"><span data-stu-id="45576-349">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="45576-350">内容可能（甚至可能性很高）应用有多个保留策略和保留标签，每个策略和标签都有不同的操作（保留、删除或保留后删除）和保留期。</span><span class="sxs-lookup"><span data-stu-id="45576-350">It's possible or even likely that content might have several retention policies and retention labels applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="45576-351">优先级</span><span class="sxs-lookup"><span data-stu-id="45576-351">What takes precedence?</span></span> 

<span data-ttu-id="45576-352">概括来说，可以确定的是，保留始终优先于删除，然后是最长保留期胜出。</span><span class="sxs-lookup"><span data-stu-id="45576-352">At a high level, you can be assured that retention always takes precedence over deletion, and then the longest retention period wins.</span></span> 

<span data-ttu-id="45576-353">不过，此复杂问题还需要考虑其他几个因素，所以请使用以下流来理解优先级顺序自上而下的结果：如果结果由第一个级别决定，则无需进入下一级别，依此类推。</span><span class="sxs-lookup"><span data-stu-id="45576-353">However, there are a few more factors to throw into the mix, so use the following flow to understand the outcome where each level acts as a tie-breaker from top to bottom: If the outcome is determined by the first level, there's no need to progress to the next level, and so on.</span></span> <span data-ttu-id="45576-354">只有当结果无法由当前级别的规则确定时，流才会向下移动到下一个级别，以确定保留设置的优先级结果。</span><span class="sxs-lookup"><span data-stu-id="45576-354">Only if the outcome can't be determined by the rules for the level does the flow move down to the next level to determine the outcome for which retention settings take precedence.</span></span>

![保留原则关系图](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="45576-356">有关四种不同级别的说明：</span><span class="sxs-lookup"><span data-stu-id="45576-356">Explanation for the four different levels:</span></span>
  
1. <span data-ttu-id="45576-357">**保留优先于删除。**</span><span class="sxs-lookup"><span data-stu-id="45576-357">**Retention wins over deletion.**</span></span> <span data-ttu-id="45576-358">如果某保留策略配置为在 3 年后删除 Exchange 电子邮件，但另一保留策略配置为将 Exchange 电子邮件保留 5 年后再删除。</span><span class="sxs-lookup"><span data-stu-id="45576-358">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="45576-359">达到 3 年的内容将被删除并隐藏，但仍保留在“可恢复项目”文件夹中，然后在达到 5 年后被永久删除。</span><span class="sxs-lookup"><span data-stu-id="45576-359">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
2. <span data-ttu-id="45576-360">**优选最长的保留期。**</span><span class="sxs-lookup"><span data-stu-id="45576-360">**The longest retention period wins.**</span></span> <span data-ttu-id="45576-361">如果内容遵循多个在不同时间段内保留内容的保留设置，内容会一直保留到最长保留期结束。</span><span class="sxs-lookup"><span data-stu-id="45576-361">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
3. <span data-ttu-id="45576-362">**显式包含优先于隐式包含。**</span><span class="sxs-lookup"><span data-stu-id="45576-362">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="45576-363">这意味着：</span><span class="sxs-lookup"><span data-stu-id="45576-363">This means:</span></span> 
    
    1. <span data-ttu-id="45576-364">如果具有保留设置的保留标签是由用户手动分配给项（如 Exchange 电子邮件或 OneDrive 文档），此保留标签优先于在站点或邮箱级别分配的保留策略，同时也优先于向文档库分配的默认保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-364">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned to the document library.</span></span> <span data-ttu-id="45576-365">例如，如果显式保留标签配置为将内容保留 10 年，但分配给此站点的保留策略配置为只将内容保留 5 年，则保留标签优先。</span><span class="sxs-lookup"><span data-stu-id="45576-365">For example, if the explicit retention label is configured to retain content for ten years, but a retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="45576-366">自动应用保留标签被视为隐式标签，而不是显式标签，因为它们由 Microsoft 365 自动应用。</span><span class="sxs-lookup"><span data-stu-id="45576-366">Auto-applied retention labels are considered implicit rather than explicit, because they're applied automatically by Microsoft 365.</span></span>
    
    2. <span data-ttu-id="45576-367">如果保留策略包含特定位置（如特定用户的邮箱或 OneDrive 帐户），此保留策略优先于应用于所有用户邮箱或 OneDrive 帐户（而不是包含具体用户邮箱）的其他保留策略。</span><span class="sxs-lookup"><span data-stu-id="45576-367">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="45576-368">**最短删除期优先。**</span><span class="sxs-lookup"><span data-stu-id="45576-368">**The shortest deletion period wins.**</span></span> <span data-ttu-id="45576-369">同样，如果内容遵循多个删除内容而无保留期的保留设置，内容会在最短保留期结束时删除。</span><span class="sxs-lookup"><span data-stu-id="45576-369">Similarly, if content is subject to multiple retention settings that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 

<span data-ttu-id="45576-370">最后，保留策略或保留标签无法永久删除任何保留用于电子数据展示的内容。</span><span class="sxs-lookup"><span data-stu-id="45576-370">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="45576-371">当保留解除时，此内容重新符合工作负载的安全位置中的清除过程的条件。</span><span class="sxs-lookup"><span data-stu-id="45576-371">When that hold is released, the content again becomes eligible for the cleanup process in the secured locations for the workload.</span></span>

## <a name="auditing-retention-configuration"></a><span data-ttu-id="45576-372">审核保留配置</span><span class="sxs-lookup"><span data-stu-id="45576-372">Auditing retention configuration</span></span>

<span data-ttu-id="45576-373">[启用审核后](turn-audit-log-search-on-or-off.md)，管理员针对保留政策和保留标签的操作会被保存到审核日志中。</span><span class="sxs-lookup"><span data-stu-id="45576-373">Administrator actions for retention policies and retention labels are saved to the audit log when [auditing is enabled](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="45576-374">例如，创建、配置或删除保留政策或标签时会创建审核事件。</span><span class="sxs-lookup"><span data-stu-id="45576-374">For example, an audit event is created when a retention policy or label is created, configured, or deleted.</span></span> <span data-ttu-id="45576-375">如需完整的列表，请参阅[保留策略和保留标签活动](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)。</span><span class="sxs-lookup"><span data-stu-id="45576-375">For the full list, see [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="45576-376">用于保留策略和保留标签的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="45576-376">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="45576-377">若要使用保留 cmdlet，必须先[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="45576-377">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="45576-378">然后，使用以下任何 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="45576-378">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="45576-379">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="45576-379">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="45576-380">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="45576-380">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="45576-381">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="45576-381">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="45576-382">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="45576-382">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="45576-383">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="45576-383">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="45576-384">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="45576-384">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="45576-385">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="45576-385">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="45576-386">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="45576-386">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="45576-387">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="45576-387">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="45576-388">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="45576-388">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="45576-389">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="45576-389">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="45576-390">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="45576-390">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="45576-391">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="45576-391">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="45576-392">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="45576-392">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a><span data-ttu-id="45576-393">何时使用保留策略和保留标签或电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="45576-393">When to use retention policies and retention labels or eDiscovery holds</span></span>

<span data-ttu-id="45576-394">虽然保留设置和[电子文件展示案列创建的保留](create-ediscovery-holds.md)都可以防止数据被永久删除，它们是针对不同情况设计的。</span><span class="sxs-lookup"><span data-stu-id="45576-394">Although retention settings and [holds that you create with an eDiscovery case](create-ediscovery-holds.md) can both prevent data from being permanently deleted, they are designed for different scenarios.</span></span> <span data-ttu-id="45576-395">为了帮助你了解差异并决定使用哪个，请使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="45576-395">To help you understand the differences and decide which to use, use the following guidance:</span></span>

- <span data-ttu-id="45576-396">在保留策略和保留标签中指定的保留设置旨在用于长期信息管理策略，以保留或删除符合法规要求的数据。</span><span class="sxs-lookup"><span data-stu-id="45576-396">Retention settings that you specify in retention policies and retention labels are designed for a long-term information governance strategy to retain or delete data for compliance requirements.</span></span> <span data-ttu-id="45576-397">通常范围很广，主要重点是位置和内容，而不是单个用户。</span><span class="sxs-lookup"><span data-stu-id="45576-397">The scope is usually broad with the main focus being the location and content rather than individual users.</span></span> <span data-ttu-id="45576-398">保留期的开始和结束是可配置的，可以选择自动删除内容，无需其他管理员干预。</span><span class="sxs-lookup"><span data-stu-id="45576-398">The start and end of the retention period is configurable, with the option to automatically delete content without additional administrator intervention.</span></span>

- <span data-ttu-id="45576-399">电子数据展示保留（核心电子数据展示或高级电子数据展示案例）的设计期限有限，可以保存数据以进行法律调查。</span><span class="sxs-lookup"><span data-stu-id="45576-399">Holds for eDiscovery (either Core eDiscovery or Advanced eDiscovery cases) are designed for a limited duration to preserve data for a legal investigation.</span></span> <span data-ttu-id="45576-400">范围是特定的，重点是已识别用户拥有的内容。</span><span class="sxs-lookup"><span data-stu-id="45576-400">The scope is specific with the focus being content owned by identified users.</span></span> <span data-ttu-id="45576-401">保留期的开始和结束是不可配置的，但取决于单个管理员的操作，如果保留被释放，则无法选择自动删除内容。</span><span class="sxs-lookup"><span data-stu-id="45576-401">The start and end of the preservation period isn't configurable but dependent on individual administrator actions, without an option to automatically delete content when the hold is released.</span></span>

<span data-ttu-id="45576-402">比较保留与电子数据展示保留的摘要：</span><span class="sxs-lookup"><span data-stu-id="45576-402">Summary to compare retention with holds:</span></span>

|<span data-ttu-id="45576-403">注意事项</span><span class="sxs-lookup"><span data-stu-id="45576-403">Consideration</span></span>|<span data-ttu-id="45576-404">保留</span><span class="sxs-lookup"><span data-stu-id="45576-404">Retention</span></span> |<span data-ttu-id="45576-405">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="45576-405">eDiscovery holds</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45576-406">业务需求：</span><span class="sxs-lookup"><span data-stu-id="45576-406">Business need:</span></span> |<span data-ttu-id="45576-407">合规性</span><span class="sxs-lookup"><span data-stu-id="45576-407">Compliance</span></span> |<span data-ttu-id="45576-408">法律</span><span class="sxs-lookup"><span data-stu-id="45576-408">Legal</span></span> |
|<span data-ttu-id="45576-409">时间范围：</span><span class="sxs-lookup"><span data-stu-id="45576-409">Time scope:</span></span> |<span data-ttu-id="45576-410">长期</span><span class="sxs-lookup"><span data-stu-id="45576-410">Long-term</span></span> |<span data-ttu-id="45576-411">短期</span><span class="sxs-lookup"><span data-stu-id="45576-411">Short-term</span></span> |
|<span data-ttu-id="45576-412">焦点：</span><span class="sxs-lookup"><span data-stu-id="45576-412">Focus:</span></span> |<span data-ttu-id="45576-413">广泛、基于内容</span><span class="sxs-lookup"><span data-stu-id="45576-413">Broad, content-based</span></span> |<span data-ttu-id="45576-414">特定、基于用户</span><span class="sxs-lookup"><span data-stu-id="45576-414">Specific, user-based</span></span> |
|<span data-ttu-id="45576-415">开始和结束日期可配置：</span><span class="sxs-lookup"><span data-stu-id="45576-415">Start and end date configurable:</span></span> |<span data-ttu-id="45576-416">是</span><span class="sxs-lookup"><span data-stu-id="45576-416">Yes</span></span> |<span data-ttu-id="45576-417">否</span><span class="sxs-lookup"><span data-stu-id="45576-417">No</span></span> |
|<span data-ttu-id="45576-418">内容删除：</span><span class="sxs-lookup"><span data-stu-id="45576-418">Content deletion:</span></span> |<span data-ttu-id="45576-419">是（可选）</span><span class="sxs-lookup"><span data-stu-id="45576-419">Yes (optional)</span></span> |<span data-ttu-id="45576-420">否</span><span class="sxs-lookup"><span data-stu-id="45576-420">No</span></span> |
|<span data-ttu-id="45576-421">管理开销：</span><span class="sxs-lookup"><span data-stu-id="45576-421">Administrative overheads:</span></span> |<span data-ttu-id="45576-422">低</span><span class="sxs-lookup"><span data-stu-id="45576-422">Low</span></span> |<span data-ttu-id="45576-423">高</span><span class="sxs-lookup"><span data-stu-id="45576-423">High</span></span> |

<span data-ttu-id="45576-424">如果内容遵循保留设置和电子数据展示保留，则保存电子数据展示保留的内容始终具有优先权。</span><span class="sxs-lookup"><span data-stu-id="45576-424">If content is subject to both retention settings and an eDiscovery hold, preserving content for the eDiscovery hold always takes precedence.</span></span> <span data-ttu-id="45576-425">这样，[保留原则](#the-principles-of-retention-or-what-takes-precedence)扩展到电子数据展示保留，因为它们保留数据，直到管理员手动释放保留为止。</span><span class="sxs-lookup"><span data-stu-id="45576-425">In this way, the [principles of retention](#the-principles-of-retention-or-what-takes-precedence) expand to eDiscovery holds because they preserve data until an administrator manually releases the hold.</span></span> <span data-ttu-id="45576-426">但是，尽管有此优先顺序，但不要将电子数据展示保留用于长期信息治理。</span><span class="sxs-lookup"><span data-stu-id="45576-426">However, despite this precedence, don't use eDiscovery holds for long-term information governance.</span></span> <span data-ttu-id="45576-427">如果担心自动删除数据，则可以将保留设置配置为永久保留项目，或将[处置审查](disposition.md#disposition-reviews)与保留标签一起使用。</span><span class="sxs-lookup"><span data-stu-id="45576-427">If you are concerned about automatic deletion of data, you can configure retention settings to retain items forever, or use [disposition review](disposition.md#disposition-reviews) with retention labels.</span></span>

<span data-ttu-id="45576-428">如果你使用的是旧的电子数据展示工具来保留数据，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="45576-428">If you are using older eDiscovery tools to preserve data, see the following resources:</span></span>

- <span data-ttu-id="45576-429">Exchange:</span><span class="sxs-lookup"><span data-stu-id="45576-429">Exchange:</span></span> 
    - [<span data-ttu-id="45576-430">就地保留和诉讼保留</span><span class="sxs-lookup"><span data-stu-id="45576-430">In-Place Hold and Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=846124)
    - [<span data-ttu-id="45576-431">如何识别为 Exchange Online 邮箱设置的保留类型</span><span class="sxs-lookup"><span data-stu-id="45576-431">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)

- <span data-ttu-id="45576-432">SharePoint 和 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="45576-432">SharePoint and OneDrive:</span></span> 
    - [<span data-ttu-id="45576-433">在电子数据展示中心将内容添加到事例并将源就地保留</span><span class="sxs-lookup"><span data-stu-id="45576-433">Add content to a case and place sources on hold in the eDiscovery Center</span></span>](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)

- [<span data-ttu-id="45576-434">旧版电子数据展示工具的停用</span><span class="sxs-lookup"><span data-stu-id="45576-434">Retirement of legacy eDiscovery tools</span></span>](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="45576-435">使用保留策略和保留标签，而不是旧功能</span><span class="sxs-lookup"><span data-stu-id="45576-435">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="45576-436">如果需要在 Microsoft 365 中主动保留或删除内容来实现信息管理，建议使用保留策略和保留标签，而不是以下旧功能。</span><span class="sxs-lookup"><span data-stu-id="45576-436">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span>

<span data-ttu-id="45576-437">如果当前使用这些旧功能，可以继续将它们与保留策略和保留标签并行使用。</span><span class="sxs-lookup"><span data-stu-id="45576-437">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="45576-438">但我们建议今后使用保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="45576-438">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="45576-439">它们为你提供了在 Microsoft 365 中集中管理内容保留和删除的单一机制。</span><span class="sxs-lookup"><span data-stu-id="45576-439">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="45576-440">**Exchange Online 中的早期功能：**</span><span class="sxs-lookup"><span data-stu-id="45576-440">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="45576-441">[保留标记和保留策略](https://go.microsoft.com/fwlink/?linkid=846125)，亦称为[邮件传递记录管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="45576-441">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>

<span data-ttu-id="45576-442">**SharePoint 和 OneDrive 中的早期功能：**</span><span class="sxs-lookup"><span data-stu-id="45576-442">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="45576-443">[文档删除策略](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff)（仅删除）</span><span class="sxs-lookup"><span data-stu-id="45576-443">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="45576-444">[配置就地记录管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a)（仅限保留）</span><span class="sxs-lookup"><span data-stu-id="45576-444">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="45576-445">[使用网站关闭和删除策略](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="45576-445">[Use policies for site closure and deletion](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="45576-446">[信息管理策略](intro-to-info-mgmt-policies.md)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="45576-446">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="45576-447">如果已将 SharePoint 网站配置为应用保留列表或库的内容的内容类型策略或信息管理策略，则这些策略会在保留策略生效时被忽略。</span><span class="sxs-lookup"><span data-stu-id="45576-447">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="45576-448">相关信息</span><span class="sxs-lookup"><span data-stu-id="45576-448">Related information</span></span>

- [<span data-ttu-id="45576-449">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="45576-449">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="45576-450">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="45576-450">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="45576-451">符合 SEC 规则 17a-4</span><span class="sxs-lookup"><span data-stu-id="45576-451">Comply with SEC Rule 17a-4</span></span>](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a><span data-ttu-id="45576-452">后续步骤</span><span class="sxs-lookup"><span data-stu-id="45576-452">Next steps</span></span>

<span data-ttu-id="45576-453">如果已准备好创建保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="45576-453">If you are ready to create retention policies, see [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="45576-454">若要创建和应用保留标签，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="45576-454">To create and apply retention labels:</span></span>
- [<span data-ttu-id="45576-455">创建保留标签并在应用中应用它们</span><span class="sxs-lookup"><span data-stu-id="45576-455">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="45576-456">自动向内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="45576-456">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

