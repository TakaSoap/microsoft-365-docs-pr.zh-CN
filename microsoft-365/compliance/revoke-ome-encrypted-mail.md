---
title: 撤销使用 Office 365 高级邮件加密进行加密的电子邮件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/8/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作为 Office 365 管理员，您可以吊销使用 Office 365 高级邮件加密进行加密的某些电子邮件。
ms.openlocfilehash: 9d694c200df161c0a52884ded14d29908376a9b7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597599"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="d6111-103">撤销使用 Office 365 高级邮件加密进行加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="d6111-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="d6111-104">电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="d6111-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="d6111-105">Office 365 高级邮件加密包含在[Microsoft 365 企业版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 e5 （非盈利员工定价）、Office 365 企业版 E5 （非盈利员工定价）和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="d6111-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="d6111-106">如果您的组织有一个不包含 Office 365 高级邮件加密的订阅，则可以使用 microsoft 365 E5 兼容性 SKU 附加项购买 Microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Office 365 高级适用于 Microsoft 365 E3、Microsoft 365 E3 （非盈利员工定价）或 Office 365 Sku 的合规性 SKU 外接程序。</span><span class="sxs-lookup"><span data-stu-id="d6111-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="d6111-107">本文是有关[Office 365 邮件加密](ome.md)的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="d6111-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="d6111-108">如果使用 Office 365 高级邮件加密对邮件进行了加密，并且您是 Office 365 管理员，则可以在特定条件下吊销邮件。</span><span class="sxs-lookup"><span data-stu-id="d6111-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="d6111-109">本文介绍了可以进行吊销的情况以及执行操作的方法。</span><span class="sxs-lookup"><span data-stu-id="d6111-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="d6111-110">您可以撤销的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="d6111-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="d6111-111">如果收件人收到基于链接的、品牌加密的电子邮件，则可以撤销加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d6111-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="d6111-112">如果收件人在受支持的 Outlook 客户端中收到本机内嵌体验，则无法撤消这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d6111-112">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="d6111-113">收件人是否收到基于链接的体验或内嵌体验取决于收件人标识类型： Office 365 和 Microsoft 帐户收件人（例如，outlook.com 用户）在支持的 Outlook 客户端中获取内嵌体验。</span><span class="sxs-lookup"><span data-stu-id="d6111-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="d6111-114">所有其他收件人类型（如 Gmail 收件人）都获得了基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="d6111-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="d6111-115">已撤销加密电子邮件的收件人体验</span><span class="sxs-lookup"><span data-stu-id="d6111-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="d6111-116">一旦电子邮件被吊销，收件人通过 Office 365 邮件加密门户访问加密的电子邮件时，会收到错误消息： "邮件已被发件人吊销"。</span><span class="sxs-lookup"><span data-stu-id="d6111-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![显示已吊销加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="d6111-118">如何撤销加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="d6111-118">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="d6111-119">第 1 步：</span><span class="sxs-lookup"><span data-stu-id="d6111-119">Step 1.</span></span> <span data-ttu-id="d6111-120">获取电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="d6111-120">Obtain the Message ID of the email</span></span>

<span data-ttu-id="d6111-121">在撤销加密邮件之前，您可以收集邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="d6111-121">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="d6111-122">MessageId 的格式通常为：</span><span class="sxs-lookup"><span data-stu-id="d6111-122">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="d6111-123">有多种方法可查找要吊销的电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="d6111-123">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="d6111-124">本节介绍了几个选项，但您可以使用任何提供该 ID 的方法。</span><span class="sxs-lookup"><span data-stu-id="d6111-124">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="d6111-125">使用安全&amp;合规性中心中的邮件跟踪来标识要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="d6111-125">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d6111-126">[在 Office 365 安全 & 合规中心中使用新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)，按发件人或收件人搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d6111-126">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="d6111-127">找到电子邮件后，选择它以显示**邮件跟踪详细信息**窗格。</span><span class="sxs-lookup"><span data-stu-id="d6111-127">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="d6111-128">展开**详细信息**以查找邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="d6111-128">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="d6111-129">在安全&amp;合规中心中使用 Office 邮件加密报告确定要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="d6111-129">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d6111-130">在 "安全&amp;合规性中心" 中，导航到 "**邮件加密" 报告**。</span><span class="sxs-lookup"><span data-stu-id="d6111-130">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="d6111-131">有关此报告的信息，请参阅[查看&amp;安全合规性中心中的电子邮件安全报告](../security/office-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="d6111-131">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="d6111-132">选择 "**查看详细信息**" 表，并确定要撤消的邮件。</span><span class="sxs-lookup"><span data-stu-id="d6111-132">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="d6111-133">双击邮件以查看包含邮件 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d6111-133">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="d6111-134">第 2 步：</span><span class="sxs-lookup"><span data-stu-id="d6111-134">Step 2.</span></span> <span data-ttu-id="d6111-135">验证邮件是否可吊销</span><span class="sxs-lookup"><span data-stu-id="d6111-135">Verify that the mail is revocable</span></span>

<span data-ttu-id="d6111-136">若要验证是否可以撤消邮件，请检查安全&amp;合规性中心的**详细信息**表中的加密报告中是否显示 "吊销状态" 字段。</span><span class="sxs-lookup"><span data-stu-id="d6111-136">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="d6111-137">若要验证是否可以使用 Windows Powershell 撤消特定的电子邮件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d6111-137">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="d6111-138">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d6111-138">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="d6111-139">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="d6111-139">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d6111-140">运行 OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6111-140">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="d6111-141">这将返回邮件的主题以及邮件是否是不可吊销的。</span><span class="sxs-lookup"><span data-stu-id="d6111-141">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="d6111-142">For example,</span><span class="sxs-lookup"><span data-stu-id="d6111-142">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="d6111-143">第 3 步：</span><span class="sxs-lookup"><span data-stu-id="d6111-143">Step 3.</span></span> <span data-ttu-id="d6111-144">撤销邮件</span><span class="sxs-lookup"><span data-stu-id="d6111-144">Revoke the mail</span></span>

<span data-ttu-id="d6111-145">一旦您知道要吊销的电子邮件的邮件 ID，并且已验证该邮件是可吊销的，则可以使用安全&amp;合规性中心或 Windows Powershell 吊销该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d6111-145">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="d6111-146">使用安全&amp;合规中心撤销邮件</span><span class="sxs-lookup"><span data-stu-id="d6111-146">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="d6111-147">若要在安全&amp;合规中心中撤销电子邮件，请在加密报告中的邮件的**详细信息**表中，选择 "**撤消邮件**"。</span><span class="sxs-lookup"><span data-stu-id="d6111-147">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="d6111-148">您可以使用 Windows Powershell 吊销电子邮件，方法是使用 OMEMessageRevocation cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d6111-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="d6111-149">[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="d6111-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d6111-150">运行 OMEMessageRevocation cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6111-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="d6111-151">若要检查电子邮件是否已被吊销，请运行 OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d6111-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="d6111-152">如果吊销成功，则 cmdlet 将返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="d6111-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="d6111-153">有关 Office 365 高级邮件加密的详细信息</span><span class="sxs-lookup"><span data-stu-id="d6111-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="d6111-154">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="d6111-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="d6111-155">Office 365 高级邮件加密-电子邮件过期</span><span class="sxs-lookup"><span data-stu-id="d6111-155">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="d6111-156">邮件策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="d6111-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
