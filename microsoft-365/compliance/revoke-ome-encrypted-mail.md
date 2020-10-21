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
description: 作为管理员和邮件发件人，您可以吊销使用 Office 365 高级邮件加密进行加密的某些电子邮件。
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868932"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="dfcce-103">撤销由高级邮件加密加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="dfcce-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="dfcce-104">电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="dfcce-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="dfcce-105">Office 365 高级邮件加密包含在 [Microsoft 365 企业版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 e5 (非盈利性员工定价) 、Office 365 企业版 E5 (非盈利性员工定价) 和 Office 365 教育版 A5。</span><span class="sxs-lookup"><span data-stu-id="dfcce-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="dfcce-106">如果您的组织具有不包含 Office 365 高级邮件加密的订阅，则可以使用 microsoft 365 E5 兼容性 SKU 附加 Microsoft 365 E3、Microsoft 365 E3 (非盈利性的员工定价) 或 Office 365 高级合规性 SKU 附加 for Microsoft 365 E3、Microsoft 365 E3 (非盈利性员工定价) 或 Office 365 Sku 购买。</span><span class="sxs-lookup"><span data-stu-id="dfcce-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="dfcce-107">本文是有关 [Office 365 邮件加密](ome.md)的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="dfcce-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="dfcce-108">如果使用 Office 365 高级邮件加密对邮件进行了加密，并且您是 Microsoft 365 管理员，或者是邮件的发件人，则可以在特定条件下撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="dfcce-109">管理员使用 PowerShell 撤消邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="dfcce-110">作为发件人，您可以吊销直接从 Outlook 网页上发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="dfcce-111">本文介绍了可以进行吊销的情况以及执行操作的方法。</span><span class="sxs-lookup"><span data-stu-id="dfcce-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="dfcce-112">您可以撤销的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="dfcce-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="dfcce-113">如果收件人收到基于链接的、品牌加密的电子邮件，则管理员和邮件发件人可以撤销加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="dfcce-114">如果收件人在受支持的 Outlook 客户端中收到本机内嵌体验，则无法撤消该邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="dfcce-115">收件人是否收到基于链接的体验或内嵌体验取决于收件人标识类型： Office 365 和 Microsoft 帐户收件人 (例如，outlook.com 用户) 在受支持的 Outlook 客户端中获取内嵌体验。</span><span class="sxs-lookup"><span data-stu-id="dfcce-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="dfcce-116">所有其他收件人类型（如 Gmail 和 Yahoo 收件人）都获得了基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="dfcce-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="dfcce-117">管理员和邮件发件人可以使用从 web 上的 Outlook 直接应用的加密来吊销加密邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="dfcce-118">例如，使用 "仅加密" 选项加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="显示 web 上的 Outlook 中的 &quot;仅加密&quot; 选项的屏幕截图。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="dfcce-120">已撤销加密电子邮件的收件人体验</span><span class="sxs-lookup"><span data-stu-id="dfcce-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="dfcce-121">一旦电子邮件被吊销，收件人通过 Office 365 邮件加密门户访问加密的电子邮件时，会收到错误消息： "邮件已被发件人吊销"。</span><span class="sxs-lookup"><span data-stu-id="dfcce-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![显示已吊销加密电子邮件的屏幕截图。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="dfcce-123">如何撤消已发送的加密邮件</span><span class="sxs-lookup"><span data-stu-id="dfcce-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="dfcce-124">若要撤消已发送的加密邮件，请完成以下步骤</span><span class="sxs-lookup"><span data-stu-id="dfcce-124">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="dfcce-125">在 web 上的 Outlook 中，在 " **已发送** " 文件夹中浏览到要撤消的邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-125">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="dfcce-126">如果邮件是可吊销的，您将在邮件顶部看到 "删除外部访问" 链接。</span><span class="sxs-lookup"><span data-stu-id="dfcce-126">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="显示 web 上的 Outlook 中的 &quot;仅加密&quot; 选项的屏幕截图。":::

2. <span data-ttu-id="dfcce-128">单击 " **删除外部访问权限** " 以撤消邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-128">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="dfcce-129">该消息显示其状态为 "已吊销"。</span><span class="sxs-lookup"><span data-stu-id="dfcce-129">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="显示 web 上的 Outlook 中的 &quot;仅加密&quot; 选项的屏幕截图。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="dfcce-131">如何以管理员身份撤消加密邮件</span><span class="sxs-lookup"><span data-stu-id="dfcce-131">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="dfcce-132">Microsoft 365 管理员按照以下常规步骤撤销符合条件的加密电子邮件：</span><span class="sxs-lookup"><span data-stu-id="dfcce-132">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="dfcce-133">获取电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="dfcce-133">Get the Message ID of the email.</span></span>
- <span data-ttu-id="dfcce-134">验证您是否可以撤消邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-134">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="dfcce-135">吊销邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-135">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="dfcce-136">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="dfcce-136">Step 1.</span></span> <span data-ttu-id="dfcce-137">获取电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="dfcce-137">Obtain the Message ID of the email</span></span>

