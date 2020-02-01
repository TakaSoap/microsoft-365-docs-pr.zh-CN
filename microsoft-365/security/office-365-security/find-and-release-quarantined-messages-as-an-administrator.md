---
title: 以管理员身份查找并释放隔离邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: 本主题介绍了 Exchange Online 和 Exchange Online Protection (EOP) 管理员如何在 Exchange 管理中心 (EAC) 中查找、释放和报告隔离邮件。
ms.openlocfilehash: d7ea57f1dc78b21dae713ca1b9861abafacfc53a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599389"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a><span data-ttu-id="aacc4-103">以管理员身份查找并释放隔离邮件</span><span class="sxs-lookup"><span data-stu-id="aacc4-103">Find and release quarantined messages as an administrator</span></span>

<span data-ttu-id="aacc4-104">本主题介绍了 Exchange Online 和 Exchange Online Protection (EOP) 管理员如何在 Exchange 管理中心 (EAC) 中查找、释放和报告隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-104">This topic describes how Exchange Online and Exchange Online Protection (EOP) admins can find, release, and report on quarantined messages in the Exchange admin center (EAC).</span></span> <span data-ttu-id="aacc4-105">Office 365 将邮件定向到隔离区，因为它们被标识为垃圾邮件或与邮件流规则匹配（也称为 "传输规则"）。</span><span class="sxs-lookup"><span data-stu-id="aacc4-105">Office 365 directs messages to quarantine either because they were identified as spam or they matched a mail flow rule (also known as a transport rule).</span></span>

<span data-ttu-id="aacc4-106">您可以使用安全 & 合规中心（而不是 EAC）来完成这些任务中的任何任务;Exchange 管理中心（EAC）内的隔离门户将设置为 "decommisioned"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-106">You can use the Security & Compliance Center instead of the EAC to complete any of these tasks as well; the Quarantine portal within the Exchange admin center (EAC) is set to be decommisioned.</span></span> <span data-ttu-id="aacc4-107">有关详细信息，请参阅[在 Office 365 中隔离电子邮件消息](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="aacc4-107">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="aacc4-108">已隔离邮件在 EAC 的 "**隔离**" 页面上列出。</span><span class="sxs-lookup"><span data-stu-id="aacc4-108">Quarantined messages are listed on the **quarantine** page in EAC.</span></span> <span data-ttu-id="aacc4-109">默认情况下，"**接收**时间" 字段中的邮件按从最新到最旧的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="aacc4-109">By default, messages are sorted from newest to oldest on the **RECEIVED** field.</span></span> <span data-ttu-id="aacc4-110">还将为每封邮件列出“发件人”\*\*\*\*、“主题”\*\*\*\* 和“到期”\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="aacc4-110">**SENDER**, **SUBJECT**, and **EXPIRES** values are also listed for each message.</span></span> <span data-ttu-id="aacc4-111">您可以通过单击标题来对任何字段排序。</span><span class="sxs-lookup"><span data-stu-id="aacc4-111">You can sort on any of these fields by clicking their headers.</span></span> <span data-ttu-id="aacc4-112">再次单击列标题将按相反顺序排序。</span><span class="sxs-lookup"><span data-stu-id="aacc4-112">If you click a column header a second time, the sort order reverses.</span></span> <span data-ttu-id="aacc4-113">"**隔离**" 页面最多显示500个邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-113">The **quarantine** page displays a maximum of 500 messages.</span></span>

<span data-ttu-id="aacc4-p104">您可以查看所有隔离邮件的列表，或者通过指定筛选条件来搜索特定邮件（如果邮件超过 500 封，筛选还可以帮助减少结果集）。搜索并找到特定的隔离邮件之后，可以查看关于邮件的详细信息。您还可以：</span><span class="sxs-lookup"><span data-stu-id="aacc4-p104">You can view a list of all quarantined messages, or you can search for specific messages by specifying filter criteria (filtering can also help reduce your result set if you have more than 500 messages). After searching for and locating a specific quarantined message, you can view details about the message. You can also:</span></span>

- <span data-ttu-id="aacc4-p105">向一个或多个收件人释放邮件，并且选择向 Microsoft 垃圾邮件分析团队将其报告为误报（非垃圾邮件），他们将评估并分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-p105">Release the message to one or more recipients, and optionally report it as a false positive (not junk) message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>

