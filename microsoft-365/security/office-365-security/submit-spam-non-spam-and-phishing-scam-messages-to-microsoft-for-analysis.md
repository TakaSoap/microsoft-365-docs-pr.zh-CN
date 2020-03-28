---
title: 手动将邮件提交给 Microsoft 进行分析
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: '你和你的用户可以将虚假的负垃圾邮件和假肯定垃圾邮件提交给 Microsoft 进行分析。 '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032800"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="f2758-103">手动将邮件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="f2758-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="f2758-104">如果您是使用 Exchange Online 邮箱的 Office 365 组织中的管理员，我们建议您在 Office 365 安全性 & 合规性中心中使用提交门户。</span><span class="sxs-lookup"><span data-stu-id="f2758-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="f2758-105">有关详细信息，请参阅[使用管理员提交将可疑的垃圾邮件、网络钓鱼、url 和文件提交给 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="f2758-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f2758-106">如果组织中的用户在其收件箱中收到垃圾邮件（垃圾邮件）或网络钓鱼邮件，或者如果邮件被标记为垃圾邮件，则可能会令人沮丧。</span><span class="sxs-lookup"><span data-stu-id="f2758-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="f2758-107">我们不断调整垃圾邮件筛选器，使其更加准确。</span><span class="sxs-lookup"><span data-stu-id="f2758-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="f2758-108">您和您的用户可以通过将误报（好的电子邮件标记为 "坏"）、"漏报（允许错误邮件）" 和 "网络钓鱼邮件" 提交给 Microsoft 进行分析来帮助此过程。</span><span class="sxs-lookup"><span data-stu-id="f2758-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="f2758-109">由于我们收到的提交量很大，我们可能无法应答所有分析请求。</span><span class="sxs-lookup"><span data-stu-id="f2758-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="f2758-110">将漏报提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2758-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f2758-111">Outlook 和 web 上的 Outlook （以前称为 Outlook Web App）中的用户可以使用 Microsoft Outlook 的报告消息外接程序，而不是使用以下过程来报告漏报。</span><span class="sxs-lookup"><span data-stu-id="f2758-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="f2758-112">有关如何安装和使用此工具的信息，请参阅[Enable The Report Message 外接程序](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="f2758-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="f2758-113">如果您收到一封邮件，该邮件将通过应标识为垃圾邮件或网络钓鱼的垃圾邮件筛选传递，则可以根据需要将邮件提交到 Microsoft 垃圾邮件分析和 Microsoft 仿冒分析团队。</span><span class="sxs-lookup"><span data-stu-id="f2758-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="f2758-114">分析师将检查邮件并将其添加到服务范围的筛选器中（如果它满足分类条件）。</span><span class="sxs-lookup"><span data-stu-id="f2758-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="f2758-115">使用以下收件人之一创建一个新的空白电子邮件：</span><span class="sxs-lookup"><span data-stu-id="f2758-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="f2758-116">**垃圾邮件**：`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f2758-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="f2758-117">**网络钓鱼**：`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="f2758-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="f2758-118">将垃圾邮件或仿冒邮件拖放到新邮件中。</span><span class="sxs-lookup"><span data-stu-id="f2758-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="f2758-119">这会将垃圾邮件或仿冒邮件保存为新邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="f2758-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="f2758-120">请勿复制和粘贴邮件的内容或转发邮件（我们需要原始邮件，以便我们可以检查邮件头）。</span><span class="sxs-lookup"><span data-stu-id="f2758-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="f2758-121">您可以在新邮件中附加多封邮件。</span><span class="sxs-lookup"><span data-stu-id="f2758-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f2758-122">确保所有邮件都属于同一类型： "仿冒欺诈邮件" 或 "垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="f2758-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="f2758-123">保留新的邮件正文空白。</span><span class="sxs-lookup"><span data-stu-id="f2758-123">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="f2758-124">对于附加的邮件，请使用 .msg （默认 Outlook 格式）或 .eml （默认 Outlook 网页格式）格式。</span><span class="sxs-lookup"><span data-stu-id="f2758-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="f2758-125">完成后，请单击 "**发送**"。</span><span class="sxs-lookup"><span data-stu-id="f2758-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f2758-126">管理员有几种不同的方法来阻止被 misidentified 为垃圾邮件的特定邮件。</span><span class="sxs-lookup"><span data-stu-id="f2758-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="f2758-127">有关详细信息，请参阅[在 Office 365 中创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f2758-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="f2758-128">向 Microsoft 提交误报</span><span class="sxs-lookup"><span data-stu-id="f2758-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="f2758-129">Outlook 和 Outlook 网页版中的用户可以使用 Microsoft Outlook 的报告消息外接程序，而不是使用以下过程报告误报。</span><span class="sxs-lookup"><span data-stu-id="f2758-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="f2758-130">有关如何安装和使用此工具的信息，请参阅[Enable The Report Message 外接程序](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="f2758-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="f2758-131">如果邮件被错误地标识为垃圾邮件，您可以将邮件提交给 Microsoft 垃圾邮件分析团队。</span><span class="sxs-lookup"><span data-stu-id="f2758-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="f2758-132">分析师将评估邮件，并且（取决于分析结果）可以调整服务范围的筛选器以允许邮件通过。</span><span class="sxs-lookup"><span data-stu-id="f2758-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="f2758-133">创建一个新的空白电子邮件， `not_junk@office365.microsoft.com`作为收件人：</span><span class="sxs-lookup"><span data-stu-id="f2758-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="f2758-134">将 misidentified 邮件拖放到新邮件中。</span><span class="sxs-lookup"><span data-stu-id="f2758-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="f2758-135">这会将 misidentified 邮件另存为新邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="f2758-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="f2758-136">请勿复制和粘贴邮件的内容或转发邮件（我们需要原始邮件，以便我们可以检查邮件头）。</span><span class="sxs-lookup"><span data-stu-id="f2758-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="f2758-137">您可以在新邮件中附加多封邮件。</span><span class="sxs-lookup"><span data-stu-id="f2758-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="f2758-138">确保所有邮件都属于同一类型： "仿冒欺诈邮件" 或 "垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="f2758-138">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="f2758-139">保留新的邮件正文空白。</span><span class="sxs-lookup"><span data-stu-id="f2758-139">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="f2758-140">对于附加的邮件，请使用 .msg （默认 Outlook 格式）或 .eml （默认 Outlook 网页格式）格式。</span><span class="sxs-lookup"><span data-stu-id="f2758-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="f2758-141">完成后，请单击 "**发送**"。</span><span class="sxs-lookup"><span data-stu-id="f2758-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="f2758-142">管理员有几种不同的方法允许特定邮件跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="f2758-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="f2758-143">有关详细信息，请参阅[在 Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f2758-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="f2758-144">创建邮件流规则以接收报告给 Microsoft 的邮件副本</span><span class="sxs-lookup"><span data-stu-id="f2758-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="f2758-145">您可以创建邮件流规则（也称为传输规则），以查找通过使用本主题中所述的方法报告给 Microsoft 的电子邮件，并且您可以配置密件抄送收件人以接收这些报告的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="f2758-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="f2758-146">您可以在 Exchange 管理中心（EAC）和 PowerShell （Office 365 客户的 Exchange Online PowerShell 中创建邮件流规则;适用于独立 EOP 客户的 Exchange Online Protection PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="f2758-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f2758-147">开始前，需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="f2758-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f2758-148">您需要先在 Exchange Online 中分配权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="f2758-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="f2758-149">具体来说，您需要分配 "**传输规则**" 角色，默认情况下会将其分配给 "**组织管理**"、"**合规性管理**" 和 "**记录管理**" 角色。</span><span class="sxs-lookup"><span data-stu-id="f2758-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="f2758-150">有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="f2758-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="f2758-151">若要在 Exchange Online 中打开 EAC，请参阅 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f2758-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="f2758-152">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f2758-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f2758-153">若要连接到独立的 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f2758-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f2758-154">有关 Exchange Online 和独立 EOP 中的邮件流规则的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f2758-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="f2758-155">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="f2758-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="f2758-156">Exchange Online 中的邮件流规则条件和例外（谓词）</span><span class="sxs-lookup"><span data-stu-id="f2758-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="f2758-157">Exchange Online 中的邮件流规则操作</span><span class="sxs-lookup"><span data-stu-id="f2758-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="f2758-158">使用 EAC 创建邮件流规则以接收报告的邮件的副本</span><span class="sxs-lookup"><span data-stu-id="f2758-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="f2758-159">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="f2758-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="f2758-160">单击 "**添加** !["](../../media/ITPro-EAC-AddIcon.png) "添加" 图标，然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="f2758-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="f2758-161">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="f2758-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="f2758-162">**名称**：输入规则的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="f2758-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="f2758-163">例如，向 Microsoft 报告的密件抄送邮件。</span><span class="sxs-lookup"><span data-stu-id="f2758-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="f2758-164">单击“其他选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f2758-164">Click **More Options**.</span></span>

   - <span data-ttu-id="f2758-165">**在以下情况下应用此规则**：选择**收件人** \> **地址包括以下任何词语**：在显示的 "**指定字词或短语**" 对话框中，输入以下值之一， **Add** ![单击 "添加](../../media/ITPro-EAC-AddIcon.png)" "添加" 图标，然后重复此步骤，直到您输入所有值为止。</span><span class="sxs-lookup"><span data-stu-id="f2758-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="f2758-166">若要编辑条目，请选择该条目**Edit** ![，然后单击](../../media/ITPro-EAC-EditIcon.png)"编辑" "编辑" 图标。</span><span class="sxs-lookup"><span data-stu-id="f2758-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="f2758-167">若要删除条目，请将其选中**Remove** ![，然后单击](../../media/ITPro-EAC-DeleteIcon.png)"删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="f2758-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="f2758-168">完成后，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="f2758-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="f2758-169">**执行下列**操作：选择 "**将收件人** \>添加**到密件抄送" 框**。</span><span class="sxs-lookup"><span data-stu-id="f2758-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="f2758-170">在出现的对话框中，查找并选择要添加的收件人。</span><span class="sxs-lookup"><span data-stu-id="f2758-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="f2758-171">完成后，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="f2758-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="f2758-172">您可以进行其他选择来审核规则、测试规则、在特定时间段内激活规则，以及其他设置。</span><span class="sxs-lookup"><span data-stu-id="f2758-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="f2758-173">建议在强制执行规则之前对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="f2758-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="f2758-174">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f2758-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="f2758-175">使用 PowerShell 创建邮件流规则以接收报告的邮件的副本</span><span class="sxs-lookup"><span data-stu-id="f2758-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="f2758-176">本示例将新建一个名为 "密件抄送给 Microsoft" 的邮件流规则，该规则将查找通过使用本主题中所述方法报告给 Microsoft 的电子邮件，并将用户 laura@contoso.com 和 julia@contoso.com 添加为密件抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="f2758-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="f2758-177">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="f2758-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f2758-178">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="f2758-178">How do you know this worked?</span></span>

<span data-ttu-id="f2758-179">若要验证是否已将邮件流规则配置为接收报告的邮件的副本，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="f2758-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="f2758-180">在 EAC 中，转到 **"邮件流** \> **规则** \> "。 \>选择该规则，](../../media/ITPro-EAC-EditIcon.png)然后单击 "**编辑** ![编辑" 图标，并验证设置。</span><span class="sxs-lookup"><span data-stu-id="f2758-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="f2758-181">在 PowerShell 中，运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="f2758-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="f2758-182">将测试邮件发送到其中一个报告电子邮件地址，并验证结果。</span><span class="sxs-lookup"><span data-stu-id="f2758-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
