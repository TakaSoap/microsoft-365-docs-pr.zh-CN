---
title: 安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: 了解如何安装和使用 Microsoft 垃圾电子邮件报告加载项将垃圾邮件、非垃圾邮件和网络钓鱼邮件报告给 Microsoft。
ms.openlocfilehash: e39fb2f4ecba806c2d26d989fbbe6ddec137adc1
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033878"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook-in-office-365"></a><span data-ttu-id="193cf-103">在 Office 365 中安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="193cf-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="193cf-104">如果您当前未使用垃圾电子邮件报告加载项，则建议您改为[报告邮件加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="193cf-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span>

<span data-ttu-id="193cf-105">Microsoft Outlook 的垃圾电子邮件报告外接程序允许用户提交误报（好的电子邮件标记为垃圾邮件）、漏报（允许的电子邮件错误）和网络钓鱼邮件到 Exchange Online Protection （EOP）。</span><span class="sxs-lookup"><span data-stu-id="193cf-105">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span> <span data-ttu-id="193cf-106">如果您的组织不使用 EOP，则您的垃圾邮件报告提交不会影响垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="193cf-106">If your organization doesn't use EOP, your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="193cf-107">本主题说明如何安装和使用垃圾邮件报告加载项。</span><span class="sxs-lookup"><span data-stu-id="193cf-107">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="193cf-108">开始前，需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="193cf-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="193cf-109">若要安装垃圾电子邮件报告加载项，请参阅本主题后面的[安装垃圾电子邮件报告外](#install-the-junk-email-reporting-add-in)接部分。</span><span class="sxs-lookup"><span data-stu-id="193cf-109">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="193cf-110">垃圾电子邮件报告加载项适用于以下版本的 Outlook：</span><span class="sxs-lookup"><span data-stu-id="193cf-110">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="193cf-111">Outlook 2013 或更高版本</span><span class="sxs-lookup"><span data-stu-id="193cf-111">Outlook 2013 or later</span></span>
  - <span data-ttu-id="193cf-112">Outlook 包含在 Office 365 专业增强版中</span><span class="sxs-lookup"><span data-stu-id="193cf-112">Outlook included with Office 365 ProPlus</span></span>

