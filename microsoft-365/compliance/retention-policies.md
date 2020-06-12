---
title: 了解用于自动保留或删除内容的保留策略
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
search.appverid:
- MOE150
- MET150
description: 使用保留策略主动决定是保留内容还是删除内容，或是先保留再删除内容；可将一个策略应用于整个组织，或应用于特定位置或用户；并能将策略应用于所有内容，或应用于满足特定条件的内容。
ms.openlocfilehash: 377c5e1f21938204123de298e620a3d0d2bb9755
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695135"
---
# <a name="learn-about-retention-policies"></a><span data-ttu-id="1db04-103">了解保留策略</span><span class="sxs-lookup"><span data-stu-id="1db04-103">Learn about retention policies</span></span>

><span data-ttu-id="1db04-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="1db04-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1db04-p101">对于大多数组织，数据量和数据复杂性每天都在增加 — 包括电子邮件、文档、即时消息等。有效管理或管理此类信息非常重要，因为要：</span><span class="sxs-lookup"><span data-stu-id="1db04-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="1db04-107">**主动遵守规定至少必须在一段时间内保留内容的行业法规和内部策略**：例如，《萨班斯-奥克斯利法案》规定，必须保留特定类型的内容七年。</span><span class="sxs-lookup"><span data-stu-id="1db04-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 
    
- <span data-ttu-id="1db04-108">**降低发生诉讼或出现安全漏洞的风险**：通过永久删除不再需要保留的旧内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="1db04-109">**帮助组织有效共享知识并提高敏捷性**：通过确保用户仅处理与自己相关的最新内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="1db04-p102">保留策略可有助于实现所有这些目标。管理内容通常需要执行以下两项操作：</span><span class="sxs-lookup"><span data-stu-id="1db04-p102">A retention policy can help you achieve all of these goals. Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="1db04-112">**保留**内容，这样除非保留期到期，否则无法永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="1db04-113">在保留期到期时永久**删除**内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    
<span data-ttu-id="1db04-114">借助保留策略，你可以：</span><span class="sxs-lookup"><span data-stu-id="1db04-114">With a retention policy, you can:</span></span>
  
- <span data-ttu-id="1db04-115">主动决定是保留内容还是删除内容 — 亦或是先保留再删除内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-115">Decide proactively whether to retain content, delete content, or both—retain and then delete the content.</span></span>
    
- <span data-ttu-id="1db04-116">将一个策略应用于整个组织，或应用于特定位置或用户。</span><span class="sxs-lookup"><span data-stu-id="1db04-116">Apply a single policy to the entire organization or specific locations or users.</span></span>
    
- <span data-ttu-id="1db04-117">将策略应用于所有内容，或满足特定条件（如包含特定关键字或[特定类型的敏感信息](what-the-sensitive-information-types-look-for.md)）的内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-117">Apply a policy to all content or to content when it meets specific conditions, such as content containing keywords or [types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
    
