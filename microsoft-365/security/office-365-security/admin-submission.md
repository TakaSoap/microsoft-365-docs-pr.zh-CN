---
title: 管理员提交、提交、垃圾邮件问题、误报、提交网络钓鱼、提交电子邮件进行扫描、在 Office 365 中使用可疑电子邮件、扫描邮件、使用 Microsoft 扫描网络钓鱼、使用 microsoft 扫描垃圾邮件、提交电子邮件、提交电子邮件、dodgy 电子邮件、错误演员邮件、可疑、不受信任的邮件、向 microsoft 报告诈骗电子邮件、向 microsoft 报告诈骗电子邮件，将电子邮件中的恶意软件报告给 Microsoft，收件箱中的垃圾邮件，电子邮件中的病毒
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
ms.collection:
- M365-security-compliance
description: 了解如何将可疑电子邮件、可疑的网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、Url 和文件从公司的公司提交到 Microsoft 进行扫描。
ms.openlocfilehash: 2d86555854f9babd202764f1bad8b548daf52c70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631377"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="222fc-103">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="222fc-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="222fc-104">如果您是使用 Exchange Online 中的邮箱的 Microsoft 365 组织中的管理员，则可以使用安全 & 合规性中心中的提交门户将电子邮件、Url 和附件提交给 Microsoft 进行扫描。</span><span class="sxs-lookup"><span data-stu-id="222fc-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="222fc-105">当您提交电子邮件时，您将获得可能允许传入的电子邮件进入租户的任何策略的信息，以及对邮件中的任何 Url 和附件的检查。</span><span class="sxs-lookup"><span data-stu-id="222fc-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="222fc-106">可能允许邮件的策略包括单个用户的安全发件人列表和租户级策略，如 Exchange 邮件流规则（也称为传输规则）。</span><span class="sxs-lookup"><span data-stu-id="222fc-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="222fc-107">有关向 Microsoft 提交电子邮件、Url 和附件的其他方法，请参阅</span><span class="sxs-lookup"><span data-stu-id="222fc-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="222fc-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="222fc-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="222fc-109">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="222fc-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="222fc-110">若要直接转到**提交**页面，请<https://protection.office.com/reportsubmission>使用。</span><span class="sxs-lookup"><span data-stu-id="222fc-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="222fc-111">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="222fc-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="222fc-112">若要连接到独立 Exchange Online Protection，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="222fc-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="222fc-113">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="222fc-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="222fc-114">若要添加、修改和删除反垃圾邮件策略，您必须是 "**组织管理**"、"**安全管理员**" 或 "**安全读者**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="222fc-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="222fc-115">有关安全 & 合规中心中的角色组的详细信息，请参阅[security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="222fc-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="222fc-116">有关用户如何向 Microsoft 提交邮件和文件的详细信息，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="222fc-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-scanning"></a><span data-ttu-id="222fc-117">如何将可疑内容定向到 Microsoft 扫描</span><span class="sxs-lookup"><span data-stu-id="222fc-117">How to direct suspicious content to Microsoft scanning</span></span>

<span data-ttu-id="222fc-118">若要将内容提交给 Microsoft，请单击 "提交" 页面左上角的 "**新建提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="222fc-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="222fc-119">将显示页面右侧的浮出控件，其中包含用于提交电子邮件、URL 或文件的选项。</span><span class="sxs-lookup"><span data-stu-id="222fc-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="222fc-120">将可疑电子邮件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="222fc-120">Submit a questionable email to Microsoft</span></span>

![电子邮件提交示例](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="222fc-122">若要提交电子邮件，请选择 "**电子邮件**"，并指定电子邮件**网络邮件 ID**或上载电子邮件文件。</span><span class="sxs-lookup"><span data-stu-id="222fc-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="222fc-123">指定您想要运行策略检查的收件人。</span><span class="sxs-lookup"><span data-stu-id="222fc-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="222fc-124">策略检查将确定电子邮件是否因用户或租户级别策略而绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="222fc-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="222fc-125">指定是否应阻止电子邮件。</span><span class="sxs-lookup"><span data-stu-id="222fc-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="222fc-126">如果应阻止该电子邮件，请指定是否应将其阻止为垃圾邮件、网络钓鱼或恶意软件。</span><span class="sxs-lookup"><span data-stu-id="222fc-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="222fc-127">如果您不确定可能的类型，请使用您的最佳判断。</span><span class="sxs-lookup"><span data-stu-id="222fc-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="222fc-128">如果由于提交策略而绕过筛选器，你将看到有关该策略的信息。</span><span class="sxs-lookup"><span data-stu-id="222fc-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="222fc-129">如果筛选器由于一个或多个策略而被绕过，扫描将在几分钟内完成。</span><span class="sxs-lookup"><span data-stu-id="222fc-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="222fc-130">您将通过单击状态链接来查看有关提交的其他信息。</span><span class="sxs-lookup"><span data-stu-id="222fc-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="222fc-131">这包括策略检查结果和重新扫描判定结果。</span><span class="sxs-lookup"><span data-stu-id="222fc-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="222fc-132">注意这不会再次通过 Office 365 ATP 完全筛选堆栈运行电子邮件，但会根据邮件、URL 或文件的某些属性运行部分重新扫描。</span><span class="sxs-lookup"><span data-stu-id="222fc-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="222fc-133">单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="222fc-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="222fc-134">向 Microsoft 发送可疑 URL</span><span class="sxs-lookup"><span data-stu-id="222fc-134">Send a suspect URL to Microsoft</span></span>

![电子邮件提交示例](../../media/submission-url-flyout.png)

1. <span data-ttu-id="222fc-136">若要提交 URL，请从浮出控件中选择**url** 。</span><span class="sxs-lookup"><span data-stu-id="222fc-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="222fc-137">键入完整 URL，包括协议（**https://**）。</span><span class="sxs-lookup"><span data-stu-id="222fc-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="222fc-138">如果您选择了 "**应该已经过筛选**"，请指定 URL 是否为网络钓鱼或恶意软件。</span><span class="sxs-lookup"><span data-stu-id="222fc-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="222fc-139">单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="222fc-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="222fc-140">将可疑文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="222fc-140">Submit a suspected file to Microsoft</span></span>

![电子邮件提交示例](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="222fc-142">若要提交文件，请从浮出控件中选择**文件**，并上载要扫描的文件。</span><span class="sxs-lookup"><span data-stu-id="222fc-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="222fc-143">单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="222fc-143">Click the **Submit** button.</span></span>