- <span data-ttu-id="193cf-113">有关将邮件报告给 Microsoft 的详细信息，请参阅[在 Office 365 中向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="193cf-113">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="193cf-114">使用垃圾电子邮件报告加载项报告垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="193cf-114">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="193cf-115">对于收件箱中的邮件或除垃圾邮件以外的任何其他电子邮件文件夹中的邮件，请使用以下任何一种方法来报告垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="193cf-115">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="193cf-116">选择邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="193cf-116">Select the message or open the message.</span></span> <span data-ttu-id="193cf-117">在功能区的 "**主页**" 或 "**邮件**" 选项卡中，单击 "**垃圾邮件**"，然后选择 "**报告为垃圾邮件**或**报告为网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-117">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="193cf-119">右键单击该邮件，选择 "**垃圾**邮件"，然后选择 "**报告为垃圾**邮件" 或 "**报告为网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-119">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![通过右键单击报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="193cf-121">选择多个邮件，单击鼠标右键，然后选择 "**报告为垃圾**邮件" 或 "**报告为网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-121">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![通过右键单击报告多个垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="193cf-123">在出现的对话框中，阅读信息，然后单击 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-123">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="193cf-124">如果你改变主意，请单击 "**不报告**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-124">If you change your mind, click **Don't Report**.</span></span>

   !["报告为垃圾邮件" 对话框](../../media/junk-email-reporting-report-as-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="193cf-p104">选定的邮件会被发送至 Microsoft 以供分析，并移动至垃圾邮件文件夹。若要确认已提交的邮件，请打开您的“已发送邮件”\*\*\*\* 文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="193cf-p104">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="193cf-129">使用垃圾电子邮件报告加载项报告垃圾邮件文件夹中的非垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="193cf-129">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="193cf-130">在 "垃圾邮件" 文件夹中，使用以下任何一种方法报告垃圾邮件误报或网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="193cf-130">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="193cf-131">选择邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="193cf-131">Select the message or open the message.</span></span> <span data-ttu-id="193cf-132">在功能区的 "**主页**" 或 "**邮件**" 选项卡中，单击 "**非垃圾邮件**"，然后选择 "**报告为非垃圾邮件**" 或 "**报告为仿冒**"</span><span class="sxs-lookup"><span data-stu-id="193cf-132">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![从 "垃圾邮件" 文件夹的功能区报告非垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="193cf-134">右键单击该邮件，单击 "**垃圾**邮件"，然后选择 "**报告为非垃圾邮件**" 或 "**报告为网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-134">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![不通过在 "垃圾邮件" 文件夹中单击鼠标右键来报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="193cf-136">选择多个邮件，单击鼠标右键，然后选择 "**报告为非垃圾邮件**" 或 "**报告为网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-136">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![在 "垃圾邮件" 文件夹中单击鼠标右键，不报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="193cf-138">在出现的对话框中，阅读信息，然后单击 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-138">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="193cf-139">如果你改变主意，请单击 "**不报告**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-139">If you change your mind, click **Don't Report**.</span></span>

   !["报告为非垃圾邮件" 对话框](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   !["报告为仿冒" 对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="193cf-p107">选定的邮件会被发送至 Microsoft 以供分析，并移动至垃圾邮件文件夹。若要确认已提交的邮件，请打开您的“已发送邮件”\*\*\*\* 文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="193cf-p107">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="193cf-144">安装垃圾电子邮件报告外接</span><span class="sxs-lookup"><span data-stu-id="193cf-144">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="193cf-145">您需要在要安装加载项的计算机上拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="193cf-145">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="193cf-146">转到<https://www.microsoft.com/download/details.aspx?id=18275>并将适用于你的 Office 版本的 .msi 文件下载到易于查找的位置：</span><span class="sxs-lookup"><span data-stu-id="193cf-146">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="193cf-147">**32 位**：`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="193cf-147">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="193cf-148">**64 位**：`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="193cf-148">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="193cf-149">对于 Outlook 2013 或更高版本，唯一的先决条件是 Microsoft .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="193cf-149">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="193cf-150">在 Windows 10 中，不会从下载安装 .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="193cf-150">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="193cf-151">使用安装向导安装垃圾电子邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="193cf-151">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="193cf-152">在您的计算机上关闭 Outlook。</span><span class="sxs-lookup"><span data-stu-id="193cf-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="193cf-153">在 Windows 10 中，验证是否已启用 .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="193cf-153">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="193cf-154">有关说明，请参阅[在 "控制面板" 中启用 .Net Framework 3.5](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)。</span><span class="sxs-lookup"><span data-stu-id="193cf-154">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="193cf-155">找到已下载的 .msi 文件，然后双击该文件。</span><span class="sxs-lookup"><span data-stu-id="193cf-155">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="193cf-156">在“欢迎使用 Microsoft 垃圾电子邮件报告外接程序安装程序”\*\*\*\* 页面上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="193cf-156">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="193cf-157">查看许可协议，如果同意条款，请单击 "**我接受许可协议中的条款**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-157">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="193cf-158">向导完成后，单击“完成”\*\*\*\*。 </span><span class="sxs-lookup"><span data-stu-id="193cf-158">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="193cf-159">启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="193cf-159">Start Outlook.</span></span>

<span data-ttu-id="193cf-160">查找 Outlook 功能区上的 "**垃圾邮件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="193cf-160">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="193cf-161">现在，可以通过在收件箱中选择垃圾电子邮件并单击“报告垃圾邮件”\*\*\*\* 按钮，向 Microsoft 报告垃圾电子邮件。</span><span class="sxs-lookup"><span data-stu-id="193cf-161">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="193cf-p111">如果想要向 Microsoft 报告仿冒垃圾电子邮件，请选择\*\*\*\*“垃圾邮件”旁边的向下箭头查看更多选项，如\*\*\*\*“报告为仿冒邮件”。如果一封电子邮件被错误识别为垃圾邮件，则在垃圾邮件文件夹中，您还可以选择“报告不是垃圾邮件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="193cf-p111">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="193cf-164">使用静默模式安装垃圾电子邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="193cf-164">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="193cf-165">在您的计算机上关闭 Outlook。</span><span class="sxs-lookup"><span data-stu-id="193cf-165">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="193cf-166">在 Windows 10 中，通过运行以下命令来安装 .NET Framework 2.0：</span><span class="sxs-lookup"><span data-stu-id="193cf-166">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="193cf-167">若要在不进行任何用户交互的情况下安装加载项，请打开命令提示符，并使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="193cf-167">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="193cf-168">`MaxMessageSelection`指定可为单个提交选择的最大邮件数。</span><span class="sxs-lookup"><span data-stu-id="193cf-168">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="193cf-169">有效值为1到50。</span><span class="sxs-lookup"><span data-stu-id="193cf-169">Valid values are from 1 to 50.</span></span> <span data-ttu-id="193cf-170">默认值为 15。</span><span class="sxs-lookup"><span data-stu-id="193cf-170">The default value is 15.</span></span>

   - <span data-ttu-id="193cf-171">`BccEmailAddress`指定将接收所有用户提交副本的其他密件抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="193cf-171">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="193cf-172">默认值为空（没有其他密件抄送收件人）。</span><span class="sxs-lookup"><span data-stu-id="193cf-172">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="193cf-173">本示例使用默认设置从指定路径安装64位版本的加载项。</span><span class="sxs-lookup"><span data-stu-id="193cf-173">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="193cf-174">此示例使用以下其他设置从指定路径安装32位版本的外接：</span><span class="sxs-lookup"><span data-stu-id="193cf-174">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="193cf-175">单个提交中最长可选择20封邮件。</span><span class="sxs-lookup"><span data-stu-id="193cf-175">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="193cf-176">junkreports@contoso.com 和 hollyd@treyresearch.net 接收所有提交的密件抄送副本。</span><span class="sxs-lookup"><span data-stu-id="193cf-176">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="193cf-177">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="193cf-177">How do you know this worked?</span></span>

<span data-ttu-id="193cf-178">若要验证是否已成功安装垃圾电子邮件报告外接程序，请在 Outlook 中执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="193cf-178">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="193cf-179">选择邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="193cf-179">Select the message or open the message.</span></span> <span data-ttu-id="193cf-180">在功能区的 "**主页**" 或 "**邮件**" 选项卡中，单击 "**垃圾邮件**"，并验证以下选项是否可用：</span><span class="sxs-lookup"><span data-stu-id="193cf-180">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="193cf-181">**报告为垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="193cf-181">**Report as Junk**</span></span>
  - <span data-ttu-id="193cf-182">**报告为网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="193cf-182">**Report as Phishing**</span></span>
  - <span data-ttu-id="193cf-183">**垃圾报告选项**</span><span class="sxs-lookup"><span data-stu-id="193cf-183">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="193cf-184">**报告垃圾联机帮助**</span><span class="sxs-lookup"><span data-stu-id="193cf-184">**Report Junk Online Help**</span></span>

  ![从功能区报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="193cf-186">右键单击该邮件，选择 "**垃圾**邮件"，并验证以下选项是否可用：</span><span class="sxs-lookup"><span data-stu-id="193cf-186">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="193cf-187">**报告为垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="193cf-187">**Report as Junk**</span></span>
  - <span data-ttu-id="193cf-188">**报告为网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="193cf-188">**Report as Phishing**</span></span>
  - <span data-ttu-id="193cf-189">**垃圾报告选项**</span><span class="sxs-lookup"><span data-stu-id="193cf-189">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="193cf-190">**报告垃圾联机帮助**</span><span class="sxs-lookup"><span data-stu-id="193cf-190">**Report Junk Online Help**</span></span>

  ![通过右键单击报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="193cf-192">选择多个邮件，右键单击，并验证以下选项是否可用：</span><span class="sxs-lookup"><span data-stu-id="193cf-192">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="193cf-193">**报告为垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="193cf-193">**Report as Junk**</span></span>
  - <span data-ttu-id="193cf-194">**报告为网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="193cf-194">**Report as Phishing**</span></span>

  ![通过右键单击报告多个垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="193cf-196">在 "**垃圾邮件**" 文件夹中执行以前的操作，并验证以前的**垃圾**报告选项目前**不是垃圾**邮件。</span><span class="sxs-lookup"><span data-stu-id="193cf-196">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![从 "垃圾邮件" 文件夹的功能区报告非垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![不通过在 "垃圾邮件" 文件夹中单击鼠标右键来报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![在 "垃圾邮件" 文件夹中单击鼠标右键，不报告垃圾邮件或仿冒电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="193cf-200">卸载垃圾电子邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="193cf-200">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="193cf-201">关闭 Outlook 后，请使用以下任一过程卸载垃圾电子邮件报告外接程序：</span><span class="sxs-lookup"><span data-stu-id="193cf-201">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="193cf-202">**"控制面板"**：按 Windows 键 + R。在打开的 "**运行**" 对话框中`control appwiz.cpl` ，输入，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="193cf-202">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="193cf-203">在列表中查找并选择**Microsoft 垃圾电子邮件报告加载项**，然后单击 "**卸载**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-203">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="193cf-204">**Windows Installer 程序包**：查找或下载相应的 .msi 文件，然后双击该文件。</span><span class="sxs-lookup"><span data-stu-id="193cf-204">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="193cf-205">**32 位**：`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="193cf-205">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="193cf-206">**64 位**：`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="193cf-206">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="193cf-207">在出现的对话框中，选择 "**删除适用于 Outlook 的 Microsoft 垃圾电子邮件报告外接程序**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="193cf-207">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="193cf-208">**静默模式**：查找或下载相应的 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="193cf-208">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="193cf-209">在命令提示符窗口中，将\<PathToFile\>替换为 .msi 文件的位置，然后运行下列命令之一：</span><span class="sxs-lookup"><span data-stu-id="193cf-209">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="193cf-210">**32 位**：</span><span class="sxs-lookup"><span data-stu-id="193cf-210">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="193cf-211">**64 位**：</span><span class="sxs-lookup"><span data-stu-id="193cf-211">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="193cf-212">当您在卸载后打开 Outlook 时，垃圾邮件、非垃圾邮件和网络钓鱼报告选项应消失。</span><span class="sxs-lookup"><span data-stu-id="193cf-212">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="193cf-213">对垃圾电子邮件报告外接加载项进行故障排除</span><span class="sxs-lookup"><span data-stu-id="193cf-213">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="193cf-214">有时，在添加垃圾电子邮件报告加载项后，Outlook 可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="193cf-214">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="193cf-215">本节介绍您可能遇到的问题，以及解决这些问题的提示。</span><span class="sxs-lookup"><span data-stu-id="193cf-215">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="193cf-216">用户疑难解答</span><span class="sxs-lookup"><span data-stu-id="193cf-216">Troubleshooting for users</span></span>

<span data-ttu-id="193cf-217">您将遇到以下一个或多个问题：</span><span class="sxs-lookup"><span data-stu-id="193cf-217">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="193cf-218">Nothing happens when you click **Report Junk**</span><span class="sxs-lookup"><span data-stu-id="193cf-218">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="193cf-219">当您选择一封电子邮件之后，Outlook 停止响应</span><span class="sxs-lookup"><span data-stu-id="193cf-219">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="193cf-220">由于收到"未送达"回复，报告的垃圾邮件无法传递</span><span class="sxs-lookup"><span data-stu-id="193cf-220">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="193cf-221">若要解决此问题，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="193cf-221">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="193cf-222">关闭并重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="193cf-222">Close and restart Outlook.</span></span>
2. <span data-ttu-id="193cf-223">创建并发送一封测试邮件，并验证收件人是否收到该邮件。</span><span class="sxs-lookup"><span data-stu-id="193cf-223">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="193cf-224">如果问题仍然存在，请与管理员联系。</span><span class="sxs-lookup"><span data-stu-id="193cf-224">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="193cf-225">有关可用于将邮件提交到 Microsoft 的其他方法，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="193cf-225">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="193cf-226">管理员的故障排除</span><span class="sxs-lookup"><span data-stu-id="193cf-226">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="193cf-227">问题：不断出现一条错误消息，询问用户是否联系其系统管理员</span><span class="sxs-lookup"><span data-stu-id="193cf-227">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="193cf-228">验证或将`LoggingLevel`注册表项设置为值 "Verbose"：</span><span class="sxs-lookup"><span data-stu-id="193cf-228">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="193cf-229">**32 位 Windows 上的32位 Outlook**：</span><span class="sxs-lookup"><span data-stu-id="193cf-229">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="193cf-230">**64 位 Windows 上的32位 Outlook**：</span><span class="sxs-lookup"><span data-stu-id="193cf-230">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="193cf-231">**64 位 Outlook**：</span><span class="sxs-lookup"><span data-stu-id="193cf-231">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="193cf-232">重新启动 Outlook 并要求用户在看到错误消息时报告回来。</span><span class="sxs-lookup"><span data-stu-id="193cf-232">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="193cf-233">收集在以下位置找到的日志信息：</span><span class="sxs-lookup"><span data-stu-id="193cf-233">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="193cf-234">联系 Exchange Online Protection 技术支持并向他们提供日志信息。</span><span class="sxs-lookup"><span data-stu-id="193cf-234">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="193cf-235">问题：用户选择在报告邮件时不会收到确认提示，现在他们希望返回提示</span><span class="sxs-lookup"><span data-stu-id="193cf-235">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="193cf-236">创建`ConfirmReportJunk`注册表项 wih 值 "True"：</span><span class="sxs-lookup"><span data-stu-id="193cf-236">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="193cf-237">重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="193cf-237">Restart Outlook.</span></span>
