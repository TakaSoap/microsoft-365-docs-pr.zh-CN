---
title: 撤销由高级邮件加密加密的电子邮件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作为管理员和邮件发件人，可以撤销某些使用 Office 365 高级邮件加密加密的电子邮件。
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105137"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="8fc96-103">撤销由高级邮件加密加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="8fc96-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="8fc96-104">电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="8fc96-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="8fc96-105">Office 365 高级邮件加密包含在 [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/home)企业版 E5、Office 365 E5、Microsoft 365 E5 (非营利组织员工定价) 、Office 365 企业版 E5 (非营利组织版员工定价) 和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="8fc96-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="8fc96-106">如果组织具有不包括 Office 365 高级邮件加密的订阅， 可以使用 Microsoft 365 E3 的 Microsoft 365 E5 合规性 SKU 加载项、Microsoft 365 E3 (非盈利性员工定价) 或 Microsoft 365 E3、Microsoft 365 E3 (非营利组织版员工定价) 或 Office 365 SKU 的 Office 365 高级合规性 SKU 加载项购买。</span><span class="sxs-lookup"><span data-stu-id="8fc96-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="8fc96-107">本文是有关 [Office 365](ome.md)邮件加密的较大系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="8fc96-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="8fc96-108">如果使用 Office 365 高级邮件加密对邮件进行加密，并且你是 Microsoft 365 管理员，或者你是邮件的发件人，则在某些情况下可以撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="8fc96-109">管理员使用 PowerShell 撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="8fc96-110">作为发件人，您可以撤销直接从 Outlook 网页邮件发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="8fc96-111">本文介绍可能吊销的情况以及如何进行吊销。</span><span class="sxs-lookup"><span data-stu-id="8fc96-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="8fc96-112">可以撤销的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="8fc96-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="8fc96-113">如果收件人收到基于链接的品牌加密电子邮件，则管理员和邮件发件人可以吊销加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="8fc96-114">如果收件人在受支持的 Outlook 客户端中收到了本机内联体验，则不能撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="8fc96-115">收件人是否收到基于链接的体验或内联体验取决于收件人标识类型：Office 365 和 Microsoft 帐户收件人 (例如，outlook.com 用户) 在受支持的 Outlook 客户端中获得内联体验。</span><span class="sxs-lookup"><span data-stu-id="8fc96-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="8fc96-116">所有其他收件人类型（如 Gmail 和 Yahoo 收件人）都获得基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="8fc96-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="8fc96-117">管理员和邮件发件人可以撤销使用直接从 Outlook 网页应用加密加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="8fc96-118">例如，使用"仅加密"选项加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="显示 Outlook 网页中的&quot;仅加密&quot;选项的屏幕截图。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="8fc96-120">已吊销加密电子邮件的收件人体验</span><span class="sxs-lookup"><span data-stu-id="8fc96-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="8fc96-121">撤销电子邮件后，收件人通过 Office 365 邮件加密门户访问加密电子邮件时收到错误："发件人已吊销邮件"。</span><span class="sxs-lookup"><span data-stu-id="8fc96-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![显示已吊销的加密电子邮件的屏幕截图。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="8fc96-123">如何撤销已发送的加密邮件</span><span class="sxs-lookup"><span data-stu-id="8fc96-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="8fc96-124">您可以撤消发送给使用社交帐户（如用户或gmail.com）的单个yahoo.com。</span><span class="sxs-lookup"><span data-stu-id="8fc96-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="8fc96-125">换句话说，您可以撤消发送给接收基于链接的体验的单个收件人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="8fc96-126">无法撤消发送给使用 Office 365 或 Microsoft 365 工作或学校帐户的收件人或使用 Microsoft 帐户的用户（例如，outlook.com帐户）的邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="8fc96-127">若要撤销已发送的加密邮件，请完成这些步骤</span><span class="sxs-lookup"><span data-stu-id="8fc96-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="8fc96-128">在 Outlook 网页 **中的"已** 发送"文件夹中，浏览到要撤销的邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="8fc96-129">如果邮件是可撤销的，你将在邮件顶部看到"删除外部访问"链接。</span><span class="sxs-lookup"><span data-stu-id="8fc96-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot showing encrypted mail that you want to revoke in Outlook on the web.":::

