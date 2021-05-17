---
title: 撤销通过高级邮件加密加密的电子邮件
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
description: 作为管理员和邮件发件人，您可以撤消某些使用邮件加密Office 365 高级邮件加密。
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051714"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="92dbd-103">撤销通过高级邮件加密加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="92dbd-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="92dbd-104">电子邮件吊销作为电子邮件吊销的一Office 365 高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="92dbd-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="92dbd-105">Office 365 高级邮件加密[包含在 Microsoft 365 企业版 E5、Office 365 E5、Microsoft 365 E5 (](https://www.microsoft.com/microsoft-365/enterprise/home)非营利组织员工定价) 、Office 365 企业版 E5 (非营利组织员工定价) 和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="92dbd-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="92dbd-106">如果你的组织订阅不包含 Office 365 高级邮件加密，可以使用 Microsoft 365 E3 的 Microsoft 365 E5 合规 SKU 加载项、Microsoft 365 E3 (非营利组织员工定价) 或 Microsoft 365 E3、Microsoft 365 E3 (非营利组织员工定价) 或 Office 365 SKU 的 Office 365 高级合规版 SKU 加载项购买它。</span><span class="sxs-lookup"><span data-stu-id="92dbd-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="92dbd-107">本文是有关本文的更多系列文章的一[Office 365 邮件加密。](ome.md)</span><span class="sxs-lookup"><span data-stu-id="92dbd-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="92dbd-108">如果邮件是使用 Office 365 高级邮件加密 加密的，并且你是Microsoft 365管理员，或者你是邮件的发件人，则在某些情况下可以撤销该邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="92dbd-109">管理员使用 PowerShell 撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="92dbd-110">作为发件人，你可以撤销直接从 Web 上的Outlook发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="92dbd-111">本文介绍可能吊销的情况以及如何进行吊销。</span><span class="sxs-lookup"><span data-stu-id="92dbd-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="92dbd-112">可以撤销的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="92dbd-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="92dbd-113">如果收件人收到基于链接的品牌加密电子邮件，则管理员和邮件发件人可以吊销加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="92dbd-114">如果收件人在受支持的客户端收到本机内联Outlook，则不能撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="92dbd-115">收件人是否收到基于链接的体验或内联体验取决于收件人标识类型：Office 365 和 Microsoft 帐户收件人 (例如，outlook.com 用户) 受支持的 Outlook 客户端获得内联体验。</span><span class="sxs-lookup"><span data-stu-id="92dbd-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="92dbd-116">所有其他收件人类型（如 Gmail 和 Yahoo 收件人）都获得基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="92dbd-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="92dbd-117">管理员和邮件发件人可以吊销使用直接来自 Web 上的Outlook加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="92dbd-118">例如，使用"仅加密"选项加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot showing Encrypt Only option in Outlook on the web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="92dbd-120">已吊销加密电子邮件的收件人体验</span><span class="sxs-lookup"><span data-stu-id="92dbd-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="92dbd-121">电子邮件被吊销后，收件人在通过 Office 365 邮件加密 门户访问加密电子邮件时会收到一个错误："发件人已吊销该邮件"。</span><span class="sxs-lookup"><span data-stu-id="92dbd-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![显示已吊销的加密电子邮件的屏幕截图。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="92dbd-123">如何撤销已发送的加密邮件</span><span class="sxs-lookup"><span data-stu-id="92dbd-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="92dbd-124">您可以撤消发送给使用社交帐户（如邮箱或邮箱）的单个 gmail.com yahoo.com。</span><span class="sxs-lookup"><span data-stu-id="92dbd-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="92dbd-125">换句话说，您可以撤消发送给接收基于链接的体验的单个收件人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="92dbd-126">您无法撤消发送给使用 Office 365 或 Microsoft 365 工作或学校帐户的收件人或使用 Microsoft 帐户（例如，outlook.com 帐户）的用户的邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="92dbd-127">若要撤销已发送的加密邮件，请完成这些步骤</span><span class="sxs-lookup"><span data-stu-id="92dbd-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="92dbd-128">在Outlook中，在"已发送 **"文件夹中浏览** 到要撤销的邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="92dbd-129">如果邮件可撤销，你将在邮件顶部看到"删除外部访问"链接。</span><span class="sxs-lookup"><span data-stu-id="92dbd-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot showing encrypted mail that you want to revoke in Outlook on the web.":::

2. <span data-ttu-id="92dbd-131">单击 **"删除外部访问** "以撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="92dbd-132">该消息显示其状态已被吊销。</span><span class="sxs-lookup"><span data-stu-id="92dbd-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot showing revoked encrypted message in Outlook on the web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="92dbd-134">如何以管理员角色撤销加密邮件</span><span class="sxs-lookup"><span data-stu-id="92dbd-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="92dbd-135">Microsoft 365管理员按照以下常规步骤撤销符合条件的加密电子邮件：</span><span class="sxs-lookup"><span data-stu-id="92dbd-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="92dbd-136">获取电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="92dbd-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="92dbd-137">验证您是否可以撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="92dbd-138">撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="92dbd-139">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="92dbd-139">Step 1.</span></span> <span data-ttu-id="92dbd-140">获取电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="92dbd-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="92dbd-141">在可以撤销加密邮件之前，请收集邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="92dbd-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="92dbd-142">MessageId 的格式通常为：</span><span class="sxs-lookup"><span data-stu-id="92dbd-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="92dbd-143">有多种方法可查找要撤销的电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="92dbd-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="92dbd-144">本节介绍几个选项，但您可以使用任何提供 ID 的方法。</span><span class="sxs-lookup"><span data-stu-id="92dbd-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="92dbd-145">使用安全与合规中心内的邮件跟踪标识要撤销的电子邮件的邮件 &amp; ID</span><span class="sxs-lookup"><span data-stu-id="92dbd-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="92dbd-146">使用安全与合规中心中的"新建邮件跟踪"按发件人 [&电子邮件](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)。</span><span class="sxs-lookup"><span data-stu-id="92dbd-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="92dbd-147">找到电子邮件后，选择它可显示"邮件 **跟踪详细信息"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="92dbd-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="92dbd-148">展开 **"详细信息** "以查找邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="92dbd-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="92dbd-149">使用安全与合规中心中的"邮件加密"报告Office要撤销的电子邮件的邮件 &amp; ID</span><span class="sxs-lookup"><span data-stu-id="92dbd-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="92dbd-150">在安全 &amp; 与合规中心中，导航到"**邮件加密报告"。**</span><span class="sxs-lookup"><span data-stu-id="92dbd-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="92dbd-151">有关此报告的信息，请参阅在安全与 [合规中心查看电子邮件 &amp; 安全报告](../security/defender-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="92dbd-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="92dbd-152">选择 **"查看详细信息** "表，并确定要撤销的邮件。</span><span class="sxs-lookup"><span data-stu-id="92dbd-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="92dbd-153">双击邮件以查看包含邮件 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="92dbd-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="92dbd-154">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="92dbd-154">Step 2.</span></span> <span data-ttu-id="92dbd-155">验证邮件是否可撤销</span><span class="sxs-lookup"><span data-stu-id="92dbd-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="92dbd-156">若要验证是否可以吊销邮件，请检查安全与合规中心的"详细信息"表中的"加密"报告中是否显示"吊销状态 &amp; "字段。</span><span class="sxs-lookup"><span data-stu-id="92dbd-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="92dbd-157">若要验证是否可以通过使用电子邮件来撤销特定Windows PowerShell，请完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="92dbd-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="92dbd-158">使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="92dbd-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="92dbd-159">有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="92dbd-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="92dbd-160">运行 Get-OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92dbd-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="92dbd-161">此命令返回邮件的主题以及邮件是否可撤销。</span><span class="sxs-lookup"><span data-stu-id="92dbd-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="92dbd-162">例如，</span><span class="sxs-lookup"><span data-stu-id="92dbd-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="92dbd-163">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="92dbd-163">Step 3.</span></span> <span data-ttu-id="92dbd-164">撤销邮件</span><span class="sxs-lookup"><span data-stu-id="92dbd-164">Revoke the mail</span></span>

<span data-ttu-id="92dbd-165">一旦知道要撤销的电子邮件的邮件 ID，并且已验证该邮件是可撤销的，可以使用安全与合规中心或 &amp; Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="92dbd-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="92dbd-166">使用安全与合规中心 &amp; 撤销邮件</span><span class="sxs-lookup"><span data-stu-id="92dbd-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="92dbd-167">使用在组织中具有全局管理员权限的工作或学校帐户，连接到安全&中心。</span><span class="sxs-lookup"><span data-stu-id="92dbd-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="92dbd-168">在加密 **报告中，** 在邮件 **的详细信息** 表中，选择撤销 **邮件**。</span><span class="sxs-lookup"><span data-stu-id="92dbd-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="92dbd-169">若要使用 cmdlet 撤销Windows PowerShell，请使用 Set-OMEMessageRevocation cmdlet。</span><span class="sxs-lookup"><span data-stu-id="92dbd-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="92dbd-170">使用在组织中具有全局管理员权限的工作或学校帐户，连接 Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="92dbd-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="92dbd-171">运行 Set-OMEMessageRevocation cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92dbd-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="92dbd-172">若要检查电子邮件是否已吊销，请运行Get-OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92dbd-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="92dbd-173">如果吊销成功，该 cmdlet 将返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="92dbd-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="92dbd-174">有关 Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="92dbd-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="92dbd-175">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="92dbd-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="92dbd-176">Office 365 高级邮件加密 - 电子邮件过期</span><span class="sxs-lookup"><span data-stu-id="92dbd-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="92dbd-177">邮件策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="92dbd-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)