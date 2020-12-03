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
description: 威胁补救措施
appliesto:
- Microsoft 365 Defender
ms.openlocfilehash: 4adabe3e85b2bff26167bfad92a9a7fcbf24e58e
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561277"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a><span data-ttu-id="77c50-103">修正在 Office 365 中传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="77c50-103">Remediate malicious email delivered in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="77c50-104">修正是指对威胁采取规定的操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-104">Remediation means taking a prescribed action against a threat.</span></span> <span data-ttu-id="77c50-105">发送到您的组织的恶意电子邮件可由系统清除)  (，也可通过 " *移动到收件箱*"、"移动到 *垃圾* 邮件"、"移动到 *已删除邮件*"、"删除项目"、" *软删除*" 或 " *硬删除*" 等补救操作进行清除。</span><span class="sxs-lookup"><span data-stu-id="77c50-105">Malicious email sent to your organization can be cleaned up either by the system, through zero-hour auto purge (ZAP), or by security teams through remediation actions like *move to inbox*, *move to junk*, *move to deleted items*, *soft delete*, or *hard delete*.</span></span> <span data-ttu-id="77c50-106">Microsoft Defender for Office 365 P2/E5 使安全团队能够通过手动和自动调查来修正电子邮件和协作功能中的威胁。</span><span class="sxs-lookup"><span data-stu-id="77c50-106">Microsoft Defender for Office 365 P2/E5 enables security teams to remediate threats in email and collaboration functionality through manual and automated investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="77c50-107">若要修正恶意电子邮件，安全团队需要分配给他们的 *搜索和清除* 角色。</span><span class="sxs-lookup"><span data-stu-id="77c50-107">To remediate malicious email, security teams need the *search and purge* role assigned to them.</span></span> <span data-ttu-id="77c50-108">角色分配通过安全与合规中心中的权限完成。</span><span class="sxs-lookup"><span data-stu-id="77c50-108">Role assignment is done through permissions in the security and compliance center.</span></span>

## <a name="what-you-need-to-know-before-you-begin"></a><span data-ttu-id="77c50-109">开始之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="77c50-109">What you need to know before you begin</span></span>

<span data-ttu-id="77c50-110">管理员可以对电子邮件执行必需的操作，但若要获取这些操作的批准，则必须通过 **Security & 合规性中心** 权限为其分配 *搜索和清除* 角色 \> **Permissions**。</span><span class="sxs-lookup"><span data-stu-id="77c50-110">Admins can take required action on emails, but to get those actions approved, they must have the *search and purge* role assigned to them via **Security & Compliance Center** \> **Permissions**.</span></span> <span data-ttu-id="77c50-111">如果没有添加到某个角色组的 "搜索和清除" 角色，他们将无法执行该操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-111">Without the "search and purge" role added to one of the role-groups, they wont be able to execute the action.</span></span>

## <a name="manual-and-automated-remediation"></a><span data-ttu-id="77c50-112">手动和自动修正</span><span class="sxs-lookup"><span data-stu-id="77c50-112">Manual and automated remediation</span></span>

<span data-ttu-id="77c50-113">当安全团队使用威胁资源管理器中的搜索和筛选功能手动识别威胁时，将发生 *手动搜寻*。</span><span class="sxs-lookup"><span data-stu-id="77c50-113">*Manual hunting* occurs when security teams identify threats manually by using the search and filtering capabilities in Threat Explorer.</span></span> <span data-ttu-id="77c50-114">在确定需要修正的一组电子邮件之后，可以通过任何电子邮件视图 (*恶意软件*、 *网络钓鱼* 或 *所有电子邮件*) 来触发手动电子邮件修复。</span><span class="sxs-lookup"><span data-stu-id="77c50-114">Manual email remediation can be triggered through any email view (*Malware*, *Phish*, or *All email*) after you identify a set of emails that need to be remediated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77c50-115">[![按日期手动搜寻 Office 365 中的威胁资源管理器。 ](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77c50-115">[ ![Manual hunting in Office 365 Threat Explorer by date.](../../media/tp-RemediationArticle1.png) ](../../media/tp-RemediationArticle1.png#lightbox)</span></span>

<span data-ttu-id="77c50-116">安全团队可以通过以下几种方式使用威胁资源管理器选择电子邮件：</span><span class="sxs-lookup"><span data-stu-id="77c50-116">Security teams can use Threat Explorer to select emails in several ways:</span></span>

- <span data-ttu-id="77c50-117">手动选择电子邮件：在各种视图中使用筛选器。</span><span class="sxs-lookup"><span data-stu-id="77c50-117">Choose emails by hand: Use filters in various views.</span></span> <span data-ttu-id="77c50-118">最高选择100封电子邮件进行修正。</span><span class="sxs-lookup"><span data-stu-id="77c50-118">Select up to 100 emails to remediate.</span></span>

- <span data-ttu-id="77c50-119">查询选择：使用 top "全 **选** " 按钮选择整个查询。</span><span class="sxs-lookup"><span data-stu-id="77c50-119">Query selection: Select an entire query by using the top **select all** button.</span></span> <span data-ttu-id="77c50-120">在操作中心邮件提交详细信息中也会显示相同的查询。</span><span class="sxs-lookup"><span data-stu-id="77c50-120">The same query is also shown in action center mail submission details.</span></span>

- <span data-ttu-id="77c50-121">包含排除的查询选择：有时安全操作团队可能需要通过选择整个查询并从查询中手动排除某些电子邮件来修正电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77c50-121">Query selection with exclusion: Sometimes security operations teams may want to remediate emails by selecting an entire query and excluding certain emails from the query manually.</span></span> <span data-ttu-id="77c50-122">若要执行此操作，管理员可以使用 " **全选** " 复选框，然后向下滚动以手动排除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77c50-122">To do so, an admin can use the **Select all** check box and scroll down to exclude emails manually.</span></span> <span data-ttu-id="77c50-123">查询最多可保留1000封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77c50-123">The query can hold a maximum of 1,000 emails.</span></span> <span data-ttu-id="77c50-124">排除次数的最大值为100。</span><span class="sxs-lookup"><span data-stu-id="77c50-124">The maximum number of exclusions is 100.</span></span>

<span data-ttu-id="77c50-125">通过威胁资源管理器选择电子邮件后，您可以通过直接操作或对电子邮件进行排队以执行某项操作来启动修正：</span><span class="sxs-lookup"><span data-stu-id="77c50-125">Once emails are selected through Threat Explorer, you can start remediation by taking direct action or by queuing up emails for an action:</span></span>

- <span data-ttu-id="77c50-126">直接批准：当具有适当权限的安全人员选择 *"移动到收件箱*"、" *移至垃圾* 邮件"、"移动到 *已删除的项目*"、" *软删除*" 或 " *硬删除* " 时，将会选择具有适当权限的安全人员的操作，修正过程将开始执行选定的操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-126">Direct approval: When actions like *move to inbox*, *move to junk*, *move to deleted items*, *soft delete*, or *hard delete* are selected by security personnel who have appropriate permissions, and the next steps in remediation are followed, the remediation process begins to execute the selected action.</span></span> <span data-ttu-id="77c50-127">临时浮出控件将显示正在进行的修正。</span><span class="sxs-lookup"><span data-stu-id="77c50-127">A temporary flyout shows remediation in progress.</span></span>

- <span data-ttu-id="77c50-128">两步批准：不具有适当权限的管理员或需要等待执行该操作的管理员可以采取 "添加到修正" 操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-128">Two-step approval: An "add to remediation" action can be taken by admins who don't have appropriate permissions or who need to wait to execute the action.</span></span> <span data-ttu-id="77c50-129">在这种情况下，目标电子邮件将添加到修正容器中。</span><span class="sxs-lookup"><span data-stu-id="77c50-129">In this case, the targeted emails are added to a remediation container.</span></span> <span data-ttu-id="77c50-130">在执行修正之前需要进行审批。</span><span class="sxs-lookup"><span data-stu-id="77c50-130">Approval is needed before the remediation is executed.</span></span>

<span data-ttu-id="77c50-131">来自威胁资源管理器的警报或安全操作团队触发了 **自动调查和响应** 操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-131">**Automated investigation and response** actions are triggered by alerts or by security operations teams from Threat Explorer.</span></span> <span data-ttu-id="77c50-132">其中可能包括安全操作团队必须批准的建议修正操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-132">These may include recommended remediation actions that must be approved by a security operations team.</span></span> <span data-ttu-id="77c50-133">自动调查中的 " **操作** " 选项卡上包含这些操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-133">These actions are included on the **Action** tab in the automated investigation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77c50-134">[![带有恶意软件的邮件在 "Zapped" 页中，显示了 Zap 执行的时间。 ](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77c50-134">[ ![Mail with malware in "Zapped" page showing time of Zap execution.](../../media/tp-RemediationArticle3.png) ](../../media/tp-RemediationArticle3.png#lightbox)</span></span>

<span data-ttu-id="77c50-135">所有 remediations (在威胁资源管理器中创建的直接批准或两步审批) ，以及来自自动调查的批准的操作将显示在操作中心中。</span><span class="sxs-lookup"><span data-stu-id="77c50-135">All remediations (either direct approval or two-step approval) that were created in Threat Explorer as well as approved actions coming from automated investigations are displayed in the Action Center.</span></span> <span data-ttu-id="77c50-136">通过左侧导航面板中的 "**审阅**  >  **操作中心**" 访问这些权限。</span><span class="sxs-lookup"><span data-stu-id="77c50-136">Access these via the left navigation panel under **Review** > **Action Center**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77c50-137">[![包含受日期和严重性的威胁列表的操作中心。 ](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77c50-137">[ ![The action center with a list of threats by date and severity.](../../media/tp-RemediationArticle4.png) ](../../media/tp-RemediationArticle4.png#lightbox)</span></span>

<span data-ttu-id="77c50-138">操作中心显示过去30天内的所有修正操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-138">Action Center shows all remediation actions for the past 30 days.</span></span> <span data-ttu-id="77c50-139">通过威胁资源管理器执行的操作按安全操作团队在创建修正时提供的名称列出。</span><span class="sxs-lookup"><span data-stu-id="77c50-139">Actions taken through Threat Explorer are listed by the name that the security operations team provided when the remediation was created.</span></span> <span data-ttu-id="77c50-140">通过自动调查执行的操作的标题以触发调查的相关警报开头，如 "Zap 电子邮件群集 ..."。</span><span class="sxs-lookup"><span data-stu-id="77c50-140">Actions taken through automated investigations have titles that begin with the related alert that triggered the investigation, such as "Zap email cluster... ."</span></span>

<span data-ttu-id="77c50-141">打开任何修正项目以查看其详细信息，包括其名称、创建日期、说明、威胁严重性和状态。</span><span class="sxs-lookup"><span data-stu-id="77c50-141">Open any remediation item to view details about it, including its name, creation date, description, threat severity, and status.</span></span> <span data-ttu-id="77c50-142">它还显示以下两个选项卡。</span><span class="sxs-lookup"><span data-stu-id="77c50-142">It also shows the following two tabs.</span></span>

- <span data-ttu-id="77c50-143">"**邮件提交**" 选项卡：显示通过威胁浏览器提交的电子邮件数或要修正的自动调查。</span><span class="sxs-lookup"><span data-stu-id="77c50-143">**Mail submission** tab: Displays the number of emails submitted through Threat Explorer or automated investigations to be remediated.</span></span> <span data-ttu-id="77c50-144">这些电子邮件可以是可操作的，也可以是不可操作的。</span><span class="sxs-lookup"><span data-stu-id="77c50-144">These emails can be actionable or not actionable.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="77c50-145">[![具有可操作和无可操作威胁的操作中心。 ](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77c50-145">[ ![The action center with actionable and not actionable threats.](../../media/tp-RemediationArticle5.png) ](../../media/tp-RemediationArticle5.png#lightbox)</span></span>

  - <span data-ttu-id="77c50-146">可 **操作**：可对以下云邮箱位置中的电子邮件执行操作并将其移动：</span><span class="sxs-lookup"><span data-stu-id="77c50-146">**Actionable**: Emails in the following cloud mailbox locations can be acted on and moved:</span></span>
    - <span data-ttu-id="77c50-147">Inbox</span><span class="sxs-lookup"><span data-stu-id="77c50-147">Inbox</span></span>
    - <span data-ttu-id="77c50-148">可疑</span><span class="sxs-lookup"><span data-stu-id="77c50-148">Junk</span></span>
    - <span data-ttu-id="77c50-149">已删除文件夹</span><span class="sxs-lookup"><span data-stu-id="77c50-149">Deleted folder</span></span>
    - <span data-ttu-id="77c50-150">软删除文件夹</span><span class="sxs-lookup"><span data-stu-id="77c50-150">Soft-deleted folder</span></span>

      > [!NOTE]
      > <span data-ttu-id="77c50-151">目前，只有对邮箱具有访问权限的用户才能恢复软删除的文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="77c50-151">Currently, only a user with access to the mailbox can recover items from a soft-deleted folder.</span></span>

  - <span data-ttu-id="77c50-152">**不可行**：以下位置中的电子邮件不能在修正操作中进行操作或移动：</span><span class="sxs-lookup"><span data-stu-id="77c50-152">**Not actionable**: Emails in the following locations can't be acted on or moved in remediation actions:</span></span>
    - <span data-ttu-id="77c50-153">隔离</span><span class="sxs-lookup"><span data-stu-id="77c50-153">Quarantine</span></span>
    - <span data-ttu-id="77c50-154">硬删除文件夹</span><span class="sxs-lookup"><span data-stu-id="77c50-154">Hard-deleted folder</span></span>
    - <span data-ttu-id="77c50-155">内部部署/外部</span><span class="sxs-lookup"><span data-stu-id="77c50-155">On-premises/external</span></span>
    - <span data-ttu-id="77c50-156">失败/丢弃</span><span class="sxs-lookup"><span data-stu-id="77c50-156">Failed/dropped</span></span>

  <span data-ttu-id="77c50-157">可疑邮件被分类为 remediable 或 nonremediable。</span><span class="sxs-lookup"><span data-stu-id="77c50-157">Suspicious messages are categorized as either remediable or nonremediable.</span></span> <span data-ttu-id="77c50-158">在大多数情况下，remediable 和 nonremediable 邮件组合为已提交的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="77c50-158">In most cases, remediable and nonremediable messages combine equals total messages submitted.</span></span> <span data-ttu-id="77c50-159">但在极少数情况下，这可能不是这样。</span><span class="sxs-lookup"><span data-stu-id="77c50-159">But in rare cases this may not be true.</span></span> <span data-ttu-id="77c50-160">出现这种情况的原因可能是系统延迟、超时或邮件已过期。</span><span class="sxs-lookup"><span data-stu-id="77c50-160">This can happen because of system delays, timeouts, or expired messages.</span></span> <span data-ttu-id="77c50-161">邮件将根据您的组织的威胁资源管理器保留期而过期。</span><span class="sxs-lookup"><span data-stu-id="77c50-161">Messages expire based on the Threat Explorer retention period for your organization.</span></span>

  <span data-ttu-id="77c50-162">除非您在组织的威胁浏览器保留期之后对旧邮件进行补救，否则建议您在遇到数字不一致情况时重试补救项目。</span><span class="sxs-lookup"><span data-stu-id="77c50-162">Unless you're remediating old messages after your organization's Threat Explorer retention period, it's advisable to retry remediating items if you see number inconsistencies.</span></span> <span data-ttu-id="77c50-163">对于系统延迟，修复更新通常在几小时内进行刷新。</span><span class="sxs-lookup"><span data-stu-id="77c50-163">For system delays, remediation updates are typically refreshed within a few hours.</span></span>

  <span data-ttu-id="77c50-164">如果组织在威胁资源管理器中的电子邮件保留期为30天，而您正在修正电子邮件将在29-30 天后发生，则邮件提交计数可能不会总增加。</span><span class="sxs-lookup"><span data-stu-id="77c50-164">If your organization's retention period for email in Threat Explorer is 30 days and you're remediating emails going back 29-30 days, mail submission counts may not always add up.</span></span> <span data-ttu-id="77c50-165">电子邮件可能已开始移出保留期。</span><span class="sxs-lookup"><span data-stu-id="77c50-165">The emails might have started moving out of the retention period already.</span></span>

  <span data-ttu-id="77c50-166">如果 remediations 在一段时间内处于 "正在进行" 状态，可能是因为系统延迟。</span><span class="sxs-lookup"><span data-stu-id="77c50-166">If remediations are stuck in the "In progress" state for a while, it's likely due to system delays.</span></span> <span data-ttu-id="77c50-167">修正可能需要几个小时的时间。</span><span class="sxs-lookup"><span data-stu-id="77c50-167">It could take up to a few hours to remediate.</span></span> <span data-ttu-id="77c50-168">您可能会看到邮件提交计数方面的变化，因为某些电子邮件可能因系统延迟而无法在修正启动时包含查询。</span><span class="sxs-lookup"><span data-stu-id="77c50-168">You might see variations in mail submission counts, as some of the emails may not have been included the query at the start of remediation due to system delays.</span></span> <span data-ttu-id="77c50-169">最好在这种情况下重试修正。</span><span class="sxs-lookup"><span data-stu-id="77c50-169">It is a good idea to retry remediating in such cases.</span></span>

  > [!NOTE]
  > <span data-ttu-id="77c50-170">为获得最佳结果，应以50000或更少的批处理完成补救措施。</span><span class="sxs-lookup"><span data-stu-id="77c50-170">For best results, remediation should be done in batches of 50,000 or fewer.</span></span>

  <span data-ttu-id="77c50-171">在修正期间只会对 remediable 电子邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-171">Only remediable emails are acted on during remediation.</span></span> <span data-ttu-id="77c50-172">Office 365 电子邮件系统无法修正 Nonremediable 电子邮件，因为它们不存储在云邮箱中。</span><span class="sxs-lookup"><span data-stu-id="77c50-172">Nonremediable emails can't be remediated by the Office 365 email system, as they aren't stored in cloud mailboxes.</span></span>

  <span data-ttu-id="77c50-173">管理员可以对隔离中的电子邮件执行操作（如有必要），但如果不手动清除这些电子邮件，则这些电子邮件将在隔离时过期。</span><span class="sxs-lookup"><span data-stu-id="77c50-173">Admins can take actions on emails in quarantine if necessary, but those emails will expire out of quarantine if they're not manually purged.</span></span> <span data-ttu-id="77c50-174">由于用户无法访问恶意内容而隔离的电子邮件，因此安全人员不必采取任何措施来消除隔离威胁。</span><span class="sxs-lookup"><span data-stu-id="77c50-174">Emails quarantined because of malicious content aren't accessible by users, so security personnel don't have to take any action to get rid of threats in quarantine.</span></span> <span data-ttu-id="77c50-175">如果电子邮件位于本地或外部，则可以联系用户以解决可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77c50-175">If the emails are on-premises or external, the user can be contacted to address the suspicious email.</span></span> <span data-ttu-id="77c50-176">或者，管理员可以使用单独的电子邮件服务器/安全工具进行删除。</span><span class="sxs-lookup"><span data-stu-id="77c50-176">Or the admins can use separate email server/security tools for removal.</span></span> <span data-ttu-id="77c50-177">可以通过在威胁资源管理器中应用 *传递位置 = 本地* 外部筛选器来识别这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77c50-177">These emails can be identified by applying the *delivery location = on-prem* external filter in Threat Explorer.</span></span> <span data-ttu-id="77c50-178">对于失败或丢失的电子邮件，或者用户无法访问的电子邮件，由于这些邮件不会到达邮箱，因此不会有任何电子邮件需要缓解。</span><span class="sxs-lookup"><span data-stu-id="77c50-178">For failed or dropped email, or email not accessible by users, there won't be any email to mitigate, since these mails don't reach the mailbox.</span></span>

  <span data-ttu-id="77c50-179">下图显示了提交在操作中心中的外观。</span><span class="sxs-lookup"><span data-stu-id="77c50-179">The following image shows how a submission looks in Action Center.</span></span> <span data-ttu-id="77c50-180">修正可以包含多个提交。</span><span class="sxs-lookup"><span data-stu-id="77c50-180">A remediation can contain multiple submissions.</span></span> <span data-ttu-id="77c50-181">如果通过一次自动调查批准了多个操作，则每个电子邮件或电子邮件群集操作将与不同的提交出现在同一修补中。</span><span class="sxs-lookup"><span data-stu-id="77c50-181">If multiple actions get approved through one automated investigation, each email or email cluster action appears in the same remediation as a different submission.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="77c50-182">[![ZAP 电子邮件群集飞出面板。 ](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="77c50-182">[ ![ZAP email cluster flyout panel.](../../media/tp-RemediationArticle6.png) ](../../media/tp-RemediationArticle6.png#lightbox)</span></span>

  <span data-ttu-id="77c50-183">选择一个邮件提交项，以显示该修正的详细信息，例如，通过自动调查或威胁资源管理器触发修正时，通过选择查询) 以及修正的开始和结束时间， (的查询。</span><span class="sxs-lookup"><span data-stu-id="77c50-183">Select a mail submission item to show the details of that remediation, such as the query (when remediation is triggered through automated investigations or Threat Explorer through selecting a query) and the start and end times of remediation.</span></span> <span data-ttu-id="77c50-184">它还显示提交以进行修正的邮件的列表。</span><span class="sxs-lookup"><span data-stu-id="77c50-184">It also displays a list of messages that were submitted for remediation.</span></span> <span data-ttu-id="77c50-185">当邮件移出威胁浏览器保留期时，邮件将从该列表中消失。</span><span class="sxs-lookup"><span data-stu-id="77c50-185">As messages move out of the Threat Explorer retention period, the messages disappear from this list.</span></span> <span data-ttu-id="77c50-186">该列表还显示了 remediable 的单个邮件。</span><span class="sxs-lookup"><span data-stu-id="77c50-186">The list also shows individual messages that are remediable.</span></span>

- <span data-ttu-id="77c50-187">**操作日志**：此选项卡显示修正的邮件，包括批准的日期、批准操作的管理员、操作、状态和计数。</span><span class="sxs-lookup"><span data-stu-id="77c50-187">**Action logs**: This tab shows the messages remediated, including approved date, admin who approved the action, action, status, and counts.</span></span>

  <span data-ttu-id="77c50-188">状态可以是：</span><span class="sxs-lookup"><span data-stu-id="77c50-188">Status can be:</span></span>

  - <span data-ttu-id="77c50-189">**已启动**：将触发修正。</span><span class="sxs-lookup"><span data-stu-id="77c50-189">**Started**: Remediation is triggered.</span></span>
  - <span data-ttu-id="77c50-190">**排队**：修正将排队等待电子邮件的缓解。</span><span class="sxs-lookup"><span data-stu-id="77c50-190">**Queued**: Remediation is queued up for mitigation of emails.</span></span>
  - <span data-ttu-id="77c50-191">**正在进行**：正在进行缓解。</span><span class="sxs-lookup"><span data-stu-id="77c50-191">**In progress**: Mitigation is in progress.</span></span>
  - <span data-ttu-id="77c50-192">**已完成**：所有 remediable 电子邮件的缓解已成功完成或发生某些故障。</span><span class="sxs-lookup"><span data-stu-id="77c50-192">**Completed**: Mitigation on all remediable emails either completed successfully or with some failures.</span></span>
  - <span data-ttu-id="77c50-193">**失败**：未成功 remediations。</span><span class="sxs-lookup"><span data-stu-id="77c50-193">**Failed**: No remediations were successful.</span></span>

  <span data-ttu-id="77c50-194">由于只能对 remediable 电子邮件执行操作，因此每封电子邮件的清除都会显示为成功或失败。</span><span class="sxs-lookup"><span data-stu-id="77c50-194">As only remediable emails can be acted on, each email's cleanup is shown as successful or failed.</span></span> <span data-ttu-id="77c50-195">从 remediable 的总电子邮件中，报告成功和失败的缓解。</span><span class="sxs-lookup"><span data-stu-id="77c50-195">From the total remediable emails, successful and failed mitigations are reported.</span></span>

  - <span data-ttu-id="77c50-196">**成功**： remediable 电子邮件上的所需操作已完成。</span><span class="sxs-lookup"><span data-stu-id="77c50-196">**Success**: The desired action on remediable emails was accomplished.</span></span> <span data-ttu-id="77c50-197">例如：管理员想要删除邮箱中的电子邮件，以便管理员采取软删除电子邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-197">For example: An admin wants to remove emails from mailboxes, so the admin takes the action of soft-deleting emails.</span></span> <span data-ttu-id="77c50-198">如果在执行操作后原始文件夹中找不到 remediable 电子邮件，则状态将显示为 "成功"。</span><span class="sxs-lookup"><span data-stu-id="77c50-198">If a remediable email isn't found in the original folder after the action is taken, the status will show as successful.</span></span>

  - <span data-ttu-id="77c50-199">**失败**： remediable 电子邮件上的所需操作失败。</span><span class="sxs-lookup"><span data-stu-id="77c50-199">**Failure**: The desired action on remediable emails failed.</span></span> <span data-ttu-id="77c50-200">例如：管理员想要删除邮箱中的电子邮件，以便管理员采取软删除电子邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="77c50-200">For example: An admin wants to remove emails from mailboxes, so the admin takes the action of soft-deleting emails.</span></span> <span data-ttu-id="77c50-201">如果在执行操作后，在邮箱中仍找到 remediable 电子邮件，则状态将显示为 "失败"。</span><span class="sxs-lookup"><span data-stu-id="77c50-201">If a remediable email is still found in the mailbox after the action is taken, status will show as failed.</span></span>

  <span data-ttu-id="77c50-202">选择操作日志中的任何项目以显示修正详细信息。</span><span class="sxs-lookup"><span data-stu-id="77c50-202">Select any item in the action log to display remediation details.</span></span> <span data-ttu-id="77c50-203">如果详细信息说 "成功" 或 "在邮箱中找不到"，则表示该项目已从邮箱中删除。</span><span class="sxs-lookup"><span data-stu-id="77c50-203">If the details say "successful" or "not found in mailbox," that item was already removed from the mailbox.</span></span> <span data-ttu-id="77c50-204">有时，在修正过程中存在系统性错误。</span><span class="sxs-lookup"><span data-stu-id="77c50-204">Sometimes there's a systemic error during remediation.</span></span> <span data-ttu-id="77c50-205">在这些情况下，最好重试修正。</span><span class="sxs-lookup"><span data-stu-id="77c50-205">In those cases, it's a good idea to retry remediation.</span></span>
  
  <span data-ttu-id="77c50-206">在修正大型批处理的情况下，还可以通过邮件提交以及通过操作日志修正的邮件导出发送以进行修正的邮件。</span><span class="sxs-lookup"><span data-stu-id="77c50-206">In case of remediating large batches, you can also export the messages send for remediation via Mail Submission and messages which got remediated via Action Logs.</span></span> <span data-ttu-id="77c50-207">将导出限制增加到10万个记录。</span><span class="sxs-lookup"><span data-stu-id="77c50-207">The export limit is increased to 100k records.</span></span>

  <span data-ttu-id="77c50-208">修正是缓解威胁和解决可疑电子邮件的强大工具。</span><span class="sxs-lookup"><span data-stu-id="77c50-208">Remediation is a powerful tool to mitigate threats and address suspicious emails.</span></span> <span data-ttu-id="77c50-209">它有助于确保组织的安全。</span><span class="sxs-lookup"><span data-stu-id="77c50-209">It helps keep an organization secure.</span></span>
