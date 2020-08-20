---
title: 在 Outlook 网页版中报告垃圾和钓鱼电子邮件
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online 中 Outlook 网页版中的内置垃圾邮件、非垃圾邮件和 (Outlook Web App) 钓鱼电子邮件报告选项，以及如何为用户禁用这些报告选项。
ms.openlocfilehash: a364afed9bb7e61d5f34ffc0206ede1c5155db65
ms.sourcegitcommit: c692bdc186fb29499816e8bb2addcddef34d23d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818329"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="2f95c-103">在 Exchange Online 的 Outlook 网页版中报告垃圾和钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="2f95c-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

<span data-ttu-id="2f95c-104">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，你可以使用 Web 上的 Outlook (中内置报告 Outlook Web App) 选项，将误报选项提交误报 (正确的电子邮件被标记为垃圾邮件) 、漏报邮件 (允许) 错误 (正式邮件和网络钓鱼邮件提交到 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="2f95c-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2f95c-105">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2f95c-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2f95c-106">如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议您使用安全与合规中心中的&提交门户。</span><span class="sxs-lookup"><span data-stu-id="2f95c-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="2f95c-107">有关详细信息，请参阅["使用管理员提交"将可取的垃圾邮件、网络钓鱼邮件、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="2f95c-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="2f95c-108">管理员可以禁用或启用用户在 Web 上的 Outlook 中向 Microsoft 报告邮件。</span><span class="sxs-lookup"><span data-stu-id="2f95c-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="2f95c-109">有关详细信息，请参阅本主题 [后面"在 Outlook 网页版中禁用或启用](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 垃圾邮件报告"一节。</span><span class="sxs-lookup"><span data-stu-id="2f95c-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="2f95c-110">您可以将报告的邮件配置为复制或重定向到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2f95c-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="2f95c-111">有关详细信息，请参阅 [在 Exchange Online 中指定提交用户收集的垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="2f95c-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="2f95c-112">有关向 Microsoft 报告消息的详细信息，请参阅"[报告邮件和文件到 Microsoft"。](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="2f95c-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="2f95c-113">在 Outlook 网页版中报告垃圾邮件和钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="2f95c-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="2f95c-114">对于"收件箱"或"垃圾邮件"之外的任何其他电子邮件文件夹中的邮件，请使用下列两种方法中的任何一种来报告垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="2f95c-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="2f95c-115">选择邮件 **，然后在**工具栏上单击"垃圾邮件"，然后选择"**垃圾邮件"\*\*\*\*或"网络钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="2f95c-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![从功能区报告垃圾或钓鱼电子邮件](../../media/owa-report-junk.png)

   - <span data-ttu-id="2f95c-117">Select one or more messages， right-click， and then select **Mark as junk**.</span><span class="sxs-lookup"><span data-stu-id="2f95c-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="2f95c-118">在出现的对话框中，单击"**报告"。**</span><span class="sxs-lookup"><span data-stu-id="2f95c-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="2f95c-119">如果您改变了主想，请单击 **"不报告"。**</span><span class="sxs-lookup"><span data-stu-id="2f95c-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="2f95c-120">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2f95c-120">Junk</span></span>|<span data-ttu-id="2f95c-121">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="2f95c-121">Phishing</span></span>|
   |:---:|:---:|
   |!["报告为垃圾邮件"对话框](../../media/owa-report-as-junk-dialog.png)|!["报告为网络钓鱼"对话框](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="2f95c-124">选定的消息会发送至 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="2f95c-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="2f95c-125">若要确认已提交的邮件，请打开您的“已发送邮件”\*\*\*\* 文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="2f95c-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="2f95c-126">从 Web 上的 Outlook 中的"垃圾邮件"文件夹报告非垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="2f95c-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="2f95c-127">在"垃圾邮件"文件夹中，请使用以下两种方法之一来报告垃圾邮件误报或网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="2f95c-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="2f95c-128">选择邮件，然后在**工具栏上单击**"非垃圾邮件"，然后选择 **"非垃圾邮件\*\*\*\*"或"网络钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="2f95c-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![从功能区报告垃圾或钓鱼电子邮件](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="2f95c-130">Select one or more messages， right-click， and then select **Mark as not junk**.</span><span class="sxs-lookup"><span data-stu-id="2f95c-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="2f95c-131">在出现的对话框中，阅读信息并单击"报告 **"。**</span><span class="sxs-lookup"><span data-stu-id="2f95c-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="2f95c-132">如果您改变了主想，请单击 **"不报告"。**</span><span class="sxs-lookup"><span data-stu-id="2f95c-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="2f95c-133">非垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2f95c-133">Not Junk</span></span>|<span data-ttu-id="2f95c-134">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="2f95c-134">Phishing</span></span>|
   |:---:|:---:|
   |![报告为非垃圾邮件对话框](../../media/owa-report-as-not-junk-dialog.png)|!["报告为网络钓鱼"对话框](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="2f95c-137">选定的消息会发送至 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="2f95c-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="2f95c-138">若要确认已提交的邮件，请打开您的“已发送邮件”\*\*\*\* 文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="2f95c-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="2f95c-139">在 Outlook 网页版中禁用或启用垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="2f95c-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="2f95c-140">默认情况下，用户可以向 Microsoft 报告垃圾邮件误报、假负和网页邮件，以供在 Web 上的 Outlook 中进行分析。</span><span class="sxs-lookup"><span data-stu-id="2f95c-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="2f95c-141">管理员可以在 Exchange Online PowerShell 中配置 Web 上的 Outlook 邮箱策略，以防止用户向 Microsoft 报告垃圾邮件误报和垃圾邮件误报。</span><span class="sxs-lookup"><span data-stu-id="2f95c-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="2f95c-142">无法禁止用户向 Microsoft 报告网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="2f95c-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2f95c-143">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2f95c-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2f95c-144">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2f95c-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2f95c-145">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="2f95c-145">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2f95c-146">具体来说，你**需要**Exchange Online 中的**收件人策略或邮件收件人**角色，这些角色默认情况下被分配**到"组织管理\*\*\*\*"和"收件人**管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="2f95c-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="2f95c-147">有关 Exchange Online 中角色组的详细信息，请参阅 Exchange [Online 中的修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="2f95c-147">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="2f95c-148">每个组织都有一个名为 OwaMailboxPolicy-Default 的默认策略，但您可以创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2f95c-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="2f95c-149">自定义策略适用于默认策略前的已确定范围的用户。</span><span class="sxs-lookup"><span data-stu-id="2f95c-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="2f95c-150">有关 Web 上的 Outlook 邮箱策略的详细信息，请参阅 [Exchange Online 中的 Outlook 网页版邮箱策略](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="2f95c-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="2f95c-151">禁用垃圾电子邮件报告不会删除 Web 上 Outlook 中的邮件被标记为垃圾邮件或非垃圾邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="2f95c-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="2f95c-152">选择"垃圾邮件"文件夹中的邮件并单击 **"非垃圾邮件"** \> **Not junk**仍然会将该邮件移回收件箱中。</span><span class="sxs-lookup"><span data-stu-id="2f95c-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="2f95c-153">选择任何其他电子邮件文件夹中的邮件并单击"垃圾邮件 **"** \> **Junk**仍会将该邮件移至垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="2f95c-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="2f95c-154">不再提供的选项向 Microsoft 报告邮件。</span><span class="sxs-lookup"><span data-stu-id="2f95c-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="2f95c-155">使用 Exchange Online PowerShell 在 Web 上的 Outlook 中禁用或启用垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="2f95c-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="2f95c-156">若要查找现有 Outlook 网页版邮箱策略和垃圾邮件报告状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2f95c-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="2f95c-157">若要禁用或启用 Web 上的 Outlook 中的垃圾邮件报告，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2f95c-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="2f95c-158">本示例禁用默认策略中的垃圾邮件报告。</span><span class="sxs-lookup"><span data-stu-id="2f95c-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="2f95c-159">本示例在名为 Contoso Managers 的自定义策略中启用垃圾邮件报告功能。</span><span class="sxs-lookup"><span data-stu-id="2f95c-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="2f95c-160">有关语法和参数的详细信息，请参阅[Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy)和[Set-OwaMailboxPolicy。](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="2f95c-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2f95c-161">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="2f95c-161">How do you know this worked?</span></span>

<span data-ttu-id="2f95c-162">若要验证是否已成功启用或禁用 Web 上的 Outlook 中的垃圾邮件报告，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="2f95c-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="2f95c-163">在 Exchange Online PowerShell 中，运行以下命令并验证 **ReportJunkEmailEnabled** 属性值：</span><span class="sxs-lookup"><span data-stu-id="2f95c-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="2f95c-164">在 Outlook 网页版中打开受影响用户的邮箱，在收件箱中选择一封邮件，单击**Junk** \> **"垃圾邮件"，** 然后验证是否显示向 Microsoft 报告该邮件的提示。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2f95c-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="2f95c-165">在 Web 上的 Outlook中打开受影响用户的邮箱，选择"垃圾邮件"文件夹中的邮件，单击 **"** \> **垃圾邮件"，** 然后确认"将该邮件报告给 Microsoft 的提示"已显示或未显示。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2f95c-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="2f95c-166"><sup>\*</sup> 用户可以隐藏该提示以在仍报告邮件时报告邮件。</span><span class="sxs-lookup"><span data-stu-id="2f95c-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="2f95c-167">若要在 Outlook 网页版中检查此设置，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2f95c-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="2f95c-168">单击 **"Web** ![ 上的设置"图标查看 ](../../media/owa-settings-icon.png) \> **所有 Outlook 设置** \> **垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="2f95c-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="2f95c-169">在" **报告** "部分中，验证值 **：发送报告前先询问我**。</span><span class="sxs-lookup"><span data-stu-id="2f95c-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Web 上的 Outlook 垃圾邮件报告设置](../../media/owa-junk-email-reporting-options.png)