<span data-ttu-id="1db04-p103">如果内容受保留策略约束，用户可以继续编辑和处理内容，就像什么都没改变一样。内容留在原处。但若有人编辑或删除受保留策略约束的内容，原始内容的副本就会保存到内容的安全保留位置上，直至该内容的保留策略失效。请参阅此页面上的[保留策略如何处理留在原处的内容](#how-a-retention-policy-works-with-content-in-place)部分</span><span class="sxs-lookup"><span data-stu-id="1db04-p103">When content is subject to a retention policy, people can continue to edit and work with the content as if nothing's changed. The content is retained in place, in its original location. But if someone edits or deletes content that's subject to the retention policy, a copy of the original content is saved to a secure location where it's retained while the retention policy for that content is in effect. For more information, see the [How a retention policy works with content in place](#how-a-retention-policy-works-with-content-in-place) section on this page</span></span>
  
<span data-ttu-id="1db04-122">最后，某些组织可能需要遵从特定规则，如美国证券交易委员会 (SEC) 规则 17a-4。</span><span class="sxs-lookup"><span data-stu-id="1db04-122">Additionally, some organizations have to comply with regulations such as Securities and Exchange Commission (SEC) Rule 17a-4.</span></span> <span data-ttu-id="1db04-123">这要求在某个保留策略启用后，不得关闭该策略或减少限制。</span><span class="sxs-lookup"><span data-stu-id="1db04-123">This regulation requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> <span data-ttu-id="1db04-124">为满足这一要求，你可以使用**保留锁定**。</span><span class="sxs-lookup"><span data-stu-id="1db04-124">To meet this requirement, you can use **Preservation Lock**.</span></span> <span data-ttu-id="1db04-125">锁定某个保留策略后，包括管理员在内的任何人都无法关闭该策略或减少其限制。</span><span class="sxs-lookup"><span data-stu-id="1db04-125">After a retention policy's been locked, no one (including an administrator) can turn off the retention policy or make it less restrictive.</span></span> <span data-ttu-id="1db04-126">有关详细信息，请参阅此页面上的[使用保留锁定遵从合规性要求](#use-preservation-lock-to-comply-with-regulatory-requirements)部分。</span><span class="sxs-lookup"><span data-stu-id="1db04-126">For more information, see the [Use Preservation Lock to comply with regulatory requirements](#use-preservation-lock-to-comply-with-regulatory-requirements) section on this page.</span></span>

## <a name="how-a-retention-policy-works-with-content-in-place"></a><span data-ttu-id="1db04-127">保留策略如何处理留在原处的内容</span><span class="sxs-lookup"><span data-stu-id="1db04-127">How a retention policy works with content in place</span></span>

<span data-ttu-id="1db04-128">将某个位置（例如网站或邮箱）包含在保留策略中时，相关内容仍保留在原处。</span><span class="sxs-lookup"><span data-stu-id="1db04-128">When you include a location such as a site or mailbox in a retention policy, the content remains in its original location.</span></span> <span data-ttu-id="1db04-129">用户可以继续使用其文档或邮件，就像没有发生任何变动一样。</span><span class="sxs-lookup"><span data-stu-id="1db04-129">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="1db04-130">但是，如果用户编辑或删除了保留策略中包含的内容，则会保留应用策略时的内容的副本。</span><span class="sxs-lookup"><span data-stu-id="1db04-130">But if they edit or delete content that's included in the retention policy, a copy of the content is retained as it existed when you applied the policy.</span></span>
  
- <span data-ttu-id="1db04-131">对于 SharePoint 和 OneDrive 网站：副本保留在**保存保留**库中。</span><span class="sxs-lookup"><span data-stu-id="1db04-131">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span> <span data-ttu-id="1db04-132">请注意，保存保留库将占用网站的存储配额。</span><span class="sxs-lookup"><span data-stu-id="1db04-132">Be aware that the Preservation Hold library consumes storage quota for the site.</span></span>

- <span data-ttu-id="1db04-133">对于电子邮件和公用文件夹：副本保留在“**可恢复的项目**”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1db04-133">For email and public folders: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="1db04-134">对于 Teams 内容：副本保留在 Exchange“**可恢复的项目**”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1db04-134">For Teams content: The copy is retained in the Exchange **Recoverable Items** folder.</span></span>

- <span data-ttu-id="1db04-135">对于 Microsoft 365 组（[以前的 Office 365 组](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）：</span><span class="sxs-lookup"><span data-stu-id="1db04-135">For Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)):</span></span> 
    - <span data-ttu-id="1db04-136">组邮箱保留在 Exchange“**可恢复的项目**”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1db04-136">The group mailbox is retained in the Exchange **Recoverable Items** folder.</span></span>
    - <span data-ttu-id="1db04-137">任何网站内容都将保留在**保存保留**库中。</span><span class="sxs-lookup"><span data-stu-id="1db04-137">Any site content is retained in the **Preservation Hold** library.</span></span>

> [!NOTE]
> <span data-ttu-id="1db04-138">保存保留库占用的存储不受网站的存储配额限制。</span><span class="sxs-lookup"><span data-stu-id="1db04-138">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="1db04-139">对 SharePoint 和 Microsoft 365 组使用保留策略时，可能需要增加存储空间。</span><span class="sxs-lookup"><span data-stu-id="1db04-139">You might need to increase your storage when you use retention policies for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="1db04-140">这些安全位置和保留内容对大部分用户不可见。</span><span class="sxs-lookup"><span data-stu-id="1db04-140">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="1db04-141">使用保留策略后，用户甚至无需知晓已向其内容应用了该策略。</span><span class="sxs-lookup"><span data-stu-id="1db04-141">With a retention policy, people do not even need to know that their content is subject to the policy.</span></span>

