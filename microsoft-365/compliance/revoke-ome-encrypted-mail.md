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
ms.date: 02/28/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作为管理员，您可以吊销使用 Office 365 高级邮件加密进行加密的某些电子邮件。
ms.openlocfilehash: 271aa1b3644983907c341cf7f9ad6d526597ad59
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626488"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="92ecb-103">撤销由高级邮件加密加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="92ecb-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="92ecb-104">电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="92ecb-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="92ecb-105">Office 365 高级邮件加密包含在[Microsoft 365 企业版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 e5 （非盈利员工定价）、Office 365 企业版 E5 （非盈利员工定价）和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="92ecb-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="92ecb-106">如果您的组织有一个不包含 Office 365 高级邮件加密的订阅，则可以使用 microsoft 365 E5 兼容性 SKU 附加 Microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Microsoft 365 高级合规性 SKU 外接程序（microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Office 365 Sku 购买它。</span><span class="sxs-lookup"><span data-stu-id="92ecb-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="92ecb-107">本文是有关[Office 365 邮件加密](ome.md)的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="92ecb-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="92ecb-108">如果使用 Office 365 高级邮件加密对邮件进行了加密，并且您是 Microsoft 365 管理员，则可以在特定条件下撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="92ecb-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="92ecb-109">本文介绍了可以进行吊销的情况以及执行操作的方法。</span><span class="sxs-lookup"><span data-stu-id="92ecb-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="92ecb-110">您可以撤销的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="92ecb-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="92ecb-111">如果收件人收到基于链接的、品牌加密的电子邮件，则可以撤销加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="92ecb-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="92ecb-112">如果收件人在受支持的 Outlook 客户端中收到了本机内嵌体验，则无法撤销这些。</span><span class="sxs-lookup"><span data-stu-id="92ecb-112">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke those.</span></span>

