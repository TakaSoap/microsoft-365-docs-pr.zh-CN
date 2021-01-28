---
title: 报告 Outlook 网页中的垃圾邮件和钓鱼电子邮件
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online 中 Outlook 网页版中的内置垃圾邮件报告选项 (Outlook Web App) 垃圾邮件报告选项，以及如何为用户禁用这些报告选项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0af57aceed608ae80e72e3ae18724925c1168e26
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029206"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="4a7e4-103">在 Exchange Online 的 Outlook 网页版中报告垃圾邮件和钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="4a7e4-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4a7e4-104">在 Exchange Online 中具有邮箱的 Microsoft 365 组织中，可以使用 Outlook 网页版中的内置报告选项 (以前称为 Outlook Web App)  (向 Exchange Online Protection (EOP) 提交标记为垃圾邮件) 、漏报 () 错误电子邮件和钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4a7e4-105">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="4a7e4-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4a7e4-106">如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议你使用安全与合规中心&门户。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="4a7e4-107">有关详细信息，请参阅"使用管理员提交"将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="4a7e4-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="4a7e4-108">管理员可以禁用或启用用户在 Web 上的 Outlook 中向 Microsoft 报告邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="4a7e4-109">有关详细信息，请参阅本文稍后介绍的" [在 Outlook 网页](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 版中禁用或启用垃圾邮件报告"部分。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="4a7e4-110">可以将报告的邮件配置为复制或重定向到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="4a7e4-111">有关详细信息，请参阅用户 [提交策略](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-111">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="4a7e4-112">有关向 Microsoft 报告邮件详细信息，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="4a7e4-113">报告 Outlook 网页中的垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="4a7e4-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="4a7e4-114">对于收件箱或其他任何电子邮件文件夹中的邮件（垃圾邮件除外），请使用以下任一方法来报告垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="4a7e4-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="4a7e4-115">选择邮件 **，单击工具栏** 上的"垃圾邮件"，然后选择"**垃圾邮件**"或"网络钓鱼 **"。**</span><span class="sxs-lookup"><span data-stu-id="4a7e4-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![从功能区报告垃圾邮件或网络钓鱼电子邮件](../../media/owa-report-junk.png)

   - <span data-ttu-id="4a7e4-117">选择一个或多个邮件，右键单击，然后选择 **"标记为垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="4a7e4-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="4a7e4-118">在出现的对话框中，单击"报告 **"。**</span><span class="sxs-lookup"><span data-stu-id="4a7e4-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="4a7e4-119">如果改变主意，请单击"**不报告"。**</span><span class="sxs-lookup"><span data-stu-id="4a7e4-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="4a7e4-120">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="4a7e4-120">Junk</span></span>|<span data-ttu-id="4a7e4-121">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="4a7e4-121">Phishing</span></span>|
   |:---:|:---:|
   |![报告为垃圾邮件对话框](../../media/owa-report-as-junk-dialog.png)|![报告为网络钓鱼对话框](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="4a7e4-124">选定的邮件将发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="4a7e4-125">若要确认已提交的邮件，请打开您的“已发送邮件”文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="4a7e4-126">从 Outlook 网页中的"垃圾邮件"文件夹报告非垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="4a7e4-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="4a7e4-127">在"垃圾邮件"文件夹中，使用以下任一方法来报告垃圾邮件误报或网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="4a7e4-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="4a7e4-128">选择邮件 **，单击工具栏** 上的"非垃圾邮件"，然后选择"**非垃圾邮件**"或"网络钓鱼 **"。**</span><span class="sxs-lookup"><span data-stu-id="4a7e4-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![从功能区报告非垃圾邮件或钓鱼电子邮件](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="4a7e4-130">选择一个或多个邮件，右键单击，然后选择 **"标记为非垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="4a7e4-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="4a7e4-131">在出现的对话框中，阅读信息并单击"报告 **"。**</span><span class="sxs-lookup"><span data-stu-id="4a7e4-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="4a7e4-132">如果改变主意，请单击"**不报告"。**</span><span class="sxs-lookup"><span data-stu-id="4a7e4-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="4a7e4-133">非垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="4a7e4-133">Not Junk</span></span>|<span data-ttu-id="4a7e4-134">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="4a7e4-134">Phishing</span></span>|
   |:---:|:---:|
   |![报告为非垃圾邮件对话框](../../media/owa-report-as-not-junk-dialog.png)|![报告为网络钓鱼对话框](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="4a7e4-137">选定的邮件将发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="4a7e4-138">若要确认已提交的邮件，请打开您的“已发送邮件”文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="4a7e4-139">在 Outlook 网页中禁用或启用垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="4a7e4-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="4a7e4-140">默认情况下，用户可以向 Microsoft 报告垃圾邮件误报、漏报和网络钓鱼邮件，以在 Outlook 网页中进行分析。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="4a7e4-141">管理员可以在 Exchange Online PowerShell 中配置 Outlook 网页版邮箱策略，以防止用户向 Microsoft 报告垃圾邮件误报和垃圾邮件漏报。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="4a7e4-142">无法禁用用户向 Microsoft 报告网络钓鱼邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4a7e4-143">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="4a7e4-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4a7e4-144">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4a7e4-145">您需在 Exchange Online 中获得权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-145">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="4a7e4-146">具体来说，您需要 **收件人策略** 或 **邮件收件人** 角色，这些角色默认情况下分配给组织管理角色组和 **收件人管理** 角色组。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="4a7e4-147">有关 Exchange Online 中的角色组详细信息，请参阅 [Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 中的权限和修改 Exchange [Online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-147">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="4a7e4-148">每个组织都有一个名为 OwaMailboxPolicy-Default 的默认策略，但您可以创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="4a7e4-149">自定义策略应用于默认策略之前的范围用户。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="4a7e4-150">有关 Outlook 网页版邮箱策略详细信息，请参阅 [Exchange Online 中的 Outlook 网页版邮箱策略](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="4a7e4-151">禁用垃圾邮件报告不会删除在 Web 上的 Outlook 中将邮件标记为垃圾邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="4a7e4-152">选择"垃圾邮件"文件夹中的邮件 **并单击"** 非垃圾邮件"仍将 \> 邮件移回收件箱。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="4a7e4-153">选择任何其他电子邮件文件夹中的邮件并单击 **"垃圾邮件**"仍将 \> 邮件移动到"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="4a7e4-154">不再可用的是向 Microsoft 报告邮件的选项。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="4a7e4-155">使用 Exchange Online PowerShell 禁用或启用 Outlook 网页版中的垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="4a7e4-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="4a7e4-156">若要查找现有的 Outlook 网页邮件策略和垃圾邮件报告的状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4a7e4-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="4a7e4-157">若要在 Web 上的 Outlook 中禁用或启用垃圾邮件报告，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="4a7e4-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="4a7e4-158">本示例在默认策略中禁用垃圾邮件报告。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="4a7e4-159">此示例在名为 Contoso Managers 的自定义策略中启用垃圾邮件报告。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="4a7e4-160">有关语法和参数的详细信息，请参阅[Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy)和[Set-OwaMailboxPolicy。](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="4a7e4-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="4a7e4-161">您如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="4a7e4-161">How do you know this worked?</span></span>

<span data-ttu-id="4a7e4-162">若要验证您是否已成功启用或禁用 Outlook 网页中的垃圾邮件报告，请使用以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="4a7e4-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="4a7e4-163">在 Exchange Online PowerShell 中，运行以下命令并验证 **ReportJunkEmailEnabled** 属性值：</span><span class="sxs-lookup"><span data-stu-id="4a7e4-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="4a7e4-164">在 Web 上的 Outlook 中打开受影响的用户的邮箱，在收件箱中选择一封邮件，单击"垃圾邮件"并验证向 Microsoft 报告邮件的 \> 提示是否显示。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4a7e4-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="4a7e4-165">在 Web 上的 Outlook 中打开受影响的用户的邮箱，在"垃圾邮件"文件夹中选择一封邮件，单击"垃圾邮件"并验证向 Microsoft 报告邮件的 \> 提示是否显示。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4a7e4-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="4a7e4-166"><sup>\*</sup> 用户可以隐藏提示以报告邮件，同时仍报告邮件。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="4a7e4-167">若要在 Outlook 网页中检查此设置，请：</span><span class="sxs-lookup"><span data-stu-id="4a7e4-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="4a7e4-168">单击 **"** ![ 设置 Outlook 网页"设置图标 ](../../media/owa-settings-icon.png) \> **"查看所有 Outlook 设置** \> **垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="4a7e4-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="4a7e4-169">在" **报告** "部分，验证值： **在发送报告之前询问我**。</span><span class="sxs-lookup"><span data-stu-id="4a7e4-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook 网页垃圾邮件报告设置](../../media/owa-junk-email-reporting-options.png)
