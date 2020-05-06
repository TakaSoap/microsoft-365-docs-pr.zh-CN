---
title: 报告电子邮件欺诈-web 上的 Outlook
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
description: 使用 Exchange Online 邮箱的 Microsoft 365 用户可以使用 web 上的 Outlook （Outlook Web App）将垃圾邮件、非垃圾邮件和网络钓鱼邮件提交给 Microsoft 进行分析。
ms.openlocfilehash: 32e60aa707bcaea9e35cc3bb8ded3aefb7fe46ab
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031486"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="abef4-103">在 Office 365 中的 Outlook 网页上报告垃圾邮件和网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="abef4-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="abef4-104">如果你是使用 Exchange Online 邮箱的 Microsoft 365 客户，则可以使用 web 上的 Outlook （以前称为 Outlook Web App）中的内置报告选项来提交误报（好的电子邮件被标记为垃圾邮件）、漏报（允许错误的电子邮件）和网络钓鱼邮件到 Exchange Online Protection （EOP）。</span><span class="sxs-lookup"><span data-stu-id="abef4-104">If you're a Microsoft 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="abef4-105">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="abef4-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="abef4-106">如果您是具有 Exchange Online 邮箱的组织中的管理员，我们建议您在安全 & 合规性中心中使用提交门户。</span><span class="sxs-lookup"><span data-stu-id="abef4-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="abef4-107">有关详细信息，请参阅[使用管理员提交将可疑的垃圾邮件、网络钓鱼、url 和文件提交给 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="abef4-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="abef4-108">管理员可以在 Outlook 网页版中禁用或启用用户将邮件报告给 Microsoft 的功能。</span><span class="sxs-lookup"><span data-stu-id="abef4-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="abef4-109">有关详细信息，请参阅本主题后面的在[Outlook 网页版中禁用或启用垃圾邮件报告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)一节。</span><span class="sxs-lookup"><span data-stu-id="abef4-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="abef4-110">您可以将报告的邮件配置为复制或重定向到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="abef4-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="abef4-111">有关详细信息，请参阅[在 Office 365 中指定用户提交垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="abef4-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Office 365](user-submission.md).</span></span>

