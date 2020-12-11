---
title: 修正在 Office 365 中传递的恶意电子邮件
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.service: O365-seccomp
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: 威胁修正
appliesto:
- Microsoft 365 Defender
ms.openlocfilehash: 67b27102ff9319e334b5ff1e006fe49f14d3f1ed
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620571"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a><span data-ttu-id="3e4b1-103">修正在 Office 365 中传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="3e4b1-103">Remediate malicious email delivered in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3e4b1-104">修正意味着对威胁采取规定的操作。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-104">Remediation means taking a prescribed action against a threat.</span></span> <span data-ttu-id="3e4b1-105">发送到组织的恶意电子邮件可以通过系统、零时差自动清除 (ZAP) 或安全团队通过修正操作（如移动到收件箱、移动到垃圾邮件、移动到已删除项目、软删除或硬删除）进行 *清理*。  </span><span class="sxs-lookup"><span data-stu-id="3e4b1-105">Malicious email sent to your organization can be cleaned up either by the system, through zero-hour auto purge (ZAP), or by security teams through remediation actions like *move to inbox*, *move to junk*, *move to deleted items*, *soft delete*, or *hard delete*.</span></span> <span data-ttu-id="3e4b1-106">Microsoft Defender for Office 365 P2/E5 使安全团队可以通过手动和自动调查修正电子邮件和协作功能中的威胁。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-106">Microsoft Defender for Office 365 P2/E5 enables security teams to remediate threats in email and collaboration functionality through manual and automated investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="3e4b1-107">若要修正恶意电子邮件，安全团队需要 *为其* 分配搜索和清除角色。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-107">To remediate malicious email, security teams need the *search and purge* role assigned to them.</span></span> <span data-ttu-id="3e4b1-108">角色分配通过安全与合规中心中的权限完成。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-108">Role assignment is done through permissions in the security and compliance center.</span></span>

## <a name="what-you-need-to-know-before-you-begin"></a><span data-ttu-id="3e4b1-109">开始之前您需要了解哪些信息</span><span class="sxs-lookup"><span data-stu-id="3e4b1-109">What you need to know before you begin</span></span>

<span data-ttu-id="3e4b1-110">管理员可以对电子邮件采取所需操作，但若要批准这些操作，他们必须通过安全与合规中心权限为其分配搜索&**清除** \> **角色**。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-110">Admins can take required action on emails, but to get those actions approved, they must have the *search and purge* role assigned to them via **Security & Compliance Center** \> **Permissions**.</span></span> <span data-ttu-id="3e4b1-111">如果没有将"搜索和清除"角色添加到其中一个角色组，他们将无法执行该操作。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-111">Without the "search and purge" role added to one of the role-groups, they won't be able to execute the action.</span></span>

## <a name="manual-and-automated-remediation"></a><span data-ttu-id="3e4b1-112">手动和自动修正</span><span class="sxs-lookup"><span data-stu-id="3e4b1-112">Manual and automated remediation</span></span>

