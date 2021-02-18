---
title: 安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: 了解如何安装和使用 Microsoft 垃圾邮件报告外接程序向 Microsoft 报告垃圾邮件、非垃圾邮件和网络钓鱼邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22a1364e8d7a1447bbcf518cc339a681c57a8af
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286617"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="bba99-103">安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="bba99-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bba99-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="bba99-104">**Applies to**</span></span>
- [<span data-ttu-id="bba99-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bba99-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bba99-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="bba99-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="bba99-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bba99-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> <span data-ttu-id="bba99-108">如果您当前没有使用垃圾邮件报告外接程序，我们建议改为使用"报告邮件"加载项或"报告钓鱼[](enable-the-report-message-add-in.md)["](enable-the-report-phish-add-in.md)外接程序。</span><span class="sxs-lookup"><span data-stu-id="bba99-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="bba99-109">有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="bba99-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="bba99-110">Microsoft Outlook 的垃圾邮件报告外接程序允许用户向 Microsoft 提交误报 (标记为垃圾邮件) 、漏报 (错误电子邮件) 和网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="bba99-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="bba99-111">如果您的组织不使用 Exchange Online Protection (例如，本地 Exchange 或 Exchange Online) 外的电子邮件服务，则垃圾邮件报告提交不会影响垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="bba99-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="bba99-112">本主题介绍如何安装和使用垃圾邮件报告外接程序。</span><span class="sxs-lookup"><span data-stu-id="bba99-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bba99-113">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="bba99-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bba99-114">若要安装垃圾邮件报告外接程序，请参阅本文稍后的"安装[](#install-the-junk-email-reporting-add-in)垃圾邮件报告外接程序"部分。</span><span class="sxs-lookup"><span data-stu-id="bba99-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="bba99-115">垃圾邮件报告外接程序适用于以下版本的 Outlook：</span><span class="sxs-lookup"><span data-stu-id="bba99-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="bba99-116">Outlook 2013 或更高版本</span><span class="sxs-lookup"><span data-stu-id="bba99-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="bba99-117">Microsoft 365 企业应用版中包含的 Outlook</span><span class="sxs-lookup"><span data-stu-id="bba99-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="bba99-118">有关向 Microsoft 报告邮件详细信息，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="bba99-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="bba99-119">使用垃圾邮件报告外接程序报告垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="bba99-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="bba99-120">对于收件箱或其他任何电子邮件文件夹中的邮件（垃圾邮件除外），请使用以下任一方法来报告垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="bba99-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="bba99-121">选择邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="bba99-121">Select the message or open the message.</span></span> <span data-ttu-id="bba99-122">在功能 **区的**"**主页**"或"邮件"选项卡中，单击"垃圾邮件"，然后选择"报告 **为** 垃圾邮件"或"报告 **为网络钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![从功能区报告垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="bba99-124">右键单击邮件 **，选择"** 垃圾邮件"，然后选择"报告 **为垃圾邮件**"或"报告 **为网络钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右键单击报告垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="bba99-126">选择多条消息，右键单击，然后选择"**报告为垃圾邮件**"或"**报告为网络钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右键单击报告多个垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="bba99-128">在出现的对话框中，读取信息并单击"报告 **"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="bba99-129">如果改变主意，请单击"**不报告"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-129">If you change your mind, click **Don't Report**.</span></span>

   ![报告为垃圾邮件对话框](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![报告为网络钓鱼对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="bba99-132">选定的邮件将发送给 Microsoft 进行分析，并：</span><span class="sxs-lookup"><span data-stu-id="bba99-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="bba99-133">如果"垃圾邮件"文件夹被报告为垃圾邮件，则移动到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="bba99-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="bba99-134">如果报告为网络钓鱼，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="bba99-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="bba99-135">若要确认已提交的邮件，请打开您的“已发送邮件”文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="bba99-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="bba99-136">使用垃圾邮件报告外接程序从"垃圾邮件"文件夹报告非垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="bba99-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="bba99-137">在"垃圾邮件"文件夹中，使用以下任一方法报告垃圾邮件误报或网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="bba99-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="bba99-138">选择邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="bba99-138">Select the message or open the message.</span></span> <span data-ttu-id="bba99-139">在功能 **区的**"**主页**"或"邮件"选项卡中，单击"非垃圾邮件"，然后选择"报告 **为非** 垃圾邮件"或"报告 **为网络钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![从"垃圾邮件"文件夹中的功能区报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="bba99-141">右键单击邮件 **，单击"** 垃圾邮件"，然后选择"**报告为非垃圾邮件**"或"报告 **为网络钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![在"垃圾邮件"文件夹中右键单击报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="bba99-143">选择多条消息，右键单击，然后选择"**报告为非垃圾邮件**"或"**报告为网络钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![在"垃圾邮件"文件夹中右键单击报告多个非垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="bba99-145">在出现的对话框中，读取信息并单击"报告 **"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="bba99-146">如果改变主意，请单击"**不报告"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-146">If you change your mind, click **Don't Report**.</span></span>

   ![报告为非垃圾邮件对话框](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![报告为网络钓鱼对话框](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="bba99-149">选定的邮件将发送给 Microsoft 进行分析，并：</span><span class="sxs-lookup"><span data-stu-id="bba99-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="bba99-150">如果"垃圾邮件"文件夹被报告为垃圾邮件，则移动到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="bba99-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="bba99-151">如果报告为网络钓鱼，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="bba99-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="bba99-152">若要确认已提交的邮件，请打开您的“已发送邮件”文件夹查看已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="bba99-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="bba99-153">安装垃圾邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="bba99-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="bba99-154">您需要在安装加载项的计算机上拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="bba99-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="bba99-155">转到 Office 版本相应的 .msi 文件，并下载到易于查找 <https://www.microsoft.com/download/details.aspx?id=18275> 的位置：</span><span class="sxs-lookup"><span data-stu-id="bba99-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="bba99-156">**32 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="bba99-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="bba99-157">**64 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="bba99-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="bba99-158">对于 Outlook 2013 或更高版本，唯一的先决条件是 Microsoft .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="bba99-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="bba99-159">在 Windows 10 中，你无法通过下载安装 .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="bba99-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="bba99-160">使用安装向导安装垃圾邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="bba99-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="bba99-161">在您的计算机上关闭 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bba99-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="bba99-162">在 Windows 10 中，验证 .NET Framework 2.0 是否已启用。</span><span class="sxs-lookup"><span data-stu-id="bba99-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="bba99-163">有关说明，请参阅["控制面板"中的"启用 .NET Framework 3.5"。](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="bba99-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="bba99-164">找到你下载的 .msi 文件，然后双击它。</span><span class="sxs-lookup"><span data-stu-id="bba99-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="bba99-165">在“欢迎使用 Microsoft 垃圾电子邮件报告外接程序安装程序”页面上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="bba99-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="bba99-166">查看许可协议 **，如果同意** 这些条款，请单击"我接受许可协议中的条款"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="bba99-167">向导完成后，单击“完成”。 </span><span class="sxs-lookup"><span data-stu-id="bba99-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="bba99-168">启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bba99-168">Start Outlook.</span></span>

<span data-ttu-id="bba99-169">在 Outlook **功能区** 上查找"垃圾邮件"按钮。</span><span class="sxs-lookup"><span data-stu-id="bba99-169">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="bba99-170">现在，可以通过在收件箱中选择垃圾电子邮件并单击“报告垃圾邮件”按钮，向 Microsoft 报告垃圾电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bba99-170">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="bba99-p110">如果想要向 Microsoft 报告仿冒垃圾电子邮件，请选择“垃圾邮件”旁边的向下箭头查看更多选项，如“报告为仿冒邮件”。如果一封电子邮件被错误识别为垃圾邮件，则在垃圾邮件文件夹中，您还可以选择“报告不是垃圾邮件”。</span><span class="sxs-lookup"><span data-stu-id="bba99-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="bba99-173">使用静默模式安装垃圾电子邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="bba99-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="bba99-174">在您的计算机上关闭 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bba99-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="bba99-175">在 Windows 10 中，通过运行以下命令安装 .NET Framework 2.0：</span><span class="sxs-lookup"><span data-stu-id="bba99-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="bba99-176">若要在没有任何用户交互的情况下安装外接程序，请打开命令提示符并使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bba99-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="bba99-177">`MaxMessageSelection` 指定你可以为单个提交选择的最大邮件数。</span><span class="sxs-lookup"><span data-stu-id="bba99-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="bba99-178">有效值为 1 到 50。</span><span class="sxs-lookup"><span data-stu-id="bba99-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="bba99-179">默认值为 15。</span><span class="sxs-lookup"><span data-stu-id="bba99-179">The default value is 15.</span></span>

   - <span data-ttu-id="bba99-180">`BccEmailAddress` 指定将接收所有用户提交副本的其他 Bcc 收件人。</span><span class="sxs-lookup"><span data-stu-id="bba99-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="bba99-181">默认值为空， (其他"Bcc"收件人) 。</span><span class="sxs-lookup"><span data-stu-id="bba99-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="bba99-182">此示例从具有默认设置的指定路径安装 64 位版本的外接程序。</span><span class="sxs-lookup"><span data-stu-id="bba99-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="bba99-183">此示例使用下列其他设置从指定路径安装 32 位版本的外接程序：</span><span class="sxs-lookup"><span data-stu-id="bba99-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="bba99-184">一次提交中最多只能选择 20 条消息。</span><span class="sxs-lookup"><span data-stu-id="bba99-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="bba99-185">junkreports@contoso.com hollyd@treyresearch.net接收所有提交的 Bcc 副本。</span><span class="sxs-lookup"><span data-stu-id="bba99-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bba99-186">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="bba99-186">How do you know this worked?</span></span>

<span data-ttu-id="bba99-187">若要验证您是否已成功安装垃圾邮件报告外接程序，请执行 Outlook 中的下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="bba99-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="bba99-188">选择邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="bba99-188">Select the message or open the message.</span></span> <span data-ttu-id="bba99-189">在功能 **区的** " **主页** "或"消息"选项卡中，单击 **"** 垃圾邮件"，并验证以下选项是否可用：</span><span class="sxs-lookup"><span data-stu-id="bba99-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="bba99-190">**报告为垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="bba99-190">**Report as Junk**</span></span>
  - <span data-ttu-id="bba99-191">**报告为网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="bba99-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="bba99-192">**垃圾邮件报告选项**</span><span class="sxs-lookup"><span data-stu-id="bba99-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="bba99-193">**报告垃圾邮件联机帮助**</span><span class="sxs-lookup"><span data-stu-id="bba99-193">**Report Junk Online Help**</span></span>

  ![从功能区报告垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="bba99-195">右键单击邮件 **，选择"** 垃圾邮件"，并验证以下选项是否可用：</span><span class="sxs-lookup"><span data-stu-id="bba99-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="bba99-196">**报告为垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="bba99-196">**Report as Junk**</span></span>
  - <span data-ttu-id="bba99-197">**报告为网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="bba99-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="bba99-198">**垃圾邮件报告选项**</span><span class="sxs-lookup"><span data-stu-id="bba99-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="bba99-199">**报告垃圾邮件联机帮助**</span><span class="sxs-lookup"><span data-stu-id="bba99-199">**Report Junk Online Help**</span></span>

  ![右键单击报告垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="bba99-201">选择多条消息，右键单击并验证以下选项是否可用：</span><span class="sxs-lookup"><span data-stu-id="bba99-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="bba99-202">**报告为垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="bba99-202">**Report as Junk**</span></span>
  - <span data-ttu-id="bba99-203">**报告为网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="bba99-203">**Report as Phishing**</span></span>

  ![右键单击报告多个垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="bba99-205">在"垃圾邮件"文件夹中执行 **之前的操作，** 并验证以前的 **"** 垃圾邮件"报告选项现在为 **"非垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![从"垃圾邮件"文件夹中的功能区报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![在"垃圾邮件"文件夹中右键单击报告非垃圾邮件或钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![在"垃圾邮件"文件夹中右键单击报告多个非垃圾邮件或网络钓鱼电子邮件](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="bba99-209">卸载垃圾电子邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="bba99-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="bba99-210">关闭 Outlook 后，使用以下任一过程卸载垃圾邮件报告外接程序：</span><span class="sxs-lookup"><span data-stu-id="bba99-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="bba99-211">**控制面板：** 按 Windows 键 + R。在打开 **的"** 运行"对话框中，输入 `control appwiz.cpl` ，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="bba99-212">在列表中查找并选择 **Microsoft 垃圾邮件** 报告外接程序，然后单击"卸载 **"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="bba99-213">**Windows Installer 程序包**：查找或下载相应的 .msi 文件，然后双击它。</span><span class="sxs-lookup"><span data-stu-id="bba99-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="bba99-214">**32 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="bba99-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="bba99-215">**64 位**： `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="bba99-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="bba99-216">在出现的对话框中，选择 **"删除 Outlook 的 Microsoft 垃圾邮件报告** 外接程序"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="bba99-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="bba99-217">**静默模式**：查找或下载相应的 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="bba99-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="bba99-218">在命令提示符窗口中， \<PathToFile\> 替换为 .msi 文件的位置，并运行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="bba99-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="bba99-219">**32 位**：</span><span class="sxs-lookup"><span data-stu-id="bba99-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="bba99-220">**64 位**：</span><span class="sxs-lookup"><span data-stu-id="bba99-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="bba99-221">卸载后打开 Outlook 时，垃圾邮件、非垃圾邮件和网络钓鱼报告选项应消失。</span><span class="sxs-lookup"><span data-stu-id="bba99-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="bba99-222">垃圾邮件报告外接程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="bba99-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="bba99-223">有时，在添加垃圾邮件报告外接程序后，您可能会遇到 Outlook 问题。</span><span class="sxs-lookup"><span data-stu-id="bba99-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="bba99-224">本节介绍您可能遇到的问题，以及解决这些问题的提示。</span><span class="sxs-lookup"><span data-stu-id="bba99-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="bba99-225">用户疑难解答</span><span class="sxs-lookup"><span data-stu-id="bba99-225">Troubleshooting for users</span></span>

<span data-ttu-id="bba99-226">您遇到以下一个或多个问题：</span><span class="sxs-lookup"><span data-stu-id="bba99-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="bba99-227">Nothing happens when you click **Report Junk**</span><span class="sxs-lookup"><span data-stu-id="bba99-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="bba99-228">当您选择一封电子邮件之后，Outlook 停止响应</span><span class="sxs-lookup"><span data-stu-id="bba99-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="bba99-229">由于收到"未送达"回复，报告的垃圾邮件无法传递</span><span class="sxs-lookup"><span data-stu-id="bba99-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="bba99-230">若要解决此问题，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="bba99-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="bba99-231">关闭并重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bba99-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="bba99-232">创建并发送测试邮件，并验证收件人是否收到该邮件。</span><span class="sxs-lookup"><span data-stu-id="bba99-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="bba99-233">如果问题仍然存在，请与管理员联系。</span><span class="sxs-lookup"><span data-stu-id="bba99-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="bba99-234">有关可用于将邮件提交到 Microsoft 的其他方法，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="bba99-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="bba99-235">管理员疑难解答</span><span class="sxs-lookup"><span data-stu-id="bba99-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="bba99-236">问题：不断出现一条错误消息，要求用户联系系统管理员</span><span class="sxs-lookup"><span data-stu-id="bba99-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="bba99-237">验证注册表 `LoggingLevel` 项或将注册表项设置为值"Verbose"：</span><span class="sxs-lookup"><span data-stu-id="bba99-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="bba99-238">**32 位 Windows 上的 32 位 Outlook：**</span><span class="sxs-lookup"><span data-stu-id="bba99-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="bba99-239">**64 位 Windows 上的 32 位 Outlook：**</span><span class="sxs-lookup"><span data-stu-id="bba99-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="bba99-240">**64 位 Outlook：**</span><span class="sxs-lookup"><span data-stu-id="bba99-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="bba99-241">重新启动 Outlook，并要求用户在看到错误消息时报告。</span><span class="sxs-lookup"><span data-stu-id="bba99-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="bba99-242">收集在以下位置找到的日志信息：</span><span class="sxs-lookup"><span data-stu-id="bba99-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="bba99-243">联系 Exchange Online Protection 技术支持并向他们提供日志信息。</span><span class="sxs-lookup"><span data-stu-id="bba99-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="bba99-244">问题：用户在报告邮件时选择不接收确认提示，但现在希望返回提示</span><span class="sxs-lookup"><span data-stu-id="bba99-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="bba99-245">创建 `ConfirmReportJunk` 值为"True"的注册表项：</span><span class="sxs-lookup"><span data-stu-id="bba99-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="bba99-246">重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bba99-246">Restart Outlook.</span></span>