<span data-ttu-id="1db04-142">有关保留策略如何用于不同工作负载的更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="1db04-142">For more detailed information about how retention policies work with different workloads, see the following articles:</span></span>

- [<span data-ttu-id="1db04-143">了解 SharePoint 和 OneDrive 的保留策略</span><span class="sxs-lookup"><span data-stu-id="1db04-143">Learn about retention policies for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="1db04-144">了解 Microsoft Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="1db04-144">Learn about retention policies for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="1db04-145">了解 Exchange 的保留策略</span><span class="sxs-lookup"><span data-stu-id="1db04-145">Learn about retention policies for Exchange</span></span>](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="1db04-146">保留原则或优先级</span><span class="sxs-lookup"><span data-stu-id="1db04-146">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="1db04-147">可能对内容应用了多个保留策略，每个策略具有不同的操作（保留、删除或先保留再删除）和保留期。</span><span class="sxs-lookup"><span data-stu-id="1db04-147">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="1db04-148">哪些内容优先？</span><span class="sxs-lookup"><span data-stu-id="1db04-148">What takes precedence?</span></span> <span data-ttu-id="1db04-149">请放心，在最高级别中，某保留策略保留的内容不可被其他保留策略永久删除。</span><span class="sxs-lookup"><span data-stu-id="1db04-149">At the highest level, rest assured that content being retained by one retention policy can't be permanently deleted by another retention policy.</span></span>
  
![保留原则关系图](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="1db04-151">若要了解不同保留策略是如何应用于内容的，请注意下面这些保留原则：</span><span class="sxs-lookup"><span data-stu-id="1db04-151">To understand how different retention policies are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="1db04-152">**保留优先于删除。**</span><span class="sxs-lookup"><span data-stu-id="1db04-152">**Retention wins over deletion.**</span></span> <span data-ttu-id="1db04-153">如果某保留策略配置为在 3 年后删除 Exchange 电子邮件，但另一保留策略配置为将 Exchange 电子邮件保留 5 年后再删除。</span><span class="sxs-lookup"><span data-stu-id="1db04-153">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="1db04-154">达到 3 年的内容将被删除并隐藏，但仍保留在“可恢复项目”文件夹中，然后在达到 5 年后被永久删除。</span><span class="sxs-lookup"><span data-stu-id="1db04-154">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
    
2. <span data-ttu-id="1db04-155">**优选最长的保留期。**</span><span class="sxs-lookup"><span data-stu-id="1db04-155">**The longest retention period wins.**</span></span> <span data-ttu-id="1db04-156">如果对内容应用了多个保留策略，它将采用最长的保留期。</span><span class="sxs-lookup"><span data-stu-id="1db04-156">If content is subject to multiple retention policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="1db04-157">**显式包含优先于隐式包含。**</span><span class="sxs-lookup"><span data-stu-id="1db04-157">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="1db04-158">这意味着：</span><span class="sxs-lookup"><span data-stu-id="1db04-158">This means:</span></span> 
    
    1. <span data-ttu-id="1db04-159">如果具有保留设置的保留标签由用户手动分配给某项目（例如 Exchange 电子邮件或 OneDrive 文档），该保留标签优先于在站点或邮箱级别分配的保留策略以及由文档库分配的默认保留标签。</span><span class="sxs-lookup"><span data-stu-id="1db04-159">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned by the document library.</span></span> <span data-ttu-id="1db04-160">例如，如果显式保留标签配置为将内容保留 10 年，但分配给此站点的保留策略仅配置为将内容保留 5 年，则优选保留标签的保留期。</span><span class="sxs-lookup"><span data-stu-id="1db04-160">For example, if the explicit retention label is configured to retain content for 10 years, but the retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="1db04-161">自动应用保留标签被视为隐式标签，而不是显式标签，因为它们由 Microsoft 365 自动应用。</span><span class="sxs-lookup"><span data-stu-id="1db04-161">Auto-applied retention labels are considered implicit rather than explicit, because they're applied automatically by Microsoft 365.</span></span>
    
    2. <span data-ttu-id="1db04-162">如果保留策略包含特定位置（如特定用户的邮箱或 OneDrive 帐户），此保留策略优先于应用于所有用户邮箱或 OneDrive 帐户（而不是包含具体用户邮箱）的其他保留策略。</span><span class="sxs-lookup"><span data-stu-id="1db04-162">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="1db04-163">**最短删除期优先。**</span><span class="sxs-lookup"><span data-stu-id="1db04-163">**The shortest deletion period wins.**</span></span> <span data-ttu-id="1db04-164">同样，如果内容受多个保留策略约束（删除无保留期的内容），它将在最短保留期到期时被删除。</span><span class="sxs-lookup"><span data-stu-id="1db04-164">Similarly, if content is subject to multiple retention policies that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="1db04-165">请注意，保留原则就像是自上而下打破平局的流：如果所有保留策略或保留标签应用的规则在一个级别上是相同的，流就会向下移至下一个级别，以确定优先应用哪个规则。</span><span class="sxs-lookup"><span data-stu-id="1db04-165">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all retention policies or retention labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="1db04-166">最后一点，保留策略或保留标签不能永久删除任何保留用于电子数据展示的内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-166">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="1db04-167">解除限制时，此内容将可再次用于上述清除过程。</span><span class="sxs-lookup"><span data-stu-id="1db04-167">When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a><span data-ttu-id="1db04-168">使用保留锁定遵从合规性要求</span><span class="sxs-lookup"><span data-stu-id="1db04-168">Use Preservation Lock to comply with regulatory requirements</span></span>

<span data-ttu-id="1db04-169">某些组织可能需要遵从由监管机构定义的规则，如美国证券交易委员会 (SEC) 规则 17a-4，这要求在某个保留策略启用后，不得关闭该策略或减少其限制。</span><span class="sxs-lookup"><span data-stu-id="1db04-169">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="1db04-170">保留锁定可确保你的组织符合此类法规要求，因为它可以锁定某个保留策略，包括管理员在内的任何人都无法关闭该策略或减少其限制。</span><span class="sxs-lookup"><span data-stu-id="1db04-170">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy so that no one—including the administrator—can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="1db04-171">锁定某个保留策略后：</span><span class="sxs-lookup"><span data-stu-id="1db04-171">When a retention policy is locked:</span></span>

- <span data-ttu-id="1db04-172">任何人都不能将其关闭</span><span class="sxs-lookup"><span data-stu-id="1db04-172">No one can it turn off</span></span>
- <span data-ttu-id="1db04-173">可以添加位置，但不能删除位置</span><span class="sxs-lookup"><span data-stu-id="1db04-173">Locations can be added but not removed</span></span> 
- <span data-ttu-id="1db04-174">无法在保留期内修改或删除受策略制约的内容</span><span class="sxs-lookup"><span data-stu-id="1db04-174">Content subject to the policy can't be modified or deleted during the retention period</span></span>
- <span data-ttu-id="1db04-175">可以延长保留期，但不能缩短保留期</span><span class="sxs-lookup"><span data-stu-id="1db04-175">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="1db04-176">总而言之，锁定的保留策略可以增加或扩展锁定的策略，但不能减少或关闭策略。</span><span class="sxs-lookup"><span data-stu-id="1db04-176">In summary, a locked retention policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1db04-177">在锁定保留策略之前，请务必了解其影响并确定组织是否需要该策略以满足合规性要求。</span><span class="sxs-lookup"><span data-stu-id="1db04-177">Before you lock a retention policy, it's critical that you understand the impact and confirm whether it's required for your organization to meet compliance requirements.</span></span>

## <a name="releasing-a-retention-policy"></a><span data-ttu-id="1db04-178">解除保留策略</span><span class="sxs-lookup"><span data-stu-id="1db04-178">Releasing a retention policy</span></span>

<span data-ttu-id="1db04-179">若保留策略没有保留锁定，则可随时关闭或删除它。</span><span class="sxs-lookup"><span data-stu-id="1db04-179">Providing your retention policy doesn't have a Preservation Lock, you can turn off or delete a retention policy at any time.</span></span> 

<span data-ttu-id="1db04-180">当你这样做时，任何被保留在保留库中的 SharePoint 或 OneDrive 内容都不会立即遭永久删除。</span><span class="sxs-lookup"><span data-stu-id="1db04-180">When you do so, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="1db04-181">相反，为了防止意外的数据丢失，我们设置了 30 天的宽限期。在此期间，相应策略的内容不会在保留库中到期，所以你可以根据需要从其中还原任何内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-181">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="1db04-182">此外，在宽限期内无法手动删除此内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-182">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="1db04-183">可在宽限期内重新启用保留策略，相应策略的任何内容都不会遭删除。</span><span class="sxs-lookup"><span data-stu-id="1db04-183">You can turn on the retention policy again during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="1db04-184">SharePoint 和 OneDrive 中的此 30 天宽限期对应于 Exchange 中的 30 天延迟保留。</span><span class="sxs-lookup"><span data-stu-id="1db04-184">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="1db04-185">有关详细信息，请参阅[管理延迟保留的邮箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。</span><span class="sxs-lookup"><span data-stu-id="1db04-185">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="use-a-retention-policy-instead-of-older-features"></a><span data-ttu-id="1db04-186">使用保留策略代替早期功能</span><span class="sxs-lookup"><span data-stu-id="1db04-186">Use a retention policy instead of older features</span></span>

<span data-ttu-id="1db04-187">可轻松将单个保留策略应用到整个组织和 Microsoft 365 中的位置，包括 Exchange Online、SharePoint Online、OneDrive 和 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="1db04-187">A single retention policy can easily apply to an entire organization and locations across Microsoft 365, including Exchange Online, SharePoint Online, OneDrive, and Microsoft 365 groups.</span></span> <span data-ttu-id="1db04-188">如果需要保留或删除 Microsoft 365 中任意位置的内容，建议使用保留策略并可辅以[保留标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="1db04-188">If you need to retain or delete content anywhere in Microsoft 365, we recommend that you use a retention policy and optionally supplement this with [retention labels](labels.md).</span></span>
  
<span data-ttu-id="1db04-189">如果你以前使用过其他配置保留或删除 Microsoft 365 中的内容，它们将继续与保留策略和保留标签配合使用。</span><span class="sxs-lookup"><span data-stu-id="1db04-189">If you have previously used other configurations to retain or delete content in Microsoft 365, they will continue to work side by side with retention policies and retention labels.</span></span> <span data-ttu-id="1db04-190">但我们建议今后使用保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="1db04-190">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="1db04-191">它们为你提供了在 Microsoft 365 中集中管理内容保留和删除的单一机制。</span><span class="sxs-lookup"><span data-stu-id="1db04-191">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="1db04-192">你可能使用过的早期功能有：</span><span class="sxs-lookup"><span data-stu-id="1db04-192">The older features that you might have used:</span></span>
  
<span data-ttu-id="1db04-193">**Exchange Online 中的早期功能：**</span><span class="sxs-lookup"><span data-stu-id="1db04-193">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="1db04-194">[就地保留和诉讼保留](https://go.microsoft.com/fwlink/?linkid=846124)（电子数据展示保留）</span><span class="sxs-lookup"><span data-stu-id="1db04-194">[In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery hold)</span></span> 

- [<span data-ttu-id="1db04-195">如何识别为 Exchange Online 邮箱设置的保留类型</span><span class="sxs-lookup"><span data-stu-id="1db04-195">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- <span data-ttu-id="1db04-196">[保留标记和保留策略](https://go.microsoft.com/fwlink/?linkid=846125)，亦称为[邮件传递记录管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="1db04-196">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>
    
<span data-ttu-id="1db04-197">另请参阅[旧版电子数据展示工具的停用](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="1db04-197">See also [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>


<span data-ttu-id="1db04-198">**SharePoint 和 OneDrive 中的早期功能：**</span><span class="sxs-lookup"><span data-stu-id="1db04-198">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="1db04-199">[在电子数据展示中心内将内容添加到案件集并保留源](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)（电子数据展示保留）</span><span class="sxs-lookup"><span data-stu-id="1db04-199">[Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="1db04-200">[文档删除策略](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff)（仅删除）</span><span class="sxs-lookup"><span data-stu-id="1db04-200">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="1db04-201">[配置就地记录管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a)（仅限保留）</span><span class="sxs-lookup"><span data-stu-id="1db04-201">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="1db04-202">[使用网站关闭和删除策略](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="1db04-202">[Use policies for site closure and deletion](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="1db04-203">[信息管理策略](intro-to-info-mgmt-policies.md)（仅限删除）</span><span class="sxs-lookup"><span data-stu-id="1db04-203">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="1db04-204">如果之前使用了任何电子数据展示保留进行信息管理，为实现主动合规，请改为使用保留策略。</span><span class="sxs-lookup"><span data-stu-id="1db04-204">If you've previously used any of the eDiscovery holds for the purpose of information governance, for proactive compliance, use a retention policy instead.</span></span> <span data-ttu-id="1db04-205">仅对保留策略使用电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="1db04-205">Use eDiscovery for holds only.</span></span>
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a><span data-ttu-id="1db04-206">保留策略和 SharePoint 内容类型策略或信息管理策略</span><span class="sxs-lookup"><span data-stu-id="1db04-206">Retention policies and SharePoint content type policies or information management policies</span></span>

<span data-ttu-id="1db04-207">如果已将 SharePoint 网站配置为应用保留列表或库的内容的内容类型策略或信息管理策略，则这些策略会在保留策略生效时被忽略。</span><span class="sxs-lookup"><span data-stu-id="1db04-207">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a><span data-ttu-id="1db04-208">保存策略转换为保留策略</span><span class="sxs-lookup"><span data-stu-id="1db04-208">Preservation policies are converted to retention policies</span></span>

<span data-ttu-id="1db04-209">如果之前使用保存策略保留邮箱、SharePoint 或 OneDrive 网站或公用文件夹中的数据，则保存策略已自动转换为保留策略 — 只会保留内容，而不会删除内容。</span><span class="sxs-lookup"><span data-stu-id="1db04-209">If you were using a preservation policy to retain data in mailboxes, SharePoint or OneDrive sites, or public folders: That policy has been automatically converted to a retention policy that uses only the retain action—the policy won't delete content.</span></span> <span data-ttu-id="1db04-210">与你配置的保留策略的结果相同，无需进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="1db04-210">No changes are needed from you for the same outcome as your configured preservation policy.</span></span>

<span data-ttu-id="1db04-211">有关配置的任何保存策略的信息，可查看 [Microsoft 365 合规中心](https://compliance.microsoft.com/)的“**策略**”页面，或者[安全&amp;合规中心](https://protection.office.com/)内“**信息管理**”下的“**保留**”页面。</span><span class="sxs-lookup"><span data-stu-id="1db04-211">You can find any configured preservation policies on the **Policies** page in the [Microsoft 365 compliance center](https://compliance.microsoft.com/), or on the **Retention** page under **Information governance** in the [Security &amp; Compliance Center](https://protection.office.com/).</span></span> <span data-ttu-id="1db04-212">可以编辑保存策略，以更改保存期限，但是无法进行添加或移动位置等其他更改。</span><span class="sxs-lookup"><span data-stu-id="1db04-212">You can edit a preservation policy to change the retention period, but you can't make other changes, such as adding or removing locations.</span></span> 


## <a name="related-information"></a><span data-ttu-id="1db04-213">相关信息</span><span class="sxs-lookup"><span data-stu-id="1db04-213">Related information</span></span>

- [<span data-ttu-id="1db04-214">了解保留标签</span><span class="sxs-lookup"><span data-stu-id="1db04-214">Learn about retention labels</span></span>](labels.md)
- [<span data-ttu-id="1db04-215">SharePoint Online 限制</span><span class="sxs-lookup"><span data-stu-id="1db04-215">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="1db04-216">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="1db04-216">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="1db04-217">符合 SEC 规则 17a-4</span><span class="sxs-lookup"><span data-stu-id="1db04-217">Comply with SEC Rule 17a-4</span></span>](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a><span data-ttu-id="1db04-218">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1db04-218">Next steps</span></span>

<span data-ttu-id="1db04-219">如果已准备好创建保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1db04-219">If you are ready to create retention polices, see [Create and configure retention policies](create-retention-policies.md).</span></span>