<span data-ttu-id="3e4b1-113">*当安全* 团队使用威胁资源管理器中的搜索和筛选功能手动识别威胁时，将发生手动搜寻。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-113">*Manual hunting* occurs when security teams identify threats manually by using the search and filtering capabilities in Threat Explorer.</span></span> <span data-ttu-id="3e4b1-114">在确定了一组需要修正的电子邮件 (恶意软件、网络钓鱼或所有电子邮件) 可以触发手动电子邮件修正。 </span><span class="sxs-lookup"><span data-stu-id="3e4b1-114">Manual email remediation can be triggered through any email view (*Malware*, *Phish*, or *All email*) after you identify a set of emails that need to be remediated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3e4b1-115">[![按日期在 Office 365 威胁资源管理器中手动搜寻。](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3e4b1-115">[![Manual hunting in Office 365 Threat Explorer by date.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)</span></span>

<span data-ttu-id="3e4b1-116">安全团队可以通过多种方式使用威胁资源管理器选择电子邮件：</span><span class="sxs-lookup"><span data-stu-id="3e4b1-116">Security teams can use Threat Explorer to select emails in several ways:</span></span>

- <span data-ttu-id="3e4b1-117">手动选择电子邮件：在各种视图中使用筛选器。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-117">Choose emails by hand: Use filters in various views.</span></span> <span data-ttu-id="3e4b1-118">选择要修正的电子邮件最多 100 封。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-118">Select up to 100 emails to remediate.</span></span>

- <span data-ttu-id="3e4b1-119">查询选择：使用顶部选择所有按钮 **选择整个** 查询。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-119">Query selection: Select an entire query by using the top **select all** button.</span></span> <span data-ttu-id="3e4b1-120">相同的查询也显示在操作中心邮件提交详细信息中。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-120">The same query is also shown in action center mail submission details.</span></span>

- <span data-ttu-id="3e4b1-121">包含排除的查询选择：有时，安全运营团队可能需要通过选择整个查询并手动从查询中排除某些电子邮件来修正电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-121">Query selection with exclusion: Sometimes security operations teams may want to remediate emails by selecting an entire query and excluding certain emails from the query manually.</span></span> <span data-ttu-id="3e4b1-122">为此，管理员可以使用"选择所有"复选框并向下滚动以手动排除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-122">To do so, an admin can use the **Select all** check box and scroll down to exclude emails manually.</span></span> <span data-ttu-id="3e4b1-123">查询最多可保留 1，000 封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-123">The query can hold a maximum of 1,000 emails.</span></span> <span data-ttu-id="3e4b1-124">排除的最大数目为 100。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-124">The maximum number of exclusions is 100.</span></span>

<span data-ttu-id="3e4b1-125">通过威胁资源管理器选择电子邮件后，可以通过直接操作或为操作将电子邮件排队来开始修正：</span><span class="sxs-lookup"><span data-stu-id="3e4b1-125">Once emails are selected through Threat Explorer, you can start remediation by taking direct action or by queuing up emails for an action:</span></span>

- <span data-ttu-id="3e4b1-126">直接审批：当具有适当权限的安全人员选择移动至收件箱、移动到垃圾邮件、移动到已删除项目、软删除或硬删除等操作后，修正过程将开始执行所选操作。 </span><span class="sxs-lookup"><span data-stu-id="3e4b1-126">Direct approval: When actions like *move to inbox*, *move to junk*, *move to deleted items*, *soft delete*, or *hard delete* are selected by security personnel who have appropriate permissions, and the next steps in remediation are followed, the remediation process begins to execute the selected action.</span></span> <span data-ttu-id="3e4b1-127">临时的飞出显示正在进行修正。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-127">A temporary flyout shows remediation in progress.</span></span>

- <span data-ttu-id="3e4b1-128">两步审批：没有适当权限或需要等待执行该操作的管理员可以执行"添加到修正"操作。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-128">Two-step approval: An "add to remediation" action can be taken by admins who don't have appropriate permissions or who need to wait to execute the action.</span></span> <span data-ttu-id="3e4b1-129">在这种情况下，目标电子邮件将添加到修正容器。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-129">In this case, the targeted emails are added to a remediation container.</span></span> <span data-ttu-id="3e4b1-130">在执行修正之前需要获得批准。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-130">Approval is needed before the remediation is executed.</span></span>

<span data-ttu-id="3e4b1-131">**自动调查和响应** 操作由警报或来自威胁资源管理器的安全操作团队触发。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-131">**Automated investigation and response** actions are triggered by alerts or by security operations teams from Threat Explorer.</span></span> <span data-ttu-id="3e4b1-132">这些可能包括必须由安全运营团队批准的建议的修正操作。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-132">These may include recommended remediation actions that must be approved by a security operations team.</span></span> <span data-ttu-id="3e4b1-133">这些操作包含在自动 **调查的** "操作"选项卡上。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-133">These actions are included on the **Action** tab in the automated investigation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3e4b1-134">[!["Zapped"页面中包含恶意软件的邮件显示 Zap 执行的时间。](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3e4b1-134">[![Mail with malware in "Zapped" page showing time of Zap execution.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)</span></span>

<span data-ttu-id="3e4b1-135">所有修正 (威胁资源管理器中创建的直接审批或两步) 审批操作，以及来自自动调查的已批准操作都显示在操作中心中。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-135">All remediations (either direct approval or two-step approval) that were created in Threat Explorer as well as approved actions coming from automated investigations are displayed in the Action Center.</span></span> <span data-ttu-id="3e4b1-136">通过查看操作中心下的左侧导航 \> **面板访问它们**。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-136">Access these via the left navigation panel under **Review** \> **Action Center**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3e4b1-137">[![包含按日期和严重性列出威胁的操作中心。](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3e4b1-137">[![The action center with a list of threats by date and severity.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)</span></span>

<span data-ttu-id="3e4b1-138">操作中心显示过去 30 天内的所有修正操作。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-138">Action Center shows all remediation actions for the past 30 days.</span></span> <span data-ttu-id="3e4b1-139">通过威胁资源管理器采取的操作按创建修正时安全操作团队提供的名称列出。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-139">Actions taken through Threat Explorer are listed by the name that the security operations team provided when the remediation was created.</span></span> <span data-ttu-id="3e4b1-140">通过自动调查采取的操作的标题以触发调查的相关警报开头，例如"Zap 电子邮件群集..."。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-140">Actions taken through automated investigations have titles that begin with the related alert that triggered the investigation, such as "Zap email cluster... ."</span></span>

<span data-ttu-id="3e4b1-141">打开任何修正项以查看其详细信息，包括名称、创建日期、说明、威胁严重性和状态。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-141">Open any remediation item to view details about it, including its name, creation date, description, threat severity, and status.</span></span> <span data-ttu-id="3e4b1-142">它还显示以下两个选项卡。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-142">It also shows the following two tabs.</span></span>

- <span data-ttu-id="3e4b1-143">**邮件提交** 选项卡：显示通过威胁资源管理器或要修正的自动调查提交的电子邮件数量。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-143">**Mail submission** tab: Displays the number of emails submitted through Threat Explorer or automated investigations to be remediated.</span></span> <span data-ttu-id="3e4b1-144">这些电子邮件可操作或不可操作。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-144">These emails can be actionable or not actionable.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="3e4b1-145">[![具有可操作且不可操作的威胁的操作中心。](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3e4b1-145">[![The action center with actionable and not actionable threats.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)</span></span>

  - <span data-ttu-id="3e4b1-146">**可操作**：可以在以下云邮箱位置操作和移动电子邮件：</span><span class="sxs-lookup"><span data-stu-id="3e4b1-146">**Actionable**: Emails in the following cloud mailbox locations can be acted on and moved:</span></span>
    - <span data-ttu-id="3e4b1-147">Inbox</span><span class="sxs-lookup"><span data-stu-id="3e4b1-147">Inbox</span></span>
    - <span data-ttu-id="3e4b1-148">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="3e4b1-148">Junk</span></span>
    - <span data-ttu-id="3e4b1-149">已删除文件夹</span><span class="sxs-lookup"><span data-stu-id="3e4b1-149">Deleted folder</span></span>
    - <span data-ttu-id="3e4b1-150">软删除文件夹</span><span class="sxs-lookup"><span data-stu-id="3e4b1-150">Soft-deleted folder</span></span>

      > [!NOTE]
      > <span data-ttu-id="3e4b1-151">目前，只有具有邮箱访问权限的用户才能从软删除文件夹中恢复项目。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-151">Currently, only a user with access to the mailbox can recover items from a soft-deleted folder.</span></span>

  - <span data-ttu-id="3e4b1-152">**不可操作**：以下位置的电子邮件无法作用于修正操作或移动：</span><span class="sxs-lookup"><span data-stu-id="3e4b1-152">**Not actionable**: Emails in the following locations can't be acted on or moved in remediation actions:</span></span>
    - <span data-ttu-id="3e4b1-153">隔离</span><span class="sxs-lookup"><span data-stu-id="3e4b1-153">Quarantine</span></span>
    - <span data-ttu-id="3e4b1-154">硬删除文件夹</span><span class="sxs-lookup"><span data-stu-id="3e4b1-154">Hard-deleted folder</span></span>
    - <span data-ttu-id="3e4b1-155">本地/外部</span><span class="sxs-lookup"><span data-stu-id="3e4b1-155">On-premises/external</span></span>
    - <span data-ttu-id="3e4b1-156">失败/丢弃</span><span class="sxs-lookup"><span data-stu-id="3e4b1-156">Failed/dropped</span></span>

  <span data-ttu-id="3e4b1-157">可疑邮件被分类为可修复或不可恢复。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-157">Suspicious messages are categorized as either remediable or nonremediable.</span></span> <span data-ttu-id="3e4b1-158">在大多数情况下，可修正邮件和非可恢复邮件合并等于提交的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-158">In most cases, remediable and nonremediable messages combine equals total messages submitted.</span></span> <span data-ttu-id="3e4b1-159">但在极少数情况下，这可能不成立。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-159">But in rare cases this may not be true.</span></span> <span data-ttu-id="3e4b1-160">由于系统延迟、超时或邮件过期，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-160">This can happen because of system delays, timeouts, or expired messages.</span></span> <span data-ttu-id="3e4b1-161">邮件根据组织的威胁资源管理器保留期过期。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-161">Messages expire based on the Threat Explorer retention period for your organization.</span></span>

  <span data-ttu-id="3e4b1-162">除非在组织的威胁资源管理器保留期后修正旧邮件，否则建议在发现号码不一致时重试修正项目。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-162">Unless you're remediating old messages after your organization's Threat Explorer retention period, it's advisable to retry remediating items if you see number inconsistencies.</span></span> <span data-ttu-id="3e4b1-163">对于系统延迟，修正更新通常在数小时内刷新。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-163">For system delays, remediation updates are typically refreshed within a few hours.</span></span>

  <span data-ttu-id="3e4b1-164">如果你的组织在威胁资源管理器中电子邮件的保留期是 30 天，并且你要修正过去 29-30 天的电子邮件，则邮件提交计数可能并不总是增加。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-164">If your organization's retention period for email in Threat Explorer is 30 days and you're remediating emails going back 29-30 days, mail submission counts may not always add up.</span></span> <span data-ttu-id="3e4b1-165">电子邮件可能已经开始退出保留期。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-165">The emails might have started moving out of the retention period already.</span></span>

  <span data-ttu-id="3e4b1-166">如果修正在"正在进行"状态中停滞一段时间，很可能是由于系统延迟。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-166">If remediations are stuck in the "In progress" state for a while, it's likely due to system delays.</span></span> <span data-ttu-id="3e4b1-167">可能需要几个小时才能修正。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-167">It could take up to a few hours to remediate.</span></span> <span data-ttu-id="3e4b1-168">你可能会在邮件提交计数中看到变化，因为由于系统延迟，一些电子邮件在修正开始时可能尚未包含在查询中。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-168">You might see variations in mail submission counts, as some of the emails may not have been included the query at the start of remediation due to system delays.</span></span> <span data-ttu-id="3e4b1-169">建议在这种情况下重试修正。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-169">It is a good idea to retry remediating in such cases.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3e4b1-170">为获得最佳结果，应分批完成 50，000 个或更少批次的修正。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-170">For best results, remediation should be done in batches of 50,000 or fewer.</span></span>

  <span data-ttu-id="3e4b1-171">修正期间仅处理可修正的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-171">Only remediable emails are acted on during remediation.</span></span> <span data-ttu-id="3e4b1-172">Office 365 电子邮件系统无法修复非安全电子邮件，因为它们不存储在云邮箱中。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-172">Nonremediable emails can't be remediated by the Office 365 email system, as they aren't stored in cloud mailboxes.</span></span>

  <span data-ttu-id="3e4b1-173">如有必要，管理员可以对隔离的电子邮件采取操作，但如果这些电子邮件未手动清除，则这些电子邮件将过期，无法隔离。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-173">Admins can take actions on emails in quarantine if necessary, but those emails will expire out of quarantine if they're not manually purged.</span></span> <span data-ttu-id="3e4b1-174">由于恶意内容而隔离的电子邮件无法被用户访问，因此安全人员不必执行任何操作来清除隔离中的威胁。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-174">Emails quarantined because of malicious content aren't accessible by users, so security personnel don't have to take any action to get rid of threats in quarantine.</span></span> <span data-ttu-id="3e4b1-175">如果电子邮件是本地或外部的，可以联系用户以解决可疑电子邮件问题。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-175">If the emails are on-premises or external, the user can be contacted to address the suspicious email.</span></span> <span data-ttu-id="3e4b1-176">或者管理员可以使用单独的电子邮件服务器/安全工具进行删除。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-176">Or the admins can use separate email server/security tools for removal.</span></span> <span data-ttu-id="3e4b1-177">可以通过在威胁资源管理器中应用传递位置 *=* 内部外部筛选器来标识这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-177">These emails can be identified by applying the *delivery location = on-prem* external filter in Threat Explorer.</span></span> <span data-ttu-id="3e4b1-178">对于失败或丢弃的电子邮件，或者用户无法访问的电子邮件，没有任何要缓解的电子邮件，因为这些邮件无法到达邮箱。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-178">For failed or dropped email, or email not accessible by users, there won't be any email to mitigate, since these mails don't reach the mailbox.</span></span>

  <span data-ttu-id="3e4b1-179">下图显示了提交在操作中心中的外观。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-179">The following image shows how a submission looks in Action Center.</span></span> <span data-ttu-id="3e4b1-180">修正可包含多个提交。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-180">A remediation can contain multiple submissions.</span></span> <span data-ttu-id="3e4b1-181">如果通过一个自动调查批准多个操作，则每个电子邮件或电子邮件群集操作将在同一修正中显示为不同的提交。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-181">If multiple actions get approved through one automated investigation, each email or email cluster action appears in the same remediation as a different submission.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="3e4b1-182">[![ZAP 电子邮件群集飞出面板。](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3e4b1-182">[![ZAP email cluster flyout panel.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)</span></span>

  <span data-ttu-id="3e4b1-183">选择邮件提交项以显示该修正的详细信息，例如通过自动调查触发修正时查询 (，或者通过选择查询) 以及修正的开始和结束时间触发修正。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-183">Select a mail submission item to show the details of that remediation, such as the query (when remediation is triggered through automated investigations or Threat Explorer through selecting a query) and the start and end times of remediation.</span></span> <span data-ttu-id="3e4b1-184">它还显示提交进行修正的邮件列表。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-184">It also displays a list of messages that were submitted for remediation.</span></span> <span data-ttu-id="3e4b1-185">当邮件从威胁资源管理器保留期中移出时，邮件将从此列表消失。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-185">As messages move out of the Threat Explorer retention period, the messages disappear from this list.</span></span> <span data-ttu-id="3e4b1-186">该列表还显示可修复的单个邮件。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-186">The list also shows individual messages that are remediable.</span></span>

- <span data-ttu-id="3e4b1-187">**操作日志**：此选项卡显示已修正的邮件，包括批准日期、批准该操作的管理员、操作、状态和计数。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-187">**Action logs**: This tab shows the messages remediated, including approved date, admin who approved the action, action, status, and counts.</span></span>

  <span data-ttu-id="3e4b1-188">状态可以是：</span><span class="sxs-lookup"><span data-stu-id="3e4b1-188">Status can be:</span></span>

  - <span data-ttu-id="3e4b1-189">**已** 启动：已触发修正。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-189">**Started**: Remediation is triggered.</span></span>
  - <span data-ttu-id="3e4b1-190">**已排队**：修正已排队以缓解电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-190">**Queued**: Remediation is queued up for mitigation of emails.</span></span>
  - <span data-ttu-id="3e4b1-191">**正在进行：** 正在缓解。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-191">**In progress**: Mitigation is in progress.</span></span>
  - <span data-ttu-id="3e4b1-192">**已完成**：所有可修复电子邮件的缓解已成功完成或出现一些故障。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-192">**Completed**: Mitigation on all remediable emails either completed successfully or with some failures.</span></span>
  - <span data-ttu-id="3e4b1-193">**失败**：没有成功修正。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-193">**Failed**: No remediations were successful.</span></span>

  <span data-ttu-id="3e4b1-194">由于只能处理可修复的电子邮件，因此每个电子邮件的清理都显示为成功或失败。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-194">As only remediable emails can be acted on, each email's cleanup is shown as successful or failed.</span></span> <span data-ttu-id="3e4b1-195">从可修复的电子邮件总数中，报告成功和失败的缓解。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-195">From the total remediable emails, successful and failed mitigations are reported.</span></span>

  - <span data-ttu-id="3e4b1-196">**成功**：已完成对可修复电子邮件的所需操作。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-196">**Success**: The desired action on remediable emails was accomplished.</span></span> <span data-ttu-id="3e4b1-197">例如：管理员希望从邮箱中删除电子邮件，以便管理员执行软删除电子邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-197">For example: An admin wants to remove emails from mailboxes, so the admin takes the action of soft-deleting emails.</span></span> <span data-ttu-id="3e4b1-198">如果在采取操作后在原始文件夹中未找到可修复电子邮件，则状态将显示为成功。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-198">If a remediable email isn't found in the original folder after the action is taken, the status will show as successful.</span></span>

  - <span data-ttu-id="3e4b1-199">**失败**：对可修复电子邮件所需操作失败。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-199">**Failure**: The desired action on remediable emails failed.</span></span> <span data-ttu-id="3e4b1-200">例如：管理员希望从邮箱中删除电子邮件，以便管理员执行软删除电子邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-200">For example: An admin wants to remove emails from mailboxes, so the admin takes the action of soft-deleting emails.</span></span> <span data-ttu-id="3e4b1-201">如果在采取操作后在邮箱中仍发现可修复电子邮件，则状态将显示为失败。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-201">If a remediable email is still found in the mailbox after the action is taken, status will show as failed.</span></span>

  <span data-ttu-id="3e4b1-202">选择操作日志中的任何项目以显示修正详细信息。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-202">Select any item in the action log to display remediation details.</span></span> <span data-ttu-id="3e4b1-203">如果详细信息显示"成功"或"在邮箱中未找到"，则该项目已从邮箱中删除。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-203">If the details say "successful" or "not found in mailbox," that item was already removed from the mailbox.</span></span> <span data-ttu-id="3e4b1-204">修正期间有时出现错误。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-204">Sometimes there's a systemic error during remediation.</span></span> <span data-ttu-id="3e4b1-205">在这种情况下，建议重试修正。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-205">In those cases, it's a good idea to retry remediation.</span></span>

  <span data-ttu-id="3e4b1-206">在修正大型批次的情况下，您还可以导出通过"邮件提交"发送的修正邮件和通过"操作日志"修正的邮件。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-206">In case of remediating large batches, you can also export the messages send for remediation via Mail Submission and messages which got remediated via Action Logs.</span></span> <span data-ttu-id="3e4b1-207">导出限制增加到 100，000 条记录。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-207">The export limit is increased to 100k records.</span></span>

  <span data-ttu-id="3e4b1-208">修正是缓解威胁和解决可疑电子邮件的强大工具。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-208">Remediation is a powerful tool to mitigate threats and address suspicious emails.</span></span> <span data-ttu-id="3e4b1-209">它有助于保证组织的安全。</span><span class="sxs-lookup"><span data-stu-id="3e4b1-209">It helps keep an organization secure.</span></span>
