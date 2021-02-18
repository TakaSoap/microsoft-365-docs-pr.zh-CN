---
title: 修正在 Office 365 中传递的恶意电子邮件
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: 威胁修正
appliesto:
- Microsoft 365 Defender
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b32982298a368dc435dad8b6c09188321d099e2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289229"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a><span data-ttu-id="b3829-103">修正在 Office 365 中传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="b3829-103">Remediate malicious email delivered in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b3829-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="b3829-104">**Applies to**</span></span>
- [<span data-ttu-id="b3829-105">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b3829-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="b3829-106">修正意味着对威胁采取规定操作。</span><span class="sxs-lookup"><span data-stu-id="b3829-106">Remediation means taking a prescribed action against a threat.</span></span> <span data-ttu-id="b3829-107">发送到组织的恶意电子邮件可以通过系统、零时差自动清除 (ZAP) 或安全团队通过修正操作（如移动到收件箱、移动到垃圾邮件、移动到已删除项目、软删除或硬删除）进行 *清理。*  </span><span class="sxs-lookup"><span data-stu-id="b3829-107">Malicious email sent to your organization can be cleaned up either by the system, through zero-hour auto purge (ZAP), or by security teams through remediation actions like *move to inbox*, *move to junk*, *move to deleted items*, *soft delete*, or *hard delete*.</span></span> <span data-ttu-id="b3829-108">Microsoft Defender for Office 365 P2/E5 使安全团队可以通过手动和自动调查修正电子邮件和协作功能中的威胁。</span><span class="sxs-lookup"><span data-stu-id="b3829-108">Microsoft Defender for Office 365 P2/E5 enables security teams to remediate threats in email and collaboration functionality through manual and automated investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="b3829-109">若要修正恶意电子邮件，安全 *团队需要为其* 分配搜索和清除角色。</span><span class="sxs-lookup"><span data-stu-id="b3829-109">To remediate malicious email, security teams need the *search and purge* role assigned to them.</span></span> <span data-ttu-id="b3829-110">角色分配通过安全与合规中心中的权限完成。</span><span class="sxs-lookup"><span data-stu-id="b3829-110">Role assignment is done through permissions in the security and compliance center.</span></span>

## <a name="what-you-need-to-know-before-you-begin"></a><span data-ttu-id="b3829-111">开始之前需要知道哪些信息</span><span class="sxs-lookup"><span data-stu-id="b3829-111">What you need to know before you begin</span></span>

<span data-ttu-id="b3829-112">管理员可以对电子邮件采取所需操作，但若要批准这些操作，他们必须通过安全与合规中心权限为其分配&**清除** \> **角色**。</span><span class="sxs-lookup"><span data-stu-id="b3829-112">Admins can take required action on emails, but to get those actions approved, they must have the *search and purge* role assigned to them via **Security & Compliance Center** \> **Permissions**.</span></span> <span data-ttu-id="b3829-113">如果没有将"搜索和清除"角色添加到其中一个角色组，他们将无法执行该操作。</span><span class="sxs-lookup"><span data-stu-id="b3829-113">Without the "search and purge" role added to one of the role-groups, they won't be able to execute the action.</span></span>

## <a name="manual-and-automated-remediation"></a><span data-ttu-id="b3829-114">手动和自动修正</span><span class="sxs-lookup"><span data-stu-id="b3829-114">Manual and automated remediation</span></span>

<span data-ttu-id="b3829-115">*当安全* 团队使用威胁资源管理器中的搜索和筛选功能手动识别威胁时，将进行手动搜寻。</span><span class="sxs-lookup"><span data-stu-id="b3829-115">*Manual hunting* occurs when security teams identify threats manually by using the search and filtering capabilities in Threat Explorer.</span></span> <span data-ttu-id="b3829-116">识别一组需要修正的电子邮件后，可以通过任何电子邮件视图 (*恶意软件*、网络钓鱼或所有电子邮件) 触发手动电子邮件修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-116">Manual email remediation can be triggered through any email view (*Malware*, *Phish*, or *All email*) after you identify a set of emails that need to be remediated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b3829-117">[![按日期在 Office 365 威胁资源管理器中手动搜寻。](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b3829-117">[![Manual hunting in Office 365 Threat Explorer by date.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)</span></span>

<span data-ttu-id="b3829-118">安全团队可以使用威胁资源管理器以多种方式选择电子邮件：</span><span class="sxs-lookup"><span data-stu-id="b3829-118">Security teams can use Threat Explorer to select emails in several ways:</span></span>

- <span data-ttu-id="b3829-119">手动选择电子邮件：在各种视图中使用筛选器。</span><span class="sxs-lookup"><span data-stu-id="b3829-119">Choose emails by hand: Use filters in various views.</span></span> <span data-ttu-id="b3829-120">选择最多 100 封电子邮件进行修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-120">Select up to 100 emails to remediate.</span></span>

- <span data-ttu-id="b3829-121">查询选择：使用顶部选择全部按钮 **选择整个** 查询。</span><span class="sxs-lookup"><span data-stu-id="b3829-121">Query selection: Select an entire query by using the top **select all** button.</span></span> <span data-ttu-id="b3829-122">相同的查询也显示在操作中心邮件提交详细信息中。</span><span class="sxs-lookup"><span data-stu-id="b3829-122">The same query is also shown in action center mail submission details.</span></span>

- <span data-ttu-id="b3829-123">包含排除的查询选择：有时安全运营团队可能需要通过选择整个查询并手动从查询中排除某些电子邮件来修正电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b3829-123">Query selection with exclusion: Sometimes security operations teams may want to remediate emails by selecting an entire query and excluding certain emails from the query manually.</span></span> <span data-ttu-id="b3829-124">为此，管理员可以使用"选择所有"复选框并向下滚动以手动排除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b3829-124">To do so, an admin can use the **Select all** check box and scroll down to exclude emails manually.</span></span> <span data-ttu-id="b3829-125">查询最多可保留 1，000 封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b3829-125">The query can hold a maximum of 1,000 emails.</span></span> <span data-ttu-id="b3829-126">排除的最大数目为 100。</span><span class="sxs-lookup"><span data-stu-id="b3829-126">The maximum number of exclusions is 100.</span></span>

<span data-ttu-id="b3829-127">通过威胁资源管理器选择电子邮件后，可以通过直接操作或将电子邮件排队以开始修正操作：</span><span class="sxs-lookup"><span data-stu-id="b3829-127">Once emails are selected through Threat Explorer, you can start remediation by taking direct action or by queuing up emails for an action:</span></span>

- <span data-ttu-id="b3829-128">直接审批：当具有适当权限的安全人员选择移动到收件箱、移动到垃圾邮件、移动到已删除项目、软删除或硬删除等操作后，将执行修正过程，然后开始执行所选操作。 </span><span class="sxs-lookup"><span data-stu-id="b3829-128">Direct approval: When actions like *move to inbox*, *move to junk*, *move to deleted items*, *soft delete*, or *hard delete* are selected by security personnel who have appropriate permissions, and the next steps in remediation are followed, the remediation process begins to execute the selected action.</span></span> <span data-ttu-id="b3829-129">临时飞出显示正在进行修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-129">A temporary flyout shows remediation in progress.</span></span>

- <span data-ttu-id="b3829-130">两步审批："添加到修正"操作由没有适当权限或需要等待执行该操作的管理员执行。</span><span class="sxs-lookup"><span data-stu-id="b3829-130">Two-step approval: An "add to remediation" action can be taken by admins who don't have appropriate permissions or who need to wait to execute the action.</span></span> <span data-ttu-id="b3829-131">在这种情况下，目标电子邮件将添加到修正容器。</span><span class="sxs-lookup"><span data-stu-id="b3829-131">In this case, the targeted emails are added to a remediation container.</span></span> <span data-ttu-id="b3829-132">在执行修正之前需要审批。</span><span class="sxs-lookup"><span data-stu-id="b3829-132">Approval is needed before the remediation is executed.</span></span>

<span data-ttu-id="b3829-133">**自动调查和响应** 操作由警报或威胁资源管理器中的安全运营团队触发。</span><span class="sxs-lookup"><span data-stu-id="b3829-133">**Automated investigation and response** actions are triggered by alerts or by security operations teams from Threat Explorer.</span></span> <span data-ttu-id="b3829-134">这些可能包括必须由安全运营团队批准的建议的修正操作。</span><span class="sxs-lookup"><span data-stu-id="b3829-134">These may include recommended remediation actions that must be approved by a security operations team.</span></span> <span data-ttu-id="b3829-135">这些操作包含在自动调查 **的** "操作"选项卡上。</span><span class="sxs-lookup"><span data-stu-id="b3829-135">These actions are included on the **Action** tab in the automated investigation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b3829-136">[![显示 Zap 执行时间"Zapped"页面中包含恶意软件的邮件。](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b3829-136">[![Mail with malware in "Zapped" page showing time of Zap execution.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)</span></span>

<span data-ttu-id="b3829-137">所有修正 (威胁资源管理器中创建的直接审批或两步审批) 以及来自自动调查的已批准操作都显示在操作中心中。</span><span class="sxs-lookup"><span data-stu-id="b3829-137">All remediations (either direct approval or two-step approval) that were created in Threat Explorer as well as approved actions coming from automated investigations are displayed in the Action Center.</span></span> <span data-ttu-id="b3829-138">通过查看操作中心下的左侧导航面板 \> **访问它们**。</span><span class="sxs-lookup"><span data-stu-id="b3829-138">Access these via the left navigation panel under **Review** \> **Action Center**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b3829-139">[![包含按日期和严重性列出威胁的操作中心。](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b3829-139">[![The action center with a list of threats by date and severity.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)</span></span>

<span data-ttu-id="b3829-140">操作中心显示过去 30 天内的所有修正操作。</span><span class="sxs-lookup"><span data-stu-id="b3829-140">Action Center shows all remediation actions for the past 30 days.</span></span> <span data-ttu-id="b3829-141">通过威胁资源管理器采取的操作按创建修正时安全操作团队提供的名称列出。</span><span class="sxs-lookup"><span data-stu-id="b3829-141">Actions taken through Threat Explorer are listed by the name that the security operations team provided when the remediation was created.</span></span> <span data-ttu-id="b3829-142">通过自动调查采取的操作具有以触发调查的相关警报开头的标题，例如"Zap 电子邮件群集..."。</span><span class="sxs-lookup"><span data-stu-id="b3829-142">Actions taken through automated investigations have titles that begin with the related alert that triggered the investigation, such as "Zap email cluster... ."</span></span>

<span data-ttu-id="b3829-143">打开任何修正项以查看其详细信息，包括其名称、创建日期、说明、威胁严重性和状态。</span><span class="sxs-lookup"><span data-stu-id="b3829-143">Open any remediation item to view details about it, including its name, creation date, description, threat severity, and status.</span></span> <span data-ttu-id="b3829-144">它还显示以下两个选项卡。</span><span class="sxs-lookup"><span data-stu-id="b3829-144">It also shows the following two tabs.</span></span>

- <span data-ttu-id="b3829-145">**邮件提交** 选项卡：显示通过威胁资源管理器提交的电子邮件数或要修正的自动调查数。</span><span class="sxs-lookup"><span data-stu-id="b3829-145">**Mail submission** tab: Displays the number of emails submitted through Threat Explorer or automated investigations to be remediated.</span></span> <span data-ttu-id="b3829-146">这些电子邮件可操作或不可操作。</span><span class="sxs-lookup"><span data-stu-id="b3829-146">These emails can be actionable or not actionable.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="b3829-147">[![具有可操作且不可操作的威胁的操作中心。](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b3829-147">[![The action center with actionable and not actionable threats.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)</span></span>

  - <span data-ttu-id="b3829-148">**可操作**：可以操作和移动以下云邮箱位置中的电子邮件：</span><span class="sxs-lookup"><span data-stu-id="b3829-148">**Actionable**: Emails in the following cloud mailbox locations can be acted on and moved:</span></span>
    - <span data-ttu-id="b3829-149">Inbox</span><span class="sxs-lookup"><span data-stu-id="b3829-149">Inbox</span></span>
    - <span data-ttu-id="b3829-150">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="b3829-150">Junk</span></span>
    - <span data-ttu-id="b3829-151">已删除文件夹</span><span class="sxs-lookup"><span data-stu-id="b3829-151">Deleted folder</span></span>
    - <span data-ttu-id="b3829-152">软删除文件夹</span><span class="sxs-lookup"><span data-stu-id="b3829-152">Soft-deleted folder</span></span>

      > [!NOTE]
      > <span data-ttu-id="b3829-153">目前，只有具有邮箱访问权限的用户才能从软删除文件夹中恢复项目。</span><span class="sxs-lookup"><span data-stu-id="b3829-153">Currently, only a user with access to the mailbox can recover items from a soft-deleted folder.</span></span>

  - <span data-ttu-id="b3829-154">**不可操作**：在修正操作中，下列位置的电子邮件无法操作或移动：</span><span class="sxs-lookup"><span data-stu-id="b3829-154">**Not actionable**: Emails in the following locations can't be acted on or moved in remediation actions:</span></span>
    - <span data-ttu-id="b3829-155">隔离</span><span class="sxs-lookup"><span data-stu-id="b3829-155">Quarantine</span></span>
    - <span data-ttu-id="b3829-156">硬删除文件夹</span><span class="sxs-lookup"><span data-stu-id="b3829-156">Hard-deleted folder</span></span>
    - <span data-ttu-id="b3829-157">本地/外部</span><span class="sxs-lookup"><span data-stu-id="b3829-157">On-premises/external</span></span>
    - <span data-ttu-id="b3829-158">失败/丢弃</span><span class="sxs-lookup"><span data-stu-id="b3829-158">Failed/dropped</span></span>

  <span data-ttu-id="b3829-159">可疑邮件分为可修正或非可修复邮件。</span><span class="sxs-lookup"><span data-stu-id="b3829-159">Suspicious messages are categorized as either remediable or nonremediable.</span></span> <span data-ttu-id="b3829-160">在大多数情况下，可修正邮件和非可恢复邮件合并等于提交的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="b3829-160">In most cases, remediable and nonremediable messages combine equals total messages submitted.</span></span> <span data-ttu-id="b3829-161">但在极少数情况下，这可能不成立。</span><span class="sxs-lookup"><span data-stu-id="b3829-161">But in rare cases this may not be true.</span></span> <span data-ttu-id="b3829-162">由于系统延迟、超时或邮件过期，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b3829-162">This can happen because of system delays, timeouts, or expired messages.</span></span> <span data-ttu-id="b3829-163">邮件根据组织的威胁资源管理器保留期过期。</span><span class="sxs-lookup"><span data-stu-id="b3829-163">Messages expire based on the Threat Explorer retention period for your organization.</span></span>

  <span data-ttu-id="b3829-164">除非在组织的威胁资源管理器保留期后修正旧邮件，否则建议在看到号码不一致时重试修正项目。</span><span class="sxs-lookup"><span data-stu-id="b3829-164">Unless you're remediating old messages after your organization's Threat Explorer retention period, it's advisable to retry remediating items if you see number inconsistencies.</span></span> <span data-ttu-id="b3829-165">对于系统延迟，修正更新通常在几小时内刷新。</span><span class="sxs-lookup"><span data-stu-id="b3829-165">For system delays, remediation updates are typically refreshed within a few hours.</span></span>

  <span data-ttu-id="b3829-166">如果你的组织在威胁资源管理器中电子邮件的保留期是 30 天，并且你要修正 29-30 天的电子邮件，则邮件提交计数可能并不总是增加。</span><span class="sxs-lookup"><span data-stu-id="b3829-166">If your organization's retention period for email in Threat Explorer is 30 days and you're remediating emails going back 29-30 days, mail submission counts may not always add up.</span></span> <span data-ttu-id="b3829-167">电子邮件可能已经开始退出保留期。</span><span class="sxs-lookup"><span data-stu-id="b3829-167">The emails might have started moving out of the retention period already.</span></span>

  <span data-ttu-id="b3829-168">如果修正在"正在进行"状态中停滞一段时间，很可能是由于系统延迟。</span><span class="sxs-lookup"><span data-stu-id="b3829-168">If remediations are stuck in the "In progress" state for a while, it's likely due to system delays.</span></span> <span data-ttu-id="b3829-169">可能需要几个小时才能修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-169">It could take up to a few hours to remediate.</span></span> <span data-ttu-id="b3829-170">您可能会在邮件提交计数中看到变体，因为由于系统延迟，某些电子邮件在修正开始时可能尚未包含查询。</span><span class="sxs-lookup"><span data-stu-id="b3829-170">You might see variations in mail submission counts, as some of the emails may not have been included the query at the start of remediation due to system delays.</span></span> <span data-ttu-id="b3829-171">在这种情况下，建议重试修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-171">It is a good idea to retry remediating in such cases.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b3829-172">为获得最佳结果，应分批完成 50，000 个或更少批次的修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-172">For best results, remediation should be done in batches of 50,000 or fewer.</span></span>

  <span data-ttu-id="b3829-173">在修正期间，仅处理可修正的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b3829-173">Only remediable emails are acted on during remediation.</span></span> <span data-ttu-id="b3829-174">Office 365 电子邮件系统无法修正不可修复的电子邮件，因为它们不会存储在云邮箱中。</span><span class="sxs-lookup"><span data-stu-id="b3829-174">Nonremediable emails can't be remediated by the Office 365 email system, as they aren't stored in cloud mailboxes.</span></span>

  <span data-ttu-id="b3829-175">如有必要，管理员可以对隔离中的电子邮件采取操作，但是如果未手动清除这些电子邮件，这些电子邮件将过期，无法隔离。</span><span class="sxs-lookup"><span data-stu-id="b3829-175">Admins can take actions on emails in quarantine if necessary, but those emails will expire out of quarantine if they're not manually purged.</span></span> <span data-ttu-id="b3829-176">由于恶意内容而隔离的电子邮件无法供用户访问，因此安全人员不必采取任何操作来消除隔离中的威胁。</span><span class="sxs-lookup"><span data-stu-id="b3829-176">Emails quarantined because of malicious content aren't accessible by users, so security personnel don't have to take any action to get rid of threats in quarantine.</span></span> <span data-ttu-id="b3829-177">如果电子邮件是本地电子邮件或外部电子邮件，可以联系用户以解决可疑电子邮件问题。</span><span class="sxs-lookup"><span data-stu-id="b3829-177">If the emails are on-premises or external, the user can be contacted to address the suspicious email.</span></span> <span data-ttu-id="b3829-178">或者管理员可以使用单独的电子邮件服务器/安全工具进行删除。</span><span class="sxs-lookup"><span data-stu-id="b3829-178">Or the admins can use separate email server/security tools for removal.</span></span> <span data-ttu-id="b3829-179">可以通过在威胁资源管理器中应用传递位置 *= 内部* 外部筛选器来标识这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b3829-179">These emails can be identified by applying the *delivery location = on-prem* external filter in Threat Explorer.</span></span> <span data-ttu-id="b3829-180">对于失败或丢弃的电子邮件，或者用户无法访问的电子邮件，没有任何要缓解的电子邮件，因为这些邮件无法到达邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3829-180">For failed or dropped email, or email not accessible by users, there won't be any email to mitigate, since these mails don't reach the mailbox.</span></span>

  <span data-ttu-id="b3829-181">下图显示了提交在操作中心中的外观。</span><span class="sxs-lookup"><span data-stu-id="b3829-181">The following image shows how a submission looks in Action Center.</span></span> <span data-ttu-id="b3829-182">修正可以包含多个提交。</span><span class="sxs-lookup"><span data-stu-id="b3829-182">A remediation can contain multiple submissions.</span></span> <span data-ttu-id="b3829-183">如果多个操作通过一个自动调查获得批准，则每个电子邮件或电子邮件群集操作将在同一个修正中显示为不同的提交。</span><span class="sxs-lookup"><span data-stu-id="b3829-183">If multiple actions get approved through one automated investigation, each email or email cluster action appears in the same remediation as a different submission.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="b3829-184">[![ZAP 电子邮件群集飞出面板。](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b3829-184">[![ZAP email cluster flyout panel.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)</span></span>

  <span data-ttu-id="b3829-185">选择邮件提交项以显示该修正的详细信息，例如当通过自动调查触发修正时查询 (，或者通过选择查询) 以及修正的开始和结束时间触发修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-185">Select a mail submission item to show the details of that remediation, such as the query (when remediation is triggered through automated investigations or Threat Explorer through selecting a query) and the start and end times of remediation.</span></span> <span data-ttu-id="b3829-186">它还显示已提交以修正的邮件列表。</span><span class="sxs-lookup"><span data-stu-id="b3829-186">It also displays a list of messages that were submitted for remediation.</span></span> <span data-ttu-id="b3829-187">当邮件离开威胁资源管理器保留期时，邮件将从此列表消失。</span><span class="sxs-lookup"><span data-stu-id="b3829-187">As messages move out of the Threat Explorer retention period, the messages disappear from this list.</span></span> <span data-ttu-id="b3829-188">该列表还显示可修正的单个邮件。</span><span class="sxs-lookup"><span data-stu-id="b3829-188">The list also shows individual messages that are remediable.</span></span>

- <span data-ttu-id="b3829-189">**操作日志**：此选项卡显示已修正的邮件，包括批准日期、批准该操作的管理员、操作、状态和计数。</span><span class="sxs-lookup"><span data-stu-id="b3829-189">**Action logs**: This tab shows the messages remediated, including approved date, admin who approved the action, action, status, and counts.</span></span>

  <span data-ttu-id="b3829-190">状态可以是：</span><span class="sxs-lookup"><span data-stu-id="b3829-190">Status can be:</span></span>

  - <span data-ttu-id="b3829-191">**已** 启动：触发修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-191">**Started**: Remediation is triggered.</span></span>
  - <span data-ttu-id="b3829-192">**已排队**：修正已排入队列以缓解电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b3829-192">**Queued**: Remediation is queued up for mitigation of emails.</span></span>
  - <span data-ttu-id="b3829-193">**正在进行：** 正在缓解。</span><span class="sxs-lookup"><span data-stu-id="b3829-193">**In progress**: Mitigation is in progress.</span></span>
  - <span data-ttu-id="b3829-194">**已完成**：所有可修复电子邮件的缓解要么成功完成，要么有一些失败。</span><span class="sxs-lookup"><span data-stu-id="b3829-194">**Completed**: Mitigation on all remediable emails either completed successfully or with some failures.</span></span>
  - <span data-ttu-id="b3829-195">**失败**：没有成功修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-195">**Failed**: No remediations were successful.</span></span>

  <span data-ttu-id="b3829-196">由于只能处理可修复的电子邮件，因此每个电子邮件的清理都显示为成功或失败。</span><span class="sxs-lookup"><span data-stu-id="b3829-196">As only remediable emails can be acted on, each email's cleanup is shown as successful or failed.</span></span> <span data-ttu-id="b3829-197">从可修复的电子邮件总数中，报告成功和失败的缓解。</span><span class="sxs-lookup"><span data-stu-id="b3829-197">From the total remediable emails, successful and failed mitigations are reported.</span></span>

  - <span data-ttu-id="b3829-198">**成功**：已完成对可修复电子邮件的所需操作。</span><span class="sxs-lookup"><span data-stu-id="b3829-198">**Success**: The desired action on remediable emails was accomplished.</span></span> <span data-ttu-id="b3829-199">例如：管理员希望从邮箱中删除电子邮件，以便管理员执行软删除电子邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="b3829-199">For example: An admin wants to remove emails from mailboxes, so the admin takes the action of soft-deleting emails.</span></span> <span data-ttu-id="b3829-200">如果在采取操作后在原始文件夹中找不到可修复的电子邮件，则状态将显示为成功。</span><span class="sxs-lookup"><span data-stu-id="b3829-200">If a remediable email isn't found in the original folder after the action is taken, the status will show as successful.</span></span>

  - <span data-ttu-id="b3829-201">**失败**：对可修复电子邮件的所需操作失败。</span><span class="sxs-lookup"><span data-stu-id="b3829-201">**Failure**: The desired action on remediable emails failed.</span></span> <span data-ttu-id="b3829-202">例如：管理员希望从邮箱中删除电子邮件，以便管理员执行软删除电子邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="b3829-202">For example: An admin wants to remove emails from mailboxes, so the admin takes the action of soft-deleting emails.</span></span> <span data-ttu-id="b3829-203">如果在采取操作后在邮箱中仍发现可修复的电子邮件，则状态将显示为"失败"。</span><span class="sxs-lookup"><span data-stu-id="b3829-203">If a remediable email is still found in the mailbox after the action is taken, status will show as failed.</span></span>

  <span data-ttu-id="b3829-204">选择操作日志中的任何项以显示修正详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3829-204">Select any item in the action log to display remediation details.</span></span> <span data-ttu-id="b3829-205">如果详细信息显示"成功"或"在邮箱中未找到"，则该项目已从邮箱中删除。</span><span class="sxs-lookup"><span data-stu-id="b3829-205">If the details say "successful" or "not found in mailbox," that item was already removed from the mailbox.</span></span> <span data-ttu-id="b3829-206">有时修正期间出现错误。</span><span class="sxs-lookup"><span data-stu-id="b3829-206">Sometimes there's a systemic error during remediation.</span></span> <span data-ttu-id="b3829-207">在这种情况下，建议重试修正。</span><span class="sxs-lookup"><span data-stu-id="b3829-207">In those cases, it's a good idea to retry remediation.</span></span>

  <span data-ttu-id="b3829-208">在修正大型批次的情况下，还可以导出通过邮件提交发送的修正邮件和通过操作日志修正的邮件。</span><span class="sxs-lookup"><span data-stu-id="b3829-208">In case of remediating large batches, you can also export the messages send for remediation via Mail Submission and messages which got remediated via Action Logs.</span></span> <span data-ttu-id="b3829-209">导出限制增加到 100，000 条记录。</span><span class="sxs-lookup"><span data-stu-id="b3829-209">The export limit is increased to 100k records.</span></span>

  <span data-ttu-id="b3829-210">修正是缓解威胁和解决可疑电子邮件的强大工具。</span><span class="sxs-lookup"><span data-stu-id="b3829-210">Remediation is a powerful tool to mitigate threats and address suspicious emails.</span></span> <span data-ttu-id="b3829-211">它有助于保证组织的安全。</span><span class="sxs-lookup"><span data-stu-id="b3829-211">It helps keep an organization secure.</span></span>