- <span data-ttu-id="aacc4-119">释放邮件并允许接收该发件人未来发送的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-119">Release the message and allow all future messages from that sender.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aacc4-120">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="aacc4-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="aacc4-121">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="aacc4-121">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="aacc4-122">若要查看所需的权限，请参阅[Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)主题中的 "隔离" 条目。</span><span class="sxs-lookup"><span data-stu-id="aacc4-122">To see what permissions you need, see the "Quarantine" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span>

- <span data-ttu-id="aacc4-123">您可以在 "**隔离**" 页面上一次释放或报告多封邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-123">You can release or report multiple messages at once on the **quarantine** page.</span></span> <span data-ttu-id="aacc4-124">或者，您可以创建一个远程 Windows PowerShell 脚本来完成此任务。</span><span class="sxs-lookup"><span data-stu-id="aacc4-124">Alternatively you can create a remote Windows PowerShell script to accomplish this task.</span></span> <span data-ttu-id="aacc4-125">使用[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet 搜索邮件，并使用[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet 释放邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-125">Use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for messages, and the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet to release them.</span></span>

- <span data-ttu-id="aacc4-126">有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="aacc4-126">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="aacc4-127">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="aacc4-127">Having problems?</span></span> <span data-ttu-id="aacc4-128">在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="aacc4-128">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a><span data-ttu-id="aacc4-129">使用高级搜索来筛选和查找隔离邮件</span><span class="sxs-lookup"><span data-stu-id="aacc4-129">Use advanced search to filter and locate quarantined messages</span></span>

<span data-ttu-id="aacc4-p109">在 Exchange 管理中心 (EAC) 中，您可以使用高级搜索根据一些不同的条件筛选隔离邮件。这些条件可以单独使用，也可以结合使用。搜索将提供满足您的所有筛选条件的邮件列表。</span><span class="sxs-lookup"><span data-stu-id="aacc4-p109">In the Exchange admin center (EAC), you can filter quarantined items based on several different conditions using advanced search. You can use these conditions separately or in combination with one another. The search will provide a list of messages that meet all your filter criteria.</span></span>

1. <span data-ttu-id="aacc4-133">在 EAC 中，导航到 "**保护** \> **隔离**"，然后单击 "**高级搜索**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-133">In EAC, navigate to **Protection** \> **quarantine**, and then click **Advanced search**.</span></span>