2. <span data-ttu-id="8fc96-131">单击 **"删除外部访问** "以撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="8fc96-132">该消息显示其状态已被吊销。</span><span class="sxs-lookup"><span data-stu-id="8fc96-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot showing revoked encrypted message in Outlook on the web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="8fc96-134">如何以管理员角色撤销加密邮件</span><span class="sxs-lookup"><span data-stu-id="8fc96-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="8fc96-135">Microsoft 365 管理员按照以下常规步骤撤销符合条件的加密电子邮件：</span><span class="sxs-lookup"><span data-stu-id="8fc96-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="8fc96-136">获取电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="8fc96-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="8fc96-137">验证您是否可以撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="8fc96-138">撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="8fc96-139">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="8fc96-139">Step 1.</span></span> <span data-ttu-id="8fc96-140">获取电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="8fc96-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="8fc96-141">在可以撤销加密邮件之前，请收集邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="8fc96-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="8fc96-142">MessageId 通常采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="8fc96-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="8fc96-143">有多种方法可查找要撤销的电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="8fc96-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="8fc96-144">本节介绍几个选项，但您可以使用任何提供 ID 的方法。</span><span class="sxs-lookup"><span data-stu-id="8fc96-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="8fc96-145">使用安全合规中心中的邮件跟踪标识要撤销的电子邮件 &amp; 的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="8fc96-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="8fc96-146">使用安全与合规中心中的"新建邮件跟踪"按发件人& [电子邮件](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)。</span><span class="sxs-lookup"><span data-stu-id="8fc96-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="8fc96-147">找到电子邮件后，选择它可显示"邮件跟踪 **详细信息"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="8fc96-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="8fc96-148">展开 **"详细信息** "以查找邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="8fc96-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="8fc96-149">使用安全合规中心中的 Office 邮件加密报告标识要撤销的电子邮件 &amp; 的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="8fc96-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="8fc96-150">在安全 &amp; 合规中心，导航到邮件 **加密报告**。</span><span class="sxs-lookup"><span data-stu-id="8fc96-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="8fc96-151">有关此报告的信息，请参阅 [安全合规中心查看 &amp; 电子邮件安全报告](../security/office-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="8fc96-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="8fc96-152">选择 **"查看详细信息** "表并标识要撤销的邮件。</span><span class="sxs-lookup"><span data-stu-id="8fc96-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="8fc96-153">双击邮件以查看包含邮件 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8fc96-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="8fc96-154">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="8fc96-154">Step 2.</span></span> <span data-ttu-id="8fc96-155">验证邮件是否可撤销</span><span class="sxs-lookup"><span data-stu-id="8fc96-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="8fc96-156">若要验证是否可以吊销邮件，请检查安全合规中心详细信息表中的"加密"报告中是否显示"吊销状态" &amp; 字段。</span><span class="sxs-lookup"><span data-stu-id="8fc96-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="8fc96-157">若要验证是否可以通过使用密码来撤销特定Windows PowerShell，请完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="8fc96-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="8fc96-158">使用组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="8fc96-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="8fc96-159">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="8fc96-159">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="8fc96-160">运行 Get-OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fc96-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="8fc96-161">此命令返回邮件的主题以及邮件是否可撤销。</span><span class="sxs-lookup"><span data-stu-id="8fc96-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="8fc96-162">例如，</span><span class="sxs-lookup"><span data-stu-id="8fc96-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="8fc96-163">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="8fc96-163">Step 3.</span></span> <span data-ttu-id="8fc96-164">撤销邮件</span><span class="sxs-lookup"><span data-stu-id="8fc96-164">Revoke the mail</span></span>

<span data-ttu-id="8fc96-165">一旦知道要撤销的电子邮件的邮件 ID，并且已验证该邮件是可撤销的，可以使用安全合规中心或安全中心 &amp; Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8fc96-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="8fc96-166">使用安全合规中心 &amp; 撤销邮件</span><span class="sxs-lookup"><span data-stu-id="8fc96-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="8fc96-167">使用组织中具有全局管理员权限的工作或学校帐户连接到安全与合规&中心。</span><span class="sxs-lookup"><span data-stu-id="8fc96-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="8fc96-168">在加密 **报告中**，在邮件的详细信息 **表中，** 选择"**撤销邮件"。**</span><span class="sxs-lookup"><span data-stu-id="8fc96-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="8fc96-169">若要使用 Windows PowerShell 撤销Set-OMEMessageRevocation cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8fc96-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="8fc96-170">使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell。](https://aka.ms/exopowershell)</span><span class="sxs-lookup"><span data-stu-id="8fc96-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="8fc96-171">运行 Set-OMEMessageRevocation cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fc96-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="8fc96-172">若要检查电子邮件是否已吊销，请运行 Get-OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8fc96-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="8fc96-173">如果吊销成功，该 cmdlet 将返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="8fc96-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="8fc96-174">有关 Office 365 高级邮件加密详细信息</span><span class="sxs-lookup"><span data-stu-id="8fc96-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="8fc96-175">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="8fc96-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="8fc96-176">Office 365 高级邮件加密 - 电子邮件过期</span><span class="sxs-lookup"><span data-stu-id="8fc96-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="8fc96-177">邮件策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="8fc96-177">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
