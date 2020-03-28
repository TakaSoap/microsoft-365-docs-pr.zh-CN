---
title: '在 Outlook 网页版中报告垃圾电子邮件和钓鱼行为 '
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
description: Office 365 具有 Exchange Online 邮箱的用户可以使用 web 上的 Outlook （Outlook Web App）将垃圾邮件、非垃圾邮件和网络钓鱼邮件提交给 Microsoft 进行分析。
ms.openlocfilehash: c6aba9a701b23be4bbbe508825a55c6438461928
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033675"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="b15eb-103">在 Office 365 中的 Outlook 网页上报告垃圾邮件和网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="b15eb-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="b15eb-104">如果你是使用 Exchange Online 邮箱的 Office 365 客户，则可以使用 web 上的 Outlook （以前称为 Outlook Web App）中的内置报告选项来提交误报（好的电子邮件被标记为垃圾邮件）、漏报（允许使用错误的电子邮件）和到 Exchange Online Protection （EOP）的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="b15eb-104">If you're an Office 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b15eb-105">开始前，需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="b15eb-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b15eb-106">如果您是使用 Exchange Online 邮箱的 Office 365 组织中的管理员，我们建议您在 Office 365 安全性 & 合规性中心中使用提交门户。</span><span class="sxs-lookup"><span data-stu-id="b15eb-106">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="b15eb-107">有关详细信息，请参阅[使用管理员提交将可疑的垃圾邮件、网络钓鱼、url 和文件提交给 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="b15eb-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="b15eb-108">管理员可以在 Outlook 网页版中禁用或启用用户将邮件报告给 Microsoft 的功能。</span><span class="sxs-lookup"><span data-stu-id="b15eb-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="b15eb-109">有关详细信息，请参阅本主题后面的在[Outlook 网页版中禁用或启用垃圾邮件报告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)一节。</span><span class="sxs-lookup"><span data-stu-id="b15eb-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="b15eb-110">有关将邮件报告给 Microsoft 的详细信息，请参阅[在 Office 365 中向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="b15eb-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="b15eb-111">在 Outlook 网页网络中报告垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="b15eb-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="b15eb-112">对于收件箱中的邮件或除垃圾邮件以外的任何其他电子邮件文件夹中的邮件，请使用下列方法之一来报告垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="b15eb-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="b15eb-113">选择邮件，单击工具栏上的 "**垃圾**邮件"，然后选择 "**垃圾**邮件" 或 "**网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="b15eb-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/owa-report-junk.png)

   - <span data-ttu-id="b15eb-115">选择一个或多个邮件，单击鼠标右键，然后选择 "**标记为垃圾**邮件"。</span><span class="sxs-lookup"><span data-stu-id="b15eb-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="b15eb-116">在出现的对话框中，单击 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="b15eb-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="b15eb-117">如果你改变主意，请单击 "**不报告**"。</span><span class="sxs-lookup"><span data-stu-id="b15eb-117">If you change your mind, click **Don't Report**.</span></span>

   !["报告为垃圾邮件" 对话框](../../media/owa-report-as-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="b15eb-120">选定的邮件将发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="b15eb-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="b15eb-121">若要确认已提交的邮件，请打开您的“已发送邮件”\*\*\*\* 文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="b15eb-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="b15eb-122">从 web 上的 Outlook 中的 "垃圾邮件" 文件夹报告非垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="b15eb-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="b15eb-123">在 "垃圾邮件" 文件夹中，使用以下任一方法报告垃圾邮件误报或网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="b15eb-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="b15eb-124">选择邮件，单击工具栏上的 "**非垃圾**邮件"，然后选择 "**不垃圾**邮件" 或 "**网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="b15eb-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="b15eb-126">选择一个或多个邮件，单击鼠标右键，然后选择 "**标记为非垃圾**邮件"。</span><span class="sxs-lookup"><span data-stu-id="b15eb-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="b15eb-127">在出现的对话框中，阅读信息，然后单击 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="b15eb-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="b15eb-128">如果你改变主意，请单击 "**不报告**"。</span><span class="sxs-lookup"><span data-stu-id="b15eb-128">If you change your mind, click **Don't Report**.</span></span>

   !["报告为非垃圾邮件" 对话框](../../media/owa-report-as-not-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="b15eb-131">选定的邮件将发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="b15eb-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="b15eb-132">若要确认已提交的邮件，请打开您的“已发送邮件”\*\*\*\* 文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="b15eb-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="b15eb-133">在 web 上的 Outlook 中禁用或启用垃圾电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="b15eb-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="b15eb-134">默认情况下，用户可以在 web 上的 Outlook 中将垃圾邮件误报、漏报和网络钓鱼邮件报告给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="b15eb-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="b15eb-135">管理员可以使用 Exchange Online 中的 web 邮箱策略上的 Outlook 来禁用或启用此功能，但只能在 Exchange Online PowerShell 中使用。</span><span class="sxs-lookup"><span data-stu-id="b15eb-135">Admins can use Outlook on the web mailbox policies in Exchange Online to disable or enable this ability, but only in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="b15eb-136">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b15eb-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b15eb-137">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="b15eb-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="b15eb-138">特别是，您需要 Exchange Online 中的**收件人策略**或**邮件收件人**角色，默认情况下，这些角色分配给**组织管理**角色组和**收件人管理**角色组。</span><span class="sxs-lookup"><span data-stu-id="b15eb-138">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="b15eb-139">有关 Exchange Online 中的角色组的详细信息，请参阅[Modify role groups In Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="b15eb-139">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="b15eb-140">每个组织都有一个名为 "Set-owamailboxpolicy" 的默认策略-默认值，但您可以创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b15eb-140">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="b15eb-141">在默认策略之前，自定义策略将应用于作用域内的用户。</span><span class="sxs-lookup"><span data-stu-id="b15eb-141">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="b15eb-142">有关 Outlook 网页版邮箱策略的详细信息，请参阅[Exchange Online 中的 "outlook on web 邮箱策略"](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="b15eb-142">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

1. <span data-ttu-id="b15eb-143">若要在 web 邮箱策略和 "垃圾邮件报告" 状态中查找您的现有 Outlook，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b15eb-143">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="b15eb-144">若要在 web 上的 Outlook 中禁用或启用垃圾邮件报告，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="b15eb-144">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="b15eb-145">本示例禁用默认策略中的垃圾邮件报告。</span><span class="sxs-lookup"><span data-stu-id="b15eb-145">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="b15eb-146">本示例在名为 Contoso 经理的自定义策略中启用了垃圾邮件报告。</span><span class="sxs-lookup"><span data-stu-id="b15eb-146">This example enabled junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="b15eb-147">有关语法和参数的详细信息，请参阅[set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)和[set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b15eb-147">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b15eb-148">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="b15eb-148">How do you know this worked?</span></span>

<span data-ttu-id="b15eb-149">若要验证您是否已成功启用或禁用 web 上的 Outlook 中的垃圾邮件报告功能，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="b15eb-149">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="b15eb-150">在 Exchange Online PowerShell 中，运行以下命令并验证**ReportJunkEmailEnabled**属性值：</span><span class="sxs-lookup"><span data-stu-id="b15eb-150">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="b15eb-151">在 Outlook 网页版中打开受影响用户的邮箱，并验证用于报告垃圾邮件、非垃圾邮件和网络钓鱼邮件的选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="b15eb-151">Open an affected user's mailbox in Outlook on the web, and verify the options to report junk, not junk, and phishing messages are available or not available.</span></span> <span data-ttu-id="b15eb-152">请注意，用户仍可以将邮件标记为垃圾邮件、网络钓鱼邮件和非垃圾邮件，但用户无法将其报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="b15eb-152">Note that the user can still mark messages as junk, phishing, and not junk, but the user can't report them to Microsoft.</span></span>