2. <span data-ttu-id="aacc4-134">在 "**高级搜索**" 窗口中，选择下列条件的任意组合。</span><span class="sxs-lookup"><span data-stu-id="aacc4-134">In the **Advanced search** window, select any combination of the following conditions.</span></span> <span data-ttu-id="aacc4-135">选中关联的复选框，以启用各个条件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-135">Select the associated check box to enable each condition.</span></span> <span data-ttu-id="aacc4-136">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="aacc4-136">Wildcards aren't supported.</span></span>

   1. <span data-ttu-id="aacc4-137">**邮件 ID**：您可以使用此参数对特定邮件执行目标搜索。</span><span class="sxs-lookup"><span data-stu-id="aacc4-137">**Message ID**: You can use this parameter to perform a targeted search for a specific message.</span></span> <span data-ttu-id="aacc4-138">例如，如果特定邮件由贵组织的用户发送，或准备发送给贵组织的用户，但是未抵达目标收件人，则您可以使用邮件跟踪功能搜索该邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-138">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reaches its destination, you can search for the message using the message trace feature.</span></span> <span data-ttu-id="aacc4-139">有关详细信息，请参阅 [运行邮件跟踪和查看结果](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/run-a-message-trace-and-view-results)。</span><span class="sxs-lookup"><span data-stu-id="aacc4-139">For details, see [Run a Message Trace and View Results](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/run-a-message-trace-and-view-results).</span></span> <span data-ttu-id="aacc4-140">如果您发现邮件被发送到隔离区，可能是因为它符合某个规则或被标识为垃圾邮件，您可以通过指定其邮件 ID，在隔离区中轻松找到此邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-140">If you discover that the message was sent to the quarantine, perhaps because it matched a rule or was identified as spam, you can then easily find this message in the quarantine by specifying its Message ID.</span></span> <span data-ttu-id="aacc4-141">请务必包含完整的邮件 ID 字符串。</span><span class="sxs-lookup"><span data-stu-id="aacc4-141">Be sure to include the full Message ID string.</span></span> <span data-ttu-id="aacc4-142">这可能包括尖括号 (\<\>)。</span><span class="sxs-lookup"><span data-stu-id="aacc4-142">This might include angle brackets (\<\>).</span></span>

   2. <span data-ttu-id="aacc4-143">**发件人电子邮件地址**：指定发送邮件的人员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aacc4-143">**Sender email address**: Specify the email address of the person who sent the message.</span></span>

   3. <span data-ttu-id="aacc4-144">**收件人电子邮件地址**：指定邮件的预期收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aacc4-144">**Recipient email address**: Specify the email address of the intended recipient of the message.</span></span>

   4. <span data-ttu-id="aacc4-145">**主题**：指定邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="aacc4-145">**Subject**: Specify the subject line text of the message.</span></span>

   5. <span data-ttu-id="aacc4-146">**已接收**：可以选择在过去24小时内（"**今天**"）、过去的48小时内（"过去**2 天**"）、过去一周内（"过去**7 天**"）的隔离中接收邮件，也可以选择隔离邮箱接收邮件的自定义时间间隔。</span><span class="sxs-lookup"><span data-stu-id="aacc4-146">**Received**: You can select that the message was received by quarantine within the past 24 hours ( **Today**), within the past 48 hours ( **Last 2 days**), within the past week ( **Last 7 days**), or you can select a custom time interval during which the message was received by the quarantine.</span></span>

   6. <span data-ttu-id="aacc4-147">**过期**：您可以选择在接下来的24小时内（"**今天**"），在接下来的48小时内（**接下来的2天**），在下一周内（接下来**7 天**），或者您可以选择将邮件从隔离区中删除的自定义时间间隔。</span><span class="sxs-lookup"><span data-stu-id="aacc4-147">**Expires**: You can select that the message will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval during which the message will be deleted from quarantine.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="aacc4-148">默认情况下，垃圾邮件隔离的邮件会在30天内保留，而与邮件流规则匹配的隔离邮件将在隔离中保留最长30天，并根据您在默认内容筛选策略中设置的保留期。</span><span class="sxs-lookup"><span data-stu-id="aacc4-148">By default, spam-quarantined messages are kept in quarantine for 30 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for up to 30 days based on the retention period set in your default content filter policy.</span></span> <span data-ttu-id="aacc4-149">7 天后，这些邮件将被 Office 365 删除并且不可检索。</span><span class="sxs-lookup"><span data-stu-id="aacc4-149">After this period of time Office 365 deletes the messages and they are not retrievable.</span></span> <span data-ttu-id="aacc4-150">与邮件流规则匹配的隔离邮件的保留期不可配置。</span><span class="sxs-lookup"><span data-stu-id="aacc4-150">The retention period for quarantined messages that matched a mail flow rule is not configurable.</span></span> <span data-ttu-id="aacc4-151">但是，垃圾邮件隔离邮件的保留期可以通过内容筛选器策略中的 "**保留垃圾邮件（天）** " 设置来降低。</span><span class="sxs-lookup"><span data-stu-id="aacc4-151">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="aacc4-152">有关详细信息，请参阅“[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)”。</span><span class="sxs-lookup"><span data-stu-id="aacc4-152">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   7. <span data-ttu-id="aacc4-153">**类型**您可以指定是否搜索已被标识为**垃圾**邮件的隔离邮件，或者是否搜索与邮件流规则匹配的邮件（**传输规则**）。</span><span class="sxs-lookup"><span data-stu-id="aacc4-153">**Type** You can specify whether to search for quarantined messages that have been identified as **Spam**, or whether to search for messages that matched a mail flow rule (**Transport rule**).</span></span>

3. <span data-ttu-id="aacc4-154">单击 **"确定"** 开始运行高级搜索。</span><span class="sxs-lookup"><span data-stu-id="aacc4-154">Click **OK** to start running the advanced search.</span></span>

   > [!NOTE]
   > <span data-ttu-id="aacc4-155">若要清除搜索条件并查看隔离中的所有邮件，请清除 "**高级搜索**" 窗口中的所有复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="aacc4-155">To clear your search criteria and view all messages in the quarantine, clear all the check boxes in the **Advanced search** window, and then click **OK**.</span></span>