- <span data-ttu-id="abef4-112">有关将邮件报告给 Microsoft 的详细信息，请参阅[在 Office 365 中向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="abef4-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="abef4-113">在 Outlook 网页网络中报告垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="abef4-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="abef4-114">对于收件箱中的邮件或除垃圾邮件以外的任何其他电子邮件文件夹中的邮件，请使用下列方法之一来报告垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="abef4-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="abef4-115">选择邮件，单击工具栏上的 "**垃圾**邮件"，然后选择 "**垃圾**邮件" 或 "**网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="abef4-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/owa-report-junk.png)

   - <span data-ttu-id="abef4-117">选择一个或多个邮件，单击鼠标右键，然后选择 "**标记为垃圾**邮件"。</span><span class="sxs-lookup"><span data-stu-id="abef4-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="abef4-118">在出现的对话框中，单击 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="abef4-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="abef4-119">如果你改变主意，请单击 "**不报告**"。</span><span class="sxs-lookup"><span data-stu-id="abef4-119">If you change your mind, click **Don't Report**.</span></span>

   !["报告为垃圾邮件" 对话框](../../media/owa-report-as-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="abef4-122">选定的邮件将发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="abef4-122">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="abef4-123">若要确认已提交的邮件，请打开您的“已发送邮件”\*\*\*\* 文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="abef4-123">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="abef4-124">从 web 上的 Outlook 中的 "垃圾邮件" 文件夹报告非垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="abef4-124">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="abef4-125">在 "垃圾邮件" 文件夹中，使用以下任一方法报告垃圾邮件误报或网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="abef4-125">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="abef4-126">选择邮件，单击工具栏上的 "**非垃圾**邮件"，然后选择 "**不垃圾**邮件" 或 "**网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="abef4-126">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="abef4-128">选择一个或多个邮件，单击鼠标右键，然后选择 "**标记为非垃圾**邮件"。</span><span class="sxs-lookup"><span data-stu-id="abef4-128">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="abef4-129">在出现的对话框中，阅读信息，然后单击 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="abef4-129">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="abef4-130">如果你改变主意，请单击 "**不报告**"。</span><span class="sxs-lookup"><span data-stu-id="abef4-130">If you change your mind, click **Don't Report**.</span></span>

   !["报告为非垃圾邮件" 对话框](../../media/owa-report-as-not-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="abef4-133">选定的邮件将发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="abef4-133">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="abef4-134">若要确认已提交的邮件，请打开您的“已发送邮件”\*\*\*\* 文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="abef4-134">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="abef4-135">在 web 上的 Outlook 中禁用或启用垃圾电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="abef4-135">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="abef4-136">默认情况下，用户可以在 web 上的 Outlook 中将垃圾邮件误报、漏报和网络钓鱼邮件报告给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="abef4-136">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="abef4-137">管理员可以在 Exchange Online PowerShell 中对 web 邮箱策略配置 Outlook，以防止用户向 Microsoft 报告垃圾邮件误报和垃圾邮件漏报。</span><span class="sxs-lookup"><span data-stu-id="abef4-137">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="abef4-138">您无法禁用用户将网络钓鱼邮件报告给 Microsoft 的功能。</span><span class="sxs-lookup"><span data-stu-id="abef4-138">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="abef4-139">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="abef4-139">What do you need to know before you begin?</span></span>

- <span data-ttu-id="abef4-140">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="abef4-140">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="abef4-141">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="abef4-141">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="abef4-142">特别是，您需要 Exchange Online 中的**收件人策略**或**邮件收件人**角色，默认情况下，这些角色分配给**组织管理**角色组和**收件人管理**角色组。</span><span class="sxs-lookup"><span data-stu-id="abef4-142">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="abef4-143">有关 Exchange Online 中的角色组的详细信息，请参阅[Modify role groups In Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="abef4-143">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="abef4-144">每个组织都有一个名为 "Set-owamailboxpolicy" 的默认策略-默认值，但您可以创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="abef4-144">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="abef4-145">在默认策略之前，自定义策略将应用于作用域内的用户。</span><span class="sxs-lookup"><span data-stu-id="abef4-145">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="abef4-146">有关 Outlook 网页版邮箱策略的详细信息，请参阅[Exchange Online 中的 "outlook on web 邮箱策略"](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="abef4-146">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="abef4-147">禁用垃圾邮件报告不会删除在 web 上的 Outlook 中将邮件标记为垃圾邮件或非垃圾邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="abef4-147">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="abef4-148">在 "垃圾邮件" 文件夹中选择一封邮件，并单击 "**非垃圾** \>邮件" 并不是**垃圾**邮件仍将邮件移回收件箱。</span><span class="sxs-lookup"><span data-stu-id="abef4-148">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="abef4-149">选择任何其他电子邮件文件夹中的邮件并单击 "**垃圾** \> **邮件" 仍会**将邮件移至 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="abef4-149">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="abef4-150">不再可用的选项是将邮件报告给 Microsoft 的选项。</span><span class="sxs-lookup"><span data-stu-id="abef4-150">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="abef4-151">使用 Exchange Online PowerShell 在 web 上的 Outlook 中禁用或启用垃圾电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="abef4-151">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="abef4-152">若要在 web 邮箱策略和 "垃圾邮件报告" 状态中查找您的现有 Outlook，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="abef4-152">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="abef4-153">若要在 web 上的 Outlook 中禁用或启用垃圾邮件报告，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="abef4-153">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="abef4-154">本示例禁用默认策略中的垃圾邮件报告。</span><span class="sxs-lookup"><span data-stu-id="abef4-154">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="abef4-155">本示例在名为 Contoso 管理员的自定义策略中启用垃圾邮件报告。</span><span class="sxs-lookup"><span data-stu-id="abef4-155">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="abef4-156">有关语法和参数的详细信息，请参阅[set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)和[set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="abef4-156">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="abef4-157">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="abef4-157">How do you know this worked?</span></span>

<span data-ttu-id="abef4-158">若要验证您是否已成功启用或禁用 web 上的 Outlook 中的垃圾邮件报告功能，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="abef4-158">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="abef4-159">在 Exchange Online PowerShell 中，运行以下命令并验证**ReportJunkEmailEnabled**属性值：</span><span class="sxs-lookup"><span data-stu-id="abef4-159">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="abef4-160">在 Outlook 网页上打开受影响用户的邮箱，在 "收件箱" 中选择一封邮件，单击 "**垃圾** \> **邮件"，并验证**提示将邮件报告给 Microsoft 是不显示。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abef4-160">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="abef4-161">在 Outlook 网页上打开一个受影响的用户的邮箱，在 "垃圾邮件" 文件夹中选择一封邮件，单击 "**垃圾** \> **邮件"，并验证**提示将该邮件报告给 Microsoft 是不显示。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abef4-161">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="abef4-162"><sup>\*</sup>用户可以在仍报告邮件的同时隐藏报告邮件的提示。</span><span class="sxs-lookup"><span data-stu-id="abef4-162"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="abef4-163">若要在 Outlook 网页网络中检查此设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="abef4-163">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="abef4-164">单击 **"设置** ![outlook on the web 设置](../../media/owa-settings-icon.png) \> " 图标**查看所有 Outlook 设置** \> **垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="abef4-164">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="abef4-165">在 "**报告**" 部分，验证值： "**发送报告前询问我**"。</span><span class="sxs-lookup"><span data-stu-id="abef4-165">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook 网页上的 Outlook 垃圾邮件报告设置](../../media/owa-junk-email-reporting-options.png)