<span data-ttu-id="dfcce-138">在您可以撤销加密邮件之前，请先收集邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="dfcce-138">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="dfcce-139">MessageId 的格式通常为：</span><span class="sxs-lookup"><span data-stu-id="dfcce-139">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="dfcce-140">有多种方法可查找要吊销的电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="dfcce-140">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="dfcce-141">本节介绍了几个选项，但您可以使用任何提供该 ID 的方法。</span><span class="sxs-lookup"><span data-stu-id="dfcce-141">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="dfcce-142">使用安全 &amp; 合规性中心中的邮件跟踪来标识要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="dfcce-142">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="dfcce-143">[在安全 & 合规中心中使用新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)，按发件人或收件人搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-143">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="dfcce-144">找到电子邮件后，选择它以显示 **邮件跟踪详细信息** 窗格。</span><span class="sxs-lookup"><span data-stu-id="dfcce-144">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="dfcce-145">展开 **详细信息** 以查找邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="dfcce-145">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="dfcce-146">在安全合规中心中使用 Office 邮件加密报告确定要吊销的电子邮件的邮件 ID &amp;</span><span class="sxs-lookup"><span data-stu-id="dfcce-146">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="dfcce-147">在 "安全 &amp; 合规性中心" 中，导航到 " **邮件加密" 报告**。</span><span class="sxs-lookup"><span data-stu-id="dfcce-147">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="dfcce-148">有关此报告的信息，请参阅 [查看安全 &amp; 合规性中心中的电子邮件安全报告](../security/office-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="dfcce-148">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="dfcce-149">选择 " **查看详细信息** " 表，并确定要撤消的邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-149">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="dfcce-150">双击邮件以查看包含邮件 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dfcce-150">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="dfcce-151">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="dfcce-151">Step 2.</span></span> <span data-ttu-id="dfcce-152">验证邮件是否可吊销</span><span class="sxs-lookup"><span data-stu-id="dfcce-152">Verify that the mail is revocable</span></span>

<span data-ttu-id="dfcce-153">若要验证是否可以撤消邮件，请检查安全合规性中心的 **详细信息** 表中的加密报告中是否显示 "吊销状态" 字段 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="dfcce-153">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="dfcce-154">若要验证是否可以使用 Windows PowerShell 撤消特定的电子邮件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="dfcce-154">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="dfcce-155">使用组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="dfcce-155">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="dfcce-156">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="dfcce-156">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="dfcce-157">运行 OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dfcce-157">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="dfcce-158">此命令返回邮件的主题以及邮件是否是不可吊销的。</span><span class="sxs-lookup"><span data-stu-id="dfcce-158">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="dfcce-159">例如，</span><span class="sxs-lookup"><span data-stu-id="dfcce-159">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="dfcce-160">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="dfcce-160">Step 3.</span></span> <span data-ttu-id="dfcce-161">撤销邮件</span><span class="sxs-lookup"><span data-stu-id="dfcce-161">Revoke the mail</span></span>

<span data-ttu-id="dfcce-162">一旦您知道要吊销的电子邮件的邮件 ID，并且已验证该邮件是可吊销的，则可以使用安全 &amp; 合规性中心或 Windows PowerShell 吊销该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dfcce-162">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="dfcce-163">使用安全 &amp; 合规中心撤销邮件</span><span class="sxs-lookup"><span data-stu-id="dfcce-163">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="dfcce-164">使用组织中具有全局管理员权限的工作或学校帐户，连接到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="dfcce-164">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="dfcce-165">在 **加密报告**中，在邮件的 **详细信息** 表中，选择 " **撤消邮件**"。</span><span class="sxs-lookup"><span data-stu-id="dfcce-165">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="dfcce-166">若要使用 Windows PowerShell 吊销电子邮件，请使用 OMEMessageRevocation cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dfcce-166">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="dfcce-167">使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="dfcce-167">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="dfcce-168">运行 OMEMessageRevocation cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dfcce-168">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="dfcce-169">若要检查电子邮件是否已被吊销，请运行 OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dfcce-169">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="dfcce-170">如果吊销成功，则 cmdlet 将返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="dfcce-170">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="dfcce-171">有关 Office 365 高级邮件加密的详细信息</span><span class="sxs-lookup"><span data-stu-id="dfcce-171">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="dfcce-172">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="dfcce-172">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="dfcce-173">Office 365 高级邮件加密-电子邮件过期</span><span class="sxs-lookup"><span data-stu-id="dfcce-173">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="dfcce-174">邮件策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="dfcce-174">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