<span data-ttu-id="aacc4-p113">在搜索好邮件后，匹配您的指定条件的结果将显示在用户界面中。EAC 中可显示最多 500 封邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-p113">After searching for messages, the results that match your specified criteria will display in the user interface. A maximum of 500 messages can be displayed in the EAC.</span></span>

## <a name="view-details-about-a-specific-quarantined-message"></a><span data-ttu-id="aacc4-158">查看有关特定隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="aacc4-158">View details about a specific quarantined message</span></span>

<span data-ttu-id="aacc4-159">在**隔离**页上找到特定的隔离邮件后，您可以查看有关该邮件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aacc4-159">After locating a specific quarantined message on the **quarantine** page, you can view details about it.</span></span>

1. <span data-ttu-id="aacc4-160">在 "**隔离**" 页面上，选择特定的邮件，屏幕右侧的详细信息窗格中将显示该邮件的属性摘要。</span><span class="sxs-lookup"><span data-stu-id="aacc4-160">On the **quarantine** page, select a specific message and a summary of the properties of that message appear in the details pane on the right side of the screen.</span></span>

   <span data-ttu-id="aacc4-161">**邮件状态**值如下所示：</span><span class="sxs-lookup"><span data-stu-id="aacc4-161">The **Message status** values are as follows:</span></span>

   - <span data-ttu-id="aacc4-162">**类型**：表示是否已将邮件标识为**垃圾**邮件或与邮件流规则（**传输规则**）相匹配。</span><span class="sxs-lookup"><span data-stu-id="aacc4-162">**Type**: Denotes whether the message has been identified as **Spam** or matched a mail flow rule (**Transport rule**).</span></span>

   - <span data-ttu-id="aacc4-163">**过期**时间：将从隔离区中删除邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="aacc4-163">**Expires**: The date when the message will be deleted from the quarantine.</span></span>

   <span data-ttu-id="aacc4-164">**消息详细信息**值如下所示：</span><span class="sxs-lookup"><span data-stu-id="aacc4-164">The **Message details** values are as follows:</span></span>

   - <span data-ttu-id="aacc4-165">**发件人**：发送邮件的人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aacc4-165">**Sender**: The email address of the person who sent the message.</span></span>

   - <span data-ttu-id="aacc4-166">**Subject**：邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="aacc4-166">**Subject**: The subject line text of the message.</span></span>

   - <span data-ttu-id="aacc4-167">**已接收**：隔离人收到邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="aacc4-167">**Received**: The date on which the message was received by the quarantine.</span></span>

   - <span data-ttu-id="aacc4-168">**大小**：邮件的大小，以千字节（kb）为单位，如果邮件大小大于 999 kb，则为兆字节（mb）。</span><span class="sxs-lookup"><span data-stu-id="aacc4-168">**Size**: The size of the message, in kilobytes (KB), or, if the message size is greater than 999 KBs, in megabytes (MB).</span></span>

   - <span data-ttu-id="aacc4-169">**查看邮件头**：单击此链接可打开 "**邮件头**" 对话框，您可以通过该对话框查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="aacc4-169">**View message header**: Click this link to open the **message header** dialog box, which lets you view the message header text.</span></span> <span data-ttu-id="aacc4-170">您还可以将邮件头文本复制到剪贴板，并粘贴到 [邮件头分析器](https://testconnectivity.microsoft.com/?tabid=mha)。</span><span class="sxs-lookup"><span data-stu-id="aacc4-170">You can also copy the message header text to your clipboard and paste it into the [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha).</span></span> <span data-ttu-id="aacc4-171">进入邮件头分析器工具后，单击" **分析标头**"以检索关于标头的信息。</span><span class="sxs-lookup"><span data-stu-id="aacc4-171">Once in the Message Header Analyzer tool, click **Analyze headers** in order to retrieve information about the header.</span></span>

    > [!TIP]
    > <span data-ttu-id="aacc4-172">有关服务插入的特定反垃圾邮件的邮件头字段的信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="aacc4-172">For information about specific anti-spam message header fields inserted by the service, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

   - <span data-ttu-id="aacc4-173">**预览电子邮件**单击此链接可查看邮件文本。</span><span class="sxs-lookup"><span data-stu-id="aacc4-173">**Preview email message** Click this link to review the text of the message.</span></span>

2. <span data-ttu-id="aacc4-174">如果双击隔离邮件，**隔离的邮件**窗口将打开，并显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="aacc4-174">If you double-click a quarantined message, the **Quarantined message** window opens and displays the following information:</span></span>

   - <span data-ttu-id="aacc4-175">**发布到**：已释放邮件的所有电子邮件地址的列表（如果有）。</span><span class="sxs-lookup"><span data-stu-id="aacc4-175">**Released to**: A list of all email addresses to whom the message has been released, if any.</span></span>

   - <span data-ttu-id="aacc4-176">**尚未发布到**：邮件尚未发布到的所有电子邮件地址的列表（如果有）。</span><span class="sxs-lookup"><span data-stu-id="aacc4-176">**Not yet released to**: A list of all email addresses to whom the message has not been released, if any.</span></span> <span data-ttu-id="aacc4-177">您可以单击 "**发布到**" 链接以释放邮件;有关释放邮件的详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="aacc4-177">You can click the **Release to** link in order to release the message; for more information about releasing a message, see the next section.</span></span>

   - <span data-ttu-id="aacc4-178">**邮件 id**：在邮件头中找到的 INTERNET 邮件 id （也称为 "客户端 ID"）。</span><span class="sxs-lookup"><span data-stu-id="aacc4-178">**Message ID**: The Internet Message ID (also known as the Client ID) found in the header of the message.</span></span>

   <span data-ttu-id="aacc4-179">单击 "**关闭**" 返回到主隔离窗格。</span><span class="sxs-lookup"><span data-stu-id="aacc4-179">Click **Close** to return to the main quarantine pane.</span></span>

## <a name="release-messages-from-quarantine"></a><span data-ttu-id="aacc4-180">从隔离区中释放邮件</span><span class="sxs-lookup"><span data-stu-id="aacc4-180">Release messages from quarantine</span></span>

<span data-ttu-id="aacc4-181">如果您想将邮件释放给收件人，您可以：</span><span class="sxs-lookup"><span data-stu-id="aacc4-181">If you want to release messages to recipients, your options are:</span></span>

- [<span data-ttu-id="aacc4-182">释放隔离邮件并允许接收该发件人未来发送的邮件</span><span class="sxs-lookup"><span data-stu-id="aacc4-182">Release a quarantined message and allow future messages from the sender</span></span>](#release-a-quarantined-message-and-allow-future-messages-from-the-sender)

- [<span data-ttu-id="aacc4-183">将隔离邮件释放给特定收件人，而不将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="aacc4-183">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>](#release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive)

- [<span data-ttu-id="aacc4-184">将一个或多个隔离邮件释放给所有收件人</span><span class="sxs-lookup"><span data-stu-id="aacc4-184">Release one or more quarantined messages to all recipients</span></span>](#release-one-or-more-quarantined-messages-to-all-recipients)

- [<span data-ttu-id="aacc4-185">将一个或多个隔离邮件释放给所有收件人并将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="aacc4-185">Release one or more quarantined messages to all recipients and report false positives</span></span>](#release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives)

### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a><span data-ttu-id="aacc4-186">释放隔离邮件并允许接收该发件人未来发送的邮件</span><span class="sxs-lookup"><span data-stu-id="aacc4-186">Release a quarantined message and allow future messages from the sender</span></span>

1. <span data-ttu-id="aacc4-187">在 EAC 中，导航到 "**保护** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-187">In EAC, navigate to **Protection** \> **quarantine**.</span></span>

2. <span data-ttu-id="aacc4-188">单击邮件以将其选中，然后单击 "**释放邮件**" 图标，如下面的屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="aacc4-188">Click on a message to select it and then click the **Release Message** icon as shown in the following screen shot.</span></span>

   ![显示隔离页（包含突出显示的释放邮件图标和释放选项）](../media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)

   <span data-ttu-id="aacc4-190">从下拉列表中单击 "**释放所选邮件并允许发件人**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-190">Click **Release selected message and allow sender** from the drop-down list.</span></span>

3. <span data-ttu-id="aacc4-191">将打开 "**释放邮件并允许发件人**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="aacc4-191">The **release message and allow sender** dialog box opens.</span></span> <span data-ttu-id="aacc4-192">（可选）您可以选择向 Microsoft 报告邮件，然后单击 "**释放并允许**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-192">Optionally, you can choose to report the message to Microsoft, then click **release and allow**.</span></span> <span data-ttu-id="aacc4-193">该邮件将被释放给所有收件人并将允许接收此发件人未来发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-193">The message will be released to all recipients it's addressed to and all future messages from this sender will be allowed.</span></span> <span data-ttu-id="aacc4-194">但是，如果此邮件是由于邮件流规则或阻止发件人而被隔离的，则将继续阻止发件人的后续邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-194">However, if this message was quarantined because of a mail flow rule or blocked sender, the sender will continue to be blocked for future messages.</span></span>

### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a><span data-ttu-id="aacc4-195">将隔离邮件释放给特定收件人，而不将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="aacc4-195">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>

1. <span data-ttu-id="aacc4-196">在 EAC 中，导航到 "**保护** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-196">In EAC, navigate to **Protection** \> **quarantine**.</span></span>

2. <span data-ttu-id="aacc4-197">选择一封邮件，单击 "**释放邮件**" 图标，然后从下拉列表中单击 "**将邮件释放给特定收件人**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-197">Select a message, click the **Release Message** icon, and then click **Release message to specific recipients** from the drop-down list.</span></span>

3. <span data-ttu-id="aacc4-198">在“释放邮件”\*\*\*\* 对话框中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="aacc4-198">In the **release message** dialog box, select one of the following options:</span></span>

   - <span data-ttu-id="aacc4-199">**向所有收件人释放邮件**选择此选项时，请注意，不能将一封邮件释放到同一收件人的一次。</span><span class="sxs-lookup"><span data-stu-id="aacc4-199">**Release message to all recipients** When you select this option, be aware that a message cannot be released more than once to the same recipient.</span></span> <span data-ttu-id="aacc4-200">如果收件人之前已经收到此邮件，则邮件不会再次释放给该收件人。</span><span class="sxs-lookup"><span data-stu-id="aacc4-200">If a recipient has previously received the message, it will not be released again to that recipient.</span></span>

   - <span data-ttu-id="aacc4-201">**将邮件释放给指定的收件人**选择可将邮件释放到的收件人。</span><span class="sxs-lookup"><span data-stu-id="aacc4-201">**Release message to specified recipients** Select the recipient(s) to whom the message can be released.</span></span> <span data-ttu-id="aacc4-202">由于一封邮件只能释放给每个收件人一次，因此该列表仅显示邮件可被释放给的目标收件人。</span><span class="sxs-lookup"><span data-stu-id="aacc4-202">Because a message can only be released once to each recipient, only recipients to whom it can be released appear in this list.</span></span> <span data-ttu-id="aacc4-203">支持多选。</span><span class="sxs-lookup"><span data-stu-id="aacc4-203">Multi-selection is supported.</span></span> <span data-ttu-id="aacc4-204">做出选择后，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-204">After making your recipient selections, click **add**.</span></span>

4. <span data-ttu-id="aacc4-205">单击“释放”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aacc4-205">Click **release**.</span></span>

<span data-ttu-id="aacc4-206">如果单击 "**刷新** ![刷新"](../media/ITPro-EAC-RefreshIcon.gif)图标刷新数据，然后双击邮件，您应该会看到它已发布到预期收件人。</span><span class="sxs-lookup"><span data-stu-id="aacc4-206">If you click **Refresh** ![Refresh Icon](../media/ITPro-EAC-RefreshIcon.gif) to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span>

### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a><span data-ttu-id="aacc4-207">将一个或多个隔离邮件释放给所有收件人</span><span class="sxs-lookup"><span data-stu-id="aacc4-207">Release one or more quarantined messages to all recipients</span></span>

1. <span data-ttu-id="aacc4-208">在 EAC 中，导航到 "**保护** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-208">In EAC, navigate to **Protection** \> **quarantine**.</span></span>

2. <span data-ttu-id="aacc4-209">单击邮件以选中它，或使用 Shift 键来选择多封邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-209">Click on a message to select it, or use the shift key to select multiple messages.</span></span> <span data-ttu-id="aacc4-210">然后单击 "**释放邮件**" 图标。</span><span class="sxs-lookup"><span data-stu-id="aacc4-210">Then click the **Release Message** icon.</span></span>

3. <span data-ttu-id="aacc4-211">从下拉列表中单击 "**将所选邮件释放给所有收件人**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-211">Click **Release selected message(s) to ALL recipients** from the drop-down list.</span></span>

4. <span data-ttu-id="aacc4-212">此时会打开一个警告对话框。</span><span class="sxs-lookup"><span data-stu-id="aacc4-212">The warning dialog box opens.</span></span> <span data-ttu-id="aacc4-213">阅读警告，如果要继续，请选择 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="aacc4-213">Read the warning and select **Yes** if you want to proceed.</span></span> <span data-ttu-id="aacc4-214">选择此选项时，请注意不能将一封邮件释放给同一收件人超过一次。</span><span class="sxs-lookup"><span data-stu-id="aacc4-214">When you select this option, be aware that a message cannot be released more than once to the same recipient.</span></span> <span data-ttu-id="aacc4-215">如果收件人之前已经收到此邮件，则邮件不会再次释放给该收件人。</span><span class="sxs-lookup"><span data-stu-id="aacc4-215">If a recipient has previously received the message, it will not be released again to that recipient.</span></span>

### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a><span data-ttu-id="aacc4-216">将一个或多个隔离邮件释放给所有收件人并将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="aacc4-216">Release one or more quarantined messages to all recipients and report false positives</span></span>

1. <span data-ttu-id="aacc4-217">在 EAC 中，导航到 "**保护** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-217">In EAC, navigate to **Protection** \> **quarantine**.</span></span>

2. <span data-ttu-id="aacc4-218">单击邮件以选中它，或使用 Shift 键来选择多封邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-218">Click on a message to select it, or use the shift key to select multiple messages.</span></span> <span data-ttu-id="aacc4-219">然后单击 "**释放邮件**" 图标。</span><span class="sxs-lookup"><span data-stu-id="aacc4-219">Then click the **Release Message** icon.</span></span>

3. <span data-ttu-id="aacc4-220">从下拉列表中单击 "**释放所选邮件并报告为误报**"。</span><span class="sxs-lookup"><span data-stu-id="aacc4-220">Click **Release selected message(s) and report as false positive** from the drop-down list.</span></span>

4. <span data-ttu-id="aacc4-221">此时会打开一个警告对话框。</span><span class="sxs-lookup"><span data-stu-id="aacc4-221">The warning dialog box opens.</span></span> <span data-ttu-id="aacc4-222">阅读警告，如果要继续，请选择 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="aacc4-222">Read the warning and select **Yes** if you want to proceed.</span></span> <span data-ttu-id="aacc4-223">选择此选项时，请注意不能将一封邮件释放给同一收件人超过一次。</span><span class="sxs-lookup"><span data-stu-id="aacc4-223">When you select this option, be aware that a message cannot be released more than once to the same recipient.</span></span> <span data-ttu-id="aacc4-224">如果收件人之前已经收到此邮件，则邮件不会再次释放给该收件人。</span><span class="sxs-lookup"><span data-stu-id="aacc4-224">If a recipient has previously received the message, it will not be released again to that recipient.</span></span>

   <span data-ttu-id="aacc4-p123">选择此选项时，会将邮件释放到所有尚未收到此邮件的收件人。如果此邮件是隔离的垃圾邮件，还会将其报告给 Microsoft 垃圾邮件分析团队，该团队将评估和分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-p123">When you choose this option, the message will be released to all recipients who have not yet received it. If it's a spam-quarantined message, it will also be reported to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>

> [!TIP]
> <span data-ttu-id="aacc4-228">按照[如何确保邮件不会标记为垃圾邮件](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)中的步骤，确保邮件未标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="aacc4-228">Help ensure that a message isn't marked as spam by following the steps in [How to help ensure that a message isn't marked as spam](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md).</span></span>

<span data-ttu-id="aacc4-229">如果单击 "**刷新**![刷新" 图标](../media/ITPro-EAC-RefreshIcon.gif)图标刷新数据，然后双击邮件，您应该会看到它已发布给预期的收件人。</span><span class="sxs-lookup"><span data-stu-id="aacc4-229">If you click the **Refresh**![Refresh Icon](../media/ITPro-EAC-RefreshIcon.gif) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="aacc4-230">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="aacc4-230">For more information</span></span>

[<span data-ttu-id="aacc4-231">隔离常见问题解答</span><span class="sxs-lookup"><span data-stu-id="aacc4-231">Quarantine FAQ</span></span>](quarantine-faq.md)