<span data-ttu-id="92ecb-113">收件人是否收到基于链接的体验或内嵌体验取决于收件人标识类型： Office 365 和 Microsoft 帐户收件人（例如，outlook.com 用户）在支持的 Outlook 客户端中获取内嵌体验。</span><span class="sxs-lookup"><span data-stu-id="92ecb-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="92ecb-114">所有其他收件人类型（如 Gmail 收件人）都获得了基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="92ecb-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="92ecb-115">已撤销加密电子邮件的收件人体验</span><span class="sxs-lookup"><span data-stu-id="92ecb-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="92ecb-116">一旦电子邮件被吊销，收件人通过 Office 365 邮件加密门户访问加密的电子邮件时，会收到错误消息： "邮件已被发件人吊销"。</span><span class="sxs-lookup"><span data-stu-id="92ecb-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![显示已吊销加密电子邮件的屏幕截图。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="92ecb-118">如何撤销加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="92ecb-118">How to revoke an encrypted email</span></span>

<span data-ttu-id="92ecb-119">Microsoft 365 管理员按照以下常规步骤撤销符合条件的加密电子邮件：</span><span class="sxs-lookup"><span data-stu-id="92ecb-119">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="92ecb-120">获取电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="92ecb-120">Get the Message ID of the email.</span></span>
- <span data-ttu-id="92ecb-121">验证您是否可以撤消邮件。</span><span class="sxs-lookup"><span data-stu-id="92ecb-121">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="92ecb-122">吊销邮件。</span><span class="sxs-lookup"><span data-stu-id="92ecb-122">Revoke the mail.</span></span>

<span data-ttu-id="92ecb-123">有关吊销过程中每个步骤的详细说明，请继续阅读。</span><span class="sxs-lookup"><span data-stu-id="92ecb-123">Keep reading for in-depth instructions for each step in the revocation process.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="92ecb-124">第 1 步：</span><span class="sxs-lookup"><span data-stu-id="92ecb-124">Step 1.</span></span> <span data-ttu-id="92ecb-125">获取电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="92ecb-125">Obtain the Message ID of the email</span></span>

<span data-ttu-id="92ecb-126">在您可以撤销加密邮件之前，请先收集邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="92ecb-126">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="92ecb-127">MessageId 的格式通常为：</span><span class="sxs-lookup"><span data-stu-id="92ecb-127">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="92ecb-128">有多种方法可查找要吊销的电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="92ecb-128">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="92ecb-129">本节介绍了几个选项，但您可以使用任何提供该 ID 的方法。</span><span class="sxs-lookup"><span data-stu-id="92ecb-129">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="92ecb-130">使用安全&amp;合规性中心中的邮件跟踪来标识要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="92ecb-130">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="92ecb-131">[在安全 & 合规中心中使用新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)，按发件人或收件人搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="92ecb-131">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="92ecb-132">找到电子邮件后，选择它以显示**邮件跟踪详细信息**窗格。</span><span class="sxs-lookup"><span data-stu-id="92ecb-132">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="92ecb-133">展开**详细信息**以查找邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="92ecb-133">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="92ecb-134">在安全&amp;合规中心中使用 Office 邮件加密报告确定要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="92ecb-134">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="92ecb-135">在 "安全&amp;合规性中心" 中，导航到 "**邮件加密" 报告**。</span><span class="sxs-lookup"><span data-stu-id="92ecb-135">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="92ecb-136">有关此报告的信息，请参阅[查看&amp;安全合规性中心中的电子邮件安全报告](../security/office-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="92ecb-136">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="92ecb-137">选择 "**查看详细信息**" 表，并确定要撤消的邮件。</span><span class="sxs-lookup"><span data-stu-id="92ecb-137">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="92ecb-138">双击邮件以查看包含邮件 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="92ecb-138">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="92ecb-139">第 2 步：</span><span class="sxs-lookup"><span data-stu-id="92ecb-139">Step 2.</span></span> <span data-ttu-id="92ecb-140">验证邮件是否可吊销</span><span class="sxs-lookup"><span data-stu-id="92ecb-140">Verify that the mail is revocable</span></span>

<span data-ttu-id="92ecb-141">若要验证是否可以撤消邮件，请检查安全&amp;合规性中心的**详细信息**表中的加密报告中是否显示 "吊销状态" 字段。</span><span class="sxs-lookup"><span data-stu-id="92ecb-141">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="92ecb-142">若要验证是否可以使用 Windows PowerShell 撤消特定的电子邮件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="92ecb-142">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="92ecb-143">使用组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="92ecb-143">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="92ecb-144">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="92ecb-144">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="92ecb-145">运行 OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92ecb-145">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="92ecb-146">此命令返回邮件的主题以及邮件是否是不可吊销的。</span><span class="sxs-lookup"><span data-stu-id="92ecb-146">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="92ecb-147">For example,</span><span class="sxs-lookup"><span data-stu-id="92ecb-147">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="92ecb-148">第 3 步：</span><span class="sxs-lookup"><span data-stu-id="92ecb-148">Step 3.</span></span> <span data-ttu-id="92ecb-149">撤销邮件</span><span class="sxs-lookup"><span data-stu-id="92ecb-149">Revoke the mail</span></span>

<span data-ttu-id="92ecb-150">一旦您知道要吊销的电子邮件的邮件 ID，并且已验证该邮件是可吊销的，则可以使用安全&amp;合规性中心或 Windows PowerShell 吊销该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="92ecb-150">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="92ecb-151">使用安全&amp;合规中心撤销邮件</span><span class="sxs-lookup"><span data-stu-id="92ecb-151">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="92ecb-152">使用组织中具有全局管理员权限的工作或学校帐户，连接到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="92ecb-152">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="92ecb-153">在**加密报告**中，在邮件的**详细信息**表中，选择 "**撤消邮件**"。</span><span class="sxs-lookup"><span data-stu-id="92ecb-153">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="92ecb-154">若要使用 Windows PowerShell 吊销电子邮件，请使用 OMEMessageRevocation cmdlet。</span><span class="sxs-lookup"><span data-stu-id="92ecb-154">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="92ecb-155">使用组织中具有全局管理员权限的工作或学校帐户，[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="92ecb-155">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="92ecb-156">运行 OMEMessageRevocation cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92ecb-156">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="92ecb-157">若要检查电子邮件是否已被吊销，请运行 OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92ecb-157">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="92ecb-158">如果吊销成功，则 cmdlet 将返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="92ecb-158">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="92ecb-159">有关 Office 365 高级邮件加密的详细信息</span><span class="sxs-lookup"><span data-stu-id="92ecb-159">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="92ecb-160">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="92ecb-160">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="92ecb-161">Office 365 高级邮件加密-电子邮件过期</span><span class="sxs-lookup"><span data-stu-id="92ecb-161">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="92ecb-162">邮件策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="92ecb-162">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
